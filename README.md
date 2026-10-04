# recursive-SQL
recursion using postgresql and syntax

    WITH [RECURSIVE] CTE_name AS 
      (
      SELECT query (Non Recursive query or the Base query)
        UNION or UNION [ALL]
      SELECT query (Recursive query using CTE_name [with a termination condition]
      )

## Display number from 1 to 10 without using any in built functions

    WITH RECURSIVE numbers AS 
      (
        SELECT 1 as n
        UNION
        select n + 1
        from numbers where n < 10
      )
    select * from numbers
    
## Find the hiearchy of employees under a given manager 'Asha'

    WITH RECURSIVE emp_hiearchy AS 
      (
        SELECT id, name, manager_id, designation
        from  emp_details where name='Asha'
        UNION
        select E.id, E.name, E.manager_id, E>designation
        from emp_hiearhy H
        join emp_details E on H.id = E.manager_id
      )
    select H2 as emp_id, H2.name as emp_name, E2.name as manager_name
    from emp_details H2 join emp_details E2 on E2.id= H2.manager_id
