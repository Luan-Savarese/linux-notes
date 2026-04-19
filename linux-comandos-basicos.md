# 🐧 Guia de Comandos e Fundamentos do Linux

Este documento reúne os principais conceitos e comandos para navegação, gerenciamento de arquivos, administração de usuários e controle de permissões em sistemas Linux.

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

## 2. Atalhos e Utilitários do Terminal

* **Autocompletar com `TAB`:** Pressione `TAB` uma vez para completar ou duas para ver as opções.
* **`clear`** (ou `Ctrl + L`): Limpa a tela do terminal.
* **`history`**: Mostra o histórico de todos os comandos digitados anteriormente no terminal.

---

## 3. Visualização e Edição de Texto

* **`echo`**: Imprime um texto ou o valor de uma variável na tela (Ex: `echo "Olá Mundo"`).
* **`nano`**: Abre o Nano, um editor de texto simples e direto executado diretamente no terminal (Ex: `nano arquivo.txt`).
* **`cat`**: Concatena e exibe o conteúdo de um arquivo inteiro no terminal de uma só vez (Ex: `cat arquivo.txt`).

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

* **`ls`**: Lista simples.
* **`ls -a`**: Lista tudo, inclusive arquivos ocultos.
* **`ls -l`**: Formato longo (permite ver permissões e tamanhos).
* **`ls -lh`**: Tamanhos em formato legível (KB, MB, GB).
* **`ls | more`**: Permite ler listas grandes aos poucos (`Enter` rola, `q` sai).
* **`ls *`**: Lista o conteúdo atual e dos subdiretórios.
* **`ls a*` / `ls g?o*` / `ls arq[1-3]*`**: Filtros com curingas para buscas específicas.

---

## 6. Criação e Remoção

* **`touch nome_do_arquivo`**: Cria um arquivo novo e vazio.
* **`mkdir nome_da_pasta`**: Cria uma nova pasta.
* **`rmdir nome_da_pasta`**: Remove uma pasta (se estiver vazia).
* **`rm nome_do_arquivo`**: Deleta arquivos.
* **`rm -rf nome_da_pasta`**: Deleta pastas e todo o seu conteúdo à força. *(Cuidado!)*

---

## 7. Gerenciamento de Usuários e Grupos

Comandos essenciais para administração de identidades no sistema:

* **`sudo`**: Executa um comando temporariamente com privilégios de superusuário (root).
* **`su usuário`**: Alterna a sessão para outro usuário. (Ex: `su root` para virar administrador).
* **`passwd usuário`**: Define ou altera a senha de um usuário. (Ex: `sudo passwd root` ou `passwd carlos`).

### Criação, Modificação e Exclusão
* **`useradd`**: Cria um novo usuário no sistema. 
  * *Exemplo:* `useradd carlos`
* **`usermod`**: Modifica as propriedades de um usuário existente.
  * *Exemplo:* `usermod -G adm,sudo mariana` (Adiciona a usuária Mariana aos grupos `adm` e `sudo`).
* **`userdel`**: Deleta um usuário.
  * *Exemplo:* `userdel -r -f roberto` (Força a exclusão `-f` do usuário Roberto e apaga o seu diretório pessoal `-r`).

### Grupos e Arquivos de Sistema
* **`groupadd nome_do_grupo`**: Cria um novo grupo de usuários.
* **`gpasswd nome_do_grupo`**: Administra o grupo (adiciona/remove membros e senhas).
* **`cat /etc/passwd`**: Exibe o arquivo do sistema que lista todos os usuários cadastrados e suas configurações básicas.
* **`cat /etc/group`**: Exibe o arquivo que lista todos os grupos do sistema e seus membros.

---

## 8. Permissões de Arquivos e Diretórios (`chmod`)

No Linux, o controle de acesso é dividido em três categorias: **Dono (User)**, **Grupo (Group)** e **Outros (Others)**. As permissões podem ser definidas por letras ou números (sistema octal).

### Tabela de Permissões
| Permissão | Símbolo | Valor Numérico | Descrição |
| :--- | :---: | :---: | :--- |
| **Read** | `r` | **4** | Permite ler/visualizar o arquivo ou listar o diretório. |
| **Write** | `w` | **2** | Permite alterar/gravar no arquivo ou criar/deletar no diretório. |
| **Execute** | `x` | **1** | Permite executar o arquivo (scripts/programas) ou acessar o diretório. |
| **Nenhuma** | `-` | **0** | Nenhuma permissão concedida. |

### Usando o `chmod`
O comando `chmod` altera essas permissões. A forma mais comum é usar a soma dos valores numéricos para o Dono, Grupo e Outros.

* *Exemplo:* `chmod 777 carta.txt`
  * O número `7` é a soma de **4 (Read) + 2 (Write) + 1 (Execute)**.
  * Como são três setes (`777`), significa permissão total (Leitura, Escrita e Execução) concedida para o Dono, para o Grupo e para Outros. 
  * *Nota de Segurança:* O uso do `777` deve ser evitado em ambientes de produção, pois permite que qualquer pessoa no sistema modifique ou execute o arquivo.

---

## 9. Serviços e Configurações Essenciais

* **`sshd_config`**: Arquivo de configuração principal do serviço de acesso remoto via SSH (Geralmente localizado em `/etc/ssh/sshd_config`). É nele que configuramos portas, bloqueamos acesso root direto e aplicamos regras críticas de cibersegurança para acessos externos. Pode ser editado com `sudo nano /etc/ssh/sshd_config`.
