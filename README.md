# Asset-Rater-for-Mean-Reversion-Tradingstrategy
# 📊 Asset Rater for Mean Reversion Strategy

Dieses Projekt analysiert verschiedene Aktien auf ihre Eignung für eine **Mean-Reversion-Tradingstrategie**. Dabei wird bewertet, welche Assets:

- intraday stark schwanken (hoher ADR),
- gleichzeitig eine geringe Volatilität der Tagesrenditen aufweisen,
- und wenig Trendverhalten zeigen (niedriger absoluter Mittelwert der Renditen).

Ziel ist es, **ruhige aber bewegliche Assets** zu identifizieren, die sich gut für Strategien eignen, bei denen der Preis immer wieder zum Mittelwert zurückkehrt.

---

## 🔍 Verwendete Kennzahlen

### 1. **ADR (Average Daily Range)**
> \[(High - Low) / Open \] in %

Misst die durchschnittliche tägliche Spanne des Kurses.

### 2. **Logarithmierte Tagesrendite**
> log(Close<sub>t</sub> / Close<sub>t−1</sub>) × 100

Wird verwendet, um die **Volatilität** (Standardabweichung) und den **Durchschnittstrend** zu berechnen.

---

## 📈 Mean Reversion Score (MRS)

Die Assets werden bewertet mit der Formel:

(ADR - |Mean Return|) / StdDev of Returns

**Interpretation**:
- Ein hoher Score bedeutet: viel Bewegung (ADR), aber wenig richtungslastiger Trend (kleiner |mean|) bei geringer Schwankung (low std).
- Ideal für Strategien, die auf Rückkehr zum Mittelwert setzen (Mean Reversion).

---

## 🧪 Beispielassets

Das Projekt vergleicht u.a. folgende Aktien:
- AAPL
- NVDA
- TSLA
- SPY
- SMH
- CAT
- GOOGL
- GE
- WMT
- ASML

> Du kannst beliebige eigene `.csv`-Dateien hinzufügen – siehe unten.

---

## 📂 Dateiformat der Eingabedaten

Die `.csv`-Dateien müssen folgende Spalten enthalten:
- `Open`
- `High`
- `Low`
- `Close`

Die Daten sollten idealerweise **zeitlich sortiert** sein (älteste zuerst).  
1000 Zeilen werden pro Datei verarbeitet.

Die Daten können z. B. von [Yahoo Finance](https://finance.yahoo.com/) exportiert werden.

---

## 🛠 Nutzung

```bash
git clone https://github.com/dein-nutzername/Asset-Rater_for_Reversion-Strategy.git
cd Asset-Rater_for_Reversion-Strategy
# Öffne das Notebook in Jupyter oder VS Code
