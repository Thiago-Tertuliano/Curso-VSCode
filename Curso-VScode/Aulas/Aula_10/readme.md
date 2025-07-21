# 🤖 Aula 10 – Automatização com Snippets e Macros

## 📝 Snippets Avançados

### **Snippets com variáveis e transformações:**

#### **Variáveis do VS Code:**
- **$TM_FILENAME**: Nome do arquivo atual
- **$TM_FILENAME_BASE**: Nome do arquivo sem extensão
- **$TM_DIRECTORY**: Diretório do arquivo
- **$TM_FILEPATH**: Caminho completo do arquivo
- **$CURRENT_YEAR**: Ano atual
- **$CURRENT_YEAR_SHORT**: Ano atual (2 dígitos)
- **$CURRENT_MONTH**: Mês atual (2 dígitos)
- **$CURRENT_DATE**: Data atual
- **$CURRENT_HOUR**: Hora atual
- **$CURRENT_MINUTE**: Minuto atual
- **$CURRENT_SECOND**: Segundo atual
- **$RANDOM**: Número aleatório
- **$RANDOM_HEX**: Número hexadecimal aleatório
- **$UUID**: UUID único

#### **Transformações de variáveis:**
```json
{
  "React Component": {
    "prefix": "rfc",
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
    "description": "React functional component"
  }
}
```

### **Snippets com lógica condicional:**
```json
{
  "Conditional Component": {
    "prefix": "rcc",
    "body": [
      "import React from 'react';",
      "",
      "interface ${1:${TM_FILENAME_BASE}}Props {",
      "\t$2",
      "}",
      "",
      "const ${1:${TM_FILENAME_BASE}}: React.FC<${1:${TM_FILENAME_BASE}}Props> = ({ $3 }) => {",
      "\treturn (",
      "\t\t<div>",
      "\t\t\t$4",
      "\t\t</div>",
      "\t);",
      "};",
      "",
      "export default ${1:${TM_FILENAME_BASE}};"
    ],
    "description": "React component with TypeScript props"
  }
}
```

### **Snippets para diferentes linguagens:**

#### **JavaScript/TypeScript:**
```json
{
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
  "Arrow Function": {
    "prefix": "arrow",
    "body": [
      "const ${1:functionName} = (${2:params}) => {",
      "\t$3",
      "}"
    ],
    "description": "Arrow function"
  },
  "Class": {
    "prefix": "class",
    "body": [
      "class ${1:ClassName} {",
      "\tconstructor(${2:params}) {",
      "\t\t$3",
      "\t}",
      "\t",
      "\t${4:methodName}() {",
      "\t\t$5",
      "\t}",
      "}"
    ],
    "description": "JavaScript class"
  }
}
```

#### **HTML:**
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
  "Form": {
    "prefix": "form",
    "body": [
      "<form action=\"$1\" method=\"$2\">",
      "\t<label for=\"$3\">$4</label>",
      "\t<input type=\"$5\" id=\"$3\" name=\"$3\" required>",
      "\t<button type=\"submit\">$6</button>",
      "</form>"
    ],
    "description": "HTML form"
  }
}
```

#### **CSS:**
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

## 🔄 Macros no VS Code

### **Extensões para macros:**

#### **Macros (geddski.macros):**
- **Funcionalidades**: Executar sequências de comandos
- **Configuração**:
```json
{
  "macros": {
    "printHello": [
      "editor.action.insertSnippet",
      {
        "snippet": "console.log('Hello, world!');"
      }
    ],
    "addComment": [
      "editor.action.insertSnippet",
      {
        "snippet": "// $1"
      }
    ],
    "createFunction": [
      "editor.action.insertSnippet",
      {
        "snippet": "function ${1:functionName}(${2:params}) {\n\t$3\n}"
      }
    ]
  }
}
```

#### **Multi Command:**
- **Funcionalidades**: Agrupar comandos em sequência
- **Configuração**:
```json
{
  "multiCommand.commands": [
    {
      "command": "multiCommand.saveAndFormat",
      "sequence": [
        "workbench.action.files.save",
        "editor.action.formatDocument"
      ]
    },
    {
      "command": "multiCommand.debugAndRun",
      "sequence": [
        "workbench.action.debug.start",
        "workbench.action.terminal.toggleTerminal"
      ]
    }
  ]
}
```

### **Exemplos de macros úteis:**

#### **Macro para desenvolvimento web:**
```json
{
  "macros": {
    "createReactComponent": [
      "editor.action.insertSnippet",
      {
        "snippet": [
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
        ].join("\n")
      }
    ]
  }
}
```

#### **Macro para debugging:**
```json
{
  "macros": {
    "addDebugLog": [
      "editor.action.insertSnippet",
      {
        "snippet": "console.log('DEBUG:', $1);"
      }
    ],
    "addErrorLog": [
      "editor.action.insertSnippet",
      {
        "snippet": "console.error('ERROR:', $1);"
      }
    ]
  }
}
```

## ⚙️ Automação avançada

### **Extensões de automação:**

#### **Auto Rename Tag:**
- Renomeia tags HTML/JSX automaticamente
- Funciona automaticamente

#### **Bracket Pair Colorizer 2:**
- Colorização de parênteses
- Facilita navegação no código

#### **Auto Close Tag:**
- Fecha tags automaticamente
- Configuração:
```json
{
  "auto-close-tag.activationOnLanguage": [
    "html",
    "xml",
    "php",
    "javascript",
    "javascriptreact",
    "typescript",
    "typescriptreact"
  ]
}
```

#### **Auto Import:**
- Importa módulos automaticamente
- Configuração:
```json
{
  "typescript.suggest.autoImports": true,
  "javascript.suggest.autoImports": true
}
```

### **Snippets globais:**
```json
{
  "File Header": {
    "prefix": "header",
    "body": [
      "/**",
      " * @fileoverview $1",
      " * @author ${2:Your Name}",
      " * @created ${CURRENT_YEAR}-${CURRENT_MONTH}-${CURRENT_DATE}",
      " * @version 1.0.0",
      " */",
      "",
      "$3"
    ],
    "description": "File header with metadata"
  },
  "Function Documentation": {
    "prefix": "doc",
    "body": [
      "/**",
      " * $1",
      " * @param {$2} $3 - $4",
      " * @returns {$5} $6",
      " */"
    ],
    "description": "Function documentation"
  }
}
```

## 🎯 Automação específica por área

### **Desenvolvimento Frontend:**
```json
{
  "React Hook": {
    "prefix": "hook",
    "body": [
      "import { useState, useEffect } from 'react';",
      "",
      "const use${1:HookName} = () => {",
      "\tconst [${2:state}, set${2/(.*)/${2:/capitalize}/}] = useState(${3:initialValue});",
      "\t",
      "\tuseEffect(() => {",
      "\t\t$4",
      "\t}, []);",
      "\t",
      "\treturn {",
      "\t\t${2},",
      "\t\tset${2/(.*)/${2:/capitalize}/}",
      "\t};",
      "};",
      "",
      "export default use${1:HookName};"
    ],
    "description": "React custom hook"
  }
}
```

### **Desenvolvimento Backend:**
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

### **Testes:**
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

## 🧪 Desafio Aula 10

### Exercícios básicos:

1. **Criar snippet básico**:
   ```json
   {
     "Console Log": {
       "prefix": "clg",
       "body": [
         "console.log('$1:', $1);"
       ],
       "description": "Console log with variable name"
     }
   }
   ```

2. **Instalar extensão Macros**:
   ```bash
   # 1. Instale a extensão Macros
   # 2. Configure no settings.json:
   {
     "macros": {
       "printHello": [
         "editor.action.insertSnippet",
         {
           "snippet": "console.log('Hello, world!');"
         }
       ]
     }
   }
   ```

3. **Testar snippet e macro**:
   ```javascript
   // Teste o snippet digitando "clg" e Tab
   // Teste a macro usando Ctrl/Cmd + Shift + P → "Macros: Run Macro"
   ```

### Exercícios intermediários:

4. **Snippet com variáveis**:
   ```json
   {
     "React Component": {
       "prefix": "rfc",
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
       "description": "React functional component"
     }
   }
   ```

5. **Macro com múltiplos comandos**:
   ```json
   {
     "macros": {
       "saveAndFormat": [
         "workbench.action.files.save",
         "editor.action.formatDocument"
       ],
       "addComment": [
         "editor.action.insertSnippet",
         {
           "snippet": "// $1"
         }
       ]
     }
   }
   ```

6. **Snippet para HTML**:
   ```json
   {
     "HTML Link": {
       "prefix": "link",
       "body": [
         "<link rel=\"stylesheet\" href=\"$1\">"
       ],
       "description": "CSS link"
     },
     "HTML Script": {
       "prefix": "script",
       "body": [
         "<script src=\"$1\"></script>"
       ],
       "description": "JavaScript script"
     }
   }
   ```

### Exercícios avançados:

7. **Snippet complexo com transformações**:
   ```json
   {
     "React Hook with TypeScript": {
       "prefix": "rhook",
       "body": [
         "import { useState, useEffect } from 'react';",
         "",
         "interface Use${1:HookName}Props {",
         "\t$2",
         "}",
         "",
         "interface Use${1:HookName}Return {",
         "\t$3",
         "}",
         "",
         "const use${1:HookName} = (props: Use${1:HookName}Props): Use${1:HookName}Return => {",
         "\t$4",
         "\t",
         "\treturn {",
         "\t\t$5",
         "\t};",
         "};",
         "",
         "export default use${1:HookName};"
       ],
       "description": "React TypeScript hook"
     }
   }
   ```

8. **Macro para desenvolvimento completo**:
   ```json
   {
     "macros": {
       "createComponent": [
         "editor.action.insertSnippet",
         {
           "snippet": [
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
           ].join("\n")
         },
         "editor.action.insertSnippet",
         {
           "snippet": [
             "import React from 'react';",
             "import { render, screen } from '@testing-library/react';",
             "import ${1:ComponentName} from './${1:ComponentName}';",
             "",
             "describe('${1:ComponentName}', () => {",
             "\tit('should render correctly', () => {",
             "\t\trender(<${1:ComponentName} />);",
             "\t});",
             "});"
           ].join("\n")
         }
       ]
     }
   }
   ```

### Checklist de conclusão:
- [ ] Snippet básico criado e testado
- [ ] Extensão Macros instalada
- [ ] Macro simples configurada
- [ ] Snippet com variáveis implementado
- [ ] Macro com múltiplos comandos criada
- [ ] Snippet para HTML configurado
- [ ] Snippet complexo com transformações
- [ ] Macro para desenvolvimento completo

### Dicas importantes:
- **Organização**: Agrupe snippets por linguagem ou projeto
- **Nomenclatura**: Use prefixos intuitivos e consistentes
- **Documentação**: Comente snippets complexos
- **Teste**: Sempre teste snippets antes de usar em produção

### Próximos passos:
Na próxima aula, aprenderemos sobre:
- Configurações de equipe
- Integração com ferramentas externas
- Extensões especializadas por área
- Automação avançada e CI/CD