# QRCodeCreator

Aplicação web simples, num único ficheiro HTML, para gerar QRCodes diretamente no browser — sem servidor, sem build, sem dependências para instalar.

## Funcionalidades

- **Gerar a partir de um URL** — escreve ou cola um endereço (com ou sem `https://`, que é adicionado automaticamente) e gera o QRCode com um clique ou a tecla Enter.
- **Gerar a partir de um ficheiro** — arrasta um ficheiro para a zona de upload (ou clica para escolher um) e o conteúdo é codificado diretamente no QRCode em base64. Não há upload para nenhum servidor: tudo acontece no browser.
- **Limite de tamanho protegido** — ficheiros demasiado grandes para caberem de forma fiável num QRCode (acima de ~2KB) são recusados com uma mensagem clara, em vez de gerarem um código ilegível.
- **Download em PNG** — depois de gerado, o QRCode pode ser descarregado como imagem PNG com um clique.
- **Interface em português**, limpa e responsiva, com tema claro.

## Como usar

1. Abre o [index.html](index.html) diretamente no browser (não precisa de servidor).
2. Escolhe o separador **URL** ou **Ficheiro**.
3. Introduz o URL ou seleciona/arrasta o ficheiro.
4. O QRCode aparece de imediato na pré-visualização.
5. Clica em **Descarregar PNG** para guardar a imagem.

## Tecnologia

- **HTML + CSS + JavaScript puro** — sem frameworks, sem passos de build.
- [qrcodejs](https://github.com/davidshimjs/qrcodejs) (via CDN) para a geração dos QRCodes.
- Leitura de ficheiros feita com a API `FileReader` do browser (`readAsDataURL`).

## Limitações

- QRCodes têm uma capacidade de dados limitada; ficheiros grandes não cabem de forma legível — o limite prático usado nesta app é de ~2KB.
- A leitura de um QRCode gerado a partir de um ficheiro depende de o leitor conseguir interpretar dados base64 em bruto (não é um link, é o próprio conteúdo).
