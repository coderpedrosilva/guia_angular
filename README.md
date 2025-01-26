# Guia Angular

# Configuração do Ambiente

Este guia detalha como configurar o ambiente necessário para trabalhar com o Angular, incluindo a instalação do Node.js, NVM, Angular CLI, além de soluções para problemas comuns.

## 1. Instalando o Node.js

### Método 1: Instalação Direta

1. Acesse o site oficial do Node.js: https://nodejs.org.
   
2. Baixe a versão **LTS (Long-Term Support)** recomendada.
   
3. Execute o instalador e siga os passos:
    - Aceite os termos de licença.
    - Escolha as opções padrão.
    - Conclua a instalação.
  
4. Verifique a instalação:
```
node -v
npm -v
```
5. Atualize o npm (se necessário):
```
npm install -g npm
```
### Método 2: Gerenciamento de Versões com NVM

O NVM permite gerenciar várias versões do Node.js, ideal para projetos com diferentes requisitos.

1. Baixe o instalador do NVM:
    - Acesse: https://github.com/coreybutler/nvm-windows/releases ou [SourceForge - nvm-setup.exe ](https://sourceforge.net/projects/nvm-for-windows.mirror/files/1.2.2/nvm-setup.exe/download)
    - Baixe e execute o arquivo `nvm-setup.exe`.
2. Instale o NVM seguindo as instruções do instalador.
   
3. Verifique a instalação:
```
nvm --version
```
**Usando o NVM**

1. Liste as versões disponíveis:
```
nvm list available
```
2. Liste as versões instaladas:
```
nvm list 
```
3. Instale a versão necessária:
```
nvm install 18.20.4 
```
4. Para garantir que as versões do Node.js sejam trocadas corretamente usando o NVM no Windows, o **Path** deve incluir os seguintes diretórios (substitua `<User>` pelo nome do seu usuário no Windows):

```
C:\Users\<User>\AppData\Roaming\npm
```
e
```
C:\Users\<User>\AppData\Roaming\nvm\nodejs
```
5. Ative a versão instalada:
```
nvm use 18.20.4 
```
6. Verifique a versão ativa:
```
node -v
```
## 2. Instalando o Angular CLI

1. Instale o Angular CLI na versão desejada:
```
npm install -g @angular/cli@17.3.9
```
2. Verifique a instalação:
```
ng version
```
3. Confirme o caminho do executável:
```
where ng
```
## 3. Listando e Alterando Versões do Angular CLI
### 3.1 Listar Versões Disponíveis
- Listar todas as versões do Angular CLI:
```
npm view @angular/cli versions
```
- Verificar uma versão específica:
```
npm view @angular/cli@17.3.9 version
```
### 3.2 Alterar a Versão do Angular CLI
1. Desinstalar a versão atual:
```
npm uninstall -g @angular/cli
```
2. Instalar uma nova versão:
```
npm install -g @angular/cli@17.3.9
```
3. Verificar a versão instalada:
```
ng version
```
## 4. Solução de Problemas
### 4.1 Reinstalar o Node.js e o Angular CLI

Se problemas persistirem, reinstale o Node.js e o Angular CLI:

1. Desinstale o Node.js e exclua as pastas residuais:
```
C:\Program Files\nodejs
C:\Users\<User>\AppData\Roaming\npm
C:\Users\<User>\AppData\Roaming\npm-cache
C:\Users\proge\AppData\Roaming\nvm
```
2. Reinstale o Node.js e também o NVM.
3. Reinstale o Angular CLI:
```
npm install -g @angular/cli@17.3.9
```
### 4.2 Recriar Arquivos do Angular CLI
Se os executáveis `ng`, `ng.cmd` ou `ng.ps1` estiverem ausentes:
1. Navegue até o diretório:
```
C:\Users\<User>\AppData\Roaming\npm
```
2. Crie os arquivos necessários:

**Arquivo** `ng.cmd`
- Conteúdo:
```
@echo off
node "%~dp0\node_modules\@angular\cli\bin\ng.js" %*
```
**Arquivo** `ng.ps1`
- Conteúdo:
```
node "$PSScriptRoot\node_modules\@angular\cli\bin\ng.js" $args
```
**Arquivo** `ng`
- Conteúdo:
```
#!/bin/sh
node "$(dirname "$0")/node_modules/@angular/cli/bin/ng.js" "$@"
```
3. Torne o arquivo `ng` executável (em terminais como Git Bash):
```
chmod +x ng
```
4. Teste os comandos:
```
ng version
```
## 5. Comandos Resumidos
|Ação	| Comando|
|-----|--------|
|Instalar versão específica do Node.js	| `nvm install 16.20.2` | 
|Alternar para uma versão do Node.js	| `nvm use 16.20.2` |
|Instalar o Angular CLI	| `npm install -g @angular/cli@13.0.4` |
|Verificar versão do Angular CLI	| `ng version` |
|Listar todas as versões do Angular CLI	| `npm view @angular/cli versions` |
|Desinstalar o Angular CLI	| `npm uninstall -g @angular/cli` |
|Reinstalar uma versão específica do CLI	| `npm install -g @angular/cli@13.3.11` |

Com esta documentação, você pode configurar, gerenciar e solucionar problemas no ambiente Angular CLI 13.0.4 com facilidade. Ajuste conforme necessário para o seu uso no GitHub. 😊


### Outras configurações

- [Trabalhando com diferentes versões do Angular](https://www.alura.com.br/artigos/trabalhando-diferentes-versoes-angular?srsltid=AfmBOopbdRoB03f5PxXOult-9ChQkuKfoBA0MGNSnqeZFdb4TjX_SuSY)
- [Mudar versão do angular-cli](https://cursos.alura.com.br/forum/topico-mudar-versao-do-angula-cli-266813)
  
# Criando e Executando um Projeto Angular

Este guia descreve como criar, executar e configurar um projeto Angular usando o Angular CLI.

## 1. Criar um Novo Projeto

Para criar um novo projeto Angular, siga os passos abaixo:

```
ng new diretorioDoProjeto
```
- `diretorioDoProjeto`: Substitua pelo nome desejado para o diretório do seu projeto.
- Durante o processo, o Angular CLI pode solicitar:
  - Adicionar roteamento (Yes/No).
  - Escolher o estilo de folha de estilo (CSS, SCSS, etc.).

## 2. Navegar para o Diretório do Projeto

Após a criação, entre no diretório do projeto:
```
cd diretorioDoProjeto
```

## 3. Executar o Servidor de Desenvolvimento

Para subir a aplicação e acessá-la no navegador, use:
```
ng serve
```
- O servidor estará disponível no endereço:<br>
      http://localhost:4200

## 4. Instalar Dependências ao Baixar do Repositório

Se você clonou o projeto de um repositório e o diretório `node_modules` não foi incluído no repositório (pois geralmente está listado no `.gitignore`), instale as dependências com:
```
npm install
```
Isso garantirá que todas as dependências definidas no arquivo `package.json` sejam instaladas localmente no projeto.

# Comandos Essenciais do Angular CLI

O Angular CLI oferece uma variedade de comandos úteis para facilitar o desenvolvimento, testes, lint e deploy de aplicações Angular. Aqui estão alguns dos mais importantes:

### **1. Servir a Aplicação**
```bash
ng serve
```
- Inicia um servidor de desenvolvimento local e recompila automaticamente o projeto ao detectar alterações.
- Por padrão, a aplicação é servida em: [http://localhost:4200](http://localhost:4200).

---

### **2. Executar Testes Unitários**
```bash
ng test
```
- Executa os testes unitários da aplicação usando a configuração de testes especificada no projeto (geralmente Karma).
- Os resultados são exibidos no terminal e em um navegador.

---

### **3. Executar Testes End-to-End**
```bash
ng e2e
```
- Executa testes end-to-end usando uma ferramenta como Protractor ou outra configurada no projeto.
- Útil para validar o comportamento completo da aplicação.

---

### **4. Verificar Qualidade do Código**
```bash
ng lint
```
- Analisa o código com ferramentas de linting (como ESLint) para identificar problemas de estilo e erros potenciais.
- Garante que o código esteja alinhado com os padrões definidos no projeto.

---

### **5. Construir o Projeto para Produção**
```bash
ng build --prod
```
- Gera uma build otimizada para produção.
- Os arquivos de saída são armazenados na pasta `dist/` e podem ser implantados em um servidor.

---

Estes comandos são fundamentais para o desenvolvimento, manutenção e publicação de aplicações Angular. Use-os regularmente para garantir um fluxo de trabalho eficiente e uma aplicação de alta qualidade.



