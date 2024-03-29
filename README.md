# Sensorlab38-Solar-Home
Το όνομα των ομάδων είναι "Smart Kids".  Στο πρότζεκτ συμμετείχαν οι παρακάτω μαθητές:

,,,, Ονόματα ...
Η διεύθυνση στο Github είναι :  https://github.com/SensorLab38/Sensorlab38-Solar-Home/edit/main/README.md

Συντονιστής του έργου: Γιώργος Κατσίμπαλης. Ηλεκτρολόγος Μηχανικός

Το πρότζεκτ θα αναπτυχθεί σε επτά (7) φάσεις και αναμένεται να έχει ολοκληρωθεί έως τις 15 Μαϊου 2023.

Οι φάσεις που θα ακολουθήσουν είναι οι παρακάτω:

Φάση 1η
Συζήτηση για την κλιματική αλλαγή και την εύρεση της ιδέας για το πρότζεκτ με το οποίο θα λάβουμε μέρος στον διαγωνισμό.

Ζητήθηκε από όλους τους μαθητές να καταθέσουν προτάσεις και ιδέες για την εργασία με θέμα την κλιματική αλλαγή, πάνω στην οποία θα εργαστούμε. Στη συζήτηση που ακολούθησε, υιοθετήθηκε μια κοινά αποδεκτή πρόταση για το οικολογικό σπίτι που θεωρήθηκε μια εφαρμόσιμη ιδέα.

Το σχέδιο του υποτιθέμενου σπιτιού φαίνεται στο παρακάτω σχήμα.

Solar-Home

Φάση 2η
Σχεδίαση και μελέτη της κατασκευής. Ξεκινάει παράλληλα το θεωρητικό μέρος, δηλαδή ο προγραμματισμός με την γλώσσα C++

Με τη βοήθεια του εργαστηρίου Sensorlab38, μελετήσαμε τρία βασικά προγράμματα τα οποία θα μας βοηθήσουμε να 
αναπτύξουμε και να καταλάβουμε καλύτερα το πρόγραμμα για την λειτουργία του οικολογικού σπιτιού.

https://github.com/SensorLab38/Sensorlab38-Solar-Home/edit/main/README.md

// Με το πρόγραμμα αυτό αναβοσβήνουμε δύο λαμπάκια (LED).

int led1 = 8;                  // Συνδέουμε το LED1 στο pin 8 του Arduino.  
int led2 = 9;                  // Συνδέουμε το LED2 στο pin 9 του Arduino.

void setup() 
{                              // Μετά το άνοιγμα της αγγύλη ξεκινάνε οι αναγκαίες δηλώσεις. 
pinMode(led1, OUTPUT);         // Δηλώνουμε ότι το pin 8 του Arduino να είναι σε κατάσταση εξόδου. 
pinMode(led2, OUTPUT);         // Δηλώνουμε ότι το pin 8 του Arduino να είναι σε κατάσταση εξόδου.
}                              // Κλείνουμε την αγγύλη.

void loop() 
{                              // Μετά το άνοιγμα της αγγύλης τοποθετούμε το κυρίως πρόγραμμα.
analogWrite(led1, HIGH);       // Με την εντολή analogWrite το arduino δίνει 5 Volt στο pin 8 για να ανάψει το Led.    
delay(1000);                   // Δίνουμε μια καθυστέριση για ένα δευτερόλεπτο (1000 msec).
analogWrite(led2, HIGH);       // Με την εντολή analogWrite το arduino δίνει 5 Volt στο pin 9 για να ανάψει το Led.
delay(1000);                   // Δίνουμε μια καθυστέριση για ένα δευτερόλεπτο (1000 msec).

analogWrite(led2, LOW);        // Με την εντολή analogWrite το arduino δίνει 0 Volt στο pin 8 για να σβήσει το Led.
delay(1000);                   // Δίνουμε μια καθυστέριση για ένα δευτερόλεπτο (1000 msec).
analogWrite(led2, LOW);        // Με την εντολή analogWrite το arduino δίνει 0 Volt στο pin 8 για να σβήσει το Led.
delay(1000);                   // Δίνουμε μια καθυστέριση για ένα δευτερόλεπτο (1000 msec).
}                              // Κλείνουμε την αγγύλη.
![Solar-Home]() 

Συνεχίζουμε με το πρόγραμμα για την λειτουργία του LCD (Liquid Crystall Display) όπως φαίνεται στο παρακάτω σχήμα.

![Solar-Home]()

//Το πρόγραμμα αυτό μας περιγράφει όλες τις λειτουργίες του LCD (16Χ2).

#include <LiquidCrystal_PCF8574.h>  // Η βιβλιοθήκη LiquidCrystal_PCF8574.h, μας επιτρέπει επικοινωνία με το LCD.
#include <Wire.h>                   // Η βιβλιοθήκη Wire.h, μας επιτρέπει την επικοινωνίας του Arduino με τις άλλες μονάδες. 

LiquidCrystal_PCF8574 lcd(0x27);    // Θέτουμε το LCD στην διεύθυνση (0χ27) ή (0Χ3F) της μνήμης του Arduino.

int t=800;                          // Ορίζουμε την μεταβλητή του χρόνου t για καθυστέρηση 800 msec. 

void setup()                       
{                                   // Μετά το άνοιγμα της αγγύλη ξεκινάνε οι αναγκαίες δηλώσεις.    
Wire.begin();                       // Δηλώνουμε ότι ξεκινάει η επικοινωνία του Arduino με το LCD.
Wire.beginTransmission(0x27);       // Δηλώνουμε την διεύθυνση της μνήμης του LCD ότι είναι η (0Χ27) ή (0Χ3F) .      
lcd.begin(16, 2);                   // Δηλώνουμε ότι το LCD που χρησιμοποιούμε, έχει 16 στήλες και 2 σειρές.
}

void loop()                         
{							        // Μετά το άνοιγμα της αγγύλη ξεκινάει το κυρίως πρόγραμμα μας. 
lcd.setBacklight(255);              // Δίνουμε εντολή να ανάψει το LCD.
lcd.print("Hello Gays.");           // Δίνουμε εντολή να τυπωθεί ότι περιέχεται μέσα στα εισαγωγικά.
delay(t);                           // Δίνουμε καθυστέρηση 800 msec. 
lcd.clear();                        // Δίνουμε εντολή να καθαρίσει η οθόνη του LCD.

lcd.print("Let us start to ");      // Δίνουμε εντολή να τυπωθεί ότι περιέχεται μέσα στα εισαγωγικά.
delay(t);                           // Δίνουμε καθυστέρηση 800 msec. 

lcd.setCursor(0, 1);                // Δίνουμε εντολή για να ορίσουμε τον κέρσορα στην στήλη 0 και στην γραμμή 1.
lcd.print("program the LCD ");      // Δίνουμε εντολή να τυπωθεί ότι περιέχεται μέσα στα εισαγωγικά.
delay(t);                           // Δίνουμε καθυστέρηση 800 msec. 
lcd.clear();                        // Δίνουμε εντολή να καθαρίσει η οθόνη του LCD.

lcd.print("monitor with I2C");      // Δίνουμε εντολή να τυπωθεί ότι περιέχεται μέσα στα εισαγωγικά.
delay(t);                           // Δίνουμε καθυστέρηση 800 msec. 
    
lcd.setCursor(0, 1);                // Δίνουμε εντολή για να ορίσουμε τον κέρσορα στην στήλη 0 και στην γραμμή 1
lcd.print("communication   ");      // Δίνουμε εντολή να τυπωθεί ότι περιέχεται μέσα στα εισαγωγικά.
delay(t);                           // Δίνουμε καθυστέρηση 800 msec. 
lcd.clear();                        // Δίνουμε εντολή να καθαρίσει η οθόνη του LCD.

lcd.print("Please attent   ");      // Δίνουμε εντολή να τυπωθεί ότι περιέχεται μέσα στα εισαγωγικά.
delay(t);                           // Δίνουμε καθυστέρηση 800 msec. 
        
lcd.setCursor(0, 1);                // Δίνουμε εντολή για να ορίσουμε τον κέρσορα στην στήλη 0 και στην γραμμή 1 
lcd.print("carefully.      ");      // Δίνουμε εντολή να τυπωθεί ότι περιέχεται μέσα στα εισαγωγικά.
delay(t);                           // Δίνουμε καθυστέρηση 800 msec. 
lcd.clear();                        // Δίνουμε εντολή να καθαρίσει η οθόνη του LCD.

lcd.print("Thanks for watch.");     // Δίνουμε εντολή να τυπωθεί ότι περιέχεται μέσα στα εισαγωγικά.
delay(t);                           // Δίνουμε καθυστέρηση 800 msec. 
    
lcd.setCursor(0, 0);                // Δίνουμε εντολή για να ορίσουμε τον κέρσορα στην στήλη 0 και στην γραμμή 0.
lcd.print("Digilab Education");     // Δίνουμε εντολή να τυπωθεί ότι περιέχεται μέσα στα εισαγωγικά.
delay(5000);                        // Δίνουμε καθυστέρηση 5 sec. 
lcd.setBacklight(0);                // Δίνουμε εντολή για να σβύσει η οθόνη του LCD.   
delay(t);                           // Δίνουμε καθυστέρηση 800 msec. 
lcd.clear();                        // Δίνουμε εντολή να καθαρίσει η οθόνη του LCD.
lcd.setBacklight(255);              // Δίνουμε εντολή να ανάψει το LCD.
lcd.blink();                        // Δίνουμε εντολή για να αναβοσβύνει ο κέρσορας.
while(1);                           // Δίνουμε την εντολή (while) για να τερματίσει το πρόγραμμα.
}

Φάση 3η
Στη Φάση αυτή προχωρήσαμε με την συναρμολόγηση και ολοκλήρωση της κατασκευής. Συνεχίζεται η διδασκαλία της γλώσσας προγραμματισμού C++

Solar-Home

Φάση 4η
Συζήτηση και απόφαση για τα ηλεκτρονικά υλικά (Πάνελ, αισθητήρες κ.ά.) που θα απαιτηθούν για την κατασκευή.

Εκτίμηση κόστους υλικών κατασκευής:
 Υλικά για το ξύλινο σπιτάκι                  Τεμ  1        20,00€
 Φωτοβολταϊκό Πάνελ 5W                        Τεμ. 1         9,90€
 Solar Battery Charger                        Tεμ. 1        13.00€
 Μπαταρία επαναφορτηζόμενη 12V                Τεμ. 1         6,00€
 Arduino MEGA                                 Τεμ. 1        11,90€
 Breadboard                                   Τεμ: 1         4,00€
 Leds 10mm                                    Τεμ. 6         1.00€
 Laser Beem                                   Tεμ. 10        4,20€
 Photoresistor LDR                            Τεμ. 10        1,60€
 Jumber wires  Male to Male                   Τεμ. 2         7.20€
 Jumper Wires 15cm Female to Male             Τεμ. 1         3.60€
 LCD 16X2 I2C                                 Tem. 1         5,90€
 Συνολικό Κόστος ......................................     ...30€
 
 Τα παραπάνω υλικά ήταν χορηγίας από την ONASYS.
 
Φάση 5η
Προμήθεια, εγκατάσταση των υλικών και δικτύωση του ηλεκτρονικού και ηλεκτρικού κυκλώματος.

Solar-Home

Φάση 6η
Στις προηγούμενες φάσης της διδασκαλίας των προγραμμάτων με την γλώσσα C++, μελετήσαμε μια σειρά από προγράμματα με σκοπό να μάθουν οι μαθητές τις βασικές έννοιες του προγραμματισμού και να καταννοήσουν καλύτερα το βασικό πρόγραμμα της κατασκευής που θα παρουσιάσουμε στον διαγωνισμό.

Έτσι λοιπόν προχωράμε στην ολοκλήρωση του προγράμματος με την C++ για να θέσουμε σε λειτουργία το πρωτότυπό μας οικολογικό σπίτι.

Παραθέτουμε παρακάτω το ηλεκτρονικό κύκλωμα στην πλακέτα SensorLab38 και το πλήρες πρόγραμμα για το Solar_Home.

Eco-Home Δεν έχει εισέλθει κανείς στο σπίτι και το φώς (Led) είναι σβηστό.

Eco-Home

Με την είσοδο ενός ή περισοτέρων ατόμων εντός του σπιτιού, ανάβει το φώς και παραμένει αναμένο έως ότου εξέλθουν όλλα τα άτομα. Το LCD μας ενημερώνει για το πόσα άτομα έχουν εισέλθει και πόσα έχουν εξέλθει.

Eco-Home Μόλις εξέλθουν όλα τα άτομα από το σπίτι τό φώς θα σβήσει.

Το τελικό πρόγραμμα λειτουργίας του Solar-Home.

/*  Το πρόγραμμα για Solar_Home διδάχθηκε στις ομάδες εργασίας, στα γραφεία της εταιρείας InflabTech
σε μαθητές δημοτικού και γυμνασίου στα πλαίσια του 5ου Πανελλήνιου Διαγωνισμού Ανοιχτών Τεχνολογιών στην Εκπαίδευση
το ακαδημαϊΚό έτος 2022 - 2023.
Αναρτήθηκε στο GitHub στην διεύθυνση https://github.com/SensorLab38/Sensorlab38-Solar-Home/edit/main/README.md
*/

// Στην αρχή του προγράμματος εισάγουμε τις απαραίτητες βιβλιοθήκες.

#include <LiquidCrystal_PCF8574.h> // Η βιβλιοθήκη LiquidCrystal_PCF8574.h, μας επιτρέπει την επικοινωνία με το LCD.
#include <Wire.h>                  // Η βιβλιοθήκη Wire.h, μας επιτρέπει την I2C επικοινωνίας του Arduino με τις άλλες μονάδες. 

LiquidCrystal_PCF8574 lcd(0x27);   // Θέτουμε το LCD στην διεύθυνση (0X27) ή (0Χ3F) της μνήμης του Arduino.

// Θέτουμε τις μεταβλητές του προγράμματος.                                      

int V0       = A0;                 // Η μεταβλητή V0 διαβάζει και αποθηκεύει την τιμή από το pin (θέση Α0) του Arduino. 
int V1       = A1;                 // Η μεταβλητή V1 διαβάζει και αποθηκεύει την τιμή από το pin (θέση Α1) του Arduino.
int Led_Home = 7;                  // Συνδέουμε το LED της εισόδου του σπιτιού, στο pin (θέση 7) του Arduino.
int IN       = 1;                  // Δίνουμε την αρχική τιμή (1) στη μεταβλιτή ΙΝ (για είδοδο στο σπίτι).
int OUT      = 1;                  // Δίνουμε την αρχική τιμή (1) στη μεταβλιτή OUT(για έξοδο από το σπίτι).


void setup()                       
{                                  // Μετά το άνοιγμα της αγγύλης ξεκινάνε οι αναγκαίες δηλώσεις. 
Wire.begin();                      // Δηλώνουμε ότι ξεκινάει η επικοινωνία του Arduino με το LCD.
Wire.beginTransmission(0x27);      // Δηλώνουμε την διεύθυνση της μνήμης του LCD ότι είναι η (0x27) ή (0Χ3F).      
lcd.begin(16, 2);                  // Δηλώνουμε ότι το LCD που χρησιμοποιούμε, έχει 16 στήλες και 2 σειρές.
pinMode(Led_Home, OUTPUT);         // Δηλώνουμε ότι το pin 7 που είναι συνδεδεμένο το LED είναι έξοδος. 
pinMode(V0,        INPUT);         // Δηλώνουμε το pin Α0 ως είσοδο. Δηλαδή το Arduino διαβάζει την τιμή που δείνει το Pin A0. 
pinMode(V1,        INPUT);         // Δηλώνουμε το pin Α1 ως είσοδο. Δηλαδή το Arduino διαβάζει την τιμή που δείνει το Pin A1.
}                                  // Κλείνουμε την αγγύλη αφού ολοκληρώσαμε τις δηλώσεις. 

void loop()                        
{                                  // Μετά το άνοιγμα της αγγύλη ξεκινάει το κυρίως πρόγραμμα μας.  
V1 = analogRead(A1);               // Η μεταβλιτή V1, διαβάζει την τιμή εισόδου από το Pin A1 του arduino. 
  if (V1<400)                      // Εάν η τιμή που διαβάζει η μεταβλητή από το Pin 1 είναι μικρότερη από 400.
   {                               // Ανοίγουμε αγγύλη και γράφουμε δύο εντολές.
     lcd.print(IN++);              // Δήνουμε αντολή να αυξηθεί η τιμή του (ΙΝ) κατά ένα και να εμφανίζεται στο LCD μας.
     delay(1000);                  // Δήνουμε εντολή να καθυστέρησει για ένα δευτερόλεπτο.
   }                               // Και κλείνουμε την αγγύλη.

   lcd.setBacklight(255);          // Δήνουμε εντολή να ανάψει το LCD.
   lcd.setCursor(0, 1);            // Θέτουμε τον κέρσορα του LCD στην στήλη 0 και στη γραμμή 1.  
   lcd.print("Person OUT  -");     // Δήνουμε εντολή να τυπωθεί στο LCD ότι είναι μεσα στα εισαγωγικά.

V0 = analogRead(A0);               // Η μεταβλιτή V0, διαβάζει την τιμή εισόδου από το Pin A0 του arduino.
  if (V0<400)                      // Εάν η τιμή που μας διαβάζει η βεταβλητή από το pin Α0 είναι μικρότερη από το 400? 
   {                               // Ανοίγουμε την αγγύλη και γράφουμε τρεις εντολές.
     lcd.print(OUT++);             // Αυξάνεται η τιμή του (ΟUT) κατά ένα.
     delay(1000);                  // Δήνουμε εντολή να καθυστέρησει για ένα δευτερόλεπτο.
     digitalWrite(Led_Home, HIGH); // Ανάβει το LED.
   }                               // Και κλείνουμε την αγγύλη.

   lcd.setBacklight(255);          // Δήνουμε εντολή για να ανάψει το LCD.
   lcd.setCursor(0, 0);            // Θέτουμε τον κέρσορα του LCD στην στήλη 0 και στη γραμμή 1.  
   lcd.print("Person IN    ");     // Δήνουμε εντολή να τυπωθεί στο LCD ότι είναι μεσα στα εισαγωγικά.

  if (IN>OUT)                      // Όσο τα άτομα που έχουν εισέλθει (ΙΝ), είναι περισότερα από αυτά έχουν εξέλθει (OUT)?
   {                               // Ανοίγουμε την αγγύλη.
     digitalWrite(Led_Home, HIGH); // Τότε το LED παραμένει συνεχώς αναμένο.
   }                               // Κλείνουμε την αγγύλη.
     else if (IN=OUT)              // Εάν όσα άτομα έχουν εισέλθει στο σπίτι, άλλα τόσα αποχώρησαν? 
     {                             // Ανοίγουμε την αγγύλη.
     digitalWrite(Led_Home, LOW);  // Τότε τα φώτα όλλα τα LED θα σφήσουν.
     }                             // Κλείνουμε την αγγύλη.
 }                                 // Με το κλείσιμο της αγγύλης τερματίζεται και το προγραμμά μας.
 
sorar-Home Πατήστε το εικονίδιο για να δείτε το βίντεο.

Το βίντεο αυτό περιγράφει την λειτουργία του Eco-Home. Το ηλιακό πάνελ στην οροφή συλλέγει την ηλιακή ενέργεια και την μετατρέπει σε ηλεκτρική (συνεχές ρεύμα). Ένας Solar battery charger, σε σύνδεση με το πάνελ, φορτίζει τις μπαταρίες για να παράχουν ηλεκτρική ενέργεια στο σπίτι όταν δεν υπάρχει ηλιοφάνεια. Ο μικροκοντρόλερ Arduino UNO ελέγχει τις εισόδους στους χώρους του σπιτιού και ανάβει ή σβήνει τα φώτα όταν άτομα μπαίνουν ή βγαίνουν από το σπίτι. Για εκπαιδευτικπούς λόγους τοποθετήσαμε LCD Display για να καταγράφουν τα άτομα που εισήλθαν και εξήλθαν σε κάθε χώρο.

Φάση 7η

Ποιοτικός έλεγχος καλής λειτουργίας του πρωτοτύπου, ολοκλήρωση του πρότζεκτ, προετοιμασία για την παρουσίαση του έργου στον 5ο Πανελλήνιο Διαγωνισμό Ρομποτικής ανοικτού κώδικα.

Παραθέτουμε φωτογραφίες από τις εργασίες των ομάδων και βίντεο για την πλήρη λειτουργία του έργου. Η παρουσίαση της λειτουργίας του Solar-Home - Video

Εικόνες από τις εργασίες των μαθητών στο εργαστήριο. Solar-Home 

About
Οι ομάδες μας θα κατασκευάσουν μία μακέτα οικίας, που θα ηλεκτροδοτείται από φωτοβολταϊκό πάνελ όπου ο φωτισμός εντός και εκτός της οικίας θα ρυθμίζεται από αισθητήρες και τον μικροκοντρόλερ Arduino Arduino mega 2560 rev3.
