# General enterprise questions

## Software engineering

### Architectures

#### What is n-tier (or multi-tier) architecture?

Arhitectura n-tier (sau multi-tier) este un model de proiectare software care implică împărțirea unei aplicații în mai
multe niveluri sau straturi distincte (tiers). Aceste nivele reprezintă diferite aspecte ale aplicației și sunt
proiectate să funcționeze independent unul de celălalt. Principalele nivele dintr-o arhitectură n-tier includ nivelul de
prezentare (UI), nivelul de logică a aplicației și nivelul de stocare a datelor (bază de date). Această abordare ajută
la separarea funcționalității și responsabilităților în aplicație și poate îmbunătăți modularitatea și scalabilitatea.

#### What are microservices? Advantages and disadvantages?

Microserviciile sunt o abordare arhitecturală în care o aplicație este împărțită în componente software mici,
independente și interoperabile, cunoscute sub numele de microservicii. Fiecare microserviciu reprezintă o unitate
funcțională distinctă a aplicației și poate fi dezvoltat, implementat și gestionat independent.

- Avantajele microserviciilor includ scalabilitatea ușoară, dezvoltarea agilă, mentenanța ușoară și flexibilitatea în
  utilizarea tehnologiilor.
- Cu toate acestea, dezavantajele pot include complexitatea sporită a administrării unei rețele de microservicii și
  provocările de gestionare a comunicării între ele.

#### What is Separation of Concerns?

SOC este un principiu de proiectare software care implică împărțirea unei aplicații în componente sau module care se
ocupă de aspecte specifice sau "preocupări" ale aplicației. Aceste preocupări pot fi, de exemplu, interfața cu
utilizatorul, logica de afaceri și stocarea datelor. Prin aplicarea acestui principiu, se urmărește simplificarea
dezvoltării, întreținerii și extinderii aplicației, deoarece fiecare componentă se concentrează pe o singură preocupare
și poate fi dezvoltată independent.

#### What is a layered design and why is it important in enterprise applications?

Un design stratificat este o abordare arhitecturală în care o aplicație este împărțită în straturi sau niveluri logice,
fiecare având responsabilități specifice și interacționând cu straturile adiacente. Exemple de straturi pot include
nivelul de prezentare (interfața cu utilizatorul), nivelul de logică a aplicației și nivelul de stocare a datelor. Un
design stratificat este important în aplicațiile enterprise pentru a separa funcționalitatea și pentru a facilita
gestionarea și dezvoltarea aplicației. De asemenea, permite echipei să lucreze la straturi diferite în paralel,
îmbunătățind eficiența dezvoltării.

#### What is Dependency Injection?

Dependency Injection (DI) este un pattern de proiectare în care dependențele unui obiect sunt furnizate de către un alt
obiect. Acesta implică furnizarea dependențelor (obiecte necesare) unui obiect în loc să le creeze obiectul în sine. DI
ajută la reducerea cuplării între componente și facilitează testarea unitară, deoarece dependențele pot fi înlocuite cu
mock-uri în timpul testării. Framework-uri precum Spring facilitează implementarea DI în aplicații Java.

#### What is the DAO pattern? When and how to implement?

DAO (Data Access Object) este un pattern de proiectare care separă logica de acces la date (de exemplu, operațiile cu
baza de date) de logica de afaceri a unei aplicații. Scopul principal al acestui pattern este de a abstractiza modul în
care datele sunt accesate și manipulare, permițând schimbarea facilă a surselor de date (de exemplu, de la o bază de
date la altă bază de date sau servicii web). DAO este implementat printr-o interfață sau clasă care definește metode
pentru operațiile de acces la date.

#### What is SOA? When to use?

Service-Oriented Architecture (SOA) este o abordare arhitecturală care se concentrează pe dezvoltarea aplicațiilor ca un
set de servicii interoperabile și reutilizabile. Aceste servicii sunt proiectate pentru a îndeplini funcționalități
specifice și pot comunica între ele pentru a oferi funcționalități complexe. SOA promovează modularitatea și
reutilizarea codului.

SOA este utilă atunci când doriți să dezvoltați aplicații care pot fi scalate și extinse ușor, pentru a gestiona
complexitatea funcționalității și pentru a facilita colaborarea între diferite aplicații sau componente. Este folosită
în special în mediile enterprise pentru a integra sisteme și pentru a facilita schimbul de date între diverse aplicații.

### Testing

#### What are unit test, integration test, system test, regression test, acceptance test? What is the major difference between these?

- Testele unitare: Testează unități individuale de cod, cum ar fi funcții sau metode, pentru a verifica dacă acestea
  funcționează corect. Sunt concentrate pe detaliile implementării.

- Testele de integrare: Verifică cum funcționează mai multe unități sau module atunci când sunt integrate împreună.
  Scopul
  este să identifice problemele care pot apărea la interacțiunea dintre acestea.

- Testele de sistem: Testează întreaga aplicație sau sistem pentru a verifica dacă acesta îndeplinește cerințele și
  specificațiile stabilite. Se concentrează pe funcționalitățile și fluxurile de lucru ale întregului sistem.

- Testele de regresie: Sunt concepute pentru a asigura că modificările noi sau actualizările de cod nu afectează
  funcționalitățile existente. Rulează testele vechi pentru a verifica dacă acestea continuă să treacă.

- Testele de acceptare: Sunt efectuate pentru a valida dacă sistemul este pregătit pentru a fi livrat sau implementat în
  producție. Acestea sunt adesea definite în colaborare cu clienții sau utilizatorii finali și se concentrează pe
  cerințele de utilizare reală.

Principala diferență constă în nivelul de detaliu și de acoperire a funcționalității testate.

#### What is code coverage? Why is it used? How you can measure?

Acoperirea de cod (code coverage) măsoară gradul în care instrucțiunile sau linii de cod ale unei aplicații sunt
executate de către testele efectuate. Este folosită pentru a evalua calitatea și eficacitatea testelor și pentru a
identifica porțiunile de cod care nu sunt testate.

#### What does mocking mean? How would you do it 'manually' (i. e. without using any fancy framework)?

"Mocking" se referă la crearea unor obiecte simulare (mock-uri) care înlocuiesc obiectele reale în timpul testării
unitare. Aceste mock-uri imită comportamentul obiectelor reale pentru a izola unitatea testată de dependențele sale și
pentru a se asigura că testele se concentrează pe unitatea în sine.

Pentru a face "mocking" manual, puteți crea clase sau obiecte mock care implementează interfețele sau clasele pe care le
utilizați în unitatea dvs. de cod. Acest lucru implică adesea supraîncărcarea metodelor din interfețe sau clase și
specificarea comportamentului dorit în timpul testelor.

#### What is a test case? What is an assertion? Give examples!

Un caz de testare (test case) este o descriere detaliată a unei situații de test, care include datele de intrare,
acțiunile efectuate și rezultatul așteptat. Este utilizat pentru a verifica dacă o anumită funcționalitate sau aspect al
aplicației funcționează corect.

O aserțiune (assertion) este o afirmație logică sau o condiție specificată într-un caz de testare care trebuie să fie
adevărată pentru ca testul să fie considerat reușit. Aserțiunile sunt utilizate pentru a verifica dacă rezultatele
obținute în timpul testării corespund rezultatelor așteptate.

Exemple: AssertTrue,AssertEquals,AssertFalse

#### What is TDD? What are the benefits?

TDD (Test-Driven Development) este o metodă de dezvoltare software în care dezvoltatorii scriu mai întâi teste automate
pentru funcționalitatea pe care urmează să o implementeze, apoi implementează codul care să treacă aceste teste.

Beneficiile TDD includ:

- Asigurarea unei acoperiri solide cu teste pentru cod.
- Identificarea mai rapidă a problemelor și erorilor.
- Documentarea funcționalității codului prin teste.
- Facilitarea refacturării și îmbunătățirii continue a codului.

#### What are the unit testing best practices? (Eg. how many assertion should a test case contain?)

- Scrierea testelor înainte de implementarea codului (TDD).
- Izolarea unității testate de dependențele externe folosind "mocking" sau stub-uri.
- Testarea diferitelor scenarii, inclusiv cazuri de eroare și situații limită.
- Asigurarea independenței testelor pentru a putea fi rulate în orice ordine.
- Păstrarea testelor la fel de simple și independente de mediu ca posibil.

Numărul de aserțiuni într-un caz de testare poate varia în funcție de complexitatea unității testate, dar este
recomandat să se limiteze la o aserțiune per caz de testare pentru a menține teste clare și ușor de înțeles.

#### What is arrange/act/assert pattern?

"Aranjare/execuție/verificare" (sau "arrange/act/assert") este un pattern folosit în teste unitare pentru a organiza
structura testului. Acesta constă în următoarele etape:

- Aranjare (arrange): În această etapă, se pregătesc condițiile prealabile pentru test, cum ar fi inițializarea
  obiectelor
  sau configurarea mediului de test. Aceasta stabilește contextul în care va fi efectuat testul.

- Execuție (act): În această etapă, se efectuează acțiunile sau operațiile care trebuie testate. Este momentul în care
  unitatea sau funcționalitatea este invocată sau utilizată într-un mod specific.

- Verificare (assert): În această etapă, se verifică rezultatele sau starea obținută în timpul execuției și se compară
  cu
  rezultatele așteptate. Aici sunt folosite aserțiunile pentru a stabili dacă testul a fost reușit sau nu.

"Aranjare/execuție/verificare" ajută la organizarea și claritatea testelor, făcându-le mai ușor de înțeles și de
menținut.

### DevOps

#### What is continuous integration? Why is CI important?

Implică integrarea automată frecventă a schimbărilor de cod într-un sistem comun de control al versiunilor și testarea
automată a acestora. Scopul CI este să asigure că modificările de cod ale dezvoltatorilor sunt verificate rapid și
eficient, reducând astfel riscul de defecte sau conflicte între codul echipelor. Este importantă pentru:

- Identificarea rapidă a problemelor de compatibilitate și a erorilor de cod.
- Creșterea eficienței dezvoltării prin automatizare.
- Asigurarea calității continue a produsului software.

#### Why are tests important in the CI workflow?

- Asigură că modificările de cod nu afectează funcționalitățile existente.
- Detectează erorile și problemele într-un stadiu timpuriu al dezvoltării.
- Contribuie la menținerea calității codului și a produsului.

#### Name some software that help the CI workflow!

- Jenkins
- Travis CI
- CircleCI
- GitLab CI/CD
- TeamCity

#### What is Continuous Delivery?

Este o practică din DevOps care implică automatizarea procesului de pregătire și livrare a software-ului pentru a putea
fi implementat în orice moment. Cu alte cuvinte, software-ul este pregătit pentru livrare și testat automat în mod
constant, iar oricând este gata pentru implementare, fără efort suplimentar.

#### What is Continuous Deployment?

Este o practică din DevOps care merge un pas mai departe decât livrarea continuă. Aici, orice schimbare de cod care
trece cu succes prin testele automate este implementată automat în producție, fără intervenția umană suplimentară.

#### What is DevOps?

Este o abordare culturală și practică care promovează colaborarea strânsă între echipele de dezvoltare (Dev) și echipele
de operațiuni (Ops) pentru a îmbunătăți procesele de dezvoltare și implementare a software-ului. Scopul este să reducă
timpul și riscul asociat dezvoltării și implementării software-ului, permițând livrări mai rapide și mai fiabile.

### Software Methodologies

#### What kind of software-lifecycle models do you know?

Există mai multe modele de ciclu de viață software, inclusiv:

- Modelul în cascadă (Waterfall Model)
- Modelul în V (V-Model)
- Modelul ciclu de viață în spirală (Spiral Model)
- Dezvoltarea rapidă a aplicațiilor (RAD)
- Dezvoltarea orientată pe prototipuri
- Metodologii Agile (cum ar fi Scrum și Kanban)

#### What is a UML diagram? What kind of diagram types do you know?

Diagrama UML (Unified Modeling Language) este un limbaj de modelare grafic utilizat pentru a reprezenta vizual diferite
aspecte ale unui sistem software. Tipurile de diagrame UML includ:

- Diagrama de clase UML
- Diagrama de secvență UML
- Diagrama de activitate UML
- Diagrama de starea UML
- Diagrama de componentă UML
- Diagrama de obiect UML
- Diagrama de pachet UML
  Și multe altele.

#### What is a UML class diagram? What are the typical elements?

Diagrama de clasă UML este o diagramă statică care prezintă structura unei clase și relațiile sale cu alte clase.
Elementele tipice includ:

- Clase și interfețe
- Atribute (variabile de instanță)
- Metode (funcții)
- Asocieri între clase
- Moștenire (relații de subclasă)
- Agregare și compoziție (relații între obiecte)
- Multiplicitate (cardinalitatea relațiilor)

#### What kind of design patterns do you know? Bring at least 3 examples.

- Modelul Singleton
- Modelul Factory
- Modelul Adapter
- Builder

#### What is the purpose of the Iterator Pattern?

Pattern-ul Iterator este utilizat pentru a oferi o modalitate de a accesa elementele unei colecții (cum ar fi o listă
sau un arbore) fără a dezvălui detaliile interne ale acesteia. Scopul său este de a itera printr-o colecție fără a ține
cont de structura acesteia, permițând astfel parcurgerea eficientă a datelor.

#### What do you know about the SOLID principles?

Principiile SOLID sunt un set de cinci principii de proiectare a software-ului care promovează dezvoltarea unor coduri
mai ușor de întreținut și de extins. Acestea sunt:

- Principiul responsabilității unice (Single Responsibility Principle - SRP)
- Principiul deschis/închis (Open/Closed Principle - OCP)
- Principiul substituției lui Liskov (Liskov Substitution Principle - LSP)
- Principiul segregării interfețelor (Interface Segregation Principle - ISP)
- Principiul inversiunii dependențelor (Dependency Inversion Principle - DIP)

#### How would you separate data storage code and business logic code (which uses stored data) in an application?

Pentru a separa codul de stocare a datelor de codul logicii de afaceri, puteți utiliza un model de arhitectură, cum ar
fi modelul MVC (Model-View-Controller) sau modelul Repository. În acest mod, veți avea:

- Modelul sau stratul de stocare a datelor (de exemplu, o bază de date sau un sistem de fișiere) care se ocupă de
  accesarea și gestionarea datelor.
- Stratul de logica de afaceri care utilizează modelul de date pentru a efectua operații și calcule specifice
  aplicației.
- Stratul de prezentare sau interfața utilizator care afișează datele și interacționează cu utilizatorii.
  Această separare permite o mai mare modularitate și ușurință în întreținerea și testarea aplicației.

## Computer science

### Data Structures

#### What is the difference between Stack and Queue data structure?

- Stack este o structură de date de tip LIFO (Last-In, First-Out), ceea ce înseamnă că ultimul element introdus este
  primul care va fi scos.
- Queue este o structură de date de tip FIFO (First-In, First-Out), ceea ce înseamnă că primul element introdus este
  primul care va fi scos.

#### What is a graph? What are simple graphs? What are directed graphs? What are weighted graphs?

Un graf este o structură de date compusă din noduri (vârfuri) și arce (muchii) care conectează nodurile între ele.

- Grafurile simple sunt grafuri în care nu există muchii duplicate între aceleași două noduri și nu există bucle (muchii
  care conectează un nod cu el însuși).
- Grafurile orientate (sau digrafele) sunt grafuri în care arcele au direcție, adică o muchie merge doar într-o direcție
  între două noduri.
- Grafurile ponderate sunt grafuri în care fiecare muchie are o valoare sau un cost asociat.

#### What are trees? What are binary trees? What are binary search trees?

Arborii sunt structuri de date ierarhice compuse din noduri, în care fiecare nod are un singur părinte, cu excepția
nodului rădăcină.

- Arborii binari sunt arbori în care fiecare nod are cel mult doi copii, unul stânga și unul dreapta.
- Arborii de căutare binară sunt arbori binari în care fiecare nod are o proprietate astfel încât toate nodurile din
  subarborele stâng conțin valori mai mici decât nodul curent, iar toate nodurile din subarborele drept conțin valori
  mai mari decât nodul curent.

#### How can you store graphs in programs? What are the advantages/disadvantages per each?

Există două metode principale pentru a stoca grafurile în programe:

- Matricea de adiacență: Aceasta constă într-o matrice bidimensională în care fiecare element indică dacă există o
  muchie
  între două noduri. Avantajele includ accesul rapid la verificarea existenței muchiilor, dar dezavantajele includ
  utilizarea ineficientă a memoriei pentru grafurile rare.

- Listele de adiacență: Aici, pentru fiecare nod se ține o listă a nodurilor la care este conectat direct. Avantajele
  includ economisirea memoriei pentru grafurile rare și eficiența în adăugarea sau eliminarea de muchii, dar
  dezavantajele
  includ căutarea mai lentă a muchiilor.

#### What are graph traversal algorithms? What is BFS, how does it work? What is DFS, how does it work?

Algoritmii de traversare a grafurilor sunt utilizate pentru a explora și a accesa toate nodurile unui graf.

- BFS (Breadth-First Search) este un algoritm care explorează grafurile în straturi sau niveluri. Algoritmul începe de
  la
  un nod sursă, explorează toți vecinii acestuia, apoi trece la următorul nivel și continuă astfel până când toate
  nodurile sunt explorate. BFS folosește o coadă pentru a ține evidența nodurilor de explorat.

- DFS (Depth-First Search) este un algoritm care explorează cât mai adânc într-un subarbore înainte de a se întoarce.
  Algoritmul începe de la un nod sursă, explorează un subarbore cât de adânc poate, apoi se întoarce și explorează alte
  subarbori. DFS folosește o stivă pentru a ține evidența nodurilor de explorat.

#### How does dictionary work?
-HashMap

#### Why is it important for keys in a hashmap to have an immutable type? (Consider string for example.)
 - hashmap - se calculeaza hash la key
 - este facut sa fie key-value pair 

### Algorithms

#### What is QuickSort? Describe the main logic of this sorting algorithm.

QuickSort este un algoritm de sortare eficient bazat pe paradigma divide și cucerește. Logica principală a QuickSort
constă în următorii pași:

- Se alege un element din vector ca pivot.
- Se partitionează vectorul astfel încât elementele mai mici sau egale cu pivotul sunt plasate în stânga acestuia, iar
  cele mai mari sunt plasate în dreapta.
- Se aplică recursiv QuickSort pentru cele două subliste (stânga și dreapta).
- Procesul se repetă până când lista este complet sortată.
  QuickSort este eficient datorită faptului că are un timp mediu de execuție rapid și utilizează un spațiu constant, dar
  poate avea performanțe mai slabe în cazul unor liste cu ordonare prea apropiată de cea inversă.

## Software design

### Security

#### What is OAuth2?

OAuth2 (Open Authorization 2.0) este un protocol de autorizare deschis și standardizat care permite aplicațiilor să
obțină permisiunea de la utilizatori pentru a accesa resursele protejate ale acestora pe internet, fără a dezvălui
parolele acestora sau a altor informații sensibile. Protocolul OAuth2 este folosit în principal pentru autentificarea și
autorizarea utilizatorilor în aplicațiile web și serviciile online.

OAuth2 funcționează prin emiterea unor token-uri de acces către aplicații terțe după ce utilizatorii au dat
consimțământul pentru accesul la resursele lor protejate. Aceste token-uri pot fi apoi folosite pentru a accesa
resursele respective fără a necesita introducerea parolei utilizatorului în mod repetat.

#### What is Basic Authentication?

Autentificarea de Bază (Basic Authentication) este o metodă simplă de autentificare utilizată în HTTP, în care un
client (de obicei un browser web) trimite un nume de utilizator și o parolă către un server pentru a se autentifica și a
accesa resurse protejate. Aceste informații de autentificare sunt trimise în antetul cererii HTTP sub forma unui șir de
caractere codificat în Base64(pentru ceva ce e binar) sau JSON.

#### What is CORS, why it’s needed in browsers?

CORS (Cross-Origin Resource Sharing) este o politică de securitate implementată în browserele web pentru a preveni
accesul neautorizat la resurse web din alte domenii (origin-uri) decât cel de pe care a fost încărcată pagina web. CORS
este necesar pentru a proteja utilizatorii de posibile atacuri ale terțelor părți care ar putea accesa și manipula
datele lor personale pe alte site-uri.

Politicile CORS sunt configurate pe servere web pentru a specifica care origin-uri sunt autorizate să acceseze resursele
serverului. Astfel, un server poate permite sau restricționa accesul resurselor sale pentru cereri provenite din anumite
origin-uri. În absența politicii CORS, browserele ar bloca implicit cererile cross-origin pentru a preveni posibilele
amenințări de securitate.

#### How can you initialize a CSRF attack?

CSRF (Cross-Site Request Forgery) este un tip de atac în care un atacator determină un utilizator autentificat să
efectueze acțiuni neintenționate pe un site web pe care acesta este autentificat. Pentru a iniția un atac CSRF,
atacatorul trebuie să convingă utilizatorul să acceseze o pagină web sau să efectueze o acțiune care va trimite o cerere
HTTP către un alt site web în numele utilizatorului.

Un exemplu simplu de atac CSRF ar putea implica trimiterea unui e-mail fals care conține un link către o pagină web cu
un formular care trimite o cerere de transfer de bani către un alt cont fără cunoștința utilizatorului. Atunci când
utilizatorul vizitează pagina și este autentificat pe site-ul respectiv, cererea este trimisă automat fără acordul său.

Pentru a preveni atacurile CSRF, site-urile web pot implementa măsuri de securitate suplimentare, cum ar fi folosirea
unor token-uri de protecție CSRF.

#### What is JWT used for? Where to store it on client side?

JWT (JSON Web Token) este un format deschis pentru reprezentarea informațiilor între părți sub formă de obiect JSON,
care este semnat digital și poate fi verificat. JWT este adesea folosit pentru autentificare și autorizare în
aplicațiile web și serviciile online. Un JWT conține informații despre subiect (de obicei, un utilizator autentificat)
și poate conține și alte atribute precum data de expirare sau scopul utilizării.

Un JWT poate fi stocat pe client într-un cookie sau într-un spațiu de stocare local (localStorage sau sessionStorage)
pentru a menține informații de autentificare între solicitările către server. De obicei, JWT este trimis ca un antet "
Authorization" în cererile HTTP către server pentru a confirma identitatea utilizatorului.

Este important de menționat că, din motive de securitate, JWT trebuie să fie protejat de accesul neautorizat și să fie
transmis în mod securizat între client și server. De asemenea, datele sensibile nu ar trebui să fie stocate într-un JWT,
deoarece acesta poate fi decriptat și citit de către oricine îl deține.

### Threaded programming

#### When do you need to use threads in an application?

Folosirea threads este necesară într-o aplicație atunci când doriți să efectuați mai multe sarcini sau
operații în paralel, pentru a profita de resursele hardware disponibile și pentru a îmbunătăți performanța.

- Procesarea paralelă a datelor sau a sarcinilor pentru a accelera timpul de răspuns al aplicației.
- Realizarea de operații asincrone pentru a menține aplicația responsivă și a evita blocarea interfeței de utilizator.
- Implementarea serviciilor de rețea sau servere concurente care trebuie să gestioneze multiple conexiuni simultane.
- Utilizarea de resurse hardware paralele, cum ar fi procesoare cu mai multe nuclee, pentru a îmbunătăți eficiența.

#### What is a daemon thread?

Este un thread în Java care rulează în fundal și nu împiedică încheierea aplicației atunci când celelalte thread
s-au terminat. Thread-ul principal al unei aplicații Java nu este un thread daemon, în timp ce thread-urile
secundare pot fi marcate ca threads daemon. Atunci când ultimul thread non-daemon se încheie, JVM (Java Virtual Machine)
încheie și toate threads daemon care mai sunt active.

Acestea sunt utile pentru activități de întreținere sau de fond care trebuie să ruleze pe tot parcursul vieții
aplicației, dar nu trebuie să împiedice încheierea acesteia.

#### What is the difference between concurrent and parallel execution of code?

Execuția concurentă se referă la gestionarea simultană a mai multor sarcini sau fire de execuție, într-un mod în care
ele pot începe, să ruleze și să se oprească în mod intercalat. Cu alte cuvinte, execuția concurentă nu implică neapărat
rularea simultană a sarcinilor, ci gestionarea lor în mod eficient pentru a îmbunătăți performanța și a menține
responsivitatea aplicației.

Execuția paralelă, pe de altă parte, se referă la rularea efectivă simultană a mai multor sarcini sau fire de execuție
pe procesoare sau nuclee separate. În acest caz, sarcinile se desfășoară cu adevărat în același timp, ceea ce poate duce
la o creștere semnificativă a performanței în aplicații care pot beneficia de paralelism.

Diferența principală constă în modul în care sunt gestionate și planificate sarcinile. Execuția concurentă poate utiliza
un singur fir de execuție pentru a rula mai multe sarcini, în timp ce execuția paralelă implică utilizarea mai multor
fire de execuție pentru a efectua sarcinile în paralel.

#### What is the most important problem developers are faced when using threads?

Una dintre cele mai importante probleme cu care se confruntă dezvoltatorii atunci când utilizează fire de execuție este
sincronizarea și gestionarea concurenței. Mai precis, dezvoltatorii trebuie să se asigure că mai multe fire de execuție
care accesează resurse comune o fac într-un mod sigur și ordonat pentru a evita condițiile de cursă, blocările și alte
probleme legate de concurență.

Sincronizarea poate deveni complexă, deoarece programatorii trebuie să utilizeze mecanisme precum blocuri sincronizate,
semafoare, mutex-uri sau variabile condiționale pentru a controla accesul concurent la resursele partajate. O gestionare
incorectă a concurenței poate duce la erori greu de depistat și de reparat în aplicații.

#### In what kind of situations can deadlocks occur?

Blocările (deadlocks) pot apărea în situații în care mai multe threads așteaptă reciproc să elibereze resursele
pe care le dețin, fără să poată face acest lucru. Această situație duce la blocarea permanentă a acestor thread,
ceea ce înseamnă că ele nu mai pot progresa.

Blocările pot apărea în situații de concurență când thread-uri încearcă să obțină acces la resursele partajate în ordine
diferită sau să aștepte ca altele să elibereze resurse pe care le dețin. Dacă niciunul dintre thread-uri nu
cedează, atunci se produce un deadlock.

#### What are possible ways to prevent deadlocks from occurring?

- Planificare ordonată a resurselor: Dezvoltatorii pot stabili o ordine fixă sau convențională în care resursele trebuie
  să fie obținute și eliberate de către thread-uri. Acest lucru poate ajuta la evitarea ciclurilor de așteptare
  reciproce.

- Utilizarea mutex-urilor și semafoarelor: Mecanisme precum mutex-urile și semafoarele pot fi utilizate pentru a bloca
  și debloca accesul la resursele partajate într-un mod controlat și sincronizat.

- Evitarea prelungirii tranzacțiilor: Dezvoltatorii pot evita să țină resursele blocate pentru perioade lungi de timp
  sau pot implementa limite de timp pentru a elibera resursele.

- Detectarea și gestionarea deadlock-urilor: Dezvoltatorii pot implementa algoritmi de detectare a blocărilor și de
  acțiune corespunzătoare pentru a le trata atunci când apar.

- Folosirea liberiilor și framework-urilor de gestionare a concurenței: Unele limbaje de programare și framework-uri
  oferă soluții și unelte pentru gestionarea concurenței și evitarea blocărilor.

Prevenirea blocărilor este esențială pentru a menține performanța și stabilitatea aplicațiilor care folosesc thread-uri
concurente.

#### What does critical section or critical region mean in the context of concurrent programming?

În programarea concurentă, o "secțiune critică" este o parte a codului care trebuie să fie executată de un singur thread
la un moment dat pentru a evita conflictele și pentru a menține integritatea datelor partajate.
