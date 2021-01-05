---
title: Testowanie danych agnostycznych przy użyciu pola Regression Suite Automation Tool
description: W tym temacie omówiono zalecenia dotyczące testowania danych agnostic przy użyciu Regression Suite Automation Tool.
author: kfend
manager: AnnBe
ms.date: 09/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 21761
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2019-09-11
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: 7fd1fc4756e74a5d07ffae533b6b9837b960f17a
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/08/2020
ms.locfileid: "4693757"
---
# <a name="data-agnostic-testing-using-the-regression-suite-automation-tool"></a>Testowanie danych agnostycznych przy użyciu pola Regression Suite Automation Tool

[!include [banner](../includes/banner.md)]

Chociaż sprawdzenie funkcjonalne aplikacji ERP nie może być w pełni anostycznymi danymi, istnieje wiele faz i metod testowania. Te fazy testowania obejmują:  

- Strukturę SysTest
- Strukturę ATL
- Regression Suite Automation Tool (RSAT)

[![Piramida klasyfikacji testu](./media/rsat-data-agnostic-testing-01.PNG)](./media/rsat-data-agnostic-testing-01.PNG)

## <a name="overview"></a>Przegląd
-   **SysTest Framework** — struktura SysTest jest godna zaufania do pisania testów jednostkowych. Ponieważ testy jednostkowe zwykle testuje metodę lub funkcję, powinny zawsze być agnostic i uzależnione od danych wejściowych dostarczanych w ramach testu.
-   **Struktura ATL** — firma Microsoft ma strukturę ATL, która jest abstrakcyjna w strukturze SysTest i upraszcza tworzenie prostych i niezawodnych testów funkcjonalnych Te struktury powinny być używane do pisania testów składników lub testów integracji prostej.
-   **RSAT** — składnik RSAT jest używany do testów integracji i testów cyklu biznesowego. Testy cyklu biznesowego, nazywane również testami sprawdzania poprawności regresji, są zależne od istniejących danych. Jednak te testy mogą stać się agnostic danymi, Jeśli rozważasz dodatkowe czynniki. 

    - O ile testy jednostkowe i testy składników są niskiego poziomu i mogą w pełni być agnostic danymi (niezależnymi od istniejących zestawów danych), testy dotyczące cyklu biznesowego lub regresji są zależne od niektórych istniejących danych. Te dane obejmują ustawienia, ustawienia konfiguracji (parametry) oraz dane główne (odbiorca, dostawcy, towary itp.), ale nigdy dane transakcji. Upewnij się, że podczas testu, jeśli którekolwiek z nich jest zmieniane, to w wyniku ostatniego testu zostaną one wycofane.
    - Umożliwia wybór danych głównych opartych na określonych kryteriach zamiast wybierania określonego rekordu Na przykład, aby wybrać towar na podstawie jego wartości wymiarów i dostępności zapasów, należy przefiltrować listę produktów o te wartości, wybrać pierwszy towar i skopiować numer, który ma być używany do przyszłych testów. Jeśli jest to prosty wiersz danych głównych, np. odbiorca, dostawca lub towar, można go utworzyć jako część automatyzacji i używać w przyszłych testach za pośrednictwem łańcucha. 
    - O umożliwia wprowadzenie unikatowych identyfikatorów, takich jak numery faktur, za pomocą sekwencji numerów lub funkcji Microsoft Excel, takich jak =TEXT(NOW(),"yyyymmddhhmm"). Ta funkcja będzie dostarczać unikatowy numer co minutę, co pozwala śledzić czas wykonania akcji. Ta opcja może być używana dla zmiennych, takich jak numery dokumentów przyjęcia produktów i numery faktur dostawców. Te testy kontynuują pracę z tą samą bazą danych ponownie i ponownie, bez konieczności przywracania.
    - Należy zawsze ustawiać **tryb edycji** środowiska jako **odczytany** lub **edytowany** jako pierwszy przypadek testowy, ponieważ opcja domyślna to **automatyczne**. Opcje **automatyczne** zawsze korzystają z poprzedniego ustawienia i mogą powodować niezawodne testy 
 
    [![Strona opcji, karta wydajności](./media/rsat-data-agnostic-testing-02.PNG)](./media/rsat-data-agnostic-testing-02.PNG)
 
    - Sprawdź tylko poprawność po filtrowaniu według określonej transakcji zamiast w ogólnym sprawdzaniu poprawności. Na przykład dla liczby rekordów należy filtrować numer transakcji lub datę transakcji, dzięki czemu sprawdzanie poprawności wyklucza wszystkie inne transakcje. 
    - W przypadku sprawdzania salda odbiorcy lub kontroli budżetu najpierw Zapisz wartość, a następnie Dodaj wartość transakcji, aby sprawdzić oczekiwany wynik, zamiast sprawdzać poprawność stałej oczekiwanej wartości. 
 
