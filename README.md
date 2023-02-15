# Livreto para Celebrações Litúrgicas

Projeto de livretos para Celebrações Litúrgicas.

## Ambiente de Desenvolvimento

### Atualização do Windows - Windows Update e Windows Store

#### Instalar o Visual Studio Code - Windows Store

#### Instalar o Windows Terminal - Windows Store

### Instalação e Configuração do WSL

* Executar o PowerShell como Administrador.
*
* Instalação do WSL:

~~~powershell
wsl --install --no-distribution
~~~

Finalizada instalação reiniciar o computador.

* Atualizar o WSL:

~~~powershell
wsl --update
~~~

* Definir a versão 2 do WSL:

~~~powershell
wsl --set-default-version 2
~~~

* Verificar as distribuições do GNU/Linux disponíveis:

~~~powershell
wsl --list --online
~~~

* Instalar a distribuição do GNU/Linux:

~~~powershell
wsl --install --distribution ubuntu-22.04
~~~

* Definir a distribuição padrão do GNU/Linux:

~~~powershell
wsl --set-default ubuntu-22.04
~~~

* Verificar as distribuições instaladas:

~~~powershell
wsl --list --verbose
~~~

### Configuração do Windows Terminal

* Executar o Windows Terminal e configurar a distribuição GNU/Linux Ubuntu como padrão na Inicialização e salvar as alterações.

### Criação do usuário e senha do GNU/Linux

### Atualização da Ubuntu

~~~bash
sudo apt update -y && sudo apt full-upgrade -y
~~~

### Pasta do Projeto

* Criar pasta do projeto

~~~bash
mkdir livreto-liturgico
~~~

### Configuração do VS Code

* Abrir o VS Code e instalar a extensão WSL.
* Reiniciar o VS Code.
* Acessar a pasta do projeto
* Abrir o Windows Terminal e abrir o VS Code no WSL.

~~~bash
code .
~~~

Será instalado o VS Code Server no WSL.

#### Instalação das Extensões do VS Code

* Realizar a instalação das extensões:

1. Dracula Official
2. Material Icon Theme
3. Brazilian Portuguese - Code Spell Checker
4. Code Spell Checker
5. EditorConfig for VS Code
6. Latex Workshop
7. Markdown All in One
8. markdownlint
9. Path Intellisense
10. Reload

#### Configuração das extensões do VS Code

##### Instalação das fontes

* Realizar download e instalação das fontes Fira Code e MesloLGS NF:

##### Configuração das preferencias do VS Code

1. Abrir o VS Code;
2. Abrir o Visual Studio Code;
3. Com o comando "Ctrl + Shift + p" abrir a Command Palette;
4. Buscar a opção: Preferences:Open Settings (JSON);
5. Substituir as configurações do JSON.

~~~json
{
    "workbench.startupEditor": "none",
    "workbench.iconTheme": "material-icon-theme",
    "workbench.colorTheme": "Dracula",
    "editor.renderLineHighlight": "gutter",
    "editor.bracketPairColorization.enabled": true,
    "editor.fontFamily": "'Fira Code'",
    "editor.fontSize": 14,
    "editor.fontLigatures": true,
    "editor.formatOnPaste": true,
    "editor.formatOnSave": true,
    "editor.insertSpaces": true,
    "editor.renderWhitespace": "boundary",
    "editor.smoothScrolling": true,
    "editor.suggestSelection": "recentlyUsedByPrefix",
    "editor.wordWrap": "bounded",
    "files.trimTrailingWhitespace": true,
    "latex-workshop.linting.chktex.enabled": true,
    "latex-workshop.linting.run": "onType",
    "latex-workshop.intellisense.package.enabled": true,
    "latex-workshop.kpsewhich.enabled": true,
    "latex-workshop.latex.autoBuild.run": "onSave",
    "latex-workshop.latex.autoClean.run": "onFailed",
    "latex-workshop.latex.clean.subfolder.enabled": true,
    "latex-workshop.latex.external.build.args": [
        "--shell-escape",
        "--synctex=1",
        "--interaction=nonstopmode",
        "--file-line-error",
        "--halt-on-error"
    ],
    "latex-workshop.latex.recipe.default": "latexmk (lualatex)",
    "latex-workshop.latex.recipes": [
        {
            "name": "latexmk (lualatex)",
            "tools": [
                "lualatexmk"
            ]
        }
    ],
    "latex-workshop.latex.tools": [
        {
            "name": "lualatexmk",
            "command": "latexmk",
            "args": [
                "--lualatex",
                "--shell-escape",
                "--synctex=1",
                "--interaction=nonstopmode",
                "--file-line-error",
                "--halt-on-error",
                "%DOC%"
            ]
        }
    ],
    "latex-workshop.synctex.afterBuild.enabled": true,
    "latex-workshop.texdoc.args": [
        "--view",
        "--shell-escape"
    ],
    "latex-workshop.view.pdf.viewer": "tab",
    "terminal.integrated.defaultProfile.linux": "zsh",
    "terminal.integrated.fontFamily": "MesloLGS NF",
    "terminal.integrated.fontSize": 14,
    "cSpell.language": "en,pt,pt_BR",
}
~~~

### Instalação e configuração do Zsh

#### Instalação do Zsh

Abrir o Windows Terminal ou Terminal do VS Code:

* Instalar pacotes de desenvolvimento.

~~~bash
sudo apt install build-essential -y
~~~

* Instalar o Zsh.

~~~bash
sudo apt install zsh -y
~~~

* Após a instalação do zsh realizar a mudança do shell:

~~~bash
chsh -s /bin/zsh
~~~

* Iniciar o zsh:

~~~bash
zsh
~~~

Reiniciar o Windows Terminal ou Terminal do VS Code para iniciar o shell Zsh.

#### Instalação do Oh My Zsh

* Instalar o Oh My Zsh:

~~~bash
sudo sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
~~~

#### Instalar e configurar o plugin zsh-autosuggestions

* Configuração do plugin zsh-autosuggestions:

~~~bash
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
~~~

Adicionar o plugin na lista de plugins do Oh My Zsh (no arquivo ~/.zshrc):

~~~bash
zsh-autosuggestions
~~~

#### Instalar e configurar zsh-syntax-highlighting

* Configuração do plugin zsh-syntax-highlighting:

~~~bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
~~~

Adicionar o plugin na lista de plugins do Oh My Zsh (no arquivo ~/.zshrc):

~~~bash
zsh-syntax-highlighting
~~~

#### Instalação e configuração do tema powerlevel10k

* Configuração do tema powerlevel10k:

~~~bash
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
~~~

Configurar o tema no arquivo (no arquivo ~/.zshrc):

~~~bash
ZSH_THEME="powerlevel10k/powerlevel10k
~~~

Após a configuração você vai realizar a configuração do visual do shell.

### Instalação do MikTeX

* Registro da chave GPG:

~~~bash
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys D6BC243565B2087BC3F897C9277A7293F59E4889
~~~

* Configurar source.list:

~~~bash
echo "deb http://miktex.org/download/ubuntu jammy universe" | sudo tee /etc/apt/sources.list.d/miktex.list
~~~

* Instalação do MikTeX:

~~~bash
sudo apt update -y && sudo apt install miktex -y
~~~

* Finalizar a configuração.

Usuário Comum

~~~bash
miktexsetup finish
~~~

Usuário Administrador

~~~bash
sudo miktexsetup --shared=yes finish
~~~

* Habilitar a instalação automática de pacote.

Usuário Comum

~~~bash
initexmf --set-config-value '[MPM]AutoInstall=1'
~~~

Usuário Administrador

~~~bash
sudo initexmf --admin --set-config-value '[MPM]AutoInstall=1'
~~~

* Atualização dos pacotes.

Usuário Comum

~~~bash
mpm --verbose --update
~~~

Usuário Administrador

~~~bash
sudo mpm --verbose --update
~~~

### Configuração do Git

~~~bash
git config --global user.name "username"
~~~

~~~bash
git config --global user.email email@dominio
~~~

~~~bash
git config --global user.editor code
~~~

~~~bash
git init
~~~
