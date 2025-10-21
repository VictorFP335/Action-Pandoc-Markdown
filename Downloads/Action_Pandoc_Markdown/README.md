# Workflow de Automação de Slides PDF

Este repositório demonstra um workflow do GitHub Actions que converte automaticamente arquivos Markdown em PDF de slides usando Pandoc.

## 📋 Funcionalidades

- **Conversão Automática**: Converte arquivos Markdown em PDF quando há push na pasta `docs/`
- **Configuração Flexível**: Usa arquivo YAML para configuração do Pandoc
- **Artefatos**: Gera PDFs como artefatos do GitHub Actions
- **Branch Dedicada**: Publica os PDFs na branch `slides-output`

## 🚀 Como Usar

### Estrutura dos Arquivos
docs/
├── presentation.md # Conteúdo dos slides em Markdown
└── pandoc.yaml # Configuração do Pandoc
.github/
└── workflows/
└── slides.yml # Workflow do GitHub Actions


### Fluxo do Workflow

1. **Trigger**: Push em arquivos Markdown na pasta `docs/`
2. **Setup**: Instala Pandoc e LaTeX no runner Ubuntu
3. **Conversão**: Converte Markdown para PDF usando Pandoc
4. **Publicação**: 
   - Upload do PDF como artefato
   - Push para branch `slides-output` (opcional)

### Acessando os PDFs

1. **Artefatos**: 
   - Vá para a aba "Actions"
   - Clique na execução mais recente
   - Baixe o artefato "slides-pdf"

2. **Branch `slides-output`**:
   - Acesse a branch `slides-output`
   - Os PDFs estarão disponíveis no root

## ⚙️ Configuração

### Arquivo Markdown

Use headers (`#`, `##`) para estruturar os slides. O nível 2 (`##`) inicia novos slides quando `slide-level: 2`.

### Personalização

Edite `docs/pandoc.yaml` para:
- Alterar o tema dos slides
- Modificar fontes e cores
- Ajustar layout e margens

## 🔧 Solução de Problemas

### Erros Comuns

1. **LaTeX não instalado**: O workflow instala automaticamente
2. **Encoding incorreto**: Use UTF-8 nos arquivos Markdown
3. **Arquivos ausentes**: Verifique os caminhos no workflow

### Logs e Debug

- Verifique a execução na aba "Actions"
- Examine os logs para mensagens de erro do Pandoc
- Valide a sintaxe Markdown localmente

## 📄 Licença

MIT License