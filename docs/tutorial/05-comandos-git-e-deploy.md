# 06. Comandos Git Essenciais e Versionamento

Até agora, você clonou o repositório, executou o código e fez algumas modificações locais. Chegou a hora de aprender como salvar essas alterações de forma estruturada usando o Git. Se você estivesse colaborando em um projeto ou quisesse ter um histórico seguro das suas versões, estes passos seriam cruciais.

## O Ciclo Básico do Git

O Git funciona com um ciclo principal para salvar suas alterações:

1.  **Modificar arquivos:** Você edita seu código no seu editor (Workspace).
2.  **Adicionar ao "Stage":** Você seleciona quais alterações quer incluir no próximo "pacote" de salvamento (`git add`).
3.  **"Comitar":** Você cria um "snapshot" (uma foto) permanente dessas alterações selecionadas, adicionando uma mensagem descritiva (`git commit`). Este snapshot é salvo localmente no seu repositório Git.
4.  **(Opcional, para colaboração/backup) Enviar para o Repositório Remoto:** Você envia seus commits locais para o GitHub (`git push`).

## Comandos Essenciais na Prática

Abra o terminal integrado do VS Code (ou seu terminal de preferência) na pasta do projeto `djlinkgen`.

1.  **`git status`**:
    *   **O que faz?** Mostra o estado atual do seu repositório: quais arquivos foram modificados, quais estão no "stage", etc. É o seu comando principal para saber "onde estou?".
    *   **Como usar:**
        ```bash
        git status
        ```
    *   Se você fez alterações nos passos anteriores, verá os arquivos modificados listados em vermelho (ou similar).

2.  **`git add <nome_do_arquivo>` ou `git add .`**:
    *   **O que faz?** Adiciona as alterações de um arquivo específico (ou todos os arquivos modificados com `.`) à área de "staging". Pense nisso como colocar os itens que você quer guardar em uma caixa antes de fechar a caixa.
    *   **Como usar (para um arquivo específico):**
        ```bash
        git add djlinkgen.py
        ```
    *   **Como usar (para todos os arquivos modificados no diretório atual e subdiretórios):**
        ```bash
        git add .
        ```
    *   Após usar `git add`, rode `git status` novamente. Você verá que os arquivos adicionados agora estão listados como "changes to be committed" (geralmente em verde).

3.  **`git commit -m "Sua mensagem descritiva aqui"`**:
    *   **O que faz?** Cria um "commit", que é um ponto de salvamento no histórico do seu projeto. A mensagem (`-m`) é crucial: ela deve descrever brevemente o que você alterou.
    *   **Como usar:**
        ```bash
        git commit -m "Modifiquei o texto de boas-vindas e o nome do arquivo de saída"
        ```
        (Use uma mensagem que reflita as alterações que você realmente fez!)
    *   Boas mensagens de commit são curtas, no imperativo (ex: "Corrige bug X", "Adiciona funcionalidade Y") e explicam o *porquê* da mudança, se não for óbvio.

4.  **`git log`**:
    *   **O que faz?** Mostra o histórico de commits do seu projeto, do mais recente ao mais antigo. Cada commit terá um identificador único (hash), o autor, a data e a mensagem.
    *   **Como usar:**
        ```bash
        git log
        ```
    *   Pressione `q` para sair da visualização do log.

## Enviando Alterações para o GitHub (Opcional por Agora)

Se você clonou o projeto de `neaigd/djlinkgen` e não é o proprietário, você não poderá enviar (`push`) suas alterações diretamente para lá (a menos que seja um colaborador). Para salvar suas próprias versões no GitHub, você precisaria primeiro fazer um "Fork" do repositório para sua própria conta GitHub e clonar o *seu fork*.

No entanto, se você estivesse trabalhando em seu próprio projeto ou em um fork seu, o comando seria:

*   **`git push origin main` (ou `git push origin master`):**
    *   **O que faz?** Envia seus commits locais (do branch `main` ou `master`) para o repositório remoto no GitHub (chamado `origin` por padrão).
    *   **Exemplo (NÃO EXECUTE SE VOCÊ CLONOU DIRETAMENTE DE `neaigd/djlinkgen` SEM FAZER FORK, pois provavelmente dará erro de permissão):**
        ```bash
        # git push origin main
        ```

**Para este tutorial, focar nos comandos `git status`, `git add`, `git commit` e `git log` é suficiente para entender o versionamento local.**

## Por Que Versionar?

*   **Histórico:** Você pode ver como seu projeto evoluiu e voltar para versões anteriores se algo der errado.
*   **Experimentação Segura:** Faça alterações drásticas em um branch (um conceito mais avançado do Git) sem medo de quebrar a versão principal estável.
*   **Colaboração:** O Git é a base para que múltiplas pessoas trabalhem no mesmo projeto de forma organizada.
*   **Backup:** Seus commits no GitHub servem como um backup do seu trabalho.

**Desafio:**
1.  Faça mais uma pequena alteração no arquivo `djlinkgen.py` (ex: adicione um comentário com seu nome).
2.  Use `git status` para ver a alteração.
3.  Use `git add djlinkgen.py` para adicionar a alteração ao stage.
4.  Use `git status` novamente para confirmar.
5.  Use `git commit -m "Adicionei meu nome como comentário no script"` para comitar.
6.  Use `git log` para ver seu novo commit no histórico.

Dominar esses comandos básicos do Git é uma habilidade fundamental para qualquer pessoa que trabalhe com código, mesmo que em projetos simples ou individuais.
