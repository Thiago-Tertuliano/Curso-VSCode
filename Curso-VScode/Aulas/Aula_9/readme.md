# 🎨 Aula 9 – Customizando interface e produtividade

## 🖌️ Temas e personalização visual

### **Temas populares e suas características:**

#### **Temas Escuros:**
- **One Dark Pro**: Baseado no Atom, cores suaves e contrastes equilibrados
- **Dracula Official**: Tema roxo/azul escuro, muito popular
- **Night Owl**: Otimizado para desenvolvimento noturno
- **Monokai Pro**: Cores vibrantes e contrastes fortes
- **Winter is Coming**: Variações de azul, tema elegante

#### **Temas Claros:**
- **Light+ (default light)**: Tema claro padrão do VS Code
- **Solarized Light**: Cores suaves e agradáveis aos olhos
- **GitHub Light**: Baseado no tema do GitHub
- **Quiet Light**: Tema minimalista e limpo

#### **Temas Especiais:**
- **Material Theme**: Baseado no Material Design
- **Ayu**: Múltiplas variações (dark, light, mirage)
- **Tokyo Night**: Tema japonês com cores únicas
- **Palenight Theme**: Tema roxo elegante

### **Instalando e aplicando temas:**
1. `Ctrl/Cmd + Shift + X` → Marketplace
2. Busque por "theme"
3. Instale o tema desejado
4. `Ctrl/Cmd + K Ctrl/Cmd + T` → Selecione o tema

### **Configurando temas via JSON:**
```json
{
  "workbench.colorTheme": "One Dark Pro",
  "workbench.iconTheme": "vscode-icons",
  "workbench.productIconTheme": "Default",
  "workbench.preferredDarkColorTheme": "One Dark Pro",
  "workbench.preferredLightColorTheme": "Light+ (default light)"
}
```

## 🎨 Ícones e organização visual

### **Extensões de ícones populares:**

#### **vscode-icons:**
- Ícones coloridos e organizados
- Suporte para muitas linguagens
- Configuração automática

#### **Material Icon Theme:**
- Baseado no Material Design
- Ícones consistentes
- Múltiplas variações

#### **Seti Icons:**
- Ícones minimalistas
- Design limpo e simples
- Boa para temas escuros

#### **A File Icon:**
- Ícones simples e claros
- Fácil identificação de arquivos
- Performance otimizada

### **Configurando ícones:**
```json
{
  "workbench.iconTheme": "vscode-icons",
  "vscode-icons.dontShowNewVersionMessage": true,
  "vscode-icons.associations.files": [
    { "icon": "js", "extensions": ["js", "jsx"] },
    { "icon": "ts", "extensions": ["ts", "tsx"] },
    { "icon": "react", "extensions": ["jsx", "tsx"] }
  ],
  "vscode-icons.associations.folders": [
    { "icon": "src", "folderNames": ["source", "src"] },
    { "icon": "dist", "folderNames": ["dist", "build"] }
  ]
}
```

## ⚡ Extensões para produtividade

### **Extensões essenciais:**

#### **GitLens - Git supercharged:**
- **Funcionalidades**: Histórico detalhado, blame, comparação
- **Configuração**:
```json
{
  "gitlens.codeLens.enabled": true,
  "gitlens.hovers.enabled": true,
  "gitlens.blame.format": "${author}, ${agoOrDate}",
  "gitlens.views.repositories.files.layout": "tree",
  "gitlens.views.fileHistory.files.layout": "tree"
}
```

#### **Todo Tree:**
- **Funcionalidades**: Gerenciar TODOs, FIXMEs, BUGs
- **Configuração**:
```json
{
  "todo-tree.general.tags": [
    "BUG",
    "HACK",
    "FIXME",
    "TODO",
    "XXX",
    "[ ]",
    "[x]"
  ],
  "todo-tree.highlights.customHighlight": {
    "TODO": {
      "icon": "check",
      "foreground": "#fff",
      "background": "#ffbd2a",
      "iconColour": "#ffbd2a"
    },
    "FIXME": {
      "icon": "alert",
      "foreground": "#fff",
      "background": "#f06292",
      "iconColour": "#f06292"
    }
  }
}
```

#### **Project Manager:**
- **Funcionalidades**: Gerenciar múltiplos projetos
- **Como usar**: `Ctrl/Cmd + Shift + P` → "Project Manager: List Projects"

#### **Code Spell Checker:**
- **Funcionalidades**: Verificar ortografia no código
- **Configuração**:
```json
{
  "cSpell.enabled": true,
  "cSpell.language": "en,pt",
  "cSpell.words": [
    "npm",
    "jsx",
    "tsx",
    "webpack"
  ]
}
```

#### **Peacock:**
- **Funcionalidades**: Mudar cor da barra do VS Code
- **Como usar**: `Ctrl/Cmd + Shift + P` → "Peacock: Change to a favorite color"

### **Extensões avançadas de produtividade:**

#### **Bookmarks:**
- Marcar linhas importantes
- Navegação rápida
- Configuração:
```json
{
  "bookmarks.saveBookmarksInProject": true,
  "bookmarks.useBreadcrumbs": true
}
```

#### **Bracket Pair Colorizer 2:**
- Colorização de parênteses
- Facilita navegação no código

#### **Indent Rainbow:**
- Colorização de indentação
- Melhor visualização da estrutura

#### **Error Lens:**
- Mostra erros inline
- Configuração:
```json
{
  "errorLens.enabled": true,
  "errorLens.messageEnabled": true,
  "errorLens.statusBarMessageEnabled": true
}
```

## 🛠️ Customizações avançadas de interface

### **Layout e organização:**

#### **Configurações de layout:**
```json
{
  "workbench.sideBar.location": "left",
  "workbench.panel.defaultLocation": "bottom",
  "workbench.editor.enablePreview": false,
  "workbench.editor.enablePreviewFromQuickOpen": false,
  "workbench.editor.showTabs": "multiple",
  "workbench.editor.tabSizing": "shrink",
  "workbench.editor.decorations.badges": true,
  "workbench.editor.decorations.colors": true
}
```

#### **Configurações de editor:**
```json
{
  "editor.minimap.enabled": true,
  "editor.minimap.renderCharacters": false,
  "editor.minimap.maxColumn": 120,
  "editor.bracketPairColorization.enabled": true,
  "editor.guides.bracketPairs": true,
  "editor.guides.bracketPairsHorizontal": true,
  "editor.guides.highlightActiveBracketPair": true,
  "editor.guides.highlightActiveIndentation": true,
  "editor.renderWhitespace": "boundary",
  "editor.renderControlCharacters": true,
  "editor.renderLineHighlight": "line",
  "editor.cursorBlinking": "smooth",
  "editor.cursorSmoothCaretAnimation": "on"
}
```

### **Modos especiais:**

#### **Zen Mode:**
- **Atalho**: `Ctrl/Cmd + K Z`
- **Funcionalidade**: Foco total no código
- **Configuração**:
```json
{
  "zenMode.fullScreen": false,
  "zenMode.hideLineNumbers": false,
  "zenMode.hideTabs": false,
  "zenMode.hideStatusBar": false,
  "zenMode.hideActivityBar": false
}
```

#### **Centered Layout:**
- **Atalho**: `Ctrl/Cmd + Shift + P` → "View: Toggle Centered Layout"
- **Funcionalidade**: Centraliza o editor

#### **Distraction Free Mode:**
- **Configuração**:
```json
{
  "workbench.activityBar.visible": false,
  "workbench.statusBar.visible": false,
  "workbench.sideBar.visible": false,
  "editor.minimap.enabled": false
}
```

## 🎯 Configurações específicas por área de desenvolvimento

### **Desenvolvimento Web:**
```json
{
  "workbench.colorTheme": "One Dark Pro",
  "workbench.iconTheme": "vscode-icons",
  "editor.fontFamily": "'Fira Code'",
  "editor.fontLigatures": true,
  "editor.tabSize": 2,
  "editor.formatOnSave": true,
  "emmet.includeLanguages": {
    "javascript": "javascriptreact"
  }
}
```

### **Desenvolvimento Python:**
```json
{
  "workbench.colorTheme": "Dracula Official",
  "workbench.iconTheme": "vscode-icons",
  "editor.fontFamily": "'JetBrains Mono'",
  "editor.tabSize": 4,
  "python.defaultInterpreterPath": "./venv/bin/python",
  "python.linting.enabled": true
}
```

### **Desenvolvimento Java:**
```json
{
  "workbench.colorTheme": "Material Theme",
  "workbench.iconTheme": "vscode-icons",
  "editor.fontFamily": "'Consolas'",
  "editor.tabSize": 4,
  "java.home": "/usr/lib/jvm/java-11-openjdk"
}
```

## 🚀 Produtividade avançada

### **Atalhos personalizados:**
```json
// keybindings.json
[
  {
    "key": "ctrl+shift+c",
    "command": "workbench.action.terminal.openInEditorArea"
  },
  {
    "key": "ctrl+shift+d",
    "command": "workbench.action.debug.start"
  },
  {
    "key": "ctrl+shift+t",
    "command": "workbench.action.terminal.toggleTerminal"
  },
  {
    "key": "ctrl+shift+z",
    "command": "workbench.action.toggleZenMode"
  }
]
```

### **Snippets para produtividade:**
```json
{
  "File Header": {
    "prefix": "header",
    "body": [
      "/**",
      " * @fileoverview $1",
      " * @author ${2:Your Name}",
      " * @created ${CURRENT_YEAR}-${CURRENT_MONTH}-${CURRENT_DATE}",
      " */",
      "",
      "$3"
    ],
    "description": "File header with metadata"
  },
  "Console Log": {
    "prefix": "clg",
    "body": [
      "console.log('$1:', $1);"
    ],
    "description": "Console log with variable name"
  }
}
```

## 🧪 Desafio Aula 9

### Exercícios básicos:

1. **Instalar e configurar tema**:
   ```bash
   # 1. Instale um tema (ex: One Dark Pro)
   # 2. Aplique o tema: Ctrl/Cmd + K Ctrl/Cmd + T
   # 3. Configure no settings.json:
   {
     "workbench.colorTheme": "One Dark Pro"
   }
   ```

2. **Configurar ícones**:
   ```bash
   # 1. Instale vscode-icons
   # 2. Configure no settings.json:
   {
     "workbench.iconTheme": "vscode-icons"
   }
   ```

3. **Instalar GitLens**:
   ```bash
   # 1. Instale GitLens
   # 2. Explore o histórico de um arquivo
   # 3. Use o blame view
   ```

### Exercícios intermediários:

4. **Configurar Todo Tree**:
   ```json
   {
     "todo-tree.general.tags": [
       "TODO",
       "FIXME",
       "BUG",
       "HACK"
     ],
     "todo-tree.highlights.customHighlight": {
       "TODO": {
         "icon": "check",
         "foreground": "#fff",
         "background": "#ffbd2a"
       }
     }
   }
   ```

5. **Configurar Code Spell Checker**:
   ```json
   {
     "cSpell.enabled": true,
     "cSpell.language": "en,pt",
     "cSpell.words": [
       "npm",
       "jsx",
       "tsx",
       "webpack"
     ]
   }
   ```

6. **Configurar Zen Mode**:
   ```json
   {
     "zenMode.fullScreen": false,
     "zenMode.hideLineNumbers": false,
     "zenMode.hideTabs": false
   }
   ```

### Exercícios avançados:

7. **Configuração completa de produtividade**:
   ```json
   {
     "workbench.colorTheme": "One Dark Pro",
     "workbench.iconTheme": "vscode-icons",
     "editor.fontFamily": "'Fira Code'",
     "editor.fontLigatures": true,
     "editor.fontSize": 14,
     "editor.lineHeight": 1.5,
     "editor.cursorBlinking": "smooth",
     "editor.bracketPairColorization.enabled": true,
     "editor.guides.bracketPairs": true,
     "editor.renderWhitespace": "boundary",
     "editor.minimap.enabled": true,
     "workbench.editor.enablePreview": false,
     "workbench.editor.showTabs": "multiple",
     "terminal.integrated.fontFamily": "'Fira Code'",
     "terminal.integrated.fontLigatures": true
   }
   ```

8. **Atalhos personalizados avançados**:
   ```json
   [
     {
       "key": "ctrl+shift+c",
       "command": "workbench.action.terminal.openInEditorArea"
     },
     {
       "key": "ctrl+shift+d",
       "command": "workbench.action.debug.start"
     },
     {
       "key": "ctrl+shift+t",
       "command": "workbench.action.terminal.toggleTerminal"
     },
     {
       "key": "ctrl+shift+z",
       "command": "workbench.action.toggleZenMode"
     },
     {
       "key": "ctrl+shift+p",
       "command": "workbench.action.quickOpen"
     }
   ]
   ```

### Checklist de conclusão:
- [ ] Tema instalado e aplicado
- [ ] Ícones configurados
- [ ] GitLens instalado e testado
- [ ] Todo Tree configurado
- [ ] Code Spell Checker ativo
- [ ] Zen Mode testado
- [ ] Configuração completa aplicada
- [ ] Atalhos personalizados configurados

### Dicas importantes:
- **Performance**: Não instale muitas extensões desnecessárias
- **Consistência**: Mantenha configurações consistentes entre projetos
- **Backup**: Use Settings Sync para backup das configurações
- **Teste**: Experimente diferentes temas antes de escolher

### Próximos passos:
Na próxima aula, aprenderemos sobre:
- Configurações de equipe
- Integração com ferramentas externas
- Extensões especializadas por área
- Automação avançada e CI/CD