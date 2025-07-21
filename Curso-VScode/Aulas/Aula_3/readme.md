# ⌨️ Aula 3 – Atalhos e produtividade no VS Code

## 🎯 Atalhos essenciais por categoria

### 📁 **Navegação e Arquivos**

| Ação | Windows/Linux | Mac | Descrição |
|------|---------------|-----|-----------|
| Abrir paleta de comandos | `Ctrl + Shift + P` | `Cmd + Shift + P` | Acesso a todos os comandos |
| Ir para arquivo | `Ctrl + P` | `Cmd + P` | Busca rápida de arquivos |
| Ir para linha | `Ctrl + G` | `Cmd + G` | Navegar para linha específica |
| Ir para símbolo | `Ctrl + Shift + O` | `Cmd + Shift + O` | Buscar funções/classes |
| Mostrar/ocultar sidebar | `Ctrl + B` | `Cmd + B` | Alternar barra lateral |
| Fechar aba | `Ctrl + W` | `Cmd + W` | Fechar arquivo atual |
| Fechar todas as abas | `Ctrl + K W` | `Cmd + K W` | Fechar todos os arquivos |

### ✏️ **Edição de Código**

| Ação | Windows/Linux | Mac | Descrição |
|------|---------------|-----|-----------|
| Salvar arquivo | `Ctrl + S` | `Cmd + S` | Salvar arquivo atual |
| Salvar todos | `Ctrl + K S` | `Cmd + K S` | Salvar todos os arquivos |
| Desfazer | `Ctrl + Z` | `Cmd + Z` | Desfazer última ação |
| Refazer | `Ctrl + Y` | `Cmd + Y` | Refazer ação |
| Comentar linha | `Ctrl + /` | `Cmd + /` | Comentar/descomentar |
| Comentar bloco | `Shift + Alt + A` | `Shift + Option + A` | Comentar seleção |
| Duplicar linha | `Shift + Alt + ↓` | `Shift + Option + ↓` | Duplicar linha atual |
| Mover linha | `Alt + ↓/↑` | `Option + ↓/↑` | Mover linha para cima/baixo |
| Deletar linha | `Ctrl + Shift + K` | `Cmd + Shift + K` | Deletar linha inteira |

### 🔍 **Busca e Seleção**

| Ação | Windows/Linux | Mac | Descrição |
|------|---------------|-----|-----------|
| Buscar no arquivo | `Ctrl + F` | `Cmd + F` | Buscar texto atual |
| Buscar no projeto | `Ctrl + Shift + F` | `Cmd + Shift + F` | Buscar em todos os arquivos |
| Substituir | `Ctrl + H` | `Cmd + H` | Substituir texto |
| Substituir em projeto | `Ctrl + Shift + H` | `Cmd + Shift + H` | Substituir em todos os arquivos |
| Selecionar próxima ocorrência | `Ctrl + D` | `Cmd + D` | Selecionar próximo match |
| Selecionar todas ocorrências | `Ctrl + Shift + L` | `Cmd + Shift + L` | Selecionar todos os matches |
| Expandir seleção | `Shift + Alt + →` | `Shift + Option + →` | Expandir seleção inteligente |
| Diminuir seleção | `Shift + Alt + ←` | `Shift + Option + ←` | Diminuir seleção |

### 🖱️ **Multi-cursor e Seleção Múltipla**

| Ação | Windows/Linux | Mac | Descrição |
|------|---------------|-----|-----------|
| Adicionar cursor | `Alt + Click` | `Option + Click` | Adicionar cursor onde clicar |
| Adicionar cursor acima | `Ctrl + Alt + ↑` | `Cmd + Option + ↑` | Cursor na linha acima |
| Adicionar cursor abaixo | `Ctrl + Alt + ↓` | `Cmd + Option + ↓` | Cursor na linha abaixo |
| Selecionar coluna | `Shift + Alt + Drag` | `Shift + Option + Drag` | Seleção em coluna |
| Adicionar cursor no final | `Alt + Shift + I` | `Option + Shift + I` | Cursor no final de cada linha |

### 🖥️ **Interface e Layout**

| Ação | Windows/Linux | Mac | Descrição |
|------|---------------|-----|-----------|
| Abrir/fechar terminal | `Ctrl + `` | `Cmd + `` | Terminal integrado |
| Dividir editor | `Ctrl + \` | `Cmd + \` | Dividir editor verticalmente |
| Dividir editor horizontal | `Ctrl + K Ctrl + \` | `Cmd + K Cmd + \` | Dividir horizontalmente |
| Alternar entre editores | `Ctrl + 1/2/3` | `Cmd + 1/2/3` | Navegar entre painéis |
| Maximizar editor | `Ctrl + K Z` | `Cmd + K Z` | Modo zen (sem interface) |
| Mostrar/ocultar minimapa | `Ctrl + Shift + P` → "Toggle Minimap" | `Cmd + Shift + P` → "Toggle Minimap" | Alternar minimapa |

## 🚀 Técnicas avançadas de produtividade

### 🎯 **Multi-cursor Avançado**

#### Seleção de múltiplas linhas:
1. **Seleção sequencial**: `Ctrl + Alt + ↑/↓`
2. **Seleção por ocorrência**: `Ctrl + D` (repetir para próximo)
3. **Seleção de todas as ocorrências**: `Ctrl + Shift + L`
4. **Seleção em coluna**: `Shift + Alt + Drag`

#### Exemplo prático:
```javascript
// Antes (seleção manual)
const user1 = { name: "João", age: 25 };
const user2 = { name: "Maria", age: 30 };
const user3 = { name: "Pedro", age: 28 };

// Depois (com multi-cursor)
const user1 = { name: "João", age: 25, email: "joao@email.com" };
const user2 = { name: "Maria", age: 30, email: "maria@email.com" };
const user3 = { name: "Pedro", age: 28, email: "pedro@email.com" };
```

### 📝 **Snippets Personalizados**

#### Criando snippets:
1. `Ctrl + Shift + P` → "Preferences: Configure User Snippets"
2. Selecione a linguagem (ex: JavaScript)
3. Adicione seu snippet:

```json
{
  "Console log": {
    "prefix": "clg",
    "body": [
      "console.log('$1');"
    ],
    "description": "Console log statement"
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

#### Snippets úteis por linguagem:

**JavaScript/TypeScript:**
- `clg` → `console.log()`
- `func` → `function()`
- `arrow` → `() => {}`
- `imp` → `import`

**HTML:**
- `html` → Estrutura HTML básica
- `div` → `<div></div>`
- `link` → `<link rel="stylesheet" href="">`

**CSS:**
- `flex` → `display: flex;`
- `grid` → `display: grid;`
- `media` → `@media query`

### 🔧 **Comandos da Paleta (Ctrl/Cmd + Shift + P)**

#### Comandos essenciais:
- **"Format Document"** - Formatar documento
- **"Go to Symbol in Workspace"** - Ir para símbolo
- **"Toggle Sidebar Visibility"** - Mostrar/ocultar sidebar
- **"Developer: Reload Window"** - Recarregar VS Code
- **"Preferences: Open Settings (JSON)"** - Abrir configurações JSON
- **"Git: Initialize Repository"** - Inicializar Git
- **"Extensions: Install Extensions"** - Instalar extensões

### 🎨 **Personalização de Teclado**

#### Acessando configurações de teclado:
1. `Ctrl/Cmd + K Ctrl/Cmd + S`
2. Ou: `Ctrl/Cmd + Shift + P` → "Preferences: Open Keyboard Shortcuts"

#### Exemplo de personalização:
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
  }
]
```

## 🧩 Técnicas de produtividade avançadas

### 📊 **Organização de Workspace**

#### Dividindo o editor:
1. **Vertical**: `Ctrl/Cmd + \`
2. **Horizontal**: `Ctrl/Cmd + K Ctrl/Cmd + \`
3. **Grid**: Combine as duas técnicas

#### Navegando entre painéis:
- `Ctrl/Cmd + 1/2/3` - Ir para painel específico
- `Ctrl/Cmd + PageUp/PageDown` - Navegar entre abas
- `Ctrl/Cmd + Shift + [` - Aba anterior
- `Ctrl/Cmd + Shift + ]` - Próxima aba

### 🔍 **Busca e Substituição Avançada**

#### Busca com regex:
```regex
// Buscar números de telefone
\d{2}\s\d{4,5}-\d{4}

// Buscar emails
[\w\.-]+@[\w\.-]+\.\w+

// Buscar URLs
https?://[^\s]+
```

#### Substituição com grupos:
```regex
// Buscar: (\w+)@(\w+)\.(\w+)
// Substituir: $1 [at] $2 [dot] $3
```

### 🎯 **Atalhos de Produtividade Específicos**

#### Para desenvolvedores web:
- `Ctrl/Cmd + Shift + I` - Inspecionar elemento (com extensão)
- `Ctrl/Cmd + Shift + C` - Selecionar elemento (com extensão)
- `Ctrl/Cmd + Shift + R` - Recarregar página (Live Server)

#### Para debug:
- `F5` - Iniciar debug
- `F9` - Toggle breakpoint
- `F10` - Step over
- `F11` - Step into
- `Shift + F11` - Step out

## 🧪 Desafio Aula 3

### Exercícios básicos:

1. **Multi-cursor básico**:
   ```javascript
   // Use multi-cursor para adicionar "const" em todas as linhas:
   user1 = "João";
   user2 = "Maria";
   user3 = "Pedro";
   ```

2. **Seleção múltipla**:
   ```html
   <!-- Use Ctrl+D para selecionar todas as tags <div> e renomeie para <section> -->
   <div class="container">
     <div class="header">
       <div class="title">Título</div>
     </div>
     <div class="content">
       <div class="item">Item 1</div>
       <div class="item">Item 2</div>
     </div>
   </div>
   ```

3. **Comandos da paleta**:
   - Abra a paleta de comandos
   - Digite "format" e formate um documento
   - Digite "fold" e dobre todo o código
   - Digite "reload" e recarregue a janela

### Exercícios intermediários:

4. **Criação de snippets**:
   - Crie um snippet para função arrow
   - Crie um snippet para console.log com timestamp
   - Crie um snippet para estrutura HTML básica

5. **Personalização de teclado**:
   - Mapeie `Ctrl + Shift + T` para abrir terminal
   - Mapeie `Ctrl + Shift + D` para iniciar debug
   - Mapeie `Ctrl + Shift + R` para recarregar janela

6. **Workspace organizado**:
   - Divida o editor em 3 painéis
   - Abra diferentes tipos de arquivo em cada painel
   - Navegue entre os painéis usando atalhos

### Exercícios avançados:

7. **Busca e substituição avançada**:
   ```javascript
   // Use regex para encontrar e substituir:
   // Buscar: function (\w+)\(\) \{
   // Substituir: const $1 = () => {
   
   function getUser() {
     return user;
   }
   
   function setUser() {
     user = newUser;
   }
   ```

8. **Projeto completo com atalhos**:
   - Crie um projeto web simples
   - Use multi-cursor para criar múltiplos elementos
   - Use snippets para estruturas repetitivas
   - Configure atalhos personalizados
   - Use busca e substituição para refatoração

### Checklist de conclusão:
- [ ] Multi-cursor dominado
- [ ] Atalhos básicos memorizados
- [ ] Paleta de comandos explorada
- [ ] Snippets criados
- [ ] Teclado personalizado
- [ ] Workspace organizado
- [ ] Busca avançada testada
- [ ] Produtividade aumentada

### Dicas de memorização:
- **Pratique diariamente**: Use os atalhos em projetos reais
- **Comece pelos básicos**: Foque nos atalhos mais usados primeiro
- **Personalize gradualmente**: Adicione atalhos conforme necessário
- **Use mnemônicos**: Associe atalhos a ações lógicas

### Próximos passos:
Na próxima aula, aprenderemos sobre:
- Debugging e troubleshooting
- Integração com Git
- Configurações avançadas
- Extensões especializadas

