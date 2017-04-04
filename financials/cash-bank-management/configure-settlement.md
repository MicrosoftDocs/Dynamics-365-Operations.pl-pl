---
title: Konfigurowanie rozliczenia
description: "Sposoby i terminy rozliczania transakcji mogą być złożonymi zagadnieniami, dlatego trzeba dokładnie poznać i poprawnie zdefiniować parametry zgodnie z potrzebami firmy. W tym artykule opisano parametry używane do rozliczeń w modułach dla Rozrachunki z odbiorcami i Rozrachunki z dostawcami."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CustOpenTrans, CustParameters, VendOpenTrans, VendParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14601
ms.assetid: 6b61e08c-aa8b-40c0-b904-9bca4e8096e7
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 6927ed98c82f174a18d3d8821fbdb302801835c4
ms.lasthandoff: 03/31/2017


---

# <a name="configure-settlement"></a>Konfigurowanie rozliczenia

Sposoby i terminy rozliczania transakcji mogą być złożonymi zagadnieniami, dlatego trzeba dokładnie poznać i poprawnie zdefiniować parametry zgodnie z potrzebami firmy. W tym artykule opisano parametry używane do rozliczeń w modułach dla Rozrachunki z odbiorcami i Rozrachunki z dostawcami. 

Następujące parametry wpływają na sposób rozliczenia są przetwarzane w usłudze Microsoft Dynamics 365 dla operacji. Rozliczenie to proces rozliczania faktury względem płatności lub faktury korygującej. Parametry te znajdują się w obszarze **Rozliczenia** na stronach **Parametry modułu rozrachunków z odbiorcami** i **Parametry modułu rozrachunków z dostawcami**.

-   **Automatyczne rozliczanie** — ustaw tę opcję jako **Tak** , jeśli transakcja ma zostać rozliczona automatycznie dla innych otwartych transakcji podczas księgowania. Jeśli ta opcja jest ustawiona jako **Nie**, użytkownicy mogą ręcznie rozliczać transakcji podczas wprowadzania płatności lub później, przy użyciu strony **Rozlicz transakcje**.
-   **Zarządzanie rabatami gotówkowymi** — określ jak [rabat gotówkowy jest obsługiwane podczas nadpłaconych faktury](cash-discount-handling-overpayments.md). Dla nadpłaty rabat gotówkowy można zmniejszyć, mogą być traktowane jako różnica lub może pozostawać na konto dostawcy lub nabywcy.
    -   **Nieokreślony** — kwota rabatu gotówkowego zostanie zmniejszona o kwotę nadpłaty. Zachowanie to stosowane jest zawsze, niezależnie od tego, czy kwota nadpłaty jest większa czy mniejsza od wartości wprowadzonej w polu **Maksymalna nadpłata lub niedopłata**.
    -   **Określony** Kwota nadpłaty jest księgowana na koncie księgowym jako różnica rabatu gotówkowego lub pozostaje jako saldo na koncie odbiorcy lub dostawcy. Zachowanie zależy od tego, czy kwota nadpłaty mieści się w przedziale między 0,00, a kwotą wprowadzoną w polu **Maksymalna nadpłata lub niedopłata** lub czy kwota nadpłaty jest wyższa od kwoty **Maksymalna nadpłata lub niedopłata**.
-   **Maksymalna różnica w groszach** — Umożliwia wprowadzanie maksymalnej dozwolonej różnicy groszowej dla rozliczanych transakcji. Jeśli różnica w groszach jest równa lub mniejsza wartości podanej w tym polu, różnica w groszach jest księgowana na koncie księgowym różnicy w groszach, które jest określony na stronie **Konta dla transakcji automatycznych**.
-   **Maksymalna nadpłata lub niedopłata** — wprowadź kwotę akceptowaną jako niedopłata i nadpłata. Aby obliczać nadpłatę lub niedopłatę podatku, na stronie **Parametry księgi głównej** kliknij **Podatek**, a następnie zaznacz opcję **Nadpłata lub niedopłata podatku**.
    -   Jeśli z powodu nadpłaty/niedopłaty powstają różnice mniejsze niż różnica zdefiniowana w polu **Maksymalna różnica w groszach**, kwota różnicy groszowej jest księgowana na koncie różnic groszowych.
    -   Jeśli z powodu nadpłaty/niedopłaty powstają różnice większe niż różnica zdefiniowana w polu **Maksymalna różnica w groszach**, kwota różnicy groszowej jest księgowana na koncie różnic wybranym dla typu księgowania **Rabat gotówkowy odbiorcy** lub **Rabat gotówkowy dostawcy** na stronie **Konta dla transakcji automatycznych**.
-   **Oblicz rabaty gotówkowe dla częściowych zapłat** — wybierz **Tak**, aby włączyć automatyczne obliczanie rabatów gotówkowych dla płatności częściowych.
    -   Działanie tej opcji zależy od wartości w polu **Użyj rabatu gotówkowego** na stronie **rozliczenia transakcji**. Jeśli ta opcja jest ustawiona jako **Tak**, rabat jest pobierany, gdy w polu **Użyj rabatu gotówkowego** ustawiono opcję **Normalny**. Jeśli w polu **Użyj rabatu gotówkowego** ustawiono opcję **Zawsze**, rabat gotówkowy jest zawsze pobierany, niezależnie od ustawienia tego pola. Jeśli w polu **Użyj rabatu gotówkowego** ustawiono opcję **Nigdy**, rabat gotówkowy nigdy nie jest pobierany, niezależnie od ustawienia tego pola.
    -   Jeśli ta opcja jest ustawiona jako **Tak**, a użytkownik zmieni wartość w polu **Kwota do rozliczenia** na stronie **Rozliczanie transakcji**, rabat jest obliczany automatycznie i wyświetlany jako domyślny wpis w polu **Kwota rabatu gotówkowego do pobrania**.
    -   Jeśli ta opcja jest ustawiona jako **Nie**, a użytkownik zmieni wartość w polu **Kwota do rozliczenia** na stronie **Rozliczanie transakcji**, domyślny wpis w polu **Kwota rabatu gotówkowego do pobrania** wynosi **zero** (0).
-   **Oblicz rabaty gotówkowe dla faktur korygujących** — ustaw tę opcję jako **Tak**, aby automatycznie obliczać rabat gotówkowy dla faktur korygujących. Na stronie Rozrachunki z odbiorcami transakcja faktury korygującej jest ujemną transakcją, która ma wartość w polu **Faktura** na stronie **Faktura niezależna** lub zwrot na stronie **Zamówienie sprzedaży**.
    -   Działanie tej opcji zależy od wartości w polu **Użyj rabatu gotówkowego** na stronie **rozliczenia transakcji**. Jeśli ta opcja jest ustawiona na **tak**, rabat wykonane po *** wykorzystania rabatu gotówkowego *** pole jest ustawione na **normalny**. Po *** wykorzystania rabatu gotówkowego *** pole jest ustawione na **zawsze**, rabat gotówkowy jest zawsze stosowane, bez względu na ustawienie tego pola. Po *** wykorzystania rabatu gotówkowego *** pole jest ustawione na **nigdy**, rabat gotówkowy nigdy nie zostanie podjęta, bez względu na ustawienie tego pola.
    -   Jeśli ta opcja ma wartość **Tak**, a faktura korygująca jest oznaczona na stronie **Rozliczanie transakcji**, rabat jest obliczany automatycznie i wyświetlany jako domyślny wpis w polu **Kwota rabatu gotówkowego do pobrania**.
    -   Jeśli ta opcja jest ustawiona jako **Nie**, a faktura korygująca jest oznaczone na stronie **Rozliczanie transakcji**, domyślnym wpisem w polu **Kwota rabatu gotówkowego** jest **0** (zero).
-   **Konta przeciwstawne rabatów (tylko AP)** — umożliwia zdefiniowanie domyślnego konta księgi rabatu gotówkowego, które ma być używane dla wpisu księgowania dla rabatów gotówkowych.
    -   **Użyj konta głównego dla rabatów dostawcy** — rabat gotówkowy jest księgowany na koncie głównym zdefiniowanym na stronie **ustawienia rabatu gotówkowego**.
    -   **Konta w wierszach faktury** — rabat gotówkowy jest księgowany na kontach księgowych z oryginalnej faktury.
-   **Oznacz wiersze na fakturach niezależnych i notach odsetkowych (tylko AR)** — ustaw tę opcję jako **Tak**, aby uaktywnić przycisk **Oznacz wiersze faktury** na stronach **Wprowadzanie płatności odbiorcy**, **Załącznik arkusza płatności**, i **Rozliczenia transakcji**. Ten przycisk umożliwia użytkownikom oznaczanie poszczególnych wierszy do rozliczenia.
-   **Określanie priorytetów rozliczenia (tylko AR)** — ustaw tę opcję jako **Tak**, aby uaktywnić przycisk **Oznacz według priorytetu** na stronach **wprowadzanie płatności odbiorcy** i **rozliczenia transakcji**. Ten przycisk umożliwia użytkownikom przypisywanie zamówienia wcześniej rozliczenia do transakcji.  Po zastosowaniu kolejność rozliczenia do transakcji kolejność i Alokacja płatności można zmodyfikować przed zaksięgowaniem.
-   **Użyj priorytetu dla rozliczeń automatycznych** — Ustaw tę opcję na **tak** używać kolejność priorytetów zdefiniowanych, gdy transakcje są automatycznie rozliczane. To pole jest dostępne tylko wtedy, gdy **określanie priorytetów rozliczenia** i **automatyczne rozliczanie** opcje są ustawione na **tak**.



