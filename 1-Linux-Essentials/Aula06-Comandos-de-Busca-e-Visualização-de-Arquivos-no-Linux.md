# sumário
``find`` Usamos quando queremos buscar algum arquivo, podemos procurar tanto por Nome, Tipo, Tamanho, Data, Permissão etc...
```ls -a``` Mostra os arquivos que são ocultos, arquivo e diretório que começa com  (  ***.***  )  Exemplo: **.cache** 
```man [nome_do_comando]``` usamos quando queremos exibir o manual de um comando ou utilitário
```info [nome_do_comando]``` como se fosse um tutoria, igual ao de cima.

-------------------------------------------------------------------------------
## Comando *Find* 
O comando Find é um comando que usado para procurar arquivos e diretórios em sistemas linux, podemos basear nossa busca em alguns critérios como: 
* Nome
* Tipo
* Tamanho
* Data de Modificação 
* Dono 
* Permissão
### Principais Operações 
#### `-name "padrão"`
* Busca por nome exato, **diferencia maiúsculas e minúsculas**.
	`find /caminho -name "arquivo.txt"`
####  `-iname "padrão"`
* Busca por nome ignorando maiúsculas/minúsculas (**case-insensitive**).
	`find /caminho -iname "arquivo.txt"` 

## Comando *Cat*  
Esse comando significa (concatenar) podemos usar para exibir o conteúdo de um arquivo no terminal.
### Mostrando Conteúdo de um arquivo
* Criamos esse arquivo chamado [arquivos.txt]
* Dentro dele escrevemos algo, mas não sabemos o que é.
![[Pasted image 20250721211107.png]]
* Podemos usar o comando *cat*  para saber o que tem escrito dentro do arquivo.
![[Pasted image 20250721211241.png]]