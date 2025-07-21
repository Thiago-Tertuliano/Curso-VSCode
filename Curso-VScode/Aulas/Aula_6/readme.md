# 🎨 Aula 6 – Customizações, Snippets e Temas

## 🧩 Snippets – Criando automações personalizadas

### O que são Snippets?
Snippets são trechos de código pré-definidos que você pode inserir rapidamente para agilizar sua escrita. Eles são como "atalhos de código" que economizam tempo e reduzem erros de digitação.

### Tipos de Snippets:
1. **User Snippets**: Snippets pessoais criados por você
2. **Extension Snippets**: Snippets que vêm com extensões
3. **Workspace Snippets**: Snippets específicos do projeto
4. **Global Snippets**: Snippets disponíveis em todas as linguagens

## 🔧 Criando Snippets Personalizados

### Método 1: Interface do VS Code
1. `Ctrl/Cmd + Shift + P` → "Preferences: Configure User Snippets"
2. Escolha a linguagem ou "New Global Snippets file"
3. Digite o nome do arquivo de snippets
4. Edite o JSON com seus snippets

### Método 2: Arquivo JSON direto
```json
// snippets/javascript.json
{
  "Console log": {
    "prefix": "clg",
    "body": [
      "console.log('$1');",
      "$2"
    ],
    "description": "Console log básico"
  },
  "Function": {
    "prefix": "func",
    "body": [
      "function ${1:functionName}(${2:params}) {",
      "\t$3",
      "}"
    ],
    "description": "Function declaration"
  },
  "Arrow Function": {
    "prefix": "arrow",
    "body": [
      "const ${1:functionName} = (${2:params}) => {",
      "\t$3",
      "}"
    ],
    "description": "Arrow function"
  }
}
```

### Estrutura de um Snippet:
```json
{
  "Nome do Snippet": {
    "prefix": "atalho",
    "body": [
      "linha 1 do código",
      "linha 2 do código"
    ],
    "description": "Descrição do snippet"
  }
}
```

### Variáveis e Placeholders:
- **$1, $2, $3**: Pontos de cursor (Tab para navegar)
- **${1:default}**: Placeholder com valor padrão
- **$TM_FILENAME**: Nome do arquivo atual
- **$CURRENT_YEAR**: Ano atual
- **$CURRENT_DATE**: Data atual
- **$RANDOM**: Número aleatório

## 📝 Snippets por linguagem

### **JavaScript/TypeScript:**
```json
{
  "Console log with timestamp": {
    "prefix": "clgt",
    "body": [
      "console.log(`[${new Date().toISOString()}] $1`);"
    ],
    "description": "Console log com timestamp"
  },
  "Async Function": {
    "prefix": "async",
    "body": [
      "async function ${1:functionName}(${2:params}) {",
      "\ttry {",
      "\t\t$3",
      "\t} catch (error) {",
      "\t\tconsole.error('Error:', error);",
      "\t\tthrow error;",
      "\t}",
      "}"
    ],
    "description": "Async function with try-catch"
  },
  "Import statement": {
    "prefix": "imp",
    "body": [
      "import { $1 } from '$2';"
    ],
    "description": "Import statement"
  },
  "Export default": {
    "prefix": "expd",
    "body": [
      "export default $1;"
    ],
    "description": "Export default"
  }
}
```

### **HTML:**
```json
{
  "HTML5 Template": {
    "prefix": "html5",
    "body": [
      "<!DOCTYPE html>",
      "<html lang=\"pt-BR\">",
      "<head>",
      "\t<meta charset=\"UTF-8\">",
      "\t<meta name=\"viewport\" content=\"width=device-width, initial-scale=1.0\">",
      "\t<title>$1</title>",
      "\t<link rel=\"stylesheet\" href=\"$2\">",
      "</head>",
      "<body>",
      "\t$3",
      "\t<script src=\"$4\"></script>",
      "</body>",
      "</html>"
    ],
    "description": "HTML5 template completo"
  },
  "React Component": {
    "prefix": "rfc",
    "body": [
      "import React from 'react';",
      "",
      "const ${1:ComponentName} = () => {",
      "\treturn (",
      "\t\t<div>",
      "\t\t\t$2",
      "\t\t</div>",
      "\t);",
      "};",
      "",
      "export default ${1:ComponentName};"
    ],
    "description": "React functional component"
  }
}
```

### **CSS:**
```json
{
  "Flexbox Container": {
    "prefix": "flex",
    "body": [
      "display: flex;",
      "justify-content: $1;",
      "align-items: $2;",
      "flex-direction: $3;"
    ],
    "description": "Flexbox container"
  },
  "CSS Grid": {
    "prefix": "grid",
    "body": [
      "display: grid;",
      "grid-template-columns: $1;",
      "grid-template-rows: $2;",
      "gap: $3;"
    ],
    "description": "CSS Grid layout"
  },
  "Media Query": {
    "prefix": "media",
    "body": [
      "@media screen and (max-width: ${1:768px}) {",
      "\t$2",
      "}"
    ],
    "description": "Media query"
  }
}
```

### **Python:**
```json
{
  "Main function": {
    "prefix": "main",
    "body": [
      "if __name__ == \"__main__\":",
      "\t$1"
    ],
    "description": "Main function guard"
  },
  "Class": {
    "prefix": "class",
    "body": [
      "class ${1:ClassName}:",
      "\tdef __init__(self, ${2:params}):",
      "\t\t$3",
      "\t",
      "\tdef ${4:method_name}(self):",
      "\t\t$5"
    ],
    "description": "Python class"
  },
  "Try except": {
    "prefix": "try",
    "body": [
      "try:",
      "\t$1",
      "except ${2:Exception} as e:",
      "\tprint(f'Error: {e}')",
      "\t$3"
    ],
    "description": "Try except block"
  }
}
```

## 🎨 Temas e Personalização Visual

### **Temas de Cores**

#### Temas populares:
- **One Dark Pro**: Tema escuro baseado no Atom
- **Dracula Official**: Tema roxo/azul escuro
- **Night Owl**: Tema para desenvolvimento noturno
- **Material Theme**: Temas baseados no Material Design
- **Monokai Pro**: Tema clássico com cores vibrantes
- **Winter is Coming**: Tema com variações de azul

#### Instalando temas:
1. `Ctrl/Cmd + Shift + X` → Marketplace
2. Busque por "theme"
3. Instale o tema desejado
4. `Ctrl/Cmd + K Ctrl/Cmd + T` → Selecione o tema

### **Ícones de Arquivos**

#### Extensões de ícones populares:
- **vscode-icons**: Ícones coloridos e organizados
- **Material Icon Theme**: Ícones Material Design
- **Seti Icons**: Ícones minimalistas
- **A File Icon**: Ícones simples e claros

#### Configurando ícones:
```json
{
  "workbench.iconTheme": "vscode-icons",
  "vscode-icons.dontShowNewVersionMessage": true,
  "vscode-icons.associations.files": [
    { "icon": "js", "extensions": ["js", "jsx"] },
    { "icon": "ts", "extensions": ["ts", "tsx"] }
  ]
}
```

### **Fontes e Tipografia**

#### Configurando fontes:
```json
{
  "editor.fontFamily": "'Fira Code', 'Consolas', 'Courier New', monospace",
  "editor.fontSize": 14,
  "editor.fontWeight": "normal",
  "editor.fontLigatures": true,
  "editor.letterSpacing": 0.5,
  "editor.lineHeight": 1.5
}
```

#### Fontes recomendadas para programação:
- **Fira Code**: Com ligaduras
- **JetBrains Mono**: Fonte oficial da JetBrains
- **Cascadia Code**: Fonte da Microsoft
- **Source Code Pro**: Fonte Adobe

## ⚙️ Configurações avançadas de customização

### **Editor e Interface**
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
  "editor.cursorSmoothCaretAnimation": "on",
  "editor.cursorStyle": "line"
}
```

### **Workbench (Interface)**
```json
{
  "workbench.colorTheme": "One Dark Pro",
  "workbench.iconTheme": "vscode-icons",
  "workbench.productIconTheme": "Default",
  "workbench.editor.enablePreview": false,
  "workbench.editor.enablePreviewFromQuickOpen": false,
  "workbench.editor.showTabs": "multiple",
  "workbench.editor.tabSizing": "shrink",
  "workbench.editor.decorations.badges": true,
  "workbench.editor.decorations.colors": true,
  "workbench.sideBar.location": "left",
  "workbench.panel.defaultLocation": "bottom",
  "workbench.statusBar.visible": true,
  "workbench.activityBar.visible": true
}
```

### **Terminal Personalizado**
```json
{
  "terminal.integrated.fontFamily": "'Fira Code'",
  "terminal.integrated.fontSize": 14,
  "terminal.integrated.lineHeight": 1.2,
  "terminal.integrated.cursorBlinking": true,
  "terminal.integrated.cursorStyle": "line",
  "terminal.integrated.shell.windows": "C:\\Program Files\\Git\\bin\\bash.exe",
  "terminal.integrated.shellArgs.windows": ["--login", "-i"],
  "terminal.integrated.defaultProfile.windows": "Git Bash"
}
```

## 🎯 Snippets avançados e produtividade

### **Snippets com lógica condicional**
```json
{
  "React Component with Props": {
    "prefix": "rfcp",
    "body": [
      "import React from 'react';",
      "",
      "interface ${1:ComponentName}Props {",
      "\t$2",
      "}",
      "",
      "const ${1:ComponentName}: React.FC<${1:ComponentName}Props> = ({ $3 }) => {",
      "\treturn (",
      "\t\t<div>",
      "\t\t\t$4",
      "\t\t</div>",
      "\t);",
      "};",
      "",
      "export default ${1:ComponentName};"
    ],
    "description": "React component with TypeScript props"
  }
}
```

### **Snippets para testes**
```json
{
  "Jest Test": {
    "prefix": "test",
    "body": [
      "describe('${1:Test Suite}', () => {",
      "\tit('${2:should do something}', () => {",
      "\t\t$3",
      "\t});",
      "});"
    ],
    "description": "Jest test structure"
  },
  "React Testing": {
    "prefix": "rtest",
    "body": [
      "import { render, screen } from '@testing-library/react';",
      "import ${1:ComponentName} from './${1:ComponentName}';",
      "",
      "describe('${1:ComponentName}', () => {",
      "\tit('${2:should render correctly}', () => {",
      "\t\trender(<${1:ComponentName} />);",
      "\t\t$3",
      "\t});",
      "});"
    ],
    "description": "React component test"
  }
}
```

### **Snippets para APIs**
```json
{
  "Express Route": {
    "prefix": "route",
    "body": [
      "app.${1:get}('${2:/api/endpoint}', async (req, res) => {",
      "\ttry {",
      "\t\t$3",
      "\t\tres.status(200).json({ success: true, data: $4 });",
      "\t} catch (error) {",
      "\t\tconsole.error('Error:', error);",
      "\t\tres.status(500).json({ success: false, error: error.message });",
      "\t}",
      "});"
    ],
    "description": "Express route with error handling"
  }
}
```

## 🧪 Desafio Aula 6

### Exercícios básicos:

1. **Criar snippets básicos**:
   ```json
   // Crie estes snippets para JavaScript:
   {
     "Console log": {
       "prefix": "clg",
       "body": ["console.log('$1');"],
       "description": "Console log básico"
     },
     "Function": {
       "prefix": "func",
       "body": [
         "function ${1:functionName}(${2:params}) {",
         "\t$3",
         "}"
       ],
       "description": "Function declaration"
     }
   }
   ```

2. **Instalar e configurar tema**:
   ```bash
   # 1. Instale um tema (ex: One Dark Pro)
   # 2. Aplique o tema: Ctrl/Cmd + K Ctrl/Cmd + T
   # 3. Configure no settings.json:
   {
     "workbench.colorTheme": "One Dark Pro"
   }
   ```

3. **Configurar ícones**:
   ```bash
   # 1. Instale vscode-icons
   # 2. Configure no settings.json:
   {
     "workbench.iconTheme": "vscode-icons"
   }
   ```

### Exercícios intermediários:

4. **Snippets para HTML**:
   ```json
   // Crie snippets para estruturas HTML comuns:
   {
     "HTML Link": {
       "prefix": "link",
       "body": ["<link rel=\"stylesheet\" href=\"$1\">"],
       "description": "CSS link"
     },
     "HTML Script": {
       "prefix": "script",
       "body": ["<script src=\"$1\"></script>"],
       "description": "JavaScript script"
     },
     "HTML Meta": {
       "prefix": "meta",
       "body": ["<meta name=\"$1\" content=\"$2\">"],
       "description": "Meta tag"
     }
   }
   ```

5. **Snippets para CSS**:
   ```json
   // Crie snippets para CSS:
   {
     "CSS Media Query": {
       "prefix": "media",
       "body": [
         "@media screen and (max-width: ${1:768px}) {",
         "\t$2",
         "}"
       ],
       "description": "Media query"
     },
     "CSS Animation": {
       "prefix": "keyframes",
       "body": [
         "@keyframes ${1:animationName} {",
         "\t0% {",
         "\t\t$2",
         "\t}",
         "\t100% {",
         "\t\t$3",
         "\t}",
         "}"
       ],
       "description": "CSS keyframes"
     }
   }
   ```

6. **Configuração avançada de fonte**:
   ```json
   // Configure uma fonte com ligaduras:
   {
     "editor.fontFamily": "'Fira Code', 'Consolas', monospace",
     "editor.fontLigatures": true,
     "editor.fontSize": 14,
     "editor.letterSpacing": 0.5,
     "terminal.integrated.fontFamily": "'Fira Code'",
     "terminal.integrated.fontLigatures": true
   }
   ```

### Exercícios avançados:

7. **Snippets complexos com variáveis**:
   ```json
   // Crie snippets que usam variáveis do VS Code:
   {
     "React Component File": {
       "prefix": "rfcfile",
       "body": [
         "import React from 'react';",
         "",
         "const ${1:${TM_FILENAME_BASE}} = () => {",
         "\treturn (",
         "\t\t<div>",
         "\t\t\t$2",
         "\t\t</div>",
         "\t);",
         "};",
         "",
         "export default ${1:${TM_FILENAME_BASE}};"
       ],
       "description": "React component using filename"
     },
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
     }
   }
   ```

8. **Tema personalizado completo**:
   ```json
   // Configure um tema personalizado completo:
   {
     "workbench.colorTheme": "One Dark Pro",
     "workbench.iconTheme": "vscode-icons",
     "editor.fontFamily": "'Fira Code'",
     "editor.fontLigatures": true,
     "editor.fontSize": 14,
     "editor.lineHeight": 1.5,
     "editor.cursorBlinking": "smooth",
     "editor.cursorSmoothCaretAnimation": "on",
     "editor.bracketPairColorization.enabled": true,
     "editor.guides.bracketPairs": true,
     "editor.renderWhitespace": "boundary",
     "editor.minimap.enabled": true,
     "terminal.integrated.fontFamily": "'Fira Code'",
     "terminal.integrated.fontLigatures": true
   }
   ```

### Checklist de conclusão:
- [ ] 3 snippets básicos criados
- [ ] Tema instalado e aplicado
- [ ] Ícones configurados
- [ ] Fonte com ligaduras configurada
- [ ] Snippets para HTML criados
- [ ] Snippets para CSS criados
- [ ] Snippets complexos com variáveis
- [ ] Tema personalizado completo

### Dicas importantes:
- **Snippets**: Use prefixos intuitivos e consistentes
- **Temas**: Teste vários temas antes de escolher
- **Performance**: Não crie muitos snippets desnecessários
- **Organização**: Agrupe snippets por linguagem ou projeto

### Próximos passos:
Na próxima aula, aprenderemos sobre:
- Automação e scripts
- Configurações de equipe
- Integração com ferramentas externas
- Extensões especializadas por área

