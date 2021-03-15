---
title: Konfiguracja zarządzania kredytem
description: W tym temacie opisano ustawienia wymagane do zarządzania kredytami.
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: a2aa1980ebc1fa8412fc388e7837bc40b6902bc0
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4991265"
---
# <a name="credit-management-setup"></a>Konfiguracja zarządzania kredytem 

[!include [banner](../includes/banner.md)]

## <a name="credit-management-workflows"></a>Przepływy prac dotyczące zarządzania kredytem

Przejdź do **Kredyt i windykacje \> Konfiguracja \> Przepływów pracy zarządzania kredytami**, aby zdefiniować przepływy pracy służące do zarządzania korektami limitu kredytu.

- Można utworzyć przepływ pracy, który umożliwi zatwierdzenie partii limitów kredytu za pomocą jednego zatwierdzenia.
- Istnieje możliwość dodania przepływu pracy na poziomie wiersza, dzięki czemu korekty limitu kredytu mogą być zatwierdzane pojedynczo.
- Można utworzyć przepływ pracy zwalniania, który będzie automatycznie przekierowywał wstrzymania do procesu przepływu pracy.

## <a name="blocking-rules"></a>Reguły blokowania

### <a name="ranking-payment-terms"></a>Ranking warunków płatności

Zamówienie sprzedaży można wstrzymać, jeśli warunki płatności w zamówieniu nie są zgodne z domyślnymi warunkami płatności dla odbiorcy. Jednak czasami warunki płatności różnią się, ale są wystarczająco podobne, że zamówienie nie powinno być wstrzymane. Warunki płatności można klasyfikować w taki sposób, aby niektóre z nich miały taką samą rangę, natomiast inne mają wyższą lub niższą rangę.

Jeśli są aktywne rankingi warunków płatności i jeśli warunki płatności w zamówieniu mają wyższą rangę niż domyślne warunki płatności dla odbiorcy, zamówienie sprzedaży zostanie wstrzymane.

Można ustawić klasyfikację warunków płatności przechodząc do **Kredyt i windykacje \> Ustawienia \> Ustawienia zarządzania kredytami  \>Klasyfikuj warunki płatności**  

### <a name="ranking-settlement-discounts"></a>Ranking rabatów rozliczenia

Zamówienie sprzedaży można wstrzymać, jeśli rabaty w gotówce w zamówieniu nie są zgodne z domyślnym rabatem w gotówce dla odbiorcy. Jednak czasami rabaty w gotówce różnią się, ale są wystarczająco podobne, że zamówienie nie powinno być wstrzymane. Rabaty w gotówce można klasyfikować w taki sposób, aby niektóre z nich miały taką samą rangę, natomiast inne mają wyższą lub niższą rangę.

Jeśli są aktywne rankingi rabatów w gotówce i jeśli rabat w gotówce w zamówieniu ma wyższą rangę niż domyślny rabat w gotówce dla odbiorcy, zamówienie sprzedazy zostanie wstrzymane.

Można ustawić klasyfikację warunków płatności przechodząc do **Kredyt i windykacje \> Ustawienia \> Ustawienia zarządzania kredytami  \>Klasyfikuj rabaty rozliczeń**  

## <a name="reasons"></a>Przyczyny

W zarządzaniu kredytami używane są różne typy przyczyn:

- Przyczyny wstrzymania wskazuje, dlaczego zamówienie sprzedaży zostało wstrzymane.
- Przyczyny zwolnienia są przypisywane do zamówienia, gdy jest ono zwalniane z wstrzymania.
- Przyczyny stanu wskazuje, dlaczego stan konta został przypisany do odbiorcy.

Przyczyny można określić na stronie **Przyczyny zarządzania kredytami** (**Kredyt i windykacje \> Konfiguracja \> Ustawienia zarządzania kredytem \> Przyczyny zarządzania kredytami**).

1. W polu **Typ przyczyny** wybierz typ przyczyny: **wstrzymanie**, **zwolnienie** lub **stan**.
2. W polu **Przyczyna** wprowadź nazwę dla przyczyny.
3. W polu **Opis** wprowadź opis kodu przyczyny.

## <a name="credit-management-groups"></a>Grupy zarządzania kredytem

Grupy zarządzania kredytami służą do identyfikowania odbiorców lub grup odbiorców o takich samych właściwościach zarządzania kredytami. Na przykład grupy zarządzania kredytami mogą być używane do określenia blokowania i wykluczania reguł zarządzania kredytami dla odbiorców.

Grupy zarządzania kredytem można tworzyć na stronie **Grupy zarządzania kredytami** (**Kredyt i windykacje \> Konfiguracja > Ustawienia zarządzania kredytem \> Grupy zarządzania kredytem**).

1. Wybierz **Nowy**, aby utworzyć wiersz.
2. Umożliwia wprowadzenie identyfikatora grupy. Identyfikator może zawierać maksymalnie 10 znaki.
3. W polu **Opis** wprowadź nazwę grupy. Nazwa może zawierać maksymalnie 60 znaki.

Grupa zarządzania kredytami jest przypisywana do odbiorcy w formularzu **Kredyty i windykacje** na skróconej karcie na stronie **Wszyscy odbiorcy** (**Rozrachunki z odbiorcami \> Odbiorcy \> Wszyscy odbiorcy**).

## <a name="account-statuses"></a>Stany kont

Istnieje możliwość tworzenia stanu konta w celu zidentyfikowania pozycji kredytowej konta odbiorcy. Można zdefiniować stan i jego wpływ na procesy fakturowania i dostawy. Stanów kont można również używać do ustalania reguł blokowania dla odbiorcy.

Stan konta można utworzyć na stronie **Stany konta** (**Kredyt i windykacje \> Konfiguracja > Ustawienia zarządzania kredytem \> Stany konta**).

1. Dodaj stan konta i wprowadź opis odpowiadający pozycji kredytowej odbiorcy. Na przykład można skorzystać zopcji **Normalny** , aby wskazać, że odbiorca jest w dobrym stanie, a otwarte zamówienia podlegają standardowemu przetwarzaniu zarządzania kredytami.
2. W polach **Fakturowanie** i **Dostawa w wstrzymaniu** wybierz typ wstrzymania dla odbiorców posiadających ten stan konta. W przypadku stosowania reguł limitu kredytu można przechować wszystkie procesy przetwarzania, zatrzymać tylko przetwarzanie faktur lub wstrzymać przetwarzanie.

## <a name="scoring-groups"></a>Grupy oceny

Istnieje możliwość skonfigurowania grup punktacji w celu zdefiniowania czynników ryzyka oraz kryteriów, które są używane do ich mierzenia. Gdy informacje o odbiorcy są stosowane do grupy punktowanej, obliczany jest wynik dla każdego współczynnika ryzyka i używany do odłożenia odbiorcy z grupy ryzyka. Grupa ryzyka może służyć do identyfikowania zdolności kredytowych i obliczania automatycznych limitów kredytu.

Można utworzyć grupy oceniania na stronie **Grupy punktacji** (**Kredyt i windykacje \> Konfiguracja \> Ustawienia zarządzania kredytem \> Ryzyko \> Grupy punktacji**).

1. Utwórz grupę punktacji i nadaj jej nazwę.
2. Wprowadź opis, aby dokładniej opisać grupę punktacji.
3. Wybierz typ grupy. Istnieje osiem wstępnie zdefiniowanych typów. Można również wybrać opcję **Zdefiniowany przez użytkownika**, aby zdefiniować typ grupy lepiej dostosowany do potrzeb danej organizacji.
4. Umożliwia wybór typu wyniku określającego sposób obliczania wyniku ryzyka przez grupę punktacji. Dostępne są następujące opcje:

    - **Zakres** — ta opcja służy do definiowania zakresu wartości, które powinny być używane do obliczania punktacji.
    - **Zdefiniowany przez użytkownika** — ta opcja służy do ręcznego definiowania listy wartości, które powinny być używane dla punktacji.

5. Jeśli wybrano **Zakres** jako typ punktacji, należy dodać wiersze w celu zdefiniowania zakresu wartości oraz odpowiednich wyników.

    1. W polu **Od wartości** określ najniższą wartość w zakresie.
    2. W polu **Do wartości** określ najwyższą wartość w zakresie.
    3. W polu **Punktacja** wprowadź wartość, która powinna zostać przypisana, gdy określona wartość jest w zakresie „od"/„do".

    Jeśli wybrano **Definiowany przez użytkownika** jako typ punktacji, należy dodać wiersze w celu zdefiniowania wartości zdefiniowanych przez użytkownika oraz odpowiednich wyników.

    1. W polu **Wartość** wprowadź zdefiniowaną przez użytkownika wartość, która powinna zostać dostarczona z informacji o odbiorcy.
    2. W polu **Punktacja** wprowadź wartość, która powinna zostać przypisana, gdy określona wartość jest w zakresie „od"/„do".

## <a name="risk-classification"></a>Klasyfikacja ryzyka

Można zdefiniować oceny ryzyka, które można przypisać do odbiorców, na podstawie ich wyniku ryzyka. Wynik ryzyka jest obliczany przez porównanie informacji o klientach z każdą grupą punktowaną. Wyniki są sumowane, a wynik łączny jest porównywany z wartościami w ustawieniach grupy ryzyka w celu zidentyfikowania grupy ryzyka, do której należy dany odbiorca. Wyniki grupy ryzyka służą do definiowania reguł blokowania i wykluczania zarządzania kredytami dla odbiorcy.

Istnieje możliwość skonfigurowania grup ryzyka na stronie **Oceny ryzyka** (**Kredyt i windykacje \> Konfiguracja \> Ustawienia zarządzania kredytem \> Ryzyko \> Klasyfikacja ryzyka**).

1. Umożliwia wprowadzenie identyfikatora grupy ryzyka.
2. Wprowadź opis, aby dokładniej opisać grupę ryzyka.
3. Umożliwia wprowadzenie zakresu wyników służącego do ustalenia, którzy odbiorcy należą do grupy ryzyka.
4. Wybierz wskaźnik grupy ryzyka, aby określić symbol reprezentujący grupę ryzyka.

## <a name="guaranteeinsurance-types"></a>Typy gwarancji/ubezpieczenia

Typy gwarancji/ubezpieczenia można skonfigurować na stronie **Typy gwarancji/ubezpieczenia** (**Kredyt i windykacje \> Konfiguracja \> Ustawienia zarządzania kredytem \> Gwarancje i ubezpieczenia \> Typy gwarancji i ubezpieczenień**).

1. Umożliwia wprowadzenie gwarancji lub typu ubezpieczenia, który identyfikuje nazwisko gwaranta lub brokera.
2. Umożliwia wprowadzenie opisu gwaranta/brokera ubezpieczeń.

## <a name="coverage-types"></a>Typy zapotrzebowania

Typów pokrycia można używać do dalszego klasyfikowania polis ubezpieczeniowych. Nie można ich używać z gwarancjami.

Typy zapotrzebowania można dodawać na stronie **Typy pokrycia** (**Kredyt i windykacje \> Konfiguracja \> Ustawienia zarządzania kredytem \> Gwarancje i ubezpieczenia \> Typy pokrycia**).

1. Umożliwia wprowadzenie typu zapotrzebowania w celu zidentyfikowania typu zapotrzebowania, który ma zostać dodany jako ubezpieczenie lub gwarancja.
2. Wprowadź krótki opis typu pokrycia.

## <a name="automatic-credit-limits"></a>Automatyczne limity kredytu

Istnieje możliwość tworzenia kryteriów automatycznych limitów kredytu na stronie **Automatyczne ograniczenia limitu** (**Kredyt i windykacje \> Konfiguracja \> Ustawienia zarządzania kredytem \> Ryzyko \> Automatyczne ograniczenia limitu**).

1. Umożliwia wybranie grupy ryzyka, do której ma być przypisany automatyczny limit kredytu.
2. Umożliwia wybór waluty dla automatycznego limitu kredytu. Istnieje możliwość utworzenia wielu automatycznych limitów kredytu w różnych walutach dla tej samej grupy ryzyka.
3. Umożliwia wprowadzenie kwoty przychodu odpowiadającej maksymalnej kwocie przychodu firmy, która może być użyta do automatycznego limitu kredytu. Po utworzeniu limitów kredytu kwota przychodu jest porównywana z wartością przychodu znajdującą się na stronie **Finanse** (**Rozrachunki z odbiorcami \> Wszyscy odbiorcy \> Wybierz odbiorcę \> Ogólne \> Statystyki \> Finanse**). System używa najnowszej wartości w sekcji **Omówienie**.

Aby dodać wiersze reprezentujące limit kredytu, który zostanie wygenerowany na podstawie wybranych kryteriów, należy wykonać poniższe kroki.

1. Umożliwia wybór grupy punktacji, która określa informacje o odbiorcy, które powinny być używane do obliczania limitu kredytu.
2. Umożliwia wybranie operatora porównania definiującego sposób oceniania informacji o grupie punktacji.
3. Umożliwia wprowadzenie wartości, która powinna być porównywana z wartością określoną dla grupy punktacji.
4. Umożliwia wprowadzenie limitu kredytowego, który powinien zostać przypisany, jeśli informacje o odbiorcy odpowiadają wartości określonej dla grupy punktacji. Można na przykład utworzyć automatyczny limit kredytu dla **Niskiej** grupy punktacji. Jeśli lata w firmie są jedną z grup punktacji, można zdefiniować jeden wiersz, który przypisuje klientowi limit kredytu 100 000, jeśli odbiorca jest w ciągu pięciu lat, a drugi wiersz przypisuje limit kredytu 200 000, jeśli klient był w trakcie prowadzenia działalności przez okres 10 lat.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]