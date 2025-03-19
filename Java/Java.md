Linguagem de Programação orientada a objeto com sua primeira versão oficial de 1996.

Seus pontos principais está:
- Possui a JVM, que permite que seu código seja rodado em qualquer sistema.
- Possui capacidade de gerenciar os recursos utilizados de forma automática, por meio do Garbage Collector.
- Vasta comunidade e tempo no mercado.

## Versões
##### Java 8
Versão LTS muito importante para a linguagem, nessa versão foram adicionadas diversas funcionalidades, como:
- **Stream API**: com diversos métodos capazes de lidar de forma otimizadas com a Collection API.
- **Lambda Function**: Diminuindo a verbosidade no uso da Stream API.
- **Optional**: Funcionalidade focada em diminuir problemas com NullPointerException.
- **Date and Time API**: Api nova e melhorada para lidar com data e hora, substituindo a problematica `java.util.Date` e `Calendar`.
- **Interface default**: Agora permite implementar método padrão já na interface.
##### Java 11
Versão LTS após o Java 8. Teve algumas atualizações importante, entre elas:
- **Var**: permite usar o tipo var que infere o tipo do arquivo em tempo de compilação.
- **Novos métodos para String**: como .trip(), .repeat();
- Permite executar arquivo .java sem necessidade de compilação explícita;
- Última versão para a versão Java EE pois Oracle não mais focaria nela, dando para a Eclipse Foundation lidar com e tornando-se o Jakarta EE.
- **HTTP/2**: reduz a latência em comunicações cliente-servidor, melhorando a eficiência de chamadas em microsserviços.
- Melhor suporte a **containeres**, pois O JVM passou a respeitar os limites de CPU e memória definidos pelo contêiner (por exemplo, `--memory` e `--cpus` no Docker), portanto trouxe melhorias para execução em ambientes leves. 
- Melhor suporte a **microsserviço** com o HTTP/2 (antes era usada biblioteca do Apache).
