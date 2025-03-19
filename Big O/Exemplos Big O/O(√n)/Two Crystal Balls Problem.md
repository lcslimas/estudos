Digamos que tem você tem que descobrir a que altura a bola de cristal se quebrará se jogada de certas alturas.
O objetivo é saber de forma eficiente qual é a altura crítica(que vai quebrar) e com poucas bolas jogadas(tentativas).

Para solucionar isso será necessário duas fases:
1. A primeira será definir a quantidade de altura que será espaçada entre as tentativas ex: tentar de 5 e 5. Mas definir um valor aleatório não minimiza a quantidade de tentativas. Portanto usaremos **√n** para ser o espaçamento entre as tentativas 
2. Quando encontrarmos uma altura que a bola será quebrada, devemos voltar um passo de **√n** e percorrermos todos os elementos entre o ponto que ocorreu a quebra e o passo anterior onde a bola não quebrou, começando do ponto em que a bola não quebrou. Dessa forma no pior dos casos percorreremos **√n**

Implementação:
`const jmpSize = Math.floor(Math.sqrt(breaks.length));`
  `let i = jmpSize;`
  `for(; i <= breaks.length; i+=jmpSize) {
    `if(breaks[i]){
      `break;
    `}
  `}
  `i -= jmpSize;`
  `for(let j = 0; j <= jmpSize && i < breaks.length; i++, j++){
    `if(breaks[i]){
      `return i;
    `}
  `}`
  `return -1`