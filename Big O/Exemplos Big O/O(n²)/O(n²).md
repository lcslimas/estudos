---
tags:
  - BigO
---
Ligado a [[Big O]]]
`int sum = 0;`

 `for (int i = 0; i<=elements.size(); i++) {`
	`sum += i;`
	`for(int j = 0; j<=elements.size(); j++) {`
		`sum -= j;`
	`}`
`}` 

Nesse caso temos *for* dentro de *for* então cada **n** será percorrido **n** vezes resultando em O(n²)