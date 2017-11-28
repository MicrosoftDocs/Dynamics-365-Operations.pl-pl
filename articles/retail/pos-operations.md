---
title: Operacje aplikacji POS
description: "Ten temat zawiera szczegółowe informacje na temat operacji dotyczących punktu sprzedaży (POS) w rozwiązaniu Microsoft Dynamics 365 for Retail. Określa, gdzie w aplikacji można wywołać operacje oraz czy są dostępne w trybie offline.."
author: jblucher
manager: AnnBe
ms.date: 10/12/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2017-09-27
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 02d777da3b97706f9e63478a1978ac9b230a591e
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="pos-operations"></a>Operacje aplikacji POS
Większość akcji wykonywanych przez użytkowników punktu sprzedaży (POS) jest uznawanych za operacje. Do konfigurowania i zarządzania operacjami służy zaplecze rozwiązania Microsoft Dynamics 365 for Retail. Do siatki przycisków punktu sprzedaży można dodać wiele operacji. Użytkownicy mogą następnie wybrać przyciski w celu wywołania operacji i wykonania przypisanych do nich funkcji. Inne operacje są częścią głównej aplikacji POS i są wywoływane za pomocą przycisków ekranowych lub jako część innych przepływów pracy lub procesów.

Poniższa tabela zawiera szczegóły dotyczące operacji dostępnych w nowoczesnym punkcie sprzedaży detalicznej i punkcie sprzedaży w chmurze dla rozwiązania Dynamics 365 for Retail. Tabela umożliwia także określenie, gdzie w aplikacji można wywołać operacje oraz czy są dostępne, gdy punkt sprzedaży działa w trybie offline..

Niektóre operacje nie są aktualnie dostępne w nowoczesnym punkcie sprzedaży detalicznej i punkcie sprzedaży w chmurze dla rozwiązania Dynamics 365 for Retail Niektóre z tych operacji zależą od ustawień regionalnych,, które wymagają dodatkowych rozszerzeń i konfiguracji. Inne to funkcje systemu Microsoft Dynamics AX 2012, które nie są aktualnie obsługiwane.

Poniższe kolumny określają, gdzie można wywołać informacje:

- **Siatka przycisków** — operacje można przypisać do przycisków na siatce przycisków punktu sprzedaży, która jest częścią układu ekranu punktu sprzedaży.
- **Ekran transakcji** — operację można wywołać z siatki przycisków punktu sprzedaży skonfigurowanych na ekranie transakcji punktu sprzedaży.
- **Ekran powitalny** — operację można wywołać z siatki przycisków punktu sprzedaży skonfigurowanych na ekranie powitalnym punktu sprzedaży.

| Identyfikator | Operacja | opis | Siatka przycisków | Ekran transakcyjny | Ekran powitalny | Dostępne w trybie offline | Specyficzne dla ustawień regionalnych |
|----|-----------|-------------|-------------|--------------------|----------------|-------------------|-----------------|
| 707 | Aktywuj urządzenie | Aktywuj bieżące urządzenie, zezwalając uwierzytelnionemu użytkownikowi podanie informacji o połączeniu oraz przypisanie urządzenia i identyfikatora kasy. | Nr | Nr | Nr | Nr | Nr |
| 134 | Dodaj przynależność | Dodaj wybraną wstępnie przynależność do transakcji. Wybierz przynależność na stronie **Przycisk właściwości**. | Tak | Tak | Nr | Tak | Nr |
| 135 | Dodaj przynależność z listy | Dodawaj przynależność do transakcji przez wybranie jej na liście. | Tak | Tak | Tak | Tak | Nr |
| 643 | Dodaj kod kuponu | Dodaj kupon, wprowadzając jego kod w punkcie sprzedaży. | Tak | Tak | Nr | Tak | Nr |
| 117 | Dodaj kartę lojalnościową | Wyświetl monit dla użytkownika o wprowadzenie numeru karty lojalnościowej, która zostanie dodana do bieżącej transakcji. | Tak | Tak | Nr | Tak | Nr |
| 136 | Dodaj numer seryjny | Ta operacja umożliwia użytkownikowi określenie numeru seryjnego dla aktualnie wybranego produktu. | Tak | Tak | Nr | Tak | Nr |
| 1214 | Dodaj adres wysyłkowy | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nr |
| 519 | Dodaj do karty upominkowej | Dodaj pieniądze do określonej karty upominkowej. | Tak | Tak | Nr | Nr | Nr |
| 6000 | Zezwalaj na pomijanie rejestracji fiskalnej | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Tak |
| 1212 | Przekazanie pieniędzy do banku | Rejestruj kwotę pieniędzy wysłaną do banku oraz inne informacje, takie jak numer worka bankowego. | Tak | Tak | Tak | Tak | Nr |
| 923 | Weryfikacja sum banku | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Tak |
| 915 | Pusta operacja | Ta operacja przedstawia dostosowywalny przycisk, który deweloper oprogramowania może programowo zmienić w taki sposób, aby służył do wykonywania dowolnej specjalistycznej operacji wymaganej przez firmę. | Tak | Tak | Tak | Tak | Nr |
| 1053 | Zmiana z ukryciem raportu podczas zamknięcia kasy | Ustaw aktualną zmianę na zmianę z ukryciem raportu i wyloguj użytkownika. Zmiana z ukryciem raportu jest niedostępna dla dodatkowych transakcji ale jest dostępna dla operacji z użyciem szuflady, takich jak pobranie środków płatniczych i deklaracja środków płatniczych. | Tak | Tak | Tak | Nr | Nr |
| 310 | Obliczanie sumy | Gdy obliczanie rabatów jest opóźnione, ta operacja inicjuje obliczanie bieżącej transakcji. | Tak | Tak | Nr | Tak | Nr |
| 642 | Wynieś wszystkie produkty | Ustaw metodę dostawy wszystkich wierszy na **Wyniesienie**. | Tak | Tak | Nr | Tak\* | Nr |
| 641 | Wynieś wybrane produkty | Ustaw metodę dostawy wybranych wierszy na **Wyniesienie**. | Tak | Tak | Nr | Tak\* | Nr |
| 1215 | Zmień hasło | Ta operacja umożliwia użytkownikowi punktu sprzedaży zmianę hasła. | Tak | Tak | Tak | Nr | Nr |
| 123 | Zmień jednostkę miary | Zmień jednostkę miary wybranej pozycji w wierszu. | Tak | Tak | Nr | Tak | Nr |
| 639 | Wyczyść domyślnego przedstawiciela handlowego w transakcji | Usuń grupę prowizji sprzedaży (przedstawiciel handlowy) z transakcji. | Tak | Tak | Nr | Tak | Nr |
| 106 | Wyczyszczenie ilości | Zresetuj ilość w aktualnie wybranym wierszu do **1**. | Tak | Tak | Nr | Tak | Nr |
| 640 | Wyczyść przedstawiciela handlowego w wierszu | Usuń grupę prowizji sprzedaży (przedstawiciel handlowy) z aktualnie wybranego wiersza. | Tak | Tak | Nr | Tak | Nr |
| 121 | Wyczyść dane sprzedawcy | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nr |
| 1055 | Zamknięcie zmiany | Zamknij bieżącą zmian, wydrukuj Końcowy raport sprzedaży i wyloguj użytkownika z systemu. | Tak | Tak | Tak | Nr | Nr |
| 925 | Kopiuj czek bankowy | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Tak |
| 620 | Utwórz zamówienie odbiorcy | Konwertuj transakcję punktu sprzedaży na zamówienie odbiorcy. | Tak | Tak | Nr | Tak\* | Nr |
| 621 | Tworzenie oferty | Konwertuj transakcję punktu sprzedaży na ofertę sprzedaży. | Tak | Tak | Nr | Tak\* | Nr |
| 636 | Utwórz transakcję detaliczną | Ta operacja umożliwia użytkownikowi utworzenie standardowej transakcji sprzedaży, gdy domyśle zachowanie punktu sprzedaży to utworzenie zamówień odbiorcy. | Tak | Tak | Nr | Tak | Nr |
| 600 | Odbiorca | Dodaj określonego klienta do transakcji. | Nr | Nr | Nr | Tak | Nr |
| 1100 | Wpłata na konto odbiorcy | Wykonaj płatność na konto odbiorcy. | Tak | Tak | Tak | Tak | Tak |
| 612 | Dodaj odbiorcę | Ta operacja umożliwia użytkownikowi utworzenie nowego rekordu odbiorcy | Tak | Tak | Tak | Tak† | Nr |
| 603 | Wyczyść dane odbiorcy | Usuń odbiorcę z bieżącej transakcji. | Tak | Tak | Nr | Tak | Nr |
| 602 | Wyszukiwanie odbiorcy | Ta operacja umożliwia użytkownikowi wyszukanie rekordu odbiorcy przez przejście strony wyszukiwania odbiorców w punkcie sprzedaży. | Tak | Tak | Tak | Tak | Nr |
| 609 | Transakcje odbiorcy | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nr |
| 917 | Stan połączenia z bazą danych | Ta operacja umożliwia użytkownikowi wyświetlenie ustawień bieżącego połączenia i przełączenie między trybem online a offline. | Tak | Tak | Tak | Tak | Nr |
| 1200 | Zadeklaruj kwotę początkową | Deklaruj kwotę w szufladzie kasowej na początku dnia lub zmiany. | Tak | Tak | Tak | Tak | Nr |
| 132 | Zastąpienie wpłaty | Zastąp wpłatę domyślną dla zamówień odbiorcy. | Tak | Tak | Nr | Tak\* | Nr |
| 913 | Wyłącz tryb projektowania | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nr |
| 912 | Włącz tryb projektowania | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nr |
| 1217 | Zdekompletuj zestawy | Zdemontuj zestaw do produktów składowych. | Tak | Tak | Tak | Tak | Nr |
| 624 | Wyświetl kwoty zwrotu | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Tak |
| 513 | Wyświetl wartość łączną | Pokaż saldo transakcji na ekranie odbiorcy. | Tak | Tak | Tak | Tak | Nr |
| 623 | Edytowanie odbiorcy | Edytuj szczegóły bieżącego odbiorcy. | Tak | Tak | Nr | Nr | Nr |
| 614 | Edytuj zamówienie odbiorcy | Wycofaj wybrane zamówienie, aby umożliwić jego zmianę w punkcie sprzedaży. | Nr | Nr | Nr | Nr | Nr |
| 615 | Edytuj ofertę | Wycofaj wybraną ofertę, aby umożliwić jej zmianę w punkcie sprzedaży. | Nr | Nr | Nr | Nr | Nr |
| 518 | Konta wypływu/wypłat | Rejestruj pieniądze wyjęte z szuflady kasowej w związku z okazjonalnymi wydatkami. | Tak | Tak | Tak | Tak | Nr |
| 919 | Logowanie rozszerzone | Przypisz lub usuń uprawnienie do logowania się przez skanowanie kodu kreskowego lub zbliżenie karty. | Tak | Tak | Tak | Nr | Nr |
| 1201 | Pozycja zmiennoprzecinkowa | Ta operacja umożliwia użytkownikowi dodanie pieniędzy do bieżącej szuflady lub zmiany. | Tak | Tak | Tak | Tak | Nr |
| 1218 | Wymuś odblokowanie urządzenia peryferyjnego | System wykorzystuję tę operację wewnętrznie do odblokowania urządzeń peryferyjnych punktu sprzedaży. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nr |
| 520 | Saldo na karcie upominkowej | Pokaż saldo karty upominkowej. | Tak | Tak | Nr | Nr | Nr |
| 708 | Dezaktywuj urządzenie | Dezaktywuj bieżące urządzenie, aby nie możny było użyć go jako kasy punktu sprzedaży. | Nr | Nr | Nr | Nr | Nr |
| 517 | Konta wpływu/wpłat | Zarejestruj pieniądze, które są wprowadzane do szuflady kasowej z przyczyn innych niż sprzedaż. | Tak | Tak | Tak | Tak | Nr |
| 801 | Wyszukiwanie w magazynie | Sprawdź ilości dostępne, zamówione i dostępność zapasów (ATP) dla bieżącego sklepu i innych dostępnych lokalizacji. | Tak | Tak | Tak | Nr | Nr |
| 122 | Komentarz do faktury | Ta operacja umożliwia użytkownikowi wprowadzenie komentarza na temat bieżącej transakcji. | Tak | Tak | Nr | Tak | Nr |
| 511 | Wystaw notę kredytową | Wystaw notę kredytową, aby podać załącznik zamiast zwrotu. | Tak | Tak | Nr | Nr | Nr |
| 512 | Wystaw kartę upominkową | Wystaw nową kartę upominkową na określoną kwotę. | Tak | Tak | Nr | Nr | Nr |
| 625 | Wydaj kartę lojalnościową | Wystaw kartę lojalnościową odbiorcy, aby odbiorca mógł uczestniczyć w programie lojalnościowym dla sklepu. | Tak | Tak | Tak | Nr | Nr |
| 300 | Kwota rabatu wiersza | Wprowadź kwotę rabatu dla wiersza towaru w transakcji. Ta operacja jest używana tylko do towarów, na które można udzielać rabatów, i tylko w określonych limitach rabatu. | Tak | Tak | Nr | Tak | Nr |
| 301 | Procent rabatu wiersza | Wprowadź procentu rabatu dla wiersza towaru w transakcji. Ta operacja jest używana tylko do towarów, na które można udzielać rabatów, i tylko w określonych limitach rabatu. | Tak | Tak | Nr | Tak | Nr |
| 703 | Blokowanie rejestru | Zablokuj bieżącą kasę, aby nie można było jej użyć, ale nie wylogowuj bieżącego użytkownika. | Nr | Nr | Nr | Tak | Nr |
| 701 | Wyloguj się | Wyloguj bieżącego użytkownika z kasy. | Tak | Tak | Tak | Tak | Nr |
| 521 | Saldo punktów na karcie lojalnościowej | Pokaż saldo punktów dla określonej karty lojalnościowej. | Tak | Tak | Nr | Nr | Nr |
| 914 | Zminimalizuj okno punktu sprzedaży | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nr |
| 1000 | Otwieranie szuflady | Wykonaj operację „brak sprzedaży” i otwórz aktualnie wybraną szufladę kasy. | Tak | Tak | Tak | Tak | Nr |
| 129 | Zastąpienie podatku dla produktu w wierszu | Zmień podatek w wierszu wybranego towaru na inny określony podatek. | Tak | Tak | Nr | Tak | Nr |
| 1.3.0 | Zastąpienie z listy podatku dla produktu w wierszu | Zmień podatek w wierszu wybranego towaru na podatek wybrany z listy przez użytkownika. | Tak | Tak | Nr | Tak | Nr |
| 127 | Zastąp podatek dla transakcji | Zmień podatek w transakcji na inny określony podatek. | Tak | Tak | Nr | Tak | Nr |
| 128 | Zastąp podatek dla transakcji podatkiem z listy | Zmień podatek w transakcji na podatek wybrany z listy przez użytkownika. | Tak | Tak | Nr | Tak | Nr |
| 131 | Dokument dostawy | Utwórz dokument dostawy dla wybranego zamówienia. | Nr | Nr | Nr | Nr | Nr |
| 710 | Sparuj stację sprzętową | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nr |
| 201 | Płatność kartą | Zaakceptuj płatność kartą kredytową lub debetową. | Tak | Tak | Nr | Tak | Nr |
| 200 | Płatność gotówką | Akceptuj płatność gotówką. | Tak | Tak | Nr | Tak | Nr |
| 206 | Szybka płatność gotówkowa | Dokończ transakcję za pomocą jednego dotknięcia i zaakceptuj należną kwotę w gotówce (odliczona kwota). | Tak | Tak | Nr | Tak | Nr |
| 204 | Płatność czekiem | Akceptuj płatność czekiem. | Tak | Tak | Nr | Tak | Nr |
| 213 | Płatność notą kredytową | Akceptuj notę uznaniową (załącznik) wystawioną przez sklep. | Tak | Tak | Nr | Nr | Nr |
| 203 | Płatność w walucie obcej | Akceptuj płatność w różnych walutach. | Tak | Tak | Nr | Tak | Nr |
| 202 | Płatność z konta odbiorcy | Obciąż kwotą transakcji konto odbiorcy. Ta metoda płatności jest niedostępna dla wpłat za zamówienia odbiorcy. | Tak | Tak | Nr | Nr | Nr |
| 214 | Płatność kartą upominkową | Zaakceptuj kartę upominkową wydaną przez sklep. | Tak | Tak | Nr | Nr | Nr |
| 207 | Płatność kartą lojalnościową | Zaakceptuj płatność kartą lojalnościową i wykorzystaj punkty na kwalifikujące się produkty. | Tak | Tak | Nr | Nr | Nr |
| 634 | Historia płatności | Pokaż historię płatności klienta dla aktualnego zamówienia odbiorcy. | Tak | Tak | Nr | Nr | Nr |
| 803 | Pobranie i przyjęcie | Otwórz stronę **Pobranie i przyjęcie**, na której można wybrać zamówienia do pobrania i odbioru w sklepie. | Tak | Tak | Tak | Nr | Nr |
| 632 | Odbierz wszystkie produkty | Ustaw metodę realizacji na **Odbiór w sklepie** dla wszystkich wierszy. | Tak | Tak | Nr | Tak\* | Nr |
| 631 | Odbierz zaznaczone produkty | Ustaw metodę realizacji na **Odbiór w sklepie** dla wybranych wierszy. | Tak | Tak | Nr | Tak\* | Nr |
| 400 | Wyskakujące okienko menu | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nr |
| 101 | Sprawdzanie ceny | Ta operacja umożliwia użytkownikowi wyszukanie ceny określonego produktu. | Tak | Tak | Tak | Tak | Nr |
| 104 | Ręczna zmiana ceny | Zastąp cenę produktu, jeśli konfiguracja produktu zezwala na zastąpienia ceny. | Tak | Tak | Nr | Tak | Nr |
| 1058 | Drukuj częściowy raport obrachunkowy sprzedaży częściowej | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Tak |
| 1059 | Drukuj obrachunkowy końcowy raport sprzedaży | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Tak |
| 927 | Drukuj etykietę pozycji | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nr |
| 926 | Drukuj etykietę półki | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nr |
| 1056 | Drukuj częściowy raport sprzedaży | Drukuj częściowy raport sprzedaży dla bieżącej zmiany. | Tak | Tak | Tak | Nr | Nr |
| 103 | Komentarz do produktu | Dodaj komentarz do wybranego wiersza towaru w transakcji. | Tak | Tak | Nr | Tak | Nr |
| 100 | Sprzedaż produktu | Dodaj określony produkt do transakcji. | Tak | Tak | Tak | Tak | Nr |
| 108 | Wyszukiwanie produktu | Ta operacja umożliwia użytkownikowi wyszukanie produktu przez przejście strony wyszukiwania produktów w punkcie sprzedaży. | Tak | Tak | Tak | Tak | Nr |
| 633 | Data ważności oferty | Ta operacja umożliwia użytkownikowi wyświetlenie lub zmodyfikowanie daty ważności oferty sprzedaży. | Tak | Tak | Nr | Tak\* | Nr |
| 627 | Oblicz ponownie | Oblicz ponownie wszystkie wiersze zamówienia odbiorcy i podatki, na podstawie bieżącej konfiguracji. | Tak | Tak | Nr | Tak\* | Nr |
| 515 | Odwołaj zamówienie | Ta operacja umożliwia użytkownikowi wyszukanie i wycofanie zamówień odbiorców i ofert sprzedaży. | Tak | Tak | Tak | Nr | Nr |
| 504 | Wznów transakcję | Ta operacja umożliwia użytkownikowi wycofanie wcześniej zawieszone transakcji z bieżącego sklepu. | Tak | Tak | Nr | Tak‡ | Nr |
| 305 | Zrealizuj punkty lojalnościowe | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Tak |
| 635 | Zwróć opłaty transportowe | Ta operacja umożliwia użytkownikowi zwrócenie opłat transportowych za anulowane zamówienie. | Nr | Nr | Nr | Nr | Nr |
| 644 | Usuń kod kuponu | Monituj użytkownika o usunięcie kuponów, przez zaznaczenie ich na liście kuponów, które są aktualnie skojarzone z transakcją. | Tak | Tak | Nr | Tak | Nr |
| 1057 | Ponowne drukowanie raportu końcowego | Wydrukuj ponownie raport końcowy sprzedaży dla poprzedniej lub wybranej zmiany. | Tak | Tak | Tak | Nr | Nr |
| 1216 | Resetuj hasło | Ta operacja umożliwia użytkownikowi z uprawnieniami do resetowania hasła zresetowanie hasła dla pracownika za pomocą hasła tymczasowego. | Tak | Tak | Tak | Nr | Nr |
| 109 | Zwrot produktu | Dokonaj zwrotu poszczególnych produktów. Następny zeskanowany produkt jest wyświetlany jako zwrócony i ma ujemną cenę i ilość. | Tak | Tak | Nr | Tak | Nr |
| 114 | Transakcja zwrotu | Wycofaj poprzednią transakcję według jej numeru paragonu, aby zwrócić niektóre lub wszystkie produkty. | Tak | Tak | Tak | Tak§ | Nr |
| 1211 | Przekazanie pieniędzy do sejfu | Przekazać pieniądze z kasy do sejfu. | Tak | Tak | Tak | Tak | Nr |
| 516 | Faktura sprzedaży | Ta operacja umożliwia odbiorcy dokonanie płatności za wybraną fakturę sprzedaży. | Tak | Tak | Nr | Nr | Nr |
| 502 | Sprzedawca | Ta operacja umożliwia użytkownikowi ustawienie wartości opcji **Osoba przyjmująca sprzedaż** w zamówieniu sprzedaży dla zamówień odbiorców w punkcie sprzedaży. | Tak | Tak | Nr | Tak\* | Nr |
| 2000 | Zarządzanie harmonogramem | Ta operacja umożliwia użytkownikowi tworzenie, modyfikowanie lub wyświetlanie harmonogramów pracowników. | Tak | Tak | Tak | Nr | Nr |
| 2001 | Planowanie żądań | Ta operacja umożliwia użytkownikowi zażądanie czasu wolnego, zamianę zmian lub zaoferowanie zmian innym pracownikom. | Tak | Tak | Tak | Nr | Nr |
| 622 | Wyszukaj zamówienia | Ta operacja umożliwia użytkownikom wstępne skonfigurowanie przycisków punktu sprzedaży w celu wyszukiwania według pozycji, odbiorcy lub kategorii. | Tak | Tak | Tak | Tak | Nr |
| 1213 | Wyszukaj adres wysyłkowy | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nr |
| 709 | Wybierz stację sprzętową | Ta operacja umożliwia użytkownikowi wybranie stacji sprzętowej z listy dostępnych stacji sprzętowych. | Tak | Tak | Tak | Tak | Nr |
| 637 | Ustaw domyślnego przedstawiciela handlowego w transakcji | Ta operacja umożliwia użytkownikowi wybranie jednej z uprawnionych grup prowizji sprzedaży (przedstawiciele handlowi) jako domyślnego przedstawiciela handlowego dla wierszy dodanych później. | Tak | Tak | Nr | Tak | Nr |
| 105 | Ustaw ilość | Zmień ilość w wierszu towaru w transakcji. | Tak | Tak | Nr | Tak | Nr |
| 638 | Ustaw przedstawiciela handlowego w wierszu | Ta operacja umożliwia użytkownikowi wybranie jednej z uprawnionych grup prowizji sprzedaży (przedstawiciele handlowi) dla aktualnie wybranego wiersza. | Tak | Tak | Nr | Tak | Nr |
| 630 | Wyślij wszystkie produkty | Ustaw tryb dostawy na **Wysyłka** dla wszystkich pozycji w wierszu. | Tak | Tak | Nr | Tak\* | Nr |
| 629 | Wyślij zaznaczone produkty | Ustaw tryb dostawy na **Wysyłka** dla wybranych wierszy. | Tak | Tak | Nr | Tak\* | Nr |
| 918 | Pokaż zmiany z ukryciem raportu | Pokaż listę zmian z ukryciem raportu. | Tak | Tak | Tak | Nr | Nr |
| 115 | Pokaż arkusz | Pokaż arkusz sklepu. Można wyświetlić transakcje, ponownie wydrukować paragony i paragony za upominek i wycofać do zwrotu. | Tak | Tak | Tak | Tak\*\* | Nr |
| 802 | Inwentaryzacja | Ta operacja umożliwia użytkownikowi utworzenie lub zmodyfikowania arkuszy inwentaryzacji dla magazynu fizycznego lub liczby cykli. | Tak | Tak | Tak | Nr | Nr |
| 401 | Menu podrzędne | Ta operacja umożliwia wyświetlenie innej połączonej siatki przycisków. | Tak | Tak | Tak | Tak | Nr |
| 1054 | Zawieszenie zmiany | Zawieś bieżącą zmianę, aby można było uaktywnić nową lub inną zmianę na bieżącej kasie. | Tak | Tak | Tak | Nr | Nr |
| 503 | Zawieś transakcję | Zawieś bieżącą transakcję sprzedaży, aby wycofać ją ponownie później w sklepie. | Tak | Tak | Nr | Tak‡ | Nr |
| 1004 | Rejestrator zadań | Otwórz Rejestrator zadań, aby zarejestrować kroki procedury w punkcie sprzedaży. | Nr | Nr | Nr | Tak | Nr |
| 1052 | Deklaracja środków płatniczych | Ta operacja umożliwia użytkownikowi określenie kwoty pieniężnej w szufladzie dla każdej liczonej metody płatności. | Tak | Tak | Tak | Tak | Nr |
| 1210 | Pobranie środków płatniczych | Ta operacja umożliwia użytkownikowi usunięcie pieniędzy z bieżącej szuflady lub zmiany. | Tak | Tak | Tak | Tak | Nr |
| 920 | Zegar | Ta operacja umożliwia użytkownikowi wbicie początku i końca zmian oraz przerw. | Tak | Tak | Tak | Nr | Nr |
| 302 | Kwota rabatu ogółem | Wprowadź kwotę rabatu transakcji. Ta operacja dotyczy tylko towarów, na które można udzielać rabatów, i tylko w określonych limitach rabatu. | Tak | Tak | Nr | Tak | Nr |
| 303 | Procent rabatu ogółem | Wprowadź procent rabatu transakcji. Ta operacja dotyczy tylko towarów, na które można udzielać rabatów, i tylko w określonych limitach rabatu. | Tak | Tak | Nr | Tak | Nr |
| 501 | Komentarz do transakcji | Dodaj komentarz do bieżącej transakcji. | Tak | Tak | Nr | Tak | Nr |
| 922 | Wyświetlanie szczegółów produktu | Otwórz stronę szczegółów produktu dla aktualnie wybranej pozycji w wierszu. | Tak | Tak | Nr | Tak | Nr |
| 1003 | Wyświetlanie raportów | Pokaż raporty skonfigurowane dla bieżącego użytkownika. | Tak | Tak | Tak | Nr | Nr |
| 921 | Wyświetlanie wpisów zegara | Pokaż wpisy zegara dla wszystkich pracowników w sklepie. | Tak | Tak | Tak | Nr | Nr |
| 211 | Unieważnij płatność | Unieważnij aktualnie wybrany wiersz płatności z transakcji. | Tak | Tak | Nr | Tak | Nr |
| 102 | Unieważnienie produktu | Unieważnij aktualnie wybraną pozycję w wierszu z transakcji. | Tak | Tak | Nr | Tak | Nr |
| 500 | Unieważnij transakcję | Unieważnij bieżącą transakcję. | Tak | Tak | Nr | Tak | Nr |
| 916 | Podstawa przepływu pracy systemu Windows | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nr |
| 924 | Raport X dotyczący kart bankowych | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Tak |

\* Operacja jest dostępna w trybie offline tylko wtedy, gdy tworzone jest zamówienie odbiorcy lub oferta sprzedaży i gdy tworzenie zamówień odbiory i ofert sprzedaży jest skonfigurowane w profilu funkcji punktu sprzedaży. Nie można wykonać tej operacji, gdy zamówienia są tworzone za pomocą usługi Real-time Service lub gdy zamówienia są wycofywane i edytowane.

† Operację można wykonać w trybie offline tylko wtedy, gdy punkt sprzedaży jest skonfigurowany tak, aby umożliwić tworzenie w trybie offline klientów w profilu funkcji punktu sprzedaży.

‡ Gdy punkt sprzedaży działa w trybie offline, zawieszone transakcje można wycofać tylko z bazy danych offline bieżącej kasy. Użytkownicy nie mogą zawiesić ani wycofać transakcji między kasami.

§ Gdy punkt sprzedaży działa w trybie offline do zwrotu można wycofać tylko transakcje w bieżącej bazie danych offline.

\*\* Gdy punkt sprzedaży działa w trybie offline, w arkuszu są widoczne tylko transakcje w bazie danych bieżącego kanału offline.

