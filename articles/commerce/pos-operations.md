---
title: Operacje online i offline w punkcie sprzedaży (POS)
description: Ten temat zawiera szczegółowe informacje dotyczące operacji punktu sprzedaży (POS) w Dynamics 365 Commerce. Określa, gdzie w aplikacji można wywołać operacje oraz czy są dostępne w trybie offline..
author: jblucher
ms.date: 11/30/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2017-09-27
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 88daca466e0e01bf3870b6eeee0628e0c159fea3
ms.sourcegitcommit: 971456c197820421f108ad7345001cc1b6c99949
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/01/2021
ms.locfileid: "7875484"
---
# <a name="online-and-offline-point-of-sale-pos-operations"></a>Operacje online i offline w punkcie sprzedaży (POS)

[!include [banner](includes/banner.md)]

Większość akcji wykonywanych przez użytkowników punktu sprzedaży (POS) jest uznawanych za operacje. Operacje są skonfigurowane i zarządzania za pomocą środowiska zaplecza Dynamics 365 Commerce. Do siatki przycisków punktu sprzedaży można dodać wiele operacji. Użytkownicy mogą następnie wybrać przyciski w celu wywołania operacji i wykonania przypisanych do nich funkcji. Inne operacje są częścią głównej aplikacji POS i są wywoływane za pomocą przycisków ekranowych lub jako część innych przepływów pracy lub procesów.

W poniższej tabeli przedstawiono szczegóły dotyczące operacji, które są dostępne w Modern POS i Cloud POS. Tabela umożliwia także określenie, gdzie w aplikacji można wywołać operacje oraz czy są dostępne, gdy punkt sprzedaży działa w trybie offline..

Niektóre operacje nie są obecnie dostępne w Modern POS lub Cloud POS. Niektóre z tych operacji zależą od ustawień regionalnych,, które wymagają dodatkowych rozszerzeń i konfiguracji. Inne to funkcje systemu Microsoft Dynamics AX 2012, które nie są aktualnie obsługiwane.

Poniższe kolumny określają, gdzie można wywołać informacje:

- **Siatka przycisków** — operacje można przypisać do przycisków na siatce przycisków punktu sprzedaży, która jest częścią układu ekranu punktu sprzedaży.
- **Ekran transakcji** — operację można wywołać z siatki przycisków punktu sprzedaży skonfigurowanych na ekranie transakcji punktu sprzedaży.
- **Ekran powitalny** — operację można wywołać z siatki przycisków punktu sprzedaży skonfigurowanych na ekranie powitalnym punktu sprzedaży.

> [!NOTE]
> Operacje wymienione poniżej mają zastosowanie do najnowszej wersji usługi Commerce. Niektóre operacje mogły ulec zmianie lub są niedostępne w poprzednich wersjach.

| Identyfikator | Operacja | opis | Siatka przycisków | Ekran transakcyjny | Ekran powitalny | Dostępne w trybie offline | Specyficzne dla ustawień regionalnych |
|----|-----------|-------------|-------------|--------------------|----------------|-------------------|-----------------|
| 707 | Aktywuj urządzenie | Aktywuj bieżące urządzenie, zezwalając uwierzytelnionemu użytkownikowi podanie informacji o połączeniu oraz przypisanie urządzenia i identyfikatora kasy. | Nie | Nie | Nie | Nie | Nie |
| 134 | Dodaj przynależność | Dodaj wybraną wstępnie przynależność do transakcji. Wybierz przynależność na stronie **Przycisk właściwości**. | Tak | Tak | Nie | Tak | Nie |
| 135 | Dodaj przynależność z listy | Dodawaj przynależność do transakcji przez wybranie jej na liście. | Tak | Tak | Tak | Tak | Nie |
| 137 | Dodaj przynależność do odbiorcy | Dodawanie przynależności do odbiorcy na stronie **Szczegóły odbiorcy**. | Nie | Nie | Nie | Tak | Nie |
| 138 | Usuń przynależność z odbiorcy | Usuwanie przynależności na stronie **Szczegóły odbiorcy**. | Nie | Nie | Nie | Tak | Nie |
| 643 | Dodaj kod kuponu | Dodaj kupon, wprowadzając jego kod w punkcie sprzedaży. | Tak | Tak | Nie | Tak | Nie |
| 141 | Dodaj opłaty z nagłówka | Dodaj opłatę dodatkową do nagłówka zamówienia. | Tak | Tak | Nie | Nie| Nie |
| 141 | Dodaj opłaty z wierszy | Umożliwia dodanie opłaty dodatkowej do wybranego wiersza sprzedaży. | Tak | Tak | Nie | Nie| Nie |
| 117 | Dodawanie karty lojalnościowej | Wyświetl monit dla użytkownika o wprowadzenie numeru karty lojalnościowej, która zostanie dodana do bieżącej transakcji. | Tak | Tak | Nie | Tak | Nie |
| 136 | Dodaj numer seryjny | Ta operacja umożliwia użytkownikowi określenie numeru seryjnego dla aktualnie wybranego produktu. | Tak | Tak | Nie | Tak | Nie |
| 1214 | Dodaj adres wysyłkowy | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie |
| 519 | Dodaj do karty upominkowej | Dodaj pieniądze do określonej karty upominkowej. | Tak | Tak | Nie | Nie | Nie |
| 6000 | Zezwalaj na pomijanie rejestracji fiskalnej | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Tak |
| 1212 | Przekazanie pieniędzy do banku | Rejestruj kwotę pieniędzy wysłaną do banku oraz inne informacje, takie jak numer worka bankowego. | Tak | Tak | Tak | Tak | Nie |
| 923 | Weryfikacja sum banku | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Tak |
| 915 | Pusta operacja | Ta operacja przedstawia dostosowywalny przycisk, który deweloper oprogramowania może programowo zmienić w taki sposób, aby służył do wykonywania dowolnej specjalistycznej operacji wymaganej przez firmę. | Tak | Tak | Tak | Tak | Nie |
| 1053 | Zmiana z ukryciem raportu podczas zamknięcia kasy | Ustaw aktualną zmianę na zmianę z ukryciem raportu i wyloguj użytkownika. Zmiana z ukryciem raportu jest niedostępna dla dodatkowych transakcji ale jest dostępna dla operacji z użyciem szuflady, takich jak pobranie środków płatniczych i deklaracja środków płatniczych. | Tak | Tak | Tak | Nie | Nie |
| 310 | Obliczanie sumy | Gdy obliczanie rabatów jest opóźnione, ta operacja inicjuje obliczanie bieżącej transakcji. | Tak | Tak | Nie | Tak | Nie |
| 642 | Wynieś wszystkie produkty | Ustaw metodę dostawy wszystkich wierszy na **Wyniesienie**. | Tak | Tak | Nie | Tak\* | Nie |
| 641 | Wynieś wybrane produkty | Ustaw metodę dostawy wybranych wierszy na **Wyniesienie**. | Tak | Tak | Nie | Tak\* | Nie |
| 647 | Zmień tryb dostawy | Zmień metodę dostawy dla wstępnie skonfigurowanych wierszy wysyłki sprzedaży. | Tak | Tak | Nie | Nie| Nie |
| 1215 | Zmień hasło | Ta operacja umożliwia użytkownikowi punktu sprzedaży zmianę hasła. | Tak | Tak | Tak | Nie | Nie |
| 123 | Zmień jednostki miary | Zmień jednostkę miary wybranej pozycji w wierszu. | Tak | Tak | Nie | Tak | Nie |
| 639 | Wyczyść domyślnego przedstawiciela handlowego w transakcji | Usuń grupę prowizji sprzedaży (przedstawiciel handlowy) z transakcji. | Tak | Tak | Nie | Tak | Nie |
| 106 | Wyczyszczenie ilości | Zresetuj ilość w aktualnie wybranym wierszu do **1**. | Tak | Tak | Nie | Tak | Nie |
| 640 | Wyczyść przedstawiciela handlowego w wierszu | Usuń grupę prowizji sprzedaży (przedstawiciel handlowy) z aktualnie wybranego wiersza. | Tak | Tak | Nie | Tak | Nie |
| 121 | Wyczyść dane sprzedawcy | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie |
| 1055 | Zamknięcie zmiany | Zamknij bieżącą zmian, wydrukuj Końcowy raport sprzedaży i wyloguj użytkownika z systemu. | Tak | Tak | Tak | Nie | Nie |
| 139 | Sfinalizuj transakcję | Monituje użytkownika o wybranie metodzie płatności | Tak | Tak | Nie | Tak | Nie |
| 925 | Kopiuj czek bankowy | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Tak |
| 620 | Utwórz zamówienie odbiorcy | Konwertuj transakcję punktu sprzedaży na zamówienie odbiorcy. | Tak | Tak | Nie | Tak\* | Nie |
| 621 | Tworzenie oferty | Konwertuj transakcję punktu sprzedaży na ofertę sprzedaży. | Tak | Tak | Nie | Tak\* | Nie |
| 636 | Utwórz transakcję detaliczną | Utwórz standardową transakcję sprzedaży, gdy domyślne zachowanie punktu sprzedaży to utworzenie zamówień odbiorcy. | Tak | Tak | Nie | Tak | Nie |
| 600 | Odbiorca | Dodaj określonego klienta do transakcji. | Nie | Nie | Nie | Tak | Nie |
| 1100 | Wpłata na konto odbiorcy | Wykonaj płatność na konto odbiorcy. | Tak | Tak | Tak | Tak | Tak |
| 612 | Dodaj odbiorcę | Tworzenie rekordu nowego klienta. | Tak | Tak | Tak | Tak† | Nie |
| 603 | Wyczyść dane odbiorcy | Usuń odbiorcę z bieżącej transakcji. | Tak | Tak | Nie | Tak | Nie |
| 602 | Wyszukiwanie odbiorcy | Wyszukaj rekord odbiorcy przez przejście do strony wyszukiwania odbiorców w punkcie sprzedaży. | Tak | Tak | Tak | Tak | Nie |
| 609 | Transakcje odbiorcy | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie |
| 917 | Stan połączenia z bazą danych | Wyświetl ustawień bieżącego połączenia i przełączenie między trybem online a offline. | Tak | Tak | Tak | Tak | Nie |
| 1200 | Zadeklaruj kwotę początkową | Deklaruj kwotę w szufladzie kasowej na początku dnia lub zmiany. | Tak | Tak | Tak | Tak | Nie |
| 132 | Zastąpienie wpłaty | Zastąp wpłatę domyślną dla zamówień odbiorcy. | Tak | Tak | Nie | Tak\* | Nie |
| 913 | Wyłącz tryb projektowania | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie |
| 912 | Włącz tryb projektowania | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie |
| 1217 | Zdekompletuj zestawy | Zdemontuj zestaw do produktów składowych. | Tak | Tak | Tak | Tak | Nie |
| 624 | Wyświetl kwoty zwrotu | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Tak |
| 513 | Wyświetl wartość łączną | Pokaż saldo transakcji na ekranie odbiorcy. | Tak | Tak | Tak | Tak | Nie |
| 623 | Edytowanie odbiorcy | Edytuj szczegóły bieżącego odbiorcy. | Tak | Tak | Nie | Nie | Nie |
| 614 | Edytuj zamówienie odbiorcy | Wycofaj wybrane zamówienie, aby umożliwić jego zmianę w punkcie sprzedaży. | Nie | Nie | Nie | Nie | Nie |
| 615 | Edytuj ofertę | Wycofaj wybraną ofertę, aby umożliwić jej zmianę w punkcie sprzedaży. | Nie | Nie | Nie | Nie | Nie |
| 518 | Konta wypływu/wypłat | Rejestruj pieniądze wyjęte z szuflady kasowej w związku z okazjonalnymi wydatkami. | Tak | Tak | Tak | Tak | Nie |
| 919 | Logowanie rozszerzone | Przypisz lub usuń uprawnienie do logowania się przez skanowanie kodu kreskowego lub zbliżenie karty. | Tak | Tak | Tak | Tak | Nie |
| 1201 | Przyjęcie do kasy | Dodaj pieniądze do bieżącej szuflady lub zmiany. | Tak | Tak | Tak | Tak | Nie |
| 1218 | Wymuś odblokowanie urządzenia peryferyjnego | System wykorzystuję tę operację wewnętrznie do odblokowania urządzeń peryferyjnych punktu sprzedaży. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie |
| 520 | Saldo na karcie upominkowej | Pokaż saldo karty upominkowej. | Tak | Tak | Nie | Nie | Nie |
| 708 | Dezaktywuj urządzenie | Dezaktywuj bieżące urządzenie, aby nie możny było użyć go jako kasy punktu sprzedaży. | Nie | Nie | Nie | Nie | Nie |
| 804 | Operacja przychodząca | Umożliwia dostęp do funkcji zarządzania przychodzącymi zapasami w magazynie sklepu. | Tak | Nie | Tak | Nie| Nie |
| 517 | Konta wpływu/wpłat | Zarejestruj pieniądze, które są wprowadzane do szuflady kasowej z przyczyn innych niż sprzedaż. | Tak | Tak | Tak | Tak | Nie |
| 801 | Wyszukiwanie w magazynie | Sprawdź ilości dostępne, zamówione i dostępność zapasów (ATP) dla bieżącego sklepu i innych dostępnych lokalizacji. | Tak | Tak | Tak | Nie | Nie |
| 122 | Komentarz do faktury | Wprowadź komentarz dotyczący bieżącej transakcji. | Tak | Tak | Nie | Tak | Nie |
| 511 | Wystaw notę kredytową | Wystaw notę kredytową, aby podać załącznik zamiast zwrotu. | Tak | Tak | Nie | Nie | Nie |
| 512 | Wystaw kartę upominkową | Wystaw nową kartę upominkową na określoną kwotę. | Tak | Tak | Nie | Nie | Nie |
| 625 | Wydaj kartę lojalnościową | Wystaw kartę lojalnościową odbiorcy, aby odbiorca mógł uczestniczyć w programie lojalnościowym dla sklepu. | Tak | Tak | Tak | Nie | Nie |
| 300 | Kwota rabatu wiersza | Wprowadź kwotę rabatu dla wiersza towaru w transakcji. Ta operacja jest używana tylko do towarów, na które można udzielać rabatów, i tylko w określonych limitach rabatu. | Tak | Tak | Nie | Tak | Nie |
| 301 | Procent rabatu wiersza | Wprowadź procentu rabatu dla wiersza towaru w transakcji. Ta operacja jest używana tylko do towarów, na które można udzielać rabatów, i tylko w określonych limitach rabatu. | Tak | Tak | Nie | Tak | Nie |
| 703 | Blokowanie rejestru | Zablokuj bieżącą kasę, aby nie można było jej użyć, ale nie wylogowuj bieżącego użytkownika. | Nie | Nie | Nie | Tak | Nie |
| 701 | Wyloguj się | Wyloguj bieżącego użytkownika z kasy. | Tak | Tak | Tak | Tak | Nie |
| 521 | Saldo punktów na karcie lojalnościowej | Pokaż saldo punktów dla określonej karty lojalnościowej. | Tak | Tak | Nie | Nie | Nie |
| 142 | Zarządzanie opłatami | Umożliwia wyświetlanie opłat dodatkowych stosowanych do transakcji i zarządzanie nimi. | Tak | Tak | Nie | Nie| Nie |
| 918 | Zarządzaj zmianami | Wyświetlanie listy zmian aktywnych, zawieszonych i z ukryciem raportu. | Tak | Tak | Tak | Nie | Nie |
| 914 | Zminimalizuj okno punktu sprzedaży | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie |
| 1000 | Otwieranie szuflady | Wykonaj operację „brak sprzedaży” i otwórz aktualnie wybraną szufladę kasy. | Tak | Tak | Tak | Tak | Nie |
| 928 | Realizacja zamówienia | Ta operacja umożliwia użytkownikom pobranie, spakowanie, wysłanie lub odwołanie zamówień pobranych przez sklep. | Tak | Tak | Tak | Nie | Nie |
| 805 | Operacja wychodząca | Umożliwia dostęp do funkcji zarządzania wysyłkami wychodzących zamówień przeniesienia. | Tak | Nie | Tak | Nie| Nie |
| 129 | Zastąpienie podatku dla produktu w wierszu | Zmień podatek w wierszu wybranego towaru na inny określony podatek. | Tak | Tak | Nie | Tak | Nie |
| 1.3.0 | Zastąpienie z listy podatku dla produktu w wierszu | Zmień podatek w wierszu wybranego towaru na podatek wybrany z listy przez użytkownika. | Tak | Tak | Nie | Tak | Nie |
| 127 | Zastąp podatek dla transakcji | Zmień podatek w transakcji na inny określony podatek. | Tak | Tak | Nie | Tak | Nie |
| 128 | Zastąp podatek dla transakcji podatkiem z listy | Zmień podatek w transakcji na podatek wybrany z listy przez użytkownika. | Tak | Tak | Nie | Tak | Nie |
| 131 | Dokument dostawy | Utwórz dokument dostawy dla wybranego zamówienia. | Nie | Nie | Nie | Nie | Nie |
| 710 | Sparuj stację sprzętową | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie |
| 201 | Płatność kartą | Zaakceptuj płatność kartą kredytową lub debetową. | Tak | Tak | Nie | Tak | Nie |
| 200 | Płatność gotówką | Akceptuj płatność gotówką. | Tak | Tak | Nie | Tak | Nie |
| 206 | Szybka płatność gotówkowa | Dokończ transakcję za pomocą jednego dotknięcia i zaakceptuj należną kwotę w gotówce (odliczona kwota). | Tak | Tak | Nie | Tak | Nie |
| 204 | Płatność czekiem | Akceptuj płatność czekiem. | Tak | Tak | Nie | Tak | Nie |
| 213 | Płatność notą kredytową | Akceptuj notę uznaniową (załącznik) wystawioną przez sklep. | Tak | Tak | Nie | Nie | Nie |
| 203 | Płatność w walucie obcej | Akceptuj płatność w różnych walutach. | Tak | Tak | Nie | Tak | Nie |
| 202 | Płatność z konta odbiorcy | Obciąż kwotą transakcji konto odbiorcy. Ta metoda płatności jest niedostępna dla wpłat za zamówienia odbiorcy. | Tak | Tak | Nie | Nie | Nie |
| 214 | Płatność kartą upominkową | Zaakceptuj kartę upominkową wydaną przez sklep. | Tak | Tak | Nie | Nie | Nie |
| 207 | Płatność kartą lojalnościową | Zaakceptuj płatność kartą lojalnościową i wykorzystaj punkty na kwalifikujące się produkty. | Tak | Tak | Nie | Nie | Nie |
| 634 | Historia płatności | Pokaż historię płatności klienta dla aktualnego zamówienia odbiorcy. | Tak | Tak | Nie | Nie | Nie |
| 803 | Pobranie i przyjęcie | Otwórz stronę **Pobranie i przyjęcie**, na której można wybrać zamówienia do pobrania i odbioru w sklepie. | Tak | Tak | Tak | Nie | Nie |
| 632 | Odbierz wszystkie produkty | Ustaw metodę realizacji na **Odbiór w sklepie** dla wszystkich wierszy. | Tak | Tak | Nie | Tak\* | Nie |
| 631 | Odbierz zaznaczone produkty | Ustaw metodę realizacji na **Odbiór w sklepie** dla wybranych wierszy. | Tak | Tak | Nie | Tak\* | Nie |
| 400 | Wyskakujące okienko menu | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie |
| 101 | Sprawdzanie ceny | Ta operacja umożliwia użytkownikowi wyszukanie ceny określonego produktu. | Tak | Tak | Tak | Tak | Nie |
| 104 | Ręczna zmiana ceny | Zastąp cenę produktu, jeśli konfiguracja produktu zezwala na zastąpienia ceny. | Tak | Tak | Nie | Tak | Nie |
| 1058 | Drukuj częściowy raport obrachunkowy sprzedaży częściowej | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Tak |
| 1059 | Drukuj obrachunkowy końcowy raport sprzedaży | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Tak |
| 927 | Drukuj etykietę pozycji | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie |
| 926 | Drukuj etykietę półki | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie |
| 1056 | Drukuj częściowy raport sprzedaży | Drukuj częściowy raport sprzedaży dla bieżącej zmiany. | Tak | Tak | Tak | Nie | Nie |
| 103 | Komentarz do produktu | Dodaj komentarz do wybranego wiersza towaru w transakcji. | Tak | Tak | Nie | Tak | Nie |
| 100 | Sprzedaż produktu | Dodaj określony produkt do transakcji. | Tak | Tak | Tak | Tak | Nie |
| 108 | Wyszukiwanie produktu | Wyszukaj rekord produktu przez przejście do strony wyszukiwania produktów w punkcie sprzedaży. | Tak | Tak | Tak | Tak | Nie |
| 633 | Data ważności oferty | Wyświetl lub zmodyfikuj datę ważności oferty sprzedaży. | Tak | Tak | Nie | Tak\* | Nie |
| 627 | Oblicz ponownie | Oblicz ponownie wszystkie wiersze zamówienia odbiorcy i podatki, na podstawie bieżącej konfiguracji. | Tak | Tak | Nie | Tak\* | Nie |
| 143 | Oblicz ponownie opłaty | Umożliwia ponowne obliczenie opłat automatycznych zastosowanych do zamówienia. | Tak | Tak | Nie | Nie| Nie |
| 515 | Odwołaj zamówienie | Wyszukaj i wycofaj zamówienia odbiorców i oferty sprzedaży. | Tak | Tak | Tak | Nie | Nie |
| 504 | Wznów transakcję | Wycofaj wcześniej zawieszone transakcje z bieżącego sklepu. | Tak | Tak | Nie | Tak‡ | Nie |
| 305 | Zrealizuj punkty lojalnościowe | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Tak |
| 635 | Zwróć opłaty transportowe | Zwróć opłaty transportowe dla anulowanego zamówienia. | Nie | Nie | Nie | Nie | Nie |
| 644 | Usuń kod kuponu | Monituj użytkownika o usunięcie kuponów, przez zaznaczenie ich na liście kuponów, które są aktualnie skojarzone z transakcją. | Tak | Tak | Nie | Tak | Nie |
| 1057 | Ponowne drukowanie raportu końcowego | Wydrukuj ponownie raport końcowy sprzedaży dla poprzedniej lub wybranej zmiany. | Tak | Tak | Tak | Nie | Nie |
| 1216 | Resetuj hasło | Ta operacja umożliwia użytkownikowi z uprawnieniami do resetowania hasła zresetowanie hasła dla pracownika za pomocą hasła tymczasowego. | Tak | Tak | Tak | Nie | Nie |
| 1219 | Otwieranie adresu URL w punkcie sprzedaży | Otwórz skonfigurowany adres URL administratora w punkcie sprzedaży. | Tak | Tak | Tak | Tak | Nie |
| 109 | Zwrot produktu | Dokonaj zwrotu poszczególnych produktów. Następny zeskanowany produkt jest wyświetlany jako zwrócony i ma ujemną cenę i ilość. | Tak | Tak | Nie | Tak | Nie |
| 114 | Transakcja zwrotu | Wycofaj poprzednią transakcję według jej numeru paragonu, aby zwrócić niektóre lub wszystkie produkty. | Tak | Tak | Tak | Tak§ | Nie |
| 1211 | Przekazanie pieniędzy do sejfu | Przekazać pieniądze z kasy do sejfu. | Tak | Tak | Tak | Tak | Nie |
| 516 | Faktura sprzedaży | Ta operacja umożliwia odbiorcy dokonanie płatności za wybraną fakturę sprzedaży. | Tak | Tak | Nie | Nie | Nie |
| 502 | Sprzedawca | Ustaw wartość opcji **Osoba przyjmująca sprzedaż** w zamówieniu sprzedaży dla zamówień odbiorców w punkcie sprzedaży. | Tak | Tak | Nie | Tak\* | Nie |
| 2000 | Zarządzanie harmonogramem | Ta operacja nie jest jeszcze obsługiwana. | Tak | Tak | Tak | Nie | Nie |
| 2001 | Planowanie żądań | Ta operacja nie jest jeszcze obsługiwana. | Tak | Tak | Tak | Nie | Nie |
| 622 | Wyszukaj zamówienia | Ta operacja umożliwia użytkownikom wstępne skonfigurowanie przycisków punktu sprzedaży w celu wyszukiwania według pozycji, odbiorcy lub kategorii. | Tak | Tak | Tak | Tak | Nie |
| 1213 | Wyszukaj adres wysyłkowy | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie |
| 709 | Wybierz aplikację hardware station | Wybierz stację sprzętową z listy dostępnych stacji sprzętowych. | Tak | Tak | Tak | Tak | Nie |
| 637 | Ustaw domyślnego przedstawiciela handlowego w transakcji | Wybierz jedną z uprawnionych grup prowizji sprzedaży (przedstawiciele handlowi) jako domyślnego przedstawiciela handlowego dla wierszy dodanych później. | Tak | Tak | Nie | Tak | Nie |
| 105 | Ustaw ilość | Zmień ilość w wierszu towaru w transakcji. | Tak | Tak | Nie | Tak | Nie |
| 638 | Ustaw przedstawiciela handlowego w wierszu | Wybierz jedną z uprawnionych grup prowizji sprzedaży (przedstawiciele handlowi) dla aktualnie wybranego wiersza. | Tak | Tak | Nie | Tak | Nie |
| 630 | Wyślij wszystkie produkty | Ustaw tryb dostawy na **Wysyłka** dla wszystkich pozycji w wierszu. | Tak | Tak | Nie | Tak\* | Nie |
| 629 | Wyślij zaznaczone produkty | Ustaw tryb dostawy na **Wysyłka** dla wybranych wierszy. | Tak | Tak | Nie | Tak\* | Nie |
| 115 | Pokaż arkusz | Pokaż arkusz sklepu. Można wyświetlić transakcje, ponownie wydrukować paragony i paragony za upominek i wycofać do zwrotu. | Tak | Tak | Tak | Tak\*\* | Nie |
| 802 | Inwentaryzacja | Utwórz lub zmodyfikuj arkusze inwentaryzacji dla magazynu fizycznego lub liczby cykli. | Tak | Tak | Tak | Nie | Nie |
| 401 | Menu podrzędne | Ta operacja umożliwia wyświetlenie innej połączonej siatki przycisków. | Tak | Tak | Tak | Tak | Nie |
| 1054 | Zawieszenie zmiany | Zawieś bieżącą zmianę, aby można było uaktywnić nową lub inną zmianę na bieżącej kasie. | Tak | Tak | Tak | Nie | Nie |
| 503 | Zawieś transakcję | Zawieś bieżącą transakcję sprzedaży, aby wycofać ją ponownie później w sklepie. | Tak | Tak | Nie | Tak‡ | Nie |
| 1004 | Rejestrator zadań | Otwórz Rejestrator zadań, aby zarejestrować kroki procedury w punkcie sprzedaży. | Nie | Nie | Nie | Tak | Nie |
| 1052 | Deklaracja środków płatniczych | Określ kwoty pieniężnej w szufladzie dla każdej liczonej metody płatności. | Tak | Tak | Tak | Tak | Nie |
| 1210 | Pobranie środków płatniczych | Usuń pieniądze z bieżącej szuflady lub zmiany. | Tak | Tak | Tak | Tak | Nie |
| 920 | Zegar | Wbij początek i koniec zmiany roboczej oraz przerw. | Tak | Tak | Tak | Nie | Nie |
| 302 | Kwota rabatu ogółem | Wprowadź kwotę rabatu transakcji. Ta operacja dotyczy tylko towarów, na które można udzielać rabatów, i tylko w określonych limitach rabatu. | Tak | Tak | Nie | Tak | Nie |
| 303 | Procent rabatu ogółem | Wprowadź procent rabatu transakcji. Ta operacja dotyczy tylko towarów, na które można udzielać rabatów, i tylko w określonych limitach rabatu. | Tak | Tak | Nie | Tak | Nie |
| 501 | Komentarz do transakcji | Dodaj komentarz do bieżącej transakcji. | Tak | Tak | Nie | Tak | Nie |
| 922 | Wyświetlanie szczegółów produktu | Otwórz stronę szczegółów produktu dla aktualnie wybranej pozycji w wierszu. | Tak | Tak | Nie | Tak | Nie |
| 1003 | Wyświetlanie raportów | Pokaż raporty skonfigurowane dla bieżącego użytkownika. | Tak | Tak | Tak | Nie | Nie |
| 921 | Wyświetlanie wpisów zegara | Pokaż wpisy zegara dla wszystkich pracowników w sklepie. | Tak | Tak | Tak | Nie | Nie |
| 211 | Unieważnij płatność | Unieważnij aktualnie wybrany wiersz płatności z transakcji. | Tak | Tak | Nie | Tak | Nie |
| 102 | Unieważnienie produktu | Unieważnij aktualnie wybraną pozycję w wierszu z transakcji. | Tak | Tak | Nie | Tak | Nie |
| 500 | Unieważnij transakcję | Unieważnij bieżącą transakcję. | Tak | Tak | Nie | Tak | Nie |
| 916 | Podstawa przepływu pracy systemu Windows | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie |
| 924 | Raport X dotyczący kart bankowych | Ta operacja nie jest obsługiwana. | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Tak |
| 311 | Usuń rabaty systemowe z transakcji | Usuń z transakcji wszystkie rabaty zastosowane przez system, w tym rabaty kuponowe. Nie powoduje usunięcia rabatów ręcznych. | Tak | Tak | Tak | Tak | Nie |
| 312 | Ponowne stosowanie rabatów systemowych | Ponownie zastosuj rabaty systemowe dla transakcji, jeśli zostały one usunięte przy użyciu operacji **Usuń rabaty systemowe z transakcji**. | Tak | Tak | Tak | Tak | Nie |

\* Operacja jest dostępna w trybie offline tylko wtedy, gdy tworzone jest zamówienie odbiorcy lub oferta sprzedaży i gdy tworzenie zamówień odbiory i ofert sprzedaży jest skonfigurowane w profilu funkcji punktu sprzedaży. Nie można wykonać tej operacji, gdy zamówienia są tworzone za pomocą usługi Real-time Service lub gdy zamówienia są wycofywane i edytowane.

† Operację można wykonać w trybie offline tylko wtedy, gdy punkt sprzedaży jest skonfigurowany tak, aby umożliwić tworzenie w trybie offline klientów w profilu funkcji punktu sprzedaży.

‡ Gdy punkt sprzedaży działa w trybie offline, zawieszone transakcje można wycofać tylko z bazy danych offline bieżącej kasy. Użytkownicy nie mogą zawiesić ani wycofać transakcji między kasami.

§ Gdy punkt sprzedaży działa w trybie offline do zwrotu można wycofać tylko transakcje w bieżącej bazie danych offline.

\*\* Gdy punkt sprzedaży działa w trybie offline, w arkuszu są widoczne tylko transakcje w bazie danych bieżącego kanału offline.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
