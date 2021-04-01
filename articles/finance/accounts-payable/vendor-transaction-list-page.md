---
title: Strona listy transakcji dostawcy
description: Ten temat zawiera informacje o stronie listy Transakcji dostawcy dostępnej w usłudze Microsoft Dynamics 365 Finance.
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTrans
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 41a8506989add6c7c4a5596892bde442c7c7dff2
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5248190"
---
# <a name="vendor-transactions-list-page"></a>Strona listy transakcji dostawcy

[!include [banner](../includes/banner.md)]

## <a name="view-settlements"></a>Wyświetl rozliczenia

Przycisk **Wyświetl rozliczenia** w okienku akcji zapewnia szybki dostęp do historii rozliczeń oraz szczegółowych informacji na temat transakcji rozliczenia. Można również wyświetlać dodatkowe transakcje, które są powiązane z wybraną transakcją, ponieważ były częścią tego samego rozliczenia albo są płatnościami utworzonymi w tym samym arkuszu płatności.

1. Wybierz kolejno opcje **Rozrachunki z dostawcami \> Wszyscy dostawcy**.
2. Wybierz dostawcę mającego transakcje, a następnie w okienku akcji na karcie **Dostawca** wybierz opcję **Transakcje**.
3. Wybierz transakcję, którą chcesz zbadać, a następnie w okienku akcji wybierz opcję **Wyświetl rozliczenia**.

    Zostanie wyświetlone okno dialogowe **Wyświetl rozliczenia**, w którym widać wybraną transakcję oraz wszystkie dokumenty, które zostały rozliczone względem niej. To okno dialogowe przypomina widok historii rozliczeń, ale zawiera wszystkich powiązane dokumenty.

4. W oknie dialogowym można wykonywać różne zadania. Zaznacz jeden lub więcej załączników, a następnie naciśnij jeden z następujących przycisków:

    - **Wyświetl powiązane** — umożliwia wyświetlenie wszystkich transakcji arkusza płatności i transakcji arkusza finansowego utworzonych przez dostawcę w arkuszach, w których utworzono dokumenty widoczne na liście. Na przykład jeśli płatność jest wyświetlana, wówczas wszystkie płatności w arkuszu płatności, w którym została utworzona, będą widoczne. Jeśli wyświetlane są faktura lub płatność i zostały utworzone w arkuszu finansowym, wówczas wszystkie dokumenty w dzienniku głównym, w którym faktura lub płatność zostały utworzone, będą widoczne. Wszystkie rozliczenia powiązane z listą dokumentów również są wyświetlane. Podczas przeglądania powiązanych płatności etykieta tego przycisku zmienia się na **Wyświetl rozliczenia**. Wybierz opcję **Wyświetl rozliczenia**, a pojawią się tylko transakcje, które były wyświetlane po pierwszym otwarciu okna dialogowego **Wyświetl rozliczenia**.
    - **Wyświetl historię** — wyświetlanie historii rozliczeń dla załączników. Kliknij przycisk **Zamknij**, aby zamknąć okno dialogowe.
    - **Wyświetl księgowanie** — są wyświetlane wszystkie załączniki powiązane z wybranym dokumentem. Kliknij przycisk **Zamknij**, aby zamknąć okno dialogowe.
    - **Eksportuj** — eksportowanie wybranych załączników do programu Microsoft Excel.
    - **Rozlicz transakcje** — ten przycisk jest wyświetlany tylko wtedy, gdy wybrany oryginalny dokument nie został w pełni rozliczony. Po naciśnięciu tego przycisku pojawi się okno dialogowe **Rozlicz transakcje**, w którym można wybrać transakcje do rozliczenia.
    - **Cofnij rozliczenia** — ten przycisk jest wyświetlany tylko wtedy, gdy wybrany oryginalny dokument został w pełni rozliczony. Po naciśnięciu tego przycisku pojawia się okno dialogowe **Cofnij rozliczenia**, gdzie można cofnąć rozliczenia dokonane dla tego dokumentu.

## <a name="global-transactions"></a>Transakcje globalne

Przycisk **Transakcje globalne** jest również wyświetlany na stronie listy **Transakcje dostawcy**. Ten przycisk umożliwia wyświetlenie wszystkich transakcji z wybranym dostawcą we wszystkich firmach. Na stronie listy **Transakcje dostawcy** są pokazane transakcje tylko dla firm, do których odbiorca ma dostęp, na podstawie jego ustawień zabezpieczeń.

Na stronie listy będą wyświetlane wszystkie transakcje z dostawcami, którzy mają ten sam identyfikator jednostki jak dostawca, z którym rozpoczęto proces. Na przykład jeśli dostawca US-001 w jednej firmie ma taki sam identyfikator jednostki, jak dostawca DE-001 w innej firmie, są wyświetlane wszystkie transakcje dla obu identyfikatorów dostawców.

Menu na stronie listy **Transakcje dostawcy** różnią się w zależności od firmy uczestniczącej w transakcji. Na przykład jeśli funkcja jest dostępna tylko w przypadku firm szwajcarskich, opcje menu tej funkcji będą wyświetlane tylko po zaznaczeniu szwajcarskiej transakcji.

Aby przejść do tej funkcji, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Rozrachunki z dostawcami** \> **Wszyscy dostawcy**.
2. Wybierz dostawcę, a następnie w okienku akcji na karcie **Dostawca** w grupie **Transakcje** wybierz opcję **Transakcje globalne**.

## <a name="more-transaction-filters"></a>Więcej filtrów transakcji

Filtr wyświetlania otwartych transakcji został zastąpiony przez nowy filtr umożliwiający wyświetlanie większej liczby kombinacji transakcji. W polu **Pokaż** są dostępne następujące opcje:

- **Wszystkie** — umożliwia wyświetlenie wszystkich transakcji z wybranymi dostawcami (otwartych i zamkniętych).
- **Zamknięte** — pokazywanie tylko transakcji, które zostały w pełni rozliczone i zamknięte.
- **Otwarte** — pokazywanie tylko transakcji, które nie zostały w pełni rozliczone.
- **Otwarte, w tym zamknięte w lub po dniu** — pokazywanie tylko transakcji, które nie zostały w pełni rozliczone według stanu na podany dzień. Po wybraniu tej opcji można zmienić dzień wyświetlany obok filtru. Transakcje, które mają wartość **Data ostatniego rozliczenia** przypadającą w lub po wskazanym dniu, są wyświetlane na liście, nawet jeśli zostały w pełni rozliczone według stanu na bieżący dzień. Jednak wartości salda reprezentują salda na bieżący dzień, a nie na wybrany dzień.

Zaznacz pole wyboru **Ukryj przeszacowanie w walucie**, aby ukryć transakcje przeliczania walut.

## <a name="modify-due-dates-and-discount-dates"></a>Modyfikowanie terminów płatności i dat rabatów

W otwartych transakcjach z odbiorcami można aktualizować terminy płatności i daty rabatu. W wersji 8.1 można dodawać terminy płatności do strony listy **Transakcje dostawcy**. Klikając termin płatności na stronie listy **Transakcje dostawcy**, można również zmienić terminy płatności, daty rabatu, warunki płatności i warunki rabatu gotówkowego w oknie dialogowym **Aktualizacja terminu płatności i dat rabatów gotówkowych**.

### <a name="activate-the-feature"></a>Aktywowanie funkcji

Aby dodać terminy płatności do strony listy **Transakcje dostawcy** i zmienić ustawienia płatności dla transakcji za pomocą okna dialogowego **Aktualizacja terminu płatności i dat rabatów gotówkowych**, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Rozrachunki z dostawcami \> Ustawienia \> Parametry modułu rozrachunków z dostawcami**.
2. Na karcie **Rozliczenia** w opcji **Pokaż termin płatności i zezwalaj na edycję** ustaw wartość **Tak**.
3. Aby umożliwić działanie tej funkcji, dodano nowe pola do transakcji z dostawcami. Te pola będą wypełniane podczas wykonywania nowej transakcji. Ponadto będą wypełniane po otwarciu okna dialogowego **Aktualizacja terminu płatności i dat rabatów gotówkowych**. Jeżeli w opcji **Pokaż termin płatności i zezwalaj na edycję** ustawisz wartość **Tak**, pojawi się okno dialogowe **Aktualizacja informacji o płatnościach**.  Aby natychmiast zaktualizować istniejące transakcje, wybierz opcję **Aktualizuj wszystkie istniejące transakcje**. Alternatywnie aby pola były wypełniane tylko dla nowych transakcji, wybierz opcję **Kontynuuj bez aktualizacji**.

Termin płatności zostanie teraz dodany do strony listy **Transakcje dostawcy**, co ułatwi modyfikowanie terminu płatności i dat rabatu dla transakcji.

### <a name="modify-the-payment-settings"></a>Modyfikowanie ustawień płatności

Na stronie listy **Transakcje dostawcy** są wyświetlane wszystkie transakcje z dostawcą. Po wybraniu terminu płatności za transakcję zostanie wyświetlone okno dialogowe. To okno dialogowe zawiera datę podstawy obliczania terminu płatności i daty rabatu, termin płatności, warunki płatności, warunki rabatu gotówkowego i daty rabatu gotówkowego.

Każde pole podczas edytowania różnie oddziałuje na transakcję:

- **Edytowanie daty podstawy** — termin płatności i daty rabatów zmieniają się tak, jakby data podstawy była datą dokumentu.
- **Edytowanie terminu płatności** — zmienia się tylko termin płatności.
- **Edytowanie dat rabatów** — są zmieniane tylko daty rabatu.
- **Edytowanie warunków płatności** — zmienia się termin płatności na podstawie daty podstawy i warunków płatności.
- **Edytowanie warunków rabatu gotówkowego** — zmieniają się rabaty gotówkowe na podstawie daty podstawy i warunków rabatu gotówkowego.

Po zakończeniu edytowania ustawień płatności kliknij opcję **Zamknij**, aby zapisać wprowadzone zmiany.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]