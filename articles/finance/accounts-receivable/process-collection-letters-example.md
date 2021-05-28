---
title: Przykład Przetwarzania ponagleń
description: W tym temacie pokazano przykład, który pokazuje proces tworzenia, drukowania i księgowania ponagleń.
author: JodiChristiansen
ms.date: 02/03/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, CustCollectionLetterNote
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: fb2651644efd2cadfccb91e48c34dfddc8383e1f
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021423"
---
# <a name="process-collection-letters-example"></a>Przykład Przetwarzania ponagleń

[!include [banner](../../includes/banner.md)]

W tym temacie pokazano przykład, który pokazuje proces tworzenia, drukowania i księgowania ponagleń. Przykład bazuje na opcji **Ignoruj płatności i noty kredytowe podczas obliczania opcji kodu ponaglenia** w kredytach i windykacjach. Używa danych w firmie demonstracyjnej USMF i nowym odbiorcy, US-045.

Aby rozpocząć, przejdź do **Rozrachunki z odbiorcami \> Odbiorcy \> Wszyscy odbiorcy**, wybierz opcję **Nowy**, a następnie wprowadź wymagane informacje, aby utworzyć odbiorcę US-045.

Po zakończeniu wykonaj poniższe czynności.

1. Przejdź do strony **Kredyt i windykacja \> Ponaglenie \> Ustaw kolejność ponagleń** i skonfiguruj kolejność ponagleń, jak pokazano w poniższej tabeli, która jest przypisana do profilu księgowania klienta.

|     Kod ponaglenia      |     opis                           |     Waluta      |     Konto główne        |     Opłata   w walucie     |     Minimalna    nadwyżka        |     Blokuj    dni      |
|---------------------------------  |---------------------------------------    |-----------------  |-----------------------    |-------------------------- |-----------------------    |---------------------  |
|     Ponaglenie   1         |     Drugie    powiadomienie z opłatą        |     USD           |                           |     0,00                  |     0,00                  |     2                 |
|     Ponaglenie   2         |     Drugie    powiadomienie z opłatą        |     Usc           |     403150                |     20.00                 |     10,00                 |     3                 |
|     Ponaglenie                    |     Ostatnie    powiadomienie z opłatą         |     USD           |     403150                |     50.00                 |     100.00                |     15                |

Na poniższej ilustracji przedstawiono informacje zawarte w tabeli w sposób, w jakby był to widoczny na stronie **Ponaglenia**. 

[![Konfigurowanie kolejności ponagleń](./media/Ignore-payments-creditmemos-1.PNG)](./media/Ignore-payments-creditmemos-1.PNG)

 Teraz trzeba ustawić dwa parametry, które są wymagane w tym przykładzie.

2. Przejdź do **Kredyty i windykacja \> Ustawienia \> Parametry modułu rozrachunków z odbiorcami** i wykonaj następujące kroki:

    1. Na karcie **Windykacje** ustaw **Ignoruj płatności i noty kredytowe podczas obliczania opcji kodu ponaglenia w kredytach i windykacjach** na **Tak**.
    2. Upewnij się, że w polu **Utwórz ponaglenie dla każdego** jest ustawiona wartość **Odbiorca**.

    [![Ustawianie parametrów rozrachunków z odbiorcami dla windykacji](./media/Ignore-payments-creditmemos-2.PNG)](./media/Ignore-payments-creditmemos-2.PNG)

3. Przejdź do **Rozrachunków z odbiorcami \> Faktury \> Wszystkie faktury bezpłatne**, wybierz opcję **Nowy**, a następnie wykonaj następujące czynności:

    1. W polu **Konto odbiorcy** zaznacz wartość **US-045**.
    2. W polu **Data faktury** wprowadź datę faktury **1/15/2021**.
    3. W polu **Data ukończenia** wprowadź datę faktury **1/16/2021**.
    4. Na skróconej karcie **Wiersze faktury** w polu **Konto główne** wprowadź wartość **401100**.
    5. W polu **Cena jednostkowa** wpisz **500.00**.
    6. Wybierz opcję **Zaksięguj**.

    Teraz musisz wprowadzić dwie faktury koryguje dla odbiorcy.

4. Wybierz opcję **Nowe**, a następnie wykonaj następujące kroki:

    1. W polu **Konto odbiorcy** zaznacz wartość **US-045**.
    2. W polu **Data faktury** wprowadź datę faktury **1/15/2021**.
    3. W polu **Data ukończenia** wprowadź datę faktury **1/16/2021**.
    4. Na skróconej karcie **Wiersze faktury** w polu **Konto główne** wprowadź wartość **401100**.
    5. W polu **Cena jednostkowa** wpisz **-100.00**.
    6. Wybierz opcję **Zaksięguj**.

5. Powtórz krok 4, ale wprowadź wartość **-200,00** w polu **Cena jednostkowa**.
6. Przejdź do **Rozrachunki z odbiorcami \> Odbiorcy \> Wszyscy odbiorcy** i wybierz odbiorcę **US-045**. Następnie w okienku akcji wybierz opcję **Transakcje \> Transakcje**, aby przejrzeć wcześniej zaksięgowane transakcje odbiorcy.

    [![Przeglądanie zaksięgowanych transakcji odbiorcy](./media/Ignore-payments-creditmemos-3.PNG)](./media/Ignore-payments-creditmemos-3.PNG)

    Musisz teraz utworzyć ponaglenia dla klienta US-045.

7. Wybierz kolejno opcje **Okienko nawigacji \> Ponaglenie \> Utwórz ponaglenia** i wykonaj następujące kroki:

    1. Ustaw w opcjach **Faktura** i **Faktura korygująca** wartość **Tak**.

        Domyślnie w polu **Ponaglenie** powinno być ustawiona wartość **Windykacyjny według odbiorcy**.

    2. W polu **Data ponaglenia** wprowadź datę faktury **1/19/2021**.
    3. W **Rekordach, które mają być uwzględnione** na skróconej karcie, wybierz opcję **Filtruj**, a następnie w polu **Konto odbiorcy** dodaj nabywcę **US-045**.
    4. Kliknij przycisk **OK**.
    5. Wybierz **OK**, aby utworzyć ponaglenie.

8. Wybierz kolejno opcje **Okienko nawigacji \> Ponaglenie \> Przeglądnij i przetwórz ponaglenia** i wykonaj następujące kroki:

    1. Należy zauważyć, że kod ponaglenia w nagłówku i wierszach transakcji to **Ponaglenie 1**, ponieważ to ponaglenie jest pierwszym ponagleniu w sekwencji. (Aby wyświetlić wiersze transakcji, konieczne może się okazać wybranie opcji skrócona karta **Transakcje**.)

   [![Sprawdzanie, czy w nagłówku i wierszach występuje ten sam kod ponaglenia](./media/Ignore-payments-creditmemos-4.PNG)](./media/Ignore-payments-creditmemos-4.PNG)

    2. W okienku akcji wybierz pozycję **Księguj**.
    3. W polu **Data księgowania** wprowadź datę faktury **1/19/2021**.

    Musisz teraz utworzyć ponowne ponaglenia dla klienta US-045.

9. Wybierz kolejno opcje **Okienko nawigacji \> Ponaglenie \> Utwórz ponaglenia** i wykonaj następujące kroki:

    1. Ustaw w opcjach **Faktura** i **Faktura korygująca** wartość **Tak**.

        Domyślnie w polu **Ponaglenie** powinno być ustawiona wartość **Windykacyjny według odbiorcy**.

    2. W polu **Data ponaglenia** wprowadź datę faktury **1/23/2021**.
    3. W **Rekordach, które mają być uwzględnione** na skróconej karcie, wybierz opcję **Filtruj**, a następnie w polu **Konto odbiorcy** dodaj nabywcę **US-045**.
    4. Kliknij przycisk **OK**.
    5. Wybierz **OK**, aby utworzyć ponaglenie.

10. Wybierz kolejno opcje **Okienko nawigacji \> Ponaglenie \> Przeglądnij i przetwórz ponaglenia** i wykonaj następujące kroki:

    1. Zwróć uwagę, że kod ponaglenia w nagłówku to **Ponaglenie 1**. Jednak kodem w wierszach transakcji jest **Ponaglenie 2**.

   [![Sprawdza, czy w nagłówku i wierszach pojawiają się różne kody ponagleń](./media/Ignore-payments-creditmemos-5.PNG)](./media/Ignore-payments-creditmemos-5.PNG)

  Kod różni się, ponieważ opcja **Ignoruj płatności i noty kredytowe podczas obliczania opcji kodu ponaglenia w kredytach i windykacjach** jest ustawiona na **Tak**.

  2. Nie księguj tego ponaglenia.

11. Przejdź do opcji **Kredyt i windykacje \> Ustawienia \> Parametry modułu rozrachunków z odbiorcami**, a następnie na karcie **Windykacja** ustaw wartość **Ignoruj płatności i noty kredytowe podczas obliczania kodu ponaglenia** na wartość **Nie**.

    [![Ustawianie opcji Ignorowania płatności i not kredytowych przy obliczaniu kodu ponaglenia na Nie](./media/Ignore-payments-creditmemos-6.PNG)](./media/Ignore-payments-creditmemos-6.PNG)

    Musisz teraz utworzyć ponowne ponaglenia dla klienta US-045.

12. Wybierz kolejno opcje **Okienko nawigacji \> Ponaglenie \> Utwórz ponaglenia** i wykonaj następujące kroki:

    1. Ustaw w opcjach **Faktura** i **Faktura korygująca** wartość **Tak**.

        Domyślnie w polu **Ponaglenie** powinno być ustawiona wartość **Windykacyjny według odbiorcy**.

    2. W polu **Data ponaglenia** wprowadź datę faktury **1/23/2021**.
    3. W **Rekordach, które mają być uwzględnione** na skróconej karcie, wybierz opcję **Filtruj**, a następnie w polu **Konto odbiorcy** dodaj nabywcę **US-045**.
    4. Kliknij przycisk **OK**.
    5. Wybierz **OK**, aby utworzyć ponaglenie.

13. Przejdź do **Kredyt i windykacje \> Ponaglenie \> Przeglądnij i przetwórz ponaglenia** i należy zauważyć, że kod ponaglenia w nagłówku i wierszach transakcji to **Ponaglenie 2**.

    [![Ponowne pokazanie, czy w nagłówku i wierszach występuje ten sam kod ponaglenia](./media/Ignore-payments-creditmemos-7.PNG)](./media/Ignore-payments-creditmemos-7.PNG)

    Ten sam kod pojawia się w obu miejscach, ponieważ opcja **Ignoruj płatności i noty kredytowe podczas obliczania opcji kodu ponaglenia w kredytach i windykacjach** jest teraz ustawiona na **Nie**.
