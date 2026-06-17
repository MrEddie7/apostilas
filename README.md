# Apostila Digital: Banco de Dados II

Este projeto é uma apostila digital interativa para a disciplina de **Banco de Dados II**. Ele foi desenvolvido utilizando o gerador de sites estáticos **Eleventy (11ty)** para garantir performance, facilidade de manutenção e uma experiência de leitura fluida para os alunos.

## Tecnologias Utilizadas

- **Eleventy (11ty)**: Gerador de sites estáticos robusto e flexível.
- **Nunjucks**: Motor de templates para reaproveitamento de código (layouts).
- **CSS Vanilla**: Estilização moderna e minimalista focada na legibilidade.
- **Mermaid.js**: Renderização de diagramas lógicos e físicos diretamente no navegador.
- **Highlight.js**: Realce de sintaxe para exemplos de código SQL, MySQL e PostgreSQL.

## Estrutura do Projeto

```text
├── _site/              # Site estático gerado (pronto para deploy)
├── src/                # Arquivos fonte
│   ├── _includes/      # Layouts e componentes reutilizáveis
│   ├── aulas/          # Conteúdo das aulas (organizado por bimestre)
│   ├── css/            # Estilos globais
│   ├── js/             # Lógica do lado do cliente (Mermaid, Highlight)
│   ├── imagens/        # Assets visuais e favicons
│   └── index.njk       # Template do Dashboard principal
├── .eleventy.js        # Configurações do compilador Eleventy
└── package.json        # Dependências e scripts do projeto
```

## Convenções de Numeração

### Aulas

As aulas são numeradas de forma **contínua** ao longo de todo o componente curricular, independente do bimestre:

- **1º Bimestre**: Aulas 01-10
- **2º Bimestre**: Aulas 11-20  
- **3º Bimestre**: Aulas 21-30
- **4º Bimestre**: Aulas 31-40

Esta convenção facilita a navegação sequencial e a referência cruzada entre conteúdos relacionados.

### Diretórios

Apesar da numeração contínua das aulas, os diretórios mantêm a organização por bimestre para facilitar a manutenção:

```text
componentes/[componente]/bimestre-XX/aula-XX/
```

## Como Executar o Projeto

### Pré-requisitos

- **Node.js** (versão 18 ou superior recomendada)
- **npm** (instalado automaticamente com o Node.js)

### Instalação

1. Clone o repositório ou baixe os arquivos.
2. No terminal, acesse a pasta do projeto e instale as dependências:

```bash
npm install
```

### Desenvolvimento

Para rodar o projeto localmente com recarregamento automático (Hot Reload):

```bash
npm start
```

O site estará disponível em `http://localhost:8080`.

### Build de Produção

Para gerar a versão final e otimizada do site:

```bash
npm run build
```

Os arquivos gerados estarão na pasta `_site/`.

## Como Hospedar no GitHub Pages

Este projeto já está configurado para deploy automático via **GitHub Actions**.

1. Suba o projeto para um repositório no GitHub.
2. No seu repositório, vá em **Settings** > **Pages**.
3. Em **Build and deployment** > **Source**, selecione **GitHub Actions**.
4. Sempre que você fizer um `push` para a branch `main`, o GitHub irá compilar o projeto e atualizar o site automaticamente.

### Importante: Path Prefix

Se o seu site não estiver na raiz do domínio (ex: `usuario.github.io/nome-do-repo/`), você deve configurar o prefixo no arquivo `.eleventy.js`:

```javascript
return {
  pathPrefix: "/nome-do-repo/",
  dir: { ... }
};
```

## Como Adicionar Conteúdo

As aulas são gerenciadas através de arquivos HTML ou Markdown dentro da pasta `src/aulas/`. Cada nova aula deve conter metadados no topo (Front Matter) para ser indexada corretamente no Dashboard:

```markdown
---
title: "Título da Aula"
componente: "Nome do Componente"
aula_numero: "XX"
description: "Breve descrição do conteúdo"
tags:
  - aula
  - bimestre-0X
---
```

## Licença

Este material foi desenvolvido para fins educacionais.
Copyright © 2026 - Professor Salomão.
