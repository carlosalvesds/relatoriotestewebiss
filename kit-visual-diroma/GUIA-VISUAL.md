# Guia visual — diRoma

Extraído dos arquivos locais do projeto Consulta NF-e. O CSS aplicado pela aplicação é a referência principal; a configuração Streamlit incluída contém os valores de base, antes das substituições feitas pelo CSS.

## Cores

| Papel | Claro | Escuro |
| --- | --- | --- |
| Fundo da página | `#f0f7ff` | `#101923` |
| Superfície / campos | `#fff` | `#182635` |
| Fundo suave | `#e4f2ff` | `#203245` |
| Hover suave | `#ccecff` | `#29435b` |
| Texto principal | `#142e4d` | `#f1f5f9` |
| Texto secundário | `#285984` | `#c1d0de` |
| Borda dos campos | `#9ac9ed` | `#354d63` |
| Legenda final | `#000` | `#ffffff` |
| Borda estrutural | `#0080D3` | `#405970` |
| Títulos | `#0080D3` | `#0080D3` |
| Botão principal | `#0149AF` | `#0149AF` |
| Ciano / ação secundária | `#00B2E2` | `#00B2E2` |

Hover do botão principal: #003c91, texto branco. Botão secundário: #00B2E2, texto #082b46 e hover #009cc7. Foco visível: contorno ciano de 3px, afastamento de 3px.

## Tipografia e composição

- Arial, sans-serif no cabeçalho, abas e conteúdo personalizado. Os demais widgets usam o sans-serif padrão do Streamlit; não há fonte personalizada para instalar.
- Título principal: 25px, peso 600. Subtítulo: 13px. Seções: 15px, peso 600. Subseções: 13px. Texto de dados: 13px, entrelinha 1,3. Rótulos e cabeçalhos de tabela: 12px.
- Conteúdo centralizado, largura máxima 1180px. Espaçamento externo desktop: 4,5rem 1,5rem 2rem, considerando a estrutura do Streamlit; adaptar o topo ao cabeçalho do destino.
- Visual compacto de portal administrativo, superfícies planas, bordas finas e organização em grupos. Sem sombras fortes ou gradientes.
- Cabeçalho claro: fundo branco, padding 18px, gap 28px, raio 10px; borda de 1px #9ac9ed, faixa esquerda de 5px #0149AF e inferior de 3px #00B2E2.
- Cabeçalho escuro: fundo transparente, padding 0 0 18px, sem arredondamento nem faixa lateral; borda inferior de 2px #405970.
- Grupos de campos: grid, gap 7px vertical / 6px horizontal, padding 6px, borda 1px, raio 5px e fundo suave. No escuro: fundo transparente, raio zero e borda estrutural.
- Valores: fundo de superfície, borda fina, padding 4px 6px e altura mínima 26px. Rótulos acima dos valores.
- Botões principais: azul profundo, texto branco e raio 6px.
- Abas: próximas umas das outras, cantos retos, altura mínima 35px, padding 6px 10px. Ativa clara: azul profundo, texto branco em negrito, linha inferior interna ciano de 3px. Ativa escura: fundo de superfície, texto ciano e sem linha interna.
- Painel de abas: superfície, borda fina, padding 16px 10px 10px. Tabelas: bordas nos campos, cabeçalhos discretos e rolagem horizontal local quando necessário.
- Upload: fundo suave e borda azul tracejada. Grupos expansíveis: resumo com fundo suave e detalhes com padding 8px.

## Logo

`assets/diroma-logo.png` é o arquivo original efetivamente carregado por app.py, com 3474 × 3474 pixels e fundo branco. A imagem contém o desenho e o texto “diRoma hotéis & parques”; não reconstruir com fontes.

O projeto exibe a imagem em uma caixa branca de 200 × 124px, raio 6px, com object-fit: cover; no celular, 170 × 106px. Isso recorta parte das margens brancas do arquivo quadrado. Reproduzir esse enquadramento para manter fidelidade, verificando que toda a marca continue visível. Não esticar, recolorir ou inverter a logo no tema escuro.

## Responsividade

Breakpoint de 700px. Abaixo dele: cabeçalho em coluna, alinhado à esquerda, gap 12px; padding externo 4rem 0,6rem 1rem; campos em duas colunas, com campos longos ocupando toda a largura. Resumos complexos se reorganizam verticalmente. Para telas ainda menores, adaptar o grid para evitar corte de conteúdo.

## Integração

`tema/tokens.css` fornece variáveis independentes de framework. Usar data-theme="light" ou data-theme="dark" no elemento raiz. Este arquivo contém somente tokens; os componentes precisam receber estilos equivalentes aos descritos aqui. `tema/tokens.json` contém as duas paletas completas.

Os arquivos em `referencia/` preservam os estilos originais. Seletores data-testid="st..." e classes stTabs são específicos do Streamlit: traduzir para os componentes do destino em vez de copiá-los cegamente. As regras estruturais do modo escuro também precisam ser adaptadas; trocar somente os tokens não reproduz todo o tema.
