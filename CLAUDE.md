# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Mintlify-based documentation site for the Speedio API. The documentation covers two main API variants:
- **Main API**: General lead management and data enrichment
- **Partners API**: Exclusive advanced features for authorized partners

## Development Commands

### Local Development
```bash
# Install Mintlify CLI globally (one-time setup)
npm i -g mintlify

# Start development server
mintlify dev
# Documentation will be available at http://localhost:3000
```

### Environment Setup
```bash
# Set up environment variables for API testing
export SPEEDIO_USERNAME="your_username"
export SPEEDIO_PASSWORD="your_password"

# Test configuration
echo -n ${SPEEDIO_USERNAME}:${SPEEDIO_PASSWORD} | base64
```

## Architecture & Structure

### Documentation Organization
- **Portuguese Language**: All content is in Brazilian Portuguese
- **MDX Format**: Uses Mintlify's MDX format with frontmatter
- **Two-tier Navigation**: Main API and Partners API sections
- **Component-driven**: Uses Mintlify components (Card, CardGroup, CodeGroup, etc.)

### Key Configuration Files
- `mint.json`: Main Mintlify configuration, navigation structure, branding
- `README.md`: Project overview and development guide

### Content Categories
1. **Introdução/Getting Started** (`introducao.mdx`, `inicio-rapido.mdx`)
2. **Authentication** (`autenticacao/` folder)
3. **API Endpoints** (`endpoints/` and `api-reference/` folders)
4. **Partners API** (`parceiros/` folder) - Exclusive advanced features
5. **Guides** (`guias/` folder) - Best practices and tutorials

### API Base URLs
- Main API: `https://api-get-leads.speedio.com.br`
- Authentication: Basic Auth with Base64 encoding

### Security Implementation
- Environment variables for credentials (`SPEEDIO_USERNAME`, `SPEEDIO_PASSWORD`)
- No hardcoded credentials in examples
- Basic Auth pattern consistently used throughout documentation

## Content Guidelines

### Authentication Examples
Always use environment variables in code examples:
```bash
curl -H "Authorization: Basic $(echo -n ${SPEEDIO_USERNAME}:${SPEEDIO_PASSWORD} | base64)"
```

### Rate Limits
- Main API: 100 req/min, 1000 req/hour
- Partners: Tiered limits based on plan

### Mintlify Components Usage
- `<Card>` and `<CardGroup>` for feature highlights
- `<CodeGroup>` for multi-language examples
- `<Warning>` and `<Note>` for important information
- `<Steps>` for sequential processes

### Content Standards
- Business focus on B2B lead generation and CNPJ data
- Emphasize security best practices
- Include practical, working examples
- Maintain consistency between main and partners documentation