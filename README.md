# Corso-OEC016-Orange (Introduzione al ML predittivo)
3-4-5 novembre 2025

Programma della prima giornata (3.11.2025) - mattina:

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


- EDA (Analisi Esplorativa dei Dati): si parte così, non con la costruzione del modello predittivo: identificare Missing Value e outlier (possono impattare molto l'accuratezza del modello), 3 plot (scatterplot, boxplot, istogramma), 
correlazioni  tra coppie di variabili numeriche, pattern
- Trend vs pattern: il primo è auto-parlante (lineare, non lineare, crescente, decrescente, esponenziale, ecc), il pattern (una forma ripetitiva nei dati, per esempio una ciclicità in una serie temporale)

Su questi punti abbiamo visto le seguenti slide del PDF "Introduzione alla DS":
- dataframe: slide 12-13, 15-16, 30
- EDA : slide 39
- pattern: slide 40
- processo di ML: slide 49, 2-3


--------------------------------------------------------------------------------------------------------------------------


Programma della prima giornata (3.11.2025) - pomeriggio

- fine del wf "getting started"

- Readme
- Commit: come funziona.

--> se la colonna risposta è qualitativa --> è un problema di CLASSIFICAZIONE e la metrica è la "classification accuracy
--> se la colonna risposta è quantitativa --> è un problema di PREVISIONE NUMERICA e la metrica è lo RMSE (Rooted Mean Square Error)
I predittori invece possono essere indifferentemente quantitativi o qualitativi (sono trattati in modo differente)

- la metrica di accuratezza della classificazione (CA = "classification accuracy") in percentuale (da 0% a 100% - anche se in genere è espressa da 0 a 1). Più alta, meglio è.
CA esprime il numero di classificazioni corrette sul totale. Il complemento a 1 della CA (cioè 1 - CA) esprime l'errore di classificazione, ovvero il numero di "misclassificazioni", ad esempio, con due classi possibili (uno
scenario molto frequente) uno 0 classificato come 1 oppure un 1 classificato come 0 sul totale delle classificazioni.

- nei problemi di classificazione in genere la classe 1 (il "positivo") rappresenta l'evento di interesse, in genere abbastanza raro: il paziente ha la malattia, il cliente non restituisce il prestito, la transazione di carta di credito 
è una frode, la email è spam, il cliente abbandona l'azienda (churn). Esistono anche eventi di interesse di significato positivo, ad esempio: il cliente risponde al contatto commerciale, l'ad sensing (click sulla pubblicità 
mostrata dal sito, la sopravvivenza al naufragio del Titanic).
La classe 0, invece, esprime in genere l'evento più frequente, che NON è di "interesse". 
Attenzione: la classe 1, poichè rappresenta un evento "raro", è poco rappresentata nel dataset di training. E' un problema perchè in questo modo l'algoritmo, fittato (adattato) ai dati, IMPARA molto meglio le relazioni
tra i predittori e la classe 0 e molto meno  le relazioni tra i predittori e la classe 1 (perchè ha pochi esempi). Le due classi 0 e 1 devono invece essere abbastanza bilanciate. Ci sono delle tecniche di RI-BILANCIAMENTO 
delle classi, la principale è lo SMOTE, vedi: https://machinelearningmastery.com/smote-oversampling-for-imbalanced-classification/ 
In Orange NON èimplementato --> https://github.com/biolab/orange3/pull/3269

- il primo modello predittivo in Orange (per il dataset Titanic); vari modelli per il dataset Credit
- con un classificatore binario (cioè 2 classi possibili) abbiamo 4 possibili esiti: TP, TN, FP, FN. La semplice metrica CA non è sufficiente perchè spesso il costo del FN >> costo del FP (vale per molti casi: default creditizio,
esame medici, ecc). Serve la matrice di confusione, che separa i 4 casi.
Emblematico è il caso del dataset Titanic (vedi "Titanic Classifier.ows) fittato con 2 modelli di classificazione (KNN e Regressione Logistica) cche forniscono la stessa CA ma #FN molto diverso.

- la metrica di accuratezza della regressione (RMSE)

- nella classificazione l'incertezza è espressa tramite le probabilità delle classi, nella regressione l'incertezza è espressa tramite un intervallo di confidenza 

- vari casi d'uso di ML (file PDF "Introduzione alla DS" --> slide 138 --> 183 e slide 7 --> 10)

- Object detection --> video AlertCalifornia (su github) e video sulle autostrade (https://www.linkedin.com/posts/ultanorourke_ai-analytics-datascience-activity-7159608320360636418-bAbL?utm_source=share&utm_medium=member_desktop)

--------------------------------------------------------------------------------------------------------------------------
 
Programma della seconda giornata (4.11.2025) - mattina

- RMSE (di test)

I modelli di ML sono ALLENATI sui dati di training e TESTATI su altri dati di test. Cioè, in pratica, la tabella, le sue righe, è suddivisa in 2 porzioni: training e test, normalmente nella percentuale 75%-25%. 
Questa è una delle principali REGOLE del ML. Quella che conta è l'accuratezza sui dati di TEST.
NB. La suddivisione è casuale (è come estrarre le palline dall'urna del Lotto). Ciò pone il problema della RIPRODUCIBILITA' dei risultati (con gli stessi dati e lo stesso software ogni utente ottiene risultati differenti).
Nei PC e nel software è impossibile generare veri numeri casuali, in realtà si parla di generazione "pseudo-casuale" perchè originata da un SEME (seed, random state, ecc). Cioè, a parità di seme, otteniamo tutti la 
STESSA suddivisione tra treeaining e test. Cioè otteniamo la riproducibilità dei risultati!

RMSE (Rooted Mean Square Error): vedi voce Wikipedia EN (https://en.wikipedia.org/wiki/Root_mean_square_deviation)
Vedi "Regressione su Credit.ows". 
Poichè RMSE è un "errore", più basso è, meglio è.
A differenza della CA della classificazione, che è "normalizzata tra 0 e 1", RMSE della Regressione NON ha una scala di riferimento, cioè può assumere qualsiasi valore. 

----

FRAMEWORK GENERALE di valutazione dei modelli predittivi.
A questo punto abbiamo 3 metriche (CA e CM per la classificazione e RMSE per la regressione) di valutazione della capacità predittiva dei vari modelli nel TEST, semplici da comprendere, facili da calcolare con 
tutti i software  (Orange, Python, R, Excel) e utili per CONFRONTARE i modelli. Cioè, noi possiamo fittare diversi algoritmi sui dati di training, calcolare le metriche sui dati di test e confrontare i modelli per individuare 
quello migliore in quel caso (l'accuratezza più alta oppure RMSE più basso).
Questa framework è usata anche per VALUTARE modelli forniti da TERZI (un fornitore, un collega, ecc).

----


- finire CdU (primo e secondo gruppo)

- fine del wf "getting started"
