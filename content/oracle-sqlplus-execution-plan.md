+++
title = "Getting query execution plan in Oracle sqlplus"
date = 2020-04-02
+++

```bash
$ rlwrap sqlplus64 login/password@DB
```

```sql
SQL> set autotrace traceonly explain;
SQL> set linesize 10000;
SQL> select * from dual;
```

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
