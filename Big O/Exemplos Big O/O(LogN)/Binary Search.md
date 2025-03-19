 Algoritmo de [O(LogN)](O(LogN)) **esse tipo de busca ocorre em dados ordenados**.
 Exemplo de implementação:
`const bsl = (arr: number[], needle: number) {`
	`let lowIndex = 0;`
	`let highIndex = arr.length`
	`do {`
		`const quantityOfIndexInTheMiddle = (highIndex - lowIndex);`
		`const mediumIndex = Math.floor(lowIndex + quantityOfIndexInTheMiddle / 2)`
		`const valueOfMedium = arr[mediumIndex]`
		`if(needdle === valueOfMedium) return true;`
		`if(valueOfMedium > needle) highIndex = medium;`
		`else lowIndex = mediumIndex + 1`
	`} while (lowIndex < highIndex)`
	`return false;`
`}`