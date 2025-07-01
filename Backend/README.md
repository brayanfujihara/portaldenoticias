# Portal de Notícias - Backend

Este projeto foi idealizado como uma aplicação fullstack, com backend em Java Spring Boot e persistência em PostgreSQL. O objetivo é fornecer uma API REST robusta para gerenciamento de notícias, categorias, usuários e publicidade, servindo como base para um portal de notícias.

## Como rodar

1. Instale o Java 21 e o PostgreSQL.
2. Crie o banco de dados `portalNoticias`.
3. Configure o arquivo `src/main/resources/application.properties`:
   ```
   spring.datasource.url=jdbc:postgresql://localhost:5432/portalNoticias
   spring.datasource.username=postgres
   spring.datasource.password=123
   ```
4. Rode o projeto:
   ```
   mvn spring-boot:run
   ```

## Endpoints principais

- `GET /api/noticias` — Lista todas as notícias
- `GET /api/noticias/{id}` — Detalhe de uma notícia
- `POST /api/noticias` — Cria uma nova notícia
- `PUT /api/noticias/{id}` — Atualiza uma notícia
- `DELETE /api/noticias/{id}` — Remove uma notícia

> Outros endpoints para categorias, usuários e publicidade podem ser consultados na documentação Swagger.

## Testando a API

- Acesse o Swagger em [http://localhost:8080/swagger-ui/index.html]
- Ou utilize o Postman para testar os endpoints manualmente.

## Estrutura do Projeto

- **Entidades:** Noticia, Categoria, Usuario, Publicidade
- **Relacionamentos:** Noticia → Categoria (`@ManyToOne`), outros conforme o modelo de domínio
- **Uso de `@Lob`:** Para textos longos em Noticia
- **Repositórios:** Todos estendem `JpaRepository`
- **Documentação:** Swagger UI disponível para consulta e testes
