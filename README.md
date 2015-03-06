# Δημιουργία Λαβυρίνθων

Γνωρίζουμε ότι αν θέλουμε να διατρέξουμε ένα γράφο μπορούμε να χρησιμοποιήσουμε είτε την κατά βάθος είτε την κατά πλάτος αναζήτηση. Γνωρίζουμε επίσης ότι οι μέθοδοι αυτοί αντιστοιχούν σε τρόπους εξερεύνησης ενός λαβυρίνθου.

Ας δούμε τώρα το αντίστροφο πρόβλημα, με ποιον τρόπο μπορούμε να φτιάξουμε λαβυρίνθους; Ένας τρόπος είναι ο παρακάτω:

1. Θεωρούμε ότι έχουμε έναν γράφο n x n, δηλαδή με n γραμμές που η κάθε μία τους έχει n κόμβους διατεταγμένους όπως σε ένα καμβά. Οι κόμβοι αντιστοιχούν στα δωμάτια του λαβυρίνθου. Αρχικά θεωρούμε ότι κάθε κόμβος είναι συνδεμένος με όλους τους γειτονικούς του κόμβους. Οι γωνιακοί κόμβοι έχουν δύο γείτονες, οι κόμβοι που βρίσκονται στην περιφέρεια του γράφου αλλά όχι στις γωνίες έχουν τρεις γείτονες και οι εσωτερικοί κόμβοι έχουν τέσσερεις γείτονες.

<img src="grid_graph.png" alt="Πλέγμα n x n" height=350>

2. Ξεκινάμε από ένα κόμβο του γράφου.

3. Σημειώνουμε ότι έχουμε επισκεφτεί τον κόμβο και παίρνουμε τη λίστα με τα γειτονικούς κόμβους του, δηλαδή τα γειτονικά δωμάτιά του. Παίρνουμε με τυχαία σειρά τα γειτονικά στοιχεία και προχωράμε ως εξής:
  
  * Αν δεν έχουμε επισκευτεί το γειτονικό κόμβο, πηγαίνουμε σε αυτόν τον κόμβο, αποθηκεύουμε το σύνδεσμο μεταξύ των δύο κόμβων και συνεχίζουμε αναδρομικά τη διαδικασία από το βήμα 3 με το γειτονικό στοιχείο.

Στην ουσία δηλαδή κάνουμε μια κατά βάθος αναζήτηση του γράφου όπου σε κάθε κόμβο παίρνουμε τους γειτονικούς του με τυχαία σειρά και αποθηκεύουμε κάπου τους συνδέσμους που ακολουθήσαμε.

Όταν ολοκληρώσουμε τη διαδικασία έχουμε στα χέρια μας ένα νέο γράφο. Οι κορυφές του είναι οι κορυφές του αρχικού γράφου και οι σύνδεσμοι είναι οι σύνδεσμοι που ακολουθήσαμε. Αυτός ο γράφος είναι ένας λαβύρινθος.

Εσείς θα φτιάξετε ένα πρόγραμμα σε γλώσσα Python το οποίο θα κατασκευάζει λαβυρίνθους με αυτή τη διαδικασία. Το πρόγραμμα θα καλείται ως εξής:

```
python make_maze.py <n> <start_x> <start_y> <seed> <output_file>
```

Προσέξτε ότι αντί για `python` στο σύστημά σας μπορεί να πρέπει να δώσετε `python3`.

Το πρόγραμμα λοιπόν παίρνει τέσσερεις παραμέτρους, ως εξής:

* `n` είναι ο αριθμός των γραμμών και των στηλών του πλέγματος του γράφου.
*  `start_x` είναι η x συντεταγμένη του κόμβου εκκίνησης, με `0 <= start_x < n`
*  `start_y` είναι η y συντεταγμένη του κόμβου εκκίνησης, με `0 <= start_y < n`
*  `seed` είναι ένας αριθμός ή συμβολοσειρά, θα εξηγήσουμε στη συνέχεια.
*  `output_file` είναι το αρχείο στο οποίο θα αποθηκευτεί ο λαβύρινθος.



