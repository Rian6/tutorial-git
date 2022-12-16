# Tutorial para o uso do git

### Git init

Inicia um novo projeto git.
```
git init
```

### Git Clone

Este comando é usado para clonar um projeto existente a partir de um link de um repositório.
```
git clone /caminho
```

## Fluxo de trabalho
 ![](1.png)
O git possui um sistema de árvore definido por áreas onde os arquivos vão ser mantidos até serem submetidos para a próxima etapa. Esse fluxo segue o seguinte caminho:

* Working Directory - É o seu local de trabalho. São todos os arquivos que foram editados, excluídos ou adicionados antes de um commit e antes de serem enviados para o servidor;
* Index - Área temporária onde os arquivos são empacotados antes de serem submetidos;
* Head - Local onde ficam os arquivos originais de cada ramificação.

### Submeter alterações

Antes de enviar um conjunto de arquivos, ou um arquivo único, para o repositório, precisamos adicionar eles ao index, para isso usamos o comando:
```
git add <arquivo>
```
Podemos também adicionar um conjunto de arquivos com o comando:
```
git add *
```
Onde adicionamos todos os arquivos do diretório relacionado. Lembrando que os arquivos ainda estão na máquina, não no servidor.

O próximo passo é juntar todos esses arquivos em um "pacote" e então submeter tudo para a árvore principal.

````
git commit -m "o seu comentario da alteração vai aqui"
````

O comando commit junta todos os arquivos que estão no index e deixa pronto para os submeter ao head

Por fim, para submeter todos os commits para a ramificação principal (head), usamos o comando:
````
git push origin sua_branch
````

## Ramificações

Quando trabalhamos com o git, podemos criar novas ramificações e trocar de ramificação quando quisermos, a vantagem disso é poder trabalhar em diferentes ambientes sem alterar o código principal, ou aquele já em operação.

Para manipular ramificações, usamos o comando checkout. Antes de criar uma ramificação precisamos entrar naquela que vai dar origem a nova, para isso usamos o seguinte comando:

````
git checkout sua_branch
````
Dica: para verificar o status de qual branch você está, dados sobre a árvore local e commits, você pode usar o comando  ```` git status ````

Após entrar em uma branch, você pode criar a nova ramificação usando o comando:
````
git checkout -b nova_branch
````

E para remover a branch:
````
git branch -d nova_branch
````
E por fim, para enviar uma branch ao servidor, use o comando ````push````
````
git push origin nova_branch
````
## Atualizar e Merge

Num projeto, cada ramificação faz parte do todo. Quando tudo está pronto é necessário unir as ramificações para lançar o projeto. Para unir todas as branchs usamos o merge. Já para atualizar a branch atual, depois de fazer as atualizações no código, usamos o pull.

Para atualizar a ramificação que estamos trabalhando usamos o comando:
````
git pull
````
Este comando é importante pois certifica que o seu código vai estar atualizado com o servidor e atualizar somente as suas implementações.

Para realizar a junção das branchs, utilizamos o comando:
````
git merge sua_branch
````
Lembrando que nos dois comandos o git vai tentar mesclar os conjuntos de arquivos, mas nem sempre isso é possível. Caso ocorra algum erro, o usuário precisará resolver os conflitos antes de submeter as alterações. Após solucioná-los, é possível realizar a atualização (pull) ou a junção (merge).
