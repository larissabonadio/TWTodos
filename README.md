# TWTodos
Aplicação web de gerenciamento de tarefas desenvolvida com **ASP.NET Core MVC**, **C#** e **Entity Framework Core**, utilizando **SQLite** como banco de dados.

O projeto foi desenvolvido como prática acompanhando o vídeo da TreinaWeb **"Criando um projeto completo com ASP.NET"**, adaptando e implementando os conceitos apresentados no curso em um projeto próprio.

## Sobre o projeto
O TWTodos é uma aplicação simples de lista de tarefas que permite cadastrar, visualizar, editar, excluir e concluir tarefas.
Cada tarefa possui:
- **Título**
- **Data de criação**
- **Data de entrega**
- **Data de conclusão**, quando finalizada

O projeto utiliza o padrão arquitetural **MVC (Model-View-Controller)**, separando as responsabilidades entre modelos, controladores e interfaces de usuário.

## Funcionalidades
- [x] Listagem de tarefas
- [x] Cadastro de novas tarefas
- [x] Edição de tarefas
- [x] Exclusão de tarefas
- [x] Conclusão de tarefas
- [x] Persistência dos dados em banco SQLite
- [x] Validação dos dados informados
- [x] Validação do título com quantidade mínima e máxima de caracteres
- [x] Validação para que a data de entrega seja atual ou futura
- [x] Tratamento de tarefas inexistentes com resposta `NotFound`

## Tecnologias utilizadas
- **C#**
- **ASP.NET Core MVC**
- **.NET 10**
- **Entity Framework Core 10**
- **Entity Framework Core SQLite**
- **SQLite**
- **Razor Views**
- **Data Annotations**
- **Git e GitHub**

O arquivo de projeto utiliza o SDK web do .NET 10 e as dependências do Entity Framework Core Design e SQLite. 

### Principais componentes

**Models/Todo.cs**
Representa a entidade de tarefa. O modelo possui propriedades como `Id`, `Title`, `CreatedAt`, `Deadline` e `FinishedAt`. Também contém validações e o método `Finish()`, responsável por registrar a data de conclusão da tarefa.

**Contexts/TWTodosContext.cs**
É o contexto do Entity Framework Core responsável pelo acesso aos dados. O projeto utiliza um banco SQLite chamado `todos.sqlite3`.

**Controllers/TodoController.cs**
Controla as operações da aplicação, incluindo:
- Listagem;
- Cadastro;
- Edição;
- Exclusão;
- Conclusão de tarefas.

**Views/**
Contém as interfaces Razor utilizadas para apresentar e manipular as tarefas.

## Validações
O projeto utiliza validações do ASP.NET Core por meio de Data Annotations.

O título da tarefa:
- é obrigatório;
- deve possuir entre **3 e 100 caracteres**.

A data de entrega:
- é obrigatória;
- não pode ser anterior à data atual.

Quando uma tarefa é concluída, a propriedade `FinishedAt` recebe a data atual.

## Banco de dados
O projeto utiliza **SQLite** para armazenar as tarefas.

A configuração do banco está definida no `TWTodosContext`:
```csharp
optionsBuilder.UseSqlite("Data Source=todos.sqlite3");
```
As migrações do Entity Framework Core estão armazenadas na pasta `Migrations/`.

## Como executar o projeto

### Pré-requisitos
Antes de executar o projeto, tenha instalado:
- [.NET 10 SDK](https://dotnet.microsoft.com/download/dotnet/10.0)
- Git
- Um editor ou IDE compatível com projetos .NET, como Visual Studio ou Visual Studio Code

### 1. Clone o repositório
```bash
git clone https://github.com/larissabonadio/TWTodos.git
```

### 2. Acesse a pasta do projeto
```bash
cd TWTodos
```

### 3. Restaure as dependências
```bash
dotnet restore
```

### 4. Execute a aplicação
```bash
dotnet run

```
Depois de iniciar a aplicação, acesse a URL informada pelo terminal.
```text
/Todo/Index
```
## Objetivo de aprendizado
Este projeto foi desenvolvido com foco no aprendizado prático de desenvolvimento web utilizando o ecossistema .NET. 

Entre os principais conceitos praticados estão:
- Criação de aplicações ASP.NET Core MVC;
- Arquitetura MVC;
- Controllers e Actions;
- Models;
- Razor Views;
- Entity Framework Core;
- Integração com banco SQLite;
- Migrations;
- Operações CRUD;
- Validação de formulários;
- Rotas;
- Persistência de dados;
- Organização de um projeto ASP.NET Core.

## Referência
O desenvolvimento teve como referência a aula da TreinaWeb: https://www.youtube.com/watch?v=aYgAb5O_QXg

## Repositório
https://github.com/larissabonadio/TWTodos

## Licença
Este projeto foi desenvolvido para fins de estudo e aprendizado.