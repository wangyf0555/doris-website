---
{
    "title": "REGEXP",
    "language": "en"
}
---

<!-- 
Licensed to the Apache Software Foundation (ASF) under one
or more contributor license agreements.  See the NOTICE file
distributed with this work for additional information
regarding copyright ownership.  The ASF licenses this file
to you under the Apache License, Version 2.0 (the
"License"); you may not use this file except in compliance
with the License.  You may obtain a copy of the License at

  http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing,
software distributed under the License is distributed on an
"AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
KIND, either express or implied.  See the License for the
specific language governing permissions and limitations
under the License.
-->

## regexp
### description
#### syntax

`BOOLEAN regexp(VARCHAR str, VARCHAR pattern)`

Perform regular matching on the string str, return true if it matches, and return false if it doesn't match. pattern is a regular expression.

Character set matching requires the use of Unicode standard character classes. For example, to match Chinese, use `\p{Han}`.

### example

```sql
--- Find all data starting with 'billie' in the k1 field
mysql> select k1 from test where k1 regexp '^billie';
+--------------------+
| k1                 |
+--------------------+
| billie eillish     |
+--------------------+

--- Find all data ending with 'ok' in the k1 field:
mysql> select k1 from test where k1 regexp 'ok$';
+----------+
| k1       |
+----------+
| It's ok  |
+----------+

mysql> select regexp('这是一段中文This is a passage in English 1234567', '\\p{Han}');
+-----------------------------------------------------------------------------+
| ('这是一段中文This is a passage in English 1234567' regexp '\p{Han}')       |
+-----------------------------------------------------------------------------+
|                                                                           1 |
+-----------------------------------------------------------------------------+
```

### keywords
    REGEXP
