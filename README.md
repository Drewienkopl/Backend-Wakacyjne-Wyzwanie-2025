# Backend-Wakacyjne-Wyzwanie-2025
This is copy of repository of the project I did during "Backend Wakacyjne Wyzwanie Solvro 2025".

Project setup:
$ npm install

Whole Project Includes:

Zadanie 0 - Elo Żelo
   Twoim zadaniem jest stworzenie prostego programu w TypeScript, który zademonstruje umiejętność definiowania funkcji z typami oraz używania podstawowych funkcji platformy Node.js. Napisz program w piku index.ts, który:
   Definiuje funkcje eloZelo, która tworzy plik elo-żelo.txt i wpisuje do niego Elo żelo określoną w parametrze funkcji ilość razy
   Wywołuje funkcje eloZelo z parametrem równym liczbie minut z aktualnej godziny (np. gdyby obecnie była 11:27, to program powinien wywołać funkcję eloZelo z argumentem równym 27)

Zadanie 1 - Hello World
   Twoim zadaniem jest wygenerowanie pierwszego projektu w NestJS, wgranie SolvroConfig (zalecam zacząć od tego, instrukcja w materiałach) oraz zmiana endpointa, w app.controller.ts, aby działał w następujący sposób:
   1. Zostanie wywołany po wysłaniu zapytania pod adres: http://127.0.0.1/wakacyjne/backend (element "/wakacyjne/" ma być ustawiony dla całej grupy endpointów z tego kontrolera)
   2. Manualnie ustaw kod statusu 418 dla naszego endpointu (tutaj tylko dla tego konkretnego)
   3. Zmień działanie funkcji getHello() w serwisie, aby zwracała ona JSON w postaci:
   {
    "title" : "Wakacyjne Wyzwanie Solvro!!!",
    "quote" : "Jakaś twoja złota myśl - liczę na kreatywność"
   } 
   4. Wykonaj zapytanie do utworzonego endpoint'a z klienta API (przykładowo Postman)

Zadanie 2 - Projekt budżetownika – ERD i modele
   1. Modelowanie budżetownika
   Utwórz diagram ERD (Entity Relationship Diagram) przedstawiający relacje między tabelami.
   Zamodeluj 3 tabele: Trip, Expense, Participant. Wykorzystaj dowolne narzędzie do stworzenia ERD (np. drawdb, drawio, paint).
   W tabelach użyj przynajmniej jednego (nie musza być wszystkie w kazdej tabeli):
      typu int
      typu string
      typu float
      typu enum
      typu opcjonalnego
      typu datetime
   Opisz relacje między tabelami. Załacz screen z diagramem ERD do Pull Requesta

   2. Konfiguracja Prisma i migracja modeli Skonfiguruj Prisme według instrukcji z wykładu.
   Zainstaluj i zainicjalizuj Prisme.
   Skonfiguruj plik .env z URI do połączenia z bazą danych.
   W pliku prisma/schema.prisma odwzoruj swoje modele z diagramu ERD.
   Uruchom migrację bazy danych.
   Sprawdź, czy migracja działa, korzystając z dowolnego narzędzia do pracy z bazą danych.

   3. Seedowanie bazy danych w NestJS Wygeneruj moduł w NestJS do komunikacji z bazą danych.
   Skonfiguruj moduł(module + serwis) według instrukcji z wykładu.
   Utwórz plik prisma/seed.ts.
   Napisz funkcję seedującą, która wprowadzi przykładowe dane – minimum po jednym wpisie dla każdego modelu.

   4.  (dla chętnych) Kontroler i endpointy API Wygeneruj kontroler do modułu bazy danych.
   Wstrzyknij do kontrolera serwis do komunikacji z bazą danych.
   constructor (private prisma : typ_serwisu_bazydanych){}
   Utwórz co najmniej dwa endpointy o różnych metodach HTTP (np. GET, POST, PUT, PATCH, DELETE).
   Przetestuj działanie endpointów w dowolnym narzędziu do pracy z API (np. Postman).
   Porównaj czy zapytania maja swoje odzwierciedlenie w bazie danych.

Zadanie 3 - CRUD i dokumentacja
   1. Zrobić CRUD dla uczestników (Participant'ów)
   2. Zrobić CRUD dla wydatków (Expense'ów)
   3. Dodać dekoratory do endpointów w celu ich dokumentacji
   4. Stworzyć DTO dla CRUDów i dodać do nich odpowiednie dekoratory
   5. Dodać i skonfigurować Swagger UI

Zadanie 4 - Autoryzacja i walidatory
   1. Dodaj endpoint do rejestracji użytkownika
      Pamiętaj o tym aby zapisać hasło po hashowaniu.
      Zastanów się jakie kody błędów powinny być zwracane? Np. 409 CONFLICT, gdy istnieje już użytkownik o podanym emailu.
   2. Zastanów się, które endpointy powinny być dostępne publicznie (dla każdego), a które tylko dla osób zalogowanych i tych z odpowiednimi uprawnieniami
      Dodaj rolę koordynatora wycieczki. Tylko on (oraz administrator) powinnen mieć prawo zmiany informacji o wycieczce.
      Podziel obecne endpointy na publiczne i prywatne dodając zabezpiecznia (guardy).
      Zastanów się, które informacje powinny móc opuścić nasze API, a co powinno zostać jednak ukryte (sprawdź i zaaktualizuj swoje DTO pod tym względem).
   3. Stwórz endpoint podobny do PATCH /user pokazanego na prezentacji. Zmień go, tak aby dany użytkownik mógł modyfikować jedynie swoje dane (tak jest obecnie) oraz, aby użytkownik z prawami administratora mógł modyfikować dane każdego użytkownika. Nie twórz dwóch osobych endpointów.
   4. Zmodyfikuj endpoint do logowania:
      Dodaj obecny znacznik czasu do tokenu.
      Dodaj zmienną środowiskową EXPIRY_TIME_MS, oznaczającą czas ważności tokenu w milisekundach
      Przy sprawdzniu poprawności tokenu, sprawdź czy token jest jeszcze ważny, jeżeli nie jest, odeśli komunikat o tym.
   5. Dodaj walidację do obecnych endpointów
      Sprawdzaj poprawność parametrów wejściowych.
      Dodaj walidację do DTO.
      Stwórz jeden własny walidator, który ma sens. Np. data nie może być lub musi być z przyszłości.
   6. (Tylko dla chętnych) Dodaj do swojej aplikacji CORS. Skonfiguruj tak, aby akceptował połączenia z localhost i portów od 5000 do 5599 włącznie.

Zadanie 5 - Testy
   1. Testy jednostkowe (unit tests):
      Dla serwisów i kontrolerów: trips, participants, expenses
      Mockowanie bazy danych
      Minimum jeden test dla każdej metody
   2. Testy end-to-end (e2e):
      Dla: trips, participants, expenses
      Wykorzystanie testowej bazy danych
      Minimum jeden test dla każdej metody
   Wśród testów powinien się znaleźć:
      Przynajmniej jeden test dla dowolnego guarda
      Przynajmniej jeden test dla dowolnego customowego walidatora


Zadanie 6 - Scrapowanie i procesy w tle
   1. Model walut - Stwórz prosty model do przechowywania par waluta-kurs. Dla chętnych: dodaj możliwość przechowywania historii kursów walut. W wersji podstawowej wystarczy opcja przechowywania tylko najnowszej wartości.
   2. Scraper kursów walut - Zaimplementuj scraper dla strony z dynamicznymi kursami walut (np. https://waluty24.info/). Pobieraj co najmniej 3 różne waluty w porównaniu do złotówki.
      Disclaimer: Nie sprawdzałem czy przykładowa strona jest przyjemna do scrapowania - znalezienie dobrej strony to też część zadania.
   3. Harmonogram zadań - Skonfiguruj cykliczne uruchamianie scrapera używając mechanizmów planowania zadań.
   4. Wdrożenie waluty do serwisu z płatnościami - Wykorzystaj informacje o aktualnym lub historycznym kursie do przeliczania transakcji w obcych walutach. Twój endpoint tworzący płatności (POST /payments) powinien przyjmować walutę i kwotę, a następnie zapisywać wartość już przeliczoną na złotówki.
   5. Powiadomienia email (opcjonalne) - Dodaj funkcjonalność wysyłania maili z podsumowaniami do uczestników wyjazdu, np. przy zamykaniu wyjazdu (endpoint /trip/close). To od Ciebie zależy jak bardzo zaawansowane będą to podsumowania - możesz, na przykład wysyłać tylko ogólne informacje o wydatkach z wyjazdu, albo podliczać kto powinien komu ile oddać.(DIDN"T DO THIS ONE)
