---
title: Ręczne obsługa wyjątków pobierania wiersza sprzedaży i przeniesienia
description: W tym artykule opisano sposób, w jaki administratorzy mogą ręcznie pobierać (lub anulować pobieranie) transakcji magazynowych w celu rozwiązania problemów spowodowanych przez uszkodzenia danych zamówień sprzedaży i przeniesienia.
author: perlynne
ms.date: 08/19/2022
ms.topic: article
ms.search.form: WHSManualSalesLinePicking, WHSManualInventTransferLinePicking, InventTransPick, WHSLoadLineManualCorrection, WHSTroubleshootingSelfService
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: d2f89a7109060e69aca6a06eadaedc017728bbae
ms.sourcegitcommit: 0220be95c007c77ba3b73fed8ac68a3d72dc2884
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/02/2022
ms.locfileid: "9403699"
---
# <a name="manually-handle-sales-and-transfer-line-picking-exceptions"></a>Ręczne obsługa wyjątków pobierania wiersza sprzedaży i przeniesienia

[!include [banner](../includes/banner.md)]

Ręczna obsługa wyjątków pobierania wiersza sprzedaży i przeniesienia umożliwia administratorom rozwiązywanie problemów spowodowanych przez uszkodzenia danych zamówień sprzedaży i przeniesienia. Zaufani użytkownicy mogą ręcznie pobierać (lub anulować pobieranie) transakcje magazynowe, które są powiązane z wierszami zamówienia sprzedaży i przeniesienia, gdy procesy magazynowe są już w toku.

Opisana tutaj funkcja powinna być używana tylko w przypadkach, gdy system w zwykły sposób nie może zakończyć przetwarzania stosu procesów magazynowych. Domyślnie tylko użytkownicy z rolą administratora systemu mogą z nich korzystać. Dostęp do tej funkcji można jednak przyznać, przypisując *Ręcznie uprawnienia pobierania wierszy sprzedaży* do innych wymaganych ról.

## <a name="turn-on-this-feature-for-your-system"></a>Włączanie funkcji w systemie

Aby można było skorzystać z funkcji opisanych w tym artykule, należy je włączyć w systemie. Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i je włączyć. W obszarze roboczym **Zarządzanie funkcjami** te funkcje są wymienione z użyciem następujących nazw:

- *Ręczna usługa pobierania wierszy sprzedaży dla administratora lub podobnych zaufanych użytkowników*<br>(Od wersji 10.0.25 Supply Chain Management ta funkcja jest obowiązkowa i nie można jej wyłączyć).
- *Ręczna usługa pobierania wierszy przeniesienia dla administratora lub podobnych zaufanych użytkowników*

## <a name="correct-transactions-related-to-sales-or-transfer-order-lines"></a>Korygowanie transakcji związanych z wierszami zamówienia sprzedaży lub przeniesienia

Aby poprawić transakcje związane z wierszami zamówienia sprzedaży lub przeniesienia, należy skorzystać z następującej procedury.

1. Postępuj zgodnie z tymi krokami w zależności od typu zamówienia, które należy poprawić:

    - Aby skorygować transakcję związaną z zamówieniem sprzedaży, przejdź do **Zarządzanie magazynem \> Zadania okresowe \> Czyszczenie \> Ręcznie pobierz wiersze sprzedaży**.
    - Aby skorygować transakcję związaną z zamówieniem przeniesienia, przejdź do **Zarządzanie magazynem \> Zadania okresowe \> Czyszczenie \> Ręcznie pobierz wiersze przeniesienia**.

1. Na stronie **Ręcznie wybierz wiersze sprzedaży** lub **Ręcznie wybierz wiersze przeniesienia**, użyj filtrów u góry siatki, aby znaleźć szukany wiersz, a następnie wybierz docelowy wiersz zamówienia w górnej siatce.
1. Aby wyświetlić więcej informacji o wybranym wierszu, użyj kart **Transakcje magazynowe**, **Wiersze ładunku**, **Wiersze pracy** i **Wiersze kontenera** w dolnej sekcji. Informacje dostępne na tych kartach zawierają podstawowy przegląd powiązanych procesów magazynowych i ich stanów.
1. W okienku akcji **Pobierz** otwórz wybrany wiersz zamówienia na stronie **Pobierz** dla transakcji magazynowych. Ten krok można wykonać nawet dla wierszy zamówienia, które zostały już zwolnione do magazynu. (Zazwyczaj wiersze zamówienia zwolnione do magazynu nie mogą być otwierane na stronie **Pobierz**.)

    > [!NOTE]
    > Po otwarciu strony **Pobierz** mogą być wyświetlane różne ostrzeżenia. Podejmij wszelkie działania zalecane w przypadku tych ostrzeżeń. Na przykład może zostać wyświetlony komunikat z ostrzeżeniem o wierszach zamówienia połączonych z pracą magazynową. W takim przypadku przed ręczną korektą warto spróbować [anulować pracę](cancel-warehouse-work.md) przy użyciu standardowych funkcji anulowania pracy.

1. Zaznacz wiersz w siatce **Transakcje**, a następnie wybierz pozycję **Dodaj wiersz pobrania** na pasku narzędzi **Transakcje**.
1. Zaznaczony wiersz jest przenoszony do siatki **Wiersze pobrania**. Ustaw odpowiednie wartości dla kolumn, w których brakuje wymaganych informacji. (Określ na przykład lokalizację i numer identyfikacyjny, z których towar ma zostać pobrany lub pobieranie wycofane.)
1. Wybierz **Potwierdź pobranie wszystkiego** na pasku narzędzie **Wiersze pobrania**.

## <a name="correct-load-line-quantities"></a>Popraw ilości w wierszach ładunku

Do poprawienia ilości ładunku należy użyć następującej procedury.

1. Postępuj zgodnie z tymi krokami w zależności od typu zamówienia, które należy poprawić:

    - Aby skorygować transakcję związaną z zamówieniem sprzedaży, przejdź do **Zarządzanie magazynem \> Zadania okresowe \> Czyszczenie \> Ręcznie pobierz wiersze sprzedaży**.
    - Aby skorygować transakcję związaną z zamówieniem przeniesienia, przejdź do **Zarządzanie magazynem \> Zadania okresowe \> Czyszczenie \> Ręcznie pobierz wiersze przeniesienia**.

1. Na stronie **Ręcznie wybierz wiersze sprzedaży** lub **Ręcznie wybierz wiersze przeniesienia**, użyj filtrów u góry siatki, aby znaleźć szukany wiersz, a następnie wybierz docelowy wiersz zamówienia w górnej siatce.
1. Na karcie **Wiersze ładunku** w dolnej sekcji wybierz **Ręcznie popraw wiersze ładunku** na pasku narzędzi.
1. Na stronie **Ręcznie popraw wiersze ładunku** w siatce **Transakcje magazynowe** przejrzyj transakcje magazynowe powiązane z wybranym wierszem ładunku.
1. W górnej siatce popraw ilości w wierszach ładunku w następujących kolumnach, zgodnie z potrzebą:

    - **Ilość utworzonej pracy**
    - **Pobrana ilość**
    - **Planowana ilość do przeładunku kompletacyjnego**

    System zweryfikuje wszystkie zmiany wprowadzone w tych kolumnach.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
