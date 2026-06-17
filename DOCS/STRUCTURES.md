# Padrões de Layout e Estrutura (Apostila Digital)

Este documento define a estrutura obrigatória para as aulas e componentes deste projeto, garantindo consistência visual e funcional.

## 1. Estrutura de Pastas

Cada componente deve seguir esta hierarquia:

```text
src/componentes/[nome-do-componente]/
├── [nome-do-componente].json  # Metadados e títulos dos bimestres
├── index.njk                  # Dashboard do componente
├── bimestre-01/
│   ├── aula-01/
│   │   └── index.html         # Conteúdo da aula
...
```

## 2. Metadados da Aula (Front-matter)

Toda aula (`index.html`) deve conter obrigatoriamente:

```yaml
---
title: "Nome da Aula"             # NÃO incluir "Aula XX: " no título
componente: "Nome do Componente"  # Para ser utilizado no <title>
aula_numero: "XX"                 # Sempre dois dígitos, entre aspas
description: "Descrição"          # Obrigatório para o card do dashboard
tags:
  - aula
  - bimestre-XX
---
```

> **Nota:** O prefixo "Aula XX: " será adicionado automaticamente pelo layout nas páginas de conteúdo. No dashboard, aparecerá apenas o "Nome da Aula" com o número acima.

## 3. Estrutura HTML da Aula (Template Padrão)

Toda aula deve seguir esta sequência de seções para garantir a consistência pedagógica:

### 1. Teoria & Conceitos

Foco na explicação técnica e teórica.

```html
<section class="section-box">
  <h2>Teoria & Conceitos</h2>
  <p>Explicação do tema...</p>
</section>
```

### 2. Exemplo de Código

Demonstração prática da sintaxe ou lógica.

```html
<section class="section-box">
  <h2>Exemplo de Código</h2>
  <div class="code-container">
    <pre><code class="language-java">// Código aqui</code></pre>
  </div>
</section>
```

### 3. Representação Gráfica

Uso de diagramas Mermaid e desenhos para facilitar a visualização e entendimento dos alunos.

```html
<section class="section-box">
  <h2>Representação Gráfica</h2>
  <div class="mermaid">
    graph TD
    A --> B
  </div>
</section>
```

### 4. Dicas & Lembretes

Destaques importantes e "pulos do gato".

```html
<div class="tip-box">
  <h4>Dicas & Lembretes</h4>
  <ul>
    <li>Dica importante 1</li>
  </ul>
</div>
```

### 5. Como aplicar na Prática

Cenários de uso real e aplicações profissionais.

```html
<section class="section-box">
  <h2>Como aplicar na Prática</h2>
  <ul>
    <li>Aplicação A...</li>
  </ul>
</section>
```

### 6. Referências

Fontes de estudo e bibliografia.

```html
<section class="section-box">
  <h2>Referências</h2>
  <ul>
    <li>Link ou Livro...</li>
  </ul>
</section>
```

### 7. Para Praticar

Lista de links para os arquivos de exercícios da aula.

```html
<section class="section-box">
  <h2>Para Praticar</h2>
  <ul>
    <li><a href="#">Exercício 1</a></li>
  </ul>
</section>
```

## 4. Dashboard do Componente

O arquivo `index.njk` de cada componente deve ser simples:

```njk
---
layout: dashboard
title: "Nome do Componente - Apostila Digital"
nav_text: "DASHBOARD"
---
```

## 5. Arquivo de Dados do Componente

O arquivo `.json` deve definir o `subject` e os títulos dos bimestres para que o dashboard renderize corretamente:

```json
{
  "subject": "slug-do-componente",
  "subject_title": "Nome Completo",
  "subject_description": "Descrição longa...",
  "tags": ["aula"],
  "bimester_titles": {
    "bimestre-01": "Título do 1º Bimestre",
    ...
  }
}
```

## 6. Estrutura do Exercício Prático

Os arquivos de exercícios (`exercicio-01.html`) devem seguir uma estrutura modular para facilitar a leitura e execução das tarefas:

### Metadados (Front-matter)
```yaml
---
layout: exercicio
title: "Título do Exercício"
exercicio_numero: "01"
aula_numero: "XX"
description: "Breve resumo da atividade"
---
```

### Seções Obrigatórias

| Seção | Descrição |
| :--- | :--- |
| **Enunciado** | Descrição clara do problema ou objetivo final da atividade. |
| **Preparação** | Requisitos técnicos, configuração de ambiente ou arquivos necessários. |
| **Código Base** | Snippets de referência ou código inicial que o aluno deve utilizar. |
| **O Desafio** | Lista de tarefas específicas (Tarefa A, B, C...) a serem realizadas. |
| **Orientações Finais** | Dicas de depuração, links úteis e orientações de entrega/teste. |

### Exemplo de Código HTML
```html
<section class="section-box">
  <h2>Enunciado</h2>
  <p>Descrição...</p>
</section>

<section class="section-box">
  <h2>Preparação</h2>
  <ul>
    <li>Configuração 1...</li>
  </ul>
</section>

<section class="section-box">
  <h2>1. Código Base: [Nome do Arquivo]</h2>
  <div class="code-container">
    <pre><code class="language-php">...</code></pre>
  </div>
</section>

<section class="section-box">
  <h2>O Desafio (Atividades)</h2>
  <h4>Tarefa A: ...</h4>
  <ul>
    <li>Passo 1</li>
  </ul>
</section>

<div class="tip-box">
  <h4>Orientações Finais</h4>
  <ul>
    <li>Lembrete importante...</li>
  </ul>
</div>
```

## 6. Estrutura do Exercício Questionário

Os arquivos de exercícios (`exercicio-02.html`) devem seguir uma estrutura modular para facilitar a leitura e execução das tarefas:

### Metadados (Front-matter)
```yaml
---
layout: questionario
title: "Título Relacionado a Aula"
exercicio_numero: "02"
aula_numero: "XX"
description: "Breve resumo da atividade."
perguntas:
  - texto: "Enunciado"
    resposta_correta: "x"
    alternativas:
      - letra: "a"
        texto: "Alternativa 1"
      - letra: "b"
        texto: "Alternativa 2"
      - letra: "c"
        texto: "Alternativa 3"
      - letra: "d"
        texto: "Alternativa 4"
---
```
