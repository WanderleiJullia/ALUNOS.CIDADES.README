# ALUNOS.CIDADES.README
O Exercício tem objetivo de realizar a junção de dados de duas tabelas diferentes. 

![Captura de tela 2023-10-09 165537](https://github.com/WanderleiJullia/ALUNOS.CIDADES.README/assets/144744092/3b69c60e-05ef-4d79-a8f9-ec98ae3a9d75)

º Utilizando o comando INTER JOIN, para realizar o ligamento das duas tabelas que foram criadas do mesmo bancos de dados, porém com informações difeferentes. Código utilizado para atividade. 

    CREATE TABLE Cidades (
        id INT PRIMARY KEY,
        nome VARCHAR(60) NOT NULL,
        populacao INT
    );
    
    
    INSERT INTO Cidades (id, nome, populacao) VALUES
    (1, 'Arraial dos Tucanos', 42632),
    (2, 'Springfield', 13820),
    (3, 'Hill Valley', 27383),
    (4, 'Coruscant', 19138),
    (5, 'Minas Tirith', 31394);
    
    
    CREATE TABLE Alunos (
        id INT PRIMARY KEY,
        nome VARCHAR(60) NOT NULL,
        data_nasc DATE,
        cidade_id INT,
        FOREIGN KEY (cidade_id) REFERENCES Cidades(id)
    );
    
    
    INSERT INTO Alunos (id, nome, data_nasc, cidade_id) VALUES
    (1, 'Immanuel Kant', '1724-04-22', 4),
    (2, 'Alan Turing', '1912-06-23', 3),
    (3, 'George Boole', '2002-01-01', 1),
    (4, 'Lynn Margulis', '1991-08-12', 3),
    (5, 'Nicola Tesla', '2090-01-08', NULL),
    (6, 'Ada Lovelace', '1978-05-28', 4),
    (7, 'Claude Shannon', '1982-10-15', 3),
    (8, 'Charles Darwin', '2010-02-06', NULL),
    (9, 'Marie Curie', '2007-07-12', 3),
    (10, 'Carl Sagan', '2000-11-20', 1),
    (11, 'Tim Berners-Lee', '1973-12-05', 4),
    (12, 'Richard Feynman', '1982-09-12', 1);
    
    
    SELECT * FROM Alunos JOIN Cidades ON Cidades.id = Alunos.cidade_id;
