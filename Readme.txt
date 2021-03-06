******** README ***********

Project ανάπτυξης λογισμικού για αλγοριθμικά προβλήματα εργασία 1η.

Στοιχεία φοιτητή:
	Όνομα: Νικόλαος
	Επίθετο:Γιαλίτσης
	Αριθμός Μητρώου:1115201400027

Τίτλος και Περιγραφή:

Υλοποίηση δομής για την εύρεση κοντινών γειτόνων στη γλώσσα C++ η οποία
επιτυγχάνεται με τη χρήση των μεθόδων LSH και Cube με μετρικές αυτές τις
ευκλείδιας απόστασης και της ομοιότητας συνιμητόνου.

Στην υλοποίηση μου έχω χρησιμοποιήσει seperate compilation και έχω
τηρήσει κανόνες απόκρυψης δεδομένων οργανώνοντας των κώδικα μου σε
header και source files και έχοντας private κομμάτια στην κλάση που
δημιούργησα με χρήση setters και getters.

 Έχει γίνει χρήση της STL της C++ και κυρίως των template της <vector>.
Για την υλοποίηση μου έχω χρησιμοποίησει και στοιχεία
της C++11 οπότε καλό θα ήταν ο υπολογιστής που θα δοκιμαστεί να έχει την τελευταία
έκδοση της C++. 


Κατάλογος αρχείων κώδικα:

1)lsh.cpp : αρχείο πηγαίου κώδικα από το οποίο προκύπτει το εκτελέσιμο για την
εκτέλεση του αλγορίθμου lsh με τον τρόπο που περιγράφεται στην εκφώνηση και με τις μετρικές
euclidean και cosine. Εδώ
γίνεται η επεξεργασία των αρχείων εισόδου dataset και τον αρχείων αναζήτησης
queries, από τα οποία πέρνουμε τα απαραίτητα στοιχεία για τη δημιουργία των δομών
αλλά και για την αναζήτηση σε αυτές.

2) cube.cpp : αρχείο πηγαίου κώδικα όπου γίνεται η εκτέλεση της μεθόδου του
υπερκύβου για να βρεθούν τα ζητούμενα. Έχει ανάλογη μορφή με το lsh.cpp.

3) lsh_classes.h : αρχείο επικεφαλίδα με τον ορισμό των συναρτήσεων και των κλάσεων
για όλες τις μεθόδους που χρησιμοποιούνται από τις ευκλείδιες και τις cosine μετρικές
με χρήση overloading για συναρτήσεις που χρησιμοποιούνται και από τις δύο μεθόδους.


Γενικά έχει δωθεί φροντίδα στο να είναι το πρόγραμμα επεκτάσιμο για double
στοιχεία.

Οδηγίες Μεταγλώτισσης του προγράμματος:

η μεταγλώττιση γίνεται κάνοντας make στον φάκελο που έχετε βάλει όλα τα αρχεία
πηγαίου κώδικα και τις επικεφαλίδες.Μπορούν να γίνουν και επιμέρους μεταγλωττίσεις
με τις εντολές make cube ή make lsh.

Γλώσσα η τελευταία έκδοση της c++.

Οδηγίες χρήσης του προγράμματος:
Η κλήση του προγράμματος μπορεί να γίνει ως εξής:
$./lsh –d <input file> –q <query file> –k <int> -L <int> -ο <output file>
$./cube –d <input file> –q <query file> –k <int> -M <int> -probes <int> -ο
<outputfile>

Για ολές τις μεθόδους και μετρικές υπάρχουν default τιμές που ακολουθούν τις οδηγίες της εκφώνησης.

Σχεδιαστικές Επιλογές ως προς τα αρχεία εισόδου:
Το προγραμμά μου υποθέτει ότι το αρχείο εισόδου δεν περιέχει id'ς . Τα ιd's αποτελούν μέρος της
εσωτερικής λετουργικότητας των μεθόδων και παράγονται αυτόματα στο runtime.

Parsing Είσόδου:
Εύρεση μετρικής: 
	αν η πρώτη γραμμή περιέχει το όνομα euclidean εκτελείται η ευκλείδια μετρική
	αν η πρώτη γραμμή περιέχει το όνομα cosine εκτελείται η cosine μετρική
	αν η πρώτη γραμμή είναι κενή εκτελείται η ευκλείδια μετρική
	αν το αρχείο ξεκινάει κατευθείαν με points τότε εκτελείται η ευκλείδια μετρική
Radius:
	αν η πρώτη γραμμή περιέχει τη λέξη Radius: x τότε η ακτίνα είναι x
	aν η πρώτη γραμμή περιέχει τη λέξη Radius:   τότε η ακτίνα είναι 1 για cosine και 350 για ευκλείδια
	αν η πρώτη γραμμή είναι κενή τότε η ακτίνα είναι 1 για cosine και 350 για ευκλείδια
	αν δίνεται κατευθείαν σημείο τότε η ακτίνα είναι 1 για cosine και 350 για ευκλείδια


Modulo: Επειδή η C++ δεν παρέχει το modulo αλλά το remainder έπρεπε να ορίσω δικές μου συναρτήσεις
modulo kαι long modulo ώστε να επιστρέφονται θετικές τιμές αλλά και να δουλεύουν για διάφορα μεγέθη τύπων.

Overflow: O κώδικας είναι γεμάτος assert() που εξασφαλίζουν ότι δεν παρουσιάζονται αρνητικές τιμές κατά τη
διάρκεια εκτέλεσης.Όσον αφορά τη μετρική συνημιτονου το ri παίρνει τιμές στο διάστημα [-20,20] έτσι ώστε
να μην δημιουργείται πολύ μεγάλος αριθμός

Κατανομές: 
	Χρησιμοποιώ τις συναρτεις της boost βιβλιοθήκης για τη δημιουργία κανονικών και ομοιόμορφων κατανομών.
	Χρησιμοποιώ ως seed το random device

Οι παρακάτω είναι εκτελέσεις των 4 συνδυασμών μεθόδων και μετρικών στο υποσυνολο των 1000
σημείων του input small και με query file το query_small.

LSH Euclidean(-k 11 )
*********************
Average Query Time : 0.0270204 seconds
Approx 1.25799
Max Ratio :1.39148
Space :428173 bits
*********************


Cube Euclidean(Cube Cosine(-k 11 -probes 30 -M 100 )
*********************
Average Query Time : 0.385728 seconds
Approx 1.1884
Max Ratio :1.58537
Space :28741451 bits

LSH Cosine (-k 11)
*********************
Average Query Time : 0.0566942 seconds
Mean LSH ratio: 1.33838
Max Ratio :2.14712
Space :372892 bits
*********************

Cube Cosine(-k 11 -probes 30 -M 100 )
*********************
Average Query Time : 0.535622 seconds
Approx 1.26531
Max Ratio :2.2629
Space :36945738 bits
*********************
*********************

Παρατηρήσεις:

Βλέπουμε λοιπόν ότι τα αποτελέσματα είναι παρόμοια και ότι επίσης:

Ο υπερκύβος στις μεγάλες διαστάσεις απαιτεί πολύ περισσότερη μνήμη απότι ο LSH αλγόριθμος αλλά
έχει λίγο μεγαλύτερη ακρίβεια(μέση).

Βέβαια βλέπουμε ότι ο χρόνος που απαιτεί ο υπερκύβος είναι πολύ μεγαλύτερος του LSH για
τον υπολογισμο του ΝΝ σε μεγάλες διαστάσεις. Όμως ο lsh απαιτεί μεγαλύτερο χρονο κατά τη δημιουργία των
δομών του hashtable.

Έχοντας όμως ήδη έτοιμες τις δομές και για πολυ μεγάλες διαστάσεις δεδομένων
καλύτερη επιλογή είναι ο lsh.

Όλα αυτά εξηγούνται και από τις πολυπλοκότητες της κάθε μεθόδου.
