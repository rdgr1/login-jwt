# **Sistema de Autenticação com JWT**

Este projeto implementa um sistema de autenticação utilizando **JSON Web Tokens (JWT)**, composto por um backend em **Spring Boot** e um frontend em **Angular**.

## **Estrutura do Projeto**

```
login-jwt/
├── login-jwt-back-end-java/   # Backend em Spring Boot
└── login-jwt-front-end-type/  # Frontend em Angular
```

## **Tecnologias Utilizadas**

- **Backend:**
  - Java 11+
  - Spring Boot
  - Spring Security
  - JWT
  - JPA/Hibernate
  - Banco de Dados (ex.: MySQL, PostgreSQL)

- **Frontend:**
  - Angular 15+
  - TypeScript
  - Angular Material
  - RxJS

## **Funcionalidades**

- **Cadastro de Usuário:** Permite que novos usuários se registrem no sistema.
- **Login:** Autenticação de usuários utilizando JWT.
- **Proteção de Rotas:** Acesso restrito a determinadas rotas no frontend baseado na autenticação.
- **Autorização:** Controle de acesso a recursos específicos baseado em roles de usuário.

## **Pré-requisitos**

- **Backend:**
  - Java 11 ou superior instalado
  - Maven instalado
  - Banco de dados configurado

- **Frontend:**
  - Node.js e npm instalados
  - Angular CLI instalada

## **Como Executar o Projeto**

### **Backend**

1. **Configurar o Banco de Dados:**
   - o arquivo `application.properties` ou `application.yml` dentro de `login-jwt-back-end-java/src/main/resources/`, configure as propriedades do banco de dados:     ```properties
     spring.datasource.url=jdbc:mysql://localhost:3306/seu_banco_de_dados
     spring.datasource.username=seu_usuario
     spring.datasource.password=sua_senha
     spring.jpa.hibernate.ddl-auto=update
     spring.jpa.show-sql=true
     spring.jpa.properties.hibernate.format_sql=true
     ```
     *juste as configurações conforme o banco de dados que estiver utilizando.*
2. **Compilar e Executar:**
   ```bash
   cd login-jwt-back-end-java
   mvn clean install
   mvn spring-boot:run
   ```
   * backend estará disponível em `http://localhost:8080`.
### **Frontend**

1. **Instalar Dependências:**
   ```bash
   cd login-jwt-front-end-type
   npm install
   ```

2. **Executar o Servidor de Desenvolvimento:**
   ```bash
   ng serve
   ```
   * frontend estará disponível em `http://localhost:4200`.
## **Endpoints Principais do Backend**

- **Registro de Usuário:**
  - **URL:** `/api/auth/register`
  - **Método:** `POST`
  - **Descrição:** Registra um novo usuário no sistema.
  - **Payload:**
    ```json
    {
      "username": "exemplo",
      "email": "exemplo@dominio.com",
      "password": "senha123"
    }
    ```

- **Login:**
  - **URL:** `/api/auth/login`
  - **Método:** `POST`
  - **Descrição:** Autentica um usuário e retorna um token JWT.
  - **Payload:**
    ```json
    {
      "username": "exemplo",
      "password": "senha123"
    }
    ```

- **Acesso a Recurso Protegido:**
  - **URL:** `/api/user/me`
  - **Método:** `GET`
  - **Descrição:** Retorna informações do usuário autenticado.
  - **Cabeçalho:**
    - `Authorization: Bearer {token}`


Este projeto serve como uma base para sistemas que necessitam de autenticação e autorização utilizando JWT. Sinta-se à vontade para expandir as funcionalidades conforme as necessidades do seu aplicativo.

---

