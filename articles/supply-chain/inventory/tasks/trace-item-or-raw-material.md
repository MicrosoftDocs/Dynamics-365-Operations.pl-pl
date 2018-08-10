---
title: "Śledzenie elementu lub surowca"
description: "Ta procedura przedstawia wykorzystanie funkcji śledzenia towarów w celu identyfikacji miejsc, gdzie towary lub surowce zostały użyte albo są używane."
author: pjacobse
manager: AnnBe
ms.date: 06/21/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: pjacobse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: d7eb282ddf9597385d6660a3fc0ef73f403ab898
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="trace-an-item-or-raw-material"></a>Śledzenie elementu lub surowca

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ta procedura przedstawia wykorzystanie funkcji śledzenia towarów w celu identyfikacji miejsc, gdzie towary lub surowce zostały użyte albo są używane. Za pomocą tej procedury można zidentyfikować towar, śledzić go z powrotem do źródła, a następnie śledzić w przód aż do produkcji i sprzedaży produktu gotowego. Proces może służyć do analizowania odbiorców, zamówień sprzedaży i innych obiektów objętych oddziaływaniem. Procedura wykorzystuje dane firmy demonstracyjnej USP2.


## <a name="trace-an-item-backwards-using-a-known-batch-number"></a>Śledzenie towaru wstecz za pomocą znanego numeru partii
1. Wybierz kolejno opcje Zarządzanie zapasami > Zapytania i raporty > Wymiary śledzenia > Śledzenie towaru.
2. W polu Numer pozycji wybierz wartość P9100.
3. Na liście kliknij łącze w wybranym wierszu.
4. W polu W przód lub w tył wybierz opcję „Wstecz”.
5. W polu Numer partii wybierz wartość as-12-344-01.
6. Na liście kliknij łącze w wybranym wierszu.
7. Kliknij przycisk OK.

## <a name="identify-an-item-trace-it-forward-and-make-an-analysis"></a>Identyfikacja towaru, śledzenie go w przód i analiza
    * Najwyższy węzeł drzewa odpowiada dostępnej ilości wybranego towaru oraz partii. Należy rozwinąć węzły drzewa, aby znaleźć towar, do którego należy zastosować śledzenie w przód.   
1. W drzewie rozwiń węzły opisane poniżej, a następnie zaznacz ostatni węzeł.
    * Rozwiń węzeł „P9100 / 1 / 10 / as-12-344-01 ● 2 kegi ● 7,00 gal  \P9100 ● Pobrane ● Zamówienie sprzedaży 000072 ● 12/22/2015 ● -1 kega ● -4,00 gal ● Oddział=1, Magazyn=10, Numer partii=as-12-344-01  \P9100 ● Produkcja B-000050 ● 12/9/2015● 7 keg ● 27,00 gal ● Oddział=1,Magazyn=10,Numer partii=as-12-344-01 ● Produkty towarzyszące: P9101”, a następnie go zaznacz.     
2. W drzewie rozwiń węzeł opisany poniżej, a następnie go zaznacz.
    * Zaczynając od węzła, który właśnie został zaznaczony, rozwiń węzeł „M9103 ● Linia produkcyjna B-000050 ● 12/9/2015 ● -160,00 lb ● Rozmiar=70, Kolor=OK, Oddział=1, Magazyn=10, Numer partii=App01”, a następnie go zaznacz.  
3. Kliknij opcję Śledź od węzła.
4. Kliknij opcję W przód.
5. W okienku akcji kliknij pozycję Śledzenie.
    * Dostępnych jest kilka opcji śledzenia, które dostarczają informacji o odbiorcach wykorzystujących śledzony towar oraz o zamówieniach sprzedaży związanych z towarem, dla których towar został wysłany lub nie.   
6. Kliknij opcję Odbiorcy.
7. Zamknij stronę.
8. W okienku akcji kliknij pozycję Śledzenie.
9. Kliknij opcję Zamówienia sprzedaży, towary wysłane.
10. Zamknij stronę.

