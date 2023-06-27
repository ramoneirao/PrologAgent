# Atividade Prática

Esse desenvolvimento é referido à atividade prática da disciplina Programação em Lógica da Universidade Federal do Pará (UFPa). O objetivo da atividade implica na construção de um agente explorador em PROLOG.

## Descrição

Este código implementa um algoritmo que encontra o caminho mais curto em um grafo ponderado, utilizando o problema do caixeiro viajante modificado. O objetivo é percorrer todos os vértices do grafo para coletar sacos de lixo, considerando a capacidade de coleta do robô.

## Definição do Ambiente:

O ambiente de atuação do agente explorador são os bairros de uma cidade, definidos por uma grafo ponderado, sendo o peso a distância dos bairros. 

### Dados do Grafo

O grafo é definido através de cláusulas `arestas/3`, onde cada cláusula representa uma aresta no grafo. Cada cláusula tem a forma `arestas(Origem, Destino, Peso)`, indicando que há uma aresta direcionada do `Origem` para o `Destino` com um peso associado.

Exemplo:

```prolog
arestas(1, 2, 3).
arestas(1, 3, 4).
arestas(2, 1, 3).
...
```

## Definição da Tarefa:

O agente explorador criado coleta os sacos de lixo por cada bairro onde passa.   

### Capacidade do Robô

O robô possui uma capacidade de coleta de lixo definida como 20 sacos. Ele só pode coletar os sacos de lixo presentes na posição atual e precisa retornar a um dos pontos centrais do grafo quando sua capacidade estiver cheia.

### Escolha dos Vértices Centrais

*Ver qual o algoritmo usado*

### Algoritmo do Caixeiro Viajante

Utiliza-se o algoritmo do caixeiro viajante modificado para encontrar uma rota que percorra todos os vértices do grafo, levando em consideração a coleta dos sacos de lixo. O objetivo é encontrar o caminho mais curto que permita coletar todos os sacos de lixo presentes em cada vértice.

## Atuação Sobre o Ambiente:

### Coleta dos Sacos de Lixo

Ao chegar a um vértice, o robô coleta os sacos de lixo presentes no local. A quantidade de sacos de lixo no vértice é reduzida para zero após a coleta.

### Esvaziamento dos Sacos de Lixo e Retorno ao Vértice

Quando a capacidade do robô atinge o limite de 20 sacos em um vértice X, ele deve retornar a um dos dois pontos centrais (em um grafo com |V| % 2 = 0) ou ao centro (em um grafo com |V| % 2 = 1) para esvaziar os sacos de lixo e voltar ao vértice X. Isso é feito para liberar espaço na capacidade do robô e continuar a coleta dos sacos de lixo em outros vértices.

### Caminho Mínimo para Eficiência

Para retornar ao centro rapidamente, é utilizado o algoritmo de caminho mínimo, que encontra o caminho mais curto entre dois vértices. Isso permite que o robô retorne ao centro de forma eficiente após esvaziar os sacos de lixo.

## Considerações Finais

Este código implementa um algoritmo que combina o problema do caixeiro viajante modificado com a coleta de sacos de lixo em um grafo. Ele permite percorrer todos os vértices do grafo, coletar sacos de lixo, esvaziá-los quando a capacidade estiver cheia e retornar ao centro de forma eficiente. No entanto, é importante notar que a eficiência do algoritmo pode ser limitada para grafos grandes ou com muitos caminhos possíveis. Outras abordagens mais avançadas, como algoritmos de otimização ou algoritmos genéticos, podem ser consideradas para obter soluções mais eficientes em problemas complexos.

## 👥Equipe

👤 Erick Fiel :-     202104940024

👤 Ramon Mendes :-   202104940013

👤 Ronald Andrade :- 202104940020

👤 Sainy Gabriel :-  202104940007
