
Three queries have been provided for optimization. For each query we provide a writeup of our optimization approach:

query 1:

SELECT 
  c.c_mktsegment,
  COUNT(o.o_orderkey) AS num_orders, 
  SUM(li.l_quantity) AS total_quantity, 
  SUM(li.l_extendedprice) AS total_price
FROM lineitem li
JOIN orders o
  ON li.l_orderkey = o.o_orderkey
JOIN customer c 
  ON o.o_custkey = c.c_custkey
WHERE li.l_commitdate BETWEEN '1992-01-01T00:00:00Z' AND '1992-12-31T00:00:00Z'
GROUP BY c.c_mktsegment;


query 2:

SELECT COUNT(CASE WHEN L_SHIPDATE between '1992-07-05' and '1992-07-07' THEN 1 END)
FROM lineitem
;


query 3:

WITH customer_lifetime_value AS (
  SELECT
    c_custkey,
    c_name,
    c_address,
    c_nationkey,
    c_phone,
    c_acctbal,
    c_mktsegment,
    c_comment,
    SUM(o_totalprice) AS ltv
  FROM customer
  JOIN orders
    ON o_custkey = c_custkey
  GROUP BY 1, 2, 3, 4, 5, 6, 7, 8
)

SELECT
  r_name,
  MAX(ltv) AS best_customer_value
FROM region
JOIN nation
  ON n_regionkey = r_regionkey
JOIN customer_lifetime_value clv
  ON clv.c_nationkey = n_nationkey
GROUP BY 1
;




Here you can see the public schema of database: 

<img width="615" alt="Assignment 5 1 Image" src="https://user-images.githubusercontent.com/84368057/157164342-94e56128-6f07-4fd1-9b50-45350c127250.png">




The optimization approach are provided https://github.com/kayfilipp/optimize-sql-query-and-deploy-aws-cloudformation-stack/blob/main/Module_5_solution.pdf
