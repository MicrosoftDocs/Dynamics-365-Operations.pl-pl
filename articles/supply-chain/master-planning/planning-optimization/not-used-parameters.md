---
title: Parametry nie są używane przez optymalizację planowania
description: W tym temacie wymieniono parametry, których optymalizacja planowania nie uwzględnia obecnie podczas działania.
author: ChristianRytt
ms.date: 09/02/2021
ms.topic: article
ms.search.form: ReqParameters, ReqGroup, ReqItemTable, ReqPlanSched, EcoResProductDetailsExtended, InventItemOrderSetup, WorkCalendarTable, PdsDispositionMaster
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-06-29
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 61cdbe3d966d06193b1dc5c145233e53be3946ff
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7571072"
---
# <a name="parameters-not-used-by-planning-optimization"></a>Parametry nie są używane przez optymalizację planowania

[!include [banner](../../includes/banner.md)]

W tym temacie wymieniono parametry, których optymalizacja planowania nie uwzględnia obecnie podczas działania. Usługa planowania może pominąć parametr, ponieważ na przykład powiązana funkcja nie jest jeszcze obsługiwana. Parametr może również zostać wycofany z powodu zmian funkcjonalnych.

W poniższych sekcjach przedstawiono parametry, których optymalizacja planowania nie używa na określonych stronach. Wyjaśniono również, dlaczego nie są używane poszczególne parametry.

## <a name="master-planning-parameters-page"></a>Strona Parametry planowania głównego

Optymalizacja planowania nie korzysta z następujących parametrów ani opcji na stronie **Parametry planowania głównego**:

- Karta **Ogólne**:

  - **Bieżący plan według prognozy** – oczekuje na obsługę *prognozy*.
  - **Bieżący statyczny plan główny** — oczekujące wsparcie *Skopiuj statyczny do dynamicznego planu*.
  - **Bieżący dynamiczny plan główny** — oczekujące wsparcie *Skopiuj statyczny do dynamicznego planu*.
  - **Skopiuj kompletny i zaktualizowany statyczny plan główny do dynamicznego planu głównego** — oczekujące wsparcie *Skopiuj statyczny do dynamicznego planu*.
  - **Godzina rozpoczęcia obliczonych opóźnień** — oczekująca obsługa *Obliczonych opóźnień*.
  - **Użyj dynamicznej liczby dni z ujemnym dniem** — Optymalizacja planowania zawsze wykorzystuje podejście *Dynamiczne dni ujemne*.
  - **Kalendarz na dzisiaj** — oczekiwana obsługa *planowania*.
  - **Użycie pamięci podręcznej** — konfiguracja subskrypcji Microsoft Azure obsługuje punkty wydajności.
  - **Liczba zadań w pakiecie zadań pomocnika** — konfiguracja subskrypcji Azure obsługuje punkty wydajności.
  - **Przetwarzanie wstępne: automatycznie filtruj według towarów z bezpośrednim popytem** — konfiguracja subskrypcji Azure obsługuje punkty wydajności.
  - **Przetwarzanie końcowe: automatycznie filtruj według towarów z bezpośrednim popytem** — konfiguracja subskrypcji Azure obsługuje punkty wydajności.
  - **Ilość zamówień w paczce akceptowania** — konfiguracja subskrypcji Azure obsługuje punkty wydajności.
  - **Ilość wątków** — konfiguracja subskrypcji Azure obsługuje punkty wydajności.
  - **Planowanie limitu czasu procesu w kilka minut** — konfiguracja subskrypcji Azure obsługuje punkty wydajności.
  - **Godzina rozpoczęcia planowania** — oczekiwana obsługa *planowania*.

- Karta **planowane zamówienia**:

  - **Czas przyjęcia** — oczekująca obsługa *planowania*.
  - **Produkcja** — oczekująca obsługa *planowania*.
  - Pola w sekcji **Projekt** — oczekiwana obsługa *planowania*.

- Karta **Standardowa aktualizacja**:

  - **Aktualizacja zaznaczania** – oczekiwanie na wsparcie *zatwierdzenia*.
  - **Zatrzymaj proces ujednania w przypadku wystąpienia błędu** — oczekiwanie na wsparcie *zatwierdzenia*.
  - **Grupuj według dostawców** — oczekiwanie na wsparcie *Zatwierdzenia*.
  - **Grupuj według grup kupujących** — oczekiwanie na wsparcie *Zatwierdzenia*.
  - **Grupuj według umowy zakupu** — oczekiwanie na wsparcie *Zatwierdzenia*.
  - **Grupuj według okresów** — oczekiwanie na wsparcie *Zatwierdzenia*.
  - **Znajdź umowy zakupu** — oczekiwanie na wsparcie *Zatwierdzenia*.
  - **Grupuj według priorytetu planowania** — oczekiwanie na wsparcie *Zatwierdzenia*.
  - **Grupuj według okresów** — oczekiwanie na wsparcie *Zatwierdzenia*.

## <a name="coverage-groups-page"></a>Strona Grupy zapotrzebowania

Optymalizacja planowania nie korzysta z następujących parametrów ani opcji na stronie **Grupy zapotrzebowania**:

- Skrócona karta **Ogólne**:

  - **Dni dodatnie** — oczekiwanie na wsparcie *Dni dodatnich*.
  - **Zużycie dostępnych zapasów** – Oczekujące wsparcie *zużycie dostępnych zapasów*.
  - **Użyj określonej wersji BOM lub formuły** — oczekujące wsparcie *Wersje formuł z produktem Co/By*.
  - **Użyj określonej wersji marszruty** — oczekujące wsparcie *Zapotrzebowanie z określonymi wymaganiami BOM lub określonymi trasami*.

- Skrócona karta **Akcja**:

  - **Komunikat akcji** – oczekujące wsparcie *Akcje*.
  - **Ogrodzenie czasu działania** – oczekujące wsparcie *Akcje*.
  - **Marża odroczona** — oczekujące wsparcie *Akcje*.
  - **Marża zaawansowana** — oczekujące wsparcie *Akcje*.
  - **Data podstawy** — oczekujące wsparcie *Akcje*.
  - **Zaawansowana** — oczekujące wsparcie *Akcje*.
  - **Odroczona** — oczekujące wsparcie *Akcje*.
  - **Obniżona** — oczekujące wsparcie *Akcje*.
  - **Podwyższona** — oczekujące wsparcie *Akcje*.
  - **Akcje pochodne** – oczekujące wsparcie *Akcje*.

- Skrócona karta **Inne**:

  - **Granice czasowe zamrożenia (dni)** — *Obsługa zamrożenia czasu* nie jest planowana w Optymalizacji planowania.
  - **Okres rozłożenia BOM (dni)** — oczekujące wsparcie *Planowanie*.
  - **Próg czasowy planowania wydajności (dni)** — oczekujące wsparcie *Planowanie*.
  - **Zatwierdzony okres zapotrzebowania (dni)** — oczekujące wsparcie *Zapotrzebowanie*.
  - **Plan prognozy czasowej** – oczekuje na obsługę *prognozy*.

- Skrócona karta **Opóźnienia**:

  - **Obliczone opóźnienia** — oczekująca obsługa *Obliczonych opóźnień*.
  - **Oblicz horyzont czasowy opóźnień (dni)** — oczekująca obsługa *Obliczonych opóźnień*.

## <a name="item-coverage-page"></a>Na stronie Zapotrzebowanie na towar

Optymalizacja planowania nie korzysta z następujących parametrów ani opcji na stronie **Zapotrzebowanie na towary**:

- Karta **Ogólne**:

  - **Typ zamówienia planowanego** – Optymalizacja planowania nie obsługuje opcji *Kanban* w oczekiwaniu na obsługę *Kanban*.
  - **Granice czasowe zamrożenia (dni)** — *Obsługa zamrożenia czasu* nie jest planowana w Optymalizacji planowania.
  - **Okres rozłożenia BOM (dni)** — oczekujące wsparcie *Planowanie*.
  - **Próg czasowy planowania wydajności (dni)** — oczekujące wsparcie *Planowanie*.
  - **Zatwierdzony okres zapotrzebowania (dni)** — oczekujące wsparcie *Zapotrzebowanie*.
  - **Spełnij minimum** — optymalizacja planowania nie obsługuje opcji *Dzisiejsze daty*, *Pierwszego wydania* i *Horyzoncie czasowego zapotrzebowania*. Zawsze używa *Daty dzisiejszej + czasu zaopatrzenia*.
  - **Okresy minimalne** – Oczekuje na obsługę *minimalnego poziomu zapasów*.
  - **Formuła planowania** – Oczekujące wsparcie *wersje formuł z produktami Co/By*.
  - **Priorytet domyślny** – Oczekujące wsparcie *wersje formuł z produktami Co/By*.
  - **Obecny domyślny** – Oczekujące wsparcie *wersje formuł z produktami Co/By*.
  - **Data zmiany** – Oczekujące wsparcie *wersje formuł z produktami Co/By*.
  - **Zużycie dostępnych zapasów** – Oczekujące wsparcie *zużycie dostępnych zapasów*.

- Karta **Czas realizacji**:

  - **Czas zakupu** — w wersjach usługi Optymalizacja planowania, które są starsze niż wydanie z 6 sierpnia 2021 roku, parametr Optymalizacja planowania używa tego parametru do obliczenia poprawnych dat zamówienia i dostawy, ale nie zapisuje w nim obliczonego czasu realizacji. W późniejszych wersjach usługa korzysta również z obliczonego czasu realizacji w celu ustawienia pola **Czas realizacji** i opcji **Dni robocze** zgodnie z odpowiednim zamówieniem planowanym.
  - **Czas produkcji** — w wersjach usługi Optymalizacja planowania, które są starsze niż wydanie z 6 sierpnia 2021 roku, parametr Optymalizacja planowania używa tego parametru do obliczenia poprawnych dat zamówienia i dostawy, ale nie zapisuje w nim obliczonego czasu realizacji. W późniejszych wersjach usługa korzysta również z obliczonego czasu realizacji w celu ustawienia pola **Czas realizacji** i opcji **Dni robocze** zgodnie z odpowiednim zamówieniem planowanym.
  - **Czas transferu** — w wersjach usługi Optymalizacja planowania, które są starsze niż wydanie z 6 sierpnia 2021 roku, parametr Optymalizacja planowania używa tego parametru do obliczenia poprawnych dat zamówienia i dostawy, ale nie zapisuje w nim obliczonego czasu realizacji. W późniejszych wersjach usługa korzysta również z obliczonego czasu realizacji w celu ustawienia pola **Czas realizacji** i opcji **Dni robocze** zgodnie z odpowiednim zamówieniem planowanym.
  - **Dni robocze** — w wersjach usługi Optymalizacja planowania, które są starsze niż wydanie z 6 sierpnia 2021 roku, parametr Optymalizacja planowania używa tego parametru do obliczenia poprawnych dat zamówienia i dostawy, ale nie zapisuje w nim obliczonego czasu realizacji. W późniejszych wersjach usługa korzysta również z obliczonego czasu realizacji w celu ustawienia pola **Czas realizacji** i opcji **Dni robocze** zgodnie z odpowiednim zamówieniem planowanym.

## <a name="master-plans-page"></a>Strona Plany główne

Optymalizacja planowania nie korzysta z następujących parametrów ani opcji na stronie **Plany główne**:

- Skrócona karta **Ogólne**:

  - **Dołączanie dostępnych zapasów** – Oczekujące wsparcie *zużycie dostępnych zapasów*.
  - **Nadpisanie dostępnych zapasów** – Oczekujące wsparcie *zużycie dostępnych zapasów*.
  - **Zużycie dostępnych zapasów** – Oczekujące wsparcie *zużycie dostępnych zapasów*.
  - **Dołączanie transakcji zapasów** – Oczekujące wsparcie *zużycie dostępnych zapasów*.
  - **Uwzględnij oferty sprzedaży** – oczekiwanie na obsługę *ofert sprzedaży*.
  - **Uwzględnij zapytania ofertowe** — Oczekujące *Prośba o wycenę*.
  - **Użyj dat okresu trwałości** – Oczekiwanie na obsługę *okresów trwałości*.
  - **Uwzględnij plan sprzedaży ciągłej** – Oczekująca obsługa *planowania sprzedaży ciągłej*.
  - **Metoda planowania** — oczekiwana obsługa *planowania*.
  - **Ograniczone właściwości** — oczekująca obsługa *planowania*.
  - **Próg czasowy zdolności planowania wstecznego** — oczekujące wsparcie *Planowanie*.
  - **Ograniczone pojemności** — oczekująca obsługa *planowania*.
  - **Ograniczone czasowe pojemności** — oczekująca obsługa *planowania*.
  - **Skończona pojemność dla zasobów wąskich gardeł** — oczekująca obsługa *planowania*.
  - **Czasowe ogrodzenie przepustowości dla zasobów w wąskim gardle** — oczekująca obsługa *planowania*.
  - **Zamówienia planowana** — optymalizacja planowania korzysta ze stałych sekwencji numerów.
  - **Sesja** — optymalizacja planowania korzysta ze stałych sekwencji numerów.
  - **Ciągły plan** — optymalizacja planowania korzysta ze stałych sekwencji numerów.

- Karta skrócona **Horyzonty czasowe w dniach**:

  - **Zamrożenie** — *Obsługa zamrożenia czasu* nie jest planowana w Optymalizacji planowania.
  - **Eksplozja** — oczekująca obsługa *planowania*.
  - **Plan prognozy czasowej** – dodatkowo oczekuje na obsługę *prognozy*.
  - **Pojemność** — oczekująca obsługa *planowania*.
  - **Ciągły plan** – Oczekująca obsługa *planowania sprzedaży ciągłej*.
  - **Komunikat akcji** – oczekujące wsparcie *Akcje*.
  - **Obliczone opóźnienia** — dodatkowa oczekująca obsługa *Obliczonych opóźnień*.
  - **Sekwencjonowanie** — oczekująca obsługa *Produkcji*.

- Skrócona karta **Obliczone opóźnienia**:

  - **Upewnij się, że planowane zlecenia nie są tworzone przed datą uruchomienia planowania głównego** — oczekująca obsługa *Obliczonych opóźnień*.
  - **Dodaj obliczone opóźnienie do daty zapotrzebowania** (w sekcji **Planowane zamówienia zakupu**) — oczekiwana obsługa *obliczonych opóźnień*.
  - **Dodaj obliczone opóźnienie do daty zapotrzebowania** (w sekcji **Planowane zamówienia produkcji**) — oczekiwana obsługa *obliczonych opóźnień*.
  - **Dodaj obliczone opóźnienie do daty zapotrzebowania** (w sekcji **Planowane zamówienia transferu**) — oczekiwana obsługa *obliczonych opóźnień*.
  - **Dodaj obliczone opóźnienie do daty zapotrzebowania** (w sekcji **Planowane kanban**) — oczekiwana obsługa *obliczonych opóźnień*.

- Skrócona karta **Sekwencjonowanie**:

  - **Sekwencjonowanie planowanych zleceń po planowaniu głównym** — oczekiwana obsługa *sekwencjonowania*.
  - **Typ przedziału** — oczekiwana obsługa *sekwencjonowania*.
  - **Typ okresu** — oczekiwana obsługa *sekwencjonowania*.
  - **Liczba przedziałów w cyklu kampanii** — oczekiwana obsługa *sekwencjonowania*.

## <a name="released-product-details-page"></a>Strona Szczegóły zwolnionego produktu

Optymalizacja planowania nie używa następującej opcji parametru na stronie **Szczegóły wydanego produktu**:

- Skrócona karta **Inżynier**:

  - **Typ produkcji** – Optymalizacja planowania nie obsługuje opcji *Planowanie elementu*, więc oczekuje na obsługę *elementów planowania*.

## <a name="default-order-settings-page"></a>Strona Ustawienia domyślne zamówień

Optymalizacja planowania nie używa następującej opcji parametru na stronie **Domyślne ustawienia zamówień**:

- Skrócona karta **Zamówienie zakupu**:

  - **Czas realizacji zakupu** — w wersjach usługi Optymalizacja planowania, które są starsze niż wydanie z 6 sierpnia 2021 roku, parametr Optymalizacja planowania używa tego parametru do obliczenia poprawnych dat zamówienia i dostawy, ale nie zapisuje w nim obliczonego czasu realizacji. W późniejszych wersjach usługa korzysta również z obliczonego czasu realizacji w celu ustawienia pola **Czas realizacji** i opcji **Dni robocze** zgodnie z odpowiednim zamówieniem planowanym.
  - **Dni robocze** — w wersjach usługi Optymalizacja planowania, które są starsze niż wydanie z 6 sierpnia 2021 roku, parametr Optymalizacja planowania używa tego parametru do obliczenia poprawnych dat zamówienia i dostawy, ale nie zapisuje w nim obliczonego czasu realizacji. W późniejszych wersjach usługa korzysta również z obliczonego czasu realizacji w celu ustawienia pola **Czas realizacji** i opcji **Dni robocze** zgodnie z odpowiednim zamówieniem planowanym.

- Skrócona karta **Zapasy**:

  - **Kontrola daty dostawy** – Optymalizacja planowania nie obsługuje opcji *CTP*, oczekiwanie na obsługę protokołu *CTP*.
  - **Czas realizacji zapasów** — w wersjach usługi Optymalizacja planowania, które są starsze niż wydanie z 6 sierpnia 2021 roku, parametr Optymalizacja planowania używa tego parametru do obliczenia poprawnych dat zamówienia i dostawy, ale nie zapisuje w nim obliczonego czasu realizacji. W późniejszych wersjach usługa korzysta również z obliczonego czasu realizacji w celu ustawienia pola **Czas realizacji** i opcji **Dni robocze** zgodnie z odpowiednim zamówieniem planowanym.
  - **Dni robocze** — w wersjach usługi Optymalizacja planowania, które są starsze niż wydanie z 6 sierpnia 2021 roku, parametr Optymalizacja planowania używa tego parametru do obliczenia poprawnych dat zamówienia i dostawy, ale nie zapisuje w nim obliczonego czasu realizacji. W późniejszych wersjach usługa korzysta również z obliczonego czasu realizacji w celu ustawienia pola **Czas realizacji** i opcji **Dni robocze** zgodnie z odpowiednim zamówieniem planowanym.

## <a name="working-time-calendars-page"></a>Strona Kalendarze czasu pracy

Optymalizacja planowania nie używa następującego parametru na stronie **Kalendarze czasu pracy**:

- **Kalendarz podstawowy** — oczekiwana obsługa *kalendarzy podstawowych*.

## <a name="batch-disposition-master-page"></a>Strona Wzorzec dyspozycji partii

Optymalizacja planowania nie korzysta z następujących parametrów ani opcji na stronie **Wzorzec dyspozycji partii**:

- Skrócona karta **Ustawienia**:

  - **Do dyspozycji** — oczekiwana obsługa *Kody dyspozycji partii*.
