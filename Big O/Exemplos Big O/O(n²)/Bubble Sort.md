Ordenação que passa por todos os elementos duas vezes verificando-os e os ordenando. Portanto, é um algoritmo de complexidade [[O(n²)]] . Exemplo de implementação: 
`for (let i = 0; i <= arr.length; i++) {`
        `for (let j = 0; j < arr.length - 1 - i; j++) {`
            `if (arr[j] > arr[j + 1]) {`
                `const actualIndexValue = arr[j];`
                `arr[j] = arr[j + 1];`
                `arr[j + 1] = actualIndexValue;`
            `}`
        `}`
    `}`
 Nessa implementação, a cada interação do for da variavel J, o último valor vai ser sempre o maior, por isso ignoramos ele diminuindo - 1 e menos o índice de i, pq se está na primeira iteração o .