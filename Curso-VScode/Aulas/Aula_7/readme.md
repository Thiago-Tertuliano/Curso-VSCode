# 🖥️ Aula 7 – Terminal integrado e tarefas

## 🔥 Terminal integrado

### Acessando o terminal
- **Atalho**: `Ctrl + `` (Windows/Linux) ou `Cmd + `` (Mac)
- **Menu**: Terminal → New Terminal
- **Paleta**: `Ctrl/Cmd + Shift + P` → "Terminal: Create New Terminal"

### Funcionalidades do terminal integrado:
- ✅ **Múltiplos terminais**: Abra quantos precisar
- ✅ **Diferentes shells**: Bash, PowerShell, CMD, Zsh
- ✅ **Navegação integrada**: Terminal na pasta do projeto
- ✅ **Histórico de comandos**: Acesso ao histórico
- ✅ **Autocompletar**: Tab para completar comandos
- ✅ **Seleção de texto**: Mouse e teclado funcionam normalmente

### Gerenciando terminais:
- **Novo terminal**: Clique no `+` ou `Ctrl/Cmd + Shift + `` 
- **Dividir terminal**: `Ctrl/Cmd + Shift + 5`
- **Alternar entre terminais**: `Ctrl/Cmd + PageUp/PageDown`
- **Fechar terminal**: `Ctrl/Cmd + Shift + W`
- **Kill terminal**: `Ctrl/Cmd + Shift + K`

## ⚙️ Configurações do terminal

### Configurações básicas:
```json
{
  "terminal.integrated.fontFamily": "'Fira Code'",
  "terminal.integrated.fontSize": 14,
  "terminal.integrated.lineHeight": 1.2,
  "terminal.integrated.cursorBlinking": true,
  "terminal.integrated.cursorStyle": "line",
  "terminal.integrated.scrollback": 10000,
  "terminal.integrated.enableMultiLinePasteWarning": false
}
```

### Configurações por sistema operacional:

#### **Windows:**
```json
{
  "terminal.integrated.defaultProfile.windows": "Git Bash",
  "terminal.integrated.shell.windows": "C:\\Program Files\\Git\\bin\\bash.exe",
  "terminal.integrated.shellArgs.windows": ["--login", "-i"],
  "terminal.integrated.env.windows": {
    "PATH": "${env:PATH};C:\\Program Files\\Git\\bin"
  }
}
```

#### **macOS:**
```json
{
  "terminal.integrated.defaultProfile.osx": "zsh",
  "terminal.integrated.shell.osx": "/bin/zsh",
  "terminal.integrated.env.osx": {
    "PATH": "/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin"
  }
}
```

#### **Linux:**
```json
{
  "terminal.integrated.defaultProfile.linux": "bash",
  "terminal.integrated.shell.linux": "/bin/bash",
  "terminal.integrated.env.linux": {
    "PATH": "/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin"
  }
}
```

## 🔧 Criando tarefas personalizadas

### Estrutura básica de tasks.json:
```json
{
  "version": "2.0.0",
  "tasks": [
    {
      "label": "Nome da Tarefa",
      "type": "shell",
      "command": "comando",
      "args": ["arg1", "arg2"],
      "group": "build",
      "presentation": {
        "echo": true,
        "reveal": "always",
        "focus": false,
        "panel": "shared"
      },
      "problemMatcher": []
    }
  ]
}
```

### Propriedades das tarefas:
- **label**: Nome da tarefa
- **type**: "shell" ou "process"
- **command**: Comando a executar
- **args**: Argumentos do comando
- **group**: "build", "test", "none"
- **presentation**: Como mostrar a saída
- **problemMatcher**: Padrões para detectar erros

## 📝 Exemplos de tarefas por tipo de projeto

### **Projeto Node.js/React:**
```json
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
    },
    {
      "label": "npm run build",
      "type": "shell",
      "command": "npm",
      "args": ["run", "build"],
      "group": "build",
      "presentation": {
        "echo": true,
        "reveal": "always",
        "focus": false,
        "panel": "shared"
      }
    },
    {
      "label": "npm test",
      "type": "shell",
      "command": "npm",
      "args": ["test"],
      "group": "test",
      "presentation": {
        "echo": true,
        "reveal": "always",
        "focus": false,
        "panel": "shared"
      }
    }
  ]
}
```

### **Projeto Python:**
```json
{
  "version": "2.0.0",
  "tasks": [
    {
      "label": "Install Dependencies",
      "type": "shell",
      "command": "pip",
      "args": ["install", "-r", "requirements.txt"],
      "group": "build",
      "presentation": {
        "echo": true,
        "reveal": "always",
        "focus": false,
        "panel": "shared"
      }
    },
    {
      "label": "Run Python Script",
      "type": "shell",
      "command": "python",
      "args": ["${file}"],
      "group": "build",
      "presentation": {
        "echo": true,
        "reveal": "always",
        "focus": false,
        "panel": "shared"
      }
    },
    {
      "label": "Run Tests",
      "type": "shell",
      "command": "python",
      "args": ["-m", "pytest"],
      "group": "test",
      "presentation": {
        "echo": true,
        "reveal": "always",
        "focus": false,
        "panel": "shared"
      }
    }
  ]
}
```

### **Projeto Java:**
```json
{
  "version": "2.0.0",
  "tasks": [
    {
      "label": "Compile Java",
      "type": "shell",
      "command": "javac",
      "args": ["*.java"],
      "group": "build",
      "presentation": {
        "echo": true,
        "reveal": "always",
        "focus": false,
        "panel": "shared"
      }
    },
    {
      "label": "Run Java",
      "type": "shell",
      "command": "java",
      "args": ["Main"],
      "group": "build",
      "presentation": {
        "echo": true,
        "reveal": "always",
        "focus": false,
        "panel": "shared"
      }
    }
  ]
}
```

## 🚀 Tarefas avançadas

### **Tarefas com dependências:**
```json
{
  "label": "Build and Deploy",
  "dependsOrder": "sequence",
  "dependsOn": ["npm install", "npm run build", "deploy"],
  "group": "build"
}
```

### **Tarefas com variáveis:**
```json
{
  "label": "Run Current File",
  "type": "shell",
  "command": "node",
  "args": ["${file}"],
  "group": "build",
  "presentation": {
    "echo": true,
    "reveal": "always",
    "focus": false,
    "panel": "shared"
  }
}
```

### **Tarefas com condições:**
```json
{
  "label": "Build for Production",
  "type": "shell",
  "command": "npm",
  "args": ["run", "build"],
  "group": "build",
  "options": {
    "env": {
      "NODE_ENV": "production"
    }
  }
}
```

### **Tarefas com problem matchers:**
```json
{
  "label": "TypeScript Compile",
  "type": "shell",
  "command": "tsc",
  "args": ["--noEmit"],
  "group": "build",
  "problemMatcher": {
    "owner": "typescript",
    "fileLocation": ["relative", "${workspaceFolder}"],
    "pattern": {
      "regexp": "^(.*)\\((\\d+,\\d+)\\):\\s+(error|warning|info)\\s+(TS\\d+):\\s+(.*)$",
      "file": 1,
      "location": 2,
      "severity": 3,
      "code": 4,
      "message": 5
    }
  }
}
```

## 🔧 Executando tarefas

### Métodos de execução:
1. **Atalho**: `Ctrl/Cmd + Shift + B` (executa tarefa padrão)
2. **Paleta**: `Ctrl/Cmd + Shift + P` → "Tasks: Run Task"
3. **Menu**: Terminal → Run Task
4. **Explorer**: Clique direito → "Run Task"

### Configurando tarefa padrão:
```json
{
  "version": "2.0.0",
  "tasks": [
    {
      "label": "Build",
      "type": "shell",
      "command": "npm",
      "args": ["run", "build"],
      "group": {
        "kind": "build",
        "isDefault": true
      }
    }
  ]
}
```

## 🎯 Automação avançada

### **Scripts de automação:**

#### **Windows (PowerShell):**
```powershell
# deploy.ps1
param(
    [string]$Environment = "development"
)

Write-Host "Deploying to $Environment environment..."

if ($Environment -eq "production") {
    npm run build
    npm run test
    # Deploy commands
} else {
    npm run dev
}
```

#### **Unix/Linux/macOS (Bash):**
```bash
#!/bin/bash
# deploy.sh

ENVIRONMENT=${1:-development}

echo "Deploying to $ENVIRONMENT environment..."

if [ "$ENVIRONMENT" = "production" ]; then
    npm run build
    npm run test
    # Deploy commands
else
    npm run dev
fi
```

### **Tarefas com scripts:**
```json
{
  "label": "Deploy to Production",
  "type": "shell",
  "command": "./deploy.sh",
  "args": ["production"],
  "group": "build",
  "presentation": {
    "echo": true,
    "reveal": "always",
    "focus": false,
    "panel": "shared"
  }
}
```

## 🧪 Desafio Aula 7

### Exercícios básicos:

1. **Configuração do terminal**:
   ```bash
   # Abra o terminal integrado
   # Configure a fonte para Fira Code
   # Teste comandos básicos:
   ls
   pwd
   echo "Hello Terminal"
   ```

2. **Tarefa básica**:
   ```json
   // .vscode/tasks.json
   {
     "version": "2.0.0",
     "tasks": [
       {
         "label": "Hello World",
         "type": "shell",
         "command": "echo",
         "args": ["Hello from VS Code Task!"],
         "group": "build",
         "presentation": {
           "echo": true,
           "reveal": "always",
           "focus": false,
           "panel": "shared"
         }
       }
     ]
   }
   ```

3. **Múltiplos terminais**:
   ```bash
   # Abra 3 terminais diferentes
   # No primeiro: npm start
   # No segundo: npm run build
   # No terceiro: npm test
   ```

### Exercícios intermediários:

4. **Tarefas para projeto Node.js**:
   ```json
   {
     "version": "2.0.0",
     "tasks": [
       {
         "label": "Install Dependencies",
         "type": "shell",
         "command": "npm",
         "args": ["install"],
         "group": "build"
       },
       {
         "label": "Start Development Server",
         "type": "shell",
         "command": "npm",
         "args": ["start"],
         "group": "build",
         "isBackground": true
       },
       {
         "label": "Run Tests",
         "type": "shell",
         "command": "npm",
         "args": ["test"],
         "group": "test"
       }
     ]
   }
   ```

5. **Script de automação**:
   ```bash
   # Crie um arquivo setup.sh
   #!/bin/bash
   echo "Setting up development environment..."
   npm install
   npm run build
   echo "Setup complete!"
   ```

6. **Tarefa com variáveis**:
   ```json
   {
     "label": "Run Current File",
     "type": "shell",
     "command": "node",
     "args": ["${file}"],
     "group": "build",
     "presentation": {
       "echo": true,
       "reveal": "always",
       "focus": false,
       "panel": "shared"
     }
   }
   ```

### Exercícios avançados:

7. **Tarefas complexas com dependências**:
   ```json
   {
     "version": "2.0.0",
     "tasks": [
       {
         "label": "Clean",
         "type": "shell",
         "command": "rm",
         "args": ["-rf", "dist", "node_modules"],
         "group": "build"
       },
       {
         "label": "Install",
         "type": "shell",
         "command": "npm",
         "args": ["install"],
         "group": "build"
       },
       {
         "label": "Build",
         "type": "shell",
         "command": "npm",
         "args": ["run", "build"],
         "group": "build"
       },
       {
         "label": "Full Setup",
         "dependsOrder": "sequence",
         "dependsOn": ["Clean", "Install", "Build"],
         "group": "build"
       }
     ]
   }
   ```

8. **Tarefas com problem matchers**:
   ```json
   {
     "label": "TypeScript Compile",
     "type": "shell",
     "command": "tsc",
     "args": ["--noEmit"],
     "group": "build",
     "problemMatcher": {
       "owner": "typescript",
       "fileLocation": ["relative", "${workspaceFolder}"],
       "pattern": {
         "regexp": "^(.*)\\((\\d+,\\d+)\\):\\s+(error|warning|info)\\s+(TS\\d+):\\s+(.*)$",
         "file": 1,
         "location": 2,
         "severity": 3,
         "code": 4,
         "message": 5
       }
     }
   }
   ```

### Checklist de conclusão:
- [ ] Terminal integrado configurado
- [ ] Múltiplos terminais testados
- [ ] Tarefa básica criada e executada
- [ ] Tarefas para projeto Node.js configuradas
- [ ] Script de automação criado
- [ ] Tarefa com variáveis implementada
- [ ] Tarefas complexas com dependências
- [ ] Problem matchers configurados

### Dicas importantes:
- **Performance**: Não execute muitas tarefas simultaneamente
- **Organização**: Agrupe tarefas por função (build, test, deploy)
- **Documentação**: Comente tarefas complexas
- **Versionamento**: Inclua tasks.json no controle de versão

### Próximos passos:
Na próxima aula, aprenderemos sobre:
- Configurações de equipe
- Integração com ferramentas externas
- Extensões especializadas por área
- Automação avançada e CI/CD

