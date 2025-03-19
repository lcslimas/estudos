É uma estrutura de dados parecida com [[Queue (Fila)]] , porém é estruturada de forma contrária. A ordem é da última para o primeiro elemento adicionado(Head estará no final), ou seja First In Last Out (primeiro a entrar será o último a sair).

Exemplo de classe:
```
type Node<T> = {

    value: T;

    prev?: Node<T>;

};

export default class Stack<T> {

    public length: number;

    private head?: Node<T>;

  

    constructor() {

        this.head = undefined;

        this.length = 0;

    }

  

    push(item: T): void {

        const node: Node<T> = {value: item};

        this.length++;

  

        if(!this.head) {

            this.head = {...node, prev: undefined};

            return;

        }

        node.prev = this.head

        this.head = node;

    }

    pop(): T | undefined {

        this.length = Math.max(0, this.length-1);

  

        if(this.length === 0) {

            const head = this.head;

            this.head = undefined;

            return head?.value;

        }

        const head = this.head as Node<T>;

        this.head = head.prev;

        return head.value;

    }

    peek(): T | undefined {

        return this.head?.value;

    }

}
```

O head sempre será o último valor adicionado e sempre será o valor demonstrado no peek por exemplo.
ao dar um Push, o novo item será a Head e o valor anterior do Head será o prev do novo head.