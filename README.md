# SprachWerkstatt

SprachWerkstatt ist ein CCIT-Semesterprojekt, das beim Schreiben hilft: Texte werden umformuliert, Wortvorschlaege mit `[MASK]` erzeugt, Uebersetzungen zwischen Deutsch und Englisch erstellt und der Ton eines Textes per Sentiment-Analyse bewertet.

Die App wird mit **Gradio (Blocks + Tabs)** umgesetzt und im **Jupyter Notebook** entwickelt und praesentiert.

## Features

1. **Umformulieren**
   - Eingabe eines Textes
   - Stilwahl: `formell`, `informell`, `einfach`, `wissenschaftlich`
   - Ausgabe eines umformulierten Textes

2. **Wort-Vorschlaege (Fill-Mask)**
   - Eingabe eines Satzes mit `[MASK]`
   - Modell schlaegt passende Woerter inkl. Wahrscheinlichkeiten vor

3. **Uebersetzer + Zusammenfassung**
   - Deutsch -> Englisch und Englisch -> Deutsch
   - Zusaetzliche kurze Zusammenfassung der Uebersetzung

4. **Ton-Check (Sentiment-Analyse)**
   - Prueft, ob ein Text eher positiv, neutral oder negativ klingt

5. **History (State)**
   - Verlauf der Umformulierungen mit `gr.State`

## Eingesetzte HuggingFace Pipelines

- `text-generation`
- `fill-mask`
- `translation`
- `sentiment-analysis`

Damit sind die Muss-Kriterien fuer mehrere kombinierte Pipelines erfuellt.

## Tech-Stack

- Python 3.10+
- Gradio
- Transformers
- PyTorch
- SentencePiece
- Jupyter Notebook

## Installation

Die `venv` erstellst du selbst. Danach einfach die Pakete installieren:

```bash
pip install -r requirements.txt
```

Alternative (direkt):

```bash
pip install gradio transformers torch sentencepiece accelerate pandas numpy matplotlib seaborn scikit-learn jupyter notebook
```

## Starten

### Notebook oeffnen

```bash
jupyter notebook
```

oder

```bash
jupyter lab
```

Dann das Projekt-Notebook ausfuehren und die Gradio-App starten.

## Design- und UX-Ziele

- Schreibtisch/Editor-Look mit hellem Hintergrund
- Schreibmaschinen-Font fuer Output-Bereiche
- Seitenleiste fuer Tools
- Responsives Layout mit `gr.Row` und `gr.Column`
- Einheitliches Farbschema, gestylte Buttons und Hover-Effekte

## Fehlerbehandlung

Die App faengt typische Eingabefehler ab:

- Leere Texte
- Zu kurze Texte
- Fehlende oder falsche `[MASK]`-Eingaben
- Ungueltige Sprachrichtung

## Projektstruktur (geplant)

```text
SprachWerkstatt/
  README.md
  Aufgabe.txt
  requirements.txt
  package.json
  SprachWerkstatt.ipynb
```

## Abgabe

1. Lauffaehiges Jupyter Notebook (`.ipynb`) mit Markdown-Erklaerungen
2. Drei Screenshots der laufenden App (verschiedene Tabs/Zustaende)
3. Kurze Doku im Notebook (5-10 Saetze):
   - Was macht die App?
   - Welche Modelle/Pipelines wurden genutzt?
   - Was war die groesste Herausforderung?
