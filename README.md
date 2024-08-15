# Guia Linux :book:

- Neste Guia, vou apresentar soluções para as dúvidas mais comuns de um ambiente Linux, vou dar preferência a mostrar as soluções pelo terminal, para que você fique mais familiarizado com os comandos do mundo Unix.

## Sumário

[Transferência de Arquivos](#transferencia-de-arquivos)

## Transferência de Arquivos :recycle:

- ### Existem dois principais modos de transferir arquivos no Linux, com os comandos `cp` e `rsync`:

  - `cp -r /caminho/origem /caminho/destino`

      - A opção `-r` (ou `--recursive`) permite que o cp copie recursivamente todo o conteúdo da pasta, incluindo subdiretórios e arquivos.

  - `rsync -av /caminho/origem /caminho/destino`

      - `-a` (ou `--archive`): Essa é uma das opções mais poderosas. Ela ativa um modo "recursivo" que preserva as seguintes propriedades durante a cópia:

        - Recursividade (-r)
        - Preservação de links simbólicos (-l)
        - Preservação de permissões (-p)
        - Preservação de timestamps (-t)
        - Preservação de grupos (-g)
        - Preservação de propriedades especiais, como dispositivos e arquivos especiais (-D)

  Em resumo, o modo -a faz uma cópia "completa" de tudo o que está dentro do diretório de origem, mantendo as características originais dos arquivos e diretórios.

`-v` (ou `--verbose`): Habilita a "verbosidade", ou seja, faz com que o rsync mostre informações detalhadas sobre os arquivos que estão sendo copiados. Isso é útil para acompanhar o progresso e ver o que está sendo transferido.

`-P`: Uma forma abreviada que combina `--progress` e `--partial`. O `--partial` preserva arquivos parcialmente transferidos caso a transferência seja interrompida, permitindo retomar do ponto em que parou.

`rsync -avP /caminho/origem /caminho/destino`

`--info=progress2`: Mostra o progresso total da transferência, incluindo o percentual concluído e a velocidade de transferência. Essa opção é mais clara para ver o progresso geral.

    `rsync -av --info=progress2 /caminho/origem /caminho/destino`
