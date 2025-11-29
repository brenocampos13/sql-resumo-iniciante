# Resumo MySQL - Módulo Iniciante  
Resumo completo dos comandos básicos de SQL que todo estagiário/júnior precisa dominar.

## Comandos fundamentais
- `SELECT` → seleciona colunas  
- `FROM` → indica a tabela  
- `WHERE` → filtra linhas (antes do agrupamento)  
- `GROUP BY` → agrupa por categoria  
- `HAVING` → filtra depois do agrupamento (aceita alias e funções agregadas)  
- `ORDER BY` → ordena (ASC ou DESC)  
- `LIMIT` → limita linhas retornadas

## Operadores e padrões
- `AND`, `OR`, `NOT` (ou `<>`)  
- `LIKE '%abc'` → termina com abc  
- `LIKE 'abc%'` → começa com abc  
- `LIKE 'A___'` → começa com A + exatamente 3 caracteres  
- `DISTINCT` → remove duplicatas  
- `AS` → alias (nome temporário)

## Funções de agregação
- `COUNT()` → conta linhas  
- `AVG()`, `SUM()`, `MIN()`, `MAX()`  
- `LENGTH()` → tamanho da string

## Exemplos reais
```sql
-- Cidades com exatamente 5 letras
SELECT cidade FROM station WHERE LENGTH(cidade) = 5;

-- Média salarial por cargo só onde média > 7000
SELECT occupation, AVG(salary) AS media_salario
FROM employee_salary
GROUP BY occupation
HAVING media_salario > 7000;

-- Top 5 maiores salários
SELECT first_name, salary
FROM employee_salary
ORDER BY salary DESC
LIMIT 5;
