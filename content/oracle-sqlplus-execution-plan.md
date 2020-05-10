+++
title = "Getting query execution plan in Oracle sqlplus"
date = 2020-04-02
+++

{{ gist(url="https://gist.github.com/timgabets/fa11b840ea9cfd080c7c452e07951930") }}

The result is:
```
Execution Plan
----------------------------------------------------------
Plan hash value: 272002086
--------------------------------------------------------------------------
| Id | Operation | Name | Rows | Bytes | Cost (%CPU)| Time |
--------------------------------------------------------------------------
| 0 | SELECT STATEMENT | | 1 | 2 | 2 (0)| 00:00:01 |
| 1 | TABLE ACCESS FULL| DUAL | 1 | 2 | 2 (0)| 00:00:01 |
--------------------------------------------------------------------------
```
