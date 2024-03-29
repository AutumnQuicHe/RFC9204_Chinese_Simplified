---
title: "附录A. 静态表"
anchor: "Appendix_A_Static_Table"
weight: 10000
rank: "h1"
---

本表是通过分析2018年实际的互联网流量，过滤掉一些不受支持的和非标准的值，最后提取出最常见的头部字段来创建的。
受限于该创建方法，部分条目间可能出现矛盾，或存在相似但不完全一致的条目。
条目的顺序是经过优化的，这是为了将最常用的标头字段编码至最少的字节中。

{{% block_ref
indx="Table_4_Static_Table"
title="表4：静态表" %}}

| 索引  | 名称                                 | 值                                                       |
|:----|:-----------------------------------|:--------------------------------------------------------|
| 0   | `:authority`                       |                                                         |
| 1   | `:path`                            | `/`                                                     |
| 2   | `age`                              | `0`                                                     |
| 3   | `content-disposition`              |                                                         |
| 4   | `content-length`                   | `0`                                                     |
| 5   | `cookie`                           |                                                         |
| 6   | `date`                             |                                                         |
| 7   | `etag`                             |                                                         |
| 8   | `if-modified-since`                |                                                         |
| 9   | `if-none-match`                    |                                                         |
| 10  | `last-modified`                    |                                                         |
| 11  | `link`                             |                                                         |
| 12  | `location`                         |                                                         |
| 13  | `referer`                          |                                                         |
| 14  | `set-cookie`                       |                                                         |
| 15  | `:method`                          | `CONNECT`                                               |
| 16  | `:method`                          | `DELETE`                                                |
| 17  | `:method`                          | `GET`                                                   |
| 18  | `:method`                          | `HEAD`                                                  |
| 19  | `:method`                          | `OPTIONS`                                               |
| 20  | `:method`                          | `POST`                                                  |
| 21  | `:method`                          | `PUT`                                                   |
| 22  | `:scheme`                          | `http`                                                  |
| 23  | `:scheme`                          | `https`                                                 |
| 24  | `:status`                          | `103`                                                   |
| 25  | `:status`                          | `200`                                                   |
| 26  | `:status`                          | `304`                                                   |
| 27  | `:status`                          | `404`                                                   |
| 28  | `:status`                          | `503`                                                   |
| 29  | `accept`                           | `*/*`                                                   |
| 30  | `accept`                           | `application/dns-message`                               |
| 31  | `accept-encoding`                  | `gzip, deflate, br`                                     |
| 32  | `accept-ranges`                    | `bytes`                                                 |
| 33  | `access-control-allow-headers`     | `cache-control`                                         |
| 34  | `access-control-allow-headers`     | `content-type`                                          |
| 35  | `access-control-allow-origin`      | `*`                                                     |
| 36  | `cache-control`                    | `max-age=0`                                             |
| 37  | `cache-control`                    | `max-age=2592000`                                       |
| 38  | `cache-control`                    | `max-age=604800`                                        |
| 39  | `cache-control`                    | `no-cache`                                              |
| 40  | `cache-control`                    | `no-store`                                              |
| 41  | `cache-control`                    | `public, max-age=31536000`                              |
| 42  | `content-encoding`                 | `br`                                                    |
| 43  | `content-encoding`                 | `gzip`                                                  |
| 44  | `content-type`                     | `application/dns-message`                               |
| 45  | `content-type`                     | `application/javascript`                                |
| 46  | `content-type`                     | `application/json`                                      |
| 47  | `content-type`                     | `application/x-www-form-urlencoded`                     |
| 48  | `content-type`                     | `image/gif`                                             |
| 49  | `content-type`                     | `image/jpeg`                                            |
| 50  | `content-type`                     | `image/png`                                             |
| 51  | `content-type`                     | `text/css`                                              |
| 52  | `content-type`                     | `text/html; charset=utf-8`                              |
| 53  | `content-type`                     | `text/plain`                                            |
| 54  | `content-type`                     | `text/plain;charset=utf-8`                              |
| 55  | `range`                            | `bytes=0-`                                              |
| 56  | `strict-transport-security`        | `max-age=31536000`                                      |
| 57  | `strict-transport-security`        | `max-age=31536000; includesubdomains`                   |
| 58  | `strict-transport-security`        | `max-age=31536000; includesubdomains; preload`          |
| 59  | `vary`                             | `accept-encoding`                                       |
| 60  | `vary`                             | `origin`                                                |
| 61  | `x-content-type-options`           | `nosniff`                                               |
| 62  | `x-xss-protection`                 | `1; mode=block`                                         |
| 63  | `:status`                          | `100`                                                   |
| 64  | `:status`                          | `204`                                                   |
| 65  | `:status`                          | `206`                                                   |
| 66  | `:status`                          | `302`                                                   |
| 67  | `:status`                          | `400`                                                   |
| 68  | `:status`                          | `403`                                                   |
| 69  | `:status`                          | `421`                                                   |
| 70  | `:status`                          | `425`                                                   |
| 71  | `:status`                          | `500`                                                   |
| 72  | `accept-language`                  |                                                         |
| 73  | `access-control-allow-credentials` | `FALSE`                                                 |
| 74  | `access-control-allow-credentials` | `TRUE`                                                  |
| 75  | `access-control-allow-headers`     | `*`                                                     |
| 76  | `access-control-allow-methods`     | `get`                                                   |
| 77  | `access-control-allow-methods`     | `get, post, options`                                    |
| 78  | `access-control-allow-methods`     | `options`                                               |
| 79  | `access-control-expose-headers`    | `content-length`                                        |
| 80  | `access-control-request-headers`   | `content-type`                                          |
| 81  | `access-control-request-method`    | `get`                                                   |
| 82  | `access-control-request-method`    | `post`                                                  |
| 83  | `alt-svc`                          | `clear`                                                 |
| 84  | `authorization`                    |                                                         |
| 85  | `content-security-policy`          | `script-src 'none'; object-src 'none'; base-uri 'none'` |
| 86  | `early-data`                       | `1`                                                     |
| 87  | `expect-ct`                        |                                                         |
| 88  | `forwarded`                        |                                                         |
| 89  | `if-range`                         |                                                         |
| 90  | `origin`                           |                                                         |
| 91  | `purpose`                          | `prefetch`                                              |
| 92  | `server`                           |                                                         |
| 93  | `timing-allow-origin`              | `*`                                                     |
| 94  | `upgrade-insecure-requests`        | `1`                                                     |
| 95  | `user-agent`                       |                                                         |
| 96  | `x-forwarded-for`                  |                                                         |
| 97  | `x-frame-options`                  | `deny`                                                  |
| 98  | `x-frame-options`                  | `sameorigin`                                            |

{{% /block_ref %}}

在字段名称或字段值内部出现的所有换行符都是由于格式限制而产生的。
