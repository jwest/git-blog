title: Wdrażanie aplikacji z repozytorium Git-a | Git-ftp
date: 2012-06-27 20:30:00
tags: git, php, programowanie, środowisko pracy, Techblog
---
Zainspirowany pytaniem o dobre wsparcie edytora dla ftp-a, postanowiłem podzielić się sposobem na wdrażanie aplikacji "po mojemu";)

Gdy już zacząłem na dobre korzystać z git-a do prowadzenia projektów, chciałem mieć możliwość podnoszenia zmian za pomocą tego narzędzia. Nie zawsze jednak dysponuję środowiskiem git-a na serwerze produkcyjnym żeby zrobić zwykłego clona i pull-a.

Okazało się, że jest prostsze i wygodniejsze rozwiązanie o nazwie git-ftp. W ramach tego narzędzia dostajemy nowe polecenie dla git-a powodujące wysłanie zmian na serwer ftp. Skrypt nie pozwoli nam wysłać tych zmian jeżeli w lokalnej kopii mamy zmiany nie wchodzące w skład repo. W samym wywołaniu polecenia możemy podać parametry serwera lub skonfigurować nasze lokalne repo tak, aby domyślnie po wykonaniu polecenia git ftp push zmiany trafiły na nasz serwer produkcyjny.

Zostaje nam do załatwienia tylko problem konfiguracji, która różni się w zależności od środowiska. Mamy 2 możliwości, albo dodajemy plik w którym mówimy narzędziu git-ftp aby pomijał pliki konfiguracyjne, albo przygotowujemy różne wersje konfiguracji i za pomocą np. zmiennych środowiskowych identyfikujemy czy mamy do czynienia z produkcją czy środowiskiem developerskim. Drugie rozwiązanie jest wspierane domyślnie przez wiele frameworków.

W ten prosty sposób likwidujemy przypadki robienia zmian bezpośrednio na serwerze oraz zawsze mamy aktualną wersję kodu w repozytorium. Wymusza to na nas prowadzenie wszelkich zmian przez git-a, a jeżeli jest coś co wymusza dobre praktyki i nie jest przy tym czasochłonne to nie może być złe ;) . Rozwiązanie to daje także możliwość cofnięcia się do poprzedniej rewizji i wycofania zmian, które mogły spowodować problem z działaniem aplikacji.

Odsyłam do github-a gdzie znajduje się instrukcja instalacji i konfiguracji: https://github.com/resmo/git-ftp.