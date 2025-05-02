# Análise de um Baralho de Cartas com PySpark

## Visão Geral

Este projeto utiliza o PySpark para criar um baralho de cartas padrão e realizar algumas análises básicas, incluindo amostragem e cálculos de probabilidade. Também são definidas funções para identificar mãos de poker.

## Metodologia

1.  **Configuração do Spark:**
    
    * Uma sessão Spark é inicializada com o nome "Baralho de Cartas".
    
2.  **Criação do Baralho:**
    
    * Listas são definidas para os naipes (`Copas`, `Espadas`, `Ouros`, `Paus`) e valores das cartas (`A`, `2`, `3`, `4`, `5`, `6`, `7`, `8`, `9`, `10`, `J`, `Q`, `K`).
    * Uma lista de tuplas (`dados_cartas`) é criada, onde cada tupla representa uma carta com suas informações (nome, naipe, valor, valor numérico, cor).
    * Um esquema é definido para o DataFrame do PySpark, especificando os nomes e tipos de dados das colunas.
    * O DataFrame `baralho_df` é criado a partir da lista de dados e do esquema.
    * O baralho completo é exibido.
    
3.  **Amostragem:**
    
    * Amostragem simples sem reposição é realizada usando `sample()` com `withReplacement=False`.
    * Amostragem simples com reposição também é demonstrada, embora comentada.
    * Amostragem estratificada é feita usando `sampleBy()` para selecionar frações diferentes de cartas de cores vermelhas e pretas.
    * O baralho é dividido em conjuntos de treino e teste usando `randomSplit()`.
    
4.  **Análise de Probabilidade:**
    
    * A probabilidade de sair o Ás de Copas é calculada.
    * A probabilidade de sair cada naipe é calculada.
    * A probabilidade de sair uma figura (Valete, Dama ou Rei) é calculada.
    * A probabilidade de sair cada valor numérico é calculada.
    
5.  **Análise de Mãos de Poker:**
    
    * Funções são definidas para identificar diferentes mãos de poker:
        * `is_par()`: Verifica se há um par.
        * `is_dois_pares()`: Verifica se há dois pares.
        * `is_trinca()`: Verifica se há uma trinca.
        * `is_straight()`: Verifica se há uma sequência.
        * `is_flush()`: Verifica se todas as cartas são do mesmo naipe.
        * `is_full_house()`: Verifica se há uma trinca e um par.
        * `is_quadra()`: Verifica se há uma quadra.
        * `is_royal_flush()`: Verifica se há um Royal Flush.
    * A função `avaliar_mao()` determina a melhor mão de poker em uma seleção de cartas.
    * Funções `simular_maos()` e `simular_maos_ultrarapida()` simulam a distribuição de mãos e calculam as probabilidades de cada tipo de mão. A versão "ultrarapida" utiliza otimizações do Spark para melhorar a performance.

## Resultados

* Um baralho de cartas completo foi gerado como um DataFrame do PySpark.
* Diferentes técnicas de amostragem foram demonstradas.
* Probabilidades de várias ocorrências de cartas foram calculadas.
* Funções para identificar mãos de poker foram implementadas, permitindo a análise de combinações de cartas.
* Simulações foram realizadas para estimar as probabilidades de diferentes mãos de poker.

## Conclusão

Este projeto demonstra como o PySpark pode ser usado para criar e manipular um baralho de cartas, além de realizar análises probabilísticas e identificar mãos de poker. As técnicas de amostragem e as funções de análise de mãos podem ser úteis em diversas aplicações de jogos e simulações.
