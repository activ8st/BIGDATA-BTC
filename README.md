# BIGDATA-BTC – Analisi dei Dati e Previsione del Prezzo di Bitcoin (2020–2025)

Questo progetto di **analisi dati e data mining** ha come obiettivo lo studio dell’andamento storico del prezzo di **Bitcoin (BTC-USD)** nel periodo 2020–2025, utilizzando le librerie Python affrontate a lezione:

**numpy, pandas, statsmodels, scikit-learn, tensorflow**

Il progetto è realizzato e presentato in formato **Jupyter Notebook (.ipynb)** ed è accompagnato dal dataset in formato **CSV**, come richiesto dalla consegna.

---

## Obiettivo del progetto

Gli obiettivi principali dell’elaborato sono:

1. Analizzare un **dataset reale** di tipo serie temporale.
2. Effettuare un’**analisi esplorativa dei dati (EDA)** per comprendere:
   - andamento del prezzo,
   - volatilità,
   - distribuzione dei rendimenti,
   - relazioni tra variabili OHLCV.
3. Verificare la **stazionarietà della serie dei prezzi** tramite test statistico ADF.
4. Costruire un **modello predittivo di base** per il prezzo di chiusura del giorno successivo.
5. Applicare e integrare le principali librerie richieste dal corso in un workflow coerente.

Il progetto ha finalità **didattiche e analitiche**, NON finanziario.
---

## Dataset

**Fonte dei dati:**  
Yahoo Finance, tramite la libreria Python `yfinance`  
https://pypi.org/project/yfinance/

**Ticker analizzato:**  
`BTC-USD` (Bitcoin / US Dollar)

**Periodo temporale:**  
1 gennaio 2020 – 1 gennaio 2025

**Formato:**  
CSV (`BTCUSD_2020_2025.csv`)

Il dataset contiene osservazioni **giornaliere** con le seguenti variabili:

- Open
- High
- Low
- Close
- Volume

Il file CSV è incluso nel repository per garantire **riproducibilità** e separazione tra dati e codice.
---

## Analisi Esplorativa dei Dati (EDA)

L’analisi esplorativa include i seguenti grafici e analisi:

1. **Andamento del prezzo di chiusura** nel tempo  
2. **Volume degli scambi giornalieri**  
3. **Distribuzione dei log-return**  
4. **Volatilità calcolata tramite deviazione standard mobile (30 giorni)**  
5. **Matrice di correlazione (heatmap) delle variabili OHLCV**  
6. **Confronto tra prezzo reale e prezzo previsto dal modello**

Questa fase consente di individuare:
- volatilità elevata,
- cambi di regime nel tempo,
- correlazioni interne tra le variabili di prezzo.

---

## Test di Stazionarietà – ADF (statsmodels)

Per verificare la stazionarietà della serie dei prezzi di chiusura è stato applicato il test
**Augmented Dickey-Fuller (ADF)** tramite la libreria `statsmodels`.

Il test restituisce:
- ADF statistic
- p-value
- valori critici

**Risultato:**  
La serie dei prezzi di Bitcoin risulta **non stazionaria**, come atteso per una serie finanziaria caratterizzata da trend e shock esterni.

Questo risultato giustifica l’uso dei modelli come **baseline predittive** e non come strumenti di inferenza causale.

---

## Modellazione – Scikit-Learn

È stato implementato un modello di **regressione lineare** per la previsione del prezzo di chiusura del giorno successivo.

- **Feature di input:** Open, High, Low, Close, Volume  
- **Target:** Close del giorno successivo  
- **Suddivisione dati:** train/test split temporale (senza shuffle)  
- **Metriche di valutazione:** MSE, R²  

Il modello fornisce una previsione semplice ma utile per dimostrare l’applicazione delle tecniche di machine learning affrontate a lezione.

---

## TensorFlow

TensorFlow è integrato nel progetto per soddisfare i requisiti del corso.

Nel notebook:
- viene verificata la disponibilità della libreria nell’ambiente di esecuzione,
- viene utilizzato un modello neurale semplice quando supportato,
- è presente un **fallback automatico** che consente al notebook di rimanere eseguibile anche in ambienti privi di TensorFlow.

Questa scelta garantisce **robustezza e riproducibilità** del progetto.
---

## File nel repository

- `BIGDATA_BTC.ipynb` — Notebook Jupyter completo del progetto  
- `BTCUSD_2020_2025.csv` — Dataset utilizzato per l’analisi  
- `README.md` — Documentazione del progetto  
- `requirements.txt` — Librerie Python utilizzate  

---

## Conclusioni

L’analisi evidenzia come il prezzo di Bitcoin presenti:
- forte non stazionarietà,
- elevata volatilità,
- correlazioni significative tra le variabili di prezzo.
Il modello di regressione lineare rappresenta una **baseline predittiva**, adeguata al contesto didattico del corso e utile per dimostrare l’intero workflow di analisi dati, dall’acquisizione del dataset alla modellazione.
