# Escola.API

API RESTful de gestão acadêmica construída para aplicar na prática **Clean Architecture** e princípios **SOLID**: gerencia alunos, professores, cursos, turmas e matrículas com isolamento completo entre domínio e infraestrutura.

## Como rodar

Execute a aplicação localmente via terminal na pasta raiz do projeto:

```bash
dotnet restore
dotnet run --project src/Escola.API
```

- Requer .NET SDK 10.0 instalado.
- Após iniciar, acesse `/swagger` no navegador para testar os endpoints.

## Estrutura

```text
Escola.API/
├── src/
│   ├── Escola.Domain/          # entidades (Aluno, Curso, Turma, Matricula) e interfaces
│   ├── Escola.Application/     # casos de uso, serviços, DTOs e validações
│   ├── Escola.Infra/           # DbContext (EF Core), mappings e repositórios
│   └── Escola.API/             # controllers REST, injeção de dependência e Swagger
└── tests/
    └── Escola.UnitTests/       # testes unitários das regras de matrícula e domínio
```

## Como adicionar uma entidade

1. Crie a entidade e sua interface de repositório em `Escola.Domain/`.
2. Implemente o mapeamento e o repositório concreto em `Escola.Infra/`.
3. Crie os DTOs e o caso de uso em `Escola.Application/` e registre no container IoC da `Escola.API`.

## Stack

C# + .NET 10 (ASP.NET Core Web API) + Entity Framework Core + xUnit.
Banco de dados: SQL Server / SQLite.