# 📚 Catálogo de Livros

[![License](https://img.shields.io/badge/license-MIT-green.svg?style=flat)](LICENSE)

Este projeto consiste em uma aplicação backend desenvolvida em Java com Spring Boot, cujo objetivo é consumir dados da API pública Gutendex e persistir informações de livros e autores em um banco de dados relacional.

<br>
<br>


🧱 Arquitetura e Organização:

<br>
<br>

<p align="center">
  <img src="https://github.com/user-attachments/assets/fa277e73-bf0f-4981-a9df-c6f2a249f7ed" alt="camadas-literalura" width="300">
</p>


<br>
<br>

A solução adota uma arquitetura em camadas, promovendo separação de responsabilidades e facilitando manutenção e evolução do código:

- Client: responsável pela comunicação HTTP com a API Gutendex, utilizando HttpClient e desserialização com Jackson.

- DTOs: representam fielmente os dados retornados pela API externa, garantindo desacoplamento entre a camada de integração e o modelo de domínio.

- Entities (JPA): modelam as entidades persistidas no banco de dados, com mapeamentos claros e relacionamentos bem definidos.

- Repositories: utilizam Spring Data JPA para abstração do acesso a dados e consultas derivadas.

- Service: concentra as regras de negócio, como prevenção de duplicidades, associação entre livros e autores e filtros específicos.

- Application (CommandLineRunner): provê uma interface de execução em modo console, permitindo interação direta com o sistema.


<br>
<br>


🔐 Regras de Negócio e Persistência

A aplicação garante:

Persistência consistente de autores, evitando duplicação por nome (case-insensitive).

Persistência controlada de livros, impedindo registros duplicados por título, idioma e autor.

Associação clara entre Livro → Autor por meio de relacionamento JPA.

Contagem de livros por idioma armazenados no banco de dados.

<br>
<br>


🔎 Funcionalidades Implementadas

- Busca de livros por título
Consulta a API Gutendex e permite salvar o livro no banco de dados mediante confirmação do usuário.

- Listagem de livros salvos
Exibe todos os livros persistidos no banco de dados local.

- Contagem de livros por idioma
Mostra a quantidade de livros armazenados por idioma disponível no banco.

- Listagem de autores
Apresenta todos os autores cadastrados no banco de dados.

- Listagem de autores vivos em um determinado ano
Filtra autores com base no ano informado, considerando nascimento e falecimento (processamento em memória).

- Exibição do Top 10 livros mais baixados
Consulta a API Gutendex e exibe os livros mais baixados, sem persistir os dados.

- Busca de autores por nome
Permite buscar autores pelo nome completo ou parcial, ignorando diferenças de maiúsculas e minúsculas.

- Busca de autores por ano de nascimento ou falecimento
Retorna autores cujo ano de nascimento ou falecimento corresponda ao ano informado (processamento em memória).


<br>
<br>


🌐 Integração com API Externa

A integração com a Gutendex é feita de forma segura:

Parâmetros de busca são devidamente codificados.

Tratamento básico de exceções de comunicação é aplicado para evitar falhas na execução.

<br>
<br>


🗄️ Configuração de Banco de Dados

O projeto utiliza PostgreSQL, com configuração externa via variáveis de ambiente.

<br>
<br>


 🛠️ **Tecnologias utilizadas**

- 📦 Spring Boot
- 🌐 HttpClient (Java 11+)
- 🐘 PostgreSQL
- 📚 Gutendex API


<br>
<br>

🚀 **Instalação e Uso**

⚙️ Como Executar o Projeto

📋 Pré-requisitos

☕ Java JDK 17+
🐘 PostgreSQL 12+
📦 Maven 3.8+

🎯 Instalação

1. Clone o repositório
````
git clone https://github.com/seu-usuario/book-catalog.git
````
2. Configure o banco de dados
````
CREATE DATABASE book_catalog;
````
3. Configure as variáveis de ambiente

4. Execute a aplicação

mvn spring-boot:run

## 📖 Funcionalidades Disponíveis

### **Menu Interativo**

Ao iniciar, você verá o seguinte menu:
```
===== Catálogo de Livros =====
1 - Buscar livro por título
2 - Listar todos os livros salvos
3 - Listar livros por idioma
4 - Listar autores salvos
5 - Listar autores vivos em determinado ano
6 - Listar Top 10 livros mais baixados
7 - Buscar autores por nome
8 - Buscar autores por ano de nascimento ou falecimento
0 - Sair
```

### **1️⃣ Buscar Livro por Título**
- Consulta a API Gutendex
- Exibe: título, autor, idioma, downloads
- Opção de salvar no banco de dados

**Exemplo:**
```
Digite o título: Pride and Prejudice
```

### **2️⃣ Listar Livros Salvos**
- Mostra todos os livros do banco local
- Inclui informações do autor

### **3️⃣ Estatísticas por Idioma**
- Conta livros em Português, Inglês e Francês
- Fonte: banco de dados local

### **4️⃣ Listar Autores**
- Exibe todos os autores salvos
- Mostra: nome, ano de nascimento e falecimento

### **5️⃣ Autores Vivos em Ano Específico**
- Filtra autores que estavam vivos no ano informado
- Lógica: nascimento ≤ ano ≤ falecimento (ou ainda vivo)

**Exemplo:**
```
Digite o ano: 1850
```

### **6️⃣ Top 10 Mais Baixados**
- Lista livros mais populares da API Gutendex
- Ordenados por número de downloads
- Não salva no banco

### **7️⃣ Buscar Autores por Nome**
- Busca parcial (case-insensitive)
- Exibe livros salvos do autor

**Exemplo:**

Digite o nome: shakespeare

Resultado: William Shakespeare

## **8️⃣ Buscar por Ano de Nascimento/Falecimento**

Encontra autores nascidos ou falecidos no ano exato. 
Mostra livros relacionados

<br>
<br>

--------


# Agradecimentos / Referências 

Alura - Cursos On Line de Tecnologia 

Oracle - Oracle Next Education - ONE


<br>


----------


# Autora:

Sheila M. M. L. Silva 

https://www.linkedin.com/in/sheilasheila/








