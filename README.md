# Nyraldar — Assets

Imagens do projeto **Nyraldar**, mantidas fora do repositório da aplicação.

Elas ficam aqui por um motivo prático: imagem é arquivo binário, e o Git guarda
uma cópia inteira de cada versão para sempre. Misturar isso com o código faz o
histórico do repositório principal crescer sem parar e nunca encolher. Separando,
o repositório da aplicação continua leve.

## Como é servido

Via [jsDelivr](https://www.jsdelivr.com/), CDN gratuito para repositórios
públicos do GitHub, sem limite de banda e com cache global.

```
https://cdn.jsdelivr.net/gh/GuardaChuva22/nyraldar-assets@main/items/arma/adaga.webp
```

A aplicação nunca escreve essa URL à mão: cada item guarda apenas o caminho
relativo (`arma/adaga.webp`) e o build monta a URL completa. Trocar de CDN é
mudar uma constante em um lugar só.

## Estrutura

```
items/<categoria>/<slug>.webp
```

A categoria vem do campo `type` do item e o slug vem do nome, sem acentos:

| Categoria    | Itens |
| ------------ | ----- |
| provisoes    | 190   |
| recurso      | 166   |
| arma         | 128   |
| ferramenta   | 121   |
| flora        | 101   |
| tesouro      | 68    |
| outro        | 51    |
| defesa       | 50    |
| magico       | 40    |
| consumivel   | 26    |
| pocao        | 15    |
| municao      | 15    |

## Formato

Tudo em WebP. Os arquivos que vieram do Firebase Storage já em WebP foram
preservados sem recompressão; os que ainda estavam em PNG foram convertidos com
`sharp` (qualidade 80), o que reduziu esses arquivos de 428 MB para 30 MB sem
perda visível.

## Adicionando imagens

Mantenha o padrão `items/<categoria>/<slug>.webp`, sempre em WebP e sem acentos
no nome. Depois de dar push, o caminho já fica disponível no jsDelivr — vale
lembrar que o CDN faz cache agressivo, então para forçar atualização de um
arquivo existente é melhor usar um nome novo do que sobrescrever.
