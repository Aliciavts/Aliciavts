<h1 align="center">Alícia Viana Tavares dos Santos</h1>

###

<p align="left"></p>

###

<h4 align="center">Health Data Science and Clinical Datasets</h4>

###

<p align="left">👋 Hi there, I'm Alícia!<br>I am a Physical Therapy undergraduate student and a CNPq Research Fellow at the Respiratory Physiology Laboratory within the São Lucas Hospital (PUCRS).<br><br>I am passionate about transforming raw health data into clinical insights that improve patient quality of life. My work lives at the intersection of Healthcare and Technology.<br><br>🛠️ What I do:<br>Data Analysis: Experience working with large-scale healthcare databases.<br><br>Data Management: Database structuring and collection via REDCap.<br><br>Scientific Research: Investigating respiratory physiology through evidence-based health practices.<br><br>💻 My Tech Toolkit:<br>R: My primary language for statistical analysis and data visualization.<br><br>Python: Currently expanding my horizons and transitioning into automation and data science.<br><br>Data Wrangling: Expertise in cleaning and organizing complex datasets.<br><br>🎯 Goals:<br>I am constantly honing my programming skills to make clinical research more agile, scalable, and reproducible. If you are interested in Health Data Science or Physiology, let's connect!<br><br>📬 Let's Connect:<br>LinkedIn: linkedin.com/in/alícia-viana-995213226<br><br>Email: aliciavts@hotmail.com</p>

###

<h2 align="left">Code and tools 🎲</h2>

###

<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/rstudio/rstudio-original.svg" height="40" alt="rstudio logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/r/r-original.svg" height="40" alt="r logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" height="40" alt="python logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/canva/canva-original.svg" height="40" alt="canva logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/notion/notion-original.svg" height="40" alt="notion logo"  />
</div>

###

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Aliciavts/Aliciavts/output/pacman-contribution-graph-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Aliciavts/Aliciavts/output/pacman-contribution-graph.svg">
  <img alt="pacman contribution graph" src="https://raw.githubusercontent.com/Aliciavts/Aliciavts/output/pacman-contribution-graph.svg">
</picture>

###

name: Generate pacman animation

on:
  schedule: # execute every 12 hours
    - cron: "* */12 * * *"

  workflow_dispatch:

  push:
    branches:
    - main

jobs:
  generate:
    permissions:
      contents: write
    runs-on: ubuntu-latest
    timeout-minutes: 5

    steps:
      - name: generate pacman-contribution-graph.svg
        uses: abozanona/pacman-contribution-graph@main
        with:
          github_user_name: ${{ github.repository_owner }}


      - name: push pacman-contribution-graph.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
