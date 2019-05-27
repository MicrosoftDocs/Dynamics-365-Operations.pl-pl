---
title: Reguły alokacji księgi
description: Ten artykuł zawiera informacje o regułach alokacji księgi. Opisano w nim różne składniki tych reguł alokacji oraz metody alokacji, których można do nich używać.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAllocation, LedgerAllocationBasisRule, LedgerAllocationRequest, LedgerAllocationRule
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 15402
ms.assetid: 8147e148-7c11-45ef-95c6-f9889a875b54
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: abbeb1bb4481139dff902916362a479f94fb96e5
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1559394"
---
# <a name="ledger-allocation-rules"></a>Reguły alokacji księgi

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera informacje o regułach alokacji księgi. Opisano w nim różne składniki tych reguł alokacji oraz metody alokacji, których można do nich używać.

Reguły alokacji księgi są używane do automatycznego obliczania i generowania arkuszy alokacji i zapisów na kontach dla alokacji sald księgi lub kwot stałych. Metody alokacji mogą być stałe lub zmienne. Dla reguł alokacji księgi można użyć następujących metod alokacji:

-   **Podstawy** — ta zmienna metoda jest używana, gdy alokacja zależy od rzeczywistego salda księgi na podstawie kryteriów filtra. Na przykład można alokować wydatki firmy na reklamę proporcjonalnie do udziału wielkości sprzedaży poszczególnych działów w łącznej wielkości sprzedaży.
-   **Stały procent** i **Stała waga** — dla tych metod procent alokacji lub waga są zdefiniowane bezpośrednio dla reguły. Na przykład wydatki na reklamę można alokować w taki sposób, by Dział A miał przypisane 70 procent wydatków na reklamę, a Dział B miał 30 procent.
-   **Równo** — ta metoda rozprowadza kwotę równomiernie do każdego zdefiniowanego miejsca docelowego. Jeśli na przykład zdefiniowano miejsca docelowe dla Działu A i Działu B, wydatki na reklamę można alokować, tak aby do obu działów zostało przypisane po 50% wydatków na reklamę.

Jeśli dla reguły alokacji używana jest metoda Podstawa, to trzeba też zdefiniować oddzielne reguły podstawy alokacji w księgowaniu. Proces „Przetwarzanie żądania alokacji” pozwala użytkownikom przetwarzać regułę alokacji księgi i wyświetlać podgląd wynikowych wpisów arkusza przed zaksięgowaniem lub usunięciem obliczonych alokacji.

## <a name="components-of-ledger-allocation-rules"></a>Składniki reguł alokacji księgi
W każdej regule alokacji występują cztery składniki — ogólny, źródłowy, celu oraz przeciwstawny. Dodatkowy składnik, zasady podstawy alokacji księgi, jest wymagany, jeśli metodą alokacji jest Podstawa. Każdy składnik zawiera istotne informacje niezbędne do przetwarzania alokacji.

-   **Ogólne** — ten składnik określa opcje odnoszące do metody alokacji, ustawień reguł między firmami oraz aktywności reguł.
-   **Źródło** — ten składnik jest używany gdy użytkownik określa dane źródłowe dla alokacji. Alokacja może opierać się na saldach księgi (**Źródło danych** = **Księga**) lub stałych kwotach (**Źródło danych** = **Stała wartość**). Gdy **Źródło danych** ma wartość **Księga**, kryteria filtra źródła muszą być zdefiniowane dla reguły alokacji księgi (np. dla wydatków na reklamę).
-   **Cel** — ten składnik określa sposób dystrybuowania i rozliczania wyniku obliczeń alokacji. Można na przykład określić po jednym wierszu celu dla każdego oddziału.
-   **Konto przeciwstawne** — ten składnik określa sposób określania kont głównych i wymiarów dla zapisów przeciwstawnych bilansujących zapisy docelowe. Zazwyczaj używane są opcje zdefiniowane przez użytkownika zamiast kont i wymiarów opartych na źródle. Jeśli **Źródło danych** ma wartość **Stała wartość**, **Źródło** nie może być używane jako opcja.
-   **Reguły podstawy alokacji księgi** — te reguły mają własne kryteria filtru źródła, które określają, które salda ksiąg powinny być używane do alokacji (np. przychód na oddział). Każda reguła podstawy alokacji może być stosowana z wieloma regułami alokacji.




