# ⚙️ Aula 4 – Configurações avançadas e Workspaces

## 🔧 O que são Workspaces?

### Definição e conceitos
Um **Workspace** é um conjunto de pastas, configurações e preferências que você pode salvar para um projeto específico. É como um "ambiente de trabalho" personalizado para cada projeto.

### Benefícios dos Workspaces:
- ✅ **Configurações específicas** para cada projeto
- ✅ **Layouts personalizados** (posição de painéis, abas abertas)
- ✅ **Extensões ativadas** apenas quando necessário
- ✅ **Tarefas personalizadas** e configurações de build
- ✅ **Configurações de debug** específicas
- ✅ **Backup e compartilhamento** de configurações de projeto

## 📂 Criando e gerenciando Workspaces

### Método 1: Criar workspace a partir de pastas
1. Abra uma ou mais pastas no VS Code
2. Menu: `File > Save Workspace As...`
3. Escolha local e nome para o arquivo `.code-workspace`
4. O workspace será salvo com todas as configurações atuais

### Método 2: Criar workspace manualmente
```json
// meu-projeto.code-workspace
{
  "folders": [
    {
      "name": "Frontend",
      "path": "./frontend"
    },
    {
      "name": "Backend", 
      "path": "./backend"
    },
    {
      "name": "Documentação",
      "path": "./docs"
    }
  ],
  "settings": {
    "editor.tabSize": 2,
    "editor.formatOnSave": true,
    "files.exclude": {
      "**/node_modules": true,
      "**/.git": true
    }
  },
  "extensions": {
    "recommendations": [
      "esbenp.prettier-vscode",
      "ms-vscode.vscode-typescript-next",
      "bradlc.vscode-tailwindcss"
    ]
  }
}
```

### Estrutura de um arquivo workspace:
```json
{
  "folders": [
    // Lista de pastas do projeto
  ],
  "settings": {
    // Configurações específicas do workspace
  },
  "extensions": {
    "recommendations": [
      // Extensões recomendadas
    ]
  },
  "launch": {
    // Configurações de debug
  },
  "tasks": {
    // Tarefas personalizadas
  }
}
```

## ⚙️ Configurações avançadas por nível

### 🔧 **User Settings (Globais)**
- **Localização**: `%APPDATA%/Code/User/settings.json` (Windows)
- **Aplicação**: Todos os projetos
- **Acesso**: `Ctrl/Cmd + ,` → ícone `{}`

### 🎯 **Workspace Settings (Específicas)**
- **Localização**: `.vscode/settings.json` na raiz do projeto
- **Aplicação**: Apenas o workspace atual
- **Prioridade**: Sobrescrevem as configurações globais

### 📁 **Folder Settings (Por pasta)**
- **Localização**: `.vscode/settings.json` em subpastas
- **Aplicação**: Apenas a pasta específica
- **Uso**: Para configurações específicas de linguagem

## 🔧 Configurações avançadas por categoria

### 📝 **Editor e Formatação**
```json
{
  "editor.tabSize": 2,
  "editor.insertSpaces": true,
  "editor.detectIndentation": true,
  "editor.formatOnSave": true,
  "editor.formatOnPaste": true,
  "editor.formatOnType": false,
  "editor.rulers": [80, 120],
  "editor.wordWrap": "on",
  "editor.minimap.enabled": true,
  "editor.bracketPairColorization.enabled": true,
  "editor.guides.bracketPairs": true,
  "editor.suggestSelection": "first",
  "editor.acceptSuggestionOnEnter": "on",
  "editor.tabCompletion": "on"
}
```

### 🎨 **Tema e Interface**
```json
{
  "workbench.colorTheme": "Default Dark+",
  "workbench.iconTheme": "vs-seti",
  "workbench.fontAliasing": "antialiased",
  "workbench.editor.enablePreview": false,
  "workbench.editor.enablePreviewFromQuickOpen": false,
  "workbench.editor.showTabs": "multiple",
  "workbench.editor.tabSizing": "shrink"
}
```

### 📁 **Explorador de Arquivos**
```json
{
  "files.exclude": {
    "**/node_modules": true,
    "**/.git": true,
    "**/.DS_Store": true,
    "**/Thumbs.db": true,
    "**/dist": true,
    "**/build": true
  },
  "files.watcherExclude": {
    "**/node_modules/**": true,
    "**/dist/**": true
  },
  "files.trimTrailingWhitespace": true,
  "files.insertFinalNewline": true,
  "files.autoSave": "afterDelay",
  "files.autoSaveDelay": 1000
}
```

### 🔍 **Busca e IntelliSense**
```json
{
  "search.exclude": {
    "**/node_modules": true,
    "**/dist": true,
    "**/build": true
  },
  "search.useGlobalIgnoreFiles": true,
  "search.useParentIgnoreFiles": true,
  "editor.quickSuggestions": {
    "other": true,
    "comments": false,
    "strings": true
  },
  "editor.suggestOnTriggerCharacters": true,
  "editor.acceptSuggestionOnCommitCharacter": true
}
```

## 🐛 Debugging e Configurações de Debug

### Configuração básica de debug:
```json
// .vscode/launch.json
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Launch Chrome",
      "type": "chrome",
      "request": "launch",
      "url": "http://localhost:3000",
      "webRoot": "${workspaceFolder}"
    },
    {
      "name": "Launch Node.js",
      "type": "node",
      "request": "launch",
      "program": "${workspaceFolder}/app.js",
      "console": "integratedTerminal"
    },
    {
      "name": "Attach to Process",
      "type": "node",
      "request": "attach",
      "port": 9229
    }
  ]
}
```

### Debugging por linguagem:

#### **JavaScript/Node.js:**
```json
{
  "name": "Debug Node.js",
  "type": "node",
  "request": "launch",
  "program": "${workspaceFolder}/src/index.js",
  "env": {
    "NODE_ENV": "development"
  },
  "console": "integratedTerminal"
}
```

#### **Python:**
```json
{
  "name": "Debug Python",
  "type": "python",
  "request": "launch",
  "program": "${workspaceFolder}/main.py",
  "console": "integratedTerminal",
  "justMyCode": true
}
```

#### **C#:**
```json
{
  "name": "Debug C#",
  "type": "coreclr",
  "request": "launch",
  "preLaunchTask": "build",
  "program": "${workspaceFolder}/bin/Debug/net6.0/MyApp.dll",
  "args": [],
  "cwd": "${workspaceFolder}",
  "console": "internalConsole"
}
```

## 🔧 Tarefas personalizadas (Tasks)

### Configuração de tarefas:
```json
// .vscode/tasks.json
{
  "version": "2.0.0",
  "tasks": [
    {
      "label": "npm install",
      "type": "shell",
      "command": "npm",
      "args": ["install"],
      "group": "build",
      "presentation": {
        "echo": true,
        "reveal": "always",
        "focus": false,
        "panel": "shared"
      }
    },
    {
      "label": "npm start",
      "type": "shell",
      "command": "npm",
      "args": ["start"],
      "group": "build",
      "isBackground": true,
      "problemMatcher": {
        "pattern": {
          "regexp": "^([^\\s].*)\\((\\d+,\\d+)\\):\\s+(error|warning|info)\\s+(CS\\d+):\\s+(.*)$",
          "file": 1,
          "location": 2,
          "severity": 3,
          "code": 4,
          "message": 5
        },
        "background": {
          "activeOnStart": true,
          "beginsPattern": "^.*starting.*$",
          "endsPattern": "^.*started.*$"
        }
      }
    }
  ]
}
```

### Executando tarefas:
- **Atalho**: `Ctrl/Cmd + Shift + P` → "Tasks: Run Task"
- **Menu**: Terminal → Run Task
- **Automação**: Configurar para executar automaticamente

## 🔄 Gerenciando Workspaces

### Carregando um workspace:
1. **Arquivo**: Abra o arquivo `.code-workspace` diretamente
2. **Menu**: File → Open Workspace from File...
3. **Recent**: File → Open Recent → selecione o workspace

### Organizando múltiplos projetos:
```json
// projetos.code-workspace
{
  "folders": [
    {
      "name": "📱 App Mobile",
      "path": "./mobile-app"
    },
    {
      "name": "🌐 Website",
      "path": "./website"
    },
    {
      "name": "📊 Dashboard",
      "path": "./dashboard"
    },
    {
      "name": "📚 Documentação",
      "path": "./docs"
    }
  ],
  "settings": {
    "editor.tabSize": 2,
    "editor.formatOnSave": true,
    "files.exclude": {
      "**/node_modules": true,
      "**/.git": true
    }
  }
}
```

### Configurações específicas por tipo de projeto:

#### **Projeto React:**
```json
{
  "folders": [
    { "path": "." }
  ],
  "settings": {
    "editor.tabSize": 2,
    "editor.formatOnSave": true,
    "emmet.includeLanguages": {
      "javascript": "javascriptreact"
    },
    "typescript.preferences.importModuleSpecifier": "relative"
  },
  "extensions": {
    "recommendations": [
      "esbenp.prettier-vscode",
      "ms-vscode.vscode-typescript-next",
      "bradlc.vscode-tailwindcss"
    ]
  }
}
```

#### **Projeto Python:**
```json
{
  "folders": [
    { "path": "." }
  ],
  "settings": {
    "python.defaultInterpreterPath": "./venv/bin/python",
    "python.linting.enabled": true,
    "python.linting.pylintEnabled": true,
    "python.formatting.provider": "black",
    "editor.tabSize": 4,
    "editor.insertSpaces": true
  },
  "extensions": {
    "recommendations": [
      "ms-python.python",
      "ms-python.pylint"
    ]
  }
}
```

## 🧪 Desafio Aula 4

### Exercícios básicos:

1. **Criar workspace simples**:
   ```bash
   # Crie uma estrutura de projeto
   mkdir meu-projeto
   cd meu-projeto
   mkdir src docs tests
   
   # Abra no VS Code e salve como workspace
   code .
   # File > Save Workspace As... > meu-projeto.code-workspace
   ```

2. **Configurações específicas**:
   ```json
   // Configure apenas para este workspace:
   {
     "editor.tabSize": 4,
     "editor.formatOnSave": false,
     "files.exclude": {
       "**/node_modules": true
     }
   }
   ```

3. **Workspace com múltiplas pastas**:
   ```json
   // Crie um workspace com frontend e backend
   {
     "folders": [
       { "name": "Frontend", "path": "./frontend" },
       { "name": "Backend", "path": "./backend" }
     ]
   }
   ```

### Exercícios intermediários:

4. **Configuração de debug**:
   ```json
   // .vscode/launch.json
   {
     "version": "0.2.0",
     "configurations": [
       {
         "name": "Debug Web App",
         "type": "chrome",
         "request": "launch",
         "url": "http://localhost:3000",
         "webRoot": "${workspaceFolder}"
       }
     ]
   }
   ```

5. **Tarefas personalizadas**:
   ```json
   // .vscode/tasks.json
   {
     "version": "2.0.0",
     "tasks": [
       {
         "label": "Start Dev Server",
         "type": "shell",
         "command": "npm",
         "args": ["run", "dev"],
         "group": "build"
       }
     ]
   }
   ```

6. **Extensões recomendadas**:
   ```json
   // Adicione extensões específicas ao workspace
   {
     "extensions": {
       "recommendations": [
         "esbenp.prettier-vscode",
         "ms-vscode.vscode-typescript-next"
       ]
     }
   }
   ```

### Exercícios avançados:

7. **Workspace complexo**:
   ```json
   // Crie um workspace para um projeto full-stack
   {
     "folders": [
       { "name": "🌐 Frontend", "path": "./frontend" },
       { "name": "⚙️ Backend", "path": "./backend" },
       { "name": "📱 Mobile", "path": "./mobile" },
       { "name": "📊 Database", "path": "./database" },
       { "name": "📚 Docs", "path": "./docs" }
     ],
     "settings": {
       "editor.tabSize": 2,
       "editor.formatOnSave": true,
       "files.exclude": {
         "**/node_modules": true,
         "**/dist": true,
         "**/.git": true
       }
     },
     "extensions": {
       "recommendations": [
         "esbenp.prettier-vscode",
         "ms-vscode.vscode-typescript-next",
         "ms-python.python",
         "ms-vscode.vscode-json"
       ]
     }
   }
   ```

8. **Configurações específicas por pasta**:
   ```json
   // .vscode/settings.json na pasta frontend
   {
     "typescript.preferences.importModuleSpecifier": "relative",
     "emmet.includeLanguages": {
       "javascript": "javascriptreact"
     }
   }
   
   // .vscode/settings.json na pasta backend
   {
     "python.defaultInterpreterPath": "./venv/bin/python",
     "python.linting.enabled": true
   }
   ```

### Checklist de conclusão:
- [ ] Workspace criado e configurado
- [ ] Configurações específicas aplicadas
- [ ] Debug configurado para projeto
- [ ] Tarefas personalizadas criadas
- [ ] Extensões recomendadas adicionadas
- [ ] Múltiplas pastas organizadas
- [ ] Configurações por pasta implementadas
- [ ] Workspace salvo e testado

### Dicas importantes:
- **Backup**: Mantenha backups dos arquivos workspace
- **Versionamento**: Inclua `.code-workspace` no Git
- **Performance**: Não carregue muitas pastas desnecessárias
- **Organização**: Use nomes descritivos para as pastas

### Próximos passos:
Na próxima aula, aprenderemos sobre:
- Integração avançada com Git
- Extensões especializadas por área
- Automação e scripts
- Configurações de equipe