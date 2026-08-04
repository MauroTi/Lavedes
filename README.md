# Lavedes

Base da loja virtual de uniformes e vestuário, organizada para ASP.NET Core, Razor Pages, JavaScript e MySQL.

## Estrutura

- `src/Lavedes.Domain`: entidades, regras e contratos centrais.
- `src/Lavedes.Application`: casos de uso, DTOs, validações e interfaces.
- `src/Lavedes.Infrastructure`: MySQL, arquivos, identidade e integrações externas.
- `src/Lavedes.Web`: loja pública, painel administrativo e API HTTP.
- `tests/Lavedes.Tests`: testes automatizados.
- `docs`: documentação técnica e decisões de arquitetura.

Consulte [docs/ARQUITETURA.md](docs/ARQUITETURA.md) para o planejamento completo.

## Comandos iniciais

```powershell
dotnet restore
dotnet build
dotnet test
dotnet run --project src/Lavedes.Web
```

