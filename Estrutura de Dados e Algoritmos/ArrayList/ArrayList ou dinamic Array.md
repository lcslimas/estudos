Tenta juntar o melhor dos mundos entre Array e List.
Ele armazena os itens de forma contígua assim como o [Array](Array), mas ele se adequa a quantidade de itens necessários, então em um ArrayList de 20 itens a sua capacidade tem que ser maior, então, para isso, caso o ArrayList chegue na capacidade máxima alocada na memória, as memórias contíguas serão alocadas para uma parte que consiga lidar com a nova capacidade máxima que permita Push no ArrayList.

```
export default class ArrayList<T> {

    public length: number;

    private items: (T | undefined)[] ;

    private capacity: number;


    constructor(capacity: number) {

        this.capacity = capacity;

        this.items = [];

        this.length = 0;

    }

  

    prepend(item: T): void {

        let idx = this.length;

        while(idx >= 0) {

            this.items[idx] = this.items[idx-1]

            idx--

        }

        this.length++;

        this.items[0] = item;

    }

    insertAt(item: T, idx: number): void {

        this.items[idx] = item;

    }

    append(item: T): void {

        this.items[this.length] = item;

        this.length++;

    }

    remove(item: T): T | undefined {

        let foundElement = undefined;

        for(let i = 0; i<this.length; i++) {

            const actualItem = this.items[i];

            if(actualItem === item) {

                foundElement = actualItem;

                this.items[i] = item;

                this.length--;

            }

  

            if(foundElement) {

                this.items[i] = this.items[i+1]

            }

        }

        return foundElement;

    }

    get(idx: number): T | undefined {

        if(idx >= this.length) throw new Error("Out Of Bounds")

        return this.items[idx]

    }

    removeAt(idx: number): T | undefined {

        if(idx >= this.length) throw new Error("Out Of Bounds")

        const foundElement = this.items[idx];

        if(foundElement) {

            do {

                this.items[idx] = this.items[idx+1]

            } while(this.items[idx++])

            this.items.pop()

            this.length--;

        };

        return foundElement;

    }

}
```

Obs: inserir um elemento no começo de um ArrayList tem a complexidade de [O(n)](O(n)) porque tem que alocar todos os elementos deixando um local no começo livre.

Obs2: Ao remover um elemento devemos lembrar de subtrair o length se o elemento existir e realocar os elementos posteriores.