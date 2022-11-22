---
title: "附录C. 单通编码算法样例"
anchor: "Appendix_C_Sample_Single_Pass_Encoding_Algorithm"
weight: 12000
rank: "h1"
---

Pseudocode for single-pass encoding, excluding handling of duplicates, non-blocking mode, available encoder stream flow control and reference tracking.

单通编码的伪代码，其中不包含对复制、非阻塞模式、编码器流的流量控制，以及引用追踪的处理。

{{% block_ref
indx="Pseudocode_c_1" %}}

```
# 辅助函数：
# ====
# 编码出一个指定前缀和长度的整型
# Encode an integer with the specified prefix and length
encodeInteger(buffer, prefix, value, prefixLength)

# 编码出一个可选静态索引名称还是动态索引名称的动态表插入指令（只能选择其一）
# Encode a dynamic table insert instruction with optional static
# or dynamic name index (but not both)
encodeInsert(buffer, staticNameIndex, dynamicNameIndex, fieldLine)

# 编码出一个使用静态索引的引用
# Encode a static index reference
encodeStaticIndexReference(buffer, staticIndex)

# 编码出一个使用相对于基点的动态索引的引用
# Encode a dynamic index reference relative to Base
encodeDynamicIndexReference(buffer, dynamicIndex, base)

# 编码出一个可选使用静态索引名称的明文
# Encode a literal with an optional static name index
encodeLiteral(buffer, staticNameIndex, fieldLine)

# 编码出一个使用相对于基点的动态索引名称的明文
# Encode a literal with a dynamic name index relative to Base
encodeDynamicLiteral(buffer, dynamicNameIndex, base, fieldLine)

# 编码算法
# Encoding Algorithm
# ====
base = dynamicTable.getInsertCount()
requiredInsertCount = 0
for line in fieldLines:
  staticIndex = staticTable.findIndex(line)
  if staticIndex is not None:
    encodeStaticIndexReference(streamBuffer, staticIndex)
    continue

  dynamicIndex = dynamicTable.findIndex(line)
  if dynamicIndex is None:
    # 没有匹配的条目，要么插入条目并引用索引，要么编码为明文
    # No matching entry.  Either insert+index or encode literal
    staticNameIndex = staticTable.findName(line.name)
    if staticNameIndex is None:
       dynamicNameIndex = dynamicTable.findName(line.name)

    if shouldIndex(line) and dynamicTable.canIndex(line):
      encodeInsert(encoderBuffer, staticNameIndex,
                   dynamicNameIndex, line)
      dynamicIndex = dynamicTable.add(line)

  if dynamicIndex is None:
    # 无法为它建立索引，使用明文
    # Could not index it, literal
    if dynamicNameIndex is not None:
      # 编码为使用动态索引名称的明文，可能超过基点
      # Encode literal with dynamic name, possibly above Base
      encodeDynamicLiteral(streamBuffer, dynamicNameIndex,
                           base, line)
      requiredInsertCount = max(requiredInsertCount,
                                dynamicNameIndex)
    else:
      # 编码出一个使用静态名称或明文名称的明文
      # Encodes a literal with a static name or literal name
      encodeLiteral(streamBuffer, staticNameIndex, line)
  else:
    # 对动态索引的引用
    # Dynamic index reference
    assert(dynamicIndex is not None)
    requiredInsertCount = max(requiredInsertCount, dynamicIndex)
    # 对`dynamicIndex`编码，可能超过基点
    # Encode dynamicIndex, possibly above Base
    encodeDynamicIndexReference(streamBuffer, dynamicIndex, base)

# 对前缀编码
# encode the prefix
if requiredInsertCount == 0:
  encodeInteger(prefixBuffer, 0x00, 0, 8)
  encodeInteger(prefixBuffer, 0x00, 0, 7)
else:
  wireRIC = (
    requiredInsertCount
    % (2 * getMaxEntries(maxTableCapacity))
  ) + 1;
  encodeInteger(prefixBuffer, 0x00, wireRIC, 8)
  if base >= requiredInsertCount:
    encodeInteger(prefixBuffer, 0x00,
                  base - requiredInsertCount, 7)
  else:
    encodeInteger(prefixBuffer, 0x80,
                  requiredInsertCount - base - 1, 7)

return encoderBuffer, prefixBuffer + streamBuffer
```

{{% /block_ref %}}

