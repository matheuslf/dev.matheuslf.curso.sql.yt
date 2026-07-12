# BANCO DE DADOS DAS AULAS PARA RESOLVER OS EXERCICIOS DA AULA 6

```sql
CREATE TABLE clientes (
   cod_cliente SERIAL PRIMARY KEY,
   nome_cliente VARCHAR(50) NOT NULL,
   sobrenome_cliente VARCHAR(50) NOT NULL
);

CREATE TABLE produtos (
   cod_produto SERIAL PRIMARY KEY,
   nome_produto VARCHAR(50) NOT NULL,
   descricao TEXT,
   preco NUMERIC(10,2) CHECK(preco > 0),
   qtde_estoque SMALLINT DEFAULT 0
);

CREATE TABLE pedidos (
   cod_pedido SERIAL PRIMARY KEY,
   cod_cliente INT REFERENCES clientes(cod_cliente),
   cod_produto INT REFERENCES produtos(cod_produto),
   qtde SMALLINT NOT NULL
);

INSERT INTO clientes (nome_cliente, sobrenome_cliente)
VALUES ('João', 'Silva');

INSERT INTO clientes (nome_cliente, sobrenome_cliente)
VALUES ('Maria', 'Oliveira');

INSERT INTO clientes (nome_cliente, sobrenome_cliente)
VALUES ('Pedro', 'Santos');

INSERT INTO clientes (nome_cliente, sobrenome_cliente)
VALUES ('Ana', 'Carvalho');

INSERT INTO clientes (nome_cliente, sobrenome_cliente)
VALUES ('Lucas', 'Moraes');

INSERT INTO produtos (nome_produto, descricao, preco, qtde_estoque)
VALUES ('Pizza Margherita', 'Pizza tradicional com molho de tomate e manjericão', 45.00, 10);

INSERT INTO produtos (nome_produto, descricao, preco, qtde_estoque)
VALUES ('Refrigerante Lata', 'Lata 350ml', 6.00, 50);

INSERT INTO produtos (nome_produto, descricao, preco, qtde_estoque)
VALUES ('Hambúrguer', 'Hambúrguer artesanal', 30.00, 20);

INSERT INTO produtos (nome_produto, descricao, preco, qtde_estoque)
VALUES ('Batata Frita', 'Porção de batata frita', 18.00, 15);

INSERT INTO produtos (nome_produto, descricao, preco, qtde_estoque)
VALUES ('Cerveja', 'Long Neck', 8.00, 25);

INSERT INTO produtos (cod_produto, nome_produto, descricao, preco, qtde_estoque)
VALUES (6, 'Detergente', 'Detergente líquido 500 ml', 1.89, 32);

INSERT INTO produtos (cod_produto, nome_produto, descricao, preco, qtde_estoque)
VALUES (7, 'Leite Integral', 'Leite interal caixa 1 litro', 6.90, 70);

INSERT INTO produtos (cod_produto, nome_produto, descricao, preco, qtde_estoque)
VALUES (8, 'Refrigerante', 'Garra de Refrigerante de 600 ml', 4.10, 14);

INSERT INTO produtos (cod_produto, nome_produto, descricao, preco, qtde_estoque)
VALUES (9, 'Refrigerante', 'Garra de Refrigerante de 1 litro', 50.00, 16);

INSERT INTO produtos (cod_produto, nome_produto, descricao, preco, qtde_estoque)
VALUES (10, 'Refrigerante', 'Lata de 350 ml', 2.99, 45);

INSERT INTO produtos (cod_produto, nome_produto, descricao, preco, qtde_estoque)
VALUES (11, 'Suco Integral', 'Suco Integral Caixa', 7.00, 100);

INSERT INTO produtos (cod_produto, nome_produto, descricao, preco, qtde_estoque)
VALUES (12, 'Margarina', NULL, 11.00, 70);

INSERT INTO pedidos (cod_cliente, cod_produto, qtde)
VALUES (1, 1, 2);

INSERT INTO pedidos (cod_cliente, cod_produto, qtde)
VALUES (2, 3, 1);

INSERT INTO pedidos (cod_cliente, cod_produto, qtde)
VALUES (1, 2, 3);

INSERT INTO pedidos (cod_cliente, cod_produto, qtde)
VALUES (3, 5, 4);

INSERT INTO pedidos (cod_cliente, cod_produto, qtde)
VALUES (4, 4, 1);
```

# EXERCICIOS AULA 6

1 Listar todos os clientes cadastrados, mostrando nome e sobrenome

2 Listar todos os produtos com preço maior que R$ 20,00

3 Listar os produtos ordenados pelo preço do mais caro para o mais barato.

4 Mostrar o nome e preço dos 3 produtos mais baratos.

5 Listar todos os pedidos, mostrando nome do cliente, nome do produto e
quantidade comprada

6 Listar todos os pedidos, mostrando nome do cliente (usando subquery),
nome do produto e quantidade comprada

7 Listar apenas os produtos que possuem estoque menor que 20 unidades.

8 Mostrar o valor total gasto pelo cliente 'João Silva' (somar preço ×
quantidade).

9 Mostrar a quantidade total de clientes cadastrados

10 Mostrar a quantidade de produtos com preço maior que R$ 20,00

11 Mostrar o preço médio dos produtos

12 Mostrar o produto mais caro e o mais barato

13 Mostrar o valor total de vendas (preço × quantidade)

14 Mostrar o valor total gasto por cada cliente

15 Mostrar apenas os clientes que gastaram mais de R$ 100

16 Mostrar todos os produtos que já foram vendidos (usando
DISTINCT )

17 Mostrar todos os produtos que possuem pedidos (usando subconsulta)

18 Mostrar o cliente que mais gastou (usando subconsulta com
MAX )
