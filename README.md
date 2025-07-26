
# Citation Matching Challenge

Αυτό το project υλοποιεί ένα σύστημα πρόβλεψης citations μεταξύ επιστημονικών άρθρων, βασισμένο σε text-, graph- και author-based χαρακτηριστικά. Αναπτύχθηκε στο πλαίσιο του μαθήματος NLP053 (Natural Language Processing), εαρινό εξάμηνο 2025.

**Ομάδα:**
- Ελένη Γιακουμάκη
- Μαρία Δημητροπούλου

---

## Project data από το Kaggle: https://www.kaggle.com/competitions/nlp-cse-uoi-2025/data

--- 

## Δομή Project

```
citation_project/
├── data/ # Raw δεδομένα και train/test splits
├── features/ # Extracted features
├── model_data/ # X_train, X_test, y_train
├── submissions/ # Τελικές υποβολές για Kaggle
├── submission_trials/ # Δοκιμαστικές υποβολές (αφαιρέθηκαν μεγάλα αρχεία)
├── citation_prediction.ipynb # Τελικό notebook με το pipeline
├── submission_experiments.ipynb # Πειράματα και alternative approaches
├── requirements.txt # Απαιτούμενες βιβλιοθήκες
├── NLP-report.pdf # Τελική αναφορά
├── kaggle_challenge_2025.pdf # Εκφώνηση Kaggle Challenge
└── NLP_exam_challenge_June_2025.pdf # Σχετικό αρχείο εξετάσεων
```

---

## Εκτέλεση

1. Δημιουργήστε περιβάλλον Python (π.χ. με `venv` ή `conda`)
2. Εγκαταστήστε τις απαιτούμενες βιβλιοθήκες:
```bash
pip install -r requirements.txt
```
3. Εκτελέστε το κύριο notebook:  
   `citation_prediction.ipynb`

---

## Περιεχόμενο Notebook

- Προεπεξεργασία και καθαρισμός δεδομένων
- Υπολογισμός χαρακτηριστικών (TF-IDF, BERT, χαρακτηριστικά γράφου, συγγραφείς)
- Συνδυασμός χαρακτηριστικών και δημιουργία τελικών datasets
- Εκπαίδευση XGBoost μοντέλου και υποβολές

---

## Αποτελέσματα

- `submission_best.csv`: Public score 0.13758 (XGBoost, full features)
- `submission_2nd.csv`: Public score 0.14199 (XGBoost, selected features)

---

## Σημειώσεις

- Όλα τα χαρακτηριστικά αποθηκεύονται σε αρχεία `.csv` για εύκολη επαναχρησιμοποίηση
- Τα notebooks έχουν διαμορφωθεί ώστε να εκτελούνται modular, χωρίς εξάρτηση από κοινό αρχικό state
- Οι δύο καλύτερες υποβολές υπάρχουν τόσο στο `citation_prediction.ipynb` όσο και στο `submission_experiments.ipynb`
- ΣΗΜΑΝΤΙΚΌ: Τα αρχεία abstracts.txt, authors.txt, edgelist.txt και test.txt δεν περιλαμβάνονται στον φάκελο data λόγω μεγέθους και επειδή έχουν δοθεί σε όλους με την εκφώνηση. Για αναπαραγωγή της εργασίας, αρκεί να προστεθούν στον data.
