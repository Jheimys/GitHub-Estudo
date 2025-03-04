# 1. Git Pull e Git fetch

O comando **git fetch** para dar uma olhada nas atualizações do repositório remoto sem trazê-las para o seu ambiente local. Ele vai baixar as mudanças feitas por lá, mas sem mexer no seu código ou fazer o merge automático.

Depois de rodar o **git fetch**, você pode usar o comando:

**git diff <branch_local> origin/<branch_remoto>**

Com isso, dá para comparar e ver o que mudou no repositório remoto antes de decidir se quer trazer essas alterações para o seu código com o **git pull**. Assim, você mantém o controle sobre o que entra no seu projeto.

# 2. Git MV
Com o comando ***git mv*** posso mover ou renomear um arquivo.

***OBS:*** tenho que esta na pasta correta e ter já ter feito push dos arquivos 

**EX1:** Mover um aquivo para uma pasta.

1.Criei a de css
2. fora dessa pasta criei o arquivo index.css
3. Fiz o push desses arquivos
4. colocar o arquivo index.css dentro da pasta css

```js
git mv index.css css/index.css
```

**EX2:** Renomear um aquivo.

1.Criei o arquivo rodapre.css dentro da pasta de css
2. Fiz o push desses arquivos
3. quero renomear o arquivo rodapre para rodape

```js
git mv css/rodapre.css css/rodape.css
```

# 2. Git Checkout

Se você fez alterações em um arquivo, mas quer descartar essas mudanças e voltar ao estado do último commit, você pode usar git checkout:

```bash
git checkout -- nome-do-arquivo
```

**Exemplo:**

Você tem o seguinte arquivo estilos.css:

```css
/* estilos.css */

body {
    background-color: white;
}

h1 {
    color: black;
}

```
Você então altera o arquivo para o seguinte:

```css
/* estilos.css */

body {
    background-color: black;
}

h1 {
    color: yellow;
}

```

Agora, você percebe que quer descartar essas alterações e voltar ao estado anterior do arquivo.

**Passo a Passo:**
1.Verificar o status do Git (opcional)
2.Restaurar o arquivo usando git checkout:

```bash
git checkout -- estilos.css
```
3.Verificar o resultado:
```css
/* estilos.css */

body {
    background-color: white;
}

h1 {
    color: black;
}

```


# 3.Git reset --flag

**1.Cenário de erro em um commit:**

Você percebe que o último commit que fez tem um erro. Você ainda não compartilhou esse commit e decide que prefere desfazer completamente essa mudança ao invés de fazer um novo commit para corrigir

```bash
git reset --hard origin/master
```

**2.Cenário de experimentação:**

Você fez várias modificações no código experimentalmente, mas agora quer descartar todas essas mudanças e voltar ao último commit estável.

```bash
git reset --hard origin/master
```

**3.Cenário de retornar a uma versão específica:**
Você precisa voltar para um commit específico, porque depois dele várias mudanças foram feitas que você deseja ignorar.

```bash
git reset --hard origin/master
```