# 01. Configuração do Ambiente

Para começar a explorar o projeto `djlinkgen` e, mais amplamente, para dar seus primeiros passos no desenvolvimento com Python e IA, você precisará configurar seu ambiente de trabalho. Não se preocupe, vamos guiá-lo em cada etapa.

## Softwares Necessários:

1.  **Python:**
    *   **O que é?** Uma linguagem de programação popular, conhecida por sua sintaxe clara e vasta quantidade de bibliotecas, sendo amplamente utilizada em IA.
    *   **Como instalar:**
        *   Visite o site oficial do Python: [python.org](https://www.python.org/downloads/)
        *   Baixe o instalador mais recente para o seu sistema operacional (Windows, macOS, Linux).
        *   Durante a instalação no Windows, **certifique-se de marcar a opção "Add Python to PATH"** ou similar. Isso facilitará a execução de comandos Python no terminal.
        *   Após a instalação, abra um terminal (Prompt de Comando ou PowerShell no Windows, Terminal no macOS/Linux) e digite `python --version` ou `python3 --version`. Você deverá ver a versão instalada.

2.  **Git:**
    *   **O que é?** Um sistema de controle de versão distribuído. Essencial para rastrear mudanças no código, colaborar com outros e gerenciar projetos de software.
    *   **Como instalar:**
        *   Visite o site oficial do Git: [git-scm.com](https://git-scm.com/downloads)
        *   Baixe e instale a versão para seu sistema operacional. As opções padrão da instalação geralmente são suficientes.
        *   Após a instalação, abra um terminal e digite `git --version`. Você deverá ver a versão instalada.

3.  **VS Code (Visual Studio Code):**
    *   **O que é?** Um editor de código-fonte leve, porém poderoso, desenvolvido pela Microsoft. Ele possui excelente suporte para Python, Git e inúmeras extensões que facilitam o desenvolvimento.
    *   **Como instalar:**
        *   Visite o site oficial do VS Code: [code.visualstudio.com](https://code.visualstudio.com/download)
        *   Baixe e instale a versão para seu sistema operacional.
    *   **Extensões Úteis (instale dentro do VS Code):**
        *   **Python (da Microsoft):** Essencial para desenvolvimento Python, oferece linting, debugging, intellisense, etc.
        *   **Pylance (da Microsoft):** Melhora a experiência com Python, oferecendo análise de código mais rápida e rica.
        *   **GitLens — Git supercharged:** Aprimora a integração com o Git, permitindo visualizar o histórico de alterações diretamente no editor.

4.  **Conta no GitHub:**
    *   **O que é?** Uma plataforma de hospedagem de código-fonte com controle de versão usando Git. É amplamente utilizada para projetos de código aberto e colaboração. O `djlinkgen` está hospedado lá.
    *   **Como criar:**
        *   Visite [github.com](https://github.com/) e crie uma conta gratuita.

## Configuração Inicial do Git (Opcional, mas recomendado)

Após instalar o Git, é uma boa prática configurar seu nome de usuário e e-mail. Isso será usado para identificar seus `commits`. Abra um terminal e digite:

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seuemail@exemplo.com"
```
Substitua "Seu Nome" e "seuemail@exemplo.com" com seus dados.

Com esses componentes instalados e configurados, você está pronto para o próximo passo: clonar o repositório `djlinkgen` para sua máquina local!
