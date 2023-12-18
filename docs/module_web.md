# Web Module Questions

### Functional patterns

**1. What is a callback function?**
* A callback function is passed to another function as an argument and it is executed after that function is invoked. Frequently, callback functions are used to continue code after an asyncronous operation was completed (asyncronous callbacks).

```
async function fetchData(callback) {
    const response = await fetch("fetchLINK");
    const json = await response.json();
    callback(json);
  }

  useEffect(() => {
    fetchData(setData);
  }, []);
```

**2. What is ECMA script ? What is the difference between Javascript & ECMA script ?**

* JavaScript is a programming language initially created by Netscape, whistl ECMAScript consists of specifications (syntax, semantics, structure) for a scripting language created by European Computer Manufacturers Association (ECMA). JavaScript is one implementation based on ECMAScript standards.

**3. What is the difference between `let` & `var` ?**

* The `let` variables only work inside the block where they are defined (they are blocked-scoped variables).
  On the other hand, the `var` variables are function-scoped variables that, if defined inside a function, are accesible anywhere in that function (including nested blocks or loops), and if they are defined globally, they are accesible globally (in any function, any loop, any block of code).   
  Also, `let` variables are a EcmaScript6 features, and `var` variables are a ECMAScript1 feature (the `let` and `const` are modern alternatives included in more recent standards, in order to have better control over variable scoping and to prevent common programming errors).

**4. Write an example where using the `var` declaration instead of the `let` could create a hard to debug code.**

:black_nib:
|                                                                         var                                                                        |                                                                         let                                                                        |
|:--------------------------------------------------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------------------------------------------:|
| function printNumbers(){<br>var num = 10;<br><br>if (true){<br>var num = 20;<br>}<br><br>console.log(num)<br>}<br><br>printNumbers() // Output: 20 | function printNumbers(){<br>let num = 10;<br><br>if (true){<br>let num = 20<br>}<br><br>console.log(num);<br>}<br><br>printNumbers() // Output: 10 |


**5. Give a practical example where you would use the `reduce` function in javascript.**

:black_nib: We can use `reduce` to calculate the sum of all numbers in an array.

```
const numbers = [1, 2, 3, 4, 5];

const sum = numbers.reduce((accumulator, currentValue) => {
  return accumulator + currentValue;
}, 0);

console.log(sum); // Output: 15
```

**6. Give a practical example where you would use the `map` function in javascript.**

:black_nib: We can use `map` to transform each element of an array into another (Celsius degrees into Fahrenheit degrees).
```
const celsiusTemperatures = [0, 10, 20, 30, 40];

const fahrenheitTemperatures = celsiusTemperatures.map((celsius) => {
  return (celsius * 9/5) + 32;
});

console.log(fahrenheitTemperatures); // Output: [32, 50, 68, 86, 104]
```

**7. Give a practical example where you would use the `filter` function in javascript.**

:black_nib: We can use `filter` to create a new array according to our criteria.

```
const people = [
  { name: 'Alice', age: 25 },
  { name: 'Bob', age: 30 },
  { name: 'Charlie', age: 35 },
  { name: 'Dave', age: 40 },
  { name: 'Eve', age: 45 },
];

const peopleOver35 = people.filter(person => person.age > 35);

console.log(peopleOver35); // Output: [ { name: 'Dave', age: 40 }, { name: 'Eve', age: 45 } ]
```

### Web basics

**8 What is a web server?**

*A web server can refer to hardware or software or both.
Commonly, a web server is a software application that receives requests from the clients, processes the data and sends back responses for requested content.

**9 Explain the client-server architecture.**

* According to `Simplilearn.com`, in the IT context, the client is a computer/phone/tablet/device, also called a Host, that uses the service and accepts information. The server is a remote computer that provides access to data and services.
* According to `Wikipedia.com`, the client–server model is a distributed application structure that partitions tasks or workloads between the providers of a resource or service, called servers, and service requesters, called clients.
* In conclusion, the client-server architecture describes the model in which one ore more clients (machines) request and receive services and data from a server over a network.


**10 What is the difference between synchronous and asynchronous execution?**

* According to `Stackoverflow.com`, when you execute something synchronously, you wait for it to finish before moving on to another task. When you execute something asynchronously, you can move on to another task before it finishes.
* When you execute code or processes in a computer program, in the synchronous execution, the program waits for each line of code to be completed in sequence. In contrast, in asynchronous execution, the program moves on to the next code regardless of the stage of execution for the previous code.

**11 What is `npm`? Why is it useful?**

*  `npm` is a package manager for Node.js that allows developers to install and manage third-party packages and dependencies for their `Node.js` projects. Developers can specify the dependencies required for their project in the `package.json` file, and then use the `npm install` command to automatically download and install all the required packages and their dependencies.

**12 What is the difference between the `depdendencies` & `devDependencies` in a `package.json` file?**

* Dependencies are packages required for the application in production, whistl devDependencies are packages needed for local development and testing.

**13 What would be the impact of javascript `fetch` if it was not asyncronous?**

* If `fetch()` was not asynchronous, the program would have to wait for the fetch response and the code would not be executed until getting that response, which would make the page slow and unresponsive.

**14 What benefits would bring to a developer to use the `Postman` application?**

* `Postman` is helping developers to save time and effort when building and testing API. Using Postman, you can test, you can collaborate, you can debug, you can understand easier the API documentation.

**15 List the parts of the URL.**

:black_nib: An URL (Uniform Resource Locator) has the following parts:

* [x] a scheme (examples: `http://`, `https://`, `ftp://`, `file://`)
* [x] a domain or host (example: `www.site.com`)
* [x] a top-level domain (examples: `.edu`, `.com`, `.org`, `.net`)
* [x] a second-level domain (what is between www and domain; in previous example: site)
* [x] an optional subdomanin (example: `blog.site.com`)
* [x] a path (example: `/index.html`)
* [x] optional query string(s) (parameter(s) or data in the URL)
* [x] an optional fragment identifier (section or resource preceded by `#` in and URL)

**16 What is query parameter?**

* According to `Branch.io`, query parameters are a defined set of parameters attached to the end of a url. They are extensions of the URL that are used to help define specific content or actions based on the data being passed.
* To append query params to the end of a URL, a `?` or `?q=` is added, followed by a query parameter.
* To add multiple parameters, an `&` is added in between each.
* A query parameter consists of a key-value pair.

`https://example.com/path?name=Branch&products=[Journeys,Email,Universal%20Ads]`
`https://example.com/search?q=apple&category=fruit`

****

### **HTTP (Hypertext Transfer Protocol)**


**17. What is HTTP?**

Reprezinta fundamentul comunicarii de date pentru World Wide Web. 
Este un protocol sau un set de reguli care dicteaza modul in care mesajele ar trebui sa fie formatate si transmise;
si de altfel dicteaza ce actiuni ar trebui sa intreprinda web serverele si browserele ca un raspuns la diversele comenzi.

**18. Why is HTTP important?**

* **Comunication:**
  * Faciliteaza comunicarea intre client devices (calculatoare, laptopuri, telefoane, tablete, etc.) si web serververs.

* **Standardization:** 
  * Coerenta: HTTP stabilește reguli clare pentru cum ar trebui să arate cererile și răspunsurile, asigurându-se că fiecare browser și server "vorbește aceeași limbă".
  * Fiabilitate: HTTP asigură că datele sunt transferate într-un mod fiabil prin utilizarea unor metode specifice (cum ar fi GET, POST) și coduri de statut (de exemplu, 200 pentru succes, 404 pentru 'Not Found'). Acest lucru este similar cu gestionarea excepțiilor în OOP. În Java, de exemplu, folosim blocuri try-catch pentru a gestiona situațiile în care ceva nu merge conform așteptărilor. În mod similar, HTTP utilizează coduri de statut pentru a informa clientul despre starea cererii sale, permițând un tratament corespunzător al diferitelor scenarii (de exemplu, reîncercarea unei cereri, gestionarea erorilor etc.).
  * Exemplu Practic:
    Să ne gândim la un scenariu simplu: un browser solicită o pagină web de la un server.
    * Cerere HTTP: Browserul trimite o cerere HTTP (de exemplu, folosind metoda GET) către server pentru a solicita o pagină web. Aceasta este similară cu apelarea unei metode în OOP, unde metoda definește acțiunea de efectuat.
    * Răspuns HTTP: Serverul răspunde cu un document HTML, împreună cu un cod de statut (de exemplu, 200 OK). Acesta este similar cu returnarea unui valorii de către o metodă în OOP, unde valorile returnate și tipurile de date sunt conforme cu definiția metodei.

* **StateLessness:**
  * Statelessness în HTTP: Fiecare cerere HTTP este tratată independent de celelalte. Serverul nu păstrează nicio informație despre starea clientului între cereri. Acest lucru este similar cu metodele stateless în OOP, unde starea unui obiect nu este afectată de apelurile metodei. De exemplu, în Java, o metodă statică poate fi considerată stateless dacă nu modifică sau depinde de starea instanței clasei.
  * Implicații pentru Gestionarea Sesiunilor Web: Deoarece HTTP este fără stare, sesiunile web trebuie gestionate în moduri alternative. Aceasta este similară cu modul în care în OOP trebuie să gestionăm explicit starea când avem nevoie de ea. De exemplu, putem folosi variabile de instanță pentru a păstra starea unui obiect în Java. În mod similar, în web, sesiunile sunt gestionate folosind cookie-uri, parametri URL, sau alte mecanisme pentru a păstra starea peste cererile HTTP.
  * Exemplu Practic:
    Să luăm exemplul unui utilizator care face cumpărături într-un magazin online:
    * Fără Stare (Statelessness): Când utilizatorul adaugă un produs în coșul de cumpărături și apoi navighează la o altă pagină, serverul nu își amintește că utilizatorul a adăugat acel produs, deoarece fiecare cerere HTTP este independentă. Acest lucru este similar cu apelarea unei metode stateless în Java, care nu păstrează nicio informație între apeluri.
    * Gestionarea Stării: Pentru a păstra informații despre produsele adăugate în coș, magazinul online folosește **cookie-uri sau sesiuni**. Acestea permit serverului să "rețină" ce a făcut utilizatorul pe parcursul mai multor cereri HTTP. În OOP, acest lucru este similar cu utilizarea variabilelor de instanță pentru a menține starea unui obiect.

**19. What is HTTP Formed By?**

**I. Requests**
* **Request Line:** Acesta este similar cu semnătura unei metode în Java. Așa cum o semnătură de metodă definește numele metodei, tipul de returnare și parametrii, linia de cerere HTTP specifică:
  * **metoda** HTTP (GET, POST etc.), prin analogie cum ne referim la numele metodei.
  * **URL-ul:** resursa solicitată, prin analogie este pe postul de parametru.
  * **versiunea HTTP** (1.1, 2, 3) care joaca rolul tipului de returnare prin analogie cu o metoda.*


* **Headers:** Furnizează informații suplimentare despre cererea clientului. Exemple de antete includ:
  * **Content-Type:** Indică tipul de date al corpului cererii, de exemplu, application/json.
  * **User-Agent:** Identifică clientul care face cererea.
  * **Accept:** Specifică tipurile de conținut pe care clientul este dispus să le primească.
  * **Authorization:** Folosit pentru autentificarea clientului.
  

* **Body:** Opțional în cereri, corpul conține datele care sunt trimise de catre client, către server. De exemplu:
  * **GET:** tipic nu are un corp, deoarece scopul său este pur și simplu de a solicita date de la server (cum ar fi solicitarea unei pagini web), iar parametrii cererii sunt transmiși de obicei în URL (de exemplu, ca parte a șirului de interogare).
  * **POST:** Utilizat pentru a trimite date pentru crearea unei noi resurse. Corpul ar putea include detaliile unui nou utilizator pentru a fi înregistrat.
  * **PUT:** Folosit pentru a actualiza o resursă existentă. Corpul ar conține datele actualizate ale resursei.
  * **PATCH:** Folosit pentru a actualiza partial o resursă existentă. Corpul ar conține datele actualizate ale resursei.
  * **Depinde de Context:** Există situații unde chiar și cererile POST sau PUT pot să nu aibă un corp, cum ar fi când toate datele necesare sunt incluse în URL sau în antete.
  * **Excepții și Exemple:** Deși tehnic este posibil ca o cerere GET să conțină un corp, acesta este un caz atipic și neobișnuit. Majoritatea serverelor și framework-urilor web ignoră corpul unei cereri GET și se bazează pe parametrii din URL pentru a procesa cererea. Nu există un standard clar în ceea ce privește procesarea corpului unei cereri GET, și de aceea este rar utilizat în practică.

* **Exemple:**
  * **Get Request:**
    ```
    GET /produse?categorie=carti HTTP/1.1
    Host: www.exemplu.com
    ```
      * **Metoda HTTP:** GET
      * **URL:** /produse?categorie=carti:
        * /produse: Este calea către resursa pe care dorim să o accesăm pe server.
        * ?categorie=carti: Aceasta este o parte de interogare (query string). Este utilizată pentru a furniza parametri suplimentari serverului. În acest caz, transmite că dorim să accesăm produsele filtrate dupa categoria "cărți".
      * **Versiunea protocolului:** HTTP/1.1.
      * **Header Request:** www.exemplu.com specifica cine este gazda (host)
  * **Post Request:**
  ```
    POST /utilizatori HTTP/1.1
    Host: www.exemplu.com
    Content-Type: application/json
    {
       "nume": "Ion Popescu",
       "email": "ion.popescu@example.com"
    }
  ```
  * **Metoda HTTP:** POST
  * **URL:** /utilizatori
  * **Versiunea protocolului:** HTTP/1.1.
  * **Header Request:** www.exemplu.com specifica cine este gazda (host)
  * **Header Request:** Content-Type: application/json: Acest antet indică tipul de date al corpului cererii, în acest caz, JSON (JavaScript Object Notation).
  * **Body Request:** { "nume": "Ion Popescu", "email": "ion.popescu@example.com" }: Acesta este corpul cererii, care conține datele trimise la server. În acest exemplu, datele sunt un obiect JSON cu două proprietăți: nume și email. Acestea reprezintă informațiile despre noul utilizator care trebuie creat.

**II. Responses**
* **Response Line:** HTTP/1.1 200 OK sau HTTP/1.1 404 Not Found.
  * **Versiunea protocolului HTTP:** 1.1
  * **HTTP Status Code:** 200 sau 404 - Număr care indică rezultatul cererii.
  * **Reason Phrase:** OK sau Not Found - O descriere text, lizibilă, a codului de stare, care explică rezultatul cererii.
* **Headers:** Oferă informații suplimentare despre răspuns. Exemple de antete de răspuns includ:
  * **Content-Type:** Tipul de date al corpului răspunsului.
  * **Content-Length:** lungimea corpului răspunsului în octeți
  * **Access-Control-Allow-Origin:** Specifică ce origini sunt permise să acceseze resursa.
  * **User-Agent:** Informații despre browserul sau clientul care a făcut cererea.
* **Empty Line:** O linie goală urmează după anteturile răspunsului, indicând sfârșitul secțiunii de anteturi și începutul corpului răspunsului.
* **Body:** Opțional, conține conținutul solicitat, cum ar fi o pagină web, o imagine sau date JSON. În OOP, acest lucru poate fi comparat cu returnarea unui obiect sau a unei structuri de date complexe de către o metodă.


* **Exemple cand are body:**
  * **Get cu body:** Un răspuns de succes (200 OK) pentru o pagină web va include, de obicei, HTML-ul paginii în Body Response.
  * **Un răspuns pentru o cerere POST:** care creează o resursă ar putea include detalii despre resursa creată.
  * **Un răspuns cu un cod de stare 204 No Content:** care este adesea folosit pentru a indica succesul unei cereri care nu produce conținut suplimentar, nu va avea un corp.
  * **Răspunsuri Informaționale sau Erori:** Pentru anumite răspunsuri, cum ar fi cele informaționale (coduri de stare 1xx) sau unele erori client (4xx) și server (5xx), corpul poate să nu fie necesar sau relevant.

**20. Cookies vs Sessions:**
* **Cookies:**
  * Cookie-urile sunt mici bucăți de date trimise de un server către browserul clientului și apoi trimise înapoi de client la fiecare cerere ulterioară către același server. Practic, acestea sunt folosite pentru a "aminti" serverului, informații despre utilizator.
  * Cum Funcționează: Când vizitați un site web, serverul poate trimite un cookie către browserul dvs. Acest cookie este stocat pe computerul dvs. și trimis înapoi la server cu fiecare cerere HTTP ulterioară. De exemplu, un site de comerț electronic poate folosi cookie-uri pentru a păstra informații despre produsele adăugate în coșul de cumpărături.
  * Caracteristici: Cookie-urile pot păstra diverse tipuri de date, de la preferințele utilizatorului până la datele de autentificare. Ele pot fi setate să expire după o anumită perioadă de timp.
  * Capacitate: sunt fisiere mici de text cu o capacitate de pana la 4kb.
  * Important: din cauza ca sunt stocate pe dispozitivul clientul nu sunt atat de sigure.

* **Sessions:**
  * Sesiunile sunt un alt mod de a păstra starea pe web. O sesiune creează un fișier unic pe server pentru fiecare utilizator care vizitează site-ul.
  * Cum Funcționează: Când un utilizator accesează un site web, serverul creează o sesiune și păstrează un identificator unic al sesiunii, de obicei trimis către browser sub forma unui cookie. Acest identificator este utilizat pentru a reasocia cererea cu sesiunea corespunzătoare. De exemplu, într-un sistem de login, sesiunea poate păstra ID-ul utilizatorului și alte detalii de autentificare.
  * Caracteristici: Ele sunt ideale pentru stocarea informațiilor sensibile și pot fi configurate să expire după o anumită perioadă de inactivitate. Cand se inchide browserul sau se face delogarea, se inchide si sesiunea.
  * Capacitate: Sunt fisiere criptate cu o capacitate de stocare de pana la 128mb.
  * Important: Sesiunile sunt păstrate pe server, ceea ce le face, în general, mai sigure decât cookie-urile stocate pe client.

**21. What kind of HTTP status codes do you know?**

* [x] **Informational responses (100 – 199):**
  * **100 Continue:** Îndeamnă clientul să continue cu trimiterea corpului cererii (utilizat în cazul cererilor care au un corp mare).
  * **101 Switching Protocols:** Serverul înțelege și este pregătit să schimbe la protocolul clientului, de exemplu, la WebSockets.
* [x] **Successful responses (200 – 299):**
  * **200 OK:** Răspunsul standard pentru cererile reușite.
  * **201 Created:** Indică că o nouă resursă a fost creată ca rezultat al cererii.
* [x] **Redirection messages (300 – 399):**
  * **301 Moved Permanently:** Resursa solicitată s-a mutat permanent la o nouă adresă URL. Clientul ar trebui să refacă cererea la noua adresă. 
  * **302 Found (sau 302 Redirect):** Resursa solicitată se află temporar sub o altă adresă URL. Clientul poate continua să folosească adresa URL originală, deoarece redirecționarea este temporară. 
  * **304 Not Modified:** Utilizat pentru cache. Indică că resursa nu a fost modificată de la ultima solicitare și clientul poate folosi versiunea stocată în cache.
* [x] **Client error responses (400 – 499):**
  * **400 Bad Request:** Cererea nu a putut fi procesată din cauza unei erori de client (de exemplu, formatul cererii este greșit). 
  * **401 Unauthorized:** Cererea necesită autentificare. Acest cod este trimis când o cerere necesită autentificare și aceasta lipsește sau este invalidă. 
  * **404 Not Found:** Serverul nu a putut găsi resursa solicitată.
* [x] **Server error responses (500 – 599):**
  * **500 Internal Server Error:** O eroare generică, indicând că serverul a întâmpinat o situație pe care nu știe cum să o gestioneze. 
  * **503 Service Unavailable:** Serverul nu este disponibil temporar, de obicei din cauza suprasolicitării sau întreținerii.

**22. Elementele esențiale ale unei cereri HTTP sunt următoarele:**

* **Metoda HTTP:** Specifică tipul acțiunii solicitate pe server. Cele mai comune metode sunt GET (pentru a solicita date), POST (pentru a trimite date), PUT (pentru a actualiza date), DELETE (pentru a șterge date), și altele.
* **URL (Uniform Resource Locator):** Adresa resursei la care se face cererea. Include protocolul (de exemplu, http sau https), numele gazdei (host), calea resursei și, opțional, parametrii de interogare.
* **Path:** Partea specifică din URL care indică resursa dorită pe server. De exemplu, în https://example.com/api/users, calea este /api/users.
* **Query Parameters:** O parte opțională a URL-ului, folosită pentru a furniza informații suplimentare serverului. Acești parametri sunt atașați la sfârșitul URL-ului și sunt precedați de un semn întrebare (?). De exemplu, ?id=123.
* **Headers:** Fournizează informații suplimentare despre cerere, cum ar fi tipul de conținut (Content-Type), autentificarea (Authorization), și alte metadate. Ele sunt esențiale pentru configurarea corectă a cererilor și răspunsurilor HTTP.
* **Body:** Partea care conține datele efective trimise sau primite în cerere. Corpul este folosit în metodele POST și PUT pentru a trimite datele necesare serverului. În cererile GET, de obicei, nu există un corp.
* **Versiunea Protocolului HTTP:** Indică versiunea protocolului HTTP folosită pentru cerere, de exemplu, HTTP/1.1 sau HTTP/2.


**23. HTTP methods:**

**a. GET**
* Utilizare: Solicită o reprezentare a unei resurse specifice. Cererile folosind metoda GET ar trebui să fie doar pentru recuperare de date și nu ar trebui să afecteze starea resursei. 
* Exemplu: Accesarea unei pagini web sau a unei imagini.

**b. POST**
* Utilizare: Trimite date către server pentru a crea o nouă resursă. Datele sunt incluse în corpul cererii. Este folosită adesea pentru trimiterea de formulare web.
* Exemplu: Înscrierea unui utilizator nou, postarea unui comentariu pe un blog.

**c. PUT**
* Utilizare: Înlocuiește toate reprezentările curente ale resursei țintă cu datele încărcate.
* Exemplu: Actualizarea detaliilor unui utilizator.

**d. PATCH**
* Utilizare: Aplică modificări parțiale la o resursă. Spre deosebire de PUT, PATCH este folosit pentru actualizări parțiale.
* Exemplu: Actualizarea adresei de email a unui utilizator, fără a modifica alte informații.

**e. DELETE**
* Utilizare: Șterge o resursă specificată.
* Exemplu: Ștergerea unui articol de pe un blog.

**f. HEAD**
* Utilizare Detaliată: Metoda HEAD este folosită pentru a solicita anteturile care ar fi returnate dacă resursa specificată ar fi solicitată cu o cerere GET. Această metodă nu returnează un corp de răspuns, ceea ce o face utilă pentru obținerea metadatelor despre o resursă fără a descărca întreaga resursă.
* Exemplu Practic: Să presupunem că vrei să verifici dacă o imagine mare sau un document PDF există pe un server web și să afli dimensiunea acestuia fără a-l descărca. Ai putea trimite o cerere HEAD către URL-ul resursei. Răspunsul va include metadate precum Content-Type și Content-Length, permițându-ți să decizi dacă să descarci sau nu resursa completă.

**g. OPTIONS**
* Utilizare Detaliată: Metoda OPTIONS este utilizată pentru a afla ce metode HTTP sunt permise pentru o resursă specifică. Acest lucru este util pentru explorarea capabilităților serverului sau pentru verificarea permisiunilor pe o resursă.
* Exemplu Practic: Înainte de a face o cerere POST pentru a încărca date pe un server, un client ar putea trimite o cerere OPTIONS la același URL pentru a verifica dacă metoda POST este acceptată. Răspunsul va include un antet Allow care enumeră toate metodele HTTP permise pentru acea resursă.

**h. CONNECT**
* Utilizare Detaliată: Metoda CONNECT este utilizată pentru a deschide un tunel prin intermediul unui server proxy. De obicei, este folosită pentru a stabili o conexiune securizată prin un proxy HTTP.
* Exemplu Practic: Când un client HTTPS dorește să se conecteze la un site securizat prin intermediul unui proxy, acesta trimite o cerere CONNECT către proxy. Proxy-ul, la rândul său, stabilește o conexiune cu serverul țintă și, odată ce conexiunea este stabilită, traficul între client și serverul țintă trece prin proxy.

**i. TRACE**
* Utilizare Detaliată: Metoda TRACE este folosită pentru diagnosticarea conținutului cererilor HTTP în cadrul rețelei. Aceasta efectuează un apel de tip "loopback" al cererii primite, permițând clientului să vadă ce modificări sau adăugiri sunt făcute de servere sau proxy-uri.
* Exemplu Practic: Dacă suspectați că un server proxy modifică cererile în tranzit, puteți trimite o cerere TRACE către serverul țintă. Răspunsul va include exact corpul cererii așa cum a fost primit de serverul țintă, permitându-vă să vedeți ce, dacă ceva, a fost modificat de proxy.

**24. Metadatele:**

  **Tipuri de Metadate:**
* **Descriptive:** Ajută la identificarea, descoperirea și localizarea unei anumite resurse. Exemple includ titlul unui document, autorul, rezumatul și cuvintele cheie. 
* **Structural:** Acestea descriu cum sunt organizate datele. De exemplu, cum sunt organizate capitolele și secțiunile într-un document sau cum sunt structurate tabelele și coloanele într-o bază de date. 
* **Administrative:** Aceste metadate sunt legate de managementul și administrarea resurselor, cum ar fi drepturile de autor, restricțiile de acces și informațiile de versionare.


  **Exemple de Metadate:**
* **În Fotografii Digitale:** Informațiile EXIF dintr-o fotografie digitală sunt metadate. Ele pot include data și ora când a fost făcută fotografia, tipul aparatului foto, setările de expunere și chiar coordonatele GPS ale locației unde a fost făcută fotografia. 
* **În Documente:** Un document Word poate avea metadate care includ autorul, data ultimei modificări, numărul de cuvinte și alte detalii despre document. 
* **Pe Web:** În HTML, etichetele <meta> din secțiunea <head> a unei pagini web sunt metadate. Acestea pot oferi descrieri, cuvinte cheie sau informații despre autor, care ajută motoarele de căutare să înțeleagă și să clasifice conținutul paginii. 
* **În Baze de Date:** Metadatele pot include schemele de tabel, tipurile de date ale coloanelor, constrângeri, relații între tabele și alte informații structurale. 
* **În Software și Aplicații:** Versiunea unui software, dependențele sale, autorul și licența sunt toate forme de metadate.


  **Importanța Metadatelor:**

* Metadatele sunt esențiale pentru gestionarea, organizarea și găsirea eficientă a informațiilor în lumea digitală. Ele permit utilizatorilor și sistemelor informatice să înțeleagă contextul și conținutul datelor fără a fi necesar să acceseze datele în sine. În plus, sunt cruciale pentru securitate, conformitate și arhivare în multe domenii, inclusiv în managementul documentelor, biblioteci digitale și arhive.

**25. HTML Behaviour:**
* **Form submit:**

```
<from action="/submit-form" method="post">
  <input type="text" name="username">
  <input type="password" name="password">
  <input type="submit" value="Submit">
</form>
```

* Când utilizatorul apasă pe butonul de submit, formularul trimite datele (în acest caz, username și password) către server la URL-ul specificat în atributul action folosind metoda HTTP specificată (în acest caz, post). Browserul va naviga automat către noua adresă, care poate conduce la reîncărcarea paginii sau la navigarea către o nouă pagină.

* **preventDefault:**

  * **Oprirea Comportamentului Implicit:** Prin apelarea preventDefault() într-un handler de evenimente, aceste acțiuni implicite sunt anulate.
  * **Nu Oprirea Propagării Evenimentului:** Este important de remarcat că preventDefault() nu oprește propagarea evenimentului. Adică, evenimentul continuă să se propage în arborele DOM. Pentru a opri propagarea, trebuie să folosiți stopPropagation() sau stopImmediatePropagation().
  * **Concluzie:** preventDefault este o modalitate puternică în JavaScript de a controla și personaliza comportamentul implicit al elementelor HTML, oferind dezvoltatorilor flexibilitatea de a implementa comportamente personalizate, cum ar fi validarea formularului pe partea clientului, trimiterea datelor prin AJAX și multe altele.

**26. Cum Funcționează AJAX?**

* Un Eveniment pe Pagina Web: O acțiune realizată de utilizator (cum ar fi apăsarea unui buton) declanșează o cerere AJAX.
* JavaScript Creează Cererea: JavaScript-ul folosește obiectul XMLHttpRequest (sau în cazuri moderne, API-ul fetch) pentru a crea o cerere către server.
* Trimiterea Cererii: Cererea este trimisă către server asincron. Pagina web nu se reîncarcă în timpul acestui proces.
* Procesarea Cererii de către Server: Serverul procesează cererea și trimite înapoi un răspuns.
* Răspunsul Serverului: Răspunsul este primit de JavaScript, care apoi poate actualiza dinamic conținutul paginii web fără a necesita o reîncărcare completă.
* Actualizare Pagină Web: Pagina web este actualizată cu noile date. Aceasta poate include actualizarea elementelor HTML, afișarea unor noi informații, modificarea stilurilor etc.

**Exemplu de Utilizare AJAX:**

* Să presupunem că ai un formular pe pagina ta web pentru a căuta informații despre un utilizator. În loc să trimiți formularul în mod tradițional și să reîncarci pagina, folosești AJAX pentru a trimite cererea.
* În acest exemplu, informațiile despre utilizator sunt cerute asincron și pagina este actualizată cu aceste informații fără a fi nevoie de reîncărcarea paginii.

**Concluzie**

* AJAX a revoluționat dezvoltarea web, permițând dezvoltatorilor să creeze experiențe de utilizator mai bogate și mai interactive. Este un instrument fundamental în multe aplicații web moderne, contribuind la fluiditatea și rapiditatea interfețelor utilizator.

**27. Why should you ignore the `node_modules` folder in `.gitignore` ?**

* It is better to put the `node_modules` folder in the `.gitignore` file because it gets too much space from the Git repository (the folder has a large size). It is enough to have them in the "package.json" so that you can use npm install and get them again when you need them. Also, it is better for the security of the project to include the "node_modules" in the ".gitignore" file.

### Rest API: Serve and Fetch

**28. Ce este un fetch?**

* API-ul fetch este o interfață modernă în JavaScript care permite efectuarea cererilor HTTP asincrone. Este un mod de a cere resurse de pe rețea, cum ar fi documente HTML, fișiere JSON, imagini etc. Este considerat un înlocuitor mai puternic și mai flexibil pentru XMLHttpRequest, oferind o sintaxă mai simplă și bazată pe promisiuni.

**29. Cum Funcționează API-ul Fetch?**

* **Cereri Asincrone:** fetch permite efectuarea cererilor asincrone în rețea. Aceasta înseamnă că poți trimite o cerere pentru a aduce date de la un server și procesa răspunsul fără a bloca restul codului tău sau a reîncărca pagina. 
* **Promisiuni:** API-ul fetch utilizează promisiuni, ceea ce înseamnă că gestionează operațiuni asincrone mai eficient. O promisiune este un obiect care reprezintă finalizarea sau eșecul unei operațiuni asincrone și valoarea ei rezultată.

**30. Exemplu de Cerere Fetch:**

* Să presupunem că vrei să obții date JSON de la un server:

```
fetch('https://example.com/data', options)
  .then(response => {
    if (!response.ok) {
      throw new Error('Network response was not ok');
    }
    return response.json();
  })
  .then(data => {
    console.log(data);
  })
  .catch(error => {
    console.error('There has been a problem with your fetch operation:', error);
  });
```
* **Initializarea cererii:**
  * **Apelul Fetch:** Se face o cerere fetch către https://example.com/data. 
  * **"options":** Poți de asemenea să specifici opțiuni suplimentare, cum ar fi metoda HTTP (GET, POST etc.), anteturile, corpul cererii și altele. Un obiect opțional care specifică diferite setări pentru cerere, cum ar fi metoda, anteturile, corpul etc.
* **Procesarea Răspunsului:**
  * **Promisiuni:** fetch returneaza o promisiune. Promisiunile sunt folosite pentru a gestiona operațiuni asincrone. O promisiune are trei stări: pending (în așteptare), fulfilled (îndeplinită) și rejected (respinsă).
  * **Gestionarea Răspunsului:** După ce cererea este trimisă, următorul pas este să procesezi răspunsul. Folosești .then() pentru a specifica ce să faci odată ce promisiunea este îndeplinită (adică când răspunsul este primit de la server).
  * **Verificarea Stării Răspunsului:** Verifici dacă răspunsul este OK (de exemplu, codul de stare HTTP este 200). Dacă nu, poți arunca o eroare pentru a intra în blocul .catch() pentru gestionarea erorilor.
  * **Conversia Răspunsului:** De obicei, convertim răspunsul în formatul adecvat, cum ar fi JSON, folosind response.json(). Alte metode includ response.text(), response.blob() etc., în funcție de tipul de date pe care îl aștepți.
* **Utilizarea Datelor Răspunsului:**
  * **Al Doilea .then():** După ce răspunsul este convertit (de exemplu, în JSON), poți folosi un alt .then() pentru a lucra cu acele date. Datele JSON sunt apoi afișate în consolă. 
* **Gestionarea Erorilor:**
  * **Blocul .catch():** La sfârșit, adaugi un .catch() pentru a prinde orice eroare care ar putea apărea în timpul cererii sau procesării datelor. Orice eroare în cerere sau în procesarea răspunsului este prinsă și afișată în consolă.

```
fetch('https://example.com/data', { method: 'GET' })
  .then(response => {
    if (!response.ok) {
      throw new Error('Network response was not ok');
    }
    return response.json();
  })
  .then(data => {
    console.log(data);
  })
  .catch(error => {
    console.error('Fetch error:', error);
  });
```
* **Concluzie:**
  * Procesul fetch implică trimiterea cererii GET la URL-ul 'https://example.com/data'
  * procesarea răspunsului asincron
  * folosirea datelor primite
  * gestionarea erorilor.
  * Este o abordare modernă și puternică pentru lucrul cu cereri și răspunsuri HTTP în JavaScript, oferind o modalitate elegantă și eficientă de a interacționa cu servere și servicii web.

**31. FETCH vs XMLHttpRequest:**

* 


**21 Why is it recommended for a developer to use the http methods `get`, `put`, `delete`?**

* HTTP methods are secure and efficient ways to work with data on a server.
* We use the `GET` method to retrieve data.
* We use the `PUT` (or `PATCH`) method to update data.
* We use `DELETE` method to delete data.

**22 How does a `POST` request look like when it is made from a web browser (on the frontend written)?**

:black_nib:
```
<form method="POST" action="/submit-form">
  <label for="name">Name:</label>
  <input type="text" id="name" name="name"><br>

  <label for="email">Email:</label>
  <input type="email" id="email" name="email"><br>

  <label for="message">Message:</label>
  <textarea id="message" name="message"></textarea><br>

  <button type="submit">Submit</button>
</form>
```
**23 What is an API?**

* API (Application Programming Interface) is a set of definitions, protocols, routines and tools for building and integrating application software (source: `Redhat.com`).
* According to `Ibm.com`, an application programming interface is a set of rules that define how applications or devices can connect and communicate with each other.

**24 What is REST API?**

* REST APIs or RESTful APIs follow the principles and procedures of the Representational State Transfer architectural style for web services.
* The client (browser/ device) communicates with the server (application/ service) in a flexible and standardized way, using almost any programming language and data formats.

**25 What is JSON and how do we use it?**

* JavaScript Object Notation (JSON) is a text-based way of representing JavaScript object literals, arrays, scalar data (source: `Oracle.com`).
* JSON format is both easy for humans to read and write and for the machines to parse and generate, and it can be used with any programming language.
* In order to use JSON, we convert data from the programming language that we use into JSON string or data structure, with the help of a JSON encoder, and we store it into a file.

**26 What is API versioning?**

* API versioning allow developers to make changes to an API without breaking the clients' apllications that rely on that API.
* The changes can be integrated in URL versioning (include change in API Url), query versioning (include change in API parameter), header versioning (include change in header) and media type versioning (include change in media type of response).

**27 Give 3 examples of HTTP response status codes. Explain what each number means.**

* From 201 to 299: message indicates succes in retrieving the data. Example: `200 OK`.
* From 401 to 499: message indicates error on client side and that the server is unable to find the requested data. Example: `404 not find`.
* From 501 to 599: message indicates error on server side. Example: `500 Internal Server Error`.

### Advanced JavaScript

**28 How does the `ternary operator` looks like in javascript?**

* According to MDN (`developer.mozilla.org`), the conditional (ternary) operator is the only JavaScript operator that takes three operands: a condition followed by a question mark (?), then an expression to execute if the condition is truthy followed by a colon (:), and finally the expression to execute if the condition is falsy.

:black_nib:

`condition ? expression1 : expression2`

**29 How to import a function from another module in JavaScript?**

* We can use `import` statement to import a function from another module (from which we export the function using the `export` statement).

:black_nib: Example from `Stackoverflow.com`:
* models/course.js
```
export function Course() {
    this.id = '';
    this.name = '';
};
```
* models/student.js
```
import { Course } from './course.js';

export function Student() {
    this.firstName = '';
    this.lastName = '';
    this.course = new Course();
};
```
* index.html
```
<div id="myDiv">
</div>
<script type="module">
    import { Student } from './models/student.js';

    window.onload = function () {
        var x = new Student();
        x.course.id = 1;
        document.getElementById('myDiv').innerHTML = x.course.id;
    }
</script>
```

**30 What is a shallow copy on an object?**

* A shallow copy (or shallow clone) of an object can be created with the spread operator (`...`) and it will generate a new object which properties will use the same memory space as the ones of the original object. This way, if we change a property value of the copy we also change the property value of the original.
* Another way to create a shallow clone is with `Object.assign()` or `slice()`.
* In order to create a copy that doesn't use the same memory space, we need to create a deep copy (deep clone), using the `JSON.parse()` and `JSON.stringify` methods.

**31 What is a callback function? Tell some examples of its usage.**

* I already gave an example at :question:1

* In JavaScript, a callback function is a function that is passed as an argument to another function, and is executed when a certain event or action occurs. The main purpose of a callback function is to allow a function to be more flexible and reusable, by allowing different behaviors to be passed as arguments.

:black_nib: Example:
```
document.querySelector('button').addEventListener('click', function() {
  // Do something when the button is clicked
});
```

```
const numbers = [1, 2, 3, 4, 5];

const doubledNumbers = numbers.map(function(number) {
  return number * 2;
});

console.log(doubledNumbers);
```

**32 What is object destructuring in JavaScript?**

* According to `Tutorialspoint.com`, JavaScript Object Destructuring is an expression which allows us to access the data from objects and assign it to new variables. Through this object destructuring, we can create variables easily from the object’s properties.

* Syntax:
```
const [a,b] = array;
const [a,b…t] = array;

const {a:a1,b:b1} = obj;
const {a:a1, b:b1,…..t:t1} = obj
```

:black_nib: Example:
```
const person = {
  name: 'John Doe',
  age: 30,
  address: {
    street: '123 Main St',
    city: 'Anytown',
    state: 'CA',
    zip: '12345'
  }
};

// Extract properties using destructuring
const { name, age, address: { city } } = person;

console.log(name);  // 'John Doe'
console.log(age);   // 30
console.log(city);  // 'Anytown'
```

**33 What is array destructuring in JavaScript?**

* With the help of array destructuring we can extract element from an array and assign them to new variables at the same time.

:black_nib: Example:
```
const array = [1,2,3,4,5];
const [a,b] = array; // a : 1 , b :2 (values of a,b)
```

**34 What is the spread operator in `js`?**

* The spread operator (`...`) allows us to create a shallow copy of an array or object or iterable at at the same time to expand it in individual elements.

:black_nib: Example:
```
const numbers = [1, 2, 3, 4, 5];

function sum(a, b, c, d, e) {
  return a + b + c + d + e;
}

const result = sum(...numbers);

console.log(result); 
```

**35 What are the differences between the `arrow` function and the regular `function`?**

|          **Differences**         |                                                     **Arrow function**                                                    |                                             **Regular function**                                             |
|:--------------------------------:|:-------------------------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------:|
|            **Syntax**            | const arrowFunction = (x, y) => {return x+y};<br>or, also possible and even better:<br>const arrowFunction =(x,y) => x+y; | function regularFunction (x, y){<br>return x+y;}                                                             |
|       **Arguments binding**      | No argument binding.                                                                                                      | Yes.<br>let myFunction(){<br>showArgs(){<br>console.log(arguments)<br>}<br>}<br>myFunction.showArgs(1,2,3,4) |
| **Acceptance of "this" keyword** | No.                                                                                                                       | Yes.                                                                                                         |
|      **Acceptance of "new"**     | No.                                                                                                                       | Yes.                                                                                                         |
|     **Duplicate parameters**     | Never.                                                                                                                    | Only in non-strict mode.                                                                                     |

**36 What is the `import` keyword used for?**

* The `import` keyword is used to include external modules or dependencies into a JavaScript file in frontend.

**37 What is the `require` used for?**

The `require` keyword is used to include external modules or dependencies into a JavaScript file in backend.

**38 What are template literals?**

* Template literals (template strings) allow us to embed expressions and variables inside a string using backticks instead of single or double quotes.

### Testing basics

**39 What is code coverage? Why is it used?**

* Code coverage indicates the proportion of lines, functions and branches of the code that were covered by a test. It helps to measure how much of the code has been tested.

**40 What is a test case? What is an assertion? Give examples!**

* A test case is a scenario that defines the input values, expected output, and any other relevant conditions or requirements for a test.
* An assertion is a statement that checks whether an expected condition is true or false.

:black_nib: Example:

```
Test Case:
A login form that accepts a username and password.

Assertions:

When the correct username and password are entered, the user should be logged in successfully.
When an incorrect username or password is entered, the user should not be logged in.
When the login form is submitted without any input, an error message should be displayed.
```

**41 What are the unit testing best practices? (Eg. how many assertion should a test case contain?)**

:black_nib: Some rules to follow:

* [x] include a single assertion in one test method (test one thing at a time; one assertion per test case)
* [x] use clear test cases
* [x] run tests frequently
* [x] write tests during development


**42 What is arrange/act/assert pattern?**

* The Arrange-Act-Assert (AAA) pattern is used in unit testing to structure and organize test cases.

**43 How do you test asynchronous code with `jest` ?**

* We can test asynchronous with `jest` using:
* [x] `done()`
* [x] `promises`
* [x] `async/ await`
* [x] `done()` + `async/ await`

**44 What is `setup` & `teardown` in jest?**

* In `jest`, `setup` and `teardown` are functions that we can use to define actions to be performed before and after running every test.

**45 Give an example when you would use in `jest` the `toBe` & `toEqual` assertions.**

* The `toBe` assertion tests for strict equality between two values.

:black_nib: Example:
```
test('addition works correctly', () => {
  expect(3 * 3).toBe(9);
});
```

* The `toEqual` assertion, on the other hand, tests for deep equality between two values.

:black_nib: Example:
```
test('objects are equal', () => {
  const obj1 = { foo: 'bar', baz: 3000 };
  const obj2 = { foo: 'bar', baz: 3000 };
  expect(obj1).toEqual(obj2);
});
```

### React basics

**46. React Fragments:**

* **Definition:** React Fragments sunt o caracteristică utilă în biblioteca React, care permite gruparea mai multor elemente JSX fără a adăuga noduri suplimentare în DOM (Document Object Model).
* **Sintaxă:** Există două moduri principale de a utiliza Fragments:
  * Sintaxa scurtă: <>...</>, care este cea mai simplă și mai curată formă.
  * Sintaxa extinsă: <React.Fragment>...</React.Fragment>, care este utilă atunci când este nevoie să adăugați atribute, cum ar fi key în cazul listelor.
* **Avantaje:**
  * Performanță: Reducerea numărului de noduri din DOM poate îmbunătăți performanța, deoarece fiecare nod suplimentar poate adăuga complexitate și poate încetini procesarea DOM.
  * Curățenie în Cod: Utilizarea Fragments ajută la menținerea unui cod mai curat și mai lizibil, evitându-se îngrămădirea cu <div>-uri inutile.
  * Menținerea Structurii CSS: Uneori, adăugarea unor elemente <div> suplimentare poate perturba structura și stilul CSS existent. Fragments elimină această problemă.

**46 What benefits does it bring for a developer to use `components` (opposed of writing all the code in a single file)?**

* Some benefits of using components instead of writing all code in one place:
* [x] code is more suple and easy to follow
* [x] it is easier to test/ debug the code
* [x] it is easier to re-use the code
* [x] it is easier to collaborate
* [x] makes things more clear and helps the logic
* [x] it is easier to make changes in the code

**47 What is the difference between Element and Component?**

* Usually, an element refers to a HTML tag, whistl a component is more complex and dynamic and encapsulates more elements.

**48 How do you pass values between components in `react`?**

* To pass values between components in React, we can use:
* [x] props
* [x] useContext
* [x] specific libraries
* [x] event handling

**49 What is `key` prop?**

* When working with a list and using `.map()` we need to include a key so that React keeps track more efficiently of what we changed, added or deleted from the list.

:black_nib: Example:

```
function MyList(props) {
  const items = props.data.map((item) => (
    <li key={item.id}>
      {item.name}
      <ul>
        {item.children.map((child) => (
          <li key={child.id}>{child.name}</li>
        ))}
      </ul>
    </li>
  ));
  return <ul>{items}</ul>;
}
```

**50 How does a child component pass data to it's parent component?**

* To pass data from a child component to its parent component, we can use props or useContext.

**51 Write the code to create in JSX an HTML DIV element that has the innerText the contents of the variable `let name = 'Andrew'`**

:black_nib: Example:

```
import React from 'react';

function MyComponent() {
  let name = 'Andrew';

  return (
    <div>{name}</div>
  );
}

export default MyComponent;
```

**52 Write the code to create in JSX an unordered list from the array `let names = ["Mathew", "John", "Maverik"]`**

:black_nib: Example:
```
import React from 'react';

function MyComponent() {
  let names = ["Mathew", "John", "Maverik"];

  return (
    <ul>
      {names.map((name) => (
        <li key={name}>{name}</li>
      ))}
    </ul>
  );
}

export default MyComponent;
```

**53 Write the code to set the background color red of a div in JSX.**

:black_nib: Example:
```
import React from 'react';

function MyComponent() {
  return (
    <div style={{ backgroundColor: 'red' }}>Hello, world!</div>
  );
}

export default MyComponent;
```

### Testing react

**54 What are unit tests, integration tests? What is the major difference between these two?**

* Unit tests are used to test a single unit or function of an application.
* Integration tests are used to test the interaction between different parts of an application.

**55 What is unit testing?**

* Unit testing is designed to test individual units or components, isolated from the rest of the application.

**56 What does `mocking` mean from a testing perspective? Give an example when you would use it.**

* When testing, mocking means to create a simulated version for the data that the code we want to test relies on.
* A frequent example of recently used mocking was to add data to see it create-read-update-delete operations work as expected.

**57 How do you test that function was called `at least` 2 times using `jest`?**

:black_nib: Example:
```
function myFunction() {
  // ...
}

// Test case
test('myFunction is called at least 2 times', () => {
  // Call the function twice
  myFunction();
  myFunction();

  // Assert that the function was called at least 2 times
  expect(myFunction).toHaveBeenCalledTimes(2);
  expect(myFunction).toBeGreaterThanOrEqual(2);
});
```

**58 Name 4 benefits a developer gets from writing tests.**

:black_nib: Some benefits for a developer to write tests:

* [x] catch and prevent bugs
* [x] better structure the code
* [x] prevent isssues in an early stage

### React patterns

**59 What is the difference between Real DOM and Virtual DOM?**

| **Differences** |                       **Real DOM**                       |                      **Virtual DOM**                      |
|:---------------:|:--------------------------------------------------------:|:---------------------------------------------------------:|
|        1        | Represents the current stage of the web page.            | Represents a copy of the Real DOM that was stored.        |
|        2        | Can change on-screen elements.                           | Cannot change on-screen elements.                         |
|        3        | Any change updates the entire DOM structure.             | Any change only updates the relevant node.                |
|        4        | Slow update.                                             | Fast update.                                              |
|        5        | Browser re-renders the entire page to reflect an update. | Framework updates only the changed parts of the Real DOM. |

**60 When adding an item to an array, why is it necessary to pass a new array to the `useState` hook?**

* When we update an array, the state variable is updated too and a new copy of the variable is created instead of changing the original, in order to be able to re-render the component.

**61 Describe what techniques or tools you use to debug a react app.**

:black_nib: Techniques and tools that we use to debug a React application:
* [x] add console.log() statements everytime we need
* [x] use browser's debugger
* [x] use VSC debugger
* [x] get help from colleagues and mentors

**62 What is the difference between a react `class` component & a `functional` component?**

* A functional component is an easy to read, write and test component that consists of a function where we can use React hooks (useState, useEffect).
* A class component usses `class` keyword and extends `React.Component` and uses render() method.

**63 Name 3 lifecycle states in a react `functional` component.**

:black_nib: Three lifecycle states in a React functional component:
* [x] useState
* [x] useEffect
* [x] useContext

**64 What is conditional rendering in `react` ? Give an example.**

* Conditional rendering means to render different parts of the code based on certain conditions.

:black_nib: Example from `legacy.reacjs.org`:
```
render() {
  const count = 0;
  return (
    <div>
      {count && <h1>Messages: {count}</h1>}
    </div>
  );
}
```

**65 Write the code that prints to the console `component destroyed` when the component it is part of is removed from the DOM tree.**

```
import React, { useEffect } from 'react';

function DestroyedComponent() {
  useEffect(() => {
    return () => {
      console.log('component destroyed');
    };
  }, []);

  return (
    <div>
      <h1>Destroyed component</h1>
      <p>This is my component</p>
    </div>
  );
}

export default DestroyedComponent;
```

**66 Why is there an infinite loop in this code?**

```function App() {
  const [count, setCount] = useState(0); //initial value of this 
  useEffect(() => {
    setCount((count) => count + 1); //increment this Hook
  }); //no dependency array.

  return (
    <div className="App">
      <p> value of count: {count} </p>
    </div>
  );
}
```
* The useEffect hook should have a dependency array, in this case [count], in order to only render when the count is changed.

**67 Why is there an infinite loop in this code?**

```
  async function App() {
  const [count, setCount] = useState("");
  setCount(count + 1);
  return (
    <div className="App">
      <p> value of count: {count} </p>
    </div>
  );
}
```
* The first problem is that the initial state of the useState hook is set to a string, which is not correct for a count (should be a number or should be set to 0 or null).
* Another problem is that the setCount should depend on a function or a button handler or a condition - so that we know when to increment the count.
* Also, it is enough to write count++ instead of count+1.

:black_nib: The reviewed version for the code should be something like this:
```
function App() {
  const [count, setCount] = useState(0);

  const incrementCount = () => {
    setCount(count + 1);
  };

  return (
    <div className="App">
      <p> value of count: {count} </p>
      <button onClick={incrementCount}>Increment</button>
    </div>
  );
}
```

### Mongo & mongoose

**68 What is a database schema?**

* A database schema in MongoDB describes the structure of data and specifies hot to store the data, what type is the data and so on.

**69 Why is the `id` unique in a database?**

* Every ObjectId in MongoDB is generated automatically and is unique, because the `_id` field is the primary key for each document, in order to efficiently retrieve the document from a collection.

**70 What are the advatanges & disadvatages of using `lean()` function in a mongo query?**

| **lean() method in Mongoose** |   **Advantages**   |   **Disadvantages**   |
|:-----------------------------:|:------------------:|:---------------------:|
|               1               | faster             | limited functionality |
|               2               | use less memory    | no schema validation  |
|               3               | better performance | no data manipulation  |

**71 Write the code to store the object `{name: "Andrew", age: 10}` to a mongo database. You can ignore the part of connection parameters.**

```
const mongoose = require('mongoose');

const personSchema = new mongoose.Schema({
  name: String,
  age: Number
});

const Person = mongoose.model('Person', personSchema);

// Connect to the database (you can ignore the connection parameters)
mongoose.connect('mongodb://localhost/...');

// Create a new user object
const person = new Person({
  name: 'Andrew',
  age: 10
});

// Save the user to the database
person.save((err, person) => {
  if (err) {
    console.error(err);
  } else {
    console.log(`User ${person.name} saved to the database.`);
  }
});
```

**72 Write the code to delete from a mongo database all employees that are over 18 years. The scheme for an employee is `{name: string, age: int}`. You can ignore the part of connection parameters.**

```
db.employees.deleteMany({age: {$gt: 18}})  // $gt means greater than
```

**73 Write the code to display in the console from a mongo database the employees who are over 18 years. The scheme for an employee is `{name: string, age: int}`. You can ignore the part of connection parameters.**

```
db.employees.find({age: {$gt: 18}}).forEach(function(employee) {
  print(employee.name + " is over 18 years old");
})
```

**74 Write the code to update from a mongo database the employees with name='John' and set the new age to 8. The scheme for an employee is `{name: string, age: int}`. You can ignore the part of connection parameters.**

```
db.employees.updateMany({name: "John"}, {$set: {age: 8}})
```

### Authentication (cookies + google)

**75 How to properly store passwords?**

* Passwords should not be stored in plain text, but should be stored in a database after being encrypted by a reversible algorithm (source: `Vaadata.com`).

**76 What are encryption and decryption?**

* Encryption transforms a readable text into an unreadable form to prevent third-parties from reading it. (plaintext => encrypted text = cipher text)

* Decryption transforms the encrypted text back into readable form. (encrypted text => plain text)

**77 What is hashing?**

* Hashing is a technique generally used in cryptography to secure data by transforming it into a hash value/ digest that ususally is a fixed-size string of characters or numbers.

**78 What is OAuth2?**

* OAuth2 (Open Authorization 2.0) is a standard meant to allow third-party websites or applications to access protected data from another web app on behalf of a user, without having access to the user's credentials.

**79 What is the difference between encryption and hashing? When would you use which?**

* According to `EncryptionConsulting.com`, encryption is a two-way function where data is passed in as plaintext and comes out as ciphertext, which is unreadable. Since encryption is two-way, the data can be decrypted so it is readable again. Hashing, on the other hand, is one-way, meaning the plaintext is scrambled into a unique digest, through the use of a salt, that cannot be decrypted.
* We use encryption to protect confidentiality of data and we use hashing to protect integrity of data (detect unauthorized changes).

**80 How/where would you store sensitive data (like db password, API key, ...) of your application?**

:black_nib: Some ways to store sensitive data:

* [x] hidden in the project code

* [x] in path for environmental variables that are set outside the app code

* [x] hidden in configuration files

* [x] encrypted - stored in a database and store the encyption key separately (in a key vault)

* [x] key vaults (secret stores) on cloud


**81 What would you use a session for?**

* According to `W3schools.com`, a session is a way to store information (in variables) to be used across multiple pages. Unlike a cookie, the information is not stored on the users computer.

**82 What would you use a cookie for?**

* Cookies are used to store data about user's preferences or login credentials. There are generally two kinds of cookies: "persistent" cookies and "session" cookies. Some of the cookies purposes are: session management, personalization, analytics, advertising.

### Mern stack

**83 What does `MERN` stand for in the context of web development?**

* MERN stands for Mongoose-Express-React-Node.

**84 What is routing in the context of a `react` app?**

* In the context of React, routing means to determine what should be displayed in a given URL path.

**85 What is routing in the context of an `express` app?**

* In the context of Express, routing means to determine which server-side function should handle a specific HTTP request using a HTTP method.

**86 What is `CORS` policy?**

* CORS (Cross-Origin Resource Sharing) policy is a security mechanism designed to prevent malicious scripts from stealing or manipulating data from sites.

```
app.use((req, res, next) => {
  res.setHeader('Access-Control-Allow-Origin', '*');
  res.setHeader('Access-Control-Allow-Methods', 'GET, POST, PUT, DELETE');
  res.setHeader('Access-Control-Allow-Headers', 'Content-Type');
  next();
});
```

**87 What advantages does a developer have for using `bootstrap` or `material ui`?**

* Using `bootstrap` or `material ui` helps developers save time, because they don't have to write the code from scratch using HTML, JS and CSS. Also, this helps maintain a consistent user interface across the application. Another advantage is that it is easy to adapt the interface to different devices and gadgets (tablet, mobile, pc, etc). 
