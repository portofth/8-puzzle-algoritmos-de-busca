# Solução do 8-Puzzle com Algoritmos de Busca

Este projeto foi desenvolvido em 2025/02 para a disciplina de Inteligência Artificial.

## Integrantes

- Davi Wenzel Cury
- Diogo Patrick Cesário de Oliveira
- Fabiano Queiroz Guimarães Almeida
- Fernando Theodoro Porto de Paula Dias
- Mateus Evangelista do Nascimento

## Descrição do Projeto

Este repositório apresenta uma solução para o problema do jogo 8-Puzzle, utilizando algoritmos de busca clássicos da Inteligência Artificial. O objetivo é transformar um estado inicial desordenado em um estado objetivo, movendo o espaço vazio (0) para cima, baixo, esquerda ou direita, sem sair do tabuleiro 3x3.

# Solução para o problema: Algoritmos de Busca no Jogo 8-Puzzle

O 8-Puzzle é um problema de busca em espaço de estados. Cada configuração do tabuleiro representa um estado, e cada movimento válido do espaço vazio gera um novo estado. O problema consiste em encontrar uma sequência de movimentos que leve o tabuleiro da configuração inicial para a configuração final:

[0, 1, 2, 3, 4, 5, 6, 7, 8]

## Representação do Estado

No projeto, o tabuleiro é representado como uma lista de 9 elementos, onde:

- 0 representa o espaço vazio;
- os demais números representam as peças do puzzle.

Exemplo de estado:

[1, 2, 3, 4, 0, 5, 7, 8, 6]

A função de geração de sucessores analisa a posição do zero e cria os estados possíveis a partir dos movimentos válidos.

## Regras do Problema

- O espaço vazio pode se mover para cima, baixo, esquerda ou direita;
- o movimento só é válido se a nova posição estiver dentro do tabuleiro 3x3;
- a solução deve chegar ao estado objetivo sem repetir ações inválidas.

## Verificação de Solubilidade

Nem todo estado do 8-Puzzle possui solução. O projeto verifica isso calculando o número de inversões das peças na sequência, e somente continua se o estado for solúvel.

## Algoritmos de Busca Implementados

### 1. Busca em Largura (BFS)

A busca em largura explora todos os estados de uma mesma profundidade antes de avançar para o próximo nível. Ela garante a menor quantidade de movimentos entre todos os caminhos possíveis, porém pode consumir mais memória.

### 2. Busca em Profundidade (DFS)

A busca em profundidade explora um ramo até o fundo antes de voltar atrás. Ela tende a ser mais econômica em memória, mas não garante a solução mais curta.

### 3. Busca A\*

A busca A\* é a abordagem mais eficiente para este tipo de problema. Ela combina:

- g(n): custo do caminho até o estado atual;
- h(n): estimativa de custo restante até o objetivo.

No projeto, a heurística utilizada é a Distância de Manhattan, que soma a distância entre cada peça e sua posição correta. Essa estratégia reduz significativamente o número de estados explorados.

## Objetivo da Solução

A solução implementada busca encontrar o caminho mínimo para chegar ao estado final, utilizando diferentes estratégias de busca e comparando a eficiência da resolução em termos de exploração de nós e profundidade da solução.

## Estrutura do Projeto

- `main.py` - ponto de entrada principal
- `interface.py` - lógica da interface
- `puzzle.py` - representação do problema e geração de sucessores
- `algoritmos/` - implementação dos algoritmos de busca
  - `a_estrela.py`
  - `BFS.py`
  - `DFS.py`

## Observação

Este projeto foi desenvolvido para registrar e aplicar os conceitos de Inteligência Artificial em buscas em espaço de estados, com foco no clássico problema do 8-Puzzle.
