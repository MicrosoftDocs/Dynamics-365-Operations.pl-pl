---
title: Ponowne obliczanie kwot netto wiersza podczas importowania zamówień sprzedaży, ofert i zwrotów
description: W tym artykule opisano, czy i w jaki sposób system ponownie oblicza kwoty netto, gdy są importowane zamówienia sprzedaży, oferty i zwroty. Wyjaśniono w nim również, jak można kontrolować zachowanie w różnych wersjach rozwiązania Microsoft Dynamics 365 Supply Chain Management.
author: Henrikan
ms.date: 06/08/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2022-06-08
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: ce34a6be7bc3d14e23bdd8769aa71dc035b983b3
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220625"
---
# <a name="recalculate-line-net-amounts-when-importing-sales-orders-quotations-and-returns"></a>Ponowne obliczanie kwot netto wiersza podczas importowania zamówień sprzedaży, ofert i zwrotów

[!include [banner](../includes/banner.md)]

W tym artykule opisano, czy i w jaki sposób system ponownie oblicza kwoty netto, gdy są importowane zamówienia sprzedaży, oferty i zwroty. Wyjaśniono w nim również, jak można kontrolować zachowanie w różnych wersjach rozwiązania Microsoft Dynamics 365 Supply Chain Management.

## <a name="how-updates-to-net-line-amounts-are-calculated-on-import"></a>Sposób obliczania aktualizacji kwot wiersza netto przy imporcie

Wprowadzono usługę Supply Chain Management w wersji 10.0.23 [poprawka 604418](https://fix.lcs.dynamics.com/issue/results/?q=604418). Ta poprawka błędu zmieniła warunki, w których pole **Kwota netto** w wierszu może być aktualizowane lub ponownie obliczane podczas importowania aktualizacji istniejących zamówień sprzedaży, zwrotów i ofert. W wersji 10.0.29 można zastąpić tę poprawkę, włączając funkcję *Oblicz kwotę netto wiersza przy imporcie*. Ta funkcja działa podobnie, ale zapewnia ustawienie globalne, które umożliwia powrót do starego zachowania, jeśli trzeba. Nowe zachowanie powoduje, że system działa w sposób bardziej specyficzny, ale może dawać nieoczekiwane wyniki w określonych scenariuszach, w których są spełnione następujące warunki:

- Dane, które aktualizują istniejące rekordy, są importowane przez *Wiersze zamówienia sprzedaży V2*, *2Wiersze oferty sprzedaży V2* lub *Wiersze zamówienia zwrotu* przy użyciu protokołu Open Data Protocol (OData), w tym w sytuacjach, w których używasz podwójnego zapisu , importuj/eksportuj przez Excel i niektóre integracje innych firm.
- [Zasady oceny umów handlowych](/dynamicsax-2012/appuser-itpro/trade-agreement-evaluation-policies-white-paper), które obowiązują, ustanawiają zasady zmian, które ograniczają aktualizacje pola **Kwota netto** w wierszach zamówienia sprzedaży, wierszach ofert sprzedaży i/lub wierszach zamówienia zwrotu.
- Importowane dane obejmują zmiany w polu **Kwota netto** w wierszach lub zmiany (takie jak cena jednostkowa, ilość lub rabat), które powodują ponowne obliczanie wartości pola **Kwota netto** w wierszach dla co najmniej jednego istniejącego rekordu wiersza.

W tych określonych scenariuszach zasada oceny umowy handlowej stanowi ograniczenie w aktualizacjach pola **Kwota netto** w wierszu. To ograniczenie jest nazywane zasadami *zmiany*. Z powodu tych zasad podczas korzystania z interfejsu użytkownika do edytowania lub ponownego obliczania pola system wyświetli monit o potwierdzenie, czy użytkownik chce dokonać zmiany. Jednak podczas importowania rekordu system musi dokonać wyboru dla użytkownika. Przed wersją 10.0.23 system zawsze pozostawił kwotę netto wiersza niezmienioną, chyba że przychodząca kwota netto dla wiersza wynosi 0 (zero). Jednak w nowszej wersji system zawsze aktualizuje lub ponownie obliczy kwotę netto, jeśli nie zostanie to jawnie określone. Chociaż nowe zachowanie jest bardziej logiczne, może to spowodować problemy, jeśli są już uruchomione procesy lub integracje, które zakładają starsze zachowanie. W tym artykule opisano sposób przywracania w razie potrzeby starego zachowania.

## <a name="control-calculations-of-line-net-amounts-in-versions-10029-and-later"></a>Obliczenia kontrolne kwot netto wiersza w wersjach 10.0.29 i nowszych

W Supply Chain Management 10.0.29 wprowadzono funkcję o nazwie *Oblicz kwotę netto wiersza przy imporcie*. Ta funkcja dodaje opcję o nazwie Oblicz **kwotę netto** wiersza na stronie **parametry rozrachunków z odbiorcami**. Ta opcja umożliwia wybór między nowymi i starszych zachowaniami podczas obliczania kwot netto wiersza przy imporcie.

### <a name="turn-the-calculate-line-net-amount-on-import-feature-on-or-off"></a>Włączanie lub wyłączanie funkcji Obliczania kwoty netto wiersza przy imporcie

Po zaktualizowaniu do wersji 10.0.29 funkcja *Oblicz* kwotę netto wiersza przy imporcie jest domyślnie włączona, a nowa opcja **Oblicz kwotę netto wiersza** ma początkowo wartość *Tak*. Ustawienie *Tak* odpowiada nowemu standardowemu zachowaniu. Pasuje do zachowania systemu przy wyłączonej funkcji, [z wyjątkiem funkcji parametru CalculateLineAmount](#CalculateLineAmount), jak opisano w dalszej części tego artykułu. Ustawienie *Nie* pasuje do zachowania systemu sprzed wersji 10.0.23 i jest dostarczane głównie do obsługi starszych scenariuszy integracji.

Administratorzy mogą włączać i wyłączać *funkcję Obliczania kwoty netto dla wiersza* podczas importowania za pomocą obszaru roboczego [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="set-the-calculate-line-net-amount-option"></a>Ustaw opcję Oblicz kwotę netto linii

Po włączeniu funkcji *Oblicz kwotę netto wiersza* przy imporcie można ustawić opcję **Oblicz kwotę netto wiersza**, korzystając z poniższych kroków.

1. Wybierz kolejno pozycje **Rozrachunki z odbiorcami \> Ustawienia \> Parametry modułu rozrachunków z odbiorcami**.
1. Na karcie **Ceny**, na skróconej **karcie Obliczanie kwoty netto** wiersza za pomocą integracji ustaw **opcję Oblicz kwotę netto** wiersza na jedną z następujących wartości:

    - *Tak* — w razie potrzeby system będzie zawsze przeliczać i aktualizować kwoty w wierszach. (W związku z tym ignoruje zasady oceny umowy handlowej).
    - *Nie* — Jeśli istniejąca lub przychodząca kwota netto dla dowolnego wiersza wynosi 0 (zero), wartość tego wiersza jest ponownie przeliczana na podstawie innych wartości (takich jak cena jednostkowa, ilość i rabat). Jeśli istniejąca lub przychodząca kwota netto różni się od 0 (zero), a w polu **Kwota netto** w wierszu została ustawiona zasada zmiany, to pole nie jest ponownie obliczanie ani aktualizowane, nawet jeśli przychodzące zmiany ceny, ilości i/lub rabatu mogą wymagać ponownego przeliczenia sumy wiersza. To zachowanie pasuje do wersji 10.0.22.

### <a name="how-the-calculate-line-net-amount-on-import-feature-affects-the-calculatelineamount-parameter"></a><a name="CalculateLineAmount"></a>Wpływ kwoty netto wiersza na import w obliczaniu kwoty netto na parametr CalculateLineAmount

Jeśli funkcja *obliczania kwoty netto przy imporcie* jest włączona, wartość parametru `CalculateLineAmount` dla tabel `SalesLine` i `SalesQuotationLine` nie ma wpływu. Zamiast tego zachowanie jest kontrolowane globalnie za pomocą **opcji Oblicz kwotę netto wiersza**, która jest opisana w poprzedniej sekcji. Dlatego, gdy funkcja jest włączona, nie można zależność od wartości `CalculateLineAmount`.

Gdy funkcja *Oblicz wartość netto wiersza przy imporcie* jest wyłączona, parametr `CalculateLineAmount` dla tabel `SalesLine` i `SalesQuotationLine` działa tak samo, jak w Supply Chain Management w wersjach od 10.0.23 do 10.0.28, jak opisano w następnej sekcji.

## <a name="control-line-net-amount-calculations-in-versions-10028-and-earlier"></a>Obliczenia kwoty netto linii kontrolnej w wersjach 10.0.28 i wcześniejszych

Gdy [poprawka 604418](https://fix.lcs.dynamics.com/issue/results/?q=604418) została wprowadzona w wersji 10.0.23, można było wybrać sposób korekty poszczególnych odpowiednich jednostek danych podczas edytowania lub ponownego przeliczania kwoty netto wiersza z powodu innych zmian (takich jak zaktualizowana cena towaru). Możesz kontrolować to zachowanie, ustawiając nowy parametr `CalculateLineAmount` dla każdego wiersza na jedną z następujących wartości w importowanym pliku:

- **`CalculateLineAmount` = *1*** – Pole **Kwota netto** w wierszu jest zawsze ponownie obliczanie i aktualizowane niezależnie od tego, czy dla tego pola ustawiono zasady zmiany, niezależnie od wartości przychodzącej lub istniejącej kwoty netto wiersza.
- **`CalculateLineAmount` = *0*** – Jeśli istniejąca lub przychodząca kwota netto dla dowolnego wiersza wynosi 0 (zero), wartość tego wiersza jest ponownie przeliczana na podstawie innych wartości (takich jak cena jednostkowa, ilość i rabat). Jeśli istniejąca lub przychodząca kwota netto różni się od 0 (zero), a w polu **Kwota netto** w wierszu została ustawiona zasada zmiany, to pole nie jest ponownie obliczanie ani aktualizowane.  

Zachowanie systemu zależy od wersji Supply Chain Management:

- W wersji 10.0.22 i wcześniejszych system zawsze zachowuje się tak, jakby `CalculateLineAmount` była ustawiona na *0* i nie ma możliwości, aby zachowywał się tak, jakby `CalculateLineAmount` była ustawiona na *1*.
- W wersjach od 10.0.23 do 10.0.28 system zachowuje się tak, jakby opcja `CalculateLineAmount` była ustawiona na *1* dla wszystkich wierszy, w których nie jest jawnie ustawiona na *0* w pliku importu.
