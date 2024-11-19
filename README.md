# Escola API

## 📖 Introdução

Este projeto é uma API desenvolvida em Django Rest Framework (DRF) para gerenciar dados de uma escola. Ele oferece funcionalidades para gerenciar estudantes, cursos e matrículas, além de endpoints específicos para consultas personalizadas.

---

## 📑 Sumário

- [Funcionalidades](#-funcionalidades)
- [Tecnologias Utilizadas](#-tecnologias-utilizadas)
- [Requisitos](#-requisitos)
- [Como Configurar](#-como-configurar)
- [Endpoints](#-endpoints)
- [Modelos de Dados](#-modelos-de-dados)
- [Serializers](#-serializers)
- [Licença](#-licença)

---

## ✨ Funcionalidades

- Gerenciamento de estudantes: criação, listagem, atualização e exclusão.
- Gerenciamento de cursos: criação, listagem, atualização e exclusão.
- Gerenciamento de matrículas: criação, listagem, atualização e exclusão.
- Listar matrículas associadas a um estudante.
- Listar estudantes matriculados em um curso.

---

## 🛠 Tecnologias Utilizadas

- Python 3.8+
- Django 4.0+
- Django Rest Framework
- SQLite (banco de dados padrão, mas pode ser substituído por outro)

---

## 📋 Requisitos

- Python 3.8 ou superior instalado
- Pip para gerenciar pacotes
- Virtualenv (opcional, mas recomendado)

---

## ⚙️ Como Configurar

1. Clone este repositório no seu ambiente local.
2. Crie e ative um ambiente virtual.
3. Instale as dependências listadas no arquivo `requirements.txt`.
4. Realize as migrações para configurar o banco de dados.
5. Inicie o servidor de desenvolvimento e acesse a aplicação.

---

## 🌐 Endpoints

### Estudantes
- **`GET /estudantes/`**: Lista todos os estudantes cadastrados.
- **`POST /estudantes/`**: Cadastra um novo estudante.
- **`GET /estudantes/{id}/`**: Detalha informações de um estudante específico.
- **`PUT /estudantes/{id}/`**: Atualiza informações de um estudante.
- **`DELETE /estudantes/{id}/`**: Remove um estudante do sistema.

### Cursos
- **`GET /cursos/`**: Lista todos os cursos cadastrados.
- **`POST /cursos/`**: Cadastra um novo curso.
- **`GET /cursos/{id}/`**: Detalha informações de um curso específico.
- **`PUT /cursos/{id}/`**: Atualiza informações de um curso.
- **`DELETE /cursos/{id}/`**: Remove um curso do sistema.

### Matrículas
- **`GET /matricula/`**: Lista todas as matrículas cadastradas.
- **`POST /matricula/`**: Cadastra uma nova matrícula.
- **`GET /matricula/{id}/`**: Detalha informações de uma matrícula específica.
- **`PUT /matricula/{id}/`**: Atualiza informações de uma matrícula.
- **`DELETE /matricula/{id}/`**: Remove uma matrícula do sistema.

### Consultas Personalizadas
- **`GET /estudantes/{id}/matriculas/`**: Lista todas as matrículas associadas a um estudante.
- **`GET /cursos/{id}/matriculas/`**: Lista todos os estudantes matriculados em um curso.

---

## 🗂 Modelos de Dados

### Estudante
- **`id`**: Identificador único.
- **`nome`**: Nome completo do estudante.
- **`email`**: Endereço de e-mail válido.
- **`cpf`**: CPF do estudante (11 caracteres).
- **`data_nascimento`**: Data de nascimento.
- **`celular`**: Número de celular (14 caracteres).

### Curso
- **`id`**: Identificador único.
- **`codigo`**: Código do curso (máximo de 10 caracteres).
- **`descricao`**: Descrição do curso.
- **`nivel`**: Nível do curso (Básico, Intermediário ou Avançado).

### Matrícula
- **`id`**: Identificador único.
- **`estudante`**: Referência ao estudante matriculado.
- **`curso`**: Referência ao curso da matrícula.
- **`periodo`**: Período do curso (Matutino, Vespertino ou Noturno).

---

## 🧩 Serializers

- **EstudanteSerializer**: Serializa os campos `id`, `nome`, `email`, `cpf`, `data_nascimento` e `celular`.
- **CursoSerializer**: Serializa todos os campos do modelo `Curso`.
- **MatriculaSerializer**: Serializa todos os campos do modelo `Matricula`.
- **ListaMatriculasEstudanteSerializer**: Retorna o nome do curso e o período para matrículas associadas a um estudante.
- **ListaMatriculasCursoSerializer**: Retorna os nomes dos estudantes matriculados em um curso.
