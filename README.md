# attack-shark-v4-R82HE-FRONT

Este repositório contém **somente o front-end já buildado** (arquivos estáticos) + assets/configs de marca, extraídos do bundle do app.

Objetivo: deixar um pacote enxuto para você usar no Bolt/refazer a UI sem precisar carregar o restante do Electron (executáveis, DLLs, locales etc.).

## Sobre o tamanho (Bolt)

Algumas ferramentas (ex.: Bolt) têm limite de tamanho na importação do repo.

- `main` (padrão): versão **reduzida** para caber nesses limites (mantém assets/configs; remove JS bundle e fontes pesadas).
- `full`: versão **completa** (inclui `app/dist/js` e fontes).

Para pegar a versão completa:

`git checkout full`

## O que tem aqui

- `app/dist/` — front-end buildado (HTML/CSS/JS/assets)
- `app/company/` — logos/imagens/configs por empresa
- `app/APPVersion.json` e `app/CurrentCompany.json` — metadados usados pelo app

## Preview local (opcional)

Como isso é estático, dá para abrir direto no browser, mas o ideal é servir via HTTP:

- Python: `python -m http.server 5173` (na pasta raiz do repo) e abra `http://localhost:5173/app/dist/`
- Node: `npx serve .` e abra `/app/dist/`

## Como usar no Bolt

- Aponte o Bolt para a raiz deste repo.
- Use `app/dist/index.html` como referência do que existe hoje (rotas, assets, estrutura do build).
- Reaproveite os arquivos de `app/company/` (logo, imagens e configs) para manter a identidade visual.

## Observações

- Isso **não** é o código-fonte original (não tem `src/`). É a saída final do build.
- Para “refazer o front”, o caminho mais saudável é criar um novo projeto (React/Vite/etc.) e gerar um novo `dist` compatível.
- O app completo (Electron/bundle) fica no repo principal: https://github.com/ferpgshy/attack-shark-v4-R82HE
