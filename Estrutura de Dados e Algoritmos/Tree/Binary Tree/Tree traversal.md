Tree Traversal ou travessia de árvore é o processo para passar em todos os nós da Árvore.

Existe três formas, que utiliza recursão:
1. **In-Order**
   Serão processados todos os nós a **esquerda**, depois a **raiz** e logo após os nós a **direita**.  ESQUERDA -> RAIZ -> DIREITA
   ex código:
   `function walkBy(curr: BinaryNode<number>, path: number[]): number[] {`
	    `if (!curr) {`
	        `return path;`
	    `}`
	    
	    `walkBy(curr.left as BinaryNode<number>, path);`
	    `path.push(curr.value)`
	    `walkBy(curr.right as BinaryNode<number>, path);`
	    `return path;`
	`}`
	`export default function in_order_search(head: BinaryNode<number>): number[] {`
	    `return walkBy(head, []);`
	`}`
1. **Pre-Order**
   Será processado o nó da raiz, depois todos os nós a esquerda e por fim os nós a direita. RAÍZ -> ESQUERDA -> DIREITA
   ex código:
   `function walkBy(curr: BinaryNode<number>, path: number[]): number[] {`
	    `if (!curr) {`
	        `return path;`
	    `}`
	    
	    `path.push(curr.value)`
	    `walkBy(curr.left as BinaryNode<number>, path);`
	    `walkBy(curr.right as BinaryNode<number>, path);`
	    `return path;`
	`}`
	`export default function pre_order_search(head: BinaryNode<number>): number[] {`
	    `return walkBy(head, []);`
	`}`
2. **Post-Order**
   Serão processados todos os nós a **esquerda**, depois todos os nós a **direita** e só então o nó **raiz**. ESQUERDA -> DIREITA -> RAÍZ
	`function walkBy(curr: BinaryNode<number>, path: number[]): number[] {`
		    `if (!curr) {`
		        `return path;`
		    `}`
		    
		    `walkBy(curr.left as BinaryNode<number>, path);`
		    `walkBy(curr.right as BinaryNode<number>, path);`
		    `path.push(curr.value)`
		    `return path;`
		`}`
		`export default function pre_order_search(head: BinaryNode<number>): number[] {`
		    `return walkBy(head, []);`
	`}`   