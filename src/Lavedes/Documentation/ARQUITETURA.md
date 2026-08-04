# Documento técnico — Loja Lavedes

## 1. Objetivo

Criar uma loja responsiva de uniformes e vestuário com catálogo, galeria, pedidos, solicitações de personalização e painel administrativo protegido.

Nesta etapa foi criado somente o esqueleto compilável. Banco de dados, autenticação, telas comerciais e integrações serão implementados posteriormente.

## 2. Tecnologias

- C# com .NET 10 e ASP.NET Core;
- HTML/Razor (`.cshtml`);
- CSS responsivo;
- JavaScript modular;
- MySQL com `MySqlConnector` e SQL explícito;
- sem Entity Framework, Dapper ou outro ORM;
- autenticação por cookies do ASP.NET Core;
- hospedagem futura em Linux, preferencialmente com Docker.

## 3. Projetos da solução

### Lavedes

Projeto ASP.NET Core único. Reúne páginas públicas, painel administrativo, API, modelos, serviços, acesso ao MySQL e integrações. A estrutura simples facilita o desenvolvimento inicial e pode ser dividida futuramente se houver necessidade real.

### Lavedes.Tests

Projeto separado para testes unitários e de integração.

## 4. Organização interna

```text
Lavedes
├── Areas/Admin          painel administrativo
├── Authentication      login e permissões
├── Controllers/Api     endpoints HTTP
├── Database/Scripts    criação e evolução do MySQL
├── Documentation       documentos técnicos
├── Integrations        pagamento, frete e WhatsApp
├── Models              dados e regras da aplicação
├── Pages               páginas HTML/Razor públicas
├── Repositories        consultas SQL e persistência
├── Services            regras e fluxos de negócio
├── Storage             armazenamento de arquivos
└── wwwroot              CSS, JavaScript e imagens
```

## 5. Módulos previstos

- Catálogo: produtos, categorias, tamanhos, cores e variações;
- Estoque: saldo por variação e alertas;
- Clientes: cadastro, endereços e histórico;
- Pedidos: carrinho, checkout, pagamento, produção e entrega;
- Orçamentos: personalização e upload de logotipo ou arte;
- Galeria: álbuns, imagens, capas, legendas e ordenação;
- Administração: dashboard, cadastros, permissões e configurações;
- Integrações: pagamentos, frete, armazenamento e WhatsApp.

## 6. Segurança e operação

- cookies seguros e permissões administrativas;
- validação de tipo e tamanho de arquivos;
- logs de alterações importantes;
- segredos fora do repositório;
- backups automatizados;
- adequação à LGPD.

## 7. Próximas etapas

1. Definir identidade visual e regras comerciais.
2. Modelar entidades e relacionamentos do banco.
3. Configurar MySQL, `MySqlConnector`, repositórios e scripts SQL.
4. Criar catálogo e galeria pública.
5. Criar autenticação e painel administrativo.
6. Implementar orçamento, carrinho, checkout e pedidos.
7. Integrar imagens, pagamento, frete e WhatsApp.
8. Adicionar testes, Docker e publicação.

