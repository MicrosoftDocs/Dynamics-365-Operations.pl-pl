---
title: Tolerancja opóźnienia (dni z ujemnym opóźnieniem)
description: Ten artykuł zawiera informacje na temat obliczania tolerancji opóźnienia i jej wpływu na tworzenie planowanych zleceń w optymalizacji planowania.
author: t-benebo
ms.date: 08/09/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: fa4d2d1506546cacf5f9a7ec936f17601c5727d2
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/23/2022
ms.locfileid: "9335384"
---
# <a name="delay-tolerance-negative-days"></a>Tolerancja opóźnienia (dni z ujemnym opóźnieniem)

[!include [banner](../../includes/banner.md)]

Funkcja tolerancji opóźnienia umożliwia optymalizacji planowania uwzględnienie wartości **Ujemne dni**, która jest ustawiona dla grup pokrycia, zapotrzebowania na towary lub planów głównych. Służy do przedłużenia okresu tolerancji opóźnienia stosowanego podczas planowania głównego. Pozwoli to uniknąć tworzenia nowych zamówień dostaw, jeśli istniejąca podaż będzie w stanie pokryć popyt w krótkim czasie. Celem tej funkcji jest określenie, czy tworzenie nowego zamówienia podażowego dla danego popytu ma sens.

## <a name="turn-delay-tolerance-features-on-or-off"></a>Wyłącz lub wyłącz funkcje tolerancji opóźnienia

Aby udostępnić funkcję w systemie, przejdź do modułu [Zarządzanie funkcjami](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) i włącz następujące funkcje:

- *Dni z ujemną wartością optymalizacji planowania* — ta funkcja włącza ustawienia dotyczące ujemnych liczby dni dla grup zapotrzebowania i zapotrzebowania na towar. Od wersji 10.0.29 Supply Chain Management funkcja jest obowiązkowa i nie można jej wyłączyć.
- *Automatyzacja dostaw produkcji na zamówienie* — ta funkcja umożliwia ustawienia ujemnych dni dla planów główne. (Aby uzyskać więcej informacji, zobacz temat [Automatyzacja dostaw produktów na zamówienie](../make-to-order-supply-automation.md).)

## <a name="delay-tolerance-in-planning-optimization"></a>Tolerancja opóźnienia w optymalizacji planowania

Tolerancja opóźnienia reprezentuje liczbę dni poza czasem realizacji, którą jesteś skłonny odczekać przed zamówieniem nowego uzupełnienia, gdy istniejąca dostawa jest już zaplanowana. Tolerancja opóźnień jest określana przy użyciu dni kalendarzowych, a nie dni roboczych.

W planowaniu głównym, podczas obliczania przez system tolerancji opóźnienia, jest ono rozważane przy ustawieniu **Liczby dni z ujemnym czasem**. Możesz ustawić wartość **Dni ujemne** na stronie **Grupy pokrycia**, **Pokrycie pozycji** lub **Plany główne**. Jeśli na więcej niż jednym poziomie są przypisywane dni z ujemnym poziomem, do decydowania, które ustawienie ma być stosowane, system stosuje następującą hierarchię:

- Jeśli na stronie **Plany główne** włączono dni ujemne, to ustawienie zastępuje wszystkie inne ustawienia dni ujemnych po uruchomieniu planu.
- Jeśli na stronie **Zapotrzebowania na towar** skonfigurowano ujemne liczby dni, ustawienie to zastępuje ustawienie grupy zapotrzebowania.
- Ujemne liczby dni skonfigurowane na stronie **Grupy zapotrzebowania** obowiązują tylko wtedy, gdy dla odpowiedniego towaru lub planu nie skonfigurowano dni z ujemnym dniem.

System łączy obliczenia tolerancji opóźnienia z *najbliższą datą uzupełnienia*, która jest równa dzisiejszej dacie plus czas realizacji. Tolerancja opóźnienia jest obliczana przy użyciu następującej formuły, w której wartość *max()* to większa z dwóch wartości:

*maks.(Najwcześniejsza data uzupełnienia, Termin realizacji zapotrzebowania)* - *Termin realizacji zapotrzebowania* + *Dni ujemne*

Formuła gwarantuje, że planowanie główne nie będzie tworzyć nowych zamówień dostaw, jeśli w czasie realizacji produktu będzie istniała wystarczająca dostawa.

> [!NOTE]
> Obliczanie tolerancji opóźnienia w optymalizacji planowania wykorzystuje zawsze dynamiczne obliczanie dni ujemnych z wbudowanego planowania głównego. Ustawienie **Użyj dynamicznej liczby dni ujemnych** na stronie **Parametry planowania głównego** nie ma wpływu na to zachowanie.

Jeśli istniejąca podaż implikuje opóźnienie popytu, które jest mniejsze lub równe obliczonej tolerancji opóźnienia, optymalizacja planowania łączy istniejącą podaż z popytem. W niektórych przypadkach lepiej jest opóźnić popyt niż skończyć z nadpodażą.

Poniższe podrozdziały przedstawiają przykłady, które pokazują, jak tolerancja opóźnień wpływa na tworzenie planowanych zleceń w optymalizacji planowania.

### <a name="example-1"></a>Przykład 1

Produkt ma następującą konfigurację:

- **Czas realizacji:** *10*
- **Ilość dni z ujemnym stanem magazynu:** *2*

W przypadku tego produktu istnieje następująca podaż i popyt:

- **Popyt dzisiaj:** Zamówienie sprzedaży na ilość 10
- **Dostawa w ciągu 12 dni:** Zamówienie zakupu na ilość 10

Istniejąca podaż może pokryć zapotrzebowanie w ciągu 12 dni, a okres ten jest równy tolerancji opóźnienia. W związku z tym podczas pracy planowania głównego nie są tworzone żadne planowane zlecenia.

### <a name="example-2"></a>Przykład 2

Produkt ma następującą konfigurację:

- **Czas realizacji:** *10*
- **Ilość dni z ujemnym stanem magazynu:** *0*

W przypadku tego produktu istnieje następująca podaż i popyt:

- **Popyt dzisiaj:** Zamówienie sprzedaży na ilość 10
- **Dostawa w ciągu 12 dni:** Zamówienie zakupu na ilość 10

Istniejąca podaż może pokrywać popyt tylko po 12 dniach. Jednak tolerancja opóźnienia wynosi 10 dni. Dlatego podczas planowania głównego tworzone jest zamówienie planowane na ilość 10.

### <a name="example-3"></a>Przykład 3

Produkt ma następującą konfigurację:

- **Czas realizacji:** *10*
- **Ilość dni z ujemnym stanem magazynu:** *2*

W przypadku tego produktu istnieje następująca podaż i popyt:

- **Popyt za 11 dni:** Zamówienie sprzedaży na ilość 10
- **Dostawa w ciągu 14 dni:** Zamówienie zakupu na ilość 10

Istniejąca podaż może pokrywać popyt tylko po 3 dniach. Jednak tolerancja opóźnienia wynosi 2 dni. (W tym przypadku tolerancja opóźnienia obejmuje tylko dwa dni ujemne. Data zapotrzebowania nie jest uwzględniana, ponieważ jest po czasie realizacji produktu). Dlatego przy uruchomieniu planowania głównego zostanie utworzone planowane zamówienie na ilość 10 sztuk.
