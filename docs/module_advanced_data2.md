# Advanced Data module

## General SQL

### What are relational databases? Explain the theory behind them!

Bazele de date relaționale sunt sisteme de gestionare a bazelor de date care sunt organizate în tabele cu rânduri și
coloane, iar relațiile dintre tabele sunt gestionate prin primary și foreign keys. Această structură permite
gestionarea eficientă a datelor și realizarea de operațiuni complexe asupra acestora.

### Why SQL is important these days?

Este important în zilele noastre deoarece oferă o modalitate standardizată și puternică de a interacționa cu bazele de
date. Cu ajutorul SQL, putem să extragem, să inserăm, să actualizăm și să ștergem date în bazele de date, ceea ce este
esențial în dezvoltarea de aplicații, analiza datelor și luarea deciziilor bazate pe date. SQL este folosit pe scară
largă în industrie, iar cunoașterea sa este esențială pentru dezvoltatori, analiști de date și profesioniști IT.

### All the new GUI tools enable me to click a button to write SQL. Why should I spend time learning to write SQL manually?

Învățarea să scrii SQL manual are mai multe avantaje:

Control mai mare si Flexibilitate: Scriind SQL manual, ai control total asupra operațiunilor pe care le efectuezi în
baza de date,poți realiza interogări personalizate și complexe, adaptate nevoilor tale specifice.

Înțelegere mai profundă: Învățarea SQL îți permite să înțelegi mai bine cum funcționează bazele de date, ceea ce te
ajută să optimizezi și să depanați interogările.

Portabilitate: Cunoștințele de SQL sunt portabile și pot fi aplicate pe diferite Sisteme de Gestionare a BD, nu doar pe
un anumit software

### If SQL is standardized, should you be able to program with SQL on any databases?

Deși SQL este standardizat, există diferențe semnificative între diferitele sisteme de gestionare a bazelor de date în
implementarea specifică a standardului. Aceste diferențe pot afecta portabilitatea codului SQL între diverse
SGBD. Cu toate acestea, majoritatea interogărilor SQL standard pot fi adaptate pentru a funcționa pe mai multe
platforme, dar este important să ții cont de particularitățile fiecărui oftware.

### What makes SQL a nonprocedural language?

SQL este considerat un limbaj nonprocedural deoarece într-o interogare SQL, se specifică ce date să fie returnate și nu
cum să fie obținute acele date. În loc să definim pașii detaliați pentru a obține un rezultat, specificăm condițiile și
relațiile pe care dorim să le aplicăm datelor. Motorul de bază de date decide cum să execute interogarea în cel mai
eficient mod, fără a necesita o abordare strict procedurală din partea dezvoltatorului.

### What can you do with SQL?

Cu SQL, poți realiza următoarele acțiuni:

Extrage date dintr-o bază de date (SELECT).
Inserezi noi înregistrări într-o bază de date (INSERT).
Actualizezi date existente într-o bază de date (UPDATE).
Ștergi înregistrări dintr-o bază de date (DELETE).
Creezi, modifici sau ștergi structuri de bază de date, cum ar fi tabele, indecși și restricții (DDL - Data Definition
Language).
Realizezi operații de agregare, filtrare și sortare a datelor pentru analiza și raportarea acestora.
SQL este un limbaj puternic pentru gestionarea datelor în bazele de date relaționale și este utilizat pe scară largă în
dezvoltarea software și analiza datelor.

---

## DQL

### Do the following statements return the same or different output? Why?

```sql
SELECT *
FROM CHECKS;
select *
from checks;
```

SQL returnează același rezultat deoarece este în general insensibil la majuscule/minuscule în ceea ce privește numele de
tabele și coloane

### The following queries do not work when entered into the command line psql console. Why not?

```sql
Select *
Select *
from checks
Select amount name payee
FROM checks;
```

Interogările nu funcționează deoarece nu sunt terminate corespunzător cu punct și virgulă (;) și nu sunt scrise cu
litere mici (SELECT, nu Select). Interogările trebuie să fie scrise corect și să fie separate cu punct și virgulă pentru
a fi interpretate corect de consola psql.

### What shorthand could you use instead of `WHERE a >= 10 AND a <=30`?

WHERE a BETWEEN 10 AND 30

### Which function capitalizes the first letter of a character string and makes the rest lowercase?

INITCAP()

### Will this query work? Why?

```sql
SELECT COUNT(LASTNAME)
FROM CHARACTERS;
```

ar trebui să funcționeze dacă coloana LASTNAME există în tabelul CHARACTERS. Ea va număra numărul de înregistrări în
care coloana LASTNAME are valori ne-nule. Cu toate acestea, dacă coloana nu există sau are un alt nume în tabel, atunci
interogarea va da eroare.

### Assuming that they are separate columns, which function(s) would splice together FIRSTNAME and LASTNAME?

Pentru a combina FIRSTNAME și LASTNAME, trebuie sa utilizam funcția CONCAT(FIRSTNAME, ' ', LASTNAME)

### Why are so few functions defined in the ANSI standard and so many defined by the individual implementations?

Standardul ANSI SQL definește funcții fundamentale pentru portabilitate între diferite baze de date, dar multe baze de
date oferă funcționalități specifice și extensii pentru a satisface nevoile specifice ale dezvoltatorilor. Aceste
extensii sunt un mod de a oferi funcționalități suplimentare și de a face bazele de date mai puternice și mai flexibile.

### What is the function of the GROUP BY clause?

GROUP BY este utilizată pentru a grupa rezultatele unei interogări în funcție de valori comune dintr-o coloană sau mai
multe coloane. Ea este adesea folosită cu funcții de agregare, cum ar fi SUM, COUNT, AVG, pentru a efectua calcule pe
grupurile de date.

### When using the HAVING clause, do you always have to use a GROUP BY also?

Da, când folosești clauza HAVING, este necesar să folosești și clauza GROUP BY. Clauza HAVING este utilizată pentru a
aplica o condiție de filtrare asupra grupurilor create cu ajutorul GROUP BY. Dacă nu există o clauză GROUP BY, nu există
grupuri pe care să aplici condiția din HAVING.

### Can you use ORDER BY on a column that is not one of the columns in the SELECT statement?

Da, poți utiliza ORDER BY pe o coloană care nu este selectată în clauza SELECT. Acest lucru este util atunci când
dorești să ordonezi rezultatele în funcție de o altă coloană din tabel sau când dorești să ordonezi rezultatele în
funcție de o expresie calculată în interogare.

---

## Joins

### Explain the different kind of joins! (outer, inner, left, right, natural, etc.)

- Inner Join (Join Intern): Returnează numai datele care au corespondență în ambele tabele.
- Left Join (Join Stânga): Returnează toate înregistrările din tabela din stânga și numai înregistrările corespunzătoare
  din tabela din dreapta.
- Right Join (Join Dreapta): Este opusul Left Join, returnând toate înregistrările din tabela din dreapta și numai
  înregistrările corespunzătoare din tabela din stânga.
- Full Outer Join (Join Extern Complet): Returnează toate înregistrările din ambele tabele, asociația înregistrărilor
  neexistente cu NULL.
- Natural Join (Join Natural): Returnează înregistrările în care coloanele cu același nume din ambele tabele au valori
  egale.

### How many tables can you join on?

Este posibil să faci join pe câte tabele dorești, specificând condițiile adecvate de asociere între ele.

### Would it be fair to say that when tables are joined, they actually become one table?

Nu, atunci când faci join între tabele, ele rămân entități separate, dar poți accesa și interoga date din ambele tabele
ca și cum ar fi o singură entitate.

### How many rows would a two-table join produce if one table had 50,000 rows and the other had 100,000?

Un join între cele două tabele ar produce un număr maxim de 50.000 de rânduri, deoarece într-un Inner Join, rezultatul
va conține doar înregistrările care au corespondență în ambele tabele.

### What type of join appears in the following SELECT statement?

```sql
select e.name, e.employee_id, ep.salary
from employee_tbl e,
     employee_pay_tbl ep
where e.employee_id = ep.employee_id;
```

În SELECT statement-ul dat apare un Inner Join, deoarece condiția e.employee_id = ep.employee_id asigură că sunt
returnate numai înregistrările care au corespondență în ambele tabele.

### In joining tables are you limited to one-column joins, or can you join on more than one column?

Poți face join pe mai multe coloane într-un query SQL. Nu ești limitat la join-uri pe o singură coloană.

---

## DML

### Does SQL have a statement for file import/export operations?

Oferă instrucțiuni pentru import/export de date, dar acestea pot varia în funcție de sistemul de gestionare a bazelor de
date utilizat. De exemplu, în PostgreSQL, poți utiliza COPY pentru a importa/exporta date către/de la fișiere.

### Can you copy data from a table into itself using the INSERT command? You would like to make duplicate copies of all the existing records and change the value of one field.

Da, poți copia date dintr-o tabelă în ea însăși folosind comanda INSERT. Pentru a face copii duplicate ale
înregistrărilor existente și pentru a schimba valoarea unui câmp, poți utiliza o comanda care selectează datele din
tabelul sursă și le introduce în același tabel țintă, aplicând modificările necesare.

### What would happen if you issued the following statement?

```sql
DELETE
* FROM COLLECTION;
```

nu este o sintaxă corectă în SQL. Instrucțiunea DELETE ar trebui să fie urmată de FROM și numele tabelului, dar * nu
este necesar și nu face parte din sintaxa corectă. O instrucțiune corectă ar arăta astfel: DELETE FROM COLLECTION;, ceea
ce ar șterge toate înregistrările din tabelul "COLLECTION".

### Can you remove columns with the ALTER TABLE statement?

Da, poți elimina coloane dintr-o tabelă utilizând instrucțiunea ALTER TABLE. Sintaxa corectă ar fi:
ALTER TABLE table_name DROP COLUMN column_name;.

### Is the DROP TABLE command functionally equivalent to the DELETE FROM <table_name> command?

Nu, comanda DROP TABLE și comanda DELETE FROM <table_name> au funcționalități diferite. DROP TABLE șterge întreaga
structură a tabelei, inclusiv datele și structura tabelului în sine, în timp ce DELETE FROM <table_name> șterge doar
datele din tabel, menținând structura tabelului intactă.

### What is the difference between the functionality of the DELETE FROM <table_name> and the TRUNCATE TABLE command?

Ambele instrucțiuni sunt utilizate pentru a șterge datele dintr-o tabelă, dar există diferențe importante:

- DELETE FROM <table_name> șterge datele înregistrărilor rând cu rând și permite condiții complexe și rollback. Este mai
  lentă pentru ștergeri masive de date.

- TRUNCATE TABLE șterge toate înregistrările din tabel rapid și resetează identitatea coloanelor la valoarea inițială,
  dar nu permite specificarea condițiilor și nu poate fi anulată (nu se poate face rollback). Este mai rapidă pentru
  ștergeri
  masive de date.

### When a table is created, who is the owner?

Proprietarul unei tabele este de obicei utilizatorul sau rolul care a creat tabela. În funcție de sistemul de gestionare
a bazelor de date (SGBD), poate fi necesară o autorizație adecvată pentru a crea o tabelă.

### If data in a character column has varying lengths, what is the best choice for the data type?

Dacă datele dintr-o coloană de tip caracter au lungimi variabile, cel mai bun tip de date este VARCHAR (Variabile
Character). Acest tip de date permite stocarea de șiruri de caractere cu lungimi variabile, economisind spațiu în
comparație cu CHAR care are o lungime fixă.
