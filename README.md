# 1211. Queries Quality and Percentage
### Problem Description : [Queries Quality and Percentage](https://leetcode.com/problems/queries-quality-and-percentage/description/?envType=study-plan-v2&envId=top-sql-50)
## Solution
```sql
/* Write your T-SQL query statement below */
select
query_name,
round(avg(cast(rating as decimal) / position), 2) as quality,
round(sum(case when rating < 3 then 1 else 0 end) * 100.0 / count(*), 2) as poor_query_percentage
from
queries
group by
query_name
order by query_name asc
