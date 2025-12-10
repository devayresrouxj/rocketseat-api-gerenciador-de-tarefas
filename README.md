![python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![flask](https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white)

# 📝 API de Gerenciamento de Tarefas

API RESTful desenvolvida com Flask para gerenciar tarefas, implementando operações CRUD completas.

## 📋 Sobre o Projeto

Este projeto foi desenvolvido durante as aulas do módulo **Desenvolvimento de APIs com Flask** da [Formação Python](https://www.rocketseat.com.br/formacao/python) da [Rocketseat](https://www.rocketseat.com.br/).

O objetivo é introduzir os fundamentos do desenvolvimento de APIs REST utilizando Flask, abordando conceitos essenciais como rotas, métodos HTTP, manipulação de JSON e testes automatizados.

## ✨ Funcionalidades

A API oferece um CRUD completo para gerenciamento de tarefas:

- **POST /tasks** - Criar nova tarefa
- **GET /tasks** - Listar todas as tarefas
- **GET /tasks/{id}** - Buscar tarefa específica por ID
- **PUT /tasks/{id}** - Atualizar tarefa existente
- **DELETE /tasks/{id}** - Deletar tarefa

## 🎯 Conceitos Aplicados

### Desenvolvimento de APIs REST

- **Arquitetura REST**: Implementação de princípios RESTful
- **Métodos HTTP**: GET, POST, PUT, DELETE
- **Status Codes**: 200 (sucesso), 404 (não encontrado)
- **Endpoints**: Rotas organizadas e semânticas

### Flask Framework

- **Rotas e decoradores**: `@app.route()`
- **Request handling**: Captura de dados com `request.get_json()`
- **Response formatting**: Retorno de JSON com `jsonify()`
- **Parâmetros de rota**: Captura de IDs dinâmicos
- **Servidor de desenvolvimento**: Configuração e execução

### Estrutura de Dados

- **Modelo de dados**: Classe `Task` representando tarefas
- **Serialização**: Conversão de objetos para dicionários (JSON)
- **Armazenamento em memória**: Lista de tarefas (não persistente)

### Testes Automatizados

- **Pytest**: Framework de testes
- **Testes de integração**: Validação de endpoints
- **Requests library**: Simulação de requisições HTTP
- **Assertions**: Verificação de respostas e comportamentos

## 🏗️ Estrutura do Projeto

```
rocketseat-api-gerenciador-de-tarefas
├── app.py                 # Aplicação Flask principal
├── tests.py               # Suite de testes automatizados
├── requirements.txt       # Dependências do projeto
└── models/
    └── task.py           # Modelo da entidade Task
```

## 🚀 Como Executar

### Pré-requisitos

- Python 3.x instalado
- pip (gerenciador de pacotes Python)

### Instalação

1. Clone este repositório:

```bash
git clone https://github.com/devayresrouxj/rocketseat-api-gerenciador-de-tarefas.git
```

2. Navegue até o diretório do projeto:

```bash
cd rocketseat-api-gerenciador-de-tarefas
```

3. Crie um ambiente virtual (recomendado):

```bash
python -m venv venv
```

4. Ative o ambiente virtual:

```bash
# Windows
venv\Scripts\activate

# Linux/Mac
source venv/bin/activate
```

5. Instale as dependências:

```bash
pip install -r requirements.txt
```

### Executando a API

1. Inicie o servidor Flask:

```bash
python app.py
```

2. A API estará disponível em: `http://127.0.0.1:5000`

3. Você verá a mensagem:

```
 * Running on http://127.0.0.1:5000
 * Debug mode: on
```

### Executando os Testes

1. Com a API rodando em um terminal, abra outro terminal

2. Execute os testes:

```bash
pytest tests.py -v
```

3. Você verá o resultado dos testes:

```
test_create_task PASSED
test_get_tasks PASSED
test_get_task PASSED
test_update_task PASSED
test_delete_task PASSED
```

## 📡 Endpoints da API

### 1. Criar Tarefa

```http
POST /tasks
Content-Type: application/json

{
  "title": "Minha tarefa",
  "description": "Descrição da tarefa"
}
```

**Resposta:**

```json
{
  "message": "Nova tarefa criada com sucesso",
  "id": 1
}
```

### 2. Listar Todas as Tarefas

```http
GET /tasks
```

**Resposta:**

```json
{
  "tasks": [
    {
      "id": 1,
      "title": "Minha tarefa",
      "description": "Descrição da tarefa",
      "completed": false
    }
  ],
  "total_tasks": 1
}
```

### 3. Buscar Tarefa por ID

```http
GET /tasks/1
```

**Resposta:**

```json
{
  "id": 1,
  "title": "Minha tarefa",
  "description": "Descrição da tarefa",
  "completed": false
}
```

### 4. Atualizar Tarefa

```http
PUT /tasks/1
Content-Type: application/json

{
  "title": "Tarefa atualizada",
  "description": "Nova descrição",
  "completed": true
}
```

**Resposta:**

```json
{
  "message": "Tarefa atualizada com sucesso"
}
```

### 5. Deletar Tarefa

```http
DELETE /tasks/1
```

**Resposta:**

```json
{
  "message": "Tarefa deletada com sucesso"
}
```

## 🛠️ Tecnologias

- **[Python 3.x](https://www.python.org/)** - Linguagem de programação
- **[Flask 2.3.0](https://flask.palletsprojects.com/)** - Framework web minimalista
- **[Werkzeug 2.3.0](https://werkzeug.palletsprojects.com/)** - Biblioteca WSGI (dependência do Flask)
- **[Requests 2.31.0](https://requests.readthedocs.io/)** - Biblioteca para requisições HTTP
- **[Pytest 7.4.3](https://pytest.org/)** - Framework de testes

## 🧪 Testes

O projeto inclui uma suite completa de testes automatizados que cobrem:

- ✅ Criação de tarefas
- ✅ Listagem de todas as tarefas
- ✅ Busca de tarefa específica
- ✅ Atualização de tarefas
- ✅ Deleção de tarefas
- ✅ Tratamento de erros (404)

Os testes seguem o fluxo completo de uma aplicação real, garantindo que todos os endpoints funcionem corretamente.

## 🎓 Aprendizados

Este projeto consolidou conhecimentos em:

- **APIs REST**: Princípios e boas práticas de design de APIs
- **Flask**: Framework para desenvolvimento web em Python
- **HTTP**: Métodos, status codes e estrutura de requisições/respostas
- **JSON**: Serialização e desserialização de dados
- **CRUD**: Operações básicas de banco de dados (Create, Read, Update, Delete)
- **Testes**: Desenvolvimento orientado a testes (TDD)
- **Validação**: Tratamento de erros e casos extremos
- **Ambiente virtual**: Isolamento de dependências

## ⚠️ Observações

- **Armazenamento em memória**: As tarefas são armazenadas em uma lista Python e são perdidas ao reiniciar o servidor
- **Sem autenticação**: A API não possui sistema de autenticação
- **Ambiente de desenvolvimento**: Configurada com `debug=True` (não usar em produção)

## 📖 Recursos Adicionais

- [Documentação Flask](https://flask.palletsprojects.com/)
- [HTTP Methods](https://developer.mozilla.org/pt-BR/docs/Web/HTTP/Methods)
- [Pytest Documentation](https://docs.pytest.org/)

## 📝 Licença

Este projeto está sob a licença MIT.

---

Desenvolvido com 💜 durante a Formação Python da Rocketseat
