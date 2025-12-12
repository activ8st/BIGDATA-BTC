# BIGDATA-BTC – Analisi e Previsione del Prezzo di Bitcoin (2020–2025)
Questo progetto è stato realizzato come prova finale per il corso di **Big Data / Data Mining**, con l'obiettivo di analizzare l'andamento del prezzo di **Bitcoin (BTC-USD)** e costruire modelli predittivi tramite le librerie Python studiate a lezione:  
**numpy, pandas, statsmodels, scikit-learn, tensorflow**.
---

## Obiettivo del progetto
1. Analizzare un dataset reale riguardante Bitcoin (storico 2020–2025).
2. Studiare:
   - andamento del prezzo,
   - volatilità,
   - distribuzioni dei rendimenti,
   - correlazioni tra variabili OHLCV.
3. Effettuare un test di stazionarietà tramite **ADF (statsmodels)**.
4. Predire il prezzo di chiusura del giorno successivo tramite:
   - **Regressione lineare (scikit-learn)**.
5. Integrare TensorFlow nel processo analitico come richiesto dal corso
   (con fallback automatico nel caso l'ambiente non supporti la libreria).
---

## Dataset

**Fonte dati:**  
Yahoo Finance, tramite la libreria `yfinance`.(https://pypi.org/project/yfinance/)

**Ticker analizzato:**  
`BTC-USD` — Bitcoin / US Dollar

**Periodo analizzato:**  
`1 gennaio 2020` → `1 gennaio 2025`

## Analisi dei Dati (EDA)
1. **Prezzo di chiusura BTC** (trend 2020–2025)  
2. **Volume giornaliero**  
3. **Istogramma dei log-return**  
4. **Media mobile e volatilità 30 giorni**  
5. **Heatmap di correlazione OHLCV**  
6. **Confronto prezzo reale vs previsto (modello ML)**  

Questi grafici costituiscono la parte di analisi esplorativa richiesta dal corso.
---

## Test di stazionarietà (ADF – statsmodels)
Per verificare se la serie è stazionaria è stato utilizzato il test **ADF (Augmented Dickey-Fuller)**.

Risultati nel notebook:
- ADF statistic
- p-value
- valori critici

Conclusione:  
Il prezzo di Bitcoin risulta **non stazionario** (come atteso per una serie finanziaria).

---
### Regressione Lineare – Scikit-Learn
È stato addestrato un modello per prevedere il prezzo di chiusura del giorno successivo.

- **Input:** Open, High, Low, Close, Volume  
- **Output:** Close del giorno successivo  
- **Metriche:** MSE, R²  
- **Grafico:** andamento reale vs predetto

---
## File nel repository

- `BIGDATA_BTC.ipynb` — Notebook Jupyter completo del progetto  
- `BTCUSD_2020_2025.csv` — Dataset utilizzato  
- `README.md` — Documentazione del progetto  

---

## Requisiti
Le principali librerie richieste dalla consegna sono state utilizzate:

- **numpy** → calcoli numerici  
- **pandas** → gestione dataset  
- **statsmodels** → test ADF  
- **scikit-learn** → modello di regressione  
- **tensorflow** → modello dimostrativo / integrazione  

---
## Conclusioni

Bitcoin mostra una dinamica fortemente non stazionaria, con elevata volatilità e correlazioni interne tra prezzi OHLC.  
Il modello di regressione lineare offre una capacità predittiva limitata ma utile per dimostrare l’applicazione delle tecniche di data mining.  
La struttura del progetto rispetta tutte le richieste del corso, integrando analisi, modellazione, grafici e librerie obbligatorie.
