---
{
    "title": "ARRAY_REVERSE_SORT",
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


## Description

Sort the elements in an array in descending order

## Syntax

```sql
ARRAY_REVERSE_SORT(<arr>)
```

## Parameters

| Parameter | Description |
|--|--|
| `<arr>` | Corresponding array |

## Return Value

Returns an array sorted in descending order. If the input array is NULL, it returns NULL. If the array element contains NULL, the output sorted array will put NULL at the end.

## Example

```sql
SELECT ARRAY_REVERSE_SORT([1, 2, 3, 6]),ARRAY_REVERSE_SORT([1, 4, 3, 5, NULL]),ARRAY_REVERSE_SORT([NULL]);
```

```text
+----------------------------------+----------------------------------------+----------------------------+
| array_reverse_sort([1, 2, 3, 6]) | array_reverse_sort([1, 4, 3, 5, NULL]) | array_reverse_sort([NULL]) |
+----------------------------------+----------------------------------------+----------------------------+
| [6, 3, 2, 1]                     | [5, 4, 3, 1, null]                     | [null]                     |
+----------------------------------+----------------------------------------+----------------------------+
```
