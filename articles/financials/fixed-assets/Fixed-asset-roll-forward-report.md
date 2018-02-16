---
title: "Raport przesunięcia środków trwałych do przodu"
description: "W tym temacie wyjaśniono, jak korzystać z raportu przesunięcia środków trwałych do przodu."
author: saraschi2
manager: 
ms.date: 01/08/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 23021
ms.assetid: d7e86f72-95db-4423-9b04-761e9536a959
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-12-20
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: 8075abccdcdde21df967dcc9948a738895f35cef
ms.openlocfilehash: 0a78df4ede8fd57afbc3e9a7e5a38b840f479cdf
ms.contentlocale: pl-pl
ms.lasthandoff: 01/25/2018

---
# <a name="fixed-assets-roll-forward-report"></a>Raport przesunięcia środków trwałych do przodu

[!include[banner](../includes/banner.md)]

Raport **Przesunięcie środków trwałych do przodu** przedstawia, w czytelnym formacie programu Microsoft Excel, szczegółowe dane środków trwałych wymagane do zamknięcia okresu, sprawozdań finansowych i sprawozdawczości podatkowej. Raport zawiera początkowe i końcowe salda środków trwałych, łącznie z przesunięciami w związku z wyceną w okresie, oraz informacje o wszelkich nabyciach i zbyciach/likwidacjach środków trwałych zaistniałych w okresie. Dane są raportowane dla poszczególnych środków trwałych, a dodatkowo wartości są sumowane dla grup środków trwałych i dla firm.

Raport **Przesunięcie środków trwałych do przodu** używa struktury modułu Raportowanie elektroniczne (ER). Aby można było wygenerować raport, konfiguracje modelu środków trwałych i rolowania środków trwałych muszą zostać zaimportowane z usługi Microsoft Dynamics Lifecycle Services (LCS). Instrukcje znajdują się w temacie [Pobieranie konfiguracji modułu Raportowanie elektroniczne z usługi Lifecycle Services](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs).

Raport ten jest dostępny w programie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition w wersji 7.3 lub jako poprawka programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition (z lipca 2017 roku). W środowiskach, w których zainstalowano wersję z lipca 2017 roku, należy zastosować trzy poprawki:

- **KB 4041754:** Po zastosowaniu pakietu aktualizacji platformy nie można pobrać Konfiguracji modułu Raportowanie elektroniczne (ER) z usługi LCS, ponieważ nie ma ona zastosowania do bieżącej wersji aplikacji
- **KB 4056107:** Aktualizacja zbiorcza 5 modułu Raportowanie elektroniczne (GER)
- **KB 4056353:** Zestawienie środków trwałych i raporty o notach nie spełniają wymogów standardów rachunkowości GAAP i IFRS

W poniższej tabeli przedstawiono pola dostępne w raporcie.

| Pole                                       | opis |
|---------------------------------------------|-------------|
| Salda: Otwarcie                           | Wartość księgowa netto środków trwałych na dzień „od” określony w raporcie. |
| Salda: Zamknięcie                           | Wartość księgowa netto środków trwałych na dzień „do” określony w raporcie. |
| Nabycia: Wartość otwarcia                 | Suma wszystkich transakcji typu **Nabycie** i **Korekta wartości początkowej** do dnia „od” określonego w raporcie. |
| Nabycia: Nabycia w okresie           | Suma wszystkich transakcji typu **Nabycie** i **Korekta wartości początkowej** zaksięgowanych w przedziale dat objętych raportem. |
| Nabycia: Likwidacje w okresie              | Suma wszystkich wycofań nabycia zawierających transakcje likwidacji, które zostały zaksięgowane w przedziale dat objętych raportem. |
| Nabycia: Wartość zamknięcia                 | Suma wszystkich transakcji typu **Nabycie** i **Korekta wartości początkowej** do dnia „do” określonego w raporcie. |
| Amortyzacje: Wartość otwarcia                | Suma wszystkich transakcji typu **Amortyzacja**, **Korekta amortyzacji**, **Specjalny odpis amortyzacyjny** i **Amortyzacja dodatkowa** do dnia „od” określonego w raporcie. |
| Amortyzacje: Amortyzacje w okresie         | Suma wszystkich transakcji typu **Amortyzacja**, **Korekta amortyzacji** i **Amortyzacja dodatkowa** zaksięgowanych w przedziale dat objętych raportem. |
| Amortyzacje: Amortyzacje specjalne w okresie | Suma wszystkich transakcji typu **Specjalny odpis amortyzacyjny** zaksięgowanych w przedziale dat objętych raportem. |
| Amortyzacje: Likwidacje w okresie             | Suma wszystkich wycofań amortyzacji zawierających transakcje likwidacji, które zostały zaksięgowane w przedziale dat objętych raportem. |
| Amortyzacje: Wartość zamknięcia                | Suma wszystkich transakcji typu **Amortyzacja**, **Korekta amortyzacji**, **Specjalny odpis amortyzacyjny** i **Amortyzacja dodatkowa** do dnia „do” określonego w raporcie. |
| Zwiększenia/zmniejszenia: Wartość otwarcia        | Suma wszystkich transakcji typu **Zwiększenie wartości**, **Zmniejszenie wartości** i **Przeszacowanie** do dnia „od” określonego w raporcie. |
| Zwiększenia/zmniejszenia: Zwiększenia w okresie     | Suma wszystkich transakcji typu **Zwiększenie wartości** zaksięgowanych w przedziale dat objętych raportem. |
| Zwiększenia/zmniejszenia: Zmniejszenia w okresie   | Suma wszystkich transakcji typu **Zmniejszenie wartości** zaksięgowanych w przedziale dat objętych raportem. |
| Zwiększenia/zmniejszenia: Przeszacowania w okresie  | Suma wszystkich transakcji typu **Przeszacowanie** zaksięgowanych w przedziale dat objętych raportem. |
| Zwiększenia/zmniejszenia: Likwidacje w okresie     | Suma wszystkich wycofań zwiększenia wartości, zmniejszenia wartości i przeszacowania zawierających transakcje likwidacji, które zostały zaksięgowane w przedziale dat objętych raportem. |
| Zwiększenia/zmniejszenia: Wartość zamknięcia        | Suma wszystkich transakcji typu **Zwiększenie wartości**, **Zmniejszenie wartości** i **Przeszacowanie** do dnia „do” określonego w raporcie. |
| Likwidacje: Data likwidacji                    | Data likwidacji w księdze środków trwałych. |
| Likwidacje: Wartość księgowa netto przy likwidacji       | Wartość księgowa netto księgi środków trwałych w momencie likwidacji. |
| Likwidacje: Wartość sprzedaży                       | Wartość sprzedaży księgi środków trwałych zawierającej transakcję likwidacji poprzez sprzedaż. |
| Likwidacje: Wartość złomowania                      | Wartość złomowania księgi środków trwałych zawierającej transakcję likwidacji poprzez złomowanie. |
| Likwidacje: Zysk/strata                      | Wartość zysku lub straty obliczona w ramach transakcji likwidacji księgi środków trwałych. |

