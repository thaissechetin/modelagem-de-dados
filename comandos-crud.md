# comandos CRUD SQL

## Resumo da sigla
- C -> CREATE  (INSERT, inserir dados)
- R -> READ (SELECT, leitura de dados)
- U -> UPDATE (UPDATE, atualuzar dados)
- D -> DELETE (DELETE, excluir dados)

## INSERT
INSERT INTO fabricantes(nome) VALUES ("Asus");
INSERT INTO fabricantes(nome) VALUES ("Dell");
INSERT INTO fabricantes(nome) VALUES ("Apple");
INSERT INTO fabricantes(nome) VALUES ("LG");

## forma abreviada do INSERT
INSERT INTO fabricantes(nome)
VALUES ("Samsung"), ("Microsoft"), ("Brastemp");

## Produtos

INSERT INTO produtos(nome, preco, quantidade, descricao, fabricante_id)
VALUES("TV Led", 2000, 5, "TV de última geração", 5);

INSERT INTO produtos(nome, preco, quantidade, descricao, fabricante_id)
VALUES("iPhone", 5500.79, 8, "Smartphone caro pra caramba", 3);

## SELECT

SELECT nome, preco FROM produtos;

SELECT nome, preco FROM produtos WHERE preco < 3000;

SELECT nome, preco FROM produtos
WHERE preco < 3000 AND preco > 2000;

SELECT nome, preco FROM produtos
WHERE fabricante_id = 3 OR fabricante_id = 1;

-- ordena por ordem crescente - padrão
SELECT nome, descricao FROM produtos
ORDER BY nome;

SELECT nome, descricao FROM produtos
ORDER BY nome DESC; -- ordem decrescente

SELECT nome, preco, quantidade, fabricante_id
FROM produtos;

SELECT
    produtos.nome AS produto,
    fabricantes.nome AS fabricante,
    produtos.preco,
    produtos.quantidade
FROM produtos INNER JOIN fabricantes
ON produtos.fabricante_id = fabricantes.id; 


-- INNER JOIN : comando que permite juntar uma ou mais tabelas que se relacionam;
-- ON: Comando para indicar a maneira como as tabelas são juntadas;
-- AS: comando que permite dar um apelido para as colunas;

## UPDATE 
UPDATE fabricantes SET nome = "LG do Brasil"
WHERE id = 4 -- SEMPRE USE WHERE, SEMPRE DÊ UMA CONDIÇÃO;

## DELETE

DELETE FROM produtos 
WHERE id = 5;