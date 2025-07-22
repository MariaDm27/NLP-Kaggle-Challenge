
# Citation Matching Challenge

Αυτό το project υλοποιεί ένα σύστημα πρόβλεψης citations μεταξύ επιστημονικών άρθρων, βασισμένο σε text-, graph- και author-based χαρακτηριστικά. Αναπτύχθηκε στο πλαίσιο του μαθήματος NLP053 (Natural Language Processing), εαρινό εξάμηνο 2025.

**Ομάδα:**
- Ελένη Γιακουμάκη (ΑΜ: 4651)
- Μαρία Δημητροπούλου (ΑΜ: 4664)

---

## Δομή Project

```
citation_project/
├── citation_prediction.ipynb       # Τελικό notebook με πλήρες pipeline
├── requirements.txt                # Απαιτούμενες βιβλιοθήκες
├── data/                           # Αρχικά δεδομένα και train/test
├── features/                       # Υπολογισμένα χαρακτηριστικά
├── model_data/                     # Τελικά X_train, X_test, y_train
├── submissions/                    # Υποβολές για το Kaggle
├── submission_trials/  			# Δοκιμαστικές υποβολές στο Kaggle. !ΑΦΑΙΡΕΘΗΚΑΝ ΛΟΓΩ ΠΕΡΙΟΡΙΣΜΟΥ ΟΓΚΟΥ!
├── other_notebooks/              	# Πειράματα με μοντέλα και feature sets
└── report/                         # Αναφορά και παρουσίαση (.docx/.pptx)
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
