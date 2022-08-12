---
title: Konfigurowanie struktury konta
description: Ten artykuł zawiera informacje dotyczące struktury kont i wymiarów finansowych.
author: aprilolson
ms.date: 07/12/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerEliminationRule
audience: Application User
ms.reviewer: twheeloc
ms.custom: 13131
ms.assetid: 08fd46ef-2eb8-4942-985d-40fd757b74a8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0f816f0fc894b902c444a3113abfd48d4146d485
ms.sourcegitcommit: e59990780830ac8e3382fea5df851abe86fbf496
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/13/2022
ms.locfileid: "9141287"
---
# <a name="configure-account-structures"></a>Skonfiguruj strukturę konta

[!include[banner](../includes/banner.md)]

Struktury kont wykorzystują konto główne i wymiary finansowe do tworzenie zestawu reguł, które określają kolejność i wartości używane podczas wprowadzania numeru konta. Można stworzyć dowolną liczbę struktur kont potrzebnych w firmie. Struktury konta są przypisywane do ustawień księgi firmy, więc mogą być współużytkowane.

Podczas tworzenia struktury konta maksymalna liczba segmentów to 11. Jeśli potrzebujesz jeszcze więcej segmentów, kompleksowo oceń swoją konfigurację i wymagania, ponieważ wpłynie to na środowisko obsługi użytkowników. Należy wziąć pod uwagę, czy można utworzyć segment pochodny w scenariuszu raportowania przy użyciu hierarchii, a nie podczas wprowadzania danych, lub za pomocą pola zdefiniowane przez użytkownika. Na przykład jeśli chcesz raportować z lokalizacji, ale nie można ustalić działu lub centrum kosztów, w którym znajduje się lokalizacja, nie potrzebujesz lokalizacji jako wymiaru finansowego. Jeśli po ocenie stwierdzisz, że potrzeba więcej niż 11 segmentów, można dodać kolejne segmenty za pomocą reguł zaawansowanych.

Struktury kont wymagają konta głównego. Konto główne nie musi być pierwszym segmentem w strukturze, ale wskazuje, jaka struktura konta jest używana podczas wprowadzania numeru konta. W związku z tym wartości konta głównego może istnieć tylko w jednej strukturze przypisanej do księgi, tak aby wartości nie zachodziły na siebie. Po zidentyfikowaniu struktury konta zostanie wyfiltrowana lista dozwolonych wartości, pozwalając użytkownikowi wybierać tylko prawidłowe wartości wymiarów i w ten sposób zmniejszając ryzyko dokonania błędnego wpisu w arkuszu.

> [!NOTE] 
> Jeśli masz zamiar budżetować względem wymiaru finansowego, musi on być częścią struktury konta. Obecnie mechanizm budżetowania nie korzysta z reguł zaawansowanych.

## <a name="example"></a>Przykład
Aby zilustrować najlepszy sposób konfigurowania struktury konta, załóżmy, że firma chce śledzić konta bilansowe (100000..399999) na poziomie konta i wymiaru finansowego jednostki biznesowej. Dla kont przychodów i wydatków (400000..999999) śledzi wymiary finansowe Jednostka biznesowa, Dział i Centrum kosztów. Jeśli coś sprzeda, chce również śledzić odbiorcę. W czasie używania tego scenariusza, zalecane jest posiadanie dwóch struktur kont przypisanych do księgi firmy — jeden dla kont bilansowych, a drugi dla rachunków zysków i strat. Aby zoptymalizować czynności użytkownika i sprawdzanie poprawności, Odbiorca powinien być regułą zaawansowaną, która jest używana tylko w przypadku użycia konta sprzedaży.

**Struktura konta bilansowego**

|Konto główne          | Jednostka biznesowa    |
|----------------------|-----------|
|100000..399999 | *;” “|

**Struktura konta wynikowego**

|Konto główne          | Jednostka biznesowa    |Dział          | Centrum kosztu    | &nbsp; |
|----------------------|------------------|--------------------|-----------|---|
|400000..999999 | \*;” “| \*;” “| \*;” “| \*;” “|

**Zaawansowana reguła dodawania odbiorcy**

Kryteria: Gdy konto główne mieści się w zakresie id 400000 do 499999, należy dodać odbiorcę. Nie może pozostać puste.

|Odbiorca         |
|-----------------|
|* |

W tym uproszczonym przykładzie są dozwolone wszystkie wartości i puste pole, więc są używane symbole * i „ ”.

## <a name="segments-and-allowed-values"></a>Segmenty i dozwolone wartości
Sekcje **Segmenty** i **Szczegóły dozwolonych wartości** zawierają siatkę umożliwiającą wprowadzanie reguł, które będą egzekwowane podczas sprawdzania poprawności w trakcie księgowania. Można wprowadzać tekst bezpośrednio w komórkach siatki, zaimportować go z programu Excel lub użyć sekcji **Szczegóły wartości dozwolonych** w celu otrzymania wskazówek wypełniania.

Opcje w sekcji **Szczegóły dozwolonych wartości** prowadzą użytkownika przez proces tworzenia kryteriów za pomocą elementów **Operatory**, takich jak „zaczyna się od”, „zawiera się między”, „zawiera” itd.

[![Dozwolone wartości.](./media/account.png)](./media/account.png) 

Dozwolone wartości będą domyślne na stronie wprowadzania arkusza lub zasad podziału księgowań, jeśli nie istnieją inne wartości, które można wybrać zgodnie z ustawieniami struktury konta.

Oto przykład **struktury konta wynikowego**.

|Konto główne          | Jednostka biznesowa    |Dział          | MPK    |
|----------------------|-----------|----------------------|-----------|
|400000..999999 | 002 | 022 | 014 |

Podczas wprowadzania arkusza i wybierania konta w zakresie wyników wybranie jednostki biznesowej „002” spowoduje, że wartości 022 i 014 będą domyślne w formancie konta. Takie zachowanie będzie również występowało na stronie zasady podziału księgowań. 

## <a name="more-than-7-criteria-needed"></a>Potrzebna więcej niż 7 kryteriów

Jeśli potrzebujesz więcej niż 7 kryteriów, możesz je dodać w następnym wierszu. Podczas pracy w sekcji **Szczegóły wartości dozwolonych** zauważysz, że po wprowadzeniu siódmego kryterium nie jest już aktywne pole dodawania kryteriów **+Dodaj nowe**. Jest to spowodowane wieloma czynnikami takimi jak: 
 - Szerokość kolumny 
 - Sposób przechowywania danych 
 - Działanie formantu **Szczegóły dozwolonych wartości**
 - Zdatność  
 
Aby kontynuować dodawanie dodatkowych kryteriów, kliknij przycisk **Duplikuj segment** i **Sekcja dozwolonych wartości**. Spowoduje to skopiowanie kryteriów do nowego wiersza. Można następnie nadpisać lub zmodyfikować sekcję **Szczegóły wartości dozwolonych**.

## <a name="best-practices"></a>Najlepsze praktyki
Podczas konfigurowania struktur kont zaleca się przestrzeganie pewnych najlepszych praktyk. Jednak jest to tylko wskazówka, a całościowa dyskusja powinna uwzględniać kwestie sytuacji firmy, planu rozwoju i planu konserwacji.

- Utwórz konto główne najpierw lub umieść je jak najbliżej z przodu struktury konta, tak aby podczas dokonywania zapisów na koncie użytkownicy byli najlepiej kierowani przez kolejne etapy.
  
  - Sprawdź, czy rozwiązania innych firm, których zamierzasz używać, obsługują konto główne na pierwszej pozycji.

- W jak największym stopniu wykorzystuj istniejące struktury kont, aby uprościć zarządzanie we wszystkich firmach.

- Dla odmian istniejących w różnych firmach należy rozważyć używanie reguł zaawansowanych, tak aby wykorzystywać istniejące struktury konta.

- Podczas definiowania dozwolonych wartości, należy użyć jak najwięcej zakresów i symboli wieloznacznych. Nie tylko umożliwia to wzrost i zmianę bez obsługi technicznej, ale system również działa lepiej w tej konfiguracji.

- Nie ograniczaj się tylko do umieszczenia gwiazdki obok każdego segmentu w strukturze konta, a następnie nie polegaj wyłącznie na regułach zaawansowanych. Może to być trudne do zarządzania i często prowadzi do błędów użytkownika podczas obsługi technicznej, co może powodować niemożność zaksięgowania przez system.

## <a name="account-structure-activation"></a>Aktywacja struktury konta
Jeśli nowe ustawienie lub zmiana struktury konta są zgodne z oczekiwaniami, musisz je aktywować. Jeśli struktura konta jest przypisana do księgi, ten proces aktywacji może potrwać bardzo długo, ponieważ wszystkie niezaksięgowane transakcje w systemie muszą zostać zsynchronizowane z nową strukturą. Zmiany struktury konta nie mają wpływu na zaksięgowane transakcje.

Aby uzyskać więcej informacji, zobacz [Planowanie planu kont](plan-chart-of-accounts.md), [Wymiary finansowe](financial-dimensions.md) i [Wpisywanie kombinacji wymiarów i kont (formant Wpis podzielony na segmenty)](enter-account-dimension-combinations-segmented-entry-control.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
