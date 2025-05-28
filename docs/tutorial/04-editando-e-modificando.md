# 04. Editando e Modificando o Código

Agora que você executou o `djlinkgen` e viu seu comportamento básico, é hora de "sujar as mãos" e começar a interagir com o código. A melhor maneira de aprender é experimentando.

## Abrindo o Código no VS Code

Se ainda não o fez, abra a pasta do projeto `djlinkgen` no VS Code. Você verá a estrutura de arquivos no painel esquerdo (Explorer). Localize o arquivo Python principal (ex: `djlinkgen.py`). Clique nele para abri-lo no editor.

## Entendendo a Estrutura do Código

Antes de modificar, tente entender o que cada parte do código faz:

1.  **`import` statements:** No início do arquivo, você verá linhas como `import os` ou `import json`. Elas trazem funcionalidades de bibliotecas externas ou módulos padrão do Python para dentro do seu script.
2.  **Funções:** Blocos de código definidos com `def nome_da_funcao():`. Funções agrupam lógica reutilizável. Tente identificar o propósito de cada função pelos seus nomes e pelos comentários (linhas que começam com `#`).
3.  **Variáveis:** Nomes que armazenam dados (texto, números, listas, etc.).
4.  **Lógica Principal:** A parte do script que não está dentro de uma função, ou a seção `if __name__ == '__main__':`, é geralmente onde a execução principal do programa acontece.

**Use os comentários no código e os nomes das variáveis/funções como pistas!**

## Fazendo Pequenas Modificações Seguras

Comece com alterações simples para ganhar confiança:

1.  **Mudar Textos (Strings):**
    *   Procure por textos que são impressos no terminal (dentro de `print("...")`) ou que são usados para gerar a saída do `djlinkgen`.
    *   **Exemplo:** Se o script imprime `print("Bem-vindo ao DJLinkGen!")`, tente mudar para `print("Explorando o DJLinkGen para Juristas!")`.
    *   Salve o arquivo (Ctrl+S ou Cmd+S) e execute o script novamente (como no Passo 03) para ver sua alteração.

2.  **Alterar Nomes de Arquivos Gerados:**
    *   Se o `djlinkgen` cria um arquivo de saída (ex: `links.html` ou `documento.txt`), procure no código onde esse nome de arquivo é definido.
    *   **Exemplo:** Você pode encontrar algo como `nome_arquivo_saida = "links.html"`. Tente mudar para `nome_arquivo_saida = "meus_links_juridicos.html"`.
    *   Salve e execute. Verifique se o novo arquivo foi criado com o nome alterado.

3.  **Modificar Parâmetros de Funções (com cuidado):**
    *   Se uma função é chamada com certos valores (argumentos), como `gerar_link("Petição Inicial", "caminho/para/peticao.pdf")`, tente alterar esses valores.
    *   **Atenção:** Isso pode quebrar o programa se os novos valores não forem do tipo esperado pela função. Faça backup mental (ou com Git) antes de grandes mudanças.

## Usando a IA para Sugerir Melhorias (Introdução)

Este é um bom momento para começar a usar uma ferramenta de IA (ChatGPT, Gemini, etc.) como sua assistente:

*   **Peça para Explicar um Trecho:** Se uma parte do código não está clara, copie e cole na IA e peça uma explicação "como se eu fosse um advogado aprendendo Python".
*   **Sugira uma Pequena Refatoração:**
    *   **Prompt Exemplo:** "Tenho esta função Python no meu projeto `djlinkgen`: `[cole a função]`. Eu sou um profissional do direito aprendendo Python. Há alguma maneira simples de tornar este código mais legível ou um pouco mais eficiente, sem mudar drasticamente sua funcionalidade?"
    *   Analise a sugestão da IA. Tente entendê-la e, se se sentir confortável, implemente-a.

## A Importância de Testar Após Cada Mudança

Sempre que fizer uma alteração, por menor que seja:
1.  **Salve** o arquivo.
2.  **Execute** o script novamente.
3.  **Observe** se o resultado é o esperado e se não surgiram novos erros.

Este ciclo de "editar -> salvar -> testar" é fundamental no desenvolvimento de software.

## Desafio

1.  Identifique uma string (texto) no código `djlinkgen.py` que é usada para gerar algum tipo de saída (seja no terminal ou em um arquivo). Mude essa string para algo relevante para sua área do Direito.
2.  Se o projeto gerar um arquivo, mude o nome do arquivo de saída.
3.  Execute o script e verifique suas alterações.

Lembre-se: o objetivo é aprender e experimentar em um ambiente seguro. Se algo der errado, você sempre pode voltar à versão anterior do código (especialmente se estiver usando Git, que veremos mais adiante).
