# Revisão – Complexidade de Algoritmos

**Profa. Maria Camila Nardini Barioni**

📚 Baseado nos materiais de Nivio Ziviani e André Backes

---

# Sumario

- [Roteiro](#roteiro)
- [Algoritmos](#algoritmos)
- [Tipos de Análise](#tipos-de-analise)
- [Função de Complexidade](#funcao-de-complexidade)
- [Melhor, Pior e Caso Médio](#melhor-pior-e-caso-medio)
- [Notação O (Ordem de Complexidade)](#notacao-o-ordem-de-complexidade)
- [Comparação de Programas](#comparacao-de-programas)
- [Principais Classes de Complexidade](#principais-classes-de-complexidade)
- [Sugestões de Leitura](#sugestoes-de-leitura)

---


# Roteiro

[🔝](#sumario)

- Por que analisar a complexidade de algoritmos?
- Função de complexidade
- Melhor caso, pior caso e caso médio
- A notação O
- Comparação de programas
- Sugestões de leitura

---

# Algoritmos

[🔝](#sumario)

- Resolver um problema computacional exige uma descrição clara e precisa
- Um **algoritmo** é uma sequência objetiva de instruções, cada uma representando uma ação básica a ser executada

---

## Vários algoritmos para o mesmo problema

- Diferem na forma como utilizam os **recursos computacionais**:
  - Tempo de execução
  - Memória utilizada

---

## Por que analisar a complexidade?

- Avalia a **eficiência**, **desempenho** e **robustez** dos algoritmos
- Diferenças de desempenho podem ser insignificantes para entradas pequenas, mas críticas para entradas grandes

---

## Complexidade computacional

- **Custo = tempo + memória**
- O custo pode incluir outros recursos (como rede), mas geralmente foca no **tempo de execução em função do tamanho da entrada**

---

# Tipos de Analise

[🔝](#sumario)

## Análise empírica

- Executa o programa e mede desempenho
- Pode ser afetada por:
  - Compilador
  - Hardware
  - Alocação de memória

## Análise matemática (analítica)

- Usa um **modelo idealizado**
- Considera **operações dominantes** (ex.: número de comparações)
- Ignora operações irrelevantes para o crescimento da função de custo

---

# Funcao de Complexidade

[🔝](#sumario)

- Representa o custo de execução de um algoritmo:
  - Tempo: f(n) = número de passos relevantes
  - Espaço: f(n) = memória usada
- Medimos o custo em função do **tamanho da entrada n**

---

## Tamanho da entrada

- É o fator mais relevante para o custo de execução
- O custo pode variar conforme a **estrutura da entrada**, não apenas seu tamanho

---

# Melhor, Pior e Caso Medio

[🔝](#sumario)

Dado um algoritmo A e um conjunto de entradas possíveis E:

- Melhor caso: `min(tᵢ)` para Ei ∈ E
- Pior caso: `max(tᵢ)` para Ei ∈ E
- Caso médio:  
  `f(n) = Σ(pᵢ × tᵢ)` onde pᵢ é a probabilidade da entrada Ei

> Em geral, a análise do **pior caso** é mais comum, pois fornece garantias.

---

## Exemplo: Registros em Arquivo

| Nº | Produto   | Estoque | Preço   |
|----|-----------|---------|---------|
| 1  | Caneta    | 1000    | 6,70    |
| 2  | Borracha  | 750     | 4,50    |
| 3  | Lápis     | 2000    | 2,50    |
| 4  | Apontador | 500     | 5,30    |
| 5  | Cola      | 350     | 12,25   |
| 6  | Caderno   | 444     | 15,10   |
| …  | …         | …       | …       |
| n  | Fichário  | 200     | 85,00   |

**Pesquisa sequencial**:

- Melhor caso: f(n) = 1
- Pior caso: f(n) = n
- Caso médio: f(n) = (n + 1) / 2

---

## Comportamento Assintótico

- Para valores pequenos de n, qualquer algoritmo parece "rápido"
- A análise foca no comportamento de **f(n) quando n → ∞**

---

# Notacao O (Ordem de Complexidade)

[🔝](#sumario)

Usada para descrever o **limite superior assintótico**:

- f(n) = O(g(n)) significa que f(n) cresce no máximo como g(n)

## Exemplo:

```math
T(n) = 10n³ + 4n - 10 ⇒ O(n³)
````

## Regras:

* Desprezar constantes aditivas/multiplicativas
* Considerar apenas o termo dominante

---

## Exemplos de Notação O

```text
f(n) = n² - 1        ⇒ O(n²)
f(n) = 5 + 2 log n   ⇒ O(log n)
f(n) = 3n + 5 log n  ⇒ O(n)
f(n) = 5·2ⁿ + 5n¹⁰   ⇒ O(2ⁿ)
```

---

# Comparacao de Programas

[🔝](#sumario)

Dois algoritmos com funções de custo:

* Algoritmo A: T(n) = 100n
* Algoritmo B: T(n) = 2n²

| n   | T₁ (100n) | T₂ (2n²) |
| --- | --------- | -------- |
| 10  | 1000      | 200      |
| 50  | 5000      | 5000     |
| 100 | 10000     | 20000    |

* Para n pequeno: O(n²) pode ser melhor
* Para n grande: O(n) é preferível

---

# Principais Classes de Complexidade

[🔝](#sumario)

Ordem de crescimento (do menor para o maior):

```
O(1) < O(log n) < O(n) < O(n log n) < O(n²) < O(n³) < O(2ⁿ) < O(n!)
```

## O(1): constante

* Execução independe do tamanho da entrada

## O(log n): logarítmica

* Divide o problema em partes (ex.: busca binária)

## O(n): linear

* Executa uma operação por elemento

## O(n log n): quase-linear

* Ex.: Mergesort, Heapsort

## O(n²): quadrática

* Ex.: algoritmos com dois laços aninhados (insertion sort)

## O(n³): cúbica

* Usado em problemas matriciais (ex.: multiplicação de matrizes)

## O(2ⁿ) e O(n!)

* Exponenciais: impraticáveis para entradas médias/grandes

---

# Sugestoes de Leitura

[🔝](#sumario)

* ZIVIANI, Nivio. *Projeto de Algoritmos* – Capítulo 1
* CORMEN et al. *Algoritmos – Teoria e Prática* – Capítulos 2, 3 e 4
* Texto do Prof. Luis Gustavo Nonato (ICMC/USP) – disponível no MS Teams

---

# Material Complementar (Vídeo Aulas)

* Aula 99 – Introdução: [youtu.be/iZK5WwJFIPE](https://youtu.be/iZK5WwJFIPE)
* Aula 100 – Contando Instruções: [youtu.be/wflNJurvTTQ](https://youtu.be/wflNJurvTTQ)
* Aula 101 – Assintótico: [youtu.be/SClFMUpBiaw](https://youtu.be/SClFMUpBiaw)
* Aula 102 – Notação O: [youtu.be/Q7nwypDgTS8](https://youtu.be/Q7nwypDgTS8)
* Aula 103 – Tipos de Análise: [youtu.be/9RgC2dxi4W8](https://youtu.be/9RgC2dxi4W8)
* Aula 104 – Classes de Problemas: [youtu.be/8RYvWMOMnXw](https://youtu.be/8RYvWMOMnXw)

---
