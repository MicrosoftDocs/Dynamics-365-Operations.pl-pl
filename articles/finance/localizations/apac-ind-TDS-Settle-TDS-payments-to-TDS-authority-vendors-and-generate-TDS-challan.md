---
title: Rozlicz płatności TDS na rzecz dostawców z urzędu TDS i wygeneruj dokument urzędowy TDS
description: W tym temacie opisano sposób rozliczania płatności podatków potrącanych w źródle (TDS) na rzecz dostawców urzędów skarbowych.
author: kailiang
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: a9912151ef9fc68941858545e39bccc1e5d3e411
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6358321"
---
# <a name="settle-tds-payments-to-tds-authority-vendors-and-generate-tds-challan"></a>Rozlicz płatności TDS na rzecz dostawców z urzędu TDS i wygeneruj dokument urzędowy TDS

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób rozliczania płatności podatków potrącanych w źródle (TDS) na rzecz dostawców urzędów skarbowych.

1. Przejdź do pozycji **Rozrachunki z dostawcami \> Płatności \> Arkusz płatności dostawcy**.

    [![Strona arkusza płatności dostawcy.](./media/apac-ind-TDS-51.png)](./media/apac-ind-TDS-51.png)

2. Na stronie **Arkusz płatności dostawców** wybierz pozycję **Nowy**, aby utworzyć wiersz arkusza.
3. W polu **Konto** wybierz dostawcę urzędu TDS, dla których chcesz rozliczyć płatności TDS.
4. Wybierz opcję **Transakcje rozliczania**, aby otworzyć stronę **Transakcje rozliczania**, na której możesz przejrzeć rozliczone transakcje TDS dla dostawcy urzędu TDS.

    Rozliczone transakcje TDS dla okresu rozliczeniowego są wyświetlane w następujący sposób:

    - Transakcje TDS, w których charakter kategorii oceny to **Firma**, są pokazywane jako jeden wiersz transakcji.
    - Transakcje TDS, w których charakter kategorii oceny to **HUF**, **Firma**, **Osoba**, **AOP**, **BOI**, **Urząd lokalny** lub **Inne**, są pokazywane jako jeden wiersz transakcji.
    - W polu **Kwota** jest przedstawiana łączna kwota TDS, która ma zostać zapłacona dostawcy urzędu TDS.

5. Wybierz **transakcje potrącenia zaliczki** na podatek, aby wyświetlić różne transakcje TDS uwzględnione w rekordzie rozliczenia. Na tej stronie można wyświetlić podział każdej transakcji TDS uwzględnionej w procesie rozliczania dla okresu rozliczeniowego.
6. Na karcie **Przegląd** zaznacz pole wyboru **Zaznacz**, aby transakcje TDS rozliczały się z dostawcą urzędu TDS.

    Na karcie **Przegląd** są podane następujące informacje dotyczące każdej otwartej transakcji TDS:

    - **Data** — Data transakcji TDS.
    - **Załącznik** – Numer załącznika finansowego.
    - **Źródło** — moduł, w których jest księgowana transakcja TDS.
    - **Dostawca/Odbiorca** — numer konta dostawcy lub odbiorcy, od których jest odejmowany identyfikator TDS.
    - **Nazwa odbiorcy/strony potrącenia** — nazwa dostawcy lub odbiorcy, od których jest odejmowany identyfikator TDS.
    - **Charakter oszacowań** – Charakter kategorii oszacowań, do której należy potrącona kwota.
    - **Kwota** – Kwota faktury, na podstawie której obliczono TDS.
    - **Kwota podatku** — kwota TDS obliczona dla transakcji.

    > [!NOTE]
    > Wyczyść pole wyboru **Zaznacz** dla wszystkich transakcji TDS, które nie powinny być rozliczane z dostawcą urzędu TDS.

    Na karcie **Ogólne** pole **PAN** zawiera trwały numer konta (PAN) potrącanego z konta. Pole **Data** zawiera datę obliczenia TDS, a pole **Wartość** zawiera łączny procent użyty do obliczenia TDS.

7. Wybierz **pozycję Załącznik**, aby wyświetlić wpisy załącznika dla transakcji TDS.
8. Zamknij stronę.
10. Wybierz **składniki potrąconej zaliczki** na podatek, aby otworzyć stronę **Składników potrąconej zaliczki na podatek**, na której możesz przejrzeć identyfikatory TDS obliczone dla określonego kodu podatku TDS.

    Na karcie **Przegląd** pole **Składnik podatku** zawiera składnik podatku TDS użyty w transakcji. W polu **Kwota** jest w walucie podstawowej obliczana kwota TDS obliczona dla składnika podatku TDS. Pole **Kwota skumulowana** zawiera łączną kwotę TDS obliczoną dla składnika podatku TDS dla wszystkich rozliczonych transakcji.

    Na karcie **Kwota** sekcja **Waluta standardowa** zawiera kwotę TDS obliczoną dla składnika podatku TDS, w walucie domyślnej. W sekcji **Waluta dodatkowa** jest wyświetlana kwota w drugiej walucie.

11. Zamknij stronę **Składniki potrąconej zaliczki** na podatek.
12. Na stronie **edycji otwartej transakcji** w polu **Kwota** zauważ, że łączna kwota do rozliczenia dla dostawcy urzędu TDS dla okresu rozliczeniowego jest aktualizowana.
13. Aby rozliczyć transakcje TDS różnych okresów rozliczeniowych TDS dla dostawcy urzędu TDS, zaznacz pole wyboru **Zaznacz** dla transakcji.
14. Zamknij stronę **Edytowanie otwartej transakcji**.

    > [!NOTE]
    > Jeśli na stronie **Transakcje potrąconej zaliczki** na podatek wybrano tylko kilka transakcji do rozliczenia, łączna kwota TDS wybranych transakcji zostanie zaktualizowana w polu **Korekta** na stronie **edycji otwartej transakcji**. Kwota korekty jest aktualizowana w wierszu arkusza na stronie załącznika **arkusza**, a strona edycji **otwartej transakcji** jest zamknięta.

    Na stronie **Załącznik arkusza** pole **Debet** zawiera łączną kwotę do zapłacenia dostawcy urzędu TDS.

15. Wprowadź szczegóły konta przeciwstawne.

    > [!NOTE]
    > Jeśli transakcje TDS mają różne numery kont podatkowych, na stronie **załącznika arkusza** są tworzone wiersze arkusza według kodów PIN.

16. Na karcie **Opłata** od płatności, w polu **Identyfikator opłaty** wybierz identyfikator opłaty o typie opłaty **Odsetki** lub **Inne**, aby na obciążenia opłatę za opóźnione płatności dokonywane przez dostawcę urzędu TDS.

    Na karcie **Informacje podatkowe** w sekcji **Informacje o firmie** w polu **Nazwa** jest wyświetlana nazwa firmy. W sekcji **Potrącona zaliczka** na podatek pole **Numer konta podatkowego** zawiera wartość TAN dołączonej do wiersza transakcji.

17. Sprawdź poprawność arkusza i zaksięguj go.
18. Wybierz **Potrącona zaliczka na podatek \> informacje formularzy informacyjnych**, aby wprowadzić szczegóły challan dla transakcji.

    W polu **Załącznik** jest przedstawiany numer załącznika transakcji.
    
19. Zaznacz pole **wyboru TDS wpłacene przy użyciu wpisu księgi**, jeśli kwota TDS jest deponowana przy użyciu wpisu w księdze.
20. W polu **Numer formularza informacyjnego** wprowadź numer formularza informacyjnego używany do zapłaty dostawcy urzędu TDS.
21. W polu **Data** wprowadź datę formularza informacyjnego.
22. W polu **Nazwa banku** wybierz nazwę banku, na konto których ma zostać wpłać kwota TDS należna dostawcy urzędu TDS. To pole zawiera listę wszystkich kont bankowych ustawionych dla dostawcy urzędu TDS w **Rozrachunki z dostawcami \> Wszyscy dostawcy \> Konfigurowanie \> Konta bankowe**.
23. W polu **Kod BSR** wprowadź kod podstawowego zwrotu statystycznego (BSR) banku.
24. Zamknij stronę.

### <a name="example"></a>Przykład

Okres 2009-04-01 został rozliczony dla grupy składników **Czynasz** TDS za pomocą okresowego procesu rozliczania TDS. Łączna kwota TDS 141 625,00 jest księgowana na koncie urzędu dostawcy TDS dla okresu rozliczeniowego TDS. Możesz wyświetlić tę kwotę w polu **Kwota** na stronie **Edytowanie otwartej transakcji** dla dostawcy urzędu TDS.

Jeśli w celu wyświetlenia różnych transakcji TDS rozliczonych dla okresu są wybrane **transakcje potrącenia zaliczki na podatek**, wyświetlane są poniższe informacje.

| Kwota podatku TDS |
|------------|
| 16,995.00  |
| 22,660.00  |
| 28,325.00  |
| 16,995.00  |
| 28,325.00  |
| 16,995.00  |
| 11,330.00  |

W przypadku określonej kwoty podatku potrącanego u źródła można wybrać **Składniki potrąconej zaliczki**, aby wyświetlić TDS obliczony dla składnika podatku potrącanego u źródła dla określonego kodu podatku potrącanego u źródła. W tym przykładzie można wybrać **składniki potrąconej zaliczki** na podatek dla 16 995,00 TDS. Zostanie pokazana kwota podatku obliczona na składnik transakcji.

| Składnik podatku | Liczba dni    | Kwota narastająco |
|---------------|-----------|--------------------|
| TDS           | 1,5000.00 | 125,000.00         |
| Dopłata     | 1,500.00  | 12,500.00          |
| PE-Cess       | 330.00    | 2,750.00           |
| SHE Cess      | 165.00    | 1,375.00           |

Jeśli zaznaczono tylko kwoty TDS 16 995,00, 22 660,00, i 2 8325,00 do rozliczenia na stronie **Transakcje potrącenia zaliczki na podatek**, łączna kwota do rozliczenia jest pokazywana jako **67 980,00** w polu **Korekta** na stronie **edycji otwartej transakcji**. Jeśli ta transakcja jest oznaczona do rozliczenia i strona **edycji otwartej transakcji** jest zamknięta, kwota **67 980,00** jest wyświetlana w polu **Debet** na stronie **Załącznik arkusza**.

Teraz można zak zaksięgowania arkusza i wygenerować formularz informacyjny TDS.

### <a name="adjustment-of-advance-payments-that-are-made-to-tds-authority-vendors"></a>Korekta płatności zaliczek dla dostawców urzędu TDS

Aby skorygować płatność zaliczkową wystosową do dostawcy urzędu TDS w związku z rzeczywistą płatnością, przejdź do **Rozrachunki z dostawcami \> Dostawcy \> Wszyscy dostawcy \> Edycja transakcji**. Jeśli rzeczywista dokonana płatność przekracza płatność zaliczki, dla transakcji są generowane dwa numery challanów. Jednak w zapytaniach TDS jest wyświetlany tylko pierwszy numer formularza informacyjnego.
