```stdin``` **Standard Input (Entrada padrão)**

* Fluxo normal, por onde o programa recebe os dados. Normalmente vem do teclado mas pode ser redirecionado para outros arquivos.

```stout```  **Standard Output (Saída padrão)**

* Por onde o programa envia os resultados ou saídas do terminal.
* Normalmente sai no Terminal/Tela 

```stderr```  **Standard Error (Erro padrão)**

* É o fluxo para mensagem de erro.
* Utilizado para separar os erros das saídas normais.
* Pode também ser redirecionado para sair no terminal.

### **🗃️ `sort`: O Organizador de Dados 📏**

O comando `sort` é o seu **organizador pessoal de linhas de texto**. Ele rearranja as linhas de um arquivo de texto (ou da entrada que você fornecer) em uma ordem específica.

- **O que faz?** Ele classifica as linhas em ordem alfabética (padrão), numérica, reversa, etc.
- **Por que é útil?**
  - **Análise de Dados:** Para organizar listas, logs ou saídas de outros comandos, tornando-os mais fáceis de ler e analisar. 📊
  - **Preparação para Processamento:** Muitas vezes, outros comandos funcionam melhor ou são mais eficientes se a entrada de dados estiver ordenada.
  - **Remoção de Duplicatas:** Combinado com a opção `-u` (unique), ele pode listar apenas as linhas únicas após a ordenação.
- **Exemplos Comuns:**
  - `sort nomes.txt`: Exibe as linhas do arquivo `nomes.txt` em ordem alfabética.
  - `sort -r numeros.txt`: Exibe as linhas do arquivo `numeros.txt` em ordem numérica reversa (do maior para o menor). 🔽
  - ```sort -u lista.txt``` : Tira duplicata 
  - `ls -l | sort -k 5n`: Lista os arquivos (com `ls -l`) e depois ordena a saída pelo 5º campo (tamanho do arquivo, `5n` para numérico). Isso é um exemplo de "pipeline", onde a saída de um comando vira a entrada de outro! 🔗

------

### **🔢 `wc`: O Contador de Palavras (e Mais!) 📝**

O comando `wc` (abreviação de **w**ord **c**ount) é como um **pequeno estatístico de texto**. Ele conta linhas, palavras e caracteres em arquivos.

- **Por que é útil?**

  - **Visão Rápida:** Para ter uma ideia do tamanho ou densidade de um arquivo de texto. 📈
  - **Contagem Específica:** Pode ser usado para contar apenas linhas (`-l`), palavras (`-w`) ou caracteres (`-m` ou `-c`).
  - **Verificação de Conteúdo:** Em scripts, pode-se verificar se um arquivo está vazio (0 linhas) ou se contém um determinado número de elementos.

- **Exemplos Comuns:**

  - `wc documento.txt`: Exibe o número de linhas, palavras e bytes no `documento.txt`.

  - `wc -l lista.txt`: Conta apenas o número de linhas no arquivo `lista.txt`.

    

    

------

### **🗓️ `date`: O Relógio do Sistema ⏰**

O comando `date` é o seu **acesso direto ao relógio e calendário do sistema**. Ele exibe ou permite que você defina a data e a hora do sistema.

- **O que faz?** Mostra a data e a hora atuais do sistema em um formato padrão. Com opções, você pode formatar a saída de várias maneiras ou até mesmo ajustar a data/hora (geralmente com permissões de administrador).
- **Por que é útil?**
  - **Verificação Rápida:** Para saber a data e hora rapidamente. ⌚
  - **Logs e Nomes de Arquivo:** Muito usado em scripts para incluir a data e hora em nomes de arquivos de backup ou entradas de log, garantindo que sejam únicos e rastreáveis. 🏷️
  - **Automatização:** Para agendar tarefas ou marcar eventos.
- **Exemplos Comuns:**
  - `date`: Exibe a data e hora atuais.
  - `date +"%Y-%m-%d_%H-%M-%S"`: Exibe a data e hora no formato "AAAA-MM-DD_HH-MM-SS", útil para nomes de arquivos. Ex: `2025-06-13_10-15-01`.
  - `date -s "2025-01-01 10:00:00"`: Define a data e hora do sistema para 1º de janeiro de 2025, 10:00:00. **(Requer `sudo` e cuidado!)** ⚠️

------

### **✍️ `touch`: O Criador/Atualizador de Arquivos (Revisado) ⏳**

Embora você já tenha visto o `touch`, vale a pena reforçar sua utilidade. Ele tem duas funções simples, mas poderosas.

- **O que faz?**
  1. **Cria um arquivo vazio:** Se o arquivo que você especifica **não existe**, o `touch` o cria instantaneamente, vazio. 📝
  2. **Atualiza a data de modificação:** Se o arquivo **já existe**, o `touch` simplesmente **atualiza a data e hora da última modificação** (e acesso) para o momento atual, sem alterar o conteúdo do arquivo. ⏰
- **Por que é útil?**
  - **Preparar Arquivos:** Para criar rapidamente arquivos "placeholder" antes de adicionar conteúdo.
  - **Marcar Tempo:** Em desenvolvimento de software ou scripts, é usado para "tocar" um arquivo, fazendo com que ele pareça recém-modificado, o que pode acionar outros processos (como recompilação de código). 🔄
  - **Organização:** Às vezes, você só quer que um arquivo apareça no topo de uma lista de arquivos ordenados por data de modificação.
- **Exemplo:**
  - `touch meu_novo_log.txt`: Cria um arquivo vazio.
  - `touch meu_documento_antigo.pdf`: Atualiza a data de modificação do PDF para "agora".

------

### **📖 `less`: O Leitor de Arquivos Página por Página 📚**

O comando `less` é um **visualizador de arquivos** que é perfeito para ler arquivos longos sem sobrecarregar o terminal.

- **O que faz?** Ele exibe o conteúdo de um arquivo **uma tela por vez**, permitindo que você role para cima e para baixo. Ele não carrega o arquivo inteiro na memória de uma vez, tornando-o eficiente para arquivos muito grandes.
- **Por que é útil?**
  - **Leitura de Logs:** Ideal para inspecionar arquivos de log grandes que podem ter milhares de linhas. 📜
  - **Visualização Segura:** Você pode navegar pelo arquivo sem o risco de modificá-lo acidentalmente.
  - **Pesquisa:** Permite pesquisar texto dentro do arquivo.
  - **Eficiência:** Não importa o tamanho do arquivo, `less` abre e começa a exibir o conteúdo quase instantaneamente. 🚀
- **Como usar:**
  - `less nome_do_arquivo.log`: Abre o arquivo para leitura.
  - **Comandos dentro do `less` (pressione):**
    - `Espaço` ou `Page Down`: Avança uma tela.
    - `b` ou `Page Up`: Volta uma tela.
    - `seta para baixo`: Rola uma linha para baixo.
    - `seta para cima`: Rola uma linha para cima.
    - `/texto_a_procurar`: Procura por "texto_a_procurar" (pressione `n` para a próxima ocorrência, `N` para a anterior). 🔍
    - `q`: Sai do `less`. 🚪