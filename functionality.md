## 1. Opis systemu

Z tworzonej bazy danych skorzysta firma oferująca różnego rodzaju kursy i szkolenia:

* webinary - odbywają się na żywo na jednej z platform chmurowych, a ich nagrania są udostępniane klientom firmy. Nagrania nie są przechowywane w bazie - jedynie informacja o nich, którą usunąć może administrator.
* kursy - krótkie formy kształcenia, trwające zazwyczaj kilka dni, istnieją wyłącznie kursy płatne. Zaliczenie kursu wymaga zaliczenia min. 80% modułów.
* studia - kilkuletnie szkolenia odbywające się online i stacjonarnie, wymagają zaliczenia praktyk i zdania egzaminu końcowego

Każda z tych form kształcenia prowadzona jest przez konkretnego wykładowcę w konkretnym języku (najczęściej polskim). Czasami treść jest tłumaczona na żywo przez tłumacza, co też powinno zostać odnotowane w bazie danych.

Możemy wyróżnić następujących aktorów systemu:

* Klient - użytkownik chcący skorzystać z oferty firmy szkoleniowej
* Właściciel - osoba tworząca materiały video i treść kursów
* Administrator - zarządzanie bazą danych oraz jej ulepszanie
 Aktorzy mogą skorzystać z następujących funkcjonalności:

### 1.1 Klient

#### 1.1.1. Webinary

* Korzystanie z nagrań bezpłatnych webinarów przez okres 30 dni od ich umieszczenia na stronie
* Użytkownicy posiadający konto: Po opłaceniu dostępu do webinarów płatnych, korzystanie z nagrań tych webinarów przez kolejne 30 dni od potwierdzenia opłaty
*

#### 1.1.2. Kursy

* Kontrolowanie zaliczenia danego kursu
(procent zaliczonych modułów >= 80 %)
Sprawdzenie statusu swojej obecności na wybranych modułach
* Dostęp do listy kursów na które użytkownik jest zapisany i dostęp do statusu płatności przy każdym kursie (nieopłacone/ zaliczka/ opłacone w całości)
* Sprawdzenie dostępności wolnych miejsc na kursy hybrydowe i stacjonarne
* Dostęp do dodatkowych informacji o kursach takich jak: język kursu, obecność tłumacza, sposobie organizacji kursu (stacjonarnie/
o-line synchronicznie/ online asynchronicznie/ hybrydowo), dacie rozpoczęcia kursu czy sali zajęciowej (informacja dostępna po uiszczeniu wszelkich opłat)
Dostęp do nagranych modułów (moduły online), po opłaceniu dostępu

#### 1.1.3. Studia

* Sprawdzenie swojej obecności na zajęciach
* Możliwość zapisania się na odrabianie zajęć w kursie lub zajęciach innego kursu o podobnej tematyce
* Sprawdzenie wyników z egzaminów
* Sprawdzenie informacji o tym, czy odbyło się praktyki (14 dni - 2 razy w ciągu roku) i frekwencji na nich
* Możliwość zapisania się na pojedyncze zajęcia
* Wyświetlenie sylabusu studiów

#### 1.1.4. Koszyk

* dodawanie produktów do koszyka  (kursy, webinary, studia)
  
### 1.2. Sekretarz

* Wyświetlanie następujących raportów:
  * lista osób, które skorzystały z oferty firmy, ale za to nie zapłaciły
  * lista osób zapisanych na przyszłe wydarzenia z informacją, czy wydarzenia te odbywają się stacjonarnie, czy online
  * raport dotyczący frekwencji na wydarzeniach przeszłych - liczba osób które brały udział w każdym kursie/webinarze/studium i były obecne
  * lista osób, które są zapisane na kolidujące ze sobą wydarzenia
  * lista wyników egzaminów dla użytkowników
  * lista obecności na zajęciach dla danego użytkownika
  * lista odbytych praktyk
  * Dodanie nowego klienta
* Wyświetlanie spisu wszystkich zajęć i wszystkich spotkań z datami

### 1.3. Manager

Funkcje jakie ma sekretarz + dodatkowo:

* Wyświetlanie następujących raportów:
  * finansowe - zestawienie przychodów dla każdego kursu/studium/webinaru - przesyłana jest informacja o tym do właściciela
  * lista osób zapisanych na każde szkolenie zawierająca imię, nazwisko, informacja, czy klient był obecny
* Wyświetlanie spisu wszystkich zajęć i wszystkich spotkań z datami oraz możliwość ich zmiany (studia)
* Określenie limitu miejsc na kursy hybrydowe/stacjonarne oraz studia
* Możliwość generowania listy klientów którzy są uprawnieni do otrzymania dyplomów (ukończyli kurs/studia)

### 1.4. Nauczyciel

* Dodawanie nagrań szkoleń
* Dostęp do prowadzonych przez siebie nagrań i list obecności z prowadzonych przez siebie zajęć
  
### 1.5. Właściciel

Funkcje managera i sekretarza + dodatkowo:

* Zezwalanie na odroczenie płatności za szkolenia

### 1.6. Funkcje systemu

#### 1.6.1. Webinary

* kontrola dostępu klientów do webinarów
  * webinary bezpłatne - dostęp przez 30 dni od umieszczenia nagrania na platformie
  * webinary płatne - dostęp przez 30 dni od uiszczenia opłaty
  * uniemożliwienie korzystania z płatnych webinarów użytkownikom niezalogowanym i tym, którzy nie uiścili opłaty

#### 1.6.2. Kursy

* weryfikacja zaliczenia danych modułów wchodzących w skład kursu
* kontrola dostępu klientów do kursów:
  * kursy on-line synchronicznie (zasady jak przy webinarach)
  * kursy online asynchronicznie (dostęp po dodaniu materiałów przez właściciela i po uiszczeniu opłat przez klienta)
  * uniemożliwienie dostępu do kursów on-line użytkownikom którzy nie wpłacili całości kwoty 3 dni przed rozpoczęciem kursu

#### 1.6.3. Studia

* kontrola dostępu klientów do studiów
  * spotkania on-line
  * spotkania stacjonarnie
  * spotkania hybrydowe
  * możliwość wykupienia dostępu płatnego do jednego spotkania
  * limit miejsc ogólny (nie może być większy niż najmniejszy spośród limitów wszystkich spotkań)
* przechowywanie informacji o sylabusie (przechowywanie listy zajęć na danym studium i listy różnych studiów jeszcze przed danym rokiem)
* przechowywanie informacji o spisie wszystkich zajęć i wszystkich spotkań z datami
  * limit miejsc na spotkanie
* kontrola, czy studenci zaliczyli praktyki trwające 14 dni - 2 razy w ciągu roku
* kontrola obecności klientów na spotkaniach i praktykach
  * aby zaliczyć studium:
    * 80% obecności na spotkaniach
    * 100% obecności na praktykach
* kontrola, czy studenci uiścili opłatę wpisową oraz za każde spotkanie najpóźniej 3 dni przed zjazdem
* przyznawanie statusu zaliczenia i ew. wysłania dyplomu Pocztą polska na status korespondencyjny (na podstawie zaliczenia praktyk i egzaminu końcowego oraz obecności)

#### 1.6.4. Koszyk

* po kliknięciu przez klienta  “Zakończ i zapłać”, wygenerowanie linku do płatności.
* po zakończeniu transakcji przesłanie informacji zwrotnej o pomyślnym zakończeniu płatności lub błędzie.

## 2. Schemat bazy danych

![schemat](Systemy_Baz_Danych_2023_2024_–_projekt-2023-12-11_17-59.svg)

## 3. Implementacje tabel

### 3.1 Core

Główna część systemu

#### Users

Zawiera wszystkich użytkowników systemu oraz ich dane - imię, nazwisko, dane adresowe oraz typ użytkownika (klucz obcy do tabeli User_types), a także informację o tym, ile dni opóźnienia w płatności jest dozwolone danemu użytkownikowi.

```sql
CREATE TABLE Users (
   user_id int  NOT NULL,
   first_name nvarchar  NOT NULL,
   last_name nvarchar  NOT NULL,
   zip_code nvarchar(10)  NOT NULL,
   city nvarchar  NOT NULL,
   street_address nvarchar  NOT NULL,
   country nvarchar(50)  NOT NULL,
   can_pay_days_later int  NOT NULL DEFAULT 0,
   user_type int  NOT NULL,
   CONSTRAINT client_id PRIMARY KEY (user_id)
);
```

#### Academics

Zawiera id wszystkich użytkowników, którzy są nauczycielami - zdecydowaliśmy się na dodanie tabel Academics, Interpreters i Clients, by rozdzielić logikę wykonywaną dla poszczególnych typów użytkownika.

```sql
CREATE TABLE Academics (
   academic_id int  NOT NULL,
   CONSTRAINT Academics_pk PRIMARY KEY  (academic_id)
);
```

#### Interpreters

Zawiera id wszystkich tłumaczy

```sql
CREATE TABLE Interpreters (
   interpreter_id int  NOT NULL,
   CONSTRAINT Interpreters_pk PRIMARY KEY  (interpreter_id)
);
```

#### Clients

Zawiera id wszystkich klientów

```sql
CREATE TABLE Clients (
   client_id int  NOT NULL,
   CONSTRAINT client_id PRIMARY KEY  (client_id)
);
```

#### User_types

Zawiera listę wszystkich typów użytkowników występujących w systemie

```sql
CREATE TABLE User_types (
   user_type int  NOT NULL,
   type_name nvarchar(50)  NOT NULL,
   CONSTRAINT User_types_pk PRIMARY KEY  (user_type)
);  
```

#### Interpreted_languages

Każdemu tłumaczowi przyporządkowuje informację o tym, z jakiego języka na jaki tłumaczy (są to FK do tabeli languages)

```sql
CREATE TABLE Interpreted_languages (
   interpreter_id int  NOT NULL,
   translate_from int  NOT NULL,
   translate_to int  NOT NULL,
   CONSTRAINT Interpreted_languages_pk PRIMARY KEY  (interpreter_id,translate_from,translate_to)
);
```

#### Languages

Lista wszystkich języków, w jakich prowadzone są szkolenia, bądź na jakie są one tłumaczone

```sql
CREATE TABLE Languages (
   language_id int  NOT NULL,
   language_name nvarchar(50)  NOT NULL,
   CONSTRAINT Languages_pk PRIMARY KEY  (language_id)
);
```

#### Products

Zawiera wszystkie produkty, informację o ich typie (odwołanie do tabeli ProductType), języku w jakim jest prowadzone dane szkolenie, wykładowcy, który je prowadzi oraz o tłumaczu i języku, na który tłumaczone jest szkolenie

```sql
CREATE TABLE Products (
   product_id int  NOT NULL,
   product_type_id int  NOT NULL,
   language int  NOT NULL,
   academic_id int  NOT NULL,
   interpreter_id int  NULL,
   translated_to int  NULL,
   CONSTRAINT Products_pk PRIMARY KEY  (product_id)
);
```

#### ProductType

Zawiera wszystkie typy produktów (webinary, spotkania, kursy, studia)

```sql
CREATE TABLE ProductType (
   procduct_type_id int  NOT NULL,
   product_type_name nvarchar  NOT NULL,
   CONSTRAINT ProductType_pk PRIMARY KEY  (procduct_type_id)
);
```

#### BucketProducts

Zawiera informację o produktach wrzuconych do koszyka przez klientów

```sql
CREATE TABLE BucketProducts (
   bucket_entry_id int  NOT NULL,
   client_id int  NOT NULL,
   product_id int  NOT NULL,
   CONSTRAINT BucketProducts_pk PRIMARY KEY  (bucket_entry_id)
);
```

#### Payments

Spis wszystkich płatności (numer klienta, data płatności, wpłacona kwota, informacja czy kwota jest zaliczką, informacja czy płatność została anulowana)

```sql
CREATE TABLE Payments (
   payment_id int  NOT NULL,
   product_id int  NOT NULL,
   client_id int  NOT NULL,
   payment_date date  NOT NULL,
   is_advance bit  NOT NULL,
   cancelled bit  NOT NULL,
   price int  NOT NULL,
   CONSTRAINT Payments_pk PRIMARY KEY  (payment_id)
);
```

#### MeetingType

Rodzaje spotkań (online, hybrydowe, stacjonarne)

```sql
CREATE TABLE MeetingType (
   type_id int  NOT NULL,
   type_name nvarchar  NOT NULL,
   CONSTRAINT type_id PRIMARY KEY  (type_id)
);
```

### 3.2. Webinars

#### Webinars

Lista wszystkich webinarów wraz z ich nazwami, datą publikacji i ceną

```sql
CREATE TABLE Webinars (
   product_id int  NOT NULL,
   webinar_name nvarchar  NOT NULL,
   posted_date date  NOT NULL,
   price int  NULL,
   CONSTRAINT product_id PRIMARY KEY  (product_id)
);
```

#### WebinarParticipants

Lista uczestników poszczególnych webinarów

```sql
CREATE TABLE WebinarParticipants (
   product_id int  NOT NULL,
   client_id int  NOT NULL,
   CONSTRAINT WebinarParticipants_pk PRIMARY KEY  (client_id,product_id)
);
```

### 3.3. Courses

#### Courses

Lista kursów wraz z ich nazwami, datami początku i końca kursu, limitem uczestników, ceną zaliczki oraz pełną ceną

```sql
CREATE TABLE Courses (
   product_id int  NOT NULL,
   course_name nvarchar  NOT NULL,
   start_date date  NOT NULL,
   end_date date  NOT NULL,
   participants_limit int  NOT NULL,
   advance_price int  NOT NULL,
   full_price int  NOT NULL,
   CONSTRAINT product_id PRIMARY KEY  (product_id)
);
```

#### CoursesParticipants

Lista uczestników poszczególnych kursów

```sql
CREATE TABLE CoursesParticipants (
   participant_id int  NOT NULL,
   client_id int  NOT NULL,
   product_id int  NOT NULL,
   CONSTRAINT CoursesParticipants_pk PRIMARY KEY  (participant_id)
);
```


#### Modules

Lista modułów kursów z nazwami, typem modułu (odwołanie do tabeli MeetingType), numerem sali oraz datą rozpoczęcia i zakończenia modułu

```sql
CREATE TABLE Modules (
   module_id int  NOT NULL,
   product_id int  NOT NULL,
   module_name varchar(50)  NOT NULL,
   module_type int  NOT NULL,
   classroom int  NULL,
   start_date date  NOT NULL,
   end_date date  NOT NULL,
   CONSTRAINT Modules_pk PRIMARY KEY  (module_id)
);
```

#### ModulesAttendance

Zawiera listę obecności uczestników kursów na poszczególnych modułach

```sql
CREATE TABLE ModulesAttendance (
   participant_id int  NOT NULL,
   module_id int  NOT NULL,
   presence bit  NOT NULL,
   CONSTRAINT ModulesAttendance_pk PRIMARY KEY  (participant_id,module_id)
);
```

### 3.4. Studies

#### Studies

Zawiera listę produktów typu "studia", nazwę studiów, limit uczestników oraz wysokość wpisowego

```sql
CREATE TABLE Studies (
   product_id int  NOT NULL,
   name nvarchar  NOT NULL,
   participants_limit int  NOT NULL,
   entry_fee int  NOT NULL,
   CONSTRAINT studies_id PRIMARY KEY  (product_id)
);
```

#### StudiesParticipants

Zawiera uczestników poszczególnych studiów

```sql
CREATE TABLE StudiesParticipants (
   participant_id int  NOT NULL,
   client_id int  NOT NULL,
   product_id int  NOT NULL,
   CONSTRAINT participant_id PRIMARY KEY  (participant_id)
);
```
#### Exams

Zawiera wyniki z egzaminów poszczególnych uczestników, datę napisania egzaminu oraz zdobyte punkty

```sql
CREATE TABLE Exams (
   exam_id int  NOT NULL,
   participant_id int  NOT NULL,
   date int  NOT NULL,
   points int  NOT NULL,
   CONSTRAINT participant_id UNIQUE (participant_id),
   CONSTRAINT Exams_pk PRIMARY KEY  (exam_id,participant_id)
);
```

#### Apprenticeship

Zawiera uczestników, którzy odbyli praktyki w określonym terminie

```sql
CREATE TABLE Apprenticeship (
   participant_id int  NOT NULL,
   date date  NOT NULL,
   CONSTRAINT participant_id PRIMARY KEY  (participant_id,date)
);
```

#### MeetingParticipants

Zawiera listę obecnych studentów na danych spotkaniach

```sql
CREATE TABLE MeetingParticipants (
   meeting_id int  NOT NULL,
   participant_id int  NOT NULL,
   CONSTRAINT meeting_id PRIMARY KEY  (meeting_id)
);
```

#### StudiesMeetings

Lista spotkań poszczególnych studiów, data spotkania, typ spotkania (FK do MeetingTypes), limit uczestników spotkania, cena dla studentów, cena dla uczestników, którzy nie są studentami

```sql
CREATE TABLE StudiesMeetings (
   meeting_id int  NOT NULL,
   studies_id int  NOT NULL,
   date date  NOT NULL,
   type_id int  NOT NULL,
   participants_limit int  NOT NULL,
   student_price int  NOT NULL,
   outer_participant_price int  NOT NULL,
   CONSTRAINT meeting_id PRIMARY KEY  (meeting_id)
);
```
