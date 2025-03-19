Fila é uma estrutura de dados que aplica a lógica FIFO (First In First Out) o primeiro a entrar será o primeiro a sair. 
Essa estrutura é feita com uma [LinkedList](LinkedList) que ao invés de ter o método pop() (operação de [[O(1)]]) no último elemento terá no primeiro.

```
type Node<T> = {
value: T;
next?: Node<T>;
}
Class Queue<T>:
	private head: Node<T>
	private last: Node<T>;
	enqueue(item: T): void: 
	dequeue(): T | undefined;
	peek(): T | undefinedd;
	 
```
O método Peek mostra o valor de head. O método **enqueue** define o ultimo elemento na fila: 

```
const enqueue = (item: T) =>  {
const newEl =  {value: item};
this.length++;
if (!this.last) {
	this.last = this.head = newEl;
}
this.last.next = newEl;
last = newEl
}
```

**dequeue**:
```
const firstEl =  first.item;
this.first = first.next();
this.lenght--;
if(!this.head) {
	this.tail = undefined
}
return firstEl;
```