
# Sql_Hr_schema
with t as
(select Department_id, Sum(salary) as department_salary,(select  sum(salary) as SUM_SALARY from employees ) AS sum_salary from employees group by department_id)

select dep.department_name,t.department_salary,t.sum_salary from t inner join departments dep  on t.department_id=dep.department_id 
