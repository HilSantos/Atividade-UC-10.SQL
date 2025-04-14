# Atividade-UC-10 SQL
Exercicio do dia 11/03/25

1. Selecione todos os alunos e seus respectivos cursos.
SELECT nome_aluno, nome_curso
FROM tb_alunos
JOIN tb_cursos
ON tb_alunos.id_aluno = tb_cursos.id_aluno_curso;

2. Selecione o nome dos alunos que estão matriculados no curso de 'Matemática'.
SELECT nome_aluno
FROM tb_alunos
JOIN tb_cursos
ON tb_alunos.id_aluno = tb_cursos.id_aluno_curso
WHERE nome_curso = 'Matemática';

3. Selecione todos os cursos e os nomes dos alunos que estão matriculados neles.
SELECT nome_curso, nome_aluno
FROM tb_cursos
JOIN tb_alunos
ON tb_cursos.id_aluno_curso = tb_alunos.id_aluno;

4. Selecione os alunos que têm mais de 21 anos e os cursos que estão fazendo.
SELECT nome_aluno, nome_curso
FROM tb_alunos
JOIN tb_cursos
ON tb_alunos.id_aluno = tb_cursos.id_aluno_curso
WHERE idade_aluno > 21;

5. Selecione os cursos que têm alunos com idade inferior a 22 anos.
SELECT nome_curso
FROM tb_cursos
JOIN tb_alunos
ON tb_cursos.id_aluno_curso = tb_alunos.id_aluno
WHERE idade_aluno < 22;

6. Selecione os alunos e a quantidade de cursos que cada um está matriculado.
SELECT nome_aluno, COUNT(nome_curso) AS quantidade_cursos
FROM tb_alunos
JOIN tb_cursos
ON tb_alunos.id_aluno = tb_cursos.id_aluno_curso
GROUP BY nome_aluno;

7. Selecione os cursos que começam com a letra 'B' e os alunos que estão matriculados neles.
SELECT nome_curso, nome_aluno
FROM tb_cursos
JOIN tb_alunos
ON tb_cursos.id_aluno_curso = tb_alunos.id_aluno
WHERE nome_curso LIKE 'B%';

8. Selecione os alunos que estão matriculados em mais de um curso.
SELECT nome_aluno
FROM tb_alunos
JOIN tb_cursos
ON tb_alunos.id_aluno = tb_cursos.id_aluno_curso
GROUP BY nome_aluno
HAVING COUNT(nome_curso) > 1;

9. Selecione os alunos que não estão matriculados em nenhum curso.
SELECT nome_aluno
FROM tb_alunos
JOIN tb_cursos
ON tb_alunos.id_aluno = tb_cursos.id_aluno_curso
WHERE id_curso IS NULL;

10. Selecione os cursos e a idade dos alunos que estão matriculados neles.
SELECT nome_curso, idade_aluno
FROM tb_cursos
JOIN tb_alunos
ON tb_cursos.id_aluno_curso = tb_alunos.id_aluno;

11. Selecione os alunos e os cursos ordenados pelo nome do curso.
SELECT nome_aluno, nome_curso
FROM tb_alunos
JOIN tb_cursos
ON tb_alunos.id_aluno = tb_cursos.id_aluno_curso
ORDER BY nome_curso;

12. Selecione os alunos e os cursos ordenados pela idade do aluno.
SELECT nome_aluno, nome_curso
FROM tb_alunos
JOIN tb_cursos
ON tb_alunos.id_aluno = tb_cursos.id_aluno_curso
ORDER BY idade_aluno;

13. Selecione os alunos que estão matriculados em cursos cujo nome tem mais de 7 caracteres.
SELECT nome_aluno
FROM tb_alunos
JOIN tb_cursos
ON tb_alunos.id_aluno = tb_cursos.id_aluno_curso
WHERE CHAR_LENGTH(nome_curso) > 7;

14. Selecione os cursos e os alunos que têm o mesmo nome (ex: 'Ana' e 'Ana').
SELECT nome_curso, nome_aluno
FROM tb_cursos
JOIN tb_alunos
ON tb_cursos.id_aluno_curso = tb_alunos.id_aluno
WHERE nome_curso = nome_aluno;

15. Selecione os alunos e os cursos, mostrando apenas os alunos com idade entre 20 e 22 anos.
SELECT nome_aluno, nome_curso
FROM tb_alunos
JOIN tb_cursos
ON tb_alunos.id_aluno = tb_cursos.id_aluno_curso
WHERE idade_aluno BETWEEN 20 AND 22;

16. Selecione os cursos e os alunos, mostrando apenas os cursos com nome de até 8 caracteres.
SELECT nome_curso, nome_aluno
FROM tb_cursos
JOIN tb_alunos
ON tb_cursos.id_aluno_curso = tb_alunos.id_aluno
WHERE CHAR_LENGTH(nome_curso) <= 8;

17. Selecione os alunos e os cursos, agrupando os resultados pelo nome do curso.
SELECT nome_curso, GROUP_CONCAT(nome_aluno) AS alunos
FROM tb_cursos
JOIN tb_alunos
ON tb_cursos.id_aluno_curso = tb_alunos.id_aluno
GROUP BY nome_curso;

18. Selecione os alunos e os cursos, agrupando os resultados pela idade do aluno.
SELECT idade_aluno, GROUP_CONCAT(nome_curso) AS cursos
FROM tb_alunos
JOIN tb_cursos
ON tb_alunos.id_aluno = tb_cursos.id_aluno_curso
GROUP BY idade_aluno;

19. Selecione os alunos e os cursos, mostrando apenas os alunos cujo nome começa com 'C'.
SELECT nome_aluno, nome_curso
FROM tb_alunos
JOIN tb_cursos
ON tb_alunos.id_aluno = tb_cursos.id_aluno_curso
WHERE nome_aluno LIKE 'C%';

20. Selecione os cursos e os alunos, mostrando apenas os cursos cujo nome termina com 'a'.
SELECT nome_curso, nome_aluno
FROM tb_cursos
JOIN tb_alunos
ON tb_cursos.id_aluno_curso = tb_alunos.id_aluno
WHERE nome_curso LIKE '%a';

21. Selecione os alunos e os cursos, mostrando apenas os alunos com idade par.
SELECT nome_aluno, nome_curso
FROM tb_alunos
JOIN tb_cursos
ON tb_alunos.id_aluno = tb_cursos.id_aluno_curso
WHERE idade_aluno % 2 = 0;

22. Selecione os cursos e os alunos, mostrando apenas os cursos com nome ímpar.
SELECT nome_curso, nome_aluno
FROM tb_cursos
JOIN tb_alunos
ON tb_cursos.id_aluno_curso = tb_alunos.id_aluno
WHERE CHAR_LENGTH(nome_curso) % 2 <> 0;

23. Selecione os alunos e os cursos, mostrando apenas os alunos cujo nome tem 4 letras.
SELECT nome_aluno, nome_curso
FROM tb_alunos
JOIN tb_cursos
ON tb_alunos.id_aluno = tb_cursos.id_aluno_curso
WHERE CHAR_LENGTH(nome_aluno) = 4;

24. Selecione os cursos e os alunos, mostrando apenas os cursos cujo nome tem 6 letras.
SELECT nome_curso, nome_aluno
FROM tb_cursos
JOIN tb_alunos
ON tb_cursos.id_aluno_curso = tb_alunos.id_aluno
WHERE CHAR_LENGTH(nome_curso) = 6;

25. Selecione os alunos e os cursos, mostrando apenas os alunos cujo nome contém a letra 'r'.
SELECT nome_aluno, nome_curso
FROM tb_alunos
JOIN tb_cursos
ON tb_alunos.id_aluno = tb_cursos.id_aluno_curso
WHERE nome_aluno LIKE '%r%';
