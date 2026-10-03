# recursive-SQL
recursion using postgresql and syntax

    WITH [RECURSIVE] CTE_name AS 
      (
      SELECT query (Non Recursive query or the Base query)
        UNION [ALL]
      SELECT query (Recursive query using CTE_name [with a termination condition]
      )
