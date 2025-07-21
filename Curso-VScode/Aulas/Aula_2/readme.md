# 🔌 Aula 2 – Extensões Essenciais para VS Code

## 📦 Como instalar e gerenciar extensões

### Acessando o marketplace de extensões
- **Atalho**: `Ctrl + Shift + X` (Windows/Linux) ou `Cmd + Shift + X` (macOS)
- **Interface**: Ícone de extensões na sidebar esquerda
- **Busca**: Digite o nome da extensão na barra de pesquisa

### Tipos de extensões
1. **Extensões de linguagem** - Suporte para linguagens específicas
2. **Extensões de formatação** - Formatadores de código
3. **Extensões de debug** - Ferramentas de depuração
4. **Extensões de produtividade** - Melhorias na interface
5. **Extensões de tema** - Personalização visual

### Gerenciando extensões
- **Instalar**: Clique em "Install"
- **Desinstalar**: Clique em "Uninstall"
- **Atualizar**: Clique em "Update" quando disponível
- **Desabilitar**: Clique em "Disable" para desativar temporariamente

## 🛠️ Extensões essenciais por categoria

### 📝 **Formatação e Qualidade de Código**

| Extensão | Descrição | Configuração Recomendada |
|----------|-----------|--------------------------|
| **Prettier - Code formatter** | Formata código automaticamente | `"editor.formatOnSave": true` |
| **ESLint** | Identifica problemas no JavaScript/TypeScript | `"eslint.autoFixOnSave": true` |
| **Beautify** | Formata HTML, CSS, JS | Alternativa ao Prettier |
| **EditorConfig** | Padrões de codificação consistentes | Cria arquivo `.editorconfig` |

### 🎨 **Visual e Interface**

| Extensão | Descrição | Benefício |
|----------|-----------|-----------|
| **vscode-icons** | Ícones para arquivos e pastas | Melhor organização visual |
| **Material Icon Theme** | Ícones Material Design | Interface mais moderna |
| **Bracket Pair Colorizer 2** | Colorização de parênteses | Facilita leitura do código |
| **Indent Rainbow** | Colorização de indentação | Melhor visualização da estrutura |
| **Highlight Matching Tag** | Destaca tags HTML correspondentes | Navegação mais fácil |

### 🚀 **Desenvolvimento Web**

| Extensão | Descrição | Como usar |
|----------|-----------|-----------|
| **Live Server** | Servidor local com reload automático | Clique direito → "Open with Live Server" |
| **Auto Rename Tag** | Renomeia tags HTML/JSX automaticamente | Funciona automaticamente |
| **HTML CSS Support** | IntelliSense para HTML/CSS | Autocompletar melhorado |
| **CSS Peek** | Navega para definições CSS | Ctrl + clique em classes |
| **IntelliSense for CSS** | Autocompletar CSS avançado | Sugestões inteligentes |

### 🔧 **Produtividade e Git**

| Extensão | Descrição | Funcionalidades |
|----------|-----------|----------------|
| **GitLens** | Git integrado avançado | Histórico, blame, comparação |
| **Git Graph** | Visualização gráfica do Git | Timeline de commits |
| **Git History** | Histórico de mudanças | Comparação de versões |
| **Path Intellisense** | Autocompletar caminhos | Ctrl + Space em imports |
| **Auto Close Tag** | Fecha tags automaticamente | Economiza tempo |

### 🐛 **Debugging e Desenvolvimento**

| Extensão | Descrição | Linguagens |
|----------|-----------|------------|
| **Debugger for Chrome** | Debug JavaScript no Chrome | JavaScript/TypeScript |
| **Python** | Suporte completo para Python | Python |
| **C/C++** | Suporte para C/C++ | C, C++ |
| **Java Extension Pack** | Suporte para Java | Java |
| **PHP Debug** | Debug PHP | PHP |

## 🔧 Configurações específicas por extensão

### Prettier
```json
{
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.formatOnSave": true,
  "prettier.singleQuote": true,
  "prettier.tabWidth": 2,
  "prettier.semi": true
}
```

### ESLint
```json
{
  "eslint.autoFixOnSave": true,
  "eslint.validate": [
    "javascript",
    "javascriptreact",
    "typescript",
    "typescriptreact"
  ]
}
```

### Live Server
```json
{
  "liveServer.settings.port": 5500,
  "liveServer.settings.root": "/",
  "liveServer.settings.CustomBrowser": "chrome"
}
```

### GitLens
```json
{
  "gitlens.codeLens.enabled": true,
  "gitlens.hovers.enabled": true,
  "gitlens.blame.format": "${author}, ${agoOrDate}"
}
```

## 🎯 Extensões por tipo de projeto

### 🌐 **Desenvolvimento Frontend**
- **Live Server** - Servidor local
- **Auto Rename Tag** - HTML/JSX
- **CSS Peek** - Navegação CSS
- **JavaScript (ES6) code snippets** - Snippets JS
- **ES7+ React/Redux/React-Native snippets** - React

### 🐍 **Desenvolvimento Python**
- **Python** - Suporte completo
- **Pylance** - IntelliSense avançado
- **Python Docstring Generator** - Documentação
- **Python Test Explorer** - Testes

### ☕ **Desenvolvimento Java**
- **Extension Pack for Java** - Suporte completo
- **Spring Boot Extension Pack** - Spring Boot
- **Maven for Java** - Gerenciamento Maven

### 🐘 **Desenvolvimento PHP**
- **PHP Intelephense** - IntelliSense
- **PHP Debug** - Debugging
- **PHP Namespace Resolver** - Imports automáticos

### 🗄️ **Desenvolvimento Backend**
- **REST Client** - Testar APIs
- **Thunder Client** - Cliente HTTP
- **Docker** - Integração Docker
- **Remote - SSH** - Desenvolvimento remoto

## 🔍 Extensões avançadas e especializadas

### 📊 **Análise e Qualidade**
- **SonarLint** - Análise de qualidade de código
- **CodeMetrics** - Métricas de complexidade
- **Import Cost** - Tamanho dos imports

### 🎨 **Temas e Personalização**
- **One Dark Pro** - Tema escuro popular
- **Dracula Official** - Tema Dracula
- **Night Owl** - Tema para desenvolvimento noturno
- **Winter is Coming** - Tema com variações

### 🚀 **Produtividade Avançada**
- **Settings Sync** - Sincronização via GitHub
- **Project Manager** - Gerenciar múltiplos projetos
- **Bookmarks** - Marcar linhas importantes
- **Todo Tree** - Gerenciar TODOs no código

## 🧪 Desafio Aula 2

### Exercícios práticos:

1. **Instalação de extensões básicas**:
   ```bash
   # Instale estas extensões essenciais:
   - Prettier - Code formatter
   - vscode-icons
   - Auto Rename Tag
   - Live Server
   - GitLens
   ```

2. **Configuração do Prettier**:
   - Crie um arquivo `.prettierrc` na raiz do projeto
   - Configure as regras de formatação
   - Teste a formatação automática

3. **Projeto de teste com Live Server**:
   ```html
   <!-- Crie um arquivo index.html -->
   <!DOCTYPE html>
   <html>
   <head>
       <title>Teste Live Server</title>
   </head>
   <body>
       <h1>Olá, Live Server!</h1>
       <p>Edite este arquivo e veja o reload automático.</p>
   </body>
   </html>
   ```

4. **Explorando GitLens**:
   - Abra um projeto com Git
   - Hover sobre linhas para ver histórico
   - Use o blame view
   - Explore o Git Graph

5. **Configuração de tema e ícones**:
   - Instale um tema de sua preferência
   - Configure os ícones de arquivos
   - Personalize as cores do editor

6. **Extensões específicas por linguagem**:
   - Instale extensões para sua linguagem principal
   - Configure o IntelliSense
   - Teste o debugging

### Exercícios avançados:

7. **Configuração de ESLint**:
   ```json
   // .eslintrc.json
   {
     "extends": ["eslint:recommended"],
     "env": {
       "browser": true,
       "es6": true
     }
   }
   ```

8. **Projeto com múltiplas extensões**:
   - Crie um projeto web simples
   - Configure Prettier + ESLint
   - Use Live Server para desenvolvimento
   - Implemente Git com GitLens

### Checklist de conclusão:
- [ ] 5 extensões essenciais instaladas
- [ ] Prettier configurado e funcionando
- [ ] Live Server testado com reload automático
- [ ] GitLens explorado
- [ ] Tema e ícones personalizados
- [ ] Extensões específicas para sua linguagem
- [ ] Configurações de formatação aplicadas

### Dicas importantes:
- **Performance**: Não instale muitas extensões desnecessárias
- **Conflitos**: Algumas extensões podem conflitar (ex: Prettier vs Beautify)
- **Atualizações**: Mantenha as extensões atualizadas
- **Backup**: Use Settings Sync para backup das configurações

### Próximos passos:
Na próxima aula, aprenderemos sobre:
- Organização de projetos e workspace
- Configurações específicas por projeto
- Snippets e automação
- Debugging avançado

