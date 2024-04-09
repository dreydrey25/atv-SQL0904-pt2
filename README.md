# atv-SQL0904-pt2

-- --ATIVIDADE_1 (FILMES)
-- menor tempo de duração
SELECT MIN(DURACAO_MINUTOS) AS menor_duracao
FROM ENTRETERIMENTO;

-- maior tempo de duração
SELECT MAX(DURACAO_MINUTOS) AS maior_duracao
FROM ENTRETERIMENTO;

-- filme/série, tipo e tempo com maior tempo de duração
SELECT NOME, TIPO, DURACAO_MINUTOS AS maior_duracao
FROM ENTRETERIMENTO
WHERE DURACAO_MINUTOS = (SELECT MAX(DURACAO_MINUTOS) FROM ENTRETERIMENTO);

-- filme/série, tipo e tempo com menor tempo de duração
SELECT NOME, TIPO, DURACAO_MINUTOS AS menor_duracao
FROM ENTRETERIMENTO
WHERE DURACAO_MINUTOS = (SELECT MIN(DURACAO_MINUTOS) FROM ENTRETERIMENTO);

-- quantidade de séries
SELECT COUNT(*) AS quantidade_series
FROM ENTRETERIMENTO
WHERE TIPO = 'SÉRIE';

-- quantidade de filmes
SELECT COUNT(*) AS quantidade_filmes
FROM ENTRETERIMENTO
WHERE TIPO = 'FILME';

-- duração média das séries
SELECT AVG(DURACAO_MINUTOS) AS duracao_media_series
FROM ENTRETERIMENTO
WHERE TIPO = 'SÉRIE';

-- soma da duração dos filmes do Brad Pitt
SELECT SUM(DURACAO_MINUTOS) AS soma_duracao_bradpitt
FROM ENTRETERIMENTO
WHERE TIPO = 'FILME' AND ATOR_PRINCIPAL = 'Brad Pitt';


-- --ATIVIDADE_2 (FILMES)
-- quantidade de séries que tem a letra 'n'
SELECT COUNT(*) AS quantidade_series_n
FROM ENTRETERIMENTO
WHERE TIPO = 'SÉRIE' AND NOME LIKE '%n%';

-- quantidade de séries que tem a letra 'o'
SELECT COUNT(*) AS quantidade_series_o
FROM ENTRETERIMENTO
WHERE TIPO = 'FILME' AND NOME LIKE '%o%';

-- média de duração das séries que começam com 'w'
SELECT AVG(DURACAO_MINUTOS) AS duracao_media_series_w
FROM ENTRETERIMENTO
WHERE TIPO = 'SÉRIE' AND NOME LIKE 'w%';

-- somar a duração dos filmes do Brad Pitt com a letra 'e'
SELECT SUM(DURACAO_MINUTOS) AS soma_duracao_bradpitt_e
FROM ENTRETERIMENTO
WHERE TIPO = 'FILME' AND ATOR_PRINCIPAL = 'Brad Pitt' AND NOME LIKE '%e%';

-- classificar duração dos filmes com a letra 's' do maior para menor
SELECT *
FROM ENTRETERIMENTO
WHERE TIPO = 'FILME' AND NOME LIKE '%s%'
ORDER BY DURACAO_MINUTOS;

-- classificar duração dos filmes com a letra 's' do menor para maior
SELECT *
FROM ENTRETERIMENTO
WHERE TIPO = 'FILME' AND NOME LIKE '%s%'
ORDER BY DURACAO_MINUTOS DESC;
