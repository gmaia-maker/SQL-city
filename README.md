# SQL — SQLBolt

## Revisão 1 — Consultas SQL

Este repositório contém a resolução dos exercícios da **Revisão 1 do SQLBolt**, com foco na prática dos comandos básicos de consulta e ordenação de dados em SQL.

### Objetivos

* Praticar consultas com `SELECT`
* Utilizar filtros com `WHERE`
* Ordenar resultados com `ORDER BY`
* Trabalhar com ordenação crescente (`ASC`) e decrescente (`DESC`)
* Utilizar `LIMIT` para restringir a quantidade de resultados
* Utilizar `OFFSET` para selecionar registros a partir de uma determinada posição

---

## Base de dados

### Tabela: `cidades_norte_americanas`

| Cidade              | País           | População |  Latitude |   Longitude |
| ------------------- | -------------- | --------: | --------: | ----------: |
| Guadalajara         | México         | 1.500.800 | 20,659699 | -103,349609 |
| Toronto             | Canadá         | 2.795.060 | 43,653226 |  -79,383184 |
| Houston             | Estados Unidos | 2.195.914 | 29,760427 |  -95,369803 |
| Nova Iorque         | Estados Unidos | 8.405.837 | 40,712784 |  -74,005941 |
| Filadélfia          | Estados Unidos | 1.553.165 | 39,952584 |  -75,165222 |
| Havana              | Cuba           | 2.106.146 | 23,054070 |  -82,345189 |
| Cidade do México    | México         | 8.555.500 | 19,432608 |  -99,133208 |
| Fênix               | Estados Unidos | 1.513.367 | 33,448377 | -112,074037 |
| Los Angeles         | Estados Unidos | 3.884.307 | 34,052234 | -118,243685 |
| Ecatepec de Morelos | México         | 1.742.000 | 19,601841 |  -99,050674 |
| Montreal            | Canadá         | 1.717.767 | 45,501689 |  -73,567256 |
| Chicago             | Estados Unidos | 2.718.782 | 41,878114 |  -87,629798 |

---

## Consultas

### 1. Cidades canadenses

**Objetivo:** listar as cidades localizadas no Canadá e suas respectivas populações.

```sql
SELECT cidade, população
FROM cidades_norte_americanas
WHERE país = 'Canadá';
```

**Resultado esperado:**

| Cidade   | População |
| -------- | --------: |
| Toronto  | 2.795.060 |
| Montreal | 1.717.767 |

---

### 2. Cidades dos Estados Unidos por latitude

**Objetivo:** listar todas as cidades dos Estados Unidos ordenadas por latitude, do norte para o sul.

```sql
SELECT cidade, latitude
FROM cidades_norte_americanas
WHERE país = 'Estados Unidos'
ORDER BY latitude DESC;
```

---

### 3. Cidades a oeste de Chicago

**Objetivo:** listar as cidades localizadas a oeste de Chicago, ordenadas de oeste para leste.

```sql
SELECT cidade, longitude
FROM cidades_norte_americanas
WHERE longitude < -87.629798
ORDER BY longitude ASC;
```

---

### 4. Duas maiores cidades do México

**Objetivo:** identificar as duas cidades mexicanas com maior população.

```sql
SELECT cidade, população
FROM cidades_norte_americanas
WHERE país = 'México'
ORDER BY população DESC
LIMIT 2;
```

---

### 5. Terceira e quarta maiores cidades dos Estados Unidos

**Objetivo:** identificar a terceira e a quarta cidades mais populosas dos Estados Unidos.

```sql
SELECT cidade, população
FROM cidades_norte_americanas
WHERE país = 'Estados Unidos'
ORDER BY população DESC
LIMIT 2 OFFSET 2;
```

---

## Conteúdos praticados

| Comando    | Finalidade                                |
| ---------- | ----------------------------------------- |
| `SELECT`   | Selecionar dados                          |
| `WHERE`    | Filtrar registros                         |
| `ORDER BY` | Ordenar resultados                        |
| `ASC`      | Ordenação crescente                       |
| `DESC`     | Ordenação decrescente                     |
| `LIMIT`    | Limitar a quantidade de resultados        |
| `OFFSET`   | Pular determinada quantidade de registros |

---

## Fonte

Exercício baseado na **Revisão 1 do SQLBolt**.

**Status:** Exercício concluído
**Área:** Banco de Dados / SQL
**Nível:** Básico
