# 💊 Sistema de Farmácia

Aplicação web para gerenciar **pacientes, medicamentos e vendas** de uma farmácia, com interface em Bootstrap e API REST em Node.js + MongoDB. Desenvolvida como projeto de avaliação escolar.

## ✨ Funcionalidades

- Cadastro, listagem, edição e exclusão de **pacientes**, **medicamentos** e **vendas** (CRUD completo)
- Busca de medicamentos por nome (sem diferenciar maiúsculas de minúsculas)
- Validação na venda: só é registrada se o paciente e o medicamento já estiverem cadastrados
- Visualização em tabelas
- Layout responsivo (versão mobile)
- Alternância entre tema claro e escuro

## 🛠️ Tecnologias

![HTML](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Bootstrap](https://img.shields.io/badge/Bootstrap-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?style=for-the-badge&logo=express&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white)

## 📁 Estrutura

```
sistema-farmacia/
├── pages/        # Páginas HTML (cadastro, listagem, atualização)
├── public/       # Arquivos estáticos (CSS, JS, imagens)
├── index.html    # Página inicial
└── server.js     # Servidor Express e rotas da API
```

## 🚀 Como executar

### Pré-requisitos

- [Node.js](https://nodejs.org/) (versão LTS)
- [MongoDB](https://www.mongodb.com/try/download/community) rodando em `127.0.0.1:27017`

### Passo a passo

```bash
git clone https://github.com/EricPfeuti/sistema-farmacia.git
cd sistema-farmacia
npm install
node server.js
```

Acesse **http://localhost:3001**. O banco `farmacia` e as coleções `pacientes`, `medicamentos` e `vendas` são criados automaticamente no primeiro cadastro.

## 🔌 Rotas da API

| Recurso | Listar | Buscar por ID | Criar | Atualizar | Excluir |
|---|---|---|---|---|---|
| Pacientes | `GET /pacientes` | `GET /paciente/:id` | `POST /cadastroPaciente` | `POST /atualizarpaciente` | `POST /deletarpaciente` |
| Medicamentos | `GET /medicamentos` | `GET /medicamento/:id` | `POST /cadastroMedicamento` | `POST /atualizarmedicamento` | `POST /deletarmedicamento` |
| Vendas | `GET /vendas` | `GET /venda/:id` | `POST /cadastroVenda` | `POST /atualizarvenda` | `POST /deletarvenda` |

Busca por nome: `GET /filtrarNome?nomeMedicamento=dipirona`

### Modelos de dados

| Coleção | Campos |
|---|---|
| `pacientes` | `nome`, `dataNascimento`, `numeroCPF` |
| `medicamentos` | `nomeMedicamento`, `codigo`, `dosagem` |
| `vendas` | `nome`, `dataCompra`, `nomeMedicamento`, `quantidade` |
