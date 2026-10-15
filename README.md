# Sistema Predittivo e di Monitoraggio del Rischio Incendi Boschivi
Un sistema software basato su Machine Learning progettato per prevedere, analizzare e monitorare il rischio di incendi boschivi sul territorio italiano. Il progetto unisce dati meteorologici, storici e geografici per stimare la probabilità di incendio, integrando strumenti per la validazione da parte di esperti forestali e test di affidabilità stagionali. // usando come IDE pycharm

# Caratteristiche Principali
Modelli di Previsione: Utilizza algoritmi di classificazione (Random Forest e Gradient Boosting) per stimare la probabilità di innesco degli incendi in base alle condizioni ambientali.

Database Storico Geospaziale: Gestisce uno spazio di archiviazione SQLite che raccoglie e analizza gli incidenti passati considerando coordinate geografiche, temperature, umidità, vento, precipitazioni e tipo di vegetazione.

Validazione con Esperti: Un modulo dedicato alla raccolta e al confronto tra le stime prodotte dall'intelligenza artificiale e le valutazioni sul campo effettuate da operatori ed esperti del settore forestale.

Framework di Test Stagionale: Esegue simulazioni sistematiche per misurare le performance predittive del sistema (tramite metriche come accuratezza, precisione e area sotto la curva ROC) suddivise per periodi dell'anno.

# Requisiti di Installazione
Assicurati di avere Python 3.8 o versioni successive installato sul tuo computer. Puoi installare le librerie richieste eseguendo questo comando nel terminale:

Bash
pip install numpy pandas requests scikit-learn joblib
Struttura del Progetto
Plaintext
├── fire_incidents.db         # Database locale SQLite con lo storico degli incendi
├── expert_validations.db     # Database per la memorizzazione dei pareri degli esperti
└── validation_requests/      # Cartella per la gestione delle richieste di riscontro pendenti

# Esempio di Utilizzo
Python
from datetime import datetime

// Inizializzazione del database storico e del sistema di validazione
db = HistoricalFireDatabase()
expert_system = ExpertValidationSystem()

# Esempio di avvio della validazione stagionale completa
// validation_framework = SeasonalValidationFramework(fire_system, db)
// report = validation_framework.run_comprehensive_seasonal_validation()

# Output di Esecuzione
```ENHANCED FIRE PREDICTION SYSTEM - DEMO
==================================================
Initializing Enhanced Fire Risk System v3.0...
Enhanced system ready!

1. PREDICTION WITH HISTORICAL CONTEXT
----------------------------------------
Fire Probability: 53.3%
Risk Level: MEDIO
Historical Incidents (5 years): 3
Prediction ID: pred_20250908_165159

2. COMPREHENSIVE VALIDATION
----------------------------------------
Running comprehensive system validation...
Starting comprehensive seasonal validation...

=== Validating WINTER ===
  Accuracy: 0.754
  AUC-ROC: 0.885
  Precision: 1.000
  Recall: 0.508

=== Validating SPRING ===
  Accuracy: 0.805
  AUC-ROC: 0.954
  Precision: 1.000
  Recall: 0.610

=== Validating SUMMER ===
  Accuracy: 0.774
  AUC-ROC: 0.994
  Precision: 1.000
  Recall: 0.548

=== Validating AUTUMN ===
  Accuracy: 0.759
  AUC-ROC: 0.910
  Precision: 1.000
  Recall: 0.519
Generating 50 sample expert validations...
Recorded outcome for prediction demo_pred_000: FIRE
Recorded outcome for prediction demo_pred_001: NO FIRE
Recorded outcome for prediction demo_pred_002: NO FIRE
Recorded outcome for prediction demo_pred_003: FIRE
Recorded outcome for prediction demo_pred_004: FIRE
Recorded outcome for prediction demo_pred_005: FIRE
Recorded outcome for prediction demo_pred_006: NO FIRE
Recorded outcome for prediction demo_pred_007: NO FIRE
Recorded outcome for prediction demo_pred_008: FIRE
Recorded outcome for prediction demo_pred_009: FIRE
Recorded outcome for prediction demo_pred_010: FIRE
Recorded outcome for prediction demo_pred_011: FIRE
Recorded outcome for prediction demo_pred_012: FIRE
Recorded outcome for prediction demo_pred_013: NO FIRE
Recorded outcome for prediction demo_pred_014: NO FIRE
Recorded outcome for prediction demo_pred_015: FIRE
Recorded outcome for prediction demo_pred_016: FIRE
Recorded outcome for prediction demo_pred_017: NO FIRE
Recorded outcome for prediction demo_pred_018: NO FIRE
Recorded outcome for prediction demo_pred_019: FIRE
Recorded outcome for prediction demo_pred_020: FIRE
Recorded outcome for prediction demo_pred_021: FIRE
Recorded outcome for prediction demo_pred_022: FIRE
Recorded outcome for prediction demo_pred_023: FIRE
Recorded outcome for prediction demo_pred_024: FIRE
================================================================================
COMPREHENSIVE VALIDATION REPORT
================================================================================

SEASONAL VALIDATION:
  Overall Accuracy: 77.5%
  Overall AUC-ROC: 0.929
  Total Samples: 1218
  Best Season: spring

EXPERT VALIDATION:
  Expert Agreement Score: 89.1%
  Sample Size: 100
  High Confidence Cases: 57

PERFORMANCE FEEDBACK:
  Recent Accuracy: 64.0%
  Feedback Samples: 50
  Actual Fire Rate: 62.0%

IMPROVEMENT SUGGESTIONS:
  1. Overall accuracy below 80% - consider model retraining
  2. Low accuracy for BASSO risk level (0.58) - review threshold calibration
  3. Low accuracy for MEDIO risk level (0.57) - review threshold calibration
================================================================================

3. PERFORMANCE ANALYSIS
----------------------------------------
============================================================
MODEL PERFORMANCE REPORT
============================================================

OVERALL METRICS (last 90 days):
  Accuracy: 64.0%
  Samples: 50
  Avg Predicted Probability: 0.498
  Actual Fire Rate: 62.0%

RISK LEVEL PERFORMANCE:
  BASSO:
    Accuracy: 57.9%
    Samples: 19
    Fire Rate: 42.1%
  MEDIO:
    Accuracy: 57.1%
    Samples: 14
    Fire Rate: 71.4%
  ALTO:
    Accuracy: 69.2%
    Samples: 13
    Fire Rate: 69.2%
  CRITICO:
    Accuracy: 100.0%
    Samples: 4
    Fire Rate: 100.0%

IMPROVEMENT SUGGESTIONS:
  1. Overall accuracy below 80% - consider model retraining
  2. Low accuracy for BASSO risk level (0.58) - review threshold calibration
  3. Low accuracy for MEDIO risk level (0.57) - review threshold calibration
  4. Low accuracy for ALTO risk level (0.69) - review threshold calibration
============================================================

Demo completed successfully!
