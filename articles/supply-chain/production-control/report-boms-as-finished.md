---
title: "Zgłaszania specyfikacji BOM jako gotowych"
description: "Ten artykuł zawiera informacje o zgłaszaniu list składowych (BOM) jako gotowych."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMReportFinish, BOMReportFinishMax
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 53251
ms.assetid: 510d05a3-0073-438d-b0c4-b6a6df1882ea
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 92c594213eea8617d11b56be43e581a461830ba4
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="report-boms-as-finished"></a>Zgłaszania specyfikacji BOM jako gotowych

[!INCLUDE [banner](../includes/banner.md)]

Ten artykuł zawiera informacje o zgłaszaniu list składowych (BOM) jako gotowych.

Strony **Zgłoszenie wyrobów gotowych** i **Maksymalna ilość zgłoszonych jako gotowe** służą do zgłaszania list składowych (BOM) jako gotowe. Co do koncepcji proces zgłaszania BOM jako gotowych jest taki sam, jak proces zgłaszania zlecenia produkcyjnego jako gotowego. Ten proces może być stosowany m.in. w przypadku procesów prostego montażu i składania, gdzie nie są wymagane bardziej zaawansowane funkcje zlecenia produkcyjnego. Strona **Zgłoszenie wyrobów gotowych** umożliwia zgłoszenie wielu BOM jako gotowych w partii. Strona **Maksymalna ilość zgłoszonych jako gotowe** umożliwia zgłoszenie tylko jednego BOM jako gotowego w danym momencie. Strona **Zgłoszenie wyrobów gotowych** jest dostępna z menu w module Zarządzanie zapasami. Obie strony są dostępne jako elementy menu na stronie **Zwolnione produkty**.

## <a name="report-as-finished-page"></a>Strona Zgłoszenie wyrobów gotowych
Po wyświetleniu strony **Zgłoszenie wyrobów gotowych** z menu zwolniony produkt, strona proponuje zgłoszenie domyślnej ilości standardowych zapasów jako gotowych. Domyślnie wyświetlana jest aktywna wersja BOM, ale możesz ją zmienić, jeśli są inne zatwierdzone wersje. Strona daje również możliwość usuwania rekordów i tworzenia nowych rekordów dla zwolnionych produktów, które powinny być zgłoszone jako gotowe. Aby użyć kwerendy do wybrania produktów, kliknij przycisk **Zaznacz**. Można ręcznie potwierdzić zgłoszenie wybranych produktów jako gotowych, klikając przycisk **OK**. Istnieje również możliwość konfiguracja uruchamiania procesu w partii. Po potwierdzeniu zgłoszenia towaru jako gotowego, system generuje arkusz BOM przetwarzania księgowania w zapasach. Ten arkusz składa się z jednego wiersza dla gotowego produktu i wierszy dla każdego wiersza BOM. Można kontrolować, czy arkusz jest księgowany automatycznie czy pozostanie otwarty w celu wprowadzenia dodatkowych korekt.

## <a name="max-report-as-finished-page"></a>Maks. wyrobów gotowych
Na stronie **Maksymalna ilość zgłoszonych jako gotowe** każdy wiersz BOM zawiera liczbę sztuk produktu, którą można zgłosić jako gotowe. Ta wartość jest obliczana na podstawie fizycznej dostępności zapasów z każdego wiersza materiału. W poniższym przykładzie jedna sztuka towaru FG korzysta z dwóch rodzajów surowca RM10 i jednej sztuki surowca RM20. Ponieważ istnieje tylko 10 sztuk RM10 na stanie, można zgłosić jako gotowe maksymalnie 5 sztuk FG. Ta wartość jest wyświetlana w polu **Maksymalna ilość zgłoszonych jako gotowe**.

| Poziom | Numer pozycji | Ilość | Zapasy | Maks. Zgłoszenie wyrobów gotowych |
|-------|-------------|----------|---------|-------------------------|
| 0     | FG          |  1 przypada na wpłatę z zysku na rzecz budżetu państwa       | 0       | 5 przypada na składniki z tytułu ubezpieczeń majątkowych i osobowych                       |
| 1 przypada na wpłatę z zysku na rzecz budżetu państwa     | RM10        | -2       | 10      | 5 przypada na składniki z tytułu ubezpieczeń majątkowych i osobowych                       |
| 1 przypada na wpłatę z zysku na rzecz budżetu państwa     | RM20        | -1       |  8      | 8                       |

## <a name="boms-that-have-multiple-levels"></a>BOM, które mają wiele poziomów
Jeśli BOM ma wiele poziomów, za pomocą pola **Rozłożenie**można kontrolować sposób rozliczania materiałów na wszystkich poziomach. To pole jest dostępne na stronach **Zgłoszenie wyrobów gotowych** i **Maksymalna ilość zgłoszonych jako gotowe**. Dostępne są następujące opcje:

-   **Nigdy** — podległe BOM nie są rozkładane w przypadku niedoboru materiału.
-   **Zawsze** — wszystkie podległe BOM są całkowicie rozkładane. W przypadku towarów składowych w formie półproduktów nie są używane żadne dostępne zapasy.
-   **Niedobór** — podległe BOM są rozkładane tylko wtedy, gdy wymagana ilość materiału nie jest w pełni dostępna.

### <a name="example"></a>Przykład

W tym przykładzie można zgłosić 3 sztuki towaru (FG) jako gotowe. Jest dwupoziomowa lista BOM, jak pokazano poniżej.

| Poziom | Numer pozycji | Ilość w wierszu BOM | Zapasy |
|-------|-------------|-------------------|---------|
| 0     | FG          |                   |         |
| 1 przypada na wpłatę z zysku na rzecz budżetu państwa     | COMP        | 1 przypada na wpłatę z zysku na rzecz budżetu państwa                 | 2       |
| 1 przypada na wpłatę z zysku na rzecz budżetu państwa     | RM          | 1 przypada na wpłatę z zysku na rzecz budżetu państwa                 |         |

Następujące tabele pokazują, jak ustawienie pola **Rozłożenie** wpływa na sposób generowania wierszy arkusza BOM. **Rozłożenie: nigdy**

| Poziom | Numer pozycji | Ilość |
|-------|-------------|----------|
| 0     | FG          | 3        |
| 1 przypada na wpłatę z zysku na rzecz budżetu państwa     | COMP        | -3       |

Jak pokazano w tabeli powyżej, tylko towar o numerze COMP jest uznawany za odjęty w arkuszu. Towar o numerze RM, który jest częścią towaru COMP, nie został rozłożony w wierszu arkusza, a dwie dostępne sztuki towaru COMP nie zostały uwzględnione. **Rozłożenie: zawsze**

| Poziom | Numer pozycji | Ilość |
|-------|-------------|----------|
| 0     | FG          | 3        |
| 1 przypada na wpłatę z zysku na rzecz budżetu państwa     | RM          | -3       |

W tym przypadku ilość towaru COMP jest rozkładana na surowiec (RM). Dwie dostępne sztuki towaru COMP nie są uwzględnione w ilości materiału RM, który musi być wykorzystany. **Rozłożenie: niedobór**

| Poziom | Numer pozycji | Ilość |
|-------|-------------|----------|
| 0     | FG          | 3        |
| 1 przypada na wpłatę z zysku na rzecz budżetu państwa     | COMP        | -2       |
| 1 przypada na wpłatę z zysku na rzecz budżetu państwa     | RM          | -1       |

W tym przypadku dwie dostępne sztuki towaru COMP zostały uwzględnione. Ale, ze względu na to, że potrzeba 3 sztuk towaru FG, konieczna jest także 1 sztuka RM do wyprodukowania dodatkowej sztuki COMP.




