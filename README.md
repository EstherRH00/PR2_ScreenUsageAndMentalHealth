# Tipologia i Cicle de Vida de les Dades — Pràctica 2

## Autors
Esther Ruano, Carles Ventura  
Maig de 2025

## Descripció

Aquest projecte analitza dades sobre la depressió en estudiants universitaris mitjançant tècniques d’anàlisi exploratòria, modelatge supervisat i no supervisat, i contrast d’hipòtesis. Està implementat en R mitjançant un arxiu `.Rmd`.

## Requisits previs

Abans d'executar l’script, assegura’t de tenir instal·lades les següents llibreries d’R:

```r
install.packages(c(
  "tidyverse", "caret", "randomForest",
  "ggplot2", "patchwork", "dplyr",
  "cluster", "factoextra", "corrplot",
  "data.table", "gridExtra", "kableExtra",
  "mltools", "knitr"
))
```

A més, cal que el fitxer de dades estigui ubicat en el directori següent:

```
data/student_depression_dataset.csv
```

## Execució

1. Obre el fitxer `PAC2-EstherRuano-CarlesVentura.Rmd` amb RStudio.
2. Comprova que el fitxer CSV es troba en el camí correcte (`data/student_depression_dataset.csv`).
3. Fes clic a **Knit** per generar l’informe (en HTML o PDF).

## Contingut del projecte

### 1. Carregament i preparació de les dades

- Conversió de valors categòrics a factors.
- Tractament de valors invàlids (per exemple, eliminació de `"Class 12"` de la variable `Degree`).
- Codificació binària de variables qualitatives per a clustering.
- Normalització de variables numèriques.

### 2. Anàlisi exploratòria de variables

- Variables quantitatives: visualització amb histogrames i boxplots.
- Variables qualitatives: anàlisi amb barplots.
- Interpretació visual de la distribució de les variables més rellevants.

### 3. Model supervisat: Random Forest

- Entrenament del model per predir la depressió en base a variables acadèmiques, socials i psicològiques.
- Divisió del dataset en conjunt d’entrenament i test.
- Avaluació amb matriu de confusió. Accuracy del 83'85%.
- Gràfic d'importància de les variables.

### 4. Model no supervisat: Clustering (K-means)

- Aplicació de K-means amb 5 clústers.
- Utilització de variables numèriques normalitzades i codificades.
- Visualització dels clústers.

### 5. Contrast d’hipòtesis

- Test de proporcions per determinar si hi ha diferències significatives entre homes i dones pel que fa a la depressió.
- Resultat: Amb un p-value de 0.7578 no es troba una diferència estadísticament significativa (p > 0.05).

## Fitxer de dades

El fitxer `student_depression_dataset.csv` ha de contenir columnes com:

- `Gender`
- `Age`
- `CGPA`
- `Depression`
- `Academic Pressure`
- `Sleep Duration`
- `Have you ever had suicidal thoughts ?`
- `Financial Stress`
- `Work/Study Hours`
- ... entre altres.

## Resultats destacats

- **Model Random Forest**: Ofereix una predicció acceptable de la depressió, amb una accuracy del 83'85%.
- **K-means**:  Els clústers amb una major proporció d’estudiants han tingut pensaments suïcides i que pateixen una elevada pressió acadèmica presenten també un percentatge més alt de casos de depressió.
- **Hipòtesi de gènere**: Amb un p-value de 0.7578 no s’han trobat evidències per afirmar que la depressió depèn del gènere en aquest conjunt de dades.

## Estructura del projecte

```
├── README.md
├── PAC2-EstherRuano-CarlesVentura.Rmd
├── data/
│   └── student_depression_dataset.csv
```
