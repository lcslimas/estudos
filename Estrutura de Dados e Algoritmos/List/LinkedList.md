Lista de elementos (nodes) que são ligados entre eles por uma variável que indica o próximo (next) elemento.
Exemplo de class LinkedList
`class Node<T>:`
 `val: T`
 `next?: Node<T>`

Next pode ser nulo, oq indica que chegamos a cauda da LinkedList, vulgo o último elemento.
Para adicionar ou remover elementos logo após o primeiro(head) ou último (tail) é usado complexidade de [[O(1)]], pois basta definir qual será o próximo elemento e definir o elemento atual como o próximo do anterior(se for adição) ou conectar o próximo valor ao anterior a ser adicionado, caso o valor removido seja o último, basta definir o next valor do elemento anterior como nulo. 
