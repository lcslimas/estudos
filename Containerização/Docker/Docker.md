O Docker é uma plataforma que permite criar, gerenciar e executar aplicativos em contêineres. Ele facilita o desenvolvimento, implantação e execução de software ao fornecer uma camada de abstração que empacota o aplicativo e todas as suas dependências em uma única unidade chamada **contêiner**.

---

### **Componentes principais do Docker**

1. **Imagem**:  
    Uma imagem é um conjunto de instruções que define tudo o que é necessário para rodar um aplicativo (sistema operacional, bibliotecas, código, dependências). É como uma "receita" para criar contêineres.
    
2. **Contêiner**:  
    Um contêiner é uma instância de uma imagem. Ele é leve, isolado e contém tudo o que o aplicativo precisa para rodar.
    
3. **Dockerfile**:  
    Um arquivo de texto com instruções para criar uma imagem. É onde você define as dependências e configurações do seu aplicativo.
    
4. **Docker Engine**:  
    O mecanismo responsável por criar e executar imagens e contêineres.
    
5. **Docker Hub**:  
    Um repositório público onde você pode encontrar e compartilhar imagens do Docker.


### **Por que usar o Docker?**

1. **Portabilidade**:  
    Um contêiner Docker pode rodar em qualquer lugar, seja no seu laptop, em servidores na nuvem ou em um ambiente de produção.
    
2. **Consistência**:  
    Evita o famoso problema de "funciona na minha máquina, mas não no servidor" ao garantir que o aplicativo e suas dependências sejam iguais em todos os ambientes.
    
3. **Eficiência**:  
    Contêineres são leves e utilizam os recursos do sistema de forma eficiente, permitindo rodar várias instâncias no mesmo servidor.
    
4. **Isolamento**:  
    Cada contêiner roda de forma independente, sem interferir em outros aplicativos ou serviços.
    
5. **Rapidez**:  
    Contêineres são mais rápidos para iniciar e escalar em comparação com máquinas virtuais tradicionais.

### **Exemplo de uso de Docker**

Para usar imagem do postgresql9.5

basta:
1. Baixar o docker no computador.
2. Executar **docker pull postgres9.5**;
3. E após finalizar o pull basta criar e iniciar o conteiner: 
  ` docker run --name postgres9.5 \ -e POSTGRES_USER=seu_usuario \ -e POSTGRES_PASSWORD=sua_senha \ -e POSTGRES_DB=seu_banco \ -p 5432:5432 \ -d postgres:9.5` 

### Comandos úteis
**Docker stop** `nome da imagem` - para parar o conteiner; 
**Docker start** `nome da imagem` - para inciar o conteiner; 
**docker logs** `nome da imagem` - para receber logs do conteiner; 
**docker ps** - para visualizar conteineres em execução (se colocar flag -a, mostra os ativos e inativos);
