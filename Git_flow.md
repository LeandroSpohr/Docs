
# Git Flow

Comandos para um git flow das galáxias.

### Git flow de desenvolvimento

#### 1 Antes de codar

1.1 O primeiro passo é dar um clone do repositório:

```bash
  git clone link_do_repo
```

1.2 Vá para a branch de desenvolvimento (nesse caso será a branch `dev`) * se não houver, crie uma no github ou através do passo 1.4:

```bash
  git checkout dev
```

1.3 Atualize a branch de desenvolvimento (localmente) *(faça isso sempre antes de abrir uma nova branch):

```bash
  git pull origin dev 
```

1.4 Crie uma nova branch a partir da dev para sua feature:

```bash
  git checkout -b nome-da-sua-branch
``` 

#### 2 Salvando sua feature

Depois de muitos codigos galácticos, salve as suas alterações localmente e na nuvem.

2.1 Adicione todas as suas alterções:

```bash
  git add .
``` 

2.2 Faça o commit dessas alterações:

```bash
  git commit -m "descricao do seu commit"
``` 

2.3 Faça o upload para a nuvem:

```bash
  git push origin nome-da-sua-branch
``` 

2.4 Atualiza a sua branch com a de `dev` para ver se nao houve alterações e ou conflitos 

```bash
  git pull origin dev
``` 

2.5 Se houver conflitos, corrija-os mantendo o que veio com o que você desenvolveu e repita os passos 2.1, 2.2 e 2.3. 
Após isso você está pronto para abrir o seu PR.

2.6 Agora você pode ir para a próxima feature e repetir tudo partir do passo 1.2.
