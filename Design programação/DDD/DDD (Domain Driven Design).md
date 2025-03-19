Conceito utilizado para simplificar a camada de domínio da aplicação, tentando modelar a aplicação por meio de uma linguagem ubíqua, para que a solução seja entendível por todos os interessados.

O DDD busca criar um método de modelagem de sistema **focada no domínio** (muito utilizado em conjunto da arquitetura [hexagonal](Hexagonal))  , **colaborativa** e **modularizada por subdomínios**.

### **Principais Conceitos do DDD**

1. **Ubiquitous Language** (Linguagem Ubíqua):
    - Uma linguagem comum usada por todos os envolvidos no projeto (técnicos e não técnicos).
    - Reduz ambiguidades e falhas de comunicação.
2. **Bounded Context** (Contexto Delimitado):
    - Divisão do sistema em partes independentes que representam subdomínios do negócio.
    - Cada Bounded Context tem seu próprio modelo e linguagem específica.
3. **Entity** (Entidade):
    - Objeto do domínio que possui identidade única e persiste ao longo do tempo.
    - Exemplo: um "Cliente" identificado por um ID.
4. **Value Object** (Objeto de Valor):
    - Objeto imutável que não possui identidade própria.
    - Exemplo: um "Endereço" com rua, cidade e CEP.
5. **Aggregate** (Agregado):
    - Conjunto de objetos relacionados (Entities e Value Objects) que são tratados como uma unidade.
    - Exemplo: um "Pedido" com "Itens do Pedido".
6. **Repository**:
    - Padrão de acesso aos dados que fornece uma abstração para lidar com persistência.
    - Exemplo: `PedidoRepository` para recuperar objetos de Pedido.
7. **Service**:
    - Contém lógica que não pertence diretamente a uma entidade ou objeto de valor.
    - Exemplo: cálculo de frete em um sistema de e-commerce.
8. **Factory**:
    - Centraliza a lógica de criação de objetos complexos do domínio.
### **DDD vs. Design Patterns**

- **DDD**:
    - Envolve modelagem estratégica e tática.
    - Focado no entendimento e na representação do domínio do negócio.
- **Design Patterns**:
    - São soluções técnicas para problemas recorrentes de design em software (e.g., Singleton, Factory, Observer).
    - Não são específicos do domínio, mas sim gerais para resolver problemas técnicos.