# Memoteca

Memoteca é uma aplicação CRUD desenvolvida com Angular e TypeScript para registrar pensamentos, citações, trechos de músicas e ideias. Os dados são persistidos em uma API simulada (Mock API) criada com JSON Server.

![Demonstração da aplicação Memoteca](docs/memoteca-demo.gif)

## Funcionalidades

- Listagem de pensamentos em um mural.
- Criação de um pensamento com autoria e escolha do modelo do card.
- Edição de pensamentos existentes.
- Exclusão com tela de confirmação.
- Pré-visualização instantânea do card durante o preenchimento.
- Navegação entre telas sem recarregar a página.

## Recursos do Angular utilizados

- **Two-way data binding:** `[(ngModel)]` mantém os campos do formulário e a prévia do card sincronizados.
- **Interpolação:** `{{ ... }}` exibe conteúdo, autoria e outros valores no template.
- **Property binding e event binding:** propriedades e eventos conectam os templates à lógica dos componentes.
- **Componentização:** cabeçalho, rodapé, listagem, card, criação, edição e exclusão são componentes separados.
- **Diretivas:** `*ngFor`, `*ngIf` e `ngClass` controlam a renderização e os estilos dos elementos.
- **Rotas parametrizadas:** o Angular Router identifica o pensamento que será editado ou excluído pelo `id` da URL.
- **Serviços e injeção de dependência:** `PensamentoService` centraliza a comunicação com a API.
- **HttpClient e Observables:** as operações HTTP são assíncronas e retornam `Observable`.
- **Interfaces TypeScript:** a interface `Pensamento` tipa os dados usados pela aplicação.

## Operações do CRUD

| Operação | Método HTTP | Endpoint |
| --- | --- | --- |
| Listar pensamentos | `GET` | `/pensamentos` |
| Buscar por ID | `GET` | `/pensamentos/:id` |
| Criar pensamento | `POST` | `/pensamentos` |
| Editar pensamento | `PUT` | `/pensamentos/:id` |
| Excluir pensamento | `DELETE` | `/pensamentos/:id` |

Durante o desenvolvimento, a Mock API fica disponível em `http://localhost:3000/pensamentos`.

## Tecnologias

- Angular 14
- TypeScript 4.7
- RxJS
- Angular Router
- Angular Forms
- Angular HttpClient
- JSON Server
- HTML e CSS

## Como executar

Este projeto utiliza Node.js 16.20.2, uma versão compatível com o Angular 14.

Instale as dependências do front-end:

```bash
npm install
```

Em um terminal, inicie a aplicação Angular:

```bash
ng serve
```

Em outro terminal, inicie a Mock API:

```bash
cd backend
npm install
npm start
```

Acesse `http://localhost:4200` no navegador. Os dois terminais precisam permanecer abertos para que todas as operações do CRUD funcionem.

## Estrutura principal

```text
memoteca/
├── backend/
│   ├── db.json
│   └── package.json
├── docs/
│   └── memoteca-demo.gif
└── src/
    └── app/
        ├── componentes/
        │   ├── cabecalho/
        │   ├── pensamentos/
        │   │   ├── criar-pensamento/
        │   │   ├── editar-pensamento/
        │   │   ├── excluir-pensamento/
        │   │   ├── listar-pensamento/
        │   │   ├── pensamento/
        │   │   └── pensamento.service.ts
        │   └── rodape/
        └── app-routing.module.ts
```
