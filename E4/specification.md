# E4 - Como implementar o KWIC em C?

Trabalho de implementação de uma versão básica do KWIC, em C, a ser realizado em dupla (e apenas um trio, se sobrar alguém sem dupla). 

**Resposta.** A resposta para o exercício E4 é a URL de um repositório na organização MATA56-IC-UFBA, com licença de software definida, com um arquivo README.md e um arquivo "kwic.c" (programa em C). O arquivo README.md (markdown) deve  informar os nomes da dupla e conter um texto de até 800 palavras, alinhado com os objetivos desta disciplina, discorrendo brevemente sobre a implementação em linguagem C para o KWIC, e sobre uma eventual escolha de uma linguagem de programa alternativa.   

Considere a descrição funcional para KWIC - Keyword In Context dada a seguir, e disponibilize um programa em C (simples, modular e documentado) que implemente o KWIC.

**Exemplo.** Considere a entrada, sua saída correspondente e uma descrição funcional bem simples:

* Entrada:
```
The C Programming Language 
The Cat in the Hat 
```
* Saída: 
```
C Programming Language, The 
Cat in the Hat, The 
Hat, The Cat in the 
Language, The C Programming 
Programming Language, The C 
````

A entrada contém títulos de livros em inglês. Para cada linha da entrada,  todos os deslocamentos circulares (circular shift) são realizados, possivelmente resultando em novas linhas. O deslocamento circular em uma linha é gerado a partir da remoção da primeira palavra da linha e sua inclusão no final da mesma linha. Assim, uma linha com N palavras tem N deslocamentos circulares (incluindo a linha original). Entretanto, um conjunto de "palavras de ruído" (noise words) -- artigos (por exemplo, "the"), preposições (por exemplo, "in") ou outras categorias de palavras --  é usado para desconsiderar deslocamentos (linhas) iniciadas por tais palavras. No exemplo acima, o título original, "The Cat in the Hat" e os deslocamentos "in the Hat, The Cat" e "the Hat, The Cat in" foram desconsiderados. As linhas resultantes (originais e com deslocamento), ordenadas, são mostrada na saída. 
  
Esta descrição simples apresenta informalmente o KWIC (KeyWord In Context).  Há várias fontes na web com informações sobre o KWIC e seu uso na prática.
Neste exercício, assume-se que as palavras de ruído serão lidas a partir do arquivo [stopwords.txt](./stopwords.txt), disponibilizado pela professora, que contém uma palavra de ruído por linha.
Apenas um arquivo de entrada deve ser considerado, contendo um ou mais títulos de livros em inglês, um título por linha, com palavras delimitadas por ao menos um espaço em branco e sem distinção entre letras maiúsculas e minúsculas.

* **Comando:**  kwic linesFile
