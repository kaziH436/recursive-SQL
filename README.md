# recursive-SQL
recursion using postgresql and syntax

    WITH [RECURSIVE] CTE_name AS 
      (
      SELECT query (Non Recursive query or the Base query)
        UNION or UNION [ALL]
      SELECT query (Recursive query using CTE_name [with a termination condition]
      )

## Display number from 1 to 10 without using any in built functions

    WITH [RECURSIVE] numbers AS 
      (
        SELECT 1 as n
        UNION
        select n + 1
        from numbers where n < 10 (why n<10? 
      )
    select * from numbers
