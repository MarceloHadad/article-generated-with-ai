# ![RESOLVENDO E EVITANDO ERROS](./assets/Slide1.PNG)

Então você está trabalhando com o vasto mundo do Git! É uma jornada emocionante, mas vamos encarar: cometer alguns erros faz parte do processo - é assim que aprendemos, afinal.

Neste artigo, vamos explorar alguns problemas comuns que eu mesmo já enfrentei, e, o mais importante, como evitá-los.

## ![CORRIGINDO O ÚLTIMO COMMIT](./assets/Slide2.PNG)

Às vezes, nos empolgamos e fazemos o commit sem revisar, mas percebemos que o autor está incorreto, não correspondendo ao nosso nome e e-mail da empresa. Talvez a mensagem do commit não tenha ficado adequada ou não siga a convenção. Para resolver isso, basta usar o comando git commit --amend. Com ele, é possível editar a mensagem ou até mesmo trocar o autor do commit. Vejamos um exemplo:

```bash
git commit --amend -m "Sua nova mensagem aqui"
```

No comando acima, estamos editando apenas a mensagem do último commit.

```bash
git commit --amend --author="Novo Autor <novo@email.com>" --no-edit
```

Já nesse outro comando, estamos trocando somente o autor do último commit. O uso do --no-edit indica para o Git que você não quer editar a mensagem do commit, apenas realizar a alteração no autor.

## ![CONFIGURANDO O GIT PARA CADA DIRETÓRIO](./assets/Slide3.PNG)

Para quem trabalha com projetos em contextos diferentes, como estudos, trabalho e faculdade, pode ser bastante útil configurar o git config para diretórios de acordo com esse contexto. Dessa forma, os projetos criados dentro desses diretórios utilizarão o autor respectivo.

No arquivo .gitconfig, você pode usar a diretiva [includeIf] para especificar condições que determinam quais configurações devem ser incluídas para diretórios específicos. Por exemplo:

```bash
[includeIf "gitdir:D:/repos/personal/"]
    path = .gitconfig-personal
```

Essa configuração diz ao Git para incluir as configurações do arquivo .gitconfig-personal quando estiver trabalhando em um diretório que corresponde ao caminho especificado.

Então, no arquivo .gitconfig-personal, no mesmo diretório do .gitconfig, você pode configurar seu nome de usuário e email como:

```bash
[user]
    name = Louro Joseph
    email = louro.joseph@gmail.com
```

Dessa forma, quando você estiver trabalhando nos projetos no diretório D:/repos/personal/, o Git utilizará automaticamente as configurações definidas no arquivo .gitconfig-personal sem que você precise configurá-las manualmente em cada repositório. Muito prático, né?

## ![CORRIGINDO COMMITS ANTIGOS COM O REBASE INTERATIVO](./assets/Slide4.PNG)

Às vezes, a gente só percebe alguns erros nos commits depois, quando já não é mais possível utilizar o amend. Mas não se desespere! Com o rebase interativo, dá para corrigir de boa. É só rodar git rebase -i HEAD~n, onde n é o número de commits que quer mexer. Aí, é só seguir as instruções e arrumar tudo bonitinho.

Quando você usa o rebase interativo, ele abrirá um arquivo com algumas instruções de comandos, os que já me foram úteis são:

```bash
pick (p): Utiliza o commit conforme está.
reword (r): Utiliza o commit, mas permite editar a mensagem do commit.
edit (e): Utiliza o commit, mas interrompe para emendar (amend), possibilitando fazer alterações.
squash (s): Utiliza o commit, mas integra-o ao commit anterior.
```

Os três primeiros são bastante autoexplicativos, já o último, merece um exemplo de uso prático. Imagine que você tem alguns commits que foram feitos durante algum teste, como ao trabalhar com um pipeline do Bitbucket, onde ele só executa o pipeline com um commit selecionado. Digamos que você fez algo como:

```bash
"Adiciona comando para instalar o pacote xpto"
"Altera o comando para instalar uma versão específica"
"Remove o comando para fazer a instalação de uma versão específica sem o gerenciador de pacote"
```

No fim, você fez tudo isso para instalar o pacote xpto na versão 2.1.3. Faz mais sentido ter apenas um commit com tudo isso, né?! Então você pode utilizar o squash para "juntar" esses commits em um só:

```bash
Adiciona a instalação do pacote xpto
```

## ![CONCLUSÃO](./assets/Slide5.PNG)

Dominar as técnicas para resolver e evitar erros ao usar o Git é essencial para qualquer desenvolvedor. Desde corrigir detalhes em commits até configurar adequadamente o ambiente de trabalho, cada passo contribui para uma experiência mais fluida e produtiva. Espero que o conhecimento compartilhado neste artigo te permita estar mais preparado para enfrentar os desafios do controle de versão e aproveitar ao máximo as vantagens que o Git oferece. Então, mãos à obra e continue explorando as possibilidades deste poderoso sistema de controle de versão!

Curtiu esse conteúdo? Ele foi gerado com o ChatGPT, sendo revisado por alguém 100% humano. Conecte comigo no [LinkedIn](https://www.linkedin.com/in/marcelohadad/) e vamos continuar essa conversa!

**Ferramentas de produção:**

Imagens geradas por: Lexica

Editor de imagem: Power Point

Conteúdo gerado em conjunto com: ChatGPT

Revisões Humanas: Marcelo Hadad

`#Git #Programação #Desenvolvimento #Tecnologia #Aprendizado`
