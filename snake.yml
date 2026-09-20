##  Path in your repo: .github/workflows/snake.yml
name: Generate Snake Animation

on:
  schedule:
    - cron: "0 */12 * * *"   # twice a day
  workflow_dispatch:          # manual run button
  push:
    branches:
      - main

jobs:
  generate:
    runs-on: ubuntu-latest
    permissions:
      contents: write
    steps:
      - name: Generate snake SVGs
        uses: Platane/snk@v3
        id: snake-gif
        with:
          github_user_name: HIBAMAHROUG
          outputs: |
            dist/github-snake.svg
            dist/github-snake-dark.svg?palette=github-dark
            dist/ocean.gif?color_snake=orange&color_dots=#bfd6f6,#8dbdff,#64a1f4,#4b91f1,#3c7dd9

      - name: Push to output branch
        uses: crazy-max/ghaction-github-pages@v4
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
