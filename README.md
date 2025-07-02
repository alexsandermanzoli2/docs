# Documentação da API Speedio

Este repositório contém a documentação completa para a API Speedio, construída com [Mintlify](https://mintlify.com).

## 🚀 Desenvolvimento

### Pré-requisitos

- Node.js 18+
- npm ou yarn

### Instalação

1. Instale o Mintlify CLI globalmente:
```bash
npm i -g mintlify
```

2. Execute o servidor de desenvolvimento:
```bash
mintlify dev
```

A documentação estará disponível em `http://localhost:3000`.

## 📁 Estrutura do Projeto

```
speedio-api-docs/
├── mint.json              # Configuração do Mintlify
├── introducao.mdx         # Página inicial
├── inicio-rapido.mdx      # Guia de início rápido
├── desenvolvimento.mdx    # Guia de desenvolvimento
├── essenciais/           # Conceitos essenciais
│   ├── autenticacao.mdx
│   ├── erros.mdx
│   ├── webhooks.mdx
│   └── limites-de-taxa.mdx
├── api-reference/        # Referência da API principal
│   ├── introducao.mdx
│   └── endpoint/
│       ├── listar-leads.mdx
│       ├── criar-lead.mdx
│       ├── atualizar-lead.mdx
│       └── deletar-lead.mdx
├── parceiros/           # API exclusiva para parceiros
│   ├── introducao.mdx
│   ├── autenticacao.mdx
│   ├── buscar-por-cnpj.mdx
│   ├── buscar-leads.mdx
│   ├── enriquecimento.mdx
│   └── validacao.mdx
├── logo/                # Arquivos de logo
└── images/             # Imagens da documentação
```

## 📚 Conteúdo da Documentação

### API Principal
- **Autenticação**: Sistema de chaves de API
- **Gerenciamento de Leads**: CRUD completo
- **Webhooks**: Notificações em tempo real
- **Rate Limits**: Controle de taxa de requisições

### API Parceiros
- **Configuração Segura**: Guia completo para variáveis de ambiente
- **Autenticação Basic Auth**: Sistema seguro sem credenciais expostas
- **Busca por CNPJ**: Endpoint exclusivo para busca detalhada por CNPJ
- **Busca de Leads**: Filtros avançados para prospecção
- **Enriquecimento**: Dados adicionais de empresas e contatos
- **Validação**: Verificação de e-mails, telefones e CNPJs

## 🎨 Personalização

### Adicionar Páginas

1. Crie um novo arquivo `.mdx`
2. Adicione frontmatter com título e descrição
3. Atualize a `navigation` no `mint.json`

### Atualizar Branding

Edite `mint.json` para customizar:
- Cores da marca
- Logo da empresa
- Navegação
- Links do footer

## 📝 Diretrizes de Escrita

- Use linguagem clara e concisa
- Inclua exemplos de código em múltiplas linguagens
- Forneça casos de uso do mundo real
- Mantenha os exemplos atualizados

## 🚀 Deploy

O Mintlify faz deploy automaticamente da documentação quando você faz push para o repositório.

## 📧 Suporte

Para dúvidas sobre a documentação da API:
- E-mail: suporte@speedio.com.br
- Problemas na documentação: [Criar issue](https://github.com/speedio/api-docs/issues)

## 🔒 Segurança

### Práticas Implementadas

- **Variáveis de Ambiente**: Todas as credenciais são configuradas via variáveis de ambiente
- **Sem Hardcode**: Nenhuma credencial real nos exemplos de código
- **Basic Auth Seguro**: Implementação correta de Basic Authentication
- **Guias de Configuração**: Instruções detalhadas para diferentes ambientes

### Configuração Rápida

```bash
# Configure suas credenciais de parceiro
export SPEEDIO_USERNAME="seu_usuario_parceiro"
export SPEEDIO_PASSWORD="sua_senha_fornecida"

# Teste a configuração
echo -n ${SPEEDIO_USERNAME}:${SPEEDIO_PASSWORD} | base64
```

### ⚠️ Importante

- **NUNCA** commite credenciais no Git
- **SEMPRE** use `.env` no `.gitignore`
- **ROTACIONE** credenciais regularmente
- **MONITORE** o uso da API

## 📄 Licença

Copyright © 2024 Speedio. Todos os direitos reservados.