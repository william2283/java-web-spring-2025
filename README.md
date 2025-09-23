# Sistema de Usuários e Departamentos (API REST)

### Visão Geral
API REST para gerenciar usuários e departamentos, permitindo:
- Buscar todos os usuários  
- Buscar um usuário pelo seu ID  
- Inserir um novo usuário (com ou sem departamento)  

![Modelo conceitual](https://raw.githubusercontent.com/devsuperior/java-web-spring-2022/main/img/dominio.png)



### Desenvolvimento moderno: relacional -> objeto -> JSON

![Objetos](https://raw.githubusercontent.com/devsuperior/java-web-spring-2022/main/img/objetos.png)

- Criar o projeto Spring Boot  
- Implementar o modelo de domínio (`User` e `Department`)  
- Mapear objetos para tabelas com JPA  
- Configurar o banco H2 (em memória)  
- Criar endpoints da API REST  


### Rodando o Projeto

1. Java 17+  
2. Executar `Application.java`  
3. Banco H2 em memória: `jdbc:h2:mem:testdb`  
4. Console H2: `http://localhost:8080/h2-console`  
   - Usuário: `sa`  
   - Senha: (vazio)  


### Populando o Banco

```sql
INSERT INTO TB_DEPARTMENT (id, name) VALUES (1, 'Gestão');
INSERT INTO TB_DEPARTMENT (id, name) VALUES (2, 'Informática');

Endpoints da API

| Método | Endpoint    | Descrição                |
| ------ | ----------- | ------------------------ |
| GET    | /users      | Buscar todos os usuários |
| GET    | /users/{id} | Buscar usuário pelo ID   |
| POST   | /users      | Criar um novo usuário    |


[
  {
    "id": 1,
    "name": "Maria",
    "email": "maria@gmail.com",
    "department": { "id": 1, "name": "Gestão" }
  },
  {
    "id": 2,
    "name": "Bob",
    "email": "bob@gmail.com",
    "department": { "id": 2, "name": "Informática" }
  },
  {
    "id": 3,
    "name": "Ana",
    "email": "ana@gmail.com",
    "department": null
  }
]




