# Texturas de terreno

Biblioteca pública usada pelo editor de pintura do tabletop do Nyraldar.

- `manifest.json`: catálogo, versão de schema 1. O ID é o número permanente no fim do nome do material original.
- `textures/`: WebP em sRGB, lado máximo de 1024 px, qualidade 88 e transparência preservada.
- `thumbnails/`: prévias com lado máximo de 144 px. A transparência é mantida; o editor escolhe o fundo da prévia.

O campo `overlay` indica uma imagem com pixels transparentes. Os nomes dos materiais e dos pacotes são preservados; as categorias de navegação estão em português.

Os originais não ficam neste repositório. Para regenerar, execute na aplicação Nyraldar:

```powershell
node scripts/prepare-terrain-textures.mjs --source "CAMINHO_DO_ACERVO" --output "CAMINHO_DO_REPO_ASSETS/tabletop/terrain"
```

Antes de mudar a resolução ou compressão, acrescente `--sample` e use uma pasta de saída separada. Isso gera cinco materiais de comparação, versões de 2048 px, métricas e uma imagem com recortes em zoom de 2×. Texturas de 1024 px ficam mais suaves quando ampliadas além dessa resolução; os originais permitem preparar variantes maiores no futuro.

Sirva o catálogo e suas imagens pela mesma versão do repositório na CDN para manter os IDs e os arquivos correspondentes.
