---
title: Tolerancja opóźnienia (dni z ujemnym opóźnieniem)
description: Ten temat zawiera informacje na temat obliczania tolerancji opóźnienia i jej wpływu na tworzenie planowanych zleceń w optymalizacji planowania.
author: crytt
ms.date: 07/30/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: c0bc3d429a1bf13285b385130d419f628330bb3728c6f071cf118edac2a59d87
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6778707"
---
# <a name="delay-tolerance-negative-days"></a>Tolerancja opóźnienia (dni z ujemnym opóźnieniem)

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]

Funkcja tolerancji opóźnienia umożliwia optymalizacji planowania uwzględnienie wartości **Ujemne dni** , która jest ustawiona dla grup pokrycia. Służy do przedłużenia okresu tolerancji opóźnienia stosowanego podczas planowania głównego. Pozwoli to uniknąć tworzenia nowych zamówień dostaw, jeśli istniejąca podaż będzie w stanie pokryć popyt w krótkim czasie. Celem tej funkcji jest określenie, czy tworzenie nowego zamówienia podażowego dla danego popytu ma sens.

## <a name="turn-on-the-feature-in-your-system"></a>Włączanie funkcji w systemie

Aby udostępnić funkcję w systemie, przejdź do modułu [Zarządzanie funkcjami](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) i włącz funkcję *Ujemne dni w optymalizacji planowania*.

## <a name="delay-tolerance-in-planning-optimization"></a>Tolerancja opóźnienia w optymalizacji planowania

Tolerancja opóźnienia reprezentuje liczbę dni poza czasem realizacji, którą jesteś skłonny odczekać przed zamówieniem nowego uzupełnienia, gdy istniejąca dostawa jest już zaplanowana. Tolerancja opóźnień jest określana przy użyciu dni kalendarzowych, a nie dni roboczych.

W planowaniu głównym, podczas obliczania przez system tolerancji opóźnienia, jest ono rozważane przy ustawieniu **Liczby dni z ujemnym czasem**. **Liczbę dni z ujemnym stanem** można określić albo na stronie **Zapotrzebowanie na towar**, albo na stronie **Grupy zapotrzebowania**.

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
