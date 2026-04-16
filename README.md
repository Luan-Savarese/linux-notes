# 🐧 Linux Basics

Este repositório contém minhas anotações de estudo sobre fundamentos do Linux, comandos de terminal e navegação no sistema de arquivos.

O objetivo é documentar comandos e conceitos aprendidos durante meus estudos contínuos em infraestrutura, Linux e cibersegurança.

---

## 📌 Tópicos Abordados

* Fundamentos do terminal Linux
* Navegação no sistema de arquivos
* Privilégios de usuário
* Comandos básicos de administração de sistema

---

## 🛠️ Exemplos de Comandos Rápidos

### Informações Básicas
* `ip a` → Exibe os endereços IP da máquina.
* `date` → Mostra a data e a hora atuais do sistema.
* `clear` → Limpa a tela do terminal.
* `pwd` → Mostra o diretório atual onde você está.

### Navegação
* `cd` → Entra em um diretório ou volta para a *home*.
* `cd ..` → Volta um nível (uma pasta para trás).
* `cd /` → Vai para o diretório raiz do sistema.

### Gerenciamento e Listagem (`ls`)
* `ls` → Lista os arquivos e diretórios.
* `touch nome_do_arquivo.extensao` → Cria um novo arquivo vazio (Ex: `touch arquivo.txt`).

#### Paginação de Resultados (Para listas grandes)
Quando a listagem de arquivos for muito grande e não couber na tela:
* `ls | more` → Permite ler o conteúdo aos poucos. 
    * *Aperte `Enter` para rolar a tela linha por linha.*
    * *Aperte `q` ou `Shift + c` para sair da paginação.*

#### Filtros (Uso de Curingas)
Você pode usar curingas para buscar padrões específicos:
* **Filtrar pela primeira letra:** `ls a*` (Lista tudo que começa com "a").
* **Filtrar por partes da palavra:** `ls g?o*` (A interrogação substitui um único caractere. Lista, por exemplo, "globo", "geo", etc.).
* **Filtrar por um intervalo (Regex básico):** `ls arquivo[1-3]*` (Lista apenas `arquivo1`, `arquivo2` e `arquivo3`).

---

## ⚠️ Notas Importantes

Os terminais Linux são **Case Sensitive**, o que significa que letras maiúsculas e minúsculas são tratadas como caracteres diferentes.

*Exemplo prático:*
`Arquivo.txt` é completamente diferente de `arquivo.txt`.

---

## 👨‍💻 Autor

**Luan Savarese**
