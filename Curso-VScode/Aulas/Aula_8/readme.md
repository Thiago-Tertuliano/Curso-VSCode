# 🐞 Aula 8 – Debug avançado e extensões

## 🚀 Debug avançado

### Interface de Debug Completa
O VS Code oferece uma interface de debug poderosa com múltiplos painéis:

- **Variables**: Variáveis locais e globais
- **Watch**: Expressões personalizadas para monitorar
- **Call Stack**: Pilha de chamadas da aplicação
- **Breakpoints**: Lista de todos os breakpoints
- **Debug Console**: Console para avaliar expressões
- **Loaded Scripts**: Scripts carregados (Chrome/Node.js)

### Funcionalidades avançadas:

#### **Breakpoints condicionais:**
1. Clique direito no breakpoint
2. Selecione "Edit Breakpoint"
3. Adicione condição: `x > 10` ou `user.isAdmin`
4. Ou logpoint: `console.log('User clicked:', user.name)`

#### **Watch expressions:**
- Adicione expressões no painel "Watch"
- Exemplos: `user.name`, `array.length`, `JSON.stringify(obj)`
- Expressões são reavaliadas a cada passo

#### **Debug Console:**
```javascript
// Execute código durante o debug
user.name = "Novo Nome"
console.log(user)
JSON.stringify(user, null, 2)
```

## 🔧 Configurações avançadas de debug

### **Configuração multi-ambiente (launch.json):**
```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Debug Node.js",
      "type": "node",
      "request": "launch",
      "program": "${workspaceFolder}/src/index.js",
      "env": {
        "NODE_ENV": "development",
        "DEBUG": "app:*"
      },
      "console": "integratedTerminal",
      "skipFiles": [
        "<node_internals>/**"
      ]
    },
    {
      "name": "Debug Chrome",
      "type": "chrome",
      "request": "launch",
      "url": "http://localhost:3000",
      "webRoot": "${workspaceFolder}",
      "sourceMaps": true,
      "userDataDir": "${workspaceFolder}/.vscode/chrome-debug-profile"
    },
    {
      "name": "Attach to Process",
      "type": "node",
      "request": "attach",
      "port": 9229,
      "restart": true,
      "localRoot": "${workspaceFolder}",
      "remoteRoot": "/app"
    }
  ],
  "compounds": [
    {
      "name": "Debug Full Stack",
      "configurations": ["Debug Node.js", "Debug Chrome"]
    }
  ]
}
```

### **Configurações específicas por linguagem:**

#### **JavaScript/TypeScript:**
```json
{
  "name": "Debug TypeScript",
  "type": "node",
  "request": "launch",
  "program": "${workspaceFolder}/src/index.ts",
  "preLaunchTask": "tsc: build - tsconfig.json",
  "outFiles": ["${workspaceFolder}/dist/**/*.js"],
  "sourceMaps": true,
  "resolveSourceMapLocations": [
    "${workspaceFolder}/**",
    "!**/node_modules/**"
  ]
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
  "justMyCode": true,
  "env": {
    "PYTHONPATH": "${workspaceFolder}"
  },
  "args": [],
  "cwd": "${workspaceFolder}"
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
  "console": "internalConsole",
  "stopAtEntry": false,
  "serverReadyAction": {
    "action": "openExternally",
    "pattern": "\\bNow listening on:\\s+(https?://\\S+)"
  }
}
```

## 🧩 Extensões especializadas para debug

### **Extensões por linguagem:**

#### **JavaScript/TypeScript:**
- **Debugger for Chrome**: Debug JavaScript no Chrome
- **Debugger for Firefox**: Debug no Firefox
- **Debugger for Edge**: Debug no Microsoft Edge
- **Jest Runner**: Debug testes Jest
- **Thunder Client**: Testar APIs REST

#### **Python:**
- **Python**: Debug completo para Python
- **Pylance**: IntelliSense avançado
- **Python Test Explorer**: Debug testes
- **Python Docstring Generator**: Documentação

#### **C/C++:**
- **C/C++**: Debug para C e C++
- **CMake Tools**: Debug projetos CMake
- **C++ TestMate**: Debug testes C++

#### **Java:**
- **Extension Pack for Java**: Debug completo
- **Spring Boot Extension Pack**: Debug Spring Boot
- **Maven for Java**: Debug projetos Maven

#### **PHP:**
- **PHP Debug**: Debug com XDebug
- **PHP Intelephense**: IntelliSense avançado
- **PHP Server**: Servidor local para debug

### **Extensões de produtividade para debug:**

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

#### **Bracket Pair Colorizer 2:**
- Colorização de parênteses
- Facilita navegação no código

#### **Bookmarks:**
- Marcar linhas importantes
- Navegação rápida durante debug

#### **Todo Tree:**
- Gerenciar TODOs e FIXMEs
- Útil para identificar pontos de debug

## 🔍 Técnicas avançadas de debug

### **Debugging de aplicações web:**

#### **Debugging React:**
```json
{
  "name": "Debug React",
  "type": "chrome",
  "request": "launch",
  "url": "http://localhost:3000",
  "webRoot": "${workspaceFolder}/src",
  "sourceMapPathOverrides": {
    "webpack:///src/*": "${webRoot}/*"
  },
  "userDataDir": "${workspaceFolder}/.vscode/chrome-debug-profile"
}
```

#### **Debugging Vue.js:**
```json
{
  "name": "Debug Vue",
  "type": "chrome",
  "request": "launch",
  "url": "http://localhost:8080",
  "webRoot": "${workspaceFolder}/src",
  "sourceMapPathOverrides": {
    "webpack:///src/*": "${webRoot}/*"
  }
}
```

### **Debugging de APIs:**

#### **Debugging Node.js API:**
```json
{
  "name": "Debug API",
  "type": "node",
  "request": "launch",
  "program": "${workspaceFolder}/server.js",
  "env": {
    "NODE_ENV": "development",
    "PORT": "3000",
    "DEBUG": "app:*"
  },
  "console": "integratedTerminal",
  "restart": true,
  "protocol": "inspector"
}
```

#### **Debugging com REST Client:**
```http
### Test API
POST http://localhost:3000/api/users
Content-Type: application/json

{
  "name": "João",
  "email": "joao@email.com"
}
```

### **Debugging de aplicações móveis:**

#### **React Native:**
```json
{
  "name": "Debug React Native",
  "type": "reactnative",
  "request": "launch",
  "platform": "android",
  "target": "device",
  "sourceMaps": true
}
```

#### **Flutter:**
```json
{
  "name": "Debug Flutter",
  "type": "dart",
  "request": "launch",
  "program": "lib/main.dart",
  "args": []
}
```

## 🎯 Debugging específico por tipo de problema

### **Debugging de performance:**
```json
{
  "name": "Debug Performance",
  "type": "node",
  "request": "launch",
  "program": "${workspaceFolder}/app.js",
  "runtimeArgs": ["--inspect"],
  "env": {
    "NODE_OPTIONS": "--max-old-space-size=4096"
  }
}
```

### **Debugging de memória:**
```json
{
  "name": "Debug Memory",
  "type": "node",
  "request": "launch",
  "program": "${workspaceFolder}/app.js",
  "runtimeArgs": ["--inspect", "--expose-gc"],
  "env": {
    "NODE_OPTIONS": "--max-old-space-size=2048"
  }
}
```

### **Debugging de testes:**
```json
{
  "name": "Debug Tests",
  "type": "node",
  "request": "launch",
  "program": "${workspaceFolder}/node_modules/.bin/jest",
  "args": ["--runInBand", "--no-cache"],
  "console": "integratedTerminal",
  "env": {
    "NODE_ENV": "test"
  }
}
```

## 🧪 Desafio Aula 8

### Exercícios básicos:

1. **Configuração básica de debug**:
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

2. **Código para testar debug**:
   ```javascript
   // app.js
   function calculateSum(numbers) {
     let total = 0;
     for (let i = 0; i < numbers.length; i++) {
       total += numbers[i];
       console.log(`Adding ${numbers[i]}, total: ${total}`);
     }
     return total;
   }
   
   const numbers = [1, 2, 3, 4, 5];
   const result = calculateSum(numbers);
   console.log(`Final result: ${result}`);
   ```

3. **Breakpoints condicionais**:
   ```javascript
   // debug-test.js
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

### Exercícios intermediários:

4. **Debugging web com Chrome**:
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

5. **Configuração multi-ambiente**:
   ```json
   {
     "version": "0.2.0",
     "configurations": [
       {
         "name": "Debug Development",
         "type": "node",
         "request": "launch",
         "program": "${workspaceFolder}/app.js",
         "env": {
           "NODE_ENV": "development",
           "DEBUG": "app:*"
         }
       },
       {
         "name": "Debug Production",
         "type": "node",
         "request": "launch",
         "program": "${workspaceFolder}/app.js",
         "env": {
           "NODE_ENV": "production"
         }
       }
     ]
   }
   ```

6. **Watch expressions avançadas**:
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

### Exercícios avançados:

7. **Debugging de API REST**:
   ```javascript
   // api-server.js
   const express = require('express');
   const app = express();
   
   app.use(express.json());
   
   const users = [
     { id: 1, name: "João", email: "joao@email.com" },
     { id: 2, name: "Maria", email: "maria@email.com" }
   ];
   
   app.get('/api/users', (req, res) => {
     console.log('GET /api/users');
     res.json(users);
   });
   
   app.post('/api/users', (req, res) => {
     const newUser = {
       id: users.length + 1,
       name: req.body.name,
       email: req.body.email
     };
     
     users.push(newUser);
     console.log('POST /api/users', newUser);
     res.status(201).json(newUser);
   });
   
   app.listen(3000, () => {
     console.log('Server running on port 3000');
   });
   ```

8. **Configuração de debug complexa**:
   ```json
   {
     "version": "0.2.0",
     "configurations": [
       {
         "name": "Debug Backend",
         "type": "node",
         "request": "launch",
         "program": "${workspaceFolder}/server.js",
         "env": {
           "NODE_ENV": "development",
           "PORT": "3000"
         },
         "console": "integratedTerminal"
       },
       {
         "name": "Debug Frontend",
         "type": "chrome",
         "request": "launch",
         "url": "http://localhost:3000",
         "webRoot": "${workspaceFolder}/public",
         "sourceMaps": true
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

### Checklist de conclusão:
- [ ] Configuração básica de debug criada
- [ ] Breakpoints condicionais testados
- [ ] Watch expressions configuradas
- [ ] Debug Console utilizado
- [ ] Extensão de debug instalada
- [ ] Configuração multi-ambiente implementada
- [ ] Debugging web testado
- [ ] Debugging de API testado

### Dicas importantes:
- **Performance**: Não deixe muitos breakpoints ativos
- **Organização**: Use nomes descritivos para configurações
- **Documentação**: Comente configurações complexas
- **Versionamento**: Inclua launch.json no controle de versão

### Próximos passos:
Na próxima aula, aprenderemos sobre:
- Configurações de equipe
- Integração com ferramentas externas
- Extensões especializadas por área
- Automação avançada e CI/CD

