No MySQL temos os seguintes comandos:

SELECT = Serve para selecionar algo do banco de dados;
FROM = Serve para especificar de onde será extraído o SELECT;

WHERE é um comando complexo, tendo algumas variáveis para ele, neste comando colocamos o que queremos que seja extraído da busca dos dados. Por Exemplo:

SELECT primeiro_nome
FROM empresax.clientes2025
WHERE genero != 'Feminino'

No WHERE colocamos a coluna que queremos e a condição, neste exemplo estou dizendo pro software: "Selecione o primeiro nome de empresax.clientes2025 onde o gênero não seja Feminino"

Também temos os operadores lógicos, sendo eles o AND, OR e NOT.

AND é pra se duas opções for verdadeira, retorna o valor, caso contrário, não retorna nada.

OR é pra se caso 2 opções forem verdadeiras ou uma ou outra condição for verdadeira, caso contrario, não retorna nada.

NOT funciona de maneira simples, se você não quer Masculino, coloque NOT gênero = 'Masculino'.

Temos o comando LIKE também:
O comando LIKE serve pra dar mais flexibilidade ou especificar mais uma condição:
Para esse comando utilizamos o "%" ou o " _ "

Temos por exemplo:
WHERE primeiro_nome LIKE 'A%'
Neste caso retornará todo nome que começa com a letra A;

WHERE primeiro_nome LIKE 'A___' 
Neste caso, retornará todo nome que começar com A e tiver 4 letras após, exemplo: "André"

Existe um comando chamado de GROUP BY:
O GROUP BY ele agrupa todos os dados por uma condição escolhida pelo analista, exemplo:
GROUP BY genero;
agrupará todos os clientes por genero (Feminino ou Masculino)

Comandos como MIN(), MAX() e AVG() serve muito bem nesse contexto para saber a idade mínima, máxima e média dos clientes. Basta acrescentar idade (ou como estiver escrito no banco de dados da empresa) em meio às parênteses! MIN(idade), MAX(idade), AVG(idade).
O comando COUNT() serve pra contar a quantidade de clientes, podendo ser utilizado pra contar a quantidade de usuários em um site ou qualquer outra necessidade.

O comando ORDER BY serve para ordenar de maneira crescente ou decrescente uma lista de dados a partir de uma condição:
Por exemplo:
ORDER BY idade ou ORDER BY idade ASC
(começa do menor para o maior);
ORDER BY idade ""DESC""
(começa do maior para o menor);

O comando HAVING vem depois do GROUP BY, para filtrar dados após serem agrupados por uma condição, por exemplo:
SELECT salario
FROM funcionarios_salario
WHERE ocupacao LIKE '%gerente%'
GROUP BY ocupacao
HAVING AVG(salario) > 7000

Neste caso estou pedindo para o MySQL:
"Selecione na coluna salário de funcionarios_salario todas as ocupações relacionadas a gerente agrupando por ocupação tendo uma médial salarial maior que 7000"

O comando LIMIT serve para limitar a quantidade de linhas que seram mostradas no output (retorno).
Exemplo: LIMIT 3 (retorna apenas as primeiras 3 linhas)

neste comando podemos acrescentar uma outra condição, onde irá retornar apenas as linhas que vêm depois da condição, por exemplo:
LIMIT 3, 1 (irá retornar uma linha depois das 3 primeiras (ou seja a quarta linha)).

O comando ALIASING serve para dar um nome temporário a uma coluna já existente no banco de dados:
Exemplo:
SELECT genero, AVG(idade) AS idade_media
FROM dados_funcionarios
GROUP BY genero
HAVING idade_media > 40

O "AS" utilizado no software, serve para que o AVG(idade) possa ser utilizado como idade_media facilitando assim a leitura no resultado da pesquisa.

Existe o comando LENGTH que serve para especificar o tamanho de algo, como por exemplo:
SELECT cidade
FROM estado
WHERE LENGTH(cidade) = 5
;
O resultado trará todas as cidades com 5 letras.

O comando DISTINCT serve para não ter condições duplicadas, por exemplo:
SELECT DISTINCT cidade (serve para, se caso tiver 2 cidades de mesmo nome, ele irá trazer apenas um).
