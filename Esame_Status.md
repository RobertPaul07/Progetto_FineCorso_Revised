# Esame Status — Progetto Esame Liceo Virgilio

**Ultimo aggiornamento:** 22 aprile 2026, sessione pomeridiana
**Cartella progetto:** `C:\Users\rober\Dev\Portfolio_Projects\02-esame-liceo-virgilio`

---

## Contesto del progetto

**Tipo:** Esame di fine corso Python da reimpostare in "stile progetto"
**Input originale:** Tre notebook di esercizi già svolti (`Esercizio_1.ipynb`, `Esercizio_2.ipynb`, `Esercizio_3.ipynb`) che costituiscono la traccia identica dell'esame
**Filo rosso scelto:** "Liceo Virgilio", liceo classico fittizio, analisi dati per la dirigenza in stile consulenza
**Strategia dati:** Opzione B — stesso contesto narrativo nei tre notebook ma dati diversi per ciascuno (più pulito, rispetta la natura dei singoli task)
**Ambiente:** conda environment dedicato `esame-liceo-virgilio` (Python 3.13 + NumPy + Pandas + Jupyter)

---

## Struttura del progetto

```
Esame_Python_LiceoVirgilio/
│
├── README.md                                   ← ⏳ da fare a fine progetto
├── environment.yml                             ← ⏳ da esportare a fine progetto
│
└── notebooks/
    ├── 00_introduzione_progetto.ipynb          ← ✅ Completato
    ├── 01_analisi_classe_3A.ipynb              ← ✅ Completato (13 celle)
    ├── 02_analisi_multidimensionale.ipynb      ← ⏭️ PROSSIMO
    └── 03_report_direzione.ipynb               ← ⏳ Da fare
```

---

## Decisioni metodologiche prese

### Impostazione complessiva
- **Stile "progetto pieno"** con filo rosso narrativo (Liceo Virgilio) attraverso i tre notebook, + notebook zero di apertura
- **Codice dei task canonici = codice originale di Robert**: non riscriviamo le funzioni, interveniamo solo sui messaggi di stampa per integrarli nel contesto narrativo
- **Registro "stile consulenza"**: dirigenza del Liceo = cliente, i tre notebook = deliverable di complessità crescente
- **Nota metodologica trasparente nel Notebook 0**: dichiara esplicitamente che alcuni task (prodotto cartesiano, multipli di 3) hanno natura prevalentemente tecnica e li dichiara come tali. Scelta deliberata di onestà intellettuale che Robert ha confermato di voler tenere così com'è

### Convenzioni stilistiche del progetto
- **Lingua:** prosa in italiano, nomi funzioni/variabili in italiano (coerente con lo stile originale)
- **Docstring:** stile Args/Returns già presente nei file originali, mantenuto
- **Emoji nei titoli markdown:** sì (📘📗📕 per i tre notebook, altre per le sezioni)
- **Emoji negli output di codice:** sì 🟢/🔴 per sufficiente/insufficiente (confermato da Robert nel Notebook 1)
- **Separatori stampa:** `"-" * 60` sotto le intestazioni dei mini-report
- **Intestazioni output:** ogni task ha un titolo tipo `"Studenti con voto insufficiente per materia — Classe 3A"`
- **Ogni notebook chiude con cella "Sintesi per la dirigenza"** + ponte al notebook successivo
- **Soglia sufficienza Task 4 Notebook 1:** `>= 6` (concettualmente più pulito, risultato identico al `> 5` della traccia letterale sui dati reali)

---

## Stato dei notebook

### Notebook 0 — `00_introduzione_progetto.ipynb` ✅
6 celle markdown, zero codice. Copertina, contesto Liceo Virgilio, presentazione delle tre analisi, stack tecnologico, nota metodologica trasparente, ponte al Notebook 1.

**Placeholder ancora da riempire nella Cella 1:** nome corso, cognome Robert, data consegna.

### Notebook 1 — `01_analisi_classe_3A.ipynb` ✅
13 celle (6 code + 7 markdown). Struttura:
1. Markdown apertura (contesto professoressa 3A, quattro domande, approccio tecnico)
2. Code setup (dati: 5 studenti × 4 materie linguistiche, identici all'originale)
3-4. Task 1: bocciati per materia (loop su colonne)
5-6. Task 2: bocciati in tutte le materie (loop nidificati — rispetta la traccia)
7-8. Task 3: medie individuali + media di classe
9-10. Task 4: studenti sopra la sufficienza
11-12. Extra: tasso di promozione della classe (KPI sintetico)
13. Markdown sintesi per la dirigenza + ponte al Notebook 2

**Dati utilizzati:**
- Studenti: Robbie, Marco, Lore, Fabri, Alba
- Materie: Latino, Spagnolo, Francese, Inglese
- Matrice voti: identica all'Esercizio_1.ipynb originale

**Risultati confermati dall'analisi:**
- 1 bocciato in Latino, Spagnolo, Francese; 3 bocciati in Inglese
- Fabri unico studente insufficiente in tutte le materie
- Medie: Robbie 7.25, Marco 5.50, Lore 8.50, Fabri 3.25, Alba 8.00
- 4/5 studenti sopra la sufficienza
- Tasso di promozione severo: 40% (2/5: Lore, Alba)

### Notebook 2 — `02_analisi_multidimensionale.ipynb` ⏭️ PROSSIMO
Da iniziare nella prossima sessione.

### Notebook 3 — `03_report_direzione.ipynb` ⏳
Da fare nella sessione successiva.

---

## Per riprendere da dove abbiamo lasciato

**Prossimo step concreto:** iniziare il Notebook 2 — Analisi multidimensionale.

**Scaletta pianificata del Notebook 2** (da confermare/rifinire a inizio sessione):

1. **Markdown apertura**
   - Contesto narrativo: la dirigenza vuole una visione d'insieme, non più limitata a una sola classe
   - Presentazione del tensore 4D: anni × classi × materie × prove
   - Dichiarazione esplicita del carattere più tecnico di questo notebook

2. **Code setup**
   - Import numpy + itertools
   - Creazione del tensore 4D simulato, shape (2, 3, 4, 5):
     - 2 anni accademici (2023/24, 2024/25)
     - 3 classi del terzo anno (3A, 3B, 3C — coerenza narrativa col Notebook 1)
     - 4 materie classiche (Latino, Greco, Italiano, Storia)
     - 5 prove per materia nell'anno
   - Fissare `np.random.seed` per riproducibilità

3. **Task 1: Somma degli ultimi due assi**
   - Interpretazione narrativa: *"per ogni anno e classe, totale punteggio cumulato"*
   - Output: matrice (2, 3) facile da leggere come tabella

4. **Task 2: Prodotto cartesiano** (il task delicato)
   - Contestualizzazione in chiave scenari di pianificazione (es. combinazioni insegnante × materia × turno)
   - Nota esplicita di onestà: task prevalentemente tecnico, dichiarato come tale
   - Uso di `itertools.product`

5. **Extra: Normalizzazione lungo un asse**
   - Interpretazione narrativa: *"confronto equo tra materie o classi con scale di punteggio diverse"*
   - Applicata a un sotto-cubo dei dati del Virgilio (non più matrice 3D random come nell'originale)
   - Funzione `normalizza_matrice` preservata dal codice originale di Robert

6. **Markdown sintesi + ponte al Notebook 3**

**Punti di attenzione tecnico-narrativi per la prossima sessione:**
- **Il prodotto cartesiano** è il task più delicato del progetto. Serve una cornice plausibile ma non sovravenduta, seguita dalla nota di trasparenza. Da gestire con attenzione: probabilmente 2-3 celle markdown di contesto che giustificano onestamente la scelta
- **La normalizzazione extra** va applicata a dati del Liceo, non a matrici random. Bisognerà probabilmente estrarre un sotto-cubo dal tensore 4D e normalizzarlo lungo l'asse "materie" per renderle comparabili

**Richiamo all'originale:** tutto il codice dei task canonici è in `/mnt/user-data/uploads/Esercizio_2.ipynb` nel materiale caricato. Da riusare praticamente così com'è, con adattamento solo dei messaggi di stampa.

---

## TODO di fine progetto

- [ ] Riempire i 3 placeholder della Cella 1 del Notebook 0 (nome corso, cognome, data)
- [ ] Esportare `environment.yml` con `conda env export --no-builds > environment.yml`
- [ ] Creare `README.md` nella root con panoramica, istruzioni setup ambiente, indice dei notebook
- [ ] Commit finale su Git (se Robert decide di mettere su repo anche questo progetto)
- [ ] Rilettura complessiva prima della consegna: coerenza terminologica, refusi, output tutti puliti

---

## Riferimenti utili per la prossima sessione

**File originali di Robert già analizzati:**
- `Esercizio_1.ipynb` → usato per Notebook 1 (completato)
- `Esercizio_2.ipynb` → base per Notebook 2 (prossima sessione)
- `Esercizio_3.ipynb` → base per Notebook 3

**Extra di Robert già ideati negli originali (da preservare e contestualizzare):**
- Extra Es.1: tasso di promozione → integrato nel Notebook 1 come KPI sintetico ✅
- Extra Es.2: normalizzazione matrice 3D lungo asse generico → andrà nel Notebook 2 come "confronto equo tra materie"
- Extra Es.3: DataFrame punteggi studenti con media e std per colonna → andrà nel Notebook 3 come "report finale consegnato alla dirigenza"

**Stile di lavoro confermato:**
- Celle passate in blocchi logici (2-4 celle per turno) per non sovraccaricare
- Ogni blocco preceduto dalla spiegazione di cosa contiene e perché
- Checkpoint di verifica dopo ogni blocco: Robert esegue, conferma, si prosegue
- Decisioni metodologiche discusse brevemente prima di scriverle in codice
