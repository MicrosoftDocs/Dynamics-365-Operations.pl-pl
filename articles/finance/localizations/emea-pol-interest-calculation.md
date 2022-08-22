---
title: Odsetki podatkowe i rynkowe w Polsce
description: W tym artykule omówiono proces konfigurowania i obliczania odsetek od podatku dla Polski.
author: AdamTrukawka
ms.date: 05/18/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Poland
ms.author: atrukawk
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 0df9a48df3556f32c4024b18521bc6ddcd858944
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272110"
---
# <a name="tax-interest-and-free-hand-interest-for-poland"></a>Odsetki podatkowe i rynkowe w Polsce

[!include[banner](../includes/banner.md)]

W Polsce używane są dwa rodzaje stawek odsetek:

- **Stawki odsetek podatkowych** są określane przez Ministerstwo Finansów. Te stopy procentowe są także określane jako *ustawowe stopy odsetek*.
- **Rynkowe stawki odsetek** są wynikiem negocjacji między dostawcą a odbiorcą.

> [!NOTE]
> Odsetki rynkowe mogą nie być obliczane, zależnie od umowy między odbiorcą a dostawcą. Należy jednak obliczyć odsetki od podatków.

Zazwyczaj dostawca ustawia okres rozliczenia nie dłuższy niż 30 dni. Jednak mogą występować następujące sytuacje:

- Dostawca i nabywca zgadzają się na okres rozliczenia, który jest dłuższy niż 30 dni lub okres rozliczenia nie został ustawiony. W takim przypadku odsetki rynkowe mogą być obliczane od trzydziestego pierwszego dnia do daty wymagalności. Ewentualnie odsetki od podatków można obliczyć, aż do daty płatności.
- Okres rozliczeniowy jest krótszy niż 30 dni. W takim przypadku dostawca może obliczyć odsetki podatkowe od dnia wymagalności aż do dnia zapłaty.

## <a name="setup"></a>Konfiguracja

Zanim będzie można obliczać odsetki od podatków i odsetki rynkowe, należy wykonać następujące zadania konfiguracyjne.

### <a name="set-up-the-accounts-receivable-parameters-to-calculate-interest"></a>Konfigurowanie parametrów rozrachunków z odbiorcami do obliczania odsetek

Użyj tej procedury do zdefiniowania parametrów dla obliczania odsetek w module rozrachunków z odbiorcami. 

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami** &gt; **Ustawienia** &gt; **Parametry modułu rozrachunków z odbiorcami**.
2. Na stronie **Parametry modułu rozrachunków z odbiorcami** na stronie **Windykacja** na skróconej karcie **Odsetki i opłaty** w polu **Obliczanie odsetek** wybierz transakcje, dla których powinny zostać obliczone odsetki.

### <a name="set-up-interest-codes"></a>Skonfiguruj kody odsetek

Procedura ta służy do ustawiania i obsługi kodów odsetek. Kody odsetek zawierają ustawienia określające, kiedy odsetki są nakładane i jak są obliczane na kontach zaległych.

1. Wybierz kolejno opcje **Kredyty i windykacja** &gt; **Odsetki** &gt; **Skonfiguruj kody odsetek**.
2. Na stronie **Odsetki** w polu **Kod odsetek** wprowadź unikatowy kod, który ma być używany do obliczania odsetek.
3. Umożliwia wprowadzenie opisu kodu odsetek.
4. W polu **Okres prolongaty** wprowadź liczbę dni, po upływie których zostaną obliczone odsetki.
5. Na skróconej karcie **Zarobki** w polu **Konto księgowania w księdze** wybierz numer konta księgowego dla zysków z odsetek.
6. Na karcie skróconej karcie **Płatności** w polu **Konto księgowania w księdze** wybierz numer konta księgowego dla płatności z tytułu odsetek.

    > [!NOTE]
    > Odsetki są obliczane od daty płatności.

7. Na skróconej karcie **Zarobki** w polu **Podstawa naliczania odsetek** wybierz opcję **Procent** lub **Kwota**. W przypadku wybrania opcji **Procent** wprowadź stawkę odsetek podatkowych w polu **Miesięczne odsetki w %**.
8. Powtórz krok 7 na skróconej karcie **Płatności**.

### <a name="set-up-a-number-sequence-code-for-the-interest-note-and-voucher"></a>Konfigurowanie kodu numeracji dla noty odsetkowej i załącznika

Użyj tej procedury, aby ustawić sekwencję liczbową, która jest używana dla not odsetkowych. Podczas tworzenia noty odsetkowej identyfikator dokumentu zostanie automatycznie przypisany w sekwencji.

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami** &gt; **Ustawienia** &gt; **Parametry modułu rozrachunków z odbiorcami**.
2. Na stronie **Parametry modułu rozrachunków z odbiorcami** na karcie **Sekwencje numerów** zaznacz kod numeracji dla odwołania **Nota odsetkowa**.
3. Wybierz kod numeracji dla odwołania **Załącznik noty odsetkowej**.

### <a name="set-up-customer-posting-profiles"></a>Konfigurowanie profili księgowania odbiorców

Aby uzyskać więcej informacji, zobacz [Profile księgowania odbiorców](../accounts-receivable/customer-posting-profiles.md).

## <a name="calculate-tax-interest-and-free-hand-interest"></a>Obliczanie odsetek od podatku i odsetek rynkowych

W Polsce stawki odsetek od podatku określa Minister Finansów. Dostawca oblicza odsetki, jeśli nastąpi rozliczenie płatności po terminie płatności. Jeśli okres płatności jest krótszy niż 30 dni, dostawca może obliczać odsetki od podatku począwszy od daty należności, aż do daty płatności. Stawki odsetek rynkowych są stosowane, gdy płatności są rozliczane między trzydziestym pierwszym dniem po księgowaniu a datą płatności.

1. Wybierz kolejno opcje **Kredyty i windykacja** &gt; **Odsetki** &gt; **Utwórz noty odsetkowe**.
2. W oknie dialogowym **Obliczanie odsetek** w ustawieniu **Faktura** zaznacz wartość **Tak**, aby obliczać odsetki na fakturach.
3. W ustawieniu **Faktura korygująca** zaznacz opcję **Tak** , aby odliczać faktury korygujące odbiorcy przed obliczeniem odsetek.
4. W ustawieniu **Płatność** zaznacz opcję **Tak**, aby przed obliczeniem odsetek odliczyć płatności od odbiorcy.
5. W ustawieniu **Odsetki** zaznacz opcję **Tak**, aby obliczać odsetki składane od poprzednich not odsetkowych.
6. W polu **Od dnia** wybierz datę początkową obliczania odsetek. Obliczanie uwzględnia transakcje, których termin mija w tym dniu lub później.
7. W polu **Do dnia** wybierz datę końcową obliczania odsetek.
8. W polu **Zaokrąglenie** określ jednostki zaokrąglania kwoty odsetek.
9. W polu **Użyj profilu księgowania z** wybierz profil księgowania, który ma być używany:

    - **Konto** — używanie profilu księgowania z odpowiedniego konta odbiorcy dla każdej noty odsetkowej.
    - **Wybierz** — Używanie profilu księgowania określonego w polu **Profil księgowania**.
    
10. Jeśli w polu **Użyj profilu księgowania z** wybrano opcję **Wybierz**, to w polu **Profil księgowania** należy wybrać profil księgowania dla obliczenia.
11. W ustawieniu **Odsetki od podatków** zaznacz opcję **Tak**, aby obliczać odsetki rynkowe oraz odsetki od podatków.
12. Na skróconej karcie **Rekordy do uwzględnienia** wybierz opcję **Filtr**, aby znaleźć i wybrać rekordy dla obliczania odsetek.
13. Kliknij przycisk **OK**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
