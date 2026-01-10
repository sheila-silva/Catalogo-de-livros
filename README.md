# 📚 Catálogo de Livros

[![License](https://img.shields.io/badge/license-MIT-green.svg?style=flat)](LICENSE)

Este projeto é um **catálogo de livros** que permite consultar obras por meio da **API Gutendex** e armazená-las em um banco de dados **PostgreSQL**.  

## ✅ Funcionalidades principais

- 🔍 Buscar livros por título via API
- 📘 Listar todos os livros registrados no banco de dados
- 🖊️ Listar autores salvos
- 📅 Listar autores vivos em determinado ano
- 🌍 Listar livros por idioma: **inglês**, **francês** e **português**

## ✨ Funcionalidades extras implementadas

- 🔝 Listar os **10 livros mais baixados** da API Gutendex
- 👤 Buscar obras por **nome do autor**
- 📆 Buscar autores por **ano de nascimento ou falecimento**

## 🧩 Estrutura do projeto

O projeto é composto por:

- Código Java moderno com orientação a objetos
- DTOs para mapear dados da API
- Entidades JPA para persistência no banco de dados
- Repositórios com Spring Data JPA (com *derived queries*)
- Camada de serviço com a lógica de negócios
- Configuração de banco de dados via `application.properties`
- Interface interativa via console (menu de opções)

## 🛠️ Tecnologias utilizadas

- 📦 **Spring Boot**
- 🌐 **HttpClient (Java 11+)**
- 🔃 **Jackson (ObjectMapper)** 
- 🗄️ **Spring Data JPA**
- 🐘 **PostgreSQL**
- 📚 **Gutendex API** 






