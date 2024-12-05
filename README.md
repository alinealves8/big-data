# big-data
repositorio para postagem mulheres tech
criando meu primeiro banco de dados

CREATE DATABASE senac_copacabana;



-- criando minha primeira tabela/entidade

CREATE TABLE alunos (

    matricula INTEGER PRIMARY KEY,

    nome_aluno TEXT NOT NULL,

    genero TEXT NOT NULL

);



-- injeção de dados-teste

INSERT INTO alunos VALUES (1, 'Marina', 'Feminino');

INSERT INTO alunos VALUES (2, 'Joana', 'Feminino');



-- consultando as injeções realizadas

SELECT * FROM alunos WHERE matricula=1;



-- ATIVIDADE: Crie uma nova tabela chamada professores

-- fazendo ao menos duas injeções de dados



-- inserindo uma chave estrangeira ao criar a tabela

-- opção 1: a tabela AINDA NÃO FOI CRIADA

CREATE TABLE professores (

    matricula_prof INTEGER PRIMARY KEY,

    matricula INT,

    nome_prof TEXT NOT NULL,

    eixo TEXT NOT NULL,

    CONSTRAINT fk_alunos

    FOREIGN KEY (matricula)

    REFERENCES alunos(matricula)

);



-- opção 2: a tabela JÁ FOI CRIADA

ALTER TABLE alunos

ADD CONSTRAINT professores

FOREIGN KEY (matricula_prof)

REFERENCES professores(matricula_prof);



-- modificando tabelas que já foram criadas

ALTER TABLE alunos

ADD email_contato VARCHAR(50);



-- comandos de exclusão:

DROP TABLE alunos;

DROP DATABASE senac_copacabana;



-- ATIVIDADE para avaliar na semana que vem:

-- criar tabelas 'alunos' e 'professores', fazendo pelo menos as

-- mesmas alterações de vínculo entre as duas e garantindo

-- que todas precisam estar relacionadas.

