# Archiviazione Demo

Demo statica HTML per gestione beni culturali, pronta per pubblicazione su GitHub Pages.

## Contenuto del progetto

- `index.html`: login demo.
- `dashboard.html`: dashboard con viewer 3D e schede oggetto.
- `meta_con_scritta.glb`: modello 3D demo usato dal viewer.
- `demo-data/`: struttura consigliata object-centric per 3 oggetti.
- `.github/workflows/deploy-pages.yml`: deploy automatico su GitHub Pages.
- `.nojekyll`: disabilita Jekyll (utile per siti statici puri).

## Struttura demo dati (object-centric)

Ogni oggetto ha la propria cartella con risorse e metadati:

```text
demo-data/
	index.json
	shared/
		taxonomy.json
	objects/
		obj-001-cippo/
			model/
			images/
			docs/
			data/
				metadata.json
				hotspots.json
		obj-002-lastra/
			model/
			images/
			docs/
			data/
				metadata.json
				hotspots.json
		obj-003-frammento/
			model/
			images/
			docs/
			data/
				metadata.json
				hotspots.json
```

Nota: la dashboard attuale usa dati JS locali/localStorage. La cartella `demo-data/` e pronta per un successivo collegamento via fetch JSON.

## Upload su GitHub (prima pubblicazione)

1. Crea un nuovo repository su GitHub (es. `archiviazione-demo`).
2. Da terminale, nella cartella progetto:

```bash
git init
git add .
git commit -m "Initial demo setup for GitHub Pages"
git branch -M main
git remote add origin https://github.com/<tuo-user>/<tuo-repo>.git
git push -u origin main
```

3. Su GitHub: `Settings -> Pages`.
4. In `Build and deployment`, seleziona `Source: GitHub Actions`.
5. Il workflow `Deploy static site to GitHub Pages` partira automaticamente a ogni push su `main`.

URL finale:

```text
https://<tuo-user>.github.io/<tuo-repo>/
```

## Aggiornare la demo

1. Modifica file e/o aggiungi nuovi oggetti in `demo-data/objects/`.
2. Esegui:

```bash
git add .
git commit -m "Update demo content"
git push
```

Il sito verra aggiornato automaticamente.