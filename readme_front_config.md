
# Frontend Tuning (Ubuntu)

Tutorial para instalação de software e configurações pra deixar a máquina tunada pra derrete nos código.


## Preparando a estrutura (obrigatótio para o funcionamento)
Node, git, yarn, IDE (VSCode).

### Repo Ubuntu

O primeiro passo é atualizar o repo do seu ubuntu:

```bash
sudo apt update && sudo apt upgrade
```

### Curl

Para poder baixar os pacotes:

```bash
sudo apt install curl
```

### Node estável

Na versão estável (pq vc é um dev, mas não vai gostar se seu ambiente quebrar! #ficaadica):

```bash
curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
sudo apt-get install -y nodejs
```

### Git

Para não perder o seu ganha pão versionado e seguro:

```bash
sudo apt install git
```

### Yarn (o npm tbm serve, ele já foi instalado junto com o Node)

O mago do ambiente de desenvolvimento:

```bash
sudo npm install --global yarn
```

### VSCode

Dispensa apresentações:

[Download VSCode](https://code.visualstudio.com/sha/download?build=stable&os=linux-deb-x64)

### Extensões do VSCode
#### Obrigatórias para o funcionamento ideal:
  * ESLint
  * Prettier
  * TSLint
  * vscode-styled-components

#### Opcionais:
  * visual studio intellicode
  * draculla Official
  * GitLens
  * Material Icon Theme
  * Rocketseat ReactJS e Native

## Melhorando a produtividade (opcional)
zsh, oh my zsh, agnoster, zsh-autosuggestions, zsh-syntax-highlighting, fonts.

Dúvido não querer ;)

### Zsh

Terminal melhorado para devs:

```bash
sudo apt install zsh
```

Após instalar execute-o digitando:

```bash
zsh
```

Na primeira execução vai pedir qual opção de config vc deseja, digite:

```bash
2
```

### Oh my zsh

Deixe o visual do terminal mais amigável:

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

Na primeira execução vai pedir se vc deseja alterar o zsh para o terminal padrao, digite:

```bash
S
```

### Oh my zsh - tema agnoster e plugins para auxílio

Acesse a pasta de plugins:

```bash
~/.oh-my-zsh/custom/plugins
```

Baixando o `zsh-autosuggestions` (sugestao de comandos para o terminal, com base no que vc já usou, tipo um cache):

```bash
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

Baixando o `zsh-syntax-highlighting` (ele identifica comandos válidos antes da execução, pra poupar tempo):

```bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

Abra o arquivo de config do terminal (vamos setar as novas configurações):

```bash
sudo gedit ~/.zshrc
```

Altere a variavel `ZSH_THEME` (dentro do arquivo) para:

```bash
ZSH_THEME='agnoster'
```

Encontre os `plugins` (ainda dentro do arquivo) e altere para:

```bash
plugins=(
    git
    zsh-autosuggestions
    zsh-syntax-highlighting
  )
```

Salve e feche o arquivo.

instale as fontes para os icones do tema agnoster:

```bash
sudo apt-get install fonts-powerline
```

### Fira Code

Uma fonte diferenciada de fácil interpretação:

```bash
sudo apt install fonts-firacode
```

### Tunando o tema agnoster

Abra o arquivo de config do tema:

```bash
sudo gedit ~/.oh-my-zsh/themes/agnoster.zsh-theme
```

Coloque um `#` na frente de `prompt_context`, (pq vc já sabe o seu nome, então não precisa fica mostrando).

Salve e feche o arquivo.

Agora vc precisa fazer um commit pra não dar problema nas atualizações automáticas:
Estando na pasta `~/.oh-my-zsh/` execute os comandos abaixo:

```bash
git config --global user.name "seu nome de usuario"
git config --global user.email "seu email"
git add /themes/agnoster.zsh-theme
git commit -m "tunning agnoster"
```

### Dica de ouro:

o comando abaixo permite que o yarn ouça alterações sem precisa do sudo:

```bash
echo fs.inotify.max_user_watches=524288 | sudo tee /etc/sysctl.d/40-max-user-watches.conf && sudo sysctl --system
```
