# SQL Cheatsheet

## SELECT

```sql
SELECT column1,column2,...
FROM table_name;
```

### DISTINCT

```sql
SELECT DISTINCT column1,column2,...
FROM table_name;
```

### WHERE

```sql
SELECT column1,column2,...
FROM table_name
WHERE condition;
```

> Operadores condicionais: =, !=, <, >, <=, >=, AND, OR.

Exemplo:

```sql
SELECT ... FROM ...
WHERE first_name = 'Nancy' AND last_name = 'Thomas';
```

### COUNT

```sql
SELECT COUNT(*) FROM table_name;
SELECT COUNT(column_name) FROM table_name;
SELECT COUNT(DISTINCT column_name) FROM table_name;
```

> `COUNT(column_name)`, diferente de `COUNT(*)`, não considera valores NULL.

### LIMIT

```sql
SELECT ... FROM ...
LIMIT 5;
```

### ORDER BY

```sql
SELECT ... FROM ...
ORDER BY column1 <ASC|DESC>, column2 <ASC|DESC>, ...;
```

### BETWEEN

```sql
SELECT ... FROM ...
WHERE column_name <NOT> BETWEEN ... AND ...;
```

### IN

```sql
SELECT ... FROM ...
WHERE column_name <NOT> IN (value1,value2,...);
```

```sql
SELECT ... FROM ...
WHERE column_name IN (SELECT ... FROM ...);
```

### LIKE

```sql
SELECT ... FROM ...
WHERE column_name LIKE 'pattern';
```

> Patterns: `%str, str%, %str% _str, str_, str_str, %str_`, etc.

- `%` Qualquer sequência de caracteres
- `_` Um único caractere

## AGGREGATE FUNCTIONS

### AVG, ROUND

```sql
SELECT AVG(column_name) FROM table_name;
SELECT ROUND(AVG(column_name),2) FROM table_name;
```

### MIN, MAX

```sql
SELECT MIN(column_name) FROM table_name;
SELECT MAX(column_name) FROM table_name;
```

### SUM

```sql
SELECT SUM(column_name) FROM table_name;
```

### GROUP BY

```sql
SELECT column1, aggregate_func(column2)
FROM table_name
GROUP BY column1;
```

Exemplo: Quantidade vendida de cada produto

```sql
SELECT product_id, SUM(qty)
FROM sales
GROUP BY product_id;
```
