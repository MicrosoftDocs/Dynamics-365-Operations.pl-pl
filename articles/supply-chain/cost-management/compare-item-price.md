---
title: Raport magazynowy porównania cen pozycji
description: Sposób generowania raportu magazynowego porównania cen pozycji, a następnie przeglądania i/lub eksportowania wyniku.
author: JennySong-SH
ms.date: 08/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace, InventItemPriceCompareStorage, InventItemPriceCompareStorageDetailsChart, InventItemPriceCompareStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2020-03-01
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: c6373679299b68413d75236ca8cc18ceba03e091
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/23/2022
ms.locfileid: "9334994"
---
# <a name="compare-item-prices-storage-report"></a>Raport magazynowy porównania cen pozycji

[!include [banner](../includes/banner.md)]

W tym artykule wyjaśniono, jak uruchomić raport **magazynowy porównania cen pozycji** i udostępnić go cyfrowo jako stronę interaktywną w systemie Dynamics 365 Supply Chain Management lub w postaci wyeksportowanego dokumentu w dowolnym z kilku formatów.

Podczas wyświetlania raportu w przeglądarce kolumny i salda zagregowane są dynamicznie dostosowywane w zależności od skonfigurowanego układu. Można posortować wyniki, przefiltrować je, przejść do kolejnych danych i wykonać inne zadania.

Wyniki raportu są przechowywane w jednostce danych **Porównaj ceny towaru**, która umożliwia filtrowanie i eksportowanie wyników do formatu, takiego jak CSV lub Microsoft Excel.

Raport **porównania cen magazynowych dla towaru** jest przydatny w przypadkach, gdy dane wyjściowe zawierają wiele wierszy. Na przykład produkcja będzie zawierać wiele wierszy, jeśli w wersji ceny znajduje się więcej niż 40 000 towarów oczekujących cenę pozycji.

## <a name="turn-the-compare-item-prices-storage-feature-on-or-off"></a>Włącz lub wyłącz funkcję przechowywania Porównania cen pozycji

Aby używać tej funkcji, należy ją włączyć dla systemu. Od wersji 10.0.29 Supply Chain Management funkcja jest obowiązkowa i nie można jej wyłączyć. Jeśli używasz wersji starszej niż 10.0.29, administratorzy mogą włączyć lub wyłączyć tę funkcję, wyszukując funkcję *Porównaj magazyn cen pozycji* w obszarze roboczym [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="generate-a-compare-item-prices-storage-report"></a>Generowanie raportu magazynowego porównania cen pozycji

Wykonaj poniższe kroki, aby wygenerować i zapisać **raport dotyczący porównania cen magazynowych pozycji**:

1. Umożliwia przejście do **Zarządzani kosztem > Zapytania i raporty > Raporty wstępnie określonych kosztów > Magazynowe porównanie cen pozycji**.

1. Wybierz opcję **nowy**, aby otworzyć okno **porównanie cen pozycji**. Aby określić, które ceny mają być porównywane w raporcie, należy skonfigurować następujące opcje:

    - Ma skróconej karcie **Parametry** podaj unikalną **Nazwę** dla raportu i użyj pól sekcji **Oczekujące ceny do porównania** i **Ceny użyte do porównania** do określenia, które ceny i daty porównać.
    - Na skróconej karcie **Rekordy do uwzględnienia** należy skonfigurować filtry i ograniczenia w celu zdefiniowania danych, które mają zostać uwzględnione w raporcie.
    - W skróconej karcie **Uruchom w tle** określ, kiedy, jak i z jaką częstotliwością ma być generowany raport.
    > [!NOTE]
    > Ten raport jest zawsze wykonywany w ramach zadania wsadowego.

1. Wybierz przycisk **OK**, aby zastosować ustawienia i zamknąć okienko.

1. Po zakończeniu zadania wsadowego zostanie ono wyświetlone na stronie **porównywanie cen zapasów**. Może być konieczne odświeżenie strony, aby wyświetlić raport.

## <a name="explore-the-compare-item-prices-storage-report"></a>Eksploracja raportu magazynowego porównania cen pozycji

Po wygenerowaniu raportu można go przeglądać i eksplorować w dowolnym momencie w następujący sposób:

1. Umożliwia przejście do **Zarządzani kosztem > Zapytania i raporty > Raporty wstępnie określonych kosztów > Magazynowe porównanie cen pozycji**.

1. Wybierz raport z listy.

1. Wykonaj jedną z następujących czynności:

    - Wybierz **Omówienie**, by wyświetlić przegląd wyników raportu.
    - Wybierz **Wyświetl szczegóły**, aby uzyskać bardziej szczegółowy widok raportu

1. Po otwarciu wybranego widoku można wykonać następujące czynności:

    - Wybierz niemal dowolny nagłówek kolumny, aby posortować lub przefiltrować tabelę według wartości w tej kolumnie, podobnie jak w przypadku większości standardowych formularzy w Supply Chain Management. Uwaga, nie można sortować ani filtrować kolumn **% zmiany ceny netto**, ponieważ jest to pole obliczeniowe.
    - Wybranie opcji **Wyświetlanie wymiarów** umożliwia otwarcie okienka, w którym można wybrać kolumnę wymiaru, która ma zostać uwzględniona w formularzu. Ustaw opcję **Zapisz ustawienia** na **tak**, jeśli chcesz zapisać te ustawienia, aby zostały zachowane podczas następnego otwierania raportu. Wybierz przycisk **OK**, aby zastosować ustawienia i zamknąć.
    - Wybierz dowolny wiersz w formularzu, a następnie wybierz opcje **Wyświetl szczegóły**, aby wyświetlić więcej informacji o wybranym towarze. W tym miejscu będziesz mieć możliwość przechodzenia do szczegółów danych.
    - Zaznacz dowolny wiersz w formularzu, a następnie wybierz opcję **Widok wykresu porównawczego**, aby zobaczyć interaktywną graficzną reprezentację wyników w miarę ich odnoszący się do wybranego elementu. Wyniki te można poznać, wybierając różne elementy graficzne w legendzie wykresu i wykresie.
    - Wybierz dowolny wiersz w formularzu, a następnie wybierz opcje **Wyświetl szczegóły obliczenia**, aby wyświetlić więcej informacji dotyczących obliczeń dla wybranego towaru. W tym miejscu będziesz mieć możliwość przechodzenia do szczegółów danych.

## <a name="export-the-compare-item-prices-storage-report"></a>Eksport raportu magazynowego porównania cen pozycji

Każdy generowany raport jest przechowywany w jednostce danych **Porównaj ceny towaru**. Za pomocą standardowych funkcji Supply Chain Management można eksportować dane z tej jednostki do dowolnego obsługiwanego formatu danych, w tym także do pliku CSV lub programu Microsoft Excel.

Poniżej przedstawiono przykład sposobu eksportowania raportu dotyczącego **magazynowego porównania cen pozycji**:

1. Wybierz kolejno opcje **Administrowanie systemem > Obszary robocze > Zarządzanie danymi**.

1. Wybierz przycisk **Eksportuj** w sekcji **Zarządzanie danymi**.

1. Zostanie otwarta strona **Eksport**, która zostanie użyta do skonfigurowania zadania eksportu. Zacznij od nadania **nazwy grupy** zadaniu.

1. W sekcji **wybrane jednostki** wybierz opcję **Dodaj jednostkę**, aby otworzyć okno dialogowe, w którym można określić następujące opcje:

    - **Nazwa jednostki** — wybierz opcję **Porównaj ceny pozycji**.
    - **Format danych docelowych** — wybierz format, do którego chcesz eksportować dane.

1. Wybierz przycisk **Dodaj**, aby dodać nowy wiersz, a następnie kliknij przycisk **Zamknij**, aby zamknąć okno dialogowe.

1. Zazwyczaj w danym momencie można eksportować jeden raport. W tym celu należy skonfigurować **filtr** dla wiersza dodanego właśnie do okienka **Zapytanie**. Pozwoli to określić, które raporty z jednostki **porównywana cena towaru** mają zostać uwzględnione w eksporcie. Aby wyeksportować pojedynczy raport, należy skonfigurować następujące opcje filtrowania:

    - Na karcie **zakres** wybierz opcję **Dodaj**, aby dodać nowy wiersz.
    - Ustaw **Tabela** na **Porównaj ceny pozycji**.
    - Ustaw **Tabela pochodna** na **Porównaj ceny pozycji**.
    - Ustaw **Pole** na pole, według którego ma być wykonywane filtrowanie. Zazwyczaj używana jest **nazwa wykonania** lub **czas wykonania**.
    - Określ **kryteria** dla wartości z wybranego pola, które chcesz wyszukać (nazwę raportu lub godzinę wygenerowania raportu).
    - W razie potrzeby Dodaj wiersze do tabeli **zakresu**, dopóki szukany raport nie zostanie jednoznacznie zidentyfikowany.

1. Wybierz przycisk **OK**, aby zapisać ustawienia i zamknąć.

1. Wybierz **Zapisz**, by zapisać ustawienia eksportu.

1. Otwórz kartę **opcje eksportu** i wybierz pozycję **Eksportuj teraz**, aby wygenerować plik eksportu.

1. Zostanie otwarta strona **podsumowanie wykonania**, na której możesz zobaczyć stan zadania eksportowania oraz listę wyeksportowanych jednostek. Wybierz jednostkę **Porównaj ceny towaru** na liście w obszarze **stan przetwarzania jednostki**, a następnie wybierz opcję **Pobierz plik**, aby pobrać dane wyeksportowane z tej jednostki.

Aby uzyskać więcej informacji o używaniu funkcji zarządzania danymi do eksportowania danych, patrze [omówienie importowania i eksportowania danych](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]