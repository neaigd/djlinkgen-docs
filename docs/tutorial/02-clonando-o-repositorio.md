# 02. Clonando o Repositório DJLinkGen

Agora que seu ambiente está configurado, o próximo passo é obter uma cópia local do projeto `djlinkgen`. Isso é feito através de um processo chamado "clonagem", utilizando o Git.

## O que é Clonar um Repositório?

Clonar um repositório significa criar uma cópia idêntica de um projeto hospedado no GitHub (ou outra plataforma similar) em sua máquina local. Essa cópia local incluirá todos os arquivos do projeto, bem como todo o histórico de alterações gerenciado pelo Git.

## Passos para Clonar:

1.  **Abra o Terminal (ou Git Bash):**
    *   No Windows, você pode usar o "Prompt de Comando", "PowerShell" ou o "Git Bash" (que é instalado junto com o Git).
    *   No macOS ou Linux, use o "Terminal".

2.  **Navegue até o Diretório Desejado:**
    Decida onde em seu computador você gostaria de salvar os arquivos do projeto. Use o comando `cd` (change directory) para navegar.
    Por exemplo, se você tem uma pasta chamada `Projetos` em seus Documentos:
    ```bash
    # Exemplo para Windows (pode variar)
    cd Documentos/Projetos

    # Exemplo para macOS/Linux
    cd ~/Documents/Projetos
    ```
    Se a pasta não existir, você pode criá-la com `mkdir Projetos` antes de usar `cd Projetos`.

3.  **Obtenha a URL do Repositório:**
    *   Vá para a página do repositório `djlinkgen` no GitHub: [https://github.com/neaigd/djlinkgen](https://github.com/neaigd/djlinkgen) (substitua `neaigd` pelo nome de usuário correto se for um fork).
    *   Clique no botão verde "<> Code".
    *   Certifique-se de que a aba "HTTPS" está selecionada.
    *   Copie a URL exibida. Deve ser algo como `https://github.com/neaigd/djlinkgen.git`.

4.  **Clone o Repositório:**
    No terminal, digite o comando `git clone` seguido da URL que você copiou:
    ```bash
    git clone https://github.com/neaigd/djlinkgen.git
    ```
    Pressione Enter. O Git fará o download do projeto para uma nova pasta chamada `djlinkgen` dentro do diretório atual. Você verá algumas mensagens indicando o progresso.

5.  **Acesse a Pasta do Projeto:**
    Após a clonagem ser concluída com sucesso, navegue para dentro da pasta do projeto recém-criada:
    ```bash
    cd djlinkgen
    ```

## Verificando o Sucesso

Dentro da pasta `djlinkgen`, você pode listar os arquivos (usando `dir` no Windows ou `ls` no macOS/Linux) para ver se o conteúdo do projeto está lá.

Você também pode abrir esta pasta no VS Code:
*   Com o VS Code aberto, vá em "File" > "Open Folder..." e selecione a pasta `djlinkgen`.
*   Ou, se você estiver no terminal dentro da pasta `djlinkgen`, pode digitar `code .` (o ponto significa "diretório atual") e pressionar Enter.

Parabéns! Você clonou com sucesso o repositório `djlinkgen` e está pronto para explorar e executar o código.
