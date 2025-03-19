Lista de elementos (nodes) que são ligados entre eles por uma variável que indica o próximo (next) elemento e o anterior, muito parecido com [linkedList](LinkedList).
Exemplo de class Double LinkedList
`class Node<T>:`
 `val: T`
 `next?: Node<T>``
 `prev?: Node<T>

Next e Prev pode ser nulo, oq indica que chegamos a cauda da double LinkedList (quando next é nulo), e na cabeça da double linkedList (quando o previous é nulo) vulgo o primeiro elemento. Para manipulação do primeiro e último arquivo, a complexidade é de [O(1)](O(1)), assim como dar um append ou prepend. 

Para utilizar valores que estão mais centralizados na DoubleLinkedList (não é o primeiro nem o último elemento) temos uma complexidade de [O(n)](O(n)), tendo em vista que precisamos passar por n elementos para obter o valor como num **get** ou no **removedAt**

Exemplo classe DoubleLinkedList:
`type Node<T> = {`
    `value?: T;`
    `next?: Node<T>;`
    `prev?: Node<T>;`
`};`

`export default class DoublyLinkedList<T> {`
    `public length: number;`
    `private head?: Node<T>;`
    `private tail?: Node<T>;`

    `constructor() {`
        `this.length = 0;`
        `this.head = this.tail = undefined;`
    `}`

    `prepend(item: T): void {`
        `const newNode = { value: item };`
        `const headNode = this.head;`
        `this.length++;`
        `if (!headNode) {`
            `this.head = this.tail = newNode;`
            `return;`
        `}`
        `this.head = { ...newNode, next: headNode };`
        `headNode.prev = this.head;`
    `}`
    `insertAt(item: T, idx: number): void {`
        `if (idx > this.length) {`
            `throw new Error();`
        `}`
        `this.length++;`
        `if (idx === this.length) {`
            `this.append(item);`
        `} else if (idx === 0) {`
            `this.prepend(item);`
        `}`
        `const newNode = { value: item };`
        `let actualNode = this.head;`
        `let count = 0;`
        `while (actualNode && count < idx) {`
            `actualNode = actualNode.next;`
            `count++;`
        `}`
        `const previousNext = actualNode?.next;`
        `if (previousNext) {`
            `previousNext.next = actualNode;`
        `}`
        `if (actualNode)`
            `actualNode.next = {`
                `...newNode,`
                `next: previousNext,`
                `prev: actualNode,`
            `};`
    `}`
    `append(item: T): void {`
        `const newNode = { value: item };`
        `if (!this.length) {`
            `this.head = this.tail = newNode;`
            `this.length++;`
            `return;`
        `}`
        `this.length++;`
        `const previousTail = this.tail;`
        `this.tail = { ...newNode, prev: previousTail };`
        `if (previousTail) {`
            `previousTail.next = this.tail;`
        `}`
    `}`
    `remove(item: T): T | undefined {`
        `let actualItem = this.head;`
        `while (actualItem) {`
            `if (actualItem.value === item) {`
                `const prevNode = actualItem.prev;`
                `const next = actualItem.next;`
                `if (prevNode) {`
                    `prevNode.next = next;`
                    `if (next) next.prev = prevNode;`
                `} else {`
                    `this.head = next;`
                `}`

                `this.length = this.length - 1 > 0 ? this.length - 1 : 0;`
                `return actualItem.value;`
            `}`
            `actualItem = actualItem.next;`
        `}`
        `return undefined;`
    `}`
    `get(idx: number): T | undefined {`
        `let actualNode = this.head;`
        `for (let i = 0; actualNode && i < idx; i++) {`
            `actualNode = actualNode.next;`
        `}`
        `return actualNode?.value;`
    `}`
    `removeAt(idx: number): T | undefined {`
        `let curr = this.head;`
        `let iterator = 0;`
        `if (idx === 0) {`
            `const headNode = this.head;`
            `const nextNode = headNode?.next;`
            `this.head = headNode?.next;`
            `if (nextNode) nextNode.prev = undefined;`
            `this.length = this.length - 1 > 0 ? this.length - 1 : 0;`
            `return headNode?.value;`
        `}`
        `do {`
            `curr = curr?.next;`
            `iterator++;`
        `} while (curr && iterator < idx);`

        `if (curr) {`
            `this.length--;`
        `}`

        `const previousCurr = curr?.prev;`
        `const nextCur = curr?.next;`

        `if (previousCurr) {`
            `previousCurr.next = nextCur;`
        `} else {`
            `this.head = nextCur;`
        `}`

        `if (nextCur) {`
            `nextCur.prev = previousCurr;`
        `}`

        `return curr?.value;`
    `}`
`}`

