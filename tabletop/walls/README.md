# Paredes do tabletop

Materiais de parede desenhados pela mesa 2D do Nyraldar sobre as linhas de parede da cena.

- `manifest.json`: catálogo, versão de schema 1. `pxPerUnit` é quantos pixels das peças valem um quadrado da mesa.
- Uma pasta por material, com o id permanente que a cena guarda em `wallSkin`:
  - `trecho-N.webp`: trechos que emendam consigo mesmos na horizontal; a mesa os repete ao longo da parede e sorteia um por parede. Têm `pad` pixels transparentes em cima e embaixo.
  - `ponta.webp`: posta onde a parede termina solta, desenhada como a ponta direita.
  - `pilar.webp`: posto nas quinas e cruzamentos.
  - `miniatura.webp`: prévia do seletor.

Os originais (pacotes Forgotten Adventures) não ficam neste repositório. Para regenerar, execute na aplicação Nyraldar:

```powershell
node scripts/pack-wall-skins.mjs --source "CAMINHO_DO_ACERVO" --output "CAMINHO_DO_REPO_ASSETS/tabletop/walls"
```

A lista curada de materiais e peças fica no próprio script. Nunca troque o id de um material publicado: as cenas apontam para ele.
