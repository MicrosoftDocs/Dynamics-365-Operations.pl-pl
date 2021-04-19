---
title: Zarządzanie aktualizacjami kosztu standardowego
description: Aktualizacjami dotyczącymi danych kosztów standardowych można zarządzać za pomocą dwóch różnych metod — metody jednej wersji lub metody dwóch wersji.
author: AndersGirke
ms.date: 01/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostingVersion, InventItemPrice, InventParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: 69992
ms.assetid: 468de7af-c7b5-4345-bd5a-ba3aa5a900cc
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: dfe55134a9a9f3c40ebddcafd1d9e481976134ec
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5832353"
---
# <a name="manage-standard-cost-updates"></a>Zarządzanie aktualizacjami kosztu standardowego

[!include [banner](../includes/banner.md)]

Aktualizacjami dotyczącymi danych kosztów standardowych można zarządzać za pomocą dwóch różnych metod — metody jednej wersji lub metody dwóch wersji.

Metoda jednej wersji zakłada użycie jednej wersji zawierającej wszystkie rekordy kosztów. Te rekordy obejmują koszty pierwotne i wszystkie aktualizacje kosztów.

Metoda dwóch wersji zakłada użycie jednej wersji z rekordami kosztów pierwotnych i drugiego z rekordami wszystkich aktualizacji kosztów. Główną zaletą metody dwóch wersji jest wyraźne nakreślenie i śledzenie zmian kosztów w oddzielnych wersjach ceny bez naruszania oryginalnej wersji ceny. Metody dwóch wersji można używać do identyfikowania wielu wzrostów kosztów z osobnymi wersjami ceny zawierającymi rekordy wzrostów kosztów.

## <a name="example"></a>Przykład

Poniżej pokazano, jak używać metod jednej i dwóch wersji do aktualizacji kosztów standardowych i środowisku produkcyjnym. Na przykład aktualizacje, które odzwierciedlają nowe pozycje lub korekty. Załóżmy, że metoda jednej wersji przedstawia koszty standardowe w bieżącym roku. Identyfikator dla tej wersji to 2020-STD. Wersja 2020-STD zawiera bieżące aktywne koszty wszystkich pozycji. Oprócz tego zawiera wszystkie kategorie kosztów związanych z marszrutami oraz wzory obliczeń narzutów znane na początku 2020 r. 2020-STD jest pierwotną wersją wyceny.

- **Aktualizacja danych o kosztach w metodzie jednej wersji** — w metodzie jednej wersji wersja ceny pierwotnej 2020-STD zawiera wszystkie rekordy kosztów. Aktualizacje kosztu są rejestrowane w 2020-STD i otrzymują stan Oczekujące. Koszty oczekujące można wprowadzić ręcznie dla nowych zakupionych towarów lub można je uwzględnić w obliczeniach w celu wykazania odchyleń. Gdy używana jest metoda jednej wersji, obliczenia BOM nie wymagają zasady rezerwowości źródła danych, ponieważ wszystkie aktywne koszty są zawarte w tej wersji ceny. Po aktywacji kosztów oczekujących oryginalna wersja ceny 2020-STD będzie znów zawierać aktywne koszty bieżące.
- **Metoda dwóch wersji** — W metodzie dwóch wersji aktualizacji danych o kosztach jest wymagana dodatkowa wersja ceny zawierająca wyłącznie aktualizacje. Przyjmijmy, że identyfikator będzie wyglądał następująco: 2020-STD-ZMIANY. Aktualizacje kosztu są rejestrowane w 2020-STD-CHANGES i otrzymują stan Oczekujące. W przypadku metody dwóch wersji obliczenia BOM kosztów oczekujących produkowanych elementów wymagają zasady rezerwowości źródła danych. Dzieje się tak, ponieważ dodatkowa wersja wyceny 2020-STD-CHANGES zawiera tylko podzestaw danych kosztów. Zasada rezerwowości może zostać wyrażona jako koszty aktywne lub określona wersja ceny 2020-STD, ponieważ oba parametry identyfikują źródło danych o kosztach, jeśli nie istnieje ono w wersji ceny 2020-STD-ZMIANY. Po aktywacji kosztów oczekujących dodatkowa wersja ceny 2020-STD-CHANGES będzie zawierać aktywne koszty bieżące odzwierciedlające aktualizację, a oryginalna wersja ceny 2020-STD pozostanie bez zmian. Zasada dwóch wersji oznacza, że zasady blokowania oryginalnej wersji ceny powinny zapobiegać aktualizacjom. Dodatkowa wersja ceny powinna zawierać dokładnie takie same zasady co oryginalna wersja ceny z wyjątkiem daty początkowej oraz udostępniać selektywne użycie zasad blokowania zezwalających na aktualizacje. Określona data początkowa powinna zostać zaktualizowana o każdy zbiór zmian uwzględniających zaplanowaną datę aktywacji.

W tym przykładzie przedstawiono jedną dodatkową wersję wyceny służącą do zarządzania aktualizacjami za rok 2020. Można użyć więcej niż jedną dodatkową wersję wyceny, na przykład osobną wersję dla poszczególnych zbiorów aktualizacji. Jeśli używanych jest kilka opcji dodatkowej wyceny, domyślnej wyraża się jako koszty aktywne, ponieważ koszty aktywne są rozciągnięte jest na kilka wersji.

## <a name="financial-dimensions-for-the-standard-cost-revaluation"></a>Wymiary finansowe dla przeszacowania kosztu standardowego

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Aktywowanie nowej ceny standardowej zwykle powoduje przeszacowanie wartości dostępnych zapasów o transakcje przeszacowania kosztu standardowego. Zazwyczaj w transakcjach są wówczas księgowane wymiary finansowe towaru. Aby jednak określić, czy i w jaki sposób są księgowane wymiary finansowe, należy za pomocą funkcji [zarządzania funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) włączyć funkcję o nazwie *Opcje domyślnego wymiaru finansowego dla przesądu kosztów standardowych zapasów*. Po włączeniu tej funkcji wybierz opcje **Zarządzanie kosztami > Ustawienia zasad księgowania zapasów > Parametry** i ustaw jedną z następujących wartości nowej listy rozwijanej **źródła wymiarów finansowych**:

- **Brak** — nie zaksięgowano wymiarów finansowych w przypadku transakcji z przeszacowaniem w walucie obcej. Jeśli struktura konta obejmuje wymagany wymiar finansowy, proces przeszacowania nadal będzie uruchamiany, ale utworzy wpisy księgowe bez wymiarów finansowych. W takim przypadku użytkownicy otrzymają najpierw komunikat ostrzegawczy, aby w razie potrzeby anulować przeszacowanie.
- **Tabela** — wymiary finansowe pozycji są księgowane w ramach transakcji przeszacowania. Jest to ustawienie domyślne i jest zgodne z oryginalnym zachowaniem systemu bez włączania funkcji *Opcje domyślnego wymiaru finansowego dla przeszacowania kosztów standardowych zapasów*.
- **Zaksięgowanie** — oznacza, że wymiary finansowe przeszacowywanej transakcji zostały zaksięgowane w transakcjach z przeszacowaniem. Domyślnie wymiary finansowe z konta magazynowego oryginalnej transakcji są używane zarówno dla konta magazynowego, jak i konta przeszacowania.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]