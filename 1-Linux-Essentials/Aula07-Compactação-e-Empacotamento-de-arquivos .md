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







