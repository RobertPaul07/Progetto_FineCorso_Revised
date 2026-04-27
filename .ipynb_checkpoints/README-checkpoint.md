# 📊 Progetto Liceo Virgilio — Analisi dati per la dirigenza scolastica

**Autore:** [NOME COGNOME]
**Corso:** [CORSO]
**Anno:** 2026

Esame di fine corso Python ristrutturato come progetto di analisi dati in stile consulenza. Tre notebook indipendenti rispondono ad altrettante richieste della dirigenza di un liceo classico fittizio (il "Liceo Virgilio"), passando dall'analisi diagnostica locale alla visione multidimensionale fino al report tabellare finale.

---

## 📂 Struttura del progetto

```
Esame_Python_LiceoVirgilio/
│
├── README.md                                ← questo file
├── .gitignore                               ← file ignorati dal version control
│
└── notebooks/
    ├── 00_introduzione_progetto.ipynb       ← contesto narrativo e nota metodologica
    ├── 01_analisi_classe_3A.ipynb           ← analisi diagnostica della classe 3A
    ├── 02_analisi_multidimensionale.ipynb   ← visione d'insieme dell'intero terzo anno
    └── 03_report_direzione.ipynb            ← report tabellare operativo per la dirigenza
```

---

## 📓 I tre notebook

### 📘 Notebook 1 — Analisi della classe 3A

**Domanda di partenza.** *"Come sta andando la 3A? Chi è in difficoltà? Quanti studenti rischiano la promozione?"*

Analisi diagnostica su una matrice 5 studenti × 4 materie linguistiche (Latino, Spagnolo, Francese, Inglese), realizzata con NumPy e loop nidificati. Il deliverable è un mini-report che identifica gli studenti bocciati per materia, gli studenti insufficienti in tutte le materie, le medie individuali e di classe, e il tasso di promozione complessivo.

### 📗 Notebook 2 — Analisi multidimensionale

**Domanda di partenza.** *"Possiamo confrontare le tre sezioni del terzo anno tra loro e rispetto all'anno precedente?"*

Analisi su un tensore quadridimensionale di forma `(2, 3, 4, 5)` — anni × classi × materie classiche × prove. Il notebook esplora tre operazioni matriciali: aggregazione lungo gli assi (somma su materie e prove per ottenere punteggi cumulati per anno × classe), prodotto cartesiano per la generazione di scenari di pianificazione, e normalizzazione lungo un asse per confronti equi tra prove di diverso peso.

### 📕 Notebook 3 — Report per la dirigenza

**Domanda di partenza.** *"Possiamo avere questi dati in tabelle strutturate invece che in array NumPy?"*

Cambio di strumento: si passa da NumPy a Pandas. Il notebook lavora su due fonti dati distinte (un elenco manuale tenuto dalla segreteria e un export del sistema informatico), le combina in un DataFrame e le riconcilia tramite `isin()` per identificare elementi comuni e differenze. Chiude con il **report finale** consegnabile alla dirigenza: DataFrame dei punteggi degli studenti del tutorato nelle quattro materie classiche, con media e deviazione standard per materia.

---

## 🛠️ Stack tecnologico

- **Python 3.13**
- **NumPy** — array multidimensionali, operazioni vettoriali, aggregazione su assi
- **Pandas** — Series e DataFrame, indicizzazione personalizzata, statistiche descrittive
- **Jupyter** — esecuzione interattiva dei notebook

---

## ▶️ Come riprodurre l'analisi

I requisiti sono minimi: un'installazione di Python 3.13 con NumPy, Pandas e Jupyter. Se le librerie non sono già disponibili nell'ambiente in uso, possono essere installate con:

```bash
pip install numpy pandas jupyterlab
```

A quel punto basta aprire i notebook nella cartella `notebooks/` ed eseguirli in ordine (00 → 01 → 02 → 03):

```bash
cd Esame_Python_LiceoVirgilio
jupyter lab
```

Tutti i seed casuali sono fissati nei notebook, quindi gli output sono **deterministici e riproducibili** identici a quelli mostrati nei file consegnati.

> *Chi voglia isolare le dipendenze del progetto può naturalmente creare un proprio ambiente virtuale (`conda create` o `python -m venv`) prima dell'installazione delle librerie.*

---

## 📝 Note metodologiche

Il progetto combina **task tecnici didattici** (richiesti dalla traccia d'esame, come dimostrazione di padronanza di specifici strumenti: loop nidificati, operazioni su assi NumPy, manipolazione di Series e DataFrame) con una **cornice applicativa coerente** (il Liceo Virgilio e le richieste della sua dirigenza).

Alcuni task hanno natura prevalentemente dimostrativa di una tecnica — per esempio il prodotto cartesiano nel Notebook 2 o il filtro dei multipli di 3 nel Notebook 3. Questi vengono presentati onestamente come tali: dove possibile sono contestualizzati nel dominio del Liceo, dove la forzatura narrativa sarebbe artificiosa il loro carattere tecnico viene dichiarato esplicitamente. Questo approccio mira a dimostrare padronanza tecnica sugli strumenti richiesti senza compromettere la credibilità del caso d'uso applicativo.
