## **📝 Opções Essenciais do `tar`**

Vamos direto ao que interessa, as opções mais usadas:

- **`-c` (create)**: 🆕 Cria um novo arquivo `.tar`. É a opção que você usa para "montar a caixa".
- **`-x` (extract)**: 📤 Extrai arquivos de um `.tar` ou `.tar.gz`. É para "abrir a caixa e tirar o conteúdo".
- **`-v` (verbose)**: 🗣️ Mostra os arquivos que estão sendo processados. É como ter um narrador te dizendo o que está acontecendo. **Sempre use!** Facilita muito ver se deu certo.
- **`-f` (file)**: 💾 Especifica o nome do arquivo `.tar` ou `.tar.gz` que você está criando ou extraindo. **Sempre use!** Ela deve ser a última opção, e o nome do arquivo vem logo depois dela.
- **`-z` (gzip)**: 💨 Comprime (ou descomprime) usando `gzip`. É a compressão mais comum e rápida. Resulta em `.tar.gz` ou `.tgz`.
- **`-j` (bzip2)**: 🗜️ Comprime (ou descomprime) usando `bzip2`. Geralmente comprime mais do que `gzip`, mas é mais lento. Resulta em `.tar.bz2` ou `.tbz2`.
- **`-J` (xz)**: 🧊 Comprime (ou descomprime) usando `xz`. A melhor compressão, mas a mais lenta. Resulta em `.tar.xz` ou `.txz`.
- **`-t` (list)**: 📜 Lista o conteúdo de um arquivo `.tar` sem extraí-lo. É para "espiar dentro da caixa".
- **`--exclude`**: 🚫 Exclui arquivos ou diretórios específicos do arquivo `.tar` durante a criação. Útil para não incluir coisas desnecessárias.



# Ferramentas de compressão

A compressão de arquivos é utilizada quando queremos diminuir a quantidade de espaço em um conjunto de de dados. Muito utilizado para diminuir a quantidade de dados que serão enviados na rede. Algumas ferramentas de empacotamento devem ser utilizadas em conjunto a algumas ferramentas de compressão.

Gerenciamento de Arquivos no Linux: Compactação (gzip, bzip2, xz) e Empacotamento (tar)

* Gzip
Compressão de dados, utilizamos o formato *gz*. Podemos usar esse comando da seguinte forma : ```gzip arquivos.txt``` 
```bash 
gzip 'ACESSOS-1-ANYDESK.XLSX'

//SAIDA 
ACESSOS-3-ANYDESK.xlsx.gz
```

* bzip2
Compressão de dados, utilizamos o formato *bz2*. Executamos esse comando da seguinte forma : ```bzip2 arquivo.txt```

```bash 
bzip2 'ACESSOS-2-ANYDESK.XLSX'

//SAIDA 
ACESSOS-1-ANYDESK.XLSX.bz2
```

* xz
Compressão de dados, utilizamos o formato **xz**. Executamos esse comando da seguinte
forma : ``` xz arquivo.txt```
```bash 
xz 'ACESSOS-3-ANYDESK.XLSX'

//SAIDA
'ACESSOS-2-ANYDESK.XLSX.xz'
```

## Descompactar Arquivos
Para descomprimir os arquivos acimas devemos usar os seguintes comandos.

* bzip2 
Devemos usar o **bunzip2**, esse comando descomprimi o arquivo **.bz2** 
```bash 
//Arquivo Compactado
bigfile2.bz2

//Descompactando
bunzip2 bigfile2.bz2
```

* Gzip
Devemos usar o **gunzip**, esse comando descomprimi o arquivo **.gz**
```bash 
//Arquivo Compactado
bigfile.gz

//Descompactar
gunzip bigfile.gz
```
* xz
Devemos usar o **unxz**, esse comando descomprimi o arquivo **.xz**
```bash
//Arquivos Compactado
bigfile3.xz

//Descompactando
unxz bigfile3.xz
```


# Ferramentas de Empacotamento

* Em Linux, o podemos dizer que o comando de empacotamento mais utilizado nos sistemas linux e o famoso ```tar```. O ```tar``` ele só *empacota* e *desempacota*. 
* Quando usamos o ```tar``` ele vai reunir os arquivos que escolhemos e vai empacotar (colocar eles dentro de um outro arquivo).

### Criando pacotes
Este comando que estamos usando, *serve para empacotar um ou mais arquivos e diretórios em um único arquivo de pacote*
```bash
tar cf aula.tar aula07/
```
 * Neste comando estamos empacotando o diretório inteiro de *aula07*, caso adicionarmos uma algum outro caminho apos a / ai sim estaremos empacotando algo especifico e não o diretório inteiro.
 * A letra ```c``` significa (create) ou (criar).
 * A letra ```f``` significa (file) ou (arquivo).

### Visualizando o conteúdo 
Podemos visualizar o conteúdo do arquivo *.tar* da seguinte maneira, devemos usar a opção ```t``` do tar.
```bash 
tar -tf aula.tar

//saida 
aula07/
aula07/compression/
aula07/compression/bigfile4
aula07/compression/bigfile
aula07/compression/bigfile2
aula07/compression/bigfile3
```
* Desta maneira conseguimos verificar quais arquivos estão presentes dentro de um arquivo compactado. 

## Desempacotando o conteúdo
Utilizando o comando a seguir conseguimos descompactar o diretório que foi empacotado.
Vamos supor que temos um arquivo da seguinte maneira : 
```bash
jetbrains-toolbox-2.7.0.48109.tar
```

* Podemos descompactar ele usando o ```tar -xf``` 
```bash 
tar -xf jetbrains-toolbox-2.7.0.48109.tar
```
executando esse comando no nosso terminal estaremos desempacotando.

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### Criar um Arquivo `.tar` (Agrupar)

Estamos criando um arquivo ```.tar``` e posteriormente iremos escolher qual e o diretório que iremos agrupar.

```
tar -cvf projeto_aula.tar aula07/
```

- `c`: **c**riar.

- `v`: **v**er o que está fazendo.

- `f`: especificar o **f**ile (`meus_projetos.tar`).

- `projeto_aula`: o diretório que você quer agrupar.

  

### Criar um Arquivo `.tar.gz` (Agrupar e Comprimir com gzip)

Essa é a forma mais comum de usar o `tar`. Você agrupa e já comprime para economizar espaço.

```
tar -czvf projeto_aula.tar.gz documentos/
```

- `c`: **c**riar
- `z`: comprimir com `g**z**ip`
- `v`: **v**er o que está fazendo
- `f`: especificar o **f**ile (`meus_documentos.tar.gz`)

### Criar um Arquivo `.tar.bz2` (Agrupar e Comprimir com bzip2)

Se a prioridade for o menor tamanho possível e você não se importa com a velocidade de compressão/descompressão, use `-j`.

```
tar -cjvf projeto_aula.tar.bz2 fotos/
```

- `c`: **c**riar
- `j`: comprimir com `b**j**ip2`
- `v`: **v**er o que está fazendo
- `f`: especificar o **f**ile (`minhas_fotos.tar.bz2`)

### **Listar o Conteúdo de um Arquivo `.tar.gz` (Espiar)**

Quer saber o que tem dentro de um arquivo `.tar.gz` sem extrair tudo? Use `-t`!

```
tar -tzf projeto_aula.tar.gz
```

- `t`: **t**estar (listar) o conteúdo

- `z`: é um arquivo `g**z**ip`

- `f`: especificar o **f**ile (`meus_documentos.tar.gz`)

### **Extrair o Conteúdo de um Arquivo `.tar.gz`**

Agora, a parte de "abrir a caixa". Para descompactar e extrair os arquivos:

```
tar -xzvf meus_documentos.tar.gz
```

- `x`: e**x**trair
- `z`: é um arquivo `g**z**ip`
- `v`: **v**er o que está sendo extraído
- `f`: especificar o **f**ile (`meus_documentos.tar.gz`)

Por padrão, ele extrai os arquivos no **diretório atual**. Se o arquivo `meus_documentos.tar.gz` continha uma pasta chamada `documentos/`, essa pasta será criada aqui.