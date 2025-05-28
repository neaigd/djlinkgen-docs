# djlinkgen — IA Generativa para o Direito

Bem-vindo ao `djlinkgen`! Este `README.md` fornece um guia completo para configurar seu ambiente, construir a documentação, personalizar o site e entender o processo de deploy automatizado para o GitHub Pages, que inclui uma página de destino personalizada e a documentação detalhada gerada com MkDocs.

## Visão Geral da Estrutura e Deploy

Este projeto utiliza:
-   Uma **página de destino personalizada** (`index.html` na raiz do projeto) como ponto de entrada principal do site.
-   **MkDocs** para gerar um site de documentação estático a partir dos arquivos Markdown localizados no diretório `docs/`.
-   **GitHub Actions** para automatizar o build e o deploy do site combinado (página de destino + documentação MkDocs) para o GitHub Pages.

Quando implantado, a estrutura no GitHub Pages será:
-   `https://<username>.github.io/<repository>/`: Exibirá a página de destino personalizada (`index.html`).
-   `https://<username>.github.io/<repository>/docs/`: Exibirá a documentação gerada pelo MkDocs.

## Pré-requisitos

Antes de começar localmente, certifique-se de ter Python e pip (gerenciador de pacotes Python) instalados.

Para construir o site localmente, incluindo todos os plugins utilizados neste projeto (conforme definido em `mkdocs.yml` e no workflow de deploy), instale:
```bash
pip install mkdocs mkdocs-material mkdocs-mermaid2 mkdocs-jupyter
```

## Estrutura do Projeto

-   `mkdocs.yml`: Arquivo de configuração principal do MkDocs. Define navegação, tema, plugins para a documentação em `/docs/`.
-   `docs/`: Contém os arquivos Markdown da documentação.
    -   `docs/index.md`: Página inicial da *documentação MkDocs*.
    -   `docs/css/extra.css` (Opcional): Para CSS personalizado da documentação MkDocs.
-   `index.html`: Página de destino HTML personalizada (landing page) na raiz do projeto.
-   `.github/workflows/mkdocs-deploy.yml`: Workflow do GitHub Actions que automatiza o build e deploy.
-   `site/` (Gerado localmente por `mkdocs build`): Contém a documentação MkDocs construída. **Não é versionado.**

## Desenvolvimento e Visualização Local

### 1. Visualizar a Documentação MkDocs
Para visualizar e trabalhar na documentação MkDocs (o conteúdo dentro de `/docs/`):
1.  Navegue até a raiz do projeto.
2.  Execute:
    ```bash
    mkdocs serve
    ```
3.  Abra seu navegador em `http://127.0.0.1:8000`. Alterações nos arquivos em `docs/` ou em `mkdocs.yml` recarregarão o site automaticamente.

### 2. Visualizar a Página de Destino Personalizada (`index.html`)
Abra o arquivo `index.html` diretamente no seu navegador para visualizar e testar as alterações.

## Processo de Deploy Automatizado para GitHub Pages

O deploy é gerenciado pelo workflow em `.github/workflows/mkdocs-deploy.yml`. Ele é acionado a cada `push` para a branch `main`.

**O que o workflow faz:**
1.  **Checkout do Código:** Baixa a versão mais recente do seu repositório.
2.  **Configura Python:** Prepara o ambiente Python.
3.  **Instala Dependências:** Instala `mkdocs`, `mkdocs-material`, `mkdocs-mermaid2`, e `mkdocs-jupyter`.

4.  **Constrói a Documentação MkDocs:** Executa `mkdocs build -d _mkdocssite` para gerar os arquivos da documentação em um diretório específico.
5.  **Prepara o Diretório de Deploy Final (`public/`):**
    *   Copia a `index.html` (página de destino personalizada) para a raiz deste diretório (`public/index.html`).
    *   Copia o conteúdo da documentação MkDocs construída (de `_mkdocssite`) para um subdiretório (`public/docs/`).
    *   (Opcional) Copia outros arquivos estáticos (como `logo.png`, se existir na raiz) para o diretório `public/`.
6.  **Implanta no GitHub Pages:** Envia o conteúdo do diretório `public/` para a branch `gh-pages` do seu repositório usando a action `peaceiris/actions-gh-pages`.

O GitHub Pages então serve o conteúdo da branch `gh-pages`.

**(Nota: O workflow em `.github/workflows/mkdocs-deploy.yml` implementa esta estratégia. Consulte o arquivo para ver os detalhes e comandos exatos.)**

## Personalização

### 1. Página de Destino (`index.html`)
-   **Logo:** Edite o arquivo `index.html`. Procure pelo comentário `LOGO PLACEHOLDER`. Você pode:
    1.  Substituir o `div.logo-placeholder` por uma tag `<img>` apontando para sua imagem de logo (ex: `<img src="logo.png" alt="djlinkgen Logo">`). Coloque o arquivo `logo.png` na raiz do projeto e certifique-se de que ele é copiado para o diretório `public` durante o passo "Prepare deployment directory" no workflow do GitHub Actions (descomentando a linha relevante em `mkdocs-deploy.yml`).
    2.  Ou, usar CSS para definir o `background-image` do `div.logo-placeholder` (lembre-se que o caminho da imagem no CSS será relativo à localização do `index.html`).
-   **Conteúdo e Estilo:** Modifique o HTML e o CSS dentro de `index.html` conforme necessário.

### 2. Documentação MkDocs (`/docs/`)
-   **`mkdocs.yml`:**
    *   **Tema e Paleta (`theme`):** Configure nome do tema (`material`), idioma (`language`), cores (`palette`), fontes (`font`), logo para a barra de navegação da documentação (`logo`), favicon (`favicon`).
    *   **Recursos do Tema (`features`):** Habilite/desabilite recursos do tema Material.
    *   **Extensões Markdown (`markdown_extensions`):** Adicione funcionalidades ao Markdown.
-   **CSS Personalizado para Documentação:**
    *   Crie/edite `docs/css/extra.css`.
    *   Referencie em `mkdocs.yml`:
        ```yaml
        extra_css:
          - css/extra.css
        ```
-   **Modificando Templates do Tema MkDocs (Avançado):**
    *   Crie um diretório (ex: `docs/overrides` ou `overrides/` na raiz) e adicione seus templates modificados.
    *   Referencie em `mkdocs.yml`: `theme: name: material, custom_dir: docs/overrides`.

---

Este `README.md` visa fornecer um guia completo para gerenciar e implantar o projeto `djlinkgen`.
