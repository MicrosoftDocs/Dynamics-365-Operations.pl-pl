---
title: Skonfiguruj opłaty za płatności z urzędu podatku potrącanego u źródła
description: W tym temacie opisano sposób skonfigurowania opłat pobieranych z podatku potrącanego z płatności urzędu źródłowego (TDS).
author: kailiang
ms.date: 02/12/2021
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
ms.openlocfilehash: b52331bb1c7a1bc2c764008112f3df9cc0385995
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023523"
---
# <a name="set-up-payment-fees-for-tds-authority-payments"></a>Skonfiguruj opłaty za płatności z urzędu podatku potrącanego u źródła

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób skonfigurowania opłat pobieranych z podatku potrącanego z płatności urzędu źródłowego (TDS).

1. Wybierz kolejno opcje **Rozrachunki z dostawcami \> Ustawienia płatności \> Opłata**.

    [![Strona Opłata](./media/apac-ind-TDS-28.png)](./media/apac-ind-TDS-28.png)

2. Wybierz **Nowy**, aby utworzyć opłatę za płatność i wprowadź wymagane szczegóły.
3. W polu **Typ opłaty** wybierz typ opłaty.

    - **None**
    - **Odsetki** — odsetki obciążają opóźnione płatności dokonywane na rzecz dostawcy urzędu TDS.
    - **Inne** — Inne opłaty są naliczane za zwłokę w płatnościach na rzecz dostawcy urzędu podatku potrącanego u źródła.

    W przypadku wybrania opcji **Odsetki** lub **Inne** pole **Opłata** jest automatycznie ustawiane na **Księga**.

4. Jeśli wybrano opcję **Odsetki** lub **Inne** w polu **Typ pola** , w polu **Konto główne** wybierz konto księgowe, na które mają być księgowane odsetki lub inne opłaty.
5. Wprowadź wymagane dane.
6. W okienku akcji wybierz **ustawienia opłat płatności**, aby otworzyć stronę **Ustawienia opłat od płatności**, na której można skonfigurować opłaty dla różnych kombinacji banków, metod płatności, specyfikacji płatności, walut i interwałów dat.

    [![Strona konfiguracji opłaty za płatność](./media/apac-ind-TDS-21.png)](./media/apac-ind-TDS-21.png)

7. Na karcie **Przegląd** w polu **Grupowanie** określ, dla których banków ma być ustawiana opłata za:

    - **Tabela** — opłata obowiązuje w przypadku określonego konta bankowego.
    - **Grupa** — Opłata obowiązuje dla określonej grupy banków.
    - **Wszystkie** — opłata obowiązuje w przypadku wszystkich kont bankowych.

8. Jeśli wybrano opcję **Tabela** lub **Grupa** w polu **Grupowanie**, w polu **Relacja bankowa** wybierz określone konto bankowe lub grupę bankową, dla których chcesz skonfigurować opłatę za płatność.
9. W polu **Metoda płatności** wybierz sposób uiszczenia opłat.
10. W polu **Specyfikacja płatności** wybierz lub wprowadź kod specyfikacji płatności wygenerowany na stronie **Specyfikacja płatności**.
    - Specyfikacja płatności jest używana do płatności za pomocą przelewów elektronicznych.
12. W polu **Waluta płatności** wybierz walutę, która aktywuje opłatę. Tylko transakcje, w których jest aktywna wybrana waluta, mogą uaktywnić opłatę. Jeśli to pole jest puste, opłaty są aktywowane przez wszystkie waluty.
13. W polu **Procent/Kwota** wybierz metodę obliczania. Dostępne opcje to **Kwota**, **Procent** i **Interwał**.
14. W polu **Kwota opłaty** określ kwotę opłaty jako procent płatności lub kwotę jednej płatności.
15. W polu **Waluta opłaty** określ kod waluty opłaty.
16. Wybierz kartę **Ogólne**, aby wyświetlić lub zmodyfikować szczegóły wybranego konta bankowego.

    [![Karta Ogólne](./media/apac-ind-TDS-22.png)](./media/apac-ind-TDS-22.png)

16. W polu **Minimum** wprowadź minimalną kwotę transakcji, która aktywuje opłatę.
17. W polu **Maksimum** wprowadź maksymalną kwotę transakcji, która aktywuje opłatę.
18. W polach **Od dnia** i **Do dnia** zdefiniuj zakres dat naliczania opłat.
19. W polu **Opłata minimalna** określ kwotę opłaty jako procent płatności lub kwotę jednej płatności.
20. W polu **Grupa podatków** wybierz grupę podatków, która ma być obliczana dla kwoty opłaty.
21. W polu **Grupa podatku od sprzedaży towaru** wybierz grupę podatków dla towaru, która ma być użyta do obliczenia podatku od sprzedaży towaru dla kwoty opłaty.
22. Wybierz kartę **Interwał**. 

    [![Karta Interwał](./media/apac-ind-TDS-23.png)](./media/apac-ind-TDS-23.png)

23. W polu **Dni** należy wpisać liczbę dni pomiędzy datą księgowania (datą dyskonta) przekazu a datą płatności skryptu dłużnego.
24. W polu **Procent/Kwota** określ, czy specyfikacja jest wartością procentową czy kwotą zestawu.
25. W polu **Kwota opłaty** określ kwotę opłaty jako procent płatności lub kwotę jednej płatności.
26. Zamknij stronę **Ustawienia opłaty** od płatności.
27. Zamknij stronę **Ustawienia opłaty** od płatności.
