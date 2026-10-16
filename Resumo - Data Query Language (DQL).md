SELECT: ferramenta para criar query (consulta). Apenas o que é "apresentado na tela" é modificado, sem modificar as tabelas em si.





SELECT tabela.coluna AS nome\_modificado\_para\_consulta\_apenas

  ^                  ^

  '                  '

SELECIONE   coluna  COMO Valdemar



\---



Strings (char, varchar, text, etc.): sequência de caracteres usados p/ representar texto. Ex.: "carro", "123".



Números (integers, floats, etc.): usados para operações matemáticas. São armazenados

no computador em uma forma binária otimizada para a aritmética.





Funções e operadores com SELECT - lembrando, apenas modificam a consulta das tabelas:





 	**SELECT \* FROM tabela**    seleciona **colunas** de uma tabela. Se deixado sem filtro, seleciona todas



 	**FROM** especificar tabela/coluna/tempo



 	**WHERE** (onde) filtro para especificar **dados**. Mt usado com UPPER, LOWER e INITCAP. Ex.: WHERE sexo\_pessoa = 'F' OR sexo\_pessoa = 'M'

                                                                    	 ^

 	**WHERE** \_ **LIKE** (onde \_ parece) especificar **dados** parecidos.       -'  Ex.: WHERE LOWER(tabela) LIKE '%azul%'    % caractere informando "não importa este caractere"



 	**WHERE** \_ **ILIKE** funciona igual o LIKE, mas é case insensitive - não diferencia caracteres maiúsculos de minúsculos



 	**UPPER**, **LOWER** e **INITCAP** mostram os dados da coluna como MAIÚSCULOS, minúsculos e Inicial\_capitalizada



 	**OR** sintaxe "OU" usada para especificar mais de um **dado**. Lembre-se da união de conjuntos - qqr uma opção das 2 entra no parâmetro



 	**ORDER BY** (ordenar por) ordenar **dados** selecionados com base na ordenação da coluna ou valor especificado

 

 	**ORDER BY DESC**/**ASC** ordenar de forma descendente/ascendente



 	**|| CONCAT()** concatenar/"juntar" 2 ou mais **dados**. Deve ter pelo menos 1 string. Todos os dados são convertidos para strings na concatenação.



 	**:: CAST()** ("Moldar" **dados**/mudar o tipo de dado)



 	**TRUNC()** omitir casas decimais de **números**



 	**ROUND()** omitir casas decimais de **números**, arrendondando



 	**EXTRACT()** extrair pedaços de **data** e **hora**



 	**INTERVAL** '00' MINUTE/HOUR/MONTH/YEAR      seleciona um intervalo de **tempo**, mt usado para somar/subtrair tempo



 	**current\_timestamp** / **now()**     "Wed 05 Nov 14:25:04.**663714** 2025 **-03**" timestamp acurado com fuso horário



 	**current\_date**                  "Tue 05 Aug 00:00:**00** 2025" timestamp sem fuso horário



 	**INNER JOIN** (junção interna) combinar **linhas** de duas ou mais tabelas que têm uma coluna em comum.



 	-------------------------------------------------------------------

 	Ex.1:



 	SELECT

    		table1.column1,

    		table1.column2,

    		table2.column1,

    		-- ... other columns

 	FROM

   		 table1

 	INNER JOIN

    		table2 ON table1.matching\_column = table2.matching\_column;



 	-------------------------------------------------------------------

 	ex.2:



 	SELECT

   		c.customer\_id,

    		c.first\_name,

    		c.last\_name,

    		o.order\_id,

    		o.order\_date

 	FROM

    		customers AS c

 	INNER JOIN

    		orders AS o ON c.customer\_id = o.customer\_id;



 	-------------------------------------------------------------------





 	**USING** (usando) funciona da mesma maneira que o INNER JOIN, com a diferença de que funciona apenas quando uma coluna tem o mesmo nome exato nas tabelas relacionadas



 	-------------------------------------------------------------------

 	Ex.:



 	SELECT CustomerID, Name, OrderDate

 	FROM Customers

 	JOIN Orders

 	USING (CustomerID);

 

 	-------------------------------------------------------------------

 	Ex. sem **USING** (cláusula **JOIN**):



 	SELECT c.CustomerID, c.Name, o.OrderDate

 	FROM Customers AS c

 	JOIN Orders AS o

 	ON c.CustomerID = o.CustomerID;

