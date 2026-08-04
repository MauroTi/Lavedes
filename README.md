# Lavedes

Loja virtual de uniformes e vestuário com HTML/Razor (`.cshtml`), C#, JavaScript, CSS e MySQL.

O acesso ao banco será feito em C# com `MySqlConnector` e SQL explícito, sem Entity Framework, Dapper ou outro ORM.

## Estrutura simplificada

- `src/Lavedes`: aplicação ASP.NET Core completa.
- `tests/Lavedes.Tests`: testes automatizados.
- `src/Lavedes/Documentation`: documentação técnica.

Consulte [src/Lavedes/Documentation/ARQUITETURA.md](src/Lavedes/Documentation/ARQUITETURA.md) para o planejamento completo.

## Comandos iniciais

```powershell
dotnet restore
dotnet build
dotnet test
dotnet run --project src/Lavedes
```
