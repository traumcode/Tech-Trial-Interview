# Pregatire pentru examen.

### (❁´◡`❁) intrebari si raspunsuri.



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



#### Care sunt tipurile de interfete ?

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

   

#### Ce este lambda ?

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



#### Ce este un HashTable ?

**Hash Table** este o extensie a **dictionarului** si implementeaza interfata **Map**. Nu poate sa aiba *null* la cheie precul si la valoare.

Clasa **Hashtable** implementeaza un hash  table care mapeaza cheia la valoare. Pentru a scoate sau a stoca un obiect din hash table, obiectele folosite ca si cheie trebuie sa implementeze metoda **hashCode** si metoda **equals()**.

Deci este o structura de date care poate mapa cheile la valori. Un hash table utilizeaza o functie hash pentru a calcula un index, numitt si hash code, intr-o matrice de *buckets* din care poate fi gasita valoarea dorita.

###### Caracteristici:

- este similar cu **HashMap** dar este sincronizat

- hashtable stocheaza perechi cheie/valoare in hash table

- in hashtable specificam un obiect care este folosit ca si cheie si o valoare care o asociem cheii. Cheia este dupaia hashuita, iar rezultatul, codul hashuit este folosit ca si index unde valoarea este stocata in interiorul tabelei.

  

#### Ce este un HashMap ?

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

3. Desi amandoua implementeaza interfata **Map**, ele extind doua clase diferite. **HashMap** extinde **AbstractMap** class unde **HashTable** extinde clasa **Dictionary**.
4. **HashMap** este parcursa de Iterator in timp ce **Hashtable** este strabatuta de **Enumerator** si **Iterator**
5. **HashMap** este mai rapid decat **HashTable** 



#### Ce este un Thread ?

Threadurile permit unui program sa functioneze mai eficient facand mai multe lucruri in acelasi timp.

Ele pot fi folosite pentru a efectua sarcini complicate in fundal fara a intrerupe programul principal.



#### Diferenta dintre enumerator si iterator.

1. Cu iterator putem citi si sterge un element in timp ce traversam elementele dintr-o colectie in tomp ce cu Enumeration putem doar citi in timp ce traversam elementele.
2. Iterator poate fi folosit cu orice clasa a colectiei in timp ce Enumaration poate fi folosit numai cu clasa mostenita a cadrulu de colectie cum ar fi Vector sau HashTable
3. Iterator are metodele  - hasNext()(**returneaza true daca iteratia are mai multe elemente**), next()(**returneaza urmatorul element**), remove()(**sterge un element din iteratie  **) // Enumaration are metodele - hasMoreElements() (**verifica daca enumeratia contine mai multe elemente**) , nextElement() (**returneaza elementul urmator daca enumaratie contine mai mult de un element**)



#### Ce este un ArrayList ?

Clasa **ArrayList** este un array redimensionabil care poate fi gasit in pachetul java.util

Diferenta dintre un build-in array si un **ArrayList** este ca dimensiunea unui array nu poate fi modificata (daca doriti sa adaugati sau sa eliminati elemente dintr-un array, trebuie sa creati un array nou). In timp ce in **ArrayList** elementele pot fi adaugate si eliminate oricand doriti.

- pentru a adauga elemente se foloseste metoda **add()**

- pentru a accesa un element se foloseste metoda **get()**
- pentru a schimba un element se foloseste metoda **set()**
- pentru a sterge un element se foloseste metoda **remove()** iar pentru a sterge toate elementele , metoda **clear()**
- pentru a verifica marimea listei se foloseste metoda **size()** 
- pentru a sorta un ArrayList se va folosi metoda **sort()**

Clasa **ArrayList** are in ea un array obisnuit. Cand un element este adaugat, acesta este plasat in array. Daca arrayul nu este suficient de mare, se creeaza o matrice noua, mai mare pentru a o inlocui pe cea veche iar cea veche este stearsa.



#### Ce este un LinkedList ?

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



