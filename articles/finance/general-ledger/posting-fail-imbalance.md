---
title: Niepowodzenie księgowania arkusza z powodu niezbilansowania
description: W tym artykule wyjaśniono, dlaczego obciążenia i uznania mogą nie zostać zbilansowane w transakcjach na załączniku, przez co nie mogą zostać zaksięgowane. Artykuł zawiera również procedurę naprawy tego problemu.
author: kweekley
ms.date: 08/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-8-03
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: f5afded3d5c42f8dab465b668e4c1fcdaed8c215
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8861337"
---
# <a name="journal-posting-failure-because-of-imbalance"></a>Niepowodzenie księgowania arkusza z powodu niezbilansowania

[!include [banner](../includes/banner.md)]

W tym artykule wyjaśniono, dlaczego obciążenia i uznania mogą nie zostać zbilansowane w transakcjach na załączniku, przez co nie mogą zostać zaksięgowane. Artykuł zawiera również procedurę naprawy tego problemu.

## <a name="symptom"></a>Objaw

W niektórych przypadkach nie można zaksięgować arkusza i wyświetlany jest następujący komunikat: „Transakcje w danym załączniku nie są zbilansowane na określony dzień (waluta rozliczeniowa: 0,01 - waluta raportowania: 0,06)”. Dlaczego arkusz nie może zostać zaksięgowany?

## <a name="resolution"></a>Rozwiązanie

Podczas księgowania w księdze głównej każdy załącznik musi być zbilansowany w walucie transakcji, walucie rozliczeniowej i walucie raportowania, o ile te waluty są zdefiniowane na stronie **Ustawienia księgi**. (Załączniki są bilansowane, gdy suma kwot po stronie Winien jest równa sumie po stronie Ma)

Sumy w dolnej części strony wierszy arkusza są wyświetlane w walucie rozliczeniowej i walucie raportowania. **Nie** są one wyświetlane w walucie transakcji w przypadku transakcji w walucie obcej. Ponadto komunikat o błędzie wyświetlany użytkownikom podczas symulacji lub księgowania pokazuje różnice tylko w walucie rozliczeniowej i walucie raportowania. Nie są one wyświetlane w walucie transakcji, ponieważ jeden załącznik może mieć więcej niż jedną walutę transakcji, a arkusz może zawierać załączniki w różnych walutach transakcji. Dlatego bardzo ważne jest ręczne sprawdzenie, czy kwoty w walucie transakcji dla każdego załącznika, który ma tylko jedną walutę transakcji, są zbilansowane.

### <a name="transaction-currency"></a>Waluta transakcji

Podczas symulacji i księgowania system sprawdza, czy każdy załącznik, który ma tylko jedną walutę transakcji, jest zbilansowany w walucie transakcji. W przypadku każdego wprowadzonego załącznika jako waluta transakcji może być używana jedna lub więcej walut. Na przykład załącznik wprowadzony w arkuszu ogólnym może mieć dwie waluty transakcji, gdy gotówka jest przelewana z konta bankowego w euro (EUR) na konto bankowe w dolarach kanadyjskich (CAD).

Jeśli załącznik ma tylko jedną walutę transakcji, sumy kwot po stronie Winien muszą być równe sumie kwot po stronie Ma w walucie transakcji dla tego załącznika. Użytkownicy napotkali następujące scenariusze, w których księgowanie nie powiodło się, ponieważ kwoty w walucie transakcji nie były zbilansowane:

- Sumy po stronach Winien i Ma **nie** były zbilansowane w walucie transakcji, ale były zbilansowane w walucie rozliczeniowej i walucie raportowania. Użytkownik zakłada, że załącznik zostanie jednak zaksięgowany. To założenie jest jednak mylne. **Kwoty w walucie transakcji w załączniku muszą być zawsze zbilansowane, jeśli wszystkie wiersze załącznika mają tę samą walutę transakcji.**
- Załącznik został zaimportowany z jednostką danych za pośrednictwem struktury zarządzania danymi (DMF), a użytkownik myślał, że kwoty w walucie transakcji były zbilansowane. W zaimportowanym pliku niektóre kwoty miały więcej niż dwa miejsca dziesiętne i więcej niż dwa miejsca dziesiętne zostały uwzględnione podczas importowania kwot. W związku z tym obciążenia nie są równe uznaniom, ponieważ różnią się między sobą ułamkami grosza. Arkusz nie odzwierciedla tej różnicy w wierszach załącznika, ponieważ wyświetlane kwoty mają tylko dwa miejsca dziesiętne.
- Załącznik został zaimportowany z jednostką danych w strukturze zarządzania danymi i użytkownik myślał, że kwoty w walucie transakcji były zbilansowane. Mimo że **załącznik** był zbilansowany, niektóre wiersze w załączniku miały różne daty transakcji. Jeśli dodano sumę obciążeń i sumę uznań w walucie transakcji na **załącznik i datę transakcji**, nie zostały one zbilansowane. Wymaganie to jest wymuszane podczas wprowadzania załącznika za pośrednictwem ogólnego arkusza w systemie. Jednak nie jest on wymuszany podczas importowania załącznika z jednostką danych za pośrednictwem struktury zarządzania danymi.

W jednym obsługiwanym scenariuszu załącznik może mieć więcej niż jedną walutę transakcji. W takim przypadku system **nie** sprawdza, czy kwota po stronie Winien jest równa kwotom po stronie Ma w walucie transakcji, ponieważ waluty nie są takie same. System sprawdza natomiast, czy kwoty w walucie rozliczeniowej i walucie raportowania są zbilansowane.

### <a name="accounting-currency"></a>Waluta rozliczeniowa

Jeśli wszystkie wiersze załącznika mają tę samą walutę transakcji i jeśli kwoty w walucie transakcji są zbilansowane, system sprawdza, czy kwoty w walucie rozliczeniowej są zbilansowane. Jeśli załącznik został wprowadzony w walucie obcej, kurs wymiany w wierszach załącznika jest używany do przeliczania kwot w walucie transakcji na walutę rozliczeniową. Po pierwsze, każdy wiersz załącznika jest tłumaczony i zaokrąglany do dwóch miejsc dziesiętnych. Następnie wiersze są sumowane w celu określenia sum po stronach Winien i Ma. Ponieważ każdy wiersz jest tłumaczony, suma kwot po stronach Winien i Ma może nie być zbilansowana. Mimo tego, jeśli całkowita wartość różnicy znajduje się w granicach wartości **Maksymalna różnica w groszach** zdefiniowanej na stronie **Parametry księgi głównej**, załącznik zostanie zaksięgowany i różnica zostanie automatycznie zaksięgowana na koncie różnic w groszach.

Jeśli załącznik ma więcej niż jedną walutę transakcji, każdy wiersz załącznika jest przeliczany na walutę rozliczeniową i zaokrąglany do dwóch miejsc po przecinku, a następnie wiersze są sumowane w celu określenia łącznych kwot po stronie Winien i Ma. Aby można było uznać je za bilansowane, obciążenia i uznania muszą być zbilansowane w walucie księgowania.  Konto różnic groszowych nie jest nigdy dodawane do załącznika w walucie księgowania w celu zbilansowania kwot debetowych i kredytowych. 

### <a name="reporting-currency"></a>Waluta raportowania

Jeśli wszystkie wiersze załącznika mają tę samą walutę transakcji i jeśli kwoty w walucie transakcji są zbilansowane, system sprawdza, czy kwoty w walucie raportowania są zbilansowane. Jeśli załącznik został wprowadzony w walucie obcej, kurs wymiany w wierszach załącznika jest używany do przeliczania kwot w walucie transakcji na walutę raportowania. Po pierwsze, każdy wiersz załącznika jest tłumaczony i zaokrąglany do dwóch miejsc dziesiętnych. Następnie wiersze są sumowane w celu określenia sum po stronach Winien i Ma. Ponieważ każdy wiersz jest tłumaczony, suma kwot po stronach Winien i Ma może nie być zbilansowana. Mimo tego, jeśli różnica znajduje się w granicach wartości **Maksymalne zaokrąglanie do grosza w walucie raportowania** zdefiniowanej na stronie **Parametry księgi głównej**, załącznik zostanie zaksięgowany i różnica zostanie automatycznie zaksięgowana na koncie różnic w groszach.

Jeśli załącznik ma więcej niż jedną walutę transakcji, każdy wiersz załącznika jest przeliczany na walutę raportowania i zaokrąglany do dwóch miejsc po przecinku, a następnie wiersze są sumowane w celu określenia łącznych kwot po stronie Winien i Ma. Aby można było uznać je za bilansowane, obciążenia i uznania muszą być zbilansowane w walucie raportowania.  Konto różnic groszowych nie jest nigdy dodawane do załącznika w walucie raportowania w celu zbilansowania kwot debetowych i kredytowych.

### <a name="example-for-an-accounting-currency-imbalance"></a>Przykład niezbilansowania waluty rozliczeniowej

> [!NOTE]
> Kwota w walucie raportowania jest obliczana na podstawie kwoty w walucie transakcji w taki sam sposób, jak kwota w walucie rozliczeniowej.

Kurs wymiany: 1,5

| Wiersz | Załącznik | Konto | Waluta | Debet (transakcja) | Kredyt (transakcja) | Debet (księgowanie) | Kredyt (księgowanie) |
|---|---|---|---|---|---|---|---|
| 1 | 001 | 1101-01 | EUR | 3.33 | | 5,00 (4,995) | |
| 2 | 001 | 1101-02 | EUR | 3.33 | | 5,00 (4,995) | |
| 3 | 001 | 1101-03 | EUR | 3.34 | | 5.01 | |
| 4 | 001 | 4101- | EUR | | 10,00 | | 15.00 |
| **Razem** | | | | **10.00** | **10.00** | **15.01** | **15.00** |

Waluta rozliczeniowa jest poza saldem o 0,01. Jeśli jednak maksymalne zaokrąglenie groszowe w walucie rozliczeniowej wynosi co najmniej 0,01, różnica zostanie automatycznie zaksięgowana na koncie różnic groszowych i załącznik zostanie pomyślnie zaksięgowany.
