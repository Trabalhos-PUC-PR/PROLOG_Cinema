## Enunciado:

No [link](https://swish.swi-prolog.org/p/Cinema_PUC_2022-1.pl):  
Existe um banco de dados com informações sobre os filmes de Hollywood. Neste link também estão as considerações referentes a criação deste banco de dados, inclusive explicando como foram criados os fatos que relacionam os átomos envolvidos.  
Sua tarefa será criar regras para atender as questões apresentadas no link acima e publicar, como resposta, o link do seu arquivo, contendo o banco, e as regras que você criou.
******
Escreva regras para responder as seguintes perguntas:  

    a. Em que ano estreiou o filme American Beauty?
    b. Liste todos os filmes que estreiaram em 2000.
    c. Liste os filmes que estreiaram antes de 2000.
    d. Liste os filmes que estreiaram depois de 1990.
    f. Encontre o diretor dos filmes com Scarlett Johansson.
    g. Encontre os atores que também dirigiram filmes.
    h. Encontre os atores, ou atrizes, que dirigiram filmes.
    i. Encontre o filme no qual John Goodman e Jeff Bridges atuaram.
    
<details><summary><h2>Mais Detalhes:</h2></summary>
  
Como este banco de dados foi montado:  
```PROLOG
    filme(M, Y) -> filme M estreiou no ano Y 
    diretor(M, D) -> filme M dirigido pelo diretor D 
    ator(M, A, R) -> ator A interpretou o papel de R no filme M 
    atriz(M, A, R) -> atriz A interpretou o papel de R no filme M 
```

 Usando discontiguos, podemos determinar a ordem em que os predicados irão aparecer no banco de dados.  
 Neste caso, a ordem foi escolhida para ser adequada ao arquivo txt que continha estas informações.  
```PROLOG
:- discontiguous
        filme/2,
        diretor/2,
        ator/3,
        atriz/3.
```
 Você vai precisar usar a variável anônima _ veja o exemplo a seguir:  
 ```PROLOG
 atriz(M, scarlett_johansson, _), diretor(M, D).
 ```
 Rode este querie e veja se funciona.   
 Todas as variáveis anônimas, são diferentes entre si e como tal são tratadas de forma diferente.  
 Maria ama joao, joao ama paula, se queremos saber se paulo quer saber quem o ama podemos  
 usar uma variável comum, mas para saber se alguém o ama podemos usar uma variável anônima  
 ```PROLOG
 ama(maria,joao).
 ama(joao,paula).
 ama(cachorro,bife).
 ama(jose,maria).
 ```
 tente: 
 ```PROLOG 
 ama(X,joao).
 ```
