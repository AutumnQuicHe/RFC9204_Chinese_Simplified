---
title: "5. 配置"
anchor: "5_Configuration"
weight: 5000
rank: "h1"
---

QPACK defines two settings for the HTTP/3 SETTINGS frame:

QPACK为HTTP/3的**设置帧**定义了以下设置：

SETTINGS_QPACK_MAX_TABLE_CAPACITY (0x01):
The default value is zero. See Section 3.2 for usage. This is the equivalent of the SETTINGS_HEADER_TABLE_SIZE from HTTP/2.

SETTINGS_QPACK_MAX_TABLE_CAPACITY（值为`0x01`）：

:   默认值为零。有关用法详见[第3.2章]()。该设置与HTTP/2的`SETTINGS_HEADER_TABLE_SIZE`等价。

SETTINGS_QPACK_BLOCKED_STREAMS (0x07):
The default value is zero. See Section 2.1.2.

SETTINGS_QPACK_BLOCKED_STREAMS（值为`0x07`）：

:   默认值为零。详见[第2.1.2章]()。
