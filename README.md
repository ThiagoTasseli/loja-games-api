# 🕹️ Loja de Games — API REST

![Java](https://img.shields.io/badge/Java-17-orange?style=flat-square&logo=openjdk)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.4-6DB33F?style=flat-square&logo=springboot)
![MySQL](https://img.shields.io/badge/MySQL-8-4479A1?style=flat-square&logo=mysql&logoColor=white)
![JWT](https://img.shields.io/badge/Auth-JWT-black?style=flat-square&logo=jsonwebtokens)

API REST de um e-commerce de games, com cadastro de **categorias**, **produtos** e **usuários**, protegida por **Spring Security + JWT**.

Projeto desenvolvido no bootcamp **Java Full Stack da Generation Brasil**.

---

## 🚀 Endpoints

### 🔐 Usuários
| Método | Rota | Descrição | Acesso |
|---|---|---|---|
| `POST` | `/usuarios/cadastrar` | Cadastra usuário | Público |
| `POST` | `/usuarios/logar` | Autentica e retorna o token JWT | Público |
| `GET` | `/usuarios` | Lista usuários | Token |
| `GET` | `/usuarios/{id}` | Busca usuário por ID | Token |
| `PUT` | `/usuarios/atualizar` | Atualiza usuário | Token |

### 🏷️ Categorias
| Método | Rota | Descrição |
|---|---|---|
| `GET` | `/categorias` | Lista categorias |
| `GET` | `/categorias/{id}` | Busca por ID |
| `GET` | `/categorias/titulo/{titulo}` | Busca por título |
| `POST` | `/categorias` | Cria categoria |
| `PUT` | `/categorias` | Atualiza categoria |
| `DELETE` | `/categorias/{id}` | Remove categoria |

### 🎮 Produtos
| Método | Rota | Descrição |
|---|---|---|
| `GET` | `/produtos` | Lista produtos |
| `GET` | `/produtos/{id}` | Busca por ID |
| `GET` | `/produtos/nome/{nome}` | Busca por nome |
| `GET` | `/produtos/preco-maior/{valor}` | Produtos acima de um preço |
| `GET` | `/produtos/preco-menor/{valor}` | Produtos abaixo de um preço |
| `POST` | `/produtos` | Cria produto |
| `PUT` | `/produtos` | Atualiza produto |
| `DELETE` | `/produtos/{id}` | Remove produto |

> Categorias e produtos exigem o header `Authorization: Bearer <token>`.

---

## 🔗 Relacionamentos

- Uma **Categoria** possui muitos **Produtos** (`@OneToMany`)
- Cada **Produto** pertence a uma **Categoria** (`@ManyToOne`)

---

## 🛠️ Tecnologias

- Java 17 · Spring Boot 3.4
- Spring Web · Spring Data JPA · Bean Validation
- Spring Security · JWT (jjwt)
- MySQL

---

## ▶️ Como rodar

```bash
git clone https://github.com/ThiagoTasseli/loja-games-api.git
cd loja-games-api

# Opcional: variáveis de ambiente
export DB_PASSWORD=sua_senha_mysql
export JWT_SECRET=$(openssl rand -base64 32)

./mvnw spring-boot:run
```

O banco `db_loja-games` é criado automaticamente no MySQL local.

---

## 🌿 Branches

| Branch | Etapa |
|---|---|
| `01_Model_Repository` | Entidades e repositórios |
| `02_Controller` | Controllers e CRUD |
| `03_Security` / `04_Security` | Autenticação com JWT |
| `main` | Versão final |

---

## 👨‍💻 Autor

**Thiago Tasseli** · [LinkedIn](https://www.linkedin.com/in/thiagotasseli-tech/) · [GitHub](https://github.com/ThiagoTasseli)
