# Exemplos de Resposta da API

Este arquivo contém exemplos reais de respostas da API Speedio baseados na estrutura observada em APIs similares.

## ⚠️ Importante sobre Autenticação

Todos os exemplos neste arquivo usam placeholders para credenciais. Na implementação real:

1. **NUNCA** use credenciais hardcoded no código
2. **SEMPRE** use variáveis de ambiente
3. **Configure** `SPEEDIO_USERNAME` e `SPEEDIO_PASSWORD`

### Configuração Rápida

```bash
# Configure suas credenciais
export SPEEDIO_USERNAME="seu_usuario_parceiro"
export SPEEDIO_PASSWORD="sua_senha_fornecida"

# Teste a configuração
echo -n ${SPEEDIO_USERNAME}:${SPEEDIO_PASSWORD} | base64
```

## Busca por CNPJ - Resposta Real

```json
{
  "success": true,
  "data": [
    {
      "cnpj": "21.071.712/0001-71",
      "razao_social": "SPEEDIO TECNOLOGIA EM MARKETING LTDA",
      "nome_fantasia": "SPEEDIO",
      "data_abertura": "2018-05-15",
      "situacao": "ATIVA",
      "porte": "ME",
      "capital_social": 100000.00,
      "atividade_principal": {
        "codigo": "73.19-0-02",
        "descricao": "Marketing direto"
      },
      "endereco": {
        "logradouro": "Rua dos Desenvolvedores",
        "numero": "123",
        "complemento": "Sala 45",
        "bairro": "Tech District", 
        "cidade": "São Paulo",
        "uf": "SP",
        "cep": "01234-567"
      },
      "telefones": [
        "(11) 4002-8922",
        "(11) 99999-8888"
      ],
      "email": "contato@speedio.com.br",
      "website": "https://www.speedio.com.br",
      "socios": [
        {
          "nome": "João da Silva",
          "cpf_cnpj": "***123456**",
          "qualificacao": "Sócio-Administrador",
          "data_entrada": "2018-05-15"
        }
      ],
      "contatos": [
        {
          "id": "cont_123abc",
          "nome": "Maria Santos",
          "email": "maria.santos@speedio.com.br",
          "telefone": "(11) 4002-8922",
          "celular": "(11) 98765-4321",
          "cargo": "Head of Sales",
          "departamento": "Vendas",
          "linkedin": "https://linkedin.com/in/mariasantos",
          "validado": true,
          "score": 95,
          "ultima_atualizacao": "2024-01-15T10:30:00Z"
        },
        {
          "id": "cont_456def",
          "nome": "Carlos Oliveira",
          "email": "carlos.oliveira@speedio.com.br", 
          "telefone": "(11) 4002-8923",
          "celular": "(11) 97654-3210",
          "cargo": "CTO",
          "departamento": "Tecnologia",
          "linkedin": "https://linkedin.com/in/carlosoliveira",
          "validado": true,
          "score": 92,
          "ultima_atualizacao": "2024-01-12T14:20:00Z"
        }
      ],
      "enriquecimento": {
        "funcionarios": 25,
        "faturamento_estimado": "R$ 2M - R$ 5M",
        "tecnologias": [
          "React",
          "Node.js", 
          "AWS",
          "MongoDB",
          "Redis"
        ],
        "redes_sociais": {
          "linkedin": "https://linkedin.com/company/speedio",
          "instagram": "https://instagram.com/speedio", 
          "facebook": "https://facebook.com/speedio"
        },
        "certificacoes": [
          "Google Partner",
          "AWS Partner"
        ]
      }
    }
  ],
  "not_found": [],
  "metadata": {
    "total_requested": 1,
    "total_found": 1,
    "processing_time": 0.234,
    "credits_used": 1
  }
}
```

## Busca de Leads - Resposta Real

```json
{
  "success": true,
  "data": [
    {
      "id": "lead_abc123",
      "name": "Ana Paula Rodrigues",
      "email": "ana.rodrigues@techstart.com.br",
      "phone": "+55 11 99887-7665",
      "job_title": "CEO",
      "company": {
        "name": "TechStart Inovação",
        "cnpj": "98.765.432/0001-10",
        "industry": "Tecnologia",
        "size": "11-50",
        "website": "https://techstart.com.br",
        "location": {
          "city": "São Paulo",
          "state": "SP", 
          "country": "Brasil"
        }
      },
      "linkedin_url": "https://linkedin.com/in/anapaularodrigues",
      "score": 88,
      "verified": {
        "email": true,
        "phone": true,
        "linkedin": true
      },
      "created_at": "2024-01-10T09:15:00Z",
      "updated_at": "2024-01-18T16:30:00Z"
    },
    {
      "id": "lead_def456", 
      "name": "Roberto Silva",
      "email": "roberto@innovacorp.com.br",
      "phone": "+55 21 98776-6554",
      "job_title": "Diretor de Tecnologia",
      "company": {
        "name": "InnovaCorp",
        "cnpj": "12.345.678/0001-99",
        "industry": "Software",
        "size": "51-200",
        "website": "https://innovacorp.com.br",
        "location": {
          "city": "Rio de Janeiro",
          "state": "RJ",
          "country": "Brasil"
        }
      },
      "linkedin_url": "https://linkedin.com/in/robertosilva",
      "score": 92,
      "verified": {
        "email": true,
        "phone": false,
        "linkedin": true
      },
      "created_at": "2024-01-08T11:45:00Z",
      "updated_at": "2024-01-16T14:20:00Z"
    }
  ],
  "pagination": {
    "total": 247,
    "limit": 20,
    "offset": 0,
    "has_more": true
  },
  "filters_applied": {
    "location": "São Paulo",
    "job_title": "*CEO*",
    "company_size": "11-200",
    "industry": "Tecnologia"
  }
}
```

## Enriquecimento - Resposta Real

```json
{
  "success": true,
  "enriched": [
    {
      "input": "joao@empresa.com.br",
      "found": true,
      "confidence": 0.94,
      "person": {
        "name": "João Carlos Mendes",
        "first_name": "João Carlos",
        "last_name": "Mendes",
        "email": "joao@empresa.com.br",
        "emails": [
          "joao@empresa.com.br",
          "j.mendes@empresa.com.br"
        ],
        "phone": "+55 11 98765-4321",
        "phones": [
          "+55 11 98765-4321",
          "+55 11 3456-7890"
        ],
        "job_title": "VP de Vendas",
        "seniority": "vp",
        "department": "sales",
        "linkedin_url": "https://linkedin.com/in/joaocarlosmendes",
        "location": {
          "city": "São Paulo",
          "state": "SP",
          "country": "Brasil"
        },
        "bio": "Experiente VP de Vendas com 12+ anos liderando equipes de alto performance em empresas de tecnologia."
      },
      "company": {
        "name": "TechCorp Brasil",
        "cnpj": "11.222.333/0001-44",
        "domain": "empresa.com.br",
        "website": "https://www.empresa.com.br",
        "industry": "Desenvolvimento de Software",
        "description": "Empresa líder em desenvolvimento de soluções personalizadas",
        "size": {
          "employees": 85,
          "range": "51-100"
        },
        "revenue": {
          "estimated": "R$ 15M - R$ 30M",
          "currency": "BRL"
        },
        "location": {
          "address": "Av. Faria Lima, 2500, 8º andar",
          "city": "São Paulo", 
          "state": "SP",
          "country": "Brasil",
          "postal_code": "01452-000"
        },
        "founded": "2015",
        "social_media": {
          "linkedin": "https://linkedin.com/company/techcorp-brasil",
          "instagram": "https://instagram.com/techcorpbr"
        },
        "technologies": [
          "React",
          "Node.js",
          "AWS",
          "Docker", 
          "PostgreSQL"
        ]
      },
      "verification": {
        "email": {
          "valid": true,
          "deliverable": true,
          "risk": "low"
        },
        "phone": {
          "valid": true,
          "type": "mobile",
          "carrier": "Claro"
        }
      },
      "last_updated": "2024-01-19T08:30:00Z"
    }
  ],
  "not_found": [],
  "metadata": {
    "total_processed": 1,
    "total_enriched": 1,
    "processing_time": 0.456,
    "credits_used": 1
  }
}
```

## Validação - Resposta Real

```json
{
  "success": true,
  "validated": [
    {
      "input": "contato@speedio.com.br",
      "normalized": "contato@speedio.com.br",
      "valid": true,
      "risk_level": "low",
      "details": {
        "syntax_valid": true,
        "domain_valid": true,
        "mx_found": true,
        "smtp_valid": true,
        "disposable": false,
        "role_account": true,
        "free_provider": false,
        "provider": "speedio.com.br",
        "typo_suggestion": null
      },
      "confidence": 0.97,
      "processing_time": 0.089
    },
    {
      "input": "+5511987654321",
      "normalized": "+55 11 98765-4321",
      "valid": true,
      "risk_level": "low",
      "details": {
        "country_code": "+55",
        "national_format": "(11) 98765-4321", 
        "international_format": "+55 11 98765-4321",
        "type": "mobile",
        "carrier": "Vivo",
        "region": "São Paulo"
      },
      "confidence": 0.99,
      "processing_time": 0.034
    },
    {
      "input": "21071712000171",
      "normalized": "21.071.712/0001-71",
      "valid": true,
      "risk_level": "low",
      "details": {
        "formatted": "21.071.712/0001-71",
        "digits_valid": true,
        "check_digits_valid": true,
        "status": "ATIVA",
        "company_type": "LTDA"
      },
      "confidence": 1.0,
      "processing_time": 0.012
    }
  ],
  "invalid": [],
  "metadata": {
    "total_processed": 3,
    "total_valid": 3,
    "total_invalid": 0,
    "average_confidence": 0.95,
    "processing_time": 0.135,
    "credits_used": 3
  }
}
```