# Pregatire pentru examen.

### (❁´◡`❁) intrebari si raspunsuri.



# OOP

## JAVA CLASE

### Ce este OOP ?



**OOP** inseamna Object Oriented Programming.

**Programarea procedurala** se refera la scrierea de proceduri sau metode care efectueaza operatii asupra datelor, in timp ce programarea orientata pe obiecte se refera la crearea de obiecte care contin atat date, cat si metode.

**OPP** are mai multe avantaje fata de **programarea procedurala**:

1. **OOP** este mai rapid si mai usor de executat.
2. **OOP** ofera o structura clara pentru programe.
3. **OOP** ajuta la mentinerea codului **Java DRY - Don't Repeat Yourself** so face codul mai usor de intretinut, modificat si debuguit.
4. **OOP** face posibila crearea de aplicatii complet reutilizabile cu mai putin cod si timp de dezvoltare mai scurt.

**Clasele ** si **Obiectele** sunt cele doua mari aspecte ale programarii orientate pe obiect.

Totul in Java este asociat cu **clase** si **obiecte**, impreuna cu metodele si atributele lor. 



### Ce este o clasa ?



O **clasa** este ca o schita utilizata pentru a crea obiecte si pentru a defini tipurie si metodele de date ale obiectelor. O clasa poate contine unul sau mai multi constructori pentru a crea obiecte.



### Ce este un obiect ?



Un obiect este o instantiere a clasei. 

Cand obiectele individuale sunt create, ele mostenesc toate variabilele si metodete din clasa.

Pentru a crea un obiect vom folosi keywordul **new**

Putem crea multiple obiecte a unei singure clase.



#### Atributele unei clase (fields)

Atributele unei clase sunt defapt variabile in cadrul acelei clase.

Puteti accesa un atribut creand un obiect al clasei si utilizand sintaxa punctului **(.)**

```java
public class Main {
  int x = 5;

  public static void main(String[] args) {
    Main myObj = new Main();
    System.out.println(myObj.x);
  }
}
```

Putem modifica valorile atributelor sau sa le suprascriem (**override**).

Daca nu vrem ca un atribut sa fie suprascris declaram atributul ca fiiind **final**

```java
public class Main {
  final int x = 10;

  public static void main(String[] args) {
    Main myObj = new Main();
    myObj.x = 25; // will generate an error: cannot assign a value to a final variable
    System.out.println(myObj.x);
  }
}
```

Keywordul **final** este util atunci cand doriti ca o variabila sa stocheze intotdeauna aceeasi valoare cum ar fi **PI (3.14)**

Keywordul **final** se mai numeste **modifier**.



#### Metodele unei clase

Metodele sunt declarate in cadrul unei clase si sunt utilizate pentru a efectua anumite actiuni

Pentru a apela o metoda, scrieti numele metodei rumata de doua paranteze

**Atributele** si **metodele** sunt fie **statice** fie **publice**



### Access modifiers



Keywordul **public** este un **modificator de acces**, ceea ce inseamna ca este ultilizat pentru a seta **nivelul de acces** pentru **clase**, **atribute**, **metode** si **constructori**

Putem impartii modificatorii in doua grupuri :

1. **Access modifiers** - care controleaza nivelul de acces
2. **Non-Access Modifiers** - adica nu controleaza nivelul de acces, dar ofera alte functionalitati



#### **Pentru *clase*:**

1. **public** - clasa este accesibila pentru orice alta clasa
2. ***default*** - clasa este accesibila de clase in interiorul aceluiasi pachet. 

#### Pentru ***atribute***, *metode* si *constructori*:

1. **public** - codul este accesibil pentru toate clasele
2. **private** - codul este accesibil numai in clasa declarata
3. ***default*** - codul este accesibil in interiorul pachetului.
4. **protected** - codul este accesibil in interiorul pachetului si sub-claselor



### Non-Access Modifiers



#### Pentru *clase*:

1. **final** - clasa nu poate sa fie mostenita de o alta clasa
2. **abastract** - clasa nu poate sa fie folosita ca sa creeze obiecte. (Pentru a accesa o clasa abstracta, ea trebuie sa fie mostenita de la o alta clasa)

#### Pentru *atribute* si *metode*:

1. **final** - atributele si metodele nu pot fi suprascrise sau modificate
2. **static** - atributele si metodele apartin clasei, mai degraba decat obiectului
3. **abstract** - poate fi folosit doar intr-o clasa abstracta si poate fi folosit numai pe metode. Metoda nu va avea un corp.
4. **transient** -  atributele si metodele sunt omise la serializarea obiectului care le contine
5. **synchronized** - metodele pot fi accesate numai de cate un **Thread** la un moment dat
6. **volatile** - valoarea unui atribut nu este memorata in cache la nivel local si este intotdeauna citita din memoria principala



##### Final

Daca nu doriti posibilitatea de a suprascrie valorile atributelor existente, declarati atributele ca fiind **final**

##### Static

O metoda statica inseamna ca poate fi accesata fara a crea un obiect al clasei spre deosebire de **public**

##### **Abstract**

O metoda abstracta apartine unei clase abstracte si nu are un corp. Corpul este furnizat de subclasa.



### Ce este un constructor ?



**Constructorul** este o metoda speciala care este folosita pentru a initializa obiectele. Constructorul este apelat atunci cand este creat un obiect al unei clase. Poate fi folosit pentru a seta valori initiale pentru atributele obiectului.

Numele **constructorului** trebuie sa se potriveasca cu numele clasei si nu poate avea un **return**.

**Constructorul **este apelat atunci cand obiectul este creat.

Toate clasele au constructori implicit. Daca nu creati un constructor de clasa,Java creeaza unul default. Cu toate astea, atunci nu veti putea seta valori initiale pentru atributele obiectului.

```java
// Create a Main class
public class Main {
  int x;  // Create a class attribute

  // Create a class constructor for the Main class
  public Main() {
    x = 5;  // Set the initial value for the class attribute x
  }

  public static void main(String[] args) {
    Main myObj = new Main(); // Create an object of class Main (This will call the constructor)
    System.out.println(myObj.x); // Print the value of x
  }
}

// Outputs 5
```

##### Parametrii constructorului

**Constructorii** pot lua **parametrii**, care sunt utilizati pentru a initializa **atribute**.

Urmatorul exemplu adauga un parametru **int y** la constructor. In interiorul constructorului setam ***x*** la ***y*** . Cand apelam constructorul, trecem un parametru constructorului ***(5)***, care va seta valoarea lui ***x*** la 5.

```java
public class Main {
  int x;

  public Main(int y) {
    x = y;
  }

  public static void main(String[] args) {
    Main myObj = new Main(5);
    System.out.println(myObj.x);
  }
}

// Outputs 5
```



## CELE 4 PRINCIPII OOP

### Encapsularea



Intelesul **Encapsularii** este de a va asigura ca datele '*sensibile*' sunt ascunse utilizatorilor. Pentru a realiza acest lucru trebuie sa:

1. Declarati **variabile / atribute** de clasa ca **privat**
2. Sa furnizati metode **publice** ***GET*** si ***SET*** pentru a accesa si actualiza valoarea unei variabile private.



#### GET & SET

Variabilele private pot fi accesate numai in cadrul aceleiasi clase (o clasa externa nu va avea acces). Cu toate acestea, este posibil sa le accesati daca oferiti metode **public** ***GET*** si ***SET***

Sintaxa pentru ambele este ca incep fie cu **get** sau **set** urmata de numele variabilei, cu prima litera in majuscule.

##### Get

Metoda **Get** returneaza valoarea variabile

##### Set

Metoda **Set** seteaza valoarea si ia un parametru pe care il atribuie variabilei de nume. Cuvantul cheie este utilizat pentru a se referi la obiectul curent.

##### De ce encapsularea?

- un control mai bun al atributelor si metodelor clasei
- atributele clasei pot fi facute doar pentru citire (daca este utilizata doar metoda **get**) sau doar pentru scriere (utilizand metoda **set**)
- flexibilitate: programatorul poate schimba o parte a codului fara a afecta alte parti
- securitate sporita a datelor

### Mostenirea



In java este posibil sa **mostenim** atribute si metode de la o clasa la alta. Conceptul de **mostenire** se poate grupa in doua categorii:

1. **Subclasa(copil)** - clasa care mosteneste de la o alta clasa
2. **Superclasa(parinte)** - clasa care este mostenita

Pentru a mosteni dintr-o clasa, se utilizeaza keywordul ***extends***.

```java
class Vehicle {
  protected String brand = "Ford";        // Vehicle attribute
  public void honk() {                    // Vehicle method
    System.out.println("Tuut, tuut!");
  }
}

class Car extends Vehicle {
  private String modelName = "Mustang";    // Car attribute
  public static void main(String[] args) {

    // Create a myCar object
    Car myCar = new Car();

    // Call the honk() method (from the Vehicle class) on the myCar object
    myCar.honk();

    // Display the value of the brand attribute (from the Vehicle class) and the value of the modelName from the Car class
    System.out.println(myCar.brand + " " + myCar.modelName);
  }
}
```

Observam modificatorul **protected** in clasa *Vehicle* ?  Am setat atributul marcii in *Vehicle* la un modificator de acces **protected**. Daca ar fi setat la **private**, clasa *Car* nu ar fi putut sa o acceseze.

##### De ce si cand sa folosim mostenirea?

- este util pentru reutilizarea codului: reutilizarea atributelor si metodelor unei clase existente atunci cand creati o noua clasa

##### The final Keyword

Daca nu doriti ca alte clase sa mosteneasca de la o clasa, utilizați keywordul **final**

### Polimorfismul



Polimorfismul inseamna "**multe forme**" si apare atunci cand avem multe clase care sunte legate intre ele prin mostenire.

**Mostenirea** ne permite sa mostenim **atribute** si **metode** de la o alta clasa. **Polimorfismul** foloseste acele metode pentru a indeplini diferite sarcini. Acest lucru ne permite sa efectuam o singura acțiune în moduri diferite.

De exemplu: **O superclasa** *Animal* care are o metoda numita **animalSound()**. **Subclasele** de animale ar putea fi *porc,* *pisica*, *caine*, si au de asemenea, propria lor implementare a unui sunet de animal (**animalSound()**), *pisica* miauna, *cainele* latra.

Putem crea obiecte de *porc*, *pisica*, *caine* si putem apela metoda **animalSound()** pentru toate trei.

```java
class Animal {
  public void animalSound() {
    System.out.println("The animal makes a sound");
  }
}

class Pig extends Animal {
  public void animalSound() {
    System.out.println("The pig says: wee wee");
  }
}

class Dog extends Animal {
  public void animalSound() {
    System.out.println("The dog says: bow wow");
  }
}

class Main {
  public static void main(String[] args) {
    Animal myAnimal = new Animal();  // Create a Animal object
    Animal myPig = new Pig();  // Create a Pig object
    Animal myDog = new Dog();  // Create a Dog object
    myAnimal.animalSound();
    myPig.animalSound();
    myDog.animalSound();
  }
}
```

##### De ce si cand sa folosim polimorfismul?

- este util pentru reutilizarea codului: reutilizarea atributelor si metodelor unei clase existente atunci cand creati o noua clasa

### Abstractizarea



**Abstractizarea** datelor este procesul de ascundere a anumitor detalii si de afisare a utilizatorului numai a informatiilor esentiale.

**Abstractizarea** poate fi realizata fie cu **clase abstracte**, fie cu **interfete**.

The keyword **abstract** este un **Non-access Modifier** utilizat pentru **clase** si **metode**.

##### Clasa abstracta

Este o clasa restrictionata care nu poate fi folosita pentru a crea obiecte (pentru a o accesa, trebuie mostenita de la o alta clasa)

##### Metoda abstracta

Poate fi utilizata doar intr-o clasa abstracta si nu are corp. Corpul este asigurat de subclasa. 

O clasa **abstracta** poate avea atat **metode abstracte** cat si **metode regulate**:

```java
abstract class Animal {
  public abstract void animalSound();
  public void sleep() {
    System.out.println("Zzz");
  }
}
```

Din clasa *Animal* nu se va putea crea un obiect.

Pentru a **accesa clasa abstracta** aceasta trebuie mostenita de la o alta clasa. Putem converti clasa *Animal* intr-o clasa **abstracta**:

```java
// Abstract class
abstract class Animal {
  // Abstract method (does not have a body)
  public abstract void animalSound();
  // Regular method
  public void sleep() {
    System.out.println("Zzz");
  }
}

// Subclass (inherit from Animal)
class Pig extends Animal {
  public void animalSound() {
    // The body of animalSound() is provided here
    System.out.println("The pig says: wee wee");
  }
}

class Main {
  public static void main(String[] args) {
    Pig myPig = new Pig(); // Create a Pig object
    myPig.animalSound();
    myPig.sleep();
  }
}
```

##### De ce si cand se utilizeaza clase si metode abstracte ?

- pentru a obtine securitate - ascunde anumite detalii si sa arate doar detaliile importante ale unui obiect.

### Interfata



O alta metoda de a realiza **abstractizarea** este cu ajutorul **interfetelor**.

**O interfata** este o **'clasa abstracta'** complet utilizata pentru a grupa metode conexe cu corpuri goale:

```java
// interface
interface Animal {
  public void animalSound(); // interface method (does not have a body)
  public void run(); // interface method (does not have a body)
}
```

Pentru a accesa **metodele interfetei**, **interfata** trebuie sa fie **implementata** (un fel de mostenire) de o alta clasa cu keywordul ***implements***. Corpul **metodei interfetei** este furnizat de clasa **implement**.

```java
// Interface
interface Animal {
  public void animalSound(); // interface method (does not have a body)
  public void sleep(); // interface method (does not have a body)
}

// Pig "implements" the Animal interface
class Pig implements Animal {
  public void animalSound() {
    // The body of animalSound() is provided here
    System.out.println("The pig says: wee wee");
  }
  public void sleep() {
    // The body of sleep() is provided here
    System.out.println("Zzz");
  }
}

class Main {
  public static void main(String[] args) {
    Pig myPig = new Pig();  // Create a Pig object
    myPig.animalSound();
    myPig.sleep();
  }
}
```

##### Note despre interfata:

- ca si clasele abstracte, **interfetele** nu pot fi folosite pentru a crea obiecte.
- **metodele interfetei** nu au corp, corpul este furnizat de clasa **implement**
- la implementarea unei **interfete**, trebuie sa suprascrieti toate metodele acesteia.
- **metodele interfetei** sunt implicit abstracte si publice
- **atributele interfetei** sunt si ele **publice**, **statice** si **finale**
- **o interfata** nu poate sa contina un **constructor** (deoarece nu poate fi folosita pentru a crea obiecte)

##### De ce si cand se folosesc interfetele ?

- pentru a obtine securitate - ascunde anumite detalii si de a afisa doar detaliile importante ale unui obiect(**interfata**)
- Java nu accepta **mostenire multipla** - o **clasa** poate **mosteni** doar de la o **superclasa**. Cu toate acestea, asta se poate realiza cu **interfetele** deoarece **clasa poate implementa mai multe interfete**.

##### Care sunt tipurile de interfete ?

1. **Normal** - mai mult de o metoda

2. **Cu o singura metoda abstracta** - Dupa nume , evident , are o singura metoda abstracta. Se mai numeste **Interfata Functionala** si putem sa folosim lambda expression care provine dintr-un limbraj de programare numit Scala

   ```java
   public class Main {
   
       public static void main(String[] args) {
           Test test = (int x, int y) -> y * x;
           System.out.println(test.show(234,324));
       }
   }
   ```

   Deci o interfata functionala este orice interfata ce ontine doar o metoda abstracta. Din aceasta cauza putem omite numele metodei atunci cand implementam interfata si putem elimina folosirea claselor anonima. In locul lor  vom avea o expresie lambda. O interfata functionala se poate adnota cu **@FunctionalInterface** 

3. ori de cate ori avem o **Interfata Marke**r - Nu are nici o metoda

### Enums



Un **Enum** este o **clasa speciala** care reprezinta un grup de constante (**variabile neschimbabile**, precum variabilele finale).

Pentru a crea un **Enum** utilizati keywordul **enum** inloc de **clasa**sau **interfata** si separati constantele cu o virgula. Acestea trebuie scrise cu majuscule.

```java
enum Level {
  LOW,
  MEDIUM,
  HIGH
}
```

Puteti accesa constantele din **enum** cu sintaxa punctului **(.)**

```java
Level myVar = Level.MEDIUM;
```

**Enum** vine de la enumerations care inseamna **enumerate in mod specific**.

Puteti avea un **Enum** in interiorul unei clase.

```java
public class Main {
  enum Level {
    LOW,
    MEDIUM,
    HIGH
  }

  public static void main(String[] args) {
    Level myVar = Level.MEDIUM; 
    System.out.println(myVar);
  }
}
```

Puteti avea un **Enum** in interiorul unui **switch** statement:

```java
enum Level {
  LOW,
  MEDIUM,
  HIGH
}

public class Main {
  public static void main(String[] args) {
    Level myVar = Level.MEDIUM;

    switch(myVar) {
      case LOW:
        System.out.println("Low level");
        break;
      case MEDIUM:
         System.out.println("Medium level");
        break;
      case HIGH:
        System.out.println("High level");
        break;
    }
  }
}
```

**Enum type** are o metoda **values()** care returneaza un array cu toate constantele enumerate. Aceasta metoda este utila atunci cand doriti sa parcurgeti constantele unui **Enum** :

```java
for (Level myVar : Level.values()) {
  System.out.println(myVar);
}
```

##### Diferenta dintre Enums si Clase:

O **enumerare** poate, la fel ca o clasa, sa aiba **atribute** si **metode**. Singura diferenta este ca **constantele enumerarii** sunt **publice, statice si finale**

O **enumerare** nu poate fi folosita pentru a crea obiecte si nu poate extinde alte clase (dar poate **implementa interfete**).

##### De ce si cand sa folosim Enums?

Folosim **Enums** cand avem valori despre care stim ca nu se vor schimba niciodata, cum ar fi zilele lunii, culorile, pachetul de carti etc.



### Ce este lambda ?



O functie **lambda** **(functie anonima)** este o functie definita si apelata fara a fi legata de un **identificator**. Ele sunt o forma de functii "incuibate" (**nested**) in sesul ca permit accesul la variabilele din domeniul functiei in care sunt continute. Expresiile lamda ne permit sa cream instante ale claselor cu o singura metoda intr-un mod mult mai compact.

E expresia lamba este un bloc scurt de cod care ia parametrii si returneaza o valoare. Expresiile lambda sunt similare metodelor, dar nu au nevoie de nume si pot fi implementate chiar in corpul unei metode.

Expresiile lambda pot fi stocate in variabile daca tipul variabilei este o interfata care are o singura metoda. Expresia lambda ar trebui sa aiba acelasi numar de parametrii si acelasi tip de returnare ca metoda respectiva. Java are multe dintre aceste tipuri de interfete incorporate, cum ar fi interfata Consumer (care se gaseste in pachetul java.util) utilizata de liste.

O expresie lambda consta:

- dintr-o lista de parametrii formali, separati prin virgula si cuprinsi eventual  intre paranteze rotunde

- sageata directionala

- un body ce consta dintr-o expresie sau un bloc de instructiuni




#### Ce este o functie anonima ?

O functie anonima este o definitie a functiei care nu este legata de un identificator adica nu are nici un nume asociat cu ea. 



#### Ce este boilerplate code ?

Sunt sectiuni de cod care se repeta in mai multe locuri, cu putine sau deloc variatii.

### Ce este un HashTable ?



**Hash Table** este o extensie a **dictionarului** si implementeaza interfata **Map**. Nu poate sa aiba *null* la cheie precul si la valoare.

Clasa **Hashtable** implementeaza un hash  table care mapeaza cheia la valoare. Pentru a scoate sau a stoca un obiect din hash table, obiectele folosite ca si cheie trebuie sa implementeze metoda **hashCode** si metoda **equals()**.

Deci este o structura de date care poate mapa cheile la valori. Un hash table utilizeaza o functie hash pentru a calcula un index, numitt si hash code, intr-o matrice de *buckets* din care poate fi gasita valoarea dorita.



##### Caracteristici:

- este similar cu **HashMap** dar este sincronizat
- hashtable stocheaza perechi cheie/valoare in hash table
- in hashtable specificam un obiect care este folosit ca si cheie si o valoare care o asociem cheii. Cheia este dupaia hashuita, iar rezultatul, codul hashuit este folosit ca si index unde valoarea este stocata in interiorul tabelei.


### Ce este un HashMap ?



Face parte din Java' collection si este gasita in java.util package. Ofera o implementare a interfetei Map. Stocheaza data in perechi cheie - valoare si se pot accesa printr-un index. Un obiect este folosit ca si cheie pentru un alt obiect ca si valoare.

Este un array de *buckets*, neordonat unde fiecare bucker foloseste linked list pentru a pastra elementele.

- nu pastreaza ordinea de inserare a entry-urilor
- capacitatea initiala a unui hashmap este de 16. reprezinta numarul de buckets. este mereu exprimata la puterea a doua
- fiecare nod al linked-list este un obiect al clasei Node<K,V>. Aceasta clasa este o static inner class a clasei HashMap care implementeaza interfata Map.Entry<K,V>

**HashMap** este similar cu **HashTable** dar este nesincronizat. 

Putem face **HashMap** suncronizat apeland **Collections.synchronizedMap(hashMap)**

Spre deosebire de HashTable permite stocarea cheilor nule insa poate avea o singura cheie nula dar multilpe valori nule.

**HashMap** functioneaza pe principiul hashingului. **Hashingul** este o metoda de a atribui un cod unic unei variabile sau obiect dupa ce a fost aplicata o formula sau un algoritm pe propietatile sale. Acest lucru se realizeaza prin intermediul functiei **hashCode()**, mostenita din clasa Obiect care returneaza o valoare de tip integru unica pentru obiect la **runtime**. Desi nu e mandatory , by default valoarea inegrului este derivata din adresa din memorie a obiectului in heap. Adica aceasta functie converteste adresa interna a obiectului intr-un integru. Hash codul obiectului este folosit pentru a determina indexul locatiei obiectului. Daca cheia este nula, nu se mai aplica metodele de hash si equals si va fi stocata automat in indexul 0,

- metoda **put()** este folosita pentru a stoca obiecte entry de tip cheie-valoare. In acest caz, metoda **hashCode()** este chemata pentru a calcula hashcodul cheii, folosit la calcularea indexului bucketului. Formula pentru a calcula indexul locatiei in bucket este ***hashcode(cheie)/ nr de buckets - 1***,
- metoda **get()** este folosita pentru a lua o valoare din hasmap prin intermediul cheii. Este din nou chemata metoda hascode pentru a calcula hascodul si implicit indexul bucketului, iar apoi se cauta prin buckets folosnt metoda **equals()**.



#### Diferente dintre Hashtable si HashMap.

1. **HashTable** a fost de cand **Java** a fost introdus, **HashMap** a fost introdusa in versiune 1.2

2. **HashMap** functioneaza doar cu un singur Thread, **HashTable** functioneaza cu Threaduri multiple

3. Cea mai semnificativa **diferenta** dintre **Hashtable** si **Hashmap** este ca **Hashmap** este nesicronizat in timp ce **Hashtable** este sincronizat. Acest lucru face ca **HashMap** sa fie mai bun pentru apliicatiile non-threaded deoarece obiectele nesincronizate de obicei functioneaza mai bine decat cele sincronizate.

4. **Hashtable** poate contine chei sau valori care sunt non-nule. Pentru a stoca si prelua obiecte dintr-un hastable obiectele folosite ca chei trebuie sa implementeze metoda **HashCode** si metoda equals. Deoarecce *null* nu este un obiect , nu poti apela .**equals**() sau .**hashCode**() deci Hashtable nu poate calcula un hash pentru a-i folosi cheia.

   **HashMap** poate contine o cheie nula si valori nule. Este mai noua si are capabilitati pe avansate , care sunt practic doar o imbunatatire a functionalitatii **HashTable**. Cand **HashMap** a fost creat , a fost conceput special pentru a gestiona valorile nule ca chei si le gestioneaza ca un caz special

5. Desi amandoua implementeaza interfata **Map**, ele extind doua clase diferite. **HashMap** extinde **AbstractMap** class unde **HashTable** extinde clasa **Dictionary**.

6. **HashMap** este parcursa de Iterator in timp ce **Hashtable** este strabatuta de **Enumerator** si **Iterator**

7. **HashMap** este mai rapid decat **HashTable** 



#### Diferenta dintre enumerator si iterator.

1. Cu iterator putem citi si sterge un element in timp ce traversam elementele dintr-o colectie in tomp ce cu Enumeration putem doar citi in timp ce traversam elementele.
2. Iterator poate fi folosit cu orice clasa a colectiei in timp ce Enumaration poate fi folosit numai cu clasa mostenita a cadrulu de colectie cum ar fi Vector sau HashTable
3. Iterator are metodele  - hasNext()(**returneaza true daca iteratia are mai multe elemente**), next()(**returneaza urmatorul element**), remove()(**sterge un element din iteratie  **) // Enumaration are metodele - hasMoreElements() (**verifica daca enumeratia contine mai multe elemente**) , nextElement() (**returneaza elementul urmator daca enumaratie contine mai mult de un element**)



#### Ce este hashingul ?

Hashing este procesul de schimbare a unui text simplu sau a unei chei într-o valoare **hash** prin aplicarea unei **funcții hash**. De obicei, lungimea de intrare este mai mare ca dimensiune decât valoarea hash de ieșire. **Hashing** este un proces de criptare unidirecțional, astfel încât o valoare hash nu poate fi inversată pentru a ajunge la textul simplu original. **Hashingul** este utilizat în criptare pentru a securiza informațiile partajate între două părți. Parolele sunt transformate în valori hash, astfel încât, chiar dacă apare o încălcare a securității, codurile PIN rămân protejate. 

###### Cum functioneaza hashingul ?

Doua chei diferite pot produce o valoare **hash** identica, ceea ce duce la o coliziune. Pentru ca hashingul sa functioneze eficient, ar trebui sa modificati algoritmul de hashing, astfel incat sa existe sanse minime de coliziune. Algoritmii de hash produc apoi valori hash diferite pentru cheile alternative. Unele caracteristici cheie ale hashului includ:

1. Un sir de intrare ar trebuie sa aibe o valoare hash speicifica **Hashinug-ul** ar trebui sa fie ireversibil.
2. O functie hash trebuie sa fie rapida
3. O usoara modificare a intrarii ar trebui sa produca un hash diferit

###### Algoritmi hashing:

1. Message Digest(MD5)
2. SHA - Secure Hashing Algorithm
3. RIPMEND

###### Scopul Hashingului:

Hashing-ul este necesar în momentul comparării unei cantități uriașe de date. Puteți crea diferite valori hash pentru date diferite. Puteți compara și hashurile.

- Este usor sa pastrati si sa gasiti inregistrari ale datelor hashing.
- Puteti utiliza hashing in aplicatii criptografica, cum ar fi o sematura digitala.
- 

#### Care este diferenta dintre encriptare si hashing ?

Deoarece criptarea este bidirectionala, datele pot fi decriptate, astfel incat sa poata fi citite din nou. Hashing, pe de alta parte, este unidirectional, ceea ce inseamna ca textul simplu este amestecat intr-un rezumat unic, prin utilizarea unei sari care nu poate fi decriptata.

### Ce este un ArrayList ?



Clasa **ArrayList** este un array redimensionabil care poate fi gasit in pachetul java.util

Diferenta dintre un build-in array si un **ArrayList** este ca dimensiunea unui array nu poate fi modificata (daca doriti sa adaugati sau sa eliminati elemente dintr-un array, trebuie sa creati un array nou). In timp ce in **ArrayList** elementele pot fi adaugate si eliminate oricand doriti.

- pentru a adauga elemente se foloseste metoda **add()**

- pentru a accesa un element se foloseste metoda **get()**
- pentru a schimba un element se foloseste metoda **set()**
- pentru a sterge un element se foloseste metoda **remove()** iar pentru a sterge toate elementele , metoda **clear()**
- pentru a verifica marimea listei se foloseste metoda **size()** 
- pentru a sorta un ArrayList se va folosi metoda **sort()**

Clasa **ArrayList** are in ea un array obisnuit. Cand un element este adaugat, acesta este plasat in array. Daca arrayul nu este suficient de mare, se creeaza o matrice noua, mai mare pentru a o inlocui pe cea veche iar cea veche este stearsa.

### Ce este un LinkedList ?



Clasa LinkedList este o colectie care poate contine multe obiecte de acelasi tip, la fel ca **ArrayList**

Are aceleasi metode ca si clasa **ArrayList** deparece ambele implementeaza interfata **List**, asta inseamna ca puteti adauga, schimba, sterge elemente in acelasi fel.

**LinkedList** in schimb stocheaza elementele in niste '*containere*' . Lista are un link catre primul *container* iar fiecare *container* are un link catre urmatorul *container* din lista. Pentru a adauga un element in lista, elementul este plasat intr-un nou container si acel container este legat de unul dintre celelalte containere din lista

#### Cand le folosim?

Folosim **ArrayList **pentru a stoca si a accesa informatie, iar **LinkedList** pentru a manipula informatia.

In multe cazuri **ArrayList** este mai eficient deoarece de cele mai multe ori este nevoie sa aveti access la elementele aleatorii din lista, dar **LinkedList** ofera mai multe metode pentru a face anumite operatii mai eficient:

- **addFirst()** - adauga un element la inceputul listei
- **addLast()** - adauga un element la sfarsitul listei
- **removeFirst()** - sterge primul element din lista
- **removeLast()** - sterge ultimul element din lista
- **getFirst()** - acceseaza primul element din lista
- **getLast()** - acceseaza ultimul element din lista

### Compile time si Runtime



#### Diferenta dintre Compile Time si Runtime

Compile Time si Runtime sunt doua faze ale ciclului de viata al programarii.  

**Compile time** este faza ciclului de viata de programare care converteste codul sursa intr-un fisier executabil.

Programul scris sau codul sursa trebuie convertit in format inteligibil de masina. Perioada de timp pentru a converti codul sursa in codul masinii este Compile Time. Sarcina precum analiza sintaxei, analiza semantica si generarea de cod au loc la momentul compilarii.

Deci Codul sursa scris de utilizator trebuie sa fie compilat in codul masinii, sa fie inteles de calculator pentru a putea fi un program executabil. 

Erorile din **Compile time** sunt erori de sintaxa.

**Runtime** este timpul in care ruleaza un program, spre deosebire de alte faze ale ciclului de viata ale programului cum ar fi timpul de compilare , timpul de conectare sau timpul de incarcare.

Mai este numit si timp de executie.

Deci **Runtime** estei perioada de timp pentru a rula fisierul executabl generat in **Compile Time** 

Erorile din **Runtime** sunt cunoscute ca exceptii.

### Exceptii



La executarea codului Java, pot aparea diferite erori: erori de codare, erori datorate unui input gresit sau alte lucruri neprevazute. 

Cand apare o eroare Java se va opri in mod normal si va genera un mesaj de eroare. Termenul tehnic pentru aceasta este: **Java va arunca o exceptie. (Java will throw an error)**



#### Try si Catch

**Try** va permite sa definiti un bloc de cod care sa fie testat petru erori in timp ce acesta este executat

**Catch** va permite sa definiti un bloc de cod care urmeaza sa fie executat, daca apare o eroare in blocul **Try**

**Try** si **Catch** vin intotdeauna in perechi:

```java
try {
  //  Block of code to try
}
catch(Exception e) {
  //  Block of code to handle errors
}
```

Exemplu:

Aceasta va genera o eroare deoarece **myNumber[10]** nu exista

```java
public class Main {
  public static void main(String[ ] args) {
    int[] myNumbers = {1, 2, 3};
    System.out.println(myNumbers[10]); // error!
  }
}
```

**Outputul** va fi:

```java
Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException: 10
    at Main.main(Main.java:4)
```

Daca apare o eroare, putem folosi **Try**...**Catch** pentru a prinde eroarea si a executa un cod pentru a o gestiona:

```java
public class Main {
  public static void main(String[ ] args) {
    try {
      int[] myNumbers = {1, 2, 3};
      System.out.println(myNumbers[10]);
    } catch (Exception e) {
      System.out.println("Something went wrong.");
    }
  }
}
```

**Outputul** va fi:

"Something went wrong"



#### Finally

Declaratia **finally** va permite sa executati codul, dupa **try** si **catch** indiferent de rezultat.

```java
public class Main {
  public static void main(String[] args) {
    try {
      int[] myNumbers = {1, 2, 3};
      System.out.println(myNumbers[10]);
    } catch (Exception e) {
      System.out.println("Something went wrong.");
    } finally {
      System.out.println("The 'try catch' is finished.");
    }
  }
}
```

**Outputul** va fi:

"Something went wrong.
The 'try catch' is finished."



#### Throw keyword

Keywordul **throw** va permite sa creati o eroare personalizata.

Este utilizata impreuna cu un **tip de exceptie**. Exista multe tipuri de exceptii disponibile in Java: **ArithmeticException**, **FileNotFoundException**, **ArrayIndexOutOfBoundsException** etc.

```java
public class Main {
  static void checkAge(int age) {
    if (age < 18) {
      throw new ArithmeticException("Access denied - You must be at least 18 years old.");
    }
    else {
      System.out.println("Access granted - You are old enough!");
    }
  }

  public static void main(String[] args) {
    checkAge(15); // Set age to 15 (which is below 18...)
  }
}
```

**Outputul** va fi:

"Exception in thread "main" java.lang.ArithmeticException: Access denied - You must be at least 18 years old.
    at Main.checkAge(Main.java:4)
    at Main.main(Main.java:12)"

Daca varsta era 20, atunci nu va fi nici o exceptie:

```java
checkAge(20);
```

**Outputul** va fi:

"Access granted - You are old enough!"



#### Unchecked exceptions

Sunt exceptiile care tin de logica

##### Lista exceptiilor unchecked:

⦁	ArithmeticException.
⦁	ClassCastException.
⦁	NullPointerException.
⦁	ArrayIndexOutOfBoundsException.
⦁	NegativeArraySizeException.
⦁	ArrayStoreException.
⦁	IllegalThreadStateException.
⦁	SecurityException, etc.

Acele exceptii care nu sunt verificate in timpul compilarii si tin de logica programatorului. Bad programming.

### Clasele Wrapper



Clasele **wrapper** ofera o modalitate de a utiliza tipuri de date primitive (**int**,**boolean**,etc) ca si obiecte.

Tabelul de mai jos prezinta tipul primitiv si clasa **wrapper** echivalenta:

| Primitive Data Type | Wrapper Class |
| :------------------ | :------------ |
| byte                | Byte          |
| short               | Short         |
| int                 | Integer       |
| long                | Long          |
| float               | Float         |
| double              | Double        |
| boolean             | Boolean       |
| char                | Character     |

Uneori trebuie sa utilizam clase **wrapper**, de exemplu atunci cand lucram cu obiecte **Collection**, cum ar fi **ArrayList**, unde tipurile primitive nu pot fi utilizate(deoarece lista poate stoca doar obiecte):

```java
ArrayList<int> myNumbers = new ArrayList<int>(); // Invalid
ArrayList<Integer> myNumbers = new ArrayList<Integer>(); // Valid
```

##### Crearea obiectelor wrapper

Pentru a crea un obiect wrapper, utilizați clasa wrapper în loc de tipul primitiv. Pentru a obține valoarea, puteți imprima obiectul

```java
public class Main {
  public static void main(String[] args) {
    Integer myInt = 5;
    Double myDouble = 5.99;
    Character myChar = 'A';
    System.out.println(myInt);
    System.out.println(myDouble);
    System.out.println(myChar);
  }
}
```

Întrucât acum lucrați cu obiecte, puteti utiliza anumite metode pentru a obtine informatii despre obiectul specific.

De exemplu, urmatoarele metode sunt utilizate pentru a obtine valoarea asociata cu obiectul **wrapper** corespunzator:

**`intValue()`,   `byteValue()`,  `shortValue()`,  `longValue()`,  `floatValue()`,  `doubleValue()`,  `charValue()`, `booleanValue()`.**

```java
public class Main {
  public static void main(String[] args) {
    Integer myInt = 5;
    Double myDouble = 5.99;
    Character myChar = 'A';
    System.out.println(myInt.intValue());
    System.out.println(myDouble.doubleValue());
    System.out.println(myChar.charValue());
  }
}
```

O alta metoda utila este metoda **toString()**, care este folosita pentru a converti obiectele **wrapper** in siruri.

```java
public class Main {
  public static void main(String[] args) {
    Integer myInt = 100;
    String myString = myInt.toString();
    System.out.println(myString.length());
  }
}
```

### Ce este un Thread?



**Threadurile** permit unui program sa funcționeze mai eficient făcând mai multe lucruri în același timp.

Ele pot fi folosite pentru a efectua sarcini complicate în fundal fără a întrerupe programul principal.



##### Crearea unui Thread

Exista doua moduri de a crea un **Thread**:

1. Poate fi creat prin extinderea clasei **Thread** si suprascriind metoda **run()**a acesteia:

```java
public class Main extends Thread {
  public void run() {
    System.out.println("This code is running in a thread");
  }
}
```

2. O alta metoda de a crea un **Thread** este de a implementa interfata **Runnable**:

```java
public class Main implements Runnable {
  public void run() {
    System.out.println("This code is running in a thread");
  }
}
```



##### Running Threads

Daca clasa extinde clasa **Thread**, threadul poate fi rulat prin crearea unei instante a clasei si apelarea metodei sale **start()**:

```java
public class Main extends Thread {
  public static void main(String[] args) {
    Main thread = new Main();
    thread.start();
    System.out.println("This code is outside of the thread");
  }
  public void run() {
    System.out.println("This code is running in a thread");
  }
}
```

Daca clasa implementeaza interfata **Runnable**, threadul de executie poate fi rulat prin trecerea unei isntante a clasei la constructorul unui obiect **Thread** si apoi apeland metoda **start()** a threadului de executie:

```java
public class Main implements Runnable {
  public static void main(String[] args) {
    Main obj = new Main();
    Thread thread = new Thread(obj);
    thread.start();
    System.out.println("This code is outside of the thread");
  }
  public void run() {
    System.out.println("This code is running in a thread");
  }
}
```



##### Diferente intre "extinderea" si "implementarea" threadurilor

Diferenta majora este ca atunci cand o clasa extinde clasa **Thread**, nu puteti extinde nicio alta clasa, dar prin implementarea interfetei **Runnable** este posibil sa se extinda si de la alta clasa, cum ar fi: clasa **MyClass** extinde **OtherClass** implementeaza **Runnable**.



##### Probleme de concurenta

Deoarece **threadurile** ruleaza in acelasi timp cu alte parti ale programului, nu exista nicio modalitate de a sti in ce ordine va rula codul. Cand **threadurile** si programul principal citesc si scriu aceleasi variabile, valorile sunt imprevizibile. Problemele care rezulta din aceasta se numeste **probleme de concurenta**.

```java
public class Main extends Thread {
  public static int amount = 0;

  public static void main(String[] args) {
    Main thread = new Main();
    thread.start();
    System.out.println(amount);
    amount++;
    System.out.println(amount);
  }

  public void run() {
    amount++;
  }
}
```

Pentru a evita problemele de concurenta, este mai bine sa partajati cat mai putine atribute in **threaduri**. Daca atributele trebuie partajate, o solutie posibila este sa folositi metoda **isAlive()** a threadului de executie pentru a verifica daca firul de executie s-a terminat de rulat inainte de a utiliza orice atribute pe care threadul de executie le poate modifica.



## Principiile SOLID

### Ce sunt principiile SOLID ?



Principiile SOLID sunt cinci principii ale designului clasei orientate pe obiect. Acestea sunt un set de reguli si cele mai bune practici de urmat in timp ce proiectati o structura de clasa.

Aceste cinci principii ne ajută să înțelegem necesitatea anumitor modele de proiectare și arhitectură software în general. Deci, cred că este un subiect pe care fiecare dezvoltator ar trebui să îl învețe.

### Cele 5 concepte care formeaza SOLID

#### 

1. **S**ingle responsability
2. **O**pen/Closed
3. **L**iskov Substitustion
4. **I**nterface Segregation
5. **D**ependency Inversion



#### Single Responsability

Acest principiu afirma ca o clasa ar trebui sa aiba o singura responsabilitate. In plus, ar trebui sa aiba un singur motiv pentru a se schimba. 

###### Beneficii:

- Testare - o clasa cu o singura responsabilitate va avea mult mai putine cazuri de testare
- Cuplare mai mica - mai putine functionalitati intr-o singura clasa vor avea mai putine dependente
- Organizare - cursurile mai mici si bine organizate sunt mai usor de cautat decat cele monolitice

#### Open for Extension, Closed for Modification

Clasele ar trebui sa fie deschise pentru extensie, dar inchise pentru modificare.

Modificarea înseamnă modificarea codului unei clase existente, iar extensia înseamnă adăugarea de noi funcționalități.

Deci, ceea ce vrea să spună acest principiu este: ar trebui să putem adăuga noi funcționalități fără a atinge codul existent pentru clasă. Acest lucru se datorează faptului că ori de câte ori modificăm codul existent, ne asumăm riscul de a crea bug-uri potențiale. Deci, ar trebui să evităm să atingem codul de producție testat și fiabil (în cea mai mare parte), dacă este posibil.

Dar cum vom adăuga noi funcționalități fără a atinge clasa, vă puteți întreba. De obicei se face cu ajutorul interfețelor și a claselor abstracte.

Acum, că am acoperit elementele de bază ale principiului, să-l aplicăm în aplicația noastră Factură.

Să presupunem că șeful nostru a venit la noi și a spus că vrea ca facturile să fie salvate într-o bază de date, astfel încât să le putem căuta cu ușurință. Credem că în regulă, acesta este șeful ușor, dă-mi doar o secundă!

Creăm baza de date, ne conectăm la ea și adăugăm o metodă de salvare la clasa noastră InvoicePersistence:

```java
public class InvoicePersistence {
    Invoice invoice;

    public InvoicePersistence(Invoice invoice) {
        this.invoice = invoice;
    }

    public void saveToFile(String filename) {
        // Creates a file with given name and writes the invoice
    }

    public void saveToDatabase() {
        // Saves the invoice to database
    }
}
```

Din păcate, noi, în calitate de dezvoltator leneș al magazinului de cărți, nu am proiectat clasele pentru a fi ușor de extins în viitor. Deci, pentru a adăuga această caracteristică, am modificat clasa InvoicePersistence.

Dacă proiectul nostru de clasă ar respecta principiul Deschis-Închis, nu ar fi nevoie să schimbăm această clasă.

Deci, în calitate de dezvoltator leneș, dar inteligent pentru magazinul de cărți, vedem problema de design și decidem să refactorăm codul pentru a ne supune principiului.

```java
interface InvoicePersistence {

    public void save(Invoice invoice);
}
```

Schimbăm tipul InvoicePersistence la Interface și adăugăm o metodă de salvare. Fiecare clasă de persistență va implementa această metodă de salvare.

```java
public class DatabasePersistence implements InvoicePersistence {

    @Override
    public void save(Invoice invoice) {
        // Save to DB
    }
}
```

```java
public class FilePersistence implements InvoicePersistence {

    @Override
    public void save(Invoice invoice) {
        // Save to file
    }
}
```

![img](https://erinc.io/wp-content/uploads/2020/08/SOLID-Tutorial-1-1024x554.jpeg)Acum logica noastră de persistență este ușor de extins. Dacă șeful nostru ne cere să adăugăm o altă bază de date și să avem 2 tipuri diferite de baze de date precum MySQL și MongoDB, putem face asta cu ușurință.

S-ar putea să credeți că am putea crea mai multe clase fără o interfață și le putem adăuga o metodă de salvare la toate.

Dar să presupunem că extindem aplicația noastră și avem mai multe clase de persistență precum InvoicePersistence, BookPersistence și creăm o clasă PersistenceManager care gestionează toate clasele de persistență:

```java
public class PersistenceManager {
    InvoicePersistence invoicePersistence;
    BookPersistence bookPersistence;
    
    public PersistenceManager(InvoicePersistence invoicePersistence,
                              BookPersistence bookPersistence) {
        this.invoicePersistence = invoicePersistence;
        this.bookPersistence = bookPersistence;
    }
}
```

Acum putem trece orice clasă care implementează interfața InvoicePersistence la această clasă cu ajutorul polimorfismului. Aceasta este flexibilitatea pe care o oferă interfețele.

#### Liskov Substitution

Principiul de substituție Liskov afirmă că subclasele ar trebui să fie înlocuibile pentru clasele lor de bază.

Aceasta înseamnă că, având în vedere că clasa B este o subclasă a clasei A, ar trebui să putem transmite un obiect din clasa B oricărei metode care așteaptă un obiect din clasa A, iar metoda nu ar trebui să ofere nicio ieșire ciudată în acest caz.

Acesta este comportamentul așteptat, deoarece atunci când folosim moștenirea presupunem că clasa copil moștenește tot ce are superclasa. Clasa de copii extinde comportamentul, dar nu îl restrânge niciodată.

Prin urmare, atunci când o clasă nu se supune acestui principiu, duce la niște bug-uri urâte care sunt greu de detectat.

Principiul lui Liskov este ușor de înțeles, dar greu de detectat în cod. Așadar, să ne uităm la un exemplu.

```java
class Rectangle {
	protected int width, height;

	public Rectangle() {
	}

	public Rectangle(int width, int height) {
		this.width = width;
		this.height = height;
	}

	public int getWidth() {
		return width;
	}

	public void setWidth(int width) {
		this.width = width;
	}

	public int getHeight() {
		return height;
	}

	public void setHeight(int height) {
		this.height = height;
	}

	public int getArea() {
		return width * height;
	}
}
```

Avem o clasă simplă Rectangle și o funcție getArea care returnează aria dreptunghiului.

Acum decidem să creăm o altă clasă pentru Squares. După cum știți, un pătrat este doar un tip special de dreptunghi, în care lățimea este egală cu înălțimea.

```java
class Square extends Rectangle {
	public Square() {}

	public Square(int size) {
		width = height = size;
	}

	@Override
	public void setWidth(int width) {
		super.setWidth(width);
		super.setHeight(width);
	}

	@Override
	public void setHeight(int height) {
		super.setHeight(height);
		super.setWidth(height);
	}
}
```

Clasa noastră Square extinde clasa dreptunghiului. Setăm înălțimea și lățimea la aceeași valoare în constructor, dar nu dorim ca niciun client (cineva care folosește clasa noastră în codul său) să schimbe înălțimea sau greutatea într-un mod care poate încălca proprietatea pătrat.

Prin urmare, înlocuim seterii pentru a seta ambele proprietăți ori de câte ori una dintre ele este modificată. Dar, făcând asta, tocmai am încălcat principiul substituției Liskov.

Să creăm o clasă principală pentru a efectua teste pe funcția getArea.

```java
class Test {

   static void getAreaTest(Rectangle r) {
      int width = r.getWidth();
      r.setHeight(10);
      System.out.println("Expected area of " + (width * 10) + ", got " + r.getArea());
   }

   public static void main(String[] args) {
      Rectangle rc = new Rectangle(2, 3);
      getAreaTest(rc);

      Rectangle sq = new Square();
      sq.setWidth(5);
      getAreaTest(sq);
   }
}
```

Testerul echipei tale tocmai a venit cu funcția de testare getAreaTest și îți spune că funcția ta getArea nu reușește să treacă testul pentru obiectele pătrate.

În primul test, creăm un dreptunghi în care lățimea este 2 și înălțimea este 3 și apelăm getAreaTest. Ieșirea este de 20 așa cum era de așteptat, dar lucrurile merg prost când trecem în pătrat. Acest lucru se datorează faptului că apelul la funcția setHeight din test setează lățimea și duce la o ieșire neașteptată.

#### Interface Segregation Principle

Segregarea înseamnă păstrarea lucrurilor separate, iar principiul de separare a interfeței este despre separarea interfețelor.

Principiul afirmă că multe interfețe specifice clientului sunt mai bune decât o interfață de uz general. Clienții nu ar trebui să fie forțați să implementeze o funcție de care nu au nevoie.

Acesta este un principiu simplu de înțeles și aplicat, așa că haideți să vedem un exemplu.

```java
public interface ParkingLot {

	void parkCar();	// Decrease empty spot count by 1
	void unparkCar(); // Increase empty spots by 1
	void getCapacity();	// Returns car capacity
	double calculateFee(Car car); // Returns the price based on number of hours
	void doPayment(Car car);
}

class Car {

}
```

Am modelat o parcare foarte simplificată. Este tipul de parcare în care plătiți o taxă orară. Acum luați în considerare că vrem să implementăm o parcare gratuită.

```java
public class FreeParking implements ParkingLot {

	@Override
	public void parkCar() {
		
	}

	@Override
	public void unparkCar() {

	}

	@Override
	public void getCapacity() {

	}

	@Override
	public double calculateFee(Car car) {
		return 0;
	}

	@Override
	public void doPayment(Car car) {
		throw new Exception("Parking lot is free");
	}
}
```

Interfața noastră de parcare a fost compusă din 2 lucruri: logică legată de parcare (parcare mașină, unpark auto, obține capacitate) și logică legată de plată.

Dar este prea specific. Din acest motiv, clasa noastră FreeParking a fost forțată să implementeze metode legate de plată care sunt irelevante. Să separăm sau să separăm interfețele.

![img](https://erinc.io/wp-content/uploads/2020/08/SOLID-Tutorial-1024x432.png)

Acum am separat parcarea. Cu acest nou model, putem chiar să mergem mai departe și să împărțim PaidParkingLot pentru a accepta diferite tipuri de plată.

Acum modelul nostru este mult mai flexibil, extensibil, iar clienții nu trebuie să implementeze nicio logică irelevantă deoarece oferim doar funcționalități legate de parcare în interfața parcării.

#### Dependency Inversion Principle

Principiul inversării dependenței afirmă că clasele noastre ar trebui să depindă de interfețe sau clase abstracte în loc de clase și funcții concrete.

În articolul său (2000), unchiul Bob rezumă acest principiu după cum urmează:

„Dacă OCP afirmă scopul arhitecturii OO, DIP stabilește mecanismul principal”.
Aceste două principii sunt într-adevăr legate și am aplicat acest model înainte în timp ce discutam despre Principiul Deschis-Închis.

Dorim ca clasele noastre să fie deschise la extensie, așa că ne-am reorganizat dependențele pentru a depinde de interfețe în loc de clase concrete. Clasa noastră PersistenceManager depinde de InvoicePersistence în loc de clasele care implementează acea interfață.



# Advanced/Spring/Web

### Ce este Spring ?



**Spring** este un framework open source care asigura mediul si simplificarea scrierii aplicatiilor in limbajul Java.

### Ce este Spring Boot?



**Spring Boot** este un framework ce ofera un suport vast pentru crearea unei infrastruccturi de dezvoltare a aplicatiilor Java. **Spring Boot** structureaza programul si legaturile intre entitati, usurand lucrul programatorului. **Spring Boot** ofera o platforma buna pentru dezvoltatorii Java pentru a dezvolta o aplicatie **Spring** autonoma si de productie pe care o putem rula.



##### Ce aplicatii are Java Spring Boot ?

**Spring** **Boot**  este folosit la crearea microserviciilor(arhitectura care permite dezvoltatorilor sa creeze servicii independent, fiecare serviciu avand procesul lui).

###### Cele mai importante aplicatii sunt:

- Aplicatii web sigure
- Backend pentru aplicatii mobile
- Furnzior API
- Software pentru intreprinderi



##### Avantaje:

- Usor de inteles si de dezvoltat aplicatii **Spring**
- Creste productivitatea 
- Reduce timpul de dezvoltare

Ne permite accelerarea crearii unei aplicatii web. Acesta analizand confugurarile setate de catre programator si injecteaza toate dependintele necesare pentru satisfacerea cerintelor acestuia.

Avantajele de baza **Spring Boot** sunt autoconfigurarea, independenta su autonomia acestuia de a lua decizii pentru a face o aplicatie cat mai optimizata. **Spring Boot** este independent si ofera posibilitatea de a integra toate serviciile automat. De exemplu, nu are nevoie de un server container aparte in care sa fie plasata aplicația, acesta oferind unul implicit, rulându-l la startul aplicației.



##### De ce Spring Boot ?

Alegem **Spring Boot** datorita caracteristicilor si beneficiilor pe care le ofera:

- Ofera o modalitate flexibila de a configura Java Beans, configuratii XML si tranzactii cu baze de date.
- Ofera o procesara puternica  si gestioneaza endpointurile REST
- In **Spring Boot** totul este configurat automat , nu sunt necesare configurari manuale
- Ofera aplicatii **Spring** bazate pe adnotari
- Include Embedded Servlet Container , adică Container Servlet incorporat
