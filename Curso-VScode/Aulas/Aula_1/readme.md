# Aula 1 – Introdução e configurações iniciais

## 1️⃣ Instalação do VS Code

### Baixando o VS Code
- **Site oficial**: https://code.visualstudio.com
- **Sistemas suportados**: Windows, macOS, Linux
- **Versão**: Sempre baixe a versão mais recente para ter as últimas funcionalidades

### Processo de instalação

#### Windows:
1. Baixe o instalador `.exe` do site oficial
2. Execute o arquivo baixado
3. Siga o assistente de instalação
4. **Dica importante**: Marque a opção "Add to PATH" para usar o VS Code pelo terminal

#### macOS:
1. Baixe o arquivo `.dmg`
2. Arraste o VS Code para a pasta Applications
3. Execute pela primeira vez para completar a instalação

#### Linux:
1. Baixe o arquivo `.deb` (Ubuntu/Debian) ou `.rpm` (Fedora)
2. Instale via terminal: `sudo dpkg -i code_*.deb`
3. Ou use o snap: `sudo snap install code --classic`

## 2️⃣ Primeira execução e interface

### Abrindo o VS Code
- **Windows/Linux**: `Ctrl + Shift + P`
- **macOS**: `Cmd + Shift + P`
- **Atalho**: `code .` no terminal (após adicionar ao PATH)

### Interface principal
- **Sidebar esquerda**: Explorador de arquivos, busca, controle de versão
- **Editor central**: Área de edição de código
- **Sidebar direita**: Extensões, configurações
- **Barra inferior**: Terminal integrado, problemas, saída

## 3️⃣ Configurações básicas

### Acessando configurações
- **Windows/Linux**: `Ctrl + ,`
- **macOS**: `Cmd + ,`
- **Comando**: `Ctrl/Cmd + Shift + P` → "Preferences: Open Settings"

### Configurações essenciais

| Configuração | Descrição | Valor Recomendado |
|--------------|-----------|-------------------|
| `editor.fontSize` | Tamanho da fonte | 14 |
| `editor.tabSize` | Espaços por tab | 2 ou 4 |
| `editor.formatOnSave` | Auto formatar ao salvar | true |
| `files.autoSave` | Auto salvar arquivos | "afterDelay" |
| `editor.minimap.enabled` | Mostra mini mapa lateral | true |
| `editor.wordWrap` | Quebra de linha automática | "on" |
| `editor.rulers` | Linhas guia | [80, 120] |
| `editor.bracketPairColorization.enabled` | Colorização de parênteses | true |
| `editor.guides.bracketPairs` | Guias de parênteses | true |

## 4️⃣ Configuração JSON avançada

### Editando configurações em JSON
1. Abra as configurações (`Ctrl/Cmd + ,`)
2. Clique no ícone `{}` no canto superior direito
3. Edite diretamente o arquivo `settings.json`

### Exemplo de configuração completa:

```json
{
  "editor.fontSize": 14,
  "editor.tabSize": 2,
  "editor.formatOnSave": true,
  "files.autoSave": "afterDelay",
  "editor.minimap.enabled": true,
  "editor.wordWrap": "on",
  "editor.rulers": [80, 120],
  "editor.bracketPairColorization.enabled": true,
  "editor.guides.bracketPairs": true,
  "editor.suggestSelection": "first",
  "editor.acceptSuggestionOnEnter": "on",
  "editor.tabCompletion": "on",
  "editor.renderWhitespace": "boundary",
  "editor.insertSpaces": true,
  "editor.detectIndentation": true,
  "files.trimTrailingWhitespace": true,
  "files.insertFinalNewline": true,
  "workbench.colorTheme": "Default Dark+",
  "workbench.iconTheme": "vs-seti"
}
```

## 5️⃣ Extensões essenciais para iniciantes

### Instalando extensões
- **Atalho**: `Ctrl/Cmd + Shift + X`
- **Busca**: Digite o nome da extensão
- **Instalação**: Clique em "Install"

### Extensões recomendadas:
1. **Auto Rename Tag** - Para HTML/XML
2. **Bracket Pair Colorizer** - Colorização de parênteses
3. **GitLens** - Integração avançada com Git
4. **Live Server** - Servidor local para desenvolvimento web
5. **Prettier** - Formatador de código
6. **ES7+ React/Redux/React-Native snippets** - Para React
7. **Python** - Para desenvolvimento Python
8. **C/C++** - Para desenvolvimento C/C++

## 6️⃣ Atalhos de teclado básicos

### Navegação
- `Ctrl/Cmd + P` - Buscar arquivos
- `Ctrl/Cmd + Shift + P` - Paleta de comandos
- `Ctrl/Cmd + B` - Mostrar/ocultar sidebar
- `Ctrl/Cmd + J` - Mostrar/ocultar terminal

### Edição
- `Ctrl/Cmd + D` - Selecionar próxima ocorrência
- `Ctrl/Cmd + Shift + L` - Selecionar todas as ocorrências
- `Alt + ↑/↓` - Mover linha para cima/baixo
- `Shift + Alt + ↑/↓` - Duplicar linha
- `Ctrl/Cmd + /` - Comentar/descomentar linha

### Arquivos
- `Ctrl/Cmd + S` - Salvar
- `Ctrl/Cmd + Shift + S` - Salvar como
- `Ctrl/Cmd + N` - Novo arquivo
- `Ctrl/Cmd + W` - Fechar arquivo

## 7️⃣ Terminal integrado

### Abrindo o terminal
- `Ctrl/Cmd + `` (backtick)
- `Ctrl/Cmd + Shift + `` (novo terminal)
- Menu: Terminal → New Terminal

### Comandos úteis no terminal
```bash
# Navegar entre pastas
cd nome-da-pasta
cd ..

# Listar arquivos
ls (Linux/Mac) ou dir (Windows)

# Criar pasta
mkdir nome-da-pasta

# Criar arquivo
touch nome-do-arquivo.txt
```

## 🧪 Desafio Aula 1

### Exercícios práticos:

1. **Instalação e configuração básica**:
   - Instale o VS Code seguindo as instruções acima
   - Configure as configurações essenciais
   - Teste os atalhos de teclado básicos

2. **Criação de projeto de teste**:
   ```bash
   # No terminal do VS Code
   mkdir meu-primeiro-projeto
   cd meu-primeiro-projeto
   code .
   ```

3. **Criação de arquivos de teste**:
   - Crie um arquivo `index.html`
   - Crie um arquivo `style.css`
   - Crie um arquivo `script.js`
   - Teste a formatação automática

4. **Explorando a interface**:
   - Use o minimapa para navegar no código
   - Teste a busca de arquivos (`Ctrl/Cmd + P`)
   - Explore a paleta de comandos (`Ctrl/Cmd + Shift + P`)
   - Teste o terminal integrado

5. **Instalação de extensões**:
   - Instale pelo menos 3 extensões recomendadas
   - Teste a funcionalidade de cada uma

### Checklist de conclusão:
- [ ] VS Code instalado e funcionando
- [ ] Configurações básicas aplicadas
- [ ] Atalhos de teclado testados
- [ ] Terminal integrado funcionando
- [ ] Extensões instaladas
- [ ] Projeto de teste criado
- [ ] Formatação automática testada

### Próximos passos:
Na próxima aula, aprenderemos sobre:
- Estrutura de pastas e organização de projetos
- Configurações específicas por linguagem
- Debugging básico
- Integração com Git