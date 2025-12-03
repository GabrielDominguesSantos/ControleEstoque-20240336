
# Controle de Estoque

O principal objetivo deste projeto foi consolidar e aprimorar habilidades em Java e explorar o desenvolvimento de aplicações robustas utilizando o framework Spring Boot. O resultado é uma API RESTful completa para gerenciar um sistema fictício de Controle de Estoque, cobrindo operações CRUD (Create, Read, Update, Delete) em Clientes, Fornecedores, Produtos e Vendas.
## 1. Tecnologias Envolvidas

- **Linguagem:** Java 21  
- **Framework:** Spring Boot  
- **Gerenciador de Dependências:** Maven  
- **Banco de Dados:** MySQL (configurado via Xampp)  
## Demonstração

[![Vídeo Demonstrativo]()]()  

## 2. Guia de Instalação e Execução

### 1. Pré-requisitos
Certifique-se de ter os seguintes itens instalados em sua máquina:
- Java Development Kit (JDK) 21  
- Editor de Código: VS Code ou similar  
- Servidor Web e MySQL: **Xampp** ou similar  
- Maven (caso não utilize o VS Code com suporte automático)

---

### 2. Clonando o Repositório
Abra o terminal e execute:

```git clone https://github.com/GabrielDominguesSantos/ControleEstoque-20240336.git ```
## 3. Configuração do Banco de Dados (Xampp)

1. Instale o Xampp.

2. Inicie os serviços Apache e MySQL no painel de controle do Xampp.

3. Crie o banco de dados conforme configurado no arquivo application.properties.
## 4. Executando a Aplicação

Após a execução, a aplicação estará disponível em:

```http://localhost:8080```
## 4.1 Opção A: Utilizando o VS Code

1. Instale a extensão Extension Pack for Java.

2. Acesse o arquivo principal: ```src/main/java/.../ApiEstoqueApplication.java```

3. Clique no botão Play (Executar) no canto superior direito.
## 4.2 Opção B: Utilizando o Maven (Via Terminal)

1. Acesse o diretório raiz do projeto: ```cd ControleEstoque-20240336```

2. Instale as dependências: ```mvn clean install```

3. Execute o projeto: ```mvn spring-boot:run```

4. Alternativa - Gerando o JAR:
```
mvn clean package -DskipTests
java -jar target/controle-estoque-0.0.1-SNAPSHOT.jar
```
## 5. Endpoints da API

Utilize um cliente HTTP como Postman ou Insomnia para testar a API em: ```http://localhost:8080```
### POST/Criar

#### Cliente
**EndPoint**: ```/api/clientes``` 

**Template de JSON**
```json
{
  "nome": "Eduardo",
  "email": "eduardoaluno@gmail.com",
  "telefone": "19995863358"
}
```

#### Fornecedor
**Endpoint**: ```/api/fornecedores```

**Template de JSON**
```json
{
  "nome": "Wagner"
}

```

#### Categoria
**Endpoint**: ```/api/categorias```

**Template de JSON**
```json
{
  "nome": "Laticínios"
}

```

#### Produto
**Endpoint**: ```/api/produtos```

**Template de JSON**
```json
{
  "nome": "Danone",
  "preco": 6.7,
  "categoria": { "id": 1 },
  "fornecedores": [
    { "id": 1 }
  ],
  "estoque": {
    "quantidade": 5
  }
}

```

#### Venda
**Endpoint**: ```/api/vendas```

**Template de JSON**
```json
{
  "cliente": { "id": 1 },
  "itens": [
    {
      "produto": { "id": 1 },
      "quantidade": 2
    }
  ]
}

```
### GET/Buscar

#### Buscando Cliente:

1. Todos os clientes
**EndPoint**: ```http://localhost:8080/api/clientes```

2. Buscando clientes por ID
**EndPoint**: ```http://localhost:8080/api/clientes/IDDOCLIENTE```

#### Buscando Fornecedores:
1. Todos os fornecedores
**EndPoint**: ```http://localhost:8080/api/fornecedores```

2. Buscando fornecedores por ID
**EndPoint**: ```http://localhost:8080/api/fornecedores/IDDOFORNECEDOR```

#### Buscando Categorias:

1. Todos as categorias
**EndPoint**: ```http://localhost:8080/api/categorias```

2. Buscando categorias por ID
**EndPoint**: ```http://localhost:8080/api/categorias/IDDACATEGORIA```

#### Buscando Produtos

1. Todos os produtos
**EndPoint**: ```http://localhost:8080/api/produtos```

2. Buscando produtos por ID
**EndPoint**: ```http://localhost:8080/api/produtos/IDDOPRODUTO```



### PUT/Atualizar

#### Cliente: 
**Endpoint**: ```/api/clientes/{id}```

**Template de JSON**
```json
{
  "nome": "Pedro Miguel",
  "email": "pedromiguel@gmail.com",
  "telefone": "19992334754"
}

```
#### Fornecedor:
**Endpoint**: ```/api/fornecedores/{id}```

**Template de JSON**
```json
{
  "nome": "Miguel"
}

```

#### Categoria:
**Endpoint**: ```/api/categorias/{id}```

**Template de JSON**
```json
{
  "nome": "Eletrônico"
}

```

#### Produto:
**Endpoint**: ```/api/produtos/{id}```

**Template de JSON**
```json
{
  "nome": "Lasanha",
  "preco": 12.99,
  "categoria": { "id": 3 },
  "fornecedores": [
    { "id": 1 }
  ],
  "estoque": {
    "quantidade": 15
  }
}

```
### DELETE/Excluindo

#### Excluindo Cliente: 
**Endpoint** ```http://localhost:8080/api/clientes/IDDOCLIENTE```

#### Excluindo Fornecedor:
**Endpoint**: ```http://localhost:8080/api/fornecedores/IDDOFORNECEDOR```

#### Excluindo Categoria:
**Endpoint**: ```http://localhost:8080/api/categorias/IDDACATEGORIA```

#### Excluindo Produto:
**Endpoint**: ```http://localhost:8080/api/produtos/IDDOPRODUTO```
