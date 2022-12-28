---
title: Zapytanie dotyczące rozliczenia księgi
description: W tym artykule opisano okno zapytań dotyczące rozliczenia księgi
author: kweekley
ms.date: 12/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerClosingSheet
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 33ae49d9503c0a83bda7e0093ab6ef69fb4aef0a
ms.sourcegitcommit: 9f3a60a583da21382a14f32ce146fc9ce03f2a09
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/15/2022
ms.locfileid: "9853143"
---
# <a name="ledger-settlement-inquiry"></a>Zapytanie dotyczące rozliczenia księgi

[!include [banner](../includes/banner.md)]

W tym artykule opisano okno **Zapytanie o rozliczenie księgi**, które można wykorzystać do przeglądania rozliczonych, nierozliczonych lub zarówno rozliczonych, jak i nierozliczonych transakcji księgi dla okresu fiskalnego.

## <a name="view-ledger-settlement-transactions"></a>Wyświetlanie transakcji rozliczeniowych księgi głównej
1.  Wybierz kolejno opcje **Księga główna > Zapytania i raporty > Zapytanie o rozliczenie księgi**.
2.  Użyj pól **Od daty** i **Do daty** lub pola **Odstęp dat**, aby określić zakres dat. Podobnie jak w przypadku zestawienia obrotów i sald, zakres dat musi mieścić się w jednym roku podatkowym.
3.  W polu **Konta główne** wybierz jedno lub więcej kont głównych, dla których chcesz wyświetlić transakcje księgowe. Na liście rozwijanej znajdują się tylko konta główne, które zostały ustawione do rozliczenia księgi głównej na stronie **Parametry księgi głównej**.
4.  Użyj pola **Zestaw wymiarów finansowych**, aby pokazać wymiary finansowe w siatce. Ponieważ konto główne jest wymagane, wartość pola **Konto główne** będzie zawsze wyświetlana jako pierwsza kolumna, nawet jeśli wybierzesz zestaw wymiarów finansowych, który nie zawiera konta głównego.
5.  W polu **Stan** wybierz opcję:
-   **Wszystko** w celu wyświetlenia zarówno rozliczonych, jak i nierozliczonych transakcji
-   **Nierozliczone**, aby wyświetlić tylko transakcje nierozliczone 
-   **Rozliczone**, aby wyświetlić tylko transakcje rozliczone
6.  Wybierz **Pokaż transakcje**. Transakcje księgi pojawiają się w siatce na podstawie wprowadzonych przez Ciebie kryteriów. Wyniki badania możesz wyeksportować do programu Microsoft Excel w celu dalszej analizy. Wybierz i przytrzymaj (lub kliknij prawym przyciskiem myszy) w siatce.

### <a name="column-details"></a>Szczegóły kolumny
Siatka na stronie **Zapytanie o rozliczenie** zawiera następujące kolumny:
-   **Konto główne** – to pole jest wymagane i jest zawsze widoczne.
-   **Wymiary finansowe** – Wymiary finansowe są wyświetlane na podstawie wybranego zestawu wymiarów finansowych.
-   **Data transakcji** – data księgowania transakcji w księdze.
-   **Data pierwotnej transakcji** – Jeśli przeprowadzono zamknięcie roku, a rozliczenie księgi zostało tak skonfigurowane, że zachowuje szczegóły dla konta głównego, nierozliczone transakcje są przenoszone w szczegółach jako bilans otwarcia. Pierwotna data księgowania transakcji w księdze jest przechowywana w polu **Data pierwotnej transakcji**.
-   **Wiek transakcji** – Wartość 0 (zero) dla wszystkich rozliczanych transakcji. W przypadku transakcji nierozliczonych wartość ta jest obliczana jako liczba dni od daty pierwotnej transakcji lub daty transakcji do daty uruchomienia zapytania.
Na przykład transakcja w księdze ma datę transakcji 1 stycznia 2022 roku (1/1/2022) i pierwotną datę transakcji 30 grudnia 2021 roku (30/12/2021). Jeśli zapytanie zostanie przeprowadzone 2 stycznia 2022 roku (2/1/2022) dla roku fiskalnego 2022, wartość **Wiek transakcji** wyniesie 4. Wartość ta jest obliczana jako liczba dni pomiędzy datą pierwotnej transakcji (30/12/2021) a 2/1/2022.

Jeśli nie ma oryginalnej daty transakcji, używana jest data transakcji.
-   **(Inne informacje o transakcji)** – Dodatkowe kolumny zawierają takie informacje, jak numer bonu, opis oraz kwoty debetowe i kredytowe we wszystkich trzech walutach (transakcyjnej, księgowej i sprawozdawczej).
-   **Stan**– ta wartość jest **rozliczona** lub **nierozliczona**.
-   **Identyfikator rozliczenia** – identyfikator przypisany do rozliczonych transakcji.

[![Strona zapytania o rozliczenie księgi](./media/Inquiry1.png)](./media/Inquiry1.png)

 
Pod siatką mogą być wyświetlane sumy.
1.  Wybierz wielokropek (…) po prawej stronie siatki, a następnie wybierz pozycję **Pokaż stopkę**.
2.  Zaznacz i przytrzymaj (lub kliknij prawym przyciskiem myszy) każdą kolumnę kwoty, a następnie wybierz **Grupuj według tej kolumny**, aby pokazać sumy. Sumy są wyświetlane w stopce. Jeśli zapytanie zostanie przefiltrowane tak, aby pokazywało tylko nierozliczone transakcje, możesz wykorzystać sumy do uzgodnienia kwot z saldem próbnym.







