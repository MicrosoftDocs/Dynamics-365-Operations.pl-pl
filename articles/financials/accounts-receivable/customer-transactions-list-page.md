---
title: Strona listy transakcji odbiorcy
description: Ten temat zawiera informacje o stronie listy Transakcje odbiorcy dostępnej w programie Microsoft Dynamics 365 for Finance and Operations.
author: mikefalkner
manager: aolson
ms.date: 08/28/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: b9936a66cc8c8abb24601dae91dcfca77e4f58a4
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "341702"
---
# <a name="customer-transactions-list-page"></a>Strona listy transakcji odbiorcy

[!include [banner](../includes/banner.md)]

## <a name="view-settlements"></a>Wyświetl rozliczenia

Przycisk **Wyświetl rozliczenia** w okienku akcji zapewnia szybki dostęp do historii rozliczeń oraz szczegółowych informacji na temat transakcji rozliczenia. Można również wyświetlać dodatkowe transakcje, które są powiązane z wybraną transakcją, ponieważ były częścią tego samego rozliczenia albo są płatnościami utworzonymi w tym samym arkuszu płatności.

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Wszyscy odbiorcy**.
2. Wybierz odbiorcę mającego transakcje, a następnie w okienku akcji na karcie **Odbiorca** wybierz opcję **Transakcje**.
3. Wybierz transakcję, którą chcesz zbadać, a następnie w okienku akcji wybierz opcję **Wyświetl rozliczenia**.

    Zostanie wyświetlone okno dialogowe **Wyświetl rozliczenia**, w którym widać wybraną transakcję oraz wszystkie dokumenty, które zostały rozliczone względem niej. To okno dialogowe przypomina widok historii rozliczeń, ale zawiera wszystkich powiązane dokumenty.

4. W oknie dialogowym można wykonywać różne zadania. Zaznacz jeden lub więcej załączników, a następnie naciśnij jeden z następujących przycisków:

    - **Wyświetl powiązane** — umożliwia wyświetlenie wszystkich transakcji arkusza płatności i transakcji arkusza finansowego utworzonych w arkuszach, w których utworzono dokumenty widoczne na liście. Na przykład jeśli płatność jest wyświetlana, wówczas wszystkie płatności w arkuszu płatności, w którym została utworzona, będą widoczne. Jeśli wyświetlane są faktura lub płatność i zostały utworzone w arkuszu finansowym, wówczas wszystkie dokumenty w dzienniku głównym, w którym faktura lub płatność zostały utworzone, będą widoczne. Wszystkie rozliczenia powiązane z listą dokumentów również są wyświetlane. Podczas przeglądania powiązanych płatności etykieta tego przycisku zmienia się na **Wyświetl rozliczenia**. Wybierz opcję **Wyświetl rozliczenia**, a pojawią się tylko transakcje, które były wyświetlane po pierwszym otwarciu okna dialogowego **Wyświetl rozliczenia**.
    - **Wyświetl historię** — wyświetlanie historii rozliczeń dla załączników. Kliknij przycisk **Zamknij**, aby zamknąć okno dialogowe.
    - **Wyświetl księgowanie** — są wyświetlane wszystkie załączniki powiązane z wybranym dokumentem. Kliknij przycisk **Zamknij**, aby zamknąć okno dialogowe.
    - **Eksportuj** — eksportowanie wybranych załączników do programu Microsoft Excel.
    - **Rozlicz transakcje** — ten przycisk jest wyświetlany tylko wtedy, gdy wybrany oryginalny dokument nie został w pełni rozliczony. Po naciśnięciu tego przycisku pojawi się okno dialogowe **Rozlicz transakcje**, w którym można wybrać transakcje do rozliczenia.
    - **Cofnij rozliczenia** — ten przycisk jest wyświetlany tylko wtedy, gdy wybrany oryginalny dokument został w pełni rozliczony. Po naciśnięciu tego przycisku pojawia się okno dialogowe **Cofnij rozliczenia**, gdzie można cofnąć rozliczenia dokonane dla tego dokumentu.

## <a name="global-transactions"></a>Transakcje globalne

Przycisk **Transakcje globalne** jest również wyświetlany na stronie listy **Transakcje odbiorcy**. Ten przycisk umożliwia wyświetlenie wszystkich transakcji z wybranym odbiorcą we wszystkich firmach. Na stronie listy **Transakcje odbiorcy** są pokazane transakcji tylko dla firm, do których odbiorca ma dostęp, na podstawie jego ustawień zabezpieczeń.

Na stronie listy są wyświetlane wszystkie transakcje z odbiorcami, którzy mają ten sam identyfikator jednostki jak odbiorca, z którym rozpoczęto proces. Na przykład jeśli odbiorca US-001 w jednej firmie ma taki sam identyfikator jednostki, jak odbiorca DE-001 w innej firmie, są wyświetlane wszystkie transakcje dla obu identyfikatorów odbiorców.

Menu na stronie listy **Transakcje odbiorcy** różnią się w zależności od firmy uczestniczącej w transakcji. Na przykład jeśli funkcja jest dostępna tylko w przypadku firm szwajcarskich, opcje menu tej funkcji będą wyświetlane tylko po zaznaczeniu szwajcarskiej transakcji.

Aby przejść do tej funkcji, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Wszyscy odbiorcy**.
2. Wybierz odbiorcę, a następnie w okienku akcji na karcie **Odbiorca** w grupie **Transakcje** wybierz opcję **Transakcje globalne**.

## <a name="more-transaction-filters"></a>Więcej filtrów transakcji 

Filtr wyświetlania otwartych transakcji został zastąpiony przez nowy filtr umożliwiający wyświetlanie większej liczby kombinacji transakcji. W polu **Pokaż** są dostępne następujące opcje:

- **Wszystkie** — umożliwia wyświetlenie wszystkich transakcji z wybranymi odbiorcami (otwartych i zamkniętych).
- **Zamknięte** — pokazywanie tylko transakcji, które zostały w pełni rozliczone i zamknięte.
- **Otwarte** — pokazywanie tylko transakcji, które nie zostały w pełni rozliczone.
- **Otwarte, w tym zamknięte w lub po dniu** — pokazywanie tylko transakcji, które nie zostały w pełni rozliczone według stanu na podany dzień. Po wybraniu tej opcji można zmienić dzień wyświetlany obok filtru. Transakcje, które mają wartość **Data ostatniego rozliczenia** przypadającą w lub po wskazanym dniu, są wyświetlane na liście, nawet jeśli zostały w pełni rozliczone według stanu na bieżący dzień. Jednak wartości salda reprezentują salda na bieżący dzień, a nie na wybrany dzień.

Zaznacz pole wyboru **Ukryj przeszacowanie w walucie**, aby ukryć transakcje przeliczania walut.

## <a name="modify-due-dates-and-discount-dates"></a>Modyfikowanie terminów płatności i dat rabatów

W otwartych transakcjach z odbiorcami można aktualizować terminy płatności i daty rabatu. W wersji 8.1 można dodawać terminy płatności do strony listy **Transakcje odbiorcy**. Klikając termin płatności na stronie listy **Transakcje odbiorcy**, można również zmienić terminy płatności, daty rabatu, warunki płatności i warunki rabatu gotówkowego w oknie dialogowym **Aktualizacja terminu płatności i dat rabatów gotówkowych**.

### <a name="activate-the-feature"></a>Aktywowanie funkcji

Aby dodać terminy płatności do strony listy **Transakcje odbiorcy** i zmienić ustawienia płatności dla transakcji za pomocą okna dialogowego **Aktualizacja terminu płatności i dat rabatów gotówkowych**, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Ustawienia \> Parametry modułu rozrachunków z odbiorcami**.
2. Na karcie **Rozliczenia** w opcji **Pokaż termin płatności i zezwalaj na edycję** ustaw wartość **Tak**.
3. Aby umożliwić działanie tej funkcji, dodano nowe pola do transakcji z odbiorcami. Te pola będą wypełniane podczas wykonywania nowej transakcji. Ponadto będą wypełniane po otwarciu okna dialogowego **Aktualizacja terminu płatności i dat rabatów gotówkowych**. Jeżeli w opcji **Pokaż termin płatności i zezwalaj na edycję** ustawisz wartość **Tak**, pojawi się okno dialogowe **Aktualizacja informacji o płatnościach**.  Aby natychmiast zaktualizować istniejące transakcje, wybierz opcję **Aktualizuj wszystkie istniejące transakcje**. Alternatywnie aby pola były wypełniane tylko dla nowych transakcji, wybierz opcję **Kontynuuj bez aktualizacji**.

Termin płatności zostanie teraz dodany do strony listy **Transakcje odbiorcy**, co ułatwi modyfikowanie terminu płatności i dat rabatu dla transakcji.

### <a name="modify-the-payment-settings"></a>Modyfikowanie ustawień płatności

Na stronie listy **Transakcje odbiorcy** są wyświetlane wszystkie transakcje z odbiorcą. Po wybraniu terminu płatności za transakcję zostanie wyświetlone okno dialogowe **Aktualizacja terminu płatności i dat rabatów gotówkowych**. To okno dialogowe zawiera datę podstawy obliczania terminu płatności i daty rabatu, termin płatności, warunki płatności, warunki rabatu gotówkowego i daty rabatu gotówkowego.

Każde pole podczas edytowania różnie oddziałuje na transakcję:

- **Edytowanie daty podstawy** — termin płatności i daty rabatów zmieniają się tak, jakby data podstawy była datą dokumentu.
- **Edytowanie terminu płatności** — zmienia się tylko termin płatności.
- **Edytowanie dat rabatów** — są zmieniane tylko daty rabatu.
- **Edytowanie warunków płatności** — zmienia się termin płatności na podstawie daty podstawy i warunków płatności.
- **Edytowanie warunków rabatu gotówkowego** — zmieniają się rabaty gotówkowe na podstawie daty podstawy i warunków rabatu gotówkowego.

Po zakończeniu edytowania ustawień płatności kliknij opcję **Zamknij**, aby zapisać wprowadzone zmiany.
