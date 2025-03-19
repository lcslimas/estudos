Nessa arquitetura, ocorre um foco na camada de domínio (**Core**), para isso ela é isolanda. E toda as integrações com as tecnologias ocorrem por **Ports**, por meio de **Adapters**. Ou seja, qualquer integração com dependência externa como Banco de Dados, API, UI e Frameworks, são separadas do Core (lógica de negócio). 

## **Ports** 
Definem como a aplicação se comunica com o mundo externo. O core só se comunica com o mundo externo por meio das interfaces/contratos dependendo somente de abstrações, aplicando o D do SOLID.
	**Driving Ports:** Representam as **entradas** para a aplicação. São usadas para expor os casos de uso ou funcionalidades principais do sistema.
		**Objetivo:** Permitir que algo externo (como um usuário, um evento, ou outra aplicação) ative comportamentos na aplicação. **Ex**: chamadas HTTP para um Rest API
	 **Driven Ports:** Representam as **saídas** da aplicação. São usadas pela lógica central (domínio) para se comunicar com sistemas externos.
		**Objetivo:** Definir como a aplicação consome serviços externos, como bancos de dados, filas, ou APIs de terceiros. **Ex**: Uma porta para salvar dados em um repositório ou Uma porta para enviar notificações via e-mail ou SMS.
		
## Adapters
Implementações externas que comunicaram com o Core por meio dos Ports.
	 **Driving Adapters:** Implementam os driving ports e traduzem as requisições externas para a aplicação. **Ex**: Um controller REST traduz uma requisição HTTP em uma chamada ao caso de uso.
	 **Driven Adapters:** Implementam os driven ports e traduzem as chamadas feitas pelo domínio para a tecnologia específica. **Ex**: Um repositório que usa um ORM como Hibernate para persistir dados.

A arquitetura recebe esse nome pq é representada por uma parte central, o Core, e as faces desse hexágono seriam os Ports que ligam o Core para as implementações externas:

![[Pasted image 20250102213604.png]]
## Vantagens 
- **Isolamento:** O domínio não conhece detalhes de infraestrutura ou tecnologia.
- **Facilidade de Teste:** É possível testar o domínio isoladamente usando mocks para os ports.
- **Flexibilidade:** Trocar tecnologias (como mudar de um banco relacional para NoSQL) exige mudanças apenas nos adaptadores.