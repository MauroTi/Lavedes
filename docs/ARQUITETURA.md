# Documento técnico — Loja Lavedes

## 1. Objetivo

Criar uma loja responsiva de uniformes e vestuário com catálogo, galeria de trabalhos, pedidos, solicitações de personalização e painel administrativo protegido.

Nesta etapa foi criado somente o esqueleto compilável da solução. Banco de dados, autenticação, telas comerciais e integrações serão implementados nas próximas etapas.

## 2. Tecnologias definidas

- C# com .NET 10 e ASP.NET Core;
- HTML/Razor (`.cshtml`) para as páginas públicas, favorecendo SEO;
- CSS responsivo;
- JavaScript modular para as interações no navegador;
- endpoints Web API para o painel e futuras integrações;
- MySQL acessado com `MySqlConnector` e SQL explícito;
- sem Entity Framework, Dapper ou outro ORM;
- autenticação por cookies do ASP.NET Core com usuários e permissões persistidos por repositórios próprios;
- armazenamento externo de imagens em produção;
- implantação futura em Linux, preferencialmente com Docker.

## 3. Projetos da solução

### Lavedes.Domain

Núcleo sem dependências de infraestrutura. Conterá entidades, objetos de valor, enums, eventos e regras de negócio de catálogo, estoque, clientes, pedidos, orçamentos e galeria.

### Lavedes.Application

Orquestra os casos de uso. Conterá DTOs, comandos, consultas, validadores e interfaces para persistência e serviços externos.

### Lavedes.Infrastructure

Implementará persistência MySQL sem ORM, repositórios SQL, autenticação, armazenamento de imagens, pagamento, frete, WhatsApp e envio de mensagens.

### Lavedes.Web

Ponto de entrada ASP.NET Core. Conterá Razor Pages da loja pública, área administrativa, controllers da API e arquivos CSS/JavaScript.

### Lavedes.Tests

Concentrará testes unitários e, futuramente, testes de integração da API e da persistência.

## 4. Dependências

```text
Web -> Application + Infrastructure
Infrastructure -> Application + Domain
Application -> Domain
Domain -> nenhuma camada interna
Tests -> Domain + Application + Infrastructure
```

O projeto Domain não deve depender de banco, framework web ou integrações externas.

## 5. Módulos previstos

- Catálogo: produtos, categorias, tamanhos, cores e variações;
- Estoque: saldo por variação e alertas de estoque baixo;
- Clientes: cadastro, endereços e histórico;
- Pedidos: carrinho, checkout, pagamento, produção e entrega;
- Orçamentos: personalização e upload de logotipo/arte;
- Galeria: álbuns, imagens, capas, legendas e ordenação;
- Administração: dashboard, cadastros, permissões e configurações;
- Integrações: pagamentos, frete, armazenamento e WhatsApp.

## 6. Status de pedidos

`AguardandoPagamento`, `Pago`, `EmSeparacao`, `EmPersonalizacao`, `ProntoParaEnvio`, `Enviado`, `Concluido` e `Cancelado`.

## 7. Segurança e operação

- cookies seguros ou JWT conforme o consumidor;
- perfis e permissões administrativas;
- validação de tipo e tamanho de arquivos;
- logs de alterações importantes;
- segredos fora do repositório;
- backups automatizados;
- política de privacidade, cookies e adequação à LGPD.

## 8. Próximas etapas sugeridas

1. Definir identidade visual, categorias e regras comerciais.
2. Modelar entidades e relacionamentos do banco.
3. Configurar MySQL, `MySqlConnector`, repositórios e scripts SQL versionados.
4. Criar catálogo e galeria pública.
5. Criar autenticação e painel administrativo.
6. Implementar orçamento, carrinho, checkout e pedidos.
7. Integrar imagens, pagamento, frete e WhatsApp.
8. Adicionar testes, Docker, observabilidade e publicação.
