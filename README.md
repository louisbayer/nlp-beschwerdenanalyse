# NLP-Analyse von Verbraucherbeschwerden

Dieses Projekt demonstriert den Einsatz von NLP-Techniken, um aus einer
Sammlung unstrukturierter Beschwerdetexte die am häufigsten angesprochenen
Themen zu extrahieren. Aus einem großen Datensatz wurden dazu 500 zufällige
Beschwerden gezogen und analysiert.

## Datensatz

Verwendet wird das Consumer Complaint Dataset (CFPB) von Kaggle
(kaggle.com/datasets/namigabbasov/consumer-complaint-dataset). Die
Beschwerdetexte stehen in der Spalte `narrative` und liegen als echte,
unbearbeitete Freitexte vor. Analysiert wird eine reproduzierbare
Zufallsstichprobe von 500 Texten.

## Vorgehen

- **Vorverarbeitung:** Kleinschreibung, Entfernen der Anonymisierungs-
  Platzhalter und URLs, Beschränkung auf Buchstaben, Tokenisierung,
  Lemmatisierung sowie Entfernen von Stopp- und sehr kurzen Wörtern.
- **Vektorisierung:** Bag-of-Words und TF-IDF, jeweils mit Uni- und Bigrammen.
- **Themenextraktion:** LDA (auf Bag-of-Words) und NMF (auf TF-IDF).
- **Evaluierung:** Vergleich beider Verfahren über den Kohärenz-Score (c_v)
  sowie über verschiedene Themenzahlen (k = 5, 8, 10).

## Ergebnis

NMF erzielte bei jeder Themenzahl höhere Kohärenzwerte als LDA. Das finale
Modell nutzt NMF mit k = 5 (c_v ≈ 0,62) und liefert fünf klar unterscheidbare
Beschwerdekategorien.

## Ausführung

​```
pip install -r requirements.txt
​```

Das Notebook wird anschließend in Jupyter oder auf Kaggle von oben nach unten
ausgeführt.
