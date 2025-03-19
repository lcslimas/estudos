Array é uma [[Estrutura de Dados e Algoritmos/Estrutura de Dados|estrutura de dados]] que armazena dados do mesmo tipo com tamanho fixo e de forma contígua na memória (É sequencial). Caso não possua valor o **Array de valores primitivos** se comporta dessa forma:
##### Linguagens como Java:

- Quando você cria um array de tipos primitivos (por exemplo, `int`, `float`, `boolean`) em linguagens como **Java**, mas não atribui valores, ele é inicializado automaticamente com um **valor padrão** para cada posição.
    
    - **Inteiros (`int`, `short`, `long`)**: São inicializados como `0`.
    - **Pontos flutuantes (`float`, `double`)**: São inicializados como `0.0`.
    - **Booleanos**: São inicializados como `false`.
    - **Caracteres (`char`)**: São inicializados como o caractere `\u0000` (null character, com valor numérico 0).
- Exemplo:
    
    java
    
    `int[] array = new int[5];  // Um array de inteiros com 5 posições // Cada elemento de 'array' é automaticamente inicializado com 0`

Ou seja, se o array armazena **valores primitivos** ele armazena o valor diretamente, caso seja objetos armazena o endereço de memória(referência).

______ - - - - - - - -- - - 
Criação em Java: 
```
int[] numeros = new int[5];
```

**Inserir** um elemento no Array, implica em criar um novo com o tamanho maior para posicionar o novo elemento. Ou seja, linear [O(n)](O(n)), diferente de linkedList que é constante [O(1)](O(1)). Outro problema que ao inserir, tem que alocar várias memórias sequenciais, enquanto que no linkedlist, é armazenado o local do próximo item.
**Remover** um elemento implica em passar por todos os elementos ligando-os novamente, tendo em vista que array é uma estrutura de dados contígua.
**Buscar** um elemento em um array não ordenado geralmente requer a verificação de todos os elementos (O(n)), mas em arrays ordenados, pesquisas mais rápidas, como busca binária (O(log n)), podem ser usadas.

para acessar um elemento é [[O(n)]]

**Multidimensional**:

- Arrays podem ser de várias dimensões. Por exemplo, um array bidimensional (`matriz`) é essencialmente um array de arrays, útil para representar tabelas ou matrizes matemáticas.
- Exemplo de um array 2D em Java:
    
    java
    
    `int[][] matriz = new int[3][3]; // Uma matriz 3x3 de inteiros matriz[0][0] = 1; // Atribuindo valores`

### Vantagens de um Array:

- **Acesso direto (O(1))**: Você pode acessar qualquer elemento diretamente, o que é muito rápido.
- **Uso simples**: Arrays são fáceis de entender e utilizar, especialmente para operações de iteração e armazenamento de dados simples.
- **Baixo overhead**: Em termos de memória, os arrays têm um overhead baixo, pois são armazenados de forma contígua.

### Desvantagens de um Array:

- **Tamanho fixo**: Uma vez que o tamanho é definido, ele não pode ser alterado. Isso significa que você pode acabar alocando mais espaço do que o necessário ou precisar de mais espaço do que foi alocado, o que exige a criação de um novo array.
- **Custo em inserções/remoções**: Inserir ou remover elementos em posições específicas pode ser caro, pois você precisa mover elementos para abrir ou preencher o espaço.
- **Uso ineficiente de memória**: Se você não souber o tamanho exato dos dados a serem armazenados, pode acabar reservando espaço desnecessário.
### Arrays Dinâmicos

Para superar algumas das limitações dos arrays tradicionais, existem estruturas de dados como **Arrays Dinâmicos** (ex.: `ArrayList` em Java ou `List` em Python). Eles oferecem:

- **Redimensionamento automático**: Eles aumentam ou diminuem de tamanho conforme necessário.
- **Inserções fáceis**: Inserir elementos ao final da lista é simples e eficiente.
- **Implementação interna**: Internamente, esses arrays dinâmicos ainda usam arrays, mas gerenciam automaticamente o redimensionamento conforme necessário.