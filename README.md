# Pregatire pentru examen.

### (❁´◡`❁) intrebari si raspunsuri.





#### Ce este o clasa ?

O **clasa** este ca o schita utilizata pentru a crea obiecte si pentru a defini tipurie si metodele de date ale obiectelor. O clasa poate contine unul sau mai multi constructori pentru a crea obiecte.



#### Ce este un constructor ?

**Constructorul** este *singura* modalitate pentru a crea instantele clasei. El este o metoda speciala care ajuta in crearea obiectelor. De fiecare data cand un obiect este creat este apelat de catre constructor, deci in java cel putin fiecare clasa are cel putin un constructor.



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



#### Diferente dintre Hashtable si HashMap.

1. Cea mai semnificativa **diferenta** dintre **Hashtable** si **Hashmap** este ca **Hashmap** este nesicronizat in timp ce **Hashtable** este sincronizat. Acest lucru face ca **HashMap** sa fie mai bun pentru apliicatiile non-threaded deoarece obiectele nesincronizate de obicei functioneaza mai bine decat cele sincronizate.

2. **Hashtable** poate contine chei sau valori care sunt non-nule. Pentru a stoca si prelua obiecte dintr-un hastable obiectele folosite ca chei trebuie sa implementeze metoda **HashCode** si metoda equals. Deoarecce *null* nu este un obiect , nu poti apela .**equals**() sau .**hashCode**() deci Hashtable nu poate calcula un hash pentru a-i folosi cheia.

   **HashMap** poate contine o cheie nula si valori nule. Este mai noua si are capabilitati pe avansate , care sunt practic doar o imbunatatire a functionalitatii **HashTable**. Cand **HashMap** a fost creat , a fost conceput special pentru a gestiona valorile nule ca chei si le gestioneaza ca un caz special

3. Desi amandoua implementeaza interfata **Map**, ele extind doua clase diferite. **HashMap** extinde **AbstractMap** class unde **HashTable** extinde clasa **Dictionary**.
4. **HashMap** este parcursa de Iterator in timp ce **Hashtable** este strabatuta de **Enumerator** si **Iterator**





#### Diferenta dintre enumerator si iterator.

1. Cu iterator putem citi si sterge un element in timp ce traversam elementele dintr-o colectie in tomp ce cu Enumeration putem doar citi in timp ce traversam elementele.
2. Iterator poate fi folosit cu orice clasa a colectiei in timp ce Enumaration poate fi folosit numai cu clasa mostenita a cadrulu de colectie cum ar fi Vector sau HashTable
3. Iterator are metodele  - hasNext()(**returneaza true daca iteratia are mai multe elemente**), next()(**returneaza urmatorul element**), remove()(**sterge un element din iteratie  **) // Enumaration are metodele - hasMoreElements() (**verifica daca enumeratia contine mai multe elemente**) , nextElement() (**returneaza elementul urmator daca enumaratie contine mai mult de un element**)



#### Ce inseamna a fi sincronizat ? 









