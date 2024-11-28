
# Virtual Reality User Identification Project

Dieses Projekt befasst sich mit der Vorbereitung und Verarbeitung von Daten aus Virtual-Reality-Sitzungen, um maschinelle Lernmodelle zu trainieren, zu validieren und zu testen. Ziel ist es, Benutzer anhand ihres Verhaltens in einer virtuellen Umgebung zu identifizieren.

## Inhaltsverzeichnis

- [Projektübersicht](#projektübersicht)
- [Datenvorbereitung](#datenvorbereitung)
- [Modelltraining](#modelltraining)
- [Modellevaluierung](#modellevaluierung)
- [Abhängigkeiten](#abhängigkeiten)

## Sehr Wichtig

.ipynb- und .pdf-Dateien können in GitHub nicht direkt angezeigt werden, da sie visuelle Darstellungen enthalten. Bitte verwenden Sie [nbviewer.org](https://nbviewer.org), um den Inhalt anzuzeigen.

## Projektübersicht

Das Ziel dieses Projekts ist es, Benutzer anhand ihres Verhaltens in einer virtuellen Realität zu identifizieren. Es werden Daten von 16 Teilnehmern verwendet, die in verschiedenen Interaktionsszenarien (Reposition, Context Menu, Bimanual Keyboard und Rescale) gesammelt wurden.

## Datenvorbereitung

Die Funktion `prepare_train_data` liest TSV-Dateien aus einem angegebenen Verzeichnis, verarbeitet die Verhaltensdaten, skaliert die Features und teilt die Daten in Trainings- und Validierungssets. Hier sind die Hauptschritte:

1. **Dateien laden**: Liest TSV-Dateien, die mit dem angegebenen Verhaltensnamen und Suffix übereinstimmen.
2. **Daten normalisieren**: Normalisiert die Kopfpositionsdaten relativ zur Startposition.
3. **Feature-Auswahl**: Filtert relevante Spalten, die Positionen und Rotationen enthalten.
4. **Daten bereinigen**: Entfernt Zeilen mit fehlenden Werten.
5. **Skalieren**: Skaliert die Features mit `StandardScaler`.
6. **Fensterbildung**: Teilt die Daten in überlappende Fenster für ein besseres Modelltraining.
7. **Trainings- und Validierungssplit**: Teilt die Daten in Trainings- und Validierungssets.

## Modelltraining

Mehrere Modelle werden mit den vorbereiteten Daten erstellt und trainiert. Die Modelle reichen von einfachen dichten neuronalen Netzen bis hin zu komplexeren Architekturen mit Convolutional- und LSTM-Schichten. Der Trainingsprozess umfasst:

1. **Modellerstellung**: Definiert die Architektur der Modelle.
2. **Modellkompilierung**: Kompiliert die Modelle mit geeigneten Verlustfunktionen und Optimierern.
3. **Modelltraining**: Trainiert die Modelle mit den Trainingsdaten und validiert sie mit den Validierungsdaten.

## Modellevaluierung

Die Modelle werden mit den Validierungsdaten bewertet, und es werden verschiedene Metriken wie Genauigkeit, Konfusionsmatrix und Klassifikationsberichte erstellt. Eine Mehrheitsabstimmungsstrategie wird angewendet, um die Robustheit der Vorhersagen zu verbessern.

## Abhängigkeiten

Das Projekt erfordert die folgenden Python-Pakete:
- os
- re
- pandas
- numpy
- scikit-learn
- matplotlib
- seaborn
- tensorflow
- scipy
