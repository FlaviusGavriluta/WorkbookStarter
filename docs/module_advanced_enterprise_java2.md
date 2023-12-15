# Enterprise module (Java branch)

### Java Enterprise and Spring

#### What are the possible uses of reflection?

Reflecția în Java permite programelor să inspecteze și să manipuleze structura claselor, metodelor și câmpurilor în
timpul rulării. Utilizările posibile includ crearea de instanțe, invocarea metodelor, accesarea și modificarea
câmpurilor private și multe altele. Reflecția este frecvent utilizată în dezvoltarea de framework-uri și instrumente
pentru generarea de cod.

#### What is Spring?

Spring este un framework de dezvoltare pentru Java care facilitează dezvoltarea, testarea și gestionarea
aplicațiilor Java prin furnizarea de funcționalități precum controlul inversiunii, injecția de dependințe, gestionarea
tranzacțiilor și multe altele.

#### What is Spring Boot?

Spring Boot este o extensie a cadrelor Spring care simplifică dezvoltarea aplicațiilor Java. Acesta oferă configurare
implicită astfel încât dezvoltatorii să poată crea rapid aplicații Java independente de platformă, cu puțin
efort de configurare.

#### What is the major difference between the Standard edition (JSE) and Enterprise edition (JEE)? You can choose Spring (Spring Boot) instead of JavaEE. Focus on comparing them.

Principala diferență constă în scopul și dimensiunea aplicațiilor. JSE (Java Standard Edition) se concentrează pe
dezvoltarea de aplicații desktop și aplicații cu cerințe mai mici, în timp ce JEE (Java Enterprise Edition) este
conceput pentru dezvoltarea de aplicații de afaceri și sisteme de nivel enterprise, cu cerințe de scalabilitate,
securitate și gestionare mai ridicate. Spring (Spring Boot) aduce o abordare mai ușoară și mai modulară pentru
dezvoltarea de aplicații de afaceri în comparație cu JavaEE.

#### What are the advantages of the Spring Framework? Focus on the Core part.

- Controlul inversiunii (IoC) pentru gestionarea dependențelor.
- Injecția de dependențe pentru o dezvoltare ușoară și modulară.
- AOP (Aspect-Oriented Programming) pentru gestionarea aspectelor transversale ale aplicației.
- Abordare modulară și ușor de testat a componentelor.

#### What is a servlet? What is the purpose of DispatcherServlet in Spring?

Un servlet este o componentă Java utilizată pentru a gestiona cereri și a genera răspunsuri pe partea serverului.
DispatcherServlet este o parte importantă a framework-ului Spring MVC și este folosit pentru a gestiona fluxul de
solicitări și răspunsuri pentru aplicațiile web bazate pe Spring. El dirijează cererile către controlerele adecvate și
facilitează procesarea acestora în mod eficient.

#### When do you use RestControllers, when just simple Controllers?

- RestController-uri atunci când dezvoltați servicii web RESTful și dorim ca rezultatele să fie
  realizate/oferite în format JSON sau XML
- Controller-e simple atunci când dezvoltați aplicații web tradiționale și vă așteptați să generați răspunsuri HTML.

#### What is Spring Application Context?

ApplicationContext este o interfață în Spring care extinde funcționalitatea BeanFactory. Aceasta oferă acces la diferite
caracteristici ale framework-ului Spring, cum ar fi gestionarea ciclului de viață a bean-urilor, gestionarea
evenimentelor, internaționalizarea, accesul la resurse externe și multe altele.

####///////////////// What are the main ways to define a bean in the Application Context?

- Annotarea @Component sau derivatele acesteia (@Service, @Repository, etc.).
- Declararea în fișierele XML de configurare Spring.
- Utilizarea programatică a API-ului Spring pentru a defini bean-uri în Java.

#### Difference between .jar and .war files.

- .jar (Java Archive): Este un fișier de arhivă utilizat pentru a grupa clase Java, biblioteci și resurse într-un singur
  pachet. Fișierele .jar sunt utilizate în principal pentru aplicații standalone sau biblioteci Java, și conțin bytecode
  și manifeste pentru a specifica informații suplimentare despre pachet.

- .war (Web Application Archive): Este un fișier de arhivă utilizat pentru a ambala și distribui aplicații web Java.
  Fișierele .war conțin toate resursele necesare pentru o aplicație web, inclusiv pagini JSP, fișiere HTML, servlets, și
  configurații. Acestea sunt utilizate pentru a desfășura aplicații web pe serverele web Java.

#### What are the major differences between Maven, Ant and Gradle?

- Maven este o unealtă de gestionare a proiectelor care se bazează pe conceptul de "convenție înaintea configurației" (
  Convention Over Configuration).
  Utilizează un fișier de configurare XML numit pom.xml pentru gestionarea dependențelor, ciclurilor de viață ale
  proiectelor și construirea proiectelor.
  Folosește convenții pentru structura proiectului și numele fișierelor.
  Ant:

- Ant (Apache Ant) este o altă unealtă de automatizare a construirii proiectelor Java.
  Utilizează fișiere XML pentru a defini sarcini (tasks) și dependențe pentru construirea proiectelor.
  Este mai flexibil și mai orientat spre configurație explicită.
  Gradle:

- Gradle este o unealtă care combină aspecte din Maven și Ant, oferind un sistem de construire bazat pe Groovy DSL.
  Permite definirea sarcinilor și dependențelor într-un mod flexibil, permițând totodată folosirea convențiilor.
  Este mai puternic și mai expresiv în comparație cu Maven și Ant.

#### What is Maven used for?

Maven este folosit pentru gestionarea proiectelor de dezvoltare a software-ului. Acesta oferă o structură și un cadru
pentru construirea, testarea, ambalarea și gestionarea proiectelor Java.

- Gestionarea dependențelor: Maven descarcă automat dependențele necesare pentru proiect din repository-urile
  configurate.
- Construirea proiectelor: Maven automatizează procesul de construire a proiectului, inclusiv compilarea codului sursă,
  generarea de rapoarte și pachetarea rezultatelor.
- Testarea: Maven facilitează executarea testelor unitare și de integrare în cadrul proiectului.
- Publicarea artefactelor: Maven permite publicarea și distribuirea bibliotecilor și aplicațiilor Java în repository-uri
  pentru a fi utilizate de alți dezvoltatori.
- Gestionarea ciclului de viață al proiectului: Maven oferă faze și cicluri de viață predefinite pentru construirea și
  gestionarea proiectelor.

#### What does a pom.xml file contains in Maven?

Fișierul pom.xml din Maven conține configurarea proiectului:

- Coordonatele proiectului, cum ar fi numele, identificatorul, versiunea, și descrierea.
- Dependințele proiectului, care specifică bibliotecile externe necesare.
- Configurația construirii proiectului, inclusiv plugin-urile utilizate pentru sarcinile specifice.
- Ciclurile de viață ale proiectului, cum ar fi fazele de construire (compilare, testare, pachetare, instalare, etc.).
- Configurația pentru rapoarte și documentație.

### Object Relational Mapping, JPA

#### What is an ORM? What are the benefits, when to use?

Un ORM (Object-Relational Mapping) este o tehnică de programare care permite maparea obiectelor dintr-o aplicație la
înregistrările dintr-o bază de date relațională și viceversa. Beneficiile utilizării unui ORM includ:

- Abstractizare a bazei de date: ORM-ul permite dezvoltatorilor să lucreze cu obiecte în codul lor și să evite detaliile
  specifice ale bazei de date, precum limbajul SQL.
- Portabilitate: Codul ORM poate fi mai ușor mutat între diferite sisteme de gestiune a bazelor de date fără a necesita
  modificări semnificative.
- Productivitate crescută: ORM-ul oferă funcționalități pentru crearea, citirea, actualizarea și ștergerea obiectelor
  din baza de date, ceea ce simplifică dezvoltarea.
- Redundanță redusă: ORM-ul gestionează aspectele repetitive ale comunicării cu baza de date, eliminând nevoia de a
  scrie instrucțiuni SQL manuale.
- Consistență obiect-bază de date: ORM-ul menține coerența între modelul de date al aplicației și structura bazei de
  date.

#### What is the difference between JDBC and JPA? Which are the advantages and disadvantages of each? Give a general overview.

- JDBC (Java Database Connectivity):

Este o specificație Java care oferă o interfață de programare pentru comunicarea directă cu bazele de date relaționale.
Dezvoltatorii trebuie să scrie instrucțiuni SQL manuale pentru a interacționa cu baza de date.
Este mai flexibil și permite control detaliat asupra operațiunilor cu baza de date.
Dezavantajul constă în nevoia de a scrie mult cod și în dificultatea de a păstra consistența între obiecte și baza de
date.

- JPA (Java Persistence API):

Este o specificație Java care definește un set de API-uri pentru ORM (Object-Relational Mapping).
Utilizează adnotări pentru a mapea obiectele la înregistrările din baza de date.
Simplifică dezvoltarea și reduce cantitatea de cod necesară.
Poate utiliza diverse implementări, cum ar fi Hibernate sau EclipseLink.
Dezavantajul constă în pierderea flexibilității detaliate oferite de JDBC în favoarea unei abstracții mai înalte.

#### What is Hibernate? What are the advantages, limitations?

Hibernate este o implementare populară a specificației JPA (Java Persistence API) și este un ORM (Object-Relational
Mapping) pentru limbajul de programare Java. Avantajele și limitele Hibernate includ:

-- Avantaje:

- Simplificare: Hibernate simplifică dezvoltarea aplicațiilor Java care interacționează cu baze de date relaționale,
  oferind o abstracție de nivel înalt peste operațiunile cu baza de date.
- Productivitate crescută: Dezvoltatorii pot lucra cu obiecte Java în loc să scrie instrucțiuni SQL manuale, ceea ce
  duce la o dezvoltare mai rapidă.
- Portabilitate: Hibernate oferă portabilitate între diferite sisteme de gestiune a bazelor de date.
- Abordare declarativă: Configurația Hibernate se face în mod declarativ folosind adnotări sau fișiere XML.
- Mai puțin cod de gestionare a resurselor: Hibernate gestionează automat conexiunile la baza de date și resursele
  asociate.

-- Limite:

- Complexitate: Pentru proiecte simple, Hibernate poate părea prea complex și poate adăuga o supracomplicare.
- Necesită învățare: Dezvoltatorii trebuie să învețe concepte specifice Hibernate pentru a-l utiliza eficient.
- Optimizare manuală: Pentru operațiuni complexe sau optimizare, poate fi necesară scrierea de cod suplimentar.

#### Name 3 different annotations used in JPA, what can they do for you?

- @Entity: Această adnotare se aplică unei clase Java pentru a o marca ca o entitate persistentă. O entitate persistentă
  este o clasă care este mapată la o tabelă într-o bază de date relațională. Adnotarea @Entity spune JPA să creeze o
  tabelă corespunzătoare pentru această clasă în baza de date.

- @Id: Această adnotare se aplică unui câmp într-o clasă marcată ca entitate persistentă. Ea indică că acel câmp
  reprezintă cheia primară a entității respective. O cheie primară este unica în cadrul tabelului și este folosită
  pentru
  a identifica înregistrările unice.

- @OneToMany: Această adnotare se aplică unei relații între două entități. Ea indică o relație de "unul-la-mulți" între
  entitatea curentă între entitatea curentă și o altă entitate. Adnotarea @OneToMany poate fi utilizată pentru a defini
  o relație de asociere între două entități, ceea ce permite gestionarea colecției de obiecte ale celeilalte entități.

#### What is object-relational impedance mismatch?

"Object-Relational Impedance Mismatch" este o problemă care apare atunci când se încearcă să se îmbine două paradigme
diferite: paradigma orientată pe obiecte a limbajului de programare și paradigma relațională a bazelor de date. Această
discrepanță se referă la dificultatea de a mapa în mod eficient și natural obiectele și structurile de date ale
limbajului de programare la tabelele și înregistrările unei baze de date relaționale.

-- Principalele aspecte ale "object-relational impedance mismatch" includ:

- Diferențe în modelarea datelor: Obiectele au o structură mai complexă și sunt organizate în mod diferit față de
  tabelele
  și înregistrările bazei de date relaționale.
- Dificultatea mapării obiectelor la baza de date: Acest proces necesită conversii complexe între obiectele de limbaj de
  programare și structurile de date relaționale.
- Performanță scăzută: Un ORM trebuie să efectueze adesea un număr mare de interogări pentru a obține sau a actualiza
  datele, ceea ce poate duce la performanță scăzută.

- Soluțiile la această problemă includ utilizarea ORM-urilor precum JPA sau Hibernate, care încearcă să reducă
  discrepanța printr-o mapare eficientă a obiectelor la structurile de date ale bazei de date.

#### What is a JpaRepository? What are the 2 main methods to define queries in them?

Un JpaRepository este o interfață specifică Spring Data JPA care extinde interfața de bază JpaRepository și adaugă
funcționalități suplimentare pentru a efectua operațiuni de bază de date asupra unei entități specificate. Acesta este
utilizat pentru a simplifica operațiunile CRUD (Create, Read, Update, Delete) pe entitățile dintr-o bază de date
folosind JPA.

Cele două metode principale pentru definirea interogărilor într-un JpaRepository sunt:

- Metodele de interogare derivate: JpaRepository permite definirea automată a interogărilor prin denumirea metodelor,
  folosind convenții de nume. De exemplu, dacă aveți o entitate numită User și doriți să găsiți toți utilizatorii cu un
  anumit nume, puteți defini o metodă în interfața JpaRepository ca findByNume(String nume). JpaRepository va genera
  interogarea SQL corespunzătoare în funcție de numele metodei.

- Anotarea @Query: JpaRepository permite definirea interogărilor personalizate folosind anotarea @Query. Cu această
  abordare, puteți specifica manual instrucțiunile SQL sau JPQL (Java Persistence Query Language) pentru a efectua
  interogări complexe. De exemplu, puteți crea o metodă în interfața JpaRepository și să o marcați cu @Query("SELECT u
  FROM User u WHERE u.age > :age") pentru a efectua o interogare specifică.

#### Why is the Set preferred over List when we want to store OneToMany relations?

- Evitarea duplicatelor: Un Set nu permite stocarea duplicatelor, ceea ce asigură că nu vor exista înregistrări
  duplicate
  în relație. În cazul unei liste (List), pot apărea duplicări, ceea ce poate duce la inconsistențe în date.

- Eficiență în operații de adăugare și ștergere: Set-urile sunt eficiente în operațiile de adăugare și ștergere a
  elementelor, deoarece nu trebuie să se verifice întreaga listă pentru duplicări sau poziții. Acest lucru este util în
  cazul relațiilor OneToMany, unde entitățile pot fi adăugate sau eliminate din set cu ușurință.

- Semnificație semantică: Folosirea unui Set subliniază intenția de a avea o colecție de elemente unice în relație. În
  cazul unei liste, semnificația poate fi mai puțin clară, și poate genera confuzii.

#### What kind of inheritance strategies are available? Which annotations are used to solve this?

- Single Table (Tabel unic): În această strategie, toate entitățile din ierarhie sunt stocate într-un singur tabel în
  baza
  de date. Se folosește adnotarea @Inheritance(strategy = InheritanceType.SINGLE_TABLE) pentru a specifica această
  strategie. Clasele concrete sunt diferențiate printr-un câmp discriminator care indică tipul entității.

- Joined Table (Tabele separate): În această strategie, fiecare clasă din ierarhie are propria sa tabelă în baza de
  date,
  iar clasele sunt conectate prin chei străine (foreign keys). Se folosește adnotarea @Inheritance(strategy =
  InheritanceType.JOINED) pentru a specifica această strategie.

- Table Per Class (Tabel per clasă): În această strategie, fiecare clasă din ierarhie are propria sa tabelă în baza de
  date, dar nu există conexiuni între tabele. Se folosește adnotarea @Inheritance(strategy =
  InheritanceType.TABLE_PER_CLASS).

- Mapped Superclass (Clasă super-mapată): În această strategie, o clasă din ierarhie este folosită doar pentru a furniza
  atribute comune și nu este mapată la o tabelă. Se folosește adnotarea @MappedSuperclass pentru a specifica această
  strategie.
