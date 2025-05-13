É uma algoritmo que fará uma busca por cada nível na árvore binária da esquerda para a direita por meio de [[Queue (Fila)]]. A complexidade do código é [O(N)](O(N)), pois passará em cada um dos elementos da árvore. Em linguagens que o método de remover o primeiro elemento da fila for de complexidade [[O(n)]], isso fará com que a complexidade do BFS seja de [[O(n²)]], pois a cada iteração ocorrerá um shift(no caso do JavaScript).

Exemplo de código com implementação de BFS:
``` 
export default function bfs(head: BinaryNode<number>, needle: number): boolean {

	const queue = [head]  

	while (queue.length) {
		const curr = queue.shift() as BinaryNode<number>;
		
		if (!curr) continue;
		
		if (curr.value === needle) {
			return true;
		}
		
		if (curr.left) {
			queue.push(curr.left)
		}
			
		if (curr.right) {
			queue.push(curr.right)
		}
	}
	return false;
}
```
