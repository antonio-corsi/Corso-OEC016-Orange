# Corso-OEC016-Orange
Repository del corso OEC016 del 3-4-5 novembre 2025

Programma della prima giornata (3.11.2025) - mattina
- Tassonomia (AI vs ML vs NN vs DL vs genAI)
- Dati strutturati (tabelle righe / colonne: tabelle SQL, fogli excel, google sheet, ecc) vs non strutturati (testo, immagini, 
video, audio, 3D). Il fuoco del corso è sui primi.
- File csv: molto usati nel ML (supportati da TUTTI gli ambienti di data management; 4 save as in excel --> evitare UTF-8, macintosh, ms-dos), 2 separatori: virgola in US e punto e virgola in EU)
- La struttura base nel ML è il dataframe, che sta in memoria ("data table" in Orange), dati "tidy" (2 cose: a. gli oggetti di business sono sulle righe e le loro proprietà sulle colonne; b. ogni cella contiene un valore singolo --> no "multi-valued cells".
- ML lavora su file singoli anzichè database (no navigazione del DB)
- Predittori (le colonne del dataframe utilizzate per prevedere la colonna risposta, anche detti "feature") vs risposta (la colonna da prevedere).
- Le colonne del dataframe sono anche dette "variabili"
- Variabili quantitative, anche dette numeriche (dominio infinito potenzialmente) vs qualitative, anche dette categoriche (dominio finito ed in genere piccolo). Non è il formato a decidere il tipo di variabile: possiamo avere variabili
 qualitative memorizzate in formato numerico: 0-setosa, 1- virginica, 2-versicolor)
- Machine Learning significa "learning" (apprendimento) sui dati ("machine").
- LEARNING: a. algoritmo (una sequenza di passi) -->  b. fit dell'algoritmo sul dataset di training -->  c. modello predittivo (un'equazione matematica, una rete neurale fatta di livelli e di neuroni, albero decisionale, ecc))
- dataset IRIS: utile perchè: "storico" (lo usò Fisher ed è ancora oggi usatissimo); semplice e facile da capire; struttura molto generalizzabile (predittori numerici e risposta categorica)
- Dataset di prova: "UCI ML datasets", "kaggle datasets" --> centinaia di dataset utilizzabili come prova degli algoritmi di ML


- EDA (Analisi Esplorativa dei Dati): si parte ccosì, non con la costruzione del modello predittivo: identificare Missing Value e outlier (possono impattare molto l'accuratezza del modello), 3 plot (scatterplot, boxplot, istogramma), 
correlazioni  tra coppie di variabili numeriche, pattern
- Trend vs pattern: il primo è auto-parlante (lineare, non lineare, crescente, decrescente, esponenziale, ecc), il pattern (una forma ripetitiva nei dati, per esempio una ciclicità in una serie temporale)

---


Programma della prima giornata (3.11.2025) - pomeriggio

- fine del wf "getting started"

- Readme
- Commit: come funziona. Aggiungere slide mancanti. 

--> se la colonna risposta è qualitativa --> è un problema di CLASSIFICAZIONE e la metrica è la "classification accuracy
--> se la colonna risposta è quantitativa --> è un problema di PREVISIONE NUMERICA e la metrica è lo RMSE (Rooted Mean Square Error)
I predittori invece possono essere indifferentemente quantitativi o qualitativi (sono trattati in modo differente)

- la metrica di accuratezza della classificazione ("classification accuracy")
- il primo modello predittivo in Orange (l'albero per il dataset Titanic); vari modelli per il dataset Credit
- la metrica di accuratezza della regressione (RMSE)

- vari casi d'uso di ML

- nella classificazione l'incertezza è espressa tramite le probabilità delle classi, nella regressione l'incertezza è espressa tramite un intervallo di confidenza 