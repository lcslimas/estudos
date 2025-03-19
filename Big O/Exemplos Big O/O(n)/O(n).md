---
tags:
  - BigO
---
Ligado a [[Big O]]]
`int sum = 0;
For(int i; i<=elements.size(); i++) {
	sum +=element[i];
}`

Exemplo de **O(n)**, pois o tempo de execução está atrelado a **N**, onde **N** é o tamanho da variável *elements*.
 - - - - - - - - - - 
`int sum = 0;
For(int i = 0; i<=elements.size(); i++) {
	sum +=element[i];
}

`For(int j = 0; j<=elements.size(); j++) {`
	`if(j%2==0) {`
		`sum -=element[j];`
	`}`
`}`

O exemplo acima, apesar de ser executado duas vezes e sendo O(2n), para a anotação Big-O, devemos ignorar as constantes, portanto o código acima tbm é O(n).