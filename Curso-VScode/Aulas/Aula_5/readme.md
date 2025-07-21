# 🔗 Aula 5 – Integração com Git e Debug

## 🗂️ Git no VS Code

### Integração nativa
O VS Code já vem com integração nativa com Git, oferecendo uma interface visual completa para controle de versão.

### Interface do Git no VS Code:
- **Source Control Panel**: `Ctrl + Shift + G` ou ícone de ramo na sidebar
- **Changes**: Lista de arquivos modificados
- **Staged Changes**: Arquivos prontos para commit
- **Unstaged Changes**: Arquivos não adicionados
- **Branches**: Gerenciamento de branches
- **Remotes**: Configuração de repositórios remotos

### Operações básicas do Git:

#### **Commit e Push:**
1. **Adicionar arquivos**: Clique no `+` ao lado do arquivo
2. **Escrever mensagem**: Campo "Message" no Source Control
3. **Fazer commit**: Clique em "✓" (Commit)
4. **Push**: Clique em "..." → "Push"

#### **Pull e Sync:**
- **Pull**: Clique em "..." → "Pull"
- **Sync**: Clique em "Sync Changes" (sincroniza push/pull)
- **Fetch**: Clique em "..." → "Fetch"

#### **Branches:**
- **Criar branch**: Clique no nome da branch → "Create new branch"
- **Mudar branch**: Clique no nome da branch → selecione
- **Merge**: Clique em "..." → "Branch" → "Merge branch"

## 🛠️ Configurações Git avançadas

### Configurações básicas:
```json
{
  "git.autofetch": true,
  "git.confirmSync": false,
  "git.enableSmartCommit": true,
  "git.enableCommitSigning": false,
  "git.autoStash": true,
  "git.allowNoVerifyCommit": false,
  "git.ignoreSubmodules": false,
  "git.showPushSuccessNotification": true
}
```

### Configurações avançadas:
```json
{
  "git.decorations.enabled": true,
  "git.decorations.colors": {
    "modified": "#FFA500",
    "added": "#4CAF50",
    "deleted": "#F44336",
    "untracked": "#9C27B0"
  },
  "git.mergeEditor": true,
  "git.diffEditor.ignoreTrimWhitespace": "auto",
  "git.diffEditor.renderSideBySide": true,
  "git.diffEditor.codeLens": true
}
```

### Configurações de commit:
```json
{
  "git.inputValidation": "always",
  "git.inputValidationLength": 72,
  "git.inputValidationSubjectLength": 50,
  "git.autoRepositoryDetection": true,
  "git.autoStash": true,
  "git.confirmSync": false,
  "git.enableSmartCommit": true
}
```

## 🔧 Extensões Git essenciais

### **GitLens** (Recomendado)
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

### **Git Graph**
- **Funcionalidades**: Visualização gráfica do Git
- **Como usar**: `Ctrl + Shift + P` → "Git Graph: View Git Graph"

### **Git History**
- **Funcionalidades**: Histórico de mudanças
- **Como usar**: Clique direito no arquivo → "Git: View File History"

### **Git Blame**
- **Funcionalidades**: Ver quem modificou cada linha
- **Como usar**: `Ctrl + Shift + P` → "Git: Toggle File Blame"

## 🐞 Debugging no VS Code

### Interface de Debug
- **Acesso**: `Ctrl + Shift + D` ou ícone de inseto
- **Breakpoints**: Clique na margem esquerda do editor
- **Variables**: Painel para ver variáveis
- **Watch**: Adicionar expressões para monitorar
- **Call Stack**: Pilha de chamadas
- **Breakpoints**: Lista de breakpoints

### Atalhos de Debug:
- **F5**: Iniciar/continuar debug
- **F9**: Toggle breakpoint
- **F10**: Step over (próxima linha)
- **F11**: Step into (entrar na função)
- **Shift + F11**: Step out (sair da função)
- **Ctrl + Shift + F5**: Restart
- **Shift + F5**: Stop

## 🔧 Configurações de Debug por linguagem

### **JavaScript/Node.js:**
```json
// .vscode/launch.json
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Launch Node.js",
      "type": "node",
      "request": "launch",
      "program": "${workspaceFolder}/src/index.js",
      "env": {
        "NODE_ENV": "development"
      },
      "console": "integratedTerminal",
      "skipFiles": [
        "<node_internals>/**"
      ]
    },
    {
      "name": "Attach to Process",
      "type": "node",
      "request": "attach",
      "port": 9229,
      "restart": true
    }
  ]
}
```

### **Python:**
```json
{
  "name": "Debug Python",
  "type": "python",
  "request": "launch",
  "program": "${workspaceFolder}/main.py",
  "console": "integratedTerminal",
  "justMyCode": true,
  "env": {
    "PYTHONPATH": "${workspaceFolder}"
  },
  "args": []
}
```

### **C#:**
```json
{
  "name": "Debug C#",
  "type": "coreclr",
  "request": "launch",
  "preLaunchTask": "build",
  "program": "${workspaceFolder}/bin/Debug/net6.0/MyApp.dll",
  "args": [],
  "cwd": "${workspaceFolder}",
  "console": "internalConsole",
  "stopAtEntry": false
}
```

### **Java:**
```json
{
  "name": "Debug Java",
  "type": "java",
  "request": "launch",
  "mainClass": "com.example.MainClass",
  "projectName": "my-project",
  "args": [],
  "vmArgs": "-Xmx512m"
}
```

## 🔍 Debugging avançado

### **Conditional Breakpoints:**
1. Clique direito no breakpoint
2. Selecione "Edit Breakpoint"
3. Adicione condição: `x > 10`
4. Ou logpoint: `console.log('x =', x)`

### **Watch Expressions:**
- Adicione expressões no painel "Watch"
- Exemplos: `user.name`, `array.length`, `obj.property`

### **Debug Console:**
- Execute código durante o debug
- Acesse variáveis: `user.name`
- Avalie expressões: `JSON.stringify(obj)`

### **Logpoints:**
```javascript
// Em vez de console.log, use logpoints
// Clique direito no breakpoint → "Add Logpoint"
// Digite: User clicked: {user.name}
```

## 🧪 Debugging específico por tipo de projeto

### **Debugging Web (Chrome):**
```json
{
  "name": "Launch Chrome",
  "type": "chrome",
  "request": "launch",
  "url": "http://localhost:3000",
  "webRoot": "${workspaceFolder}",
  "sourceMaps": true,
  "userDataDir": "${workspaceFolder}/.vscode/chrome-debug-profile"
}
```

### **Debugging React:**
```json
{
  "name": "Launch Chrome (React)",
  "type": "chrome",
  "request": "launch",
  "url": "http://localhost:3000",
  "webRoot": "${workspaceFolder}/src",
  "sourceMapPathOverrides": {
    "webpack:///src/*": "${webRoot}/*"
  }
}
```

### **Debugging API (Node.js):**
```json
{
  "name": "Debug API",
  "type": "node",
  "request": "launch",
  "program": "${workspaceFolder}/server.js",
  "env": {
    "NODE_ENV": "development",
    "PORT": "3000"
  },
  "console": "integratedTerminal",
  "restart": true,
  "protocol": "inspector"
}
```

## 🔧 Configurações de debug avançadas

### **Multi-target debugging:**
```json
{
  "name": "Debug Full Stack",
  "configurations": [
    {
      "name": "Debug Backend",
      "type": "node",
      "request": "launch",
      "program": "${workspaceFolder}/backend/server.js"
    },
    {
      "name": "Debug Frontend",
      "type": "chrome",
      "request": "launch",
      "url": "http://localhost:3000"
    }
  ],
  "compounds": [
    {
      "name": "Debug Full Stack",
      "configurations": ["Debug Backend", "Debug Frontend"]
    }
  ]
}
```

### **Debugging com variáveis de ambiente:**
```json
{
  "name": "Debug with Env",
  "type": "node",
  "request": "launch",
  "program": "${workspaceFolder}/app.js",
  "envFile": "${workspaceFolder}/.env",
  "env": {
    "DEBUG": "app:*",
    "NODE_ENV": "development"
  }
}
```

## 🧪 Desafio Aula 5

### Exercícios básicos:

1. **Configuração Git básica**:
   ```bash
   # Inicialize um repositório Git
   git init
   
   # Crie alguns arquivos de teste
   echo "console.log('Hello World');" > app.js
   echo "# Meu Projeto" > README.md
   
   # Use o VS Code para fazer commit
   # 1. Abra o Source Control (Ctrl + Shift + G)
   # 2. Adicione os arquivos (+)
   # 3. Escreva mensagem de commit
   # 4. Faça o commit (✓)
   ```

2. **Configuração de debug básica**:
   ```javascript
   // app.js
   function calculateSum(a, b) {
     const result = a + b;
     console.log(`Sum: ${a} + ${b} = ${result}`);
     return result;
   }
   
   const numbers = [1, 2, 3, 4, 5];
   let total = 0;
   
   for (let i = 0; i < numbers.length; i++) {
     total = calculateSum(total, numbers[i]);
   }
   
   console.log(`Total: ${total}`);
   ```

3. **Configuração de debug**:
   ```json
   // .vscode/launch.json
   {
     "version": "0.2.0",
     "configurations": [
       {
         "name": "Debug Node.js",
         "type": "node",
         "request": "launch",
         "program": "${workspaceFolder}/app.js",
         "console": "integratedTerminal"
       }
     ]
   }
   ```

### Exercícios intermediários:

4. **Debugging com breakpoints condicionais**:
   ```javascript
   // debug-example.js
   function processUser(user) {
     if (user.age < 18) {
       console.log("User is underage");
       return false;
     }
     
     if (user.balance < 100) {
       console.log("Insufficient balance");
       return false;
     }
     
     console.log("User approved");
     return true;
   }
   
   const users = [
     { name: "João", age: 25, balance: 500 },
     { name: "Maria", age: 16, balance: 200 },
     { name: "Pedro", age: 30, balance: 50 }
   ];
   
   users.forEach(user => {
     const approved = processUser(user);
     console.log(`${user.name}: ${approved ? 'Approved' : 'Rejected'}`);
   });
   ```

5. **Git branching e merge**:
   ```bash
   # Crie uma nova branch
   git checkout -b feature/new-feature
   
   # Faça algumas mudanças
   echo "// Nova funcionalidade" >> app.js
   
   # Commit na nova branch
   git add app.js
   git commit -m "Add new feature"
   
   # Volte para main e faça merge
   git checkout main
   git merge feature/new-feature
   ```

6. **Debugging web com Chrome**:
   ```html
   <!-- index.html -->
   <!DOCTYPE html>
   <html>
   <head>
       <title>Debug Test</title>
   </head>
   <body>
       <h1>Debug Test</h1>
       <button onclick="testFunction()">Test</button>
       <div id="output"></div>
       
       <script>
       function testFunction() {
           const output = document.getElementById('output');
           const numbers = [1, 2, 3, 4, 5];
           let sum = 0;
           
           for (let i = 0; i < numbers.length; i++) {
               sum += numbers[i];
               output.innerHTML += `<p>Sum: ${sum}</p>`;
           }
       }
       </script>
   </body>
   </html>
   ```

### Exercícios avançados:

7. **Debugging complexo com watch**:
   ```javascript
   // complex-debug.js
   class UserManager {
     constructor() {
       this.users = [];
       this.activeUser = null;
     }
     
     addUser(user) {
       this.users.push(user);
       console.log(`User added: ${user.name}`);
     }
     
     findUser(name) {
       const user = this.users.find(u => u.name === name);
       if (user) {
         this.activeUser = user;
         return user;
       }
       return null;
     }
     
     updateUser(name, updates) {
       const user = this.findUser(name);
       if (user) {
         Object.assign(user, updates);
         console.log(`User updated: ${name}`);
       }
     }
   }
   
   const manager = new UserManager();
   manager.addUser({ name: "João", age: 25 });
   manager.addUser({ name: "Maria", age: 30 });
   
   manager.findUser("João");
   manager.updateUser("João", { age: 26 });
   ```

8. **Git workflow completo**:
   ```bash
   # 1. Clone um repositório ou crie um novo
   git init
   
   # 2. Configure o VS Code para o projeto
   # Crie .vscode/settings.json com configurações específicas
   
   # 3. Desenvolva com branches
   git checkout -b feature/user-authentication
   # Faça mudanças e commits
   
   # 4. Use o VS Code para resolver conflitos
   git checkout main
   git merge feature/user-authentication
   
   # 5. Configure debug para o projeto
   # Crie .vscode/launch.json
   
   # 6. Teste o debugging
   # Coloque breakpoints e execute
   ```

### Checklist de conclusão:
- [ ] Repositório Git configurado
- [ ] Commits feitos pelo VS Code
- [ ] Branches criadas e gerenciadas
- [ ] Debug configurado para projeto
- [ ] Breakpoints testados
- [ ] Watch expressions configuradas
- [ ] Debugging web testado
- [ ] Git workflow dominado

### Dicas importantes:
- **Git**: Use mensagens de commit descritivas
- **Debug**: Use logpoints em vez de console.log
- **Performance**: Não deixe muitos breakpoints ativos
- **Segurança**: Não commite informações sensíveis

### Próximos passos:
Na próxima aula, aprenderemos sobre:
- Extensões especializadas por área
- Automação e scripts
- Configurações de equipe
- Integração com ferramentas externas

