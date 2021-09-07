---
title: Niepowodzenie księgowania arkusza z powodu niezbilansowania
description: W tym temacie wyjaśniono, dlaczego obciążenia i uznania mogą nie zostać zbilansowane w transakcjach na załączniku, przez co nie mogą zostać zaksięgowane. Temat zawiera również procedurę naprawy tego problemu.
author: kweekley
ms.date: 08/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-8-03
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: a59724ff698b6ad0e84b0642240da5f8953ab3d1
ms.sourcegitcommit: 9642494da87c0d237f9fcbe15df14315d9e88fa2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/15/2021
ms.locfileid: "7385730"
---
# <a name="journal-posting-failure-because-of-imbalance"></a>Niepowodzenie księgowania arkusza z powodu niezbilansowania

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, dlaczego obciążenia i uznania mogą nie zostać zbilansowane w transakcjach na załączniku, przez co nie mogą zostać zaksięgowane. Temat zawiera również procedurę naprawy tego problemu.

## <a name="symptom"></a>Objaw

W niektórych przypadkach nie można zaksięgować arkusza i wyświetlany jest następujący komunikat: „Transakcje w danym załączniku nie są zbilansowane na określony dzień (waluta rozliczeniowa: 0,01 - waluta raportowania: 0,06)”. Dlaczego arkusz nie może zostać zaksięgowany?

## <a name="resolution"></a>Rozwiązanie

Podczas księgowania w księdze głównej każdy załącznik musi być zbilansowany w walucie transakcji, walucie rozliczeniowej i walucie raportowania, o ile te waluty są zdefiniowane na stronie **Ustawienia księgi**. (Załączniki są bilansowane, gdy suma kwot po stronie Winien jest równa sumie po stronie Ma)

Sumy w dolnej części strony wierszy arkusza są wyświetlane w walucie rozliczeniowej i walucie raportowania. **Nie** są one wyświetlane w walucie transakcji w przypadku transakcji w walucie obcej. Ponadto komunikat o błędzie wyświetlany użytkownikom podczas symulacji lub księgowania pokazuje różnice tylko w walucie rozliczeniowej i walucie raportowania. Nie są one wyświetlane w walucie transakcji, ponieważ jeden załącznik może mieć więcej niż jedną walutę transakcji, a arkusz może zawierać załączniki w różnych walutach transakcji. Dlatego bardzo ważne jest sprawdzenie, czy kwoty w walucie transakcji każdego załącznika są zbilansowane.

### <a name="transaction-currency"></a>Waluta transakcji

Podczas symulacji i księgowania system sprawdza, czy każdy załącznik jest zbilansowany w walucie transakcji. W przypadku każdego wprowadzonego załącznika jako waluta transakcji może być używana jedna lub więcej walut. Na przykład załącznik wprowadzony w arkuszu ogólnym może mieć dwie waluty transakcji, gdy gotówka jest przelewana z konta bankowego w euro (EUR) na konto bankowe w dolarach kanadyjskich (CAD).

Jeśli załącznik ma tylko jedną walutę transakcji, sumy kwot po stronie Winien muszą być równe sumie kwot po stronie Ma tego załącznika. Użytkownicy napotkali następujące scenariusze, w których księgowanie nie powiodło się, ponieważ kwoty w walucie transakcji nie były zbilansowane:

- Sumy po stronach Winien i Ma **nie** były zbilansowane w walucie transakcji, ale były zbilansowane w walucie rozliczeniowej i walucie raportowania. Użytkownik zakłada, że załącznik zostanie jednak zaksięgowany. To założenie jest jednak mylne. **Kwoty w walucie transakcji w załączniku muszą być zawsze zbilansowane, jeśli wszystkie wiersze załącznika mają tę samą walutę.**
- Załącznik został zaimportowany w programie Microsoft Excel i użytkownik pomyślał, że kwoty w walucie transakcji są zbilansowane. W skoroszycie programu Excel zaimportowane kwoty zostały ustawione jako wartości **liczbowe**, a nie wartości **waluty**. W tym scenariuszu kwoty liczbowe w skoroszycie miały więcej niż dwa miejsca dziesiętne i więcej niż dwa miejsca dziesiętne zostały uwzględnione podczas importowania kwot. W związku z tym obciążenia nie są równe uznaniom, ponieważ różnią się między sobą ułamkami grosza. Arkusz nie odzwierciedla tej różnicy w wierszach załącznika, ponieważ wyświetlane kwoty mają tylko dwa miejsca dziesiętne.
- Załącznik został zaimportowany w programie Excel i użytkownik pomyślał, że kwoty w walucie transakcji są zbilansowane. Mimo że załącznik był zbilansowany, niektóre wiersze w załączniku miały różne daty transakcji. Jeśli dodano sumę obciążeń i sumę uznań na poziomie załącznika i daty transakcji, nie zostały one zbilansowane. System zapobiega teraz temu scenariuszowi. Załącznik może mieć tylko jedną datę transakcji. Wymaganie to jest wymuszane podczas wprowadzania załącznika za pośrednictwem ogólnego arkusza w systemie. Jednak pierwotnie nie było to wymuszane podczas importowania załącznika w programie Excel.

W jednym obsługiwanym scenariuszu załącznik może mieć więcej niż jedną walutę transakcji. W takim przypadku system **nie** sprawdza, czy kwota po stronie Winien jest równa kwotom po stronie Ma w walucie transakcji, ponieważ waluty nie są takie same. System sprawdza natomiast, czy kwoty w walucie rozliczeniowej są zbilansowane.

### <a name="accounting-currency"></a>Waluta rozliczeniowa

Jeśli wszystkie wiersze załącznika mają tę samą walutę transakcji i jeśli kwoty w walucie transakcji są zbilansowane, system sprawdza, czy kwoty w walucie rozliczeniowej są zbilansowane. Jeśli załącznik został wprowadzony w walucie obcej, kurs wymiany w wierszach załącznika jest używany do przeliczania kwot w walucie transakcji na walutę rozliczeniową. Najpierw każdy wiersz załącznika jest tłumaczony. Następnie wiersze są sumowane w celu określenia sum po stronach Winien i Ma. Ponieważ każdy wiersz jest tłumaczony, suma kwot po stronach Winien i Ma może nie być zbilansowana. Mimo tego, jeśli różnica znajduje się w granicach wartości **Maksymalna różnica w groszach** zdefiniowanej na stronie **Parametry księgi głównej**, załącznik zostanie zaksięgowany i różnica zostanie automatycznie zaksięgowana na koncie różnic w groszach.

Jeśli załącznik ma więcej niż jedną walutę transakcji, każdy wiersz załącznika jest przeliczany na walutę rozliczeniową, a następnie wiersze są sumowane w celu określenia łącznych kwot po stronie Winien i Ma. Aby można było uznać je za bilansowane, obciążenia i uznania muszą być zbilansowane i nie może być różnicy zaokrągleń do grosza.

### <a name="reporting-currency"></a>Waluta raportowania

Jeśli wszystkie wiersze załącznika mają tę samą walutę transakcji i jeśli kwoty w walucie transakcji są zbilansowane, system sprawdza, czy kwoty w walucie raportowania są zbilansowane. Jeśli załącznik został wprowadzony w walucie obcej, kurs wymiany w wierszach załącznika jest używany do przeliczania kwot w walucie transakcji na walutę raportowania. Najpierw każdy wiersz załącznika jest tłumaczony. Następnie wiersze są sumowane w celu określenia sum po stronach Winien i Ma. Ponieważ każdy wiersz jest tłumaczony, suma kwot po stronach Winien i Ma może nie być zbilansowana. Mimo tego, jeśli różnica znajduje się w granicach wartości **Maksymalne zaokrąglanie do grosza w walucie raportowania** zdefiniowanej na stronie **Parametry księgi głównej**, załącznik zostanie zaksięgowany i różnica zostanie automatycznie zaksięgowana na koncie różnic w groszach.

Jeśli załącznik ma więcej niż jedną walutę transakcji, każdy wiersz załącznika jest przeliczany na walutę raportowania, a następnie wiersze są sumowane w celu określenia łącznych kwot po stronie Winien i Ma. Aby można było uznać je za bilansowane, obciążenia i uznania muszą być zbilansowane i nie może być różnicy zaokrągleń do grosza.
