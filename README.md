# BigDataSnowflake — лабораторная №1

Запуск пайплайна:

```powershell
cd путь\к\BDSnowflake-main
.\run.ps1
```

---

### PostgreSQL

```sql
SELECT COUNT(*) FROM staging.mock_data;

SELECT COUNT(*) FROM dw.fact_sales;

SELECT COUNT(*) FROM dw.dim_date;
SELECT COUNT(*) FROM dw.dim_customer;
SELECT COUNT(*) FROM dw.dim_product;
SELECT COUNT(*) FROM dw.dim_seller;
SELECT COUNT(*) FROM dw.dim_store;
SELECT COUNT(*) FROM dw.dim_supplier;

\dt dw.*

SELECT f.sale_sk, d.full_date, c.first_name, p.product_name, f.sale_total_price
FROM dw.fact_sales f
JOIN dw.dim_date d ON f.date_sk = d.date_sk
JOIN dw.dim_customer c ON f.customer_sk = c.customer_sk
JOIN dw.dim_product p ON f.product_sk = p.product_sk
LIMIT 10;
```
