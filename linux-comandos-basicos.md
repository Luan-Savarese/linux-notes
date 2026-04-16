# 🐧 Guia de Comandos e Fundamentos do Linux

Este documento reúne os principais conceitos e comandos para navegação, gerenciamento de arquivos e administração básica em sistemas Linux.

---

## 1. Fundamentos do Terminal

* **Case Sensitive:** O sistema diferencia letras maiúsculas de minúsculas. 
  * *Exemplo:* `Arquivo.txt` é considerado diferente de `arquivo.txt`.

### Entendendo o Prompt de Comando
Ao abrir o terminal, a linha de comando exibe informações importantes:
* **`@` (arroba):** Separa o nome do usuário do *hostname* (nome da máquina).
* **`~` (til):** Indica que você está na *home* (pasta pessoal) do usuário atual.
* **`$`:** Indica um usuário comum.
* **`#`:** Indica o usuário `root` (administrador).

---

## 2. Atalhos e Dicas Úteis

* **Autocompletar com `TAB`:** Pressione `TAB` uma vez para completar ou duas para ver as opções.
* **Limpar o terminal:** Comando `clear` ou atalho `Ctrl + L`.

---

## 3. Informações do Sistema

* **`date`**: Mostra data e hora atuais.
* **`ip a`**: Exibe os endereços IP das interfaces de rede.

---

## 4. Navegação pelo Sistema de Arquivos

O diretório raiz é representado pela barra **`/`**.

* **`pwd`**: Mostra o caminho (diretório) atual.
* **`cd`**: Entra em pastas ou volta para a *home*.
* **`cd /`**: Vai para a raiz.
* **`cd ..`**: Volta um nível.
* **`cd ../nome-da-pasta`**: Volta um nível e entra em outra pasta.

---

## 5. Listagem de Arquivos e Filtros (`ls`)

O comando `ls` possui diversas opções e filtros poderosos:

### Flags de Visualização
* **`ls`**: Lista simples.
* **`ls -a`**: Lista tudo, inclusive arquivos ocultos.
* **`ls -l`**: Formato longo (permite ver permissões e tamanhos).
* **`ls -lh`**: Tamanhos em formato legível (KB, MB, GB).
* **`ls -i`**: Mostra o número do *inode*.

### Paginação (Para listas grandes)
* **`ls | more`**: Permite ler a lista aos poucos. 
    * *`Enter` rola a linha e `q` sai da visualização.*

### Filtros e Curingas
* **`ls *`**: Lista o conteúdo atual e dos subdiretórios.
* **`ls a*`**: Lista tudo que começa com a letra "a".
* **`ls g?o*`**: O `?` substitui um caractere. (Ex: encontra `globo`, `geo`).
* **`ls arquivo[1-3]*`**: Busca por um intervalo. (Ex: `arquivo1`, `arquivo2`, `arquivo3`).

**Cores Padrão:** Azul (Diretório), Branco (Arquivo), Ciano (Link/Atalho).

---

## 6. Criação e Remoção

* **`touch nome_do_arquivo`**: Cria um arquivo novo e vazio.
* **`mkdir nome_da_pasta`**: Cria uma nova pasta.
* **`rmdir nome_da_pasta`**: Remove uma pasta (se estiver vazia).
* **`rm nome_do_arquivo`**: Deleta arquivos.
* **`rm -rf nome_da_pasta`**: Deleta pastas e todo o seu conteúdo à força. *(Cuidado!)*

---

## 7. Busca de Arquivos (`find`)

* **`find`**: Lista recursivamente tudo a partir de onde você está.
* **`find -name "nome"`**: Busca pelo nome exato do arquivo ou pasta.
