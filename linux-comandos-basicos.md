# 🐧 Guia de Comandos e Fundamentos do Linux

Este documento reúne os principais conceitos e comandos para navegação, gerenciamento de arquivos e administração básica em sistemas Linux.

---

## 1. Fundamentos do Terminal

* **Case Sensitive:** O sistema diferencia letras maiúsculas de minúsculas. 
  * *Exemplo:* `Arquivo.txt` é considerado diferente de `arquivo.txt`.

### Entendendo o Prompt de Comando
Ao abrir o terminal, a linha de comando exibe informações importantes, geralmente no formato `usuario@maquina ~ $`:
* **`@` (arroba):** Separa o nome do usuário do *hostname* (nome da máquina).
* **`~` (til):** Indica que você está na *home* (pasta pessoal) do usuário atual.
* **`$`:** Indica que você está utilizando um usuário comum (sem privilégios administrativos).
* **`#`:** Indica que você está utilizando o usuário `root` (administrador do sistema).

---

## 2. Atalhos e Dicas Úteis

* **Autocompletar com `TAB`:** Ao começar a digitar o nome de um diretório ou arquivo, pressione `TAB`. O terminal tentará completá-lo automaticamente. Se pressionar `TAB` duas vezes, ele exibe todas as opções possíveis.
* **Limpar o terminal:**
  * Comando: `clear`
  * Atalho: `Ctrl + L`

---

## 3. Informações do Sistema

* **`date`**: Mostra a data e a hora atuais do sistema.
* **`ip a`**: Exibe os endereços IP associados às interfaces de rede da máquina.

---

## 4. Navegação pelo Sistema de Arquivos

O diretório raiz (onde todo o sistema começa) é representado pela barra **`/`**.

* **`pwd`** (*Print Working Directory*): Mostra o caminho completo de onde você está atualmente.
* **`cd`** (*Change Directory*): Sem argumentos, leva você de volta para o diretório *home*.
* **`cd /`**: Vai direto para o diretório raiz do sistema.
* **`cd ..`**: Volta um nível (uma pasta para trás).
* **`cd ../nome-do-diretorio`**: Volta um nível e, imediatamente, entra no diretório especificado.

---

## 5. Listagem de Arquivos e Diretórios (`ls`)

O comando `ls` exibe o conteúdo do diretório atual. Ele pode ser combinado com diversas opções (flags) para detalhar a visualização:

* **`ls`**: Lista simples do conteúdo.
* **`ls *`**: Lista o conteúdo do diretório atual e também o que há dentro de seus subdiretórios imediatos.
* **`ls -a`**: Lista todos os arquivos, incluindo os ocultos (que começam com um ponto `.`).
* **`ls -l`**: Lista no formato longo. Exibe permissões,
