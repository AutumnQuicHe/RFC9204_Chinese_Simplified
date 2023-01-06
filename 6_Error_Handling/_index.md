---
title: "6. 错误处理"
anchor: "6_Error_Handling"
weight: 6000
rank: "h1"
---

为HTTP/3定义的以下错误码是为了指出QPACK中使得流或连接无法继续维持的错误。

QPACK_DECOMPRESSION_FAILED（值为`0x0200`）：

:   解码器无法解释编码字段组，且无法继续解码该字段组。

QPACK_ENCODER_STREAM_ERROR（值为`0x0201`）：

:   解码器无法解释在编码流上接收到的某条编码指令。

QPACK_DECODER_STREAM_ERROR（值为`0x0202`）：

:   编码器无法解释在解码流上接收到的某条解码指令。
