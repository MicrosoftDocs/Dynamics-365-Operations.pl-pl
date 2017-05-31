---
title: "Likwidacja środków trwałych dla Polski"
description: "Ten temat zawiera informacje o funkcjonalności likwidacji środków trwałych dla użytkowników w firmach w Polsce."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetParameters, AssetPosting, CustFreeInvoice, LedgerJournalTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 266964
ms.assetid: 99f3a20c-2e2e-4fc7-b846-3d86802174c4
ms.search.region: Poland
ms.author: v-elgolu
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 97648c78104decb7a1f50dba078a7ca06e65b0de
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017


---

# <a name="fixed-assets-disposal-for-poland"></a>Likwidacja środków trwałych dla Polski

[!include[banner](../includes/banner.md)]


Ten temat zawiera informacje o funkcjonalności likwidacji środków trwałych dla użytkowników w firmach w Polsce. 

Środki trwałe mogą być sprzedawane za pomocą funkcji likwidacji przy użyciu faktury niezależnej, arkusza środków trwałych lub arkusza finansowego w księdze głównej. Aby uzyskać więcej informacji dotyczących likwidacji środków trwałych, zobacz [Konta księgowania likwidacji środków trwałych](../fixed-assets/fixed-asset-disposal-posting-accounts.md). Dla użytkowników w firmach w Polsce rozszerzenie dodające funkcjonalność likwidacji środków trwałych zawiera następujące elementy:

-   Szablon do likwidowania środków trwałych na stronie **Profile księgowania środków trwałych**.
-   Dwa dodatkowe parametry na stronie **Uprawnienie do sprzedaży środka trwałego**. Pola wyboru **Sprawdź dopuszczenie środka do sprzedaży** i **Uprawnienie do sprzedaży środka trwałego** na skróconej karcie **Odwołanie i notatki** dla środka trwałego. Jeśli jest zaznaczone pole wyboru **Sprawdź dopuszczenie środka do sprzedaży**, można sprzedawać tylko składniki aktywów oznaczone jako **Uprawnienie do sprzedaży środka trwałego**.
-   Konto sprzedaży do likwidacji środków trwałych, które zawiera dodatkowy parametr na skróconej karcie **Sprzedaż** na stronie **Parametry środków trwałych**. Za pomocą tego parametru można zdefiniować domyślne konto księgowe do księgowania sprzedaży środków trwałych.
-   Dodatkowe pole na stronie **Częściowa likwidacja**, gdzie użytkownicy mogą wprowadzić wartość procentową. Ta wartość procentowa będzie służyć do obliczania kwoty wiersza jako wartości księgowej netto wybranego środka trwałego pomnożonej o wartość procentową.

## <a name="templates-for-fixed-asset-disposal"></a>Szablony likwidacji środków trwałych
Szablonu likwidacji środków trwałych można używać jako opcji upraszczającej konfigurowanie kont likwidacji środków trwałych dla profili księgowania. Aby utworzyć lub edytować szablon likwidacji środków trwałych, wykonaj następujące kroki:

1.  Wybierz kolejno opcje **Środki trwałe** &gt; **Ustawienia** &gt; **Profile księgowania środków trwałych**.
2.  W sekcji **Likwidacja** kliknij opcję **Utwórz szablon** i wybierz profil księgowania środków trwałych.
3.  Wypełnij następujące pola:
    |                    |                                                                                                                                |
    |--------------------|--------------------------------------------------------------------------------------------------------------------------------|
    | **Pole**          | **Opis**                                                                                                                |
    | **Księga**           | Wybierz księgę, w której chcesz skonfigurować lub aktualizować konta księgowania likwidacji składników aktywów.                                         |
    | **Konto główne**   | Wybrane konto będzie automatycznie używane jako **Konto główne** podczas tworzenia lub aktualizowania kont na potrzeby księgowania likwidacji.       |
    | **Konto przeciwstawne** | Wybrane konto będzie automatycznie używane jako **Konto przeciwstawne** podczas tworzenia lub aktualizowania kont na potrzeby księgowania likwidacji. |
    | **Zastępowanie**      | Jeśli zaznaczysz tę opcję, system zastąpi istniejące konta likwidacji dla wybranej wartości **Księga**.                                     |

4.  Kliknij przycisk **OK**. System automatycznie będzie tworzył lub aktualizował reguły księgowania w wybranej księdze dla następujących składników (typów transakcji) likwidacji środków trwałych:
    -   Amortyzacja (lata ubiegłe)
    -   Amortyzacja (ten rok)
    -   Korekta amortyzacji (lata wcześniejsze)
    -   Korekta amortyzacji (ten rok)
    -   Amortyzacja dodatkowa (poprzednie lata)
    -   Amortyzacja dodatkowa (bieżący rok)
    -   Umorzenie BO (lata ubiegłe)
    -   Umorzenie BO (ten rok)
    -   Zmiana wartości umorzenia (lata ubiegłe)
    -   Zmiana wartości umorzenia (ten rok)

## <a name="permission-to-sell"></a>Zezwolenie na sprzedaż
Funkcja zezwolenia na sprzedaż rozszerza podstawową funkcjonalność likwidacji poprzez sprzedaż dla użytkowników w firmach w Polsce o dwa dodatkowe parametry:

-   **Sprawdź dopuszczenie środka do sprzedaży** — To pole wyboru umożliwia aktywację dodatkowego filtra w polu wyszukiwania podczas wybierania środka trwałego do sprzedaży w wierszu faktury niezależnej lub arkusza. Dodatkowy filtr ma wpływ tylko na transakcje o typie **Likwidacja — sprzedaż**. Aby edytować pole **Sprawdź dopuszczenie środka do sprzedaży**, otwórz skróconą kartę **Sprzedaż** na stronie **Środki trwałe** &gt; **Ustawienia** &gt; **Parametry środków trwałych**.
-   **Uprawnienie do sprzedaży środka trwałego** — Użyj tego pola wyboru, aby określić, czy jest dozwolona sprzedaż poszczególnych parametrów każdego środka trwałego. Aby edytować to pole, otwórz skróconą kartę **Odwołanie i notatki** dla wybranego środka trwałego.

## <a name="sales-account-for-fixed-assets-disposal"></a>Konto sprzedaży do likwidacji środków trwałych
Gdy utworzysz transakcję likwidacji przez sprzedaż za pomocą arkusza środków trwałych lub arkusza finansowego w księdze głównej, konto sprzedaży domyślnie jest łączone z wierszem arkusza podanym w konfiguracji na stronie **Profile księgowania środków trwałych**. W przypadku tworzenia transakcji likwidacji przez sprzedaż za pomocą faktury niezależnej użytkownik powinien w polu **Konto główne** wpisać konto sprzedaży. Funkcjonalność konta sprzedaży do likwidacji środków trwałych umożliwia użytkownikom w firmach w Polsce skonfigurowanie konta księgowego, które domyślnie będzie traktowane jako konto sprzedaży dla transakcji likwidacji przez sprzedaż tworzonych przy użyciu faktury niezależnej. Aby skonfigurować konto sprzedaży do likwidacji środków trwałych, otwórz skróconą kartę **Sprzedaż** na stronie **Środki trwałe** &gt; **Ustawienia** &gt; **Parametry środków trwałych**.

## <a name="partial-sales-of-fixed-assets"></a>Sprzedaż częściowa środków trwałych
Likwidacja środka trwałego przez sprzedaż lub złomowanie umożliwia zlikwidowanie tylko całego środka trwałego. Funkcjonalność sprzedaży częściowej środków trwałych pozwala użytkownikom w firmach w Polsce pozbywać się środków trwałych częściowo za pomocą transakcji sprzedaży lub złomowania. Funkcja częściowej sprzedaży środków trwałych może być realizowana przy użyciu faktury niezależnej, arkusza środków trwałych lub arkusza finansowego w księdze głównej. Aby częściowo zlikwidować środek trwały, wprowadź wartość procentową (liczbę całkowitą od 0 do 100) w polu **Sprzedaż częściowa** w jednym z następujących miejsc:

-   Karta **Ogólne** w wierszu **Arkusz środków trwałych**.
-   Karta **Środki trwałe** w wierszu **Arkusze finansowe**.
-   Karta **Ogólne** w wierszu **Faktura niezależna**.

Domyślnie pole **Sprzedaż częściowa** zawiera wartość **100**. Gdy użytkownik wybierze typ transakcji **Likwidacja — odpadki** lub **Likwidacja — sprzedaż** oraz składnik aktywów w arkuszu, w wierszu arkusza domyślnie zostanie umieszczona wartość księgowa netto. Jeśli użytkownik zmieni wartość procentową, wartość księgowa netto w wierszu arkusza zostanie zmniejszona. Użytkownik może również ręcznie zmienić wartość księgową netto, co spowoduje przeliczenie wartości procentowej w polu **Sprzedaż częściowa**. **Przykład** Środek trwały został nabyty za 10 000 USD, amortyzacja wynosi 1000 USD, czyli wartość księgowa netto to 9000 USD. Pierwszy sprzedaż częściowa opiewa na 50% — wartość księgowa netto obliczona dla wiersza arkusza wynosi 50% z 9000 USD = 4500 USD. Sprzedaż częściowa drugich 50% — obliczona wartość księgowa netto dla wiersza arkusza wynosi 50% pozostałej wartość księgowej netto 4500 USD = 2250 USD. Jeśli użytkownik chce zaliczyć w koszty pozostałą wartość księgową netto 2250 USD, musi wprowadzić wartość procentową 100 w wierszu arkusza lub faktury niezależnej.




