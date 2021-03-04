---
title: Zmiana alokacji rozpoznawania przychodów — scenariusz 2
description: W tym temacie zostanie omówiony scenariusz zmiany alokacji, w ramach którego wprowadzone zostaną dwa zamówienia sprzedaży, po czym odbiorca doda pozycję do umowy po zafakturowaniu pierwszego zamówienia sprzedaży. Po dodaniu do umowy nową pozycję można dodać do nowego lub istniejącego zamówienia sprzedaży.
author: kweekley
manager: aolson
ms.date: 12/21/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 30b4c55a82237b5c8b6b41032243da337a5ec969
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5003409"
---
# <a name="revenue-recognition-reallocation--scenario-2"></a>Zmiana alokacji rozpoznawania przychodów — scenariusz 2

[!include [banner](../includes/banner.md)]

W tym temacie zostanie omówiony scenariusz zmiany alokacji, w ramach którego wprowadzone zostaną dwa zamówienia sprzedaży, po czym odbiorca doda pozycję do umowy po zafakturowaniu pierwszego zamówienia sprzedaży. Po dodaniu do umowy nową pozycję można dodać do nowego lub istniejącego zamówienia sprzedaży.

W tym scenariuszu dla opcji **Księgowanie korekt faktury do rozrachunków z odbiorcami** jest wybrana wartość **Nie** na karcie **Rozpoznawanie przychodów** na stronie **Parametry księgi głównej** (**Rozpoznawanie przychodów \> Konfiguracja \> Parametry księgi głównej**).

[![Dla opcji Księgowanie korekt faktury do rozrachunków z odbiorcami jest wybrana wartość Nie](./media/12_rev-rec-scenarios.png)](./media/12_rev-rec-scenarios.png)

Utworzono zamówienie sprzedaży dla odbiorcy US\_SI\_0003. Odbiorca nabywa usługi instalacyjne (kod towaru S0001) i plan pomocy technicznej (kod towaru S0008) dla laptopa, przy czym laptop nie został jeszcze przez niego wybrany. Przychód z usług instalacyjnych zostanie odroczony do daty zakupu laptopa. Przychód z planu pomocy technicznej zostanie odroczony i rozpoznany w ciągu 12 miesięcy, zgodnie z zakresem dat określonym w umowie.

[![Wiersze zamówień sprzedaży usług instalacyjnych i planu pomocy technicznej](./media/13_rev-rec-scenarios.png)](./media/13_rev-rec-scenarios.png)

Zamówienie sprzedaży zostaje potwierdzone. Jako że oba towary są skonfigurowane pod kątem alokacji ceny przychodu, cena przychodu jest obliczana po potwierdzeniu zamówienia sprzedaży. Przychód, który zostanie rozpoznany, można sprawdzić na stronie **Alokacja ceny przychodu** (na stronie **Zamówienia sprzedaży**, w okienku akcji, na karcie **Zarządzanie**, w grupie **Rozpoznawanie przychodów** wybierz pozycję **Alokacja ceny przychodu**). Przychód z usług instalacyjnych zostanie zaksięgowany na koncie Przychód odroczony w kwocie 250,00$. Przychód z planu pomocy technicznej także zostanie zaksięgowany na koncie Przychód odroczony w kwocie 150,00$. Suma cen przychodu musi być równa sumie wierszy skonfigurowanych w celu zarejestrowania alokacji ceny przychodu (400,00$).

[![Strona alokacji ceny przychodu](./media/14_rev-rec-scenarios.png)](./media/14_rev-rec-scenarios.png)

Zamówienie sprzedaży jest w pełni zafakturowane. Na poniższej ilustracji przedstawiono wpis księgowania księgowany dla faktury.

[![Wpis księgowania dla w pełni zafakturowanego zamówienia sprzedaży](./media/15_rev-rec-scenarios.png)](./media/15_rev-rec-scenarios.png)

Ma także miejsce utworzenie harmonogramu rozpoznawania przychodów, ale żaden z przychodów nie zostaje jeszcze rozpoznany.

[![Strona harmonogramu rozpoznawania przychodów](./media/16_rev-rec-scenarios.png)](./media/16_rev-rec-scenarios.png)

Kilka dni później odbiorca wybierze laptopa. Dla odbiorcy zostaje wprowadzone drugie zamówienie sprzedaży.

[![Wiersz zamówienia sprzedaży dla laptopa](./media/17_rev-rec-scenarios.png)](./media/17_rev-rec-scenarios.png)

Drugie zamówienie sprzedaży zostaje potwierdzone. Jako że to zamówienie sprzedaży zawiera tylko jeden wiersz, alokacja ceny przychodu nie jest realizowana podczas potwierdzania zamówienia sprzedaży. Alokacja cen przychodów ma miejsce tylko, jeśli istnieją co najmniej dwa unikatowe towary i jeśli towary te zostały skonfigurowane pod kątem alokacji cen przychodów.

Jeśli wspomniane nowe zamówienie sprzedaży stanowi jedyną zmianę wprowadzaną do umowy odbiorcy, można teraz uruchomić proces zmiany alokacji. W jednym z dwóch zamówień sprzedaży wybierz opcję **Zmień alokację ceny za pomocą nowych wierszy zamówienia**, aby otworzyć stronę **Zmień alokację ceny za pomocą nowych wierszy zamówienia**. Możesz również wybrać kolejno **Rozpoznawanie przychodów \> Zadania okresowe \> Zmień alokację ceny za pomocą nowych wierszy zamówienia**. Wybierz dwa zamówienia sprzedaży i odpowiadające im wiersze zamówienia sprzedaży, a następnie wybierz opcję **Aktualizuj zmianę alokacji**. W kolumnie **Kwota po zmianie alokacji** znajduje się nowa cena przychodu dla każdego wiersza zamówienia sprzedaży.

[![Nowe ceny przychodu na stronie Zmień alokację ceny za pomocą nowych wierszy zamówienia](./media/18_rev-rec-scenarios.png)](./media/18_rev-rec-scenarios.png)

Następnie wybierz opcję **Oczekiwany załącznik**, aby wyświetlić wpisy księgowania, które zostaną zaksięgowane tylko w księdze głównej. Jako że dla opcji **Księgowanie korekt faktury do rozrachunków z odbiorcami** została wybrana wartość **Nie** na stronie **Parametry księgi głównej**, podczas przetwarzania zmiany alokacji nie zostaną wprowadzone żadne zmiany w obszarze Rozrachunki z odbiorcami.

[![Wpisy księgowania na stronie Oczekiwany załącznik](./media/19_rev-rec-scenarios.png)](./media/19_rev-rec-scenarios.png)

Na stronie **Oczekiwany załącznik** ostatnie trzy wiersze wycofują oryginalny wpis księgowania z zaksięgowanej faktury. Pierwsze cztery wiersze składają się na nowy wpis księgowania księgowany dla faktury. Należy pamiętać, że nowa faktura nie jest przedstawiana odbiorcy. Po zmianie alokacji odbiorca nadal jest winny 426,00$ — jest to kwota, jaka musi zostać zaksięgowana w obszarze Rozrachunki z odbiorcami w nowym wpisie księgowania. Podatkowa transakcja przeciwstawna oraz odroczony przychód dają kwotę 188,69$ + 314,48$ + 26,00$ = 529,17$. Kwota odroczonego przychodu uległa zmianie z powodu zmiany alokacji. Różnica 103,17$ jest księgowana na koncie Częściowe rozliczenie przychodu faktury. To saldo zostanie rozliczone po zaksięgowaniu faktury pod kątem drugiego zamówienia sprzedaży ujętego w zmianie alokacji.

Aby zakończyć proces zmiany alokacji, wybierz opcję **Przetwarzanie**. Nawet jeśli nic nie zostanie zaksięgowane, zostanie wyświetlony monit o podanie daty księgowania. Po zakończeniu procesu zmiany alokacji na stronie **Alokacja ceny przychodu** dla każdego zamówienia sprzedaży będzie wyświetlana alokacja ceny dla wszystkich towarów uwzględnionych na obu zamówieniach sprzedaży. Innymi słowy, strona **Alokacja ceny przychodu** dla każdego zamówienia sprzedaży będzie zawierać towar, który nie istnieje na danym zamówieniu sprzedaży, jako że jest on uwzględniony w ramach tej samej umowy, ale na innym zamówieniu sprzedaży.

> [!TIP]
> Aby dostarczyć kontekst, w jakim są wyświetlane dodatkowe towary, można dodać do siatki inne kolumny, takie jak **Identyfikator zmiany alokacji** i **Zamówienie sprzedaży**.
> 
> [![Dodatkowe kolumny na stronie Alokacje ceny przychodu](./media/20_rev-rec-scenarios.png)](./media/20_rev-rec-scenarios.png)

W zamówieniu sprzedaży 00036 harmonogram rozpoznawania przychodów także został zaktualizowany na podstawie nowej ceny zmiany alokacji przychodu. Z poziomu tego zamówienia sprzedaży otwórz stronę **Harmonogram rozpoznawania przychodów**. Poprzednio dla towaru S0008 istniało 13 wierszy (do tego towaru przypisano harmonogram na 12 miesięcy). Teraz jest ich 39, w tym: 13 wierszy oryginalnego harmonogramu, 13 wierszy harmonogramu cofnięcia i 13 wierszy opartych na nowej cenie przychodu.

[![Strona zaktualizowanego harmonogramu rozpoznawania przychodów z 39 wierszami dla pozycji S0008](./media/21_rev-rec-scenarios.png)](./media/21_rev-rec-scenarios.png)

Analogicznie poprzednio istniały dwa wiersze dla towaru S0001, a teraz jest ich sześć.

[![Strona zaktualizowanego harmonogramu rozpoznawania przychodów z sześcioma wierszami dla pozycji S0001](./media/22_rev-rec-scenarios.png)](./media/22_rev-rec-scenarios.png)

Jeśli w zamówieniu sprzedaży 000036 zostanie wybrana opcja **Załącznik**, w arkuszu faktur będzie wyświetlany oryginalny wpis księgowania. Aby wyświetlić wpis wycofania oraz nowy wpis księgowania z zamówienia sprzedaży, wybierz opcję **Korekty przychodu** w okienku akcji, a następnie wybierz opcję **Załącznik**.

[![Zamówienie sprzedaży 000036](./media/23_rev-rec-scenarios.png)](./media/23_rev-rec-scenarios.png)

Następnie otwórz stronę **Wszyscy odbiorcy** (**Rozrachunki z odbiorcami \> Odbiorcy \> Wszyscy odbiorcy**), wybierz odbiorcę **US\_SI\_0003**, a następnie wybierz opcję **Transakcje**. Zostanie wyświetlona otwarta faktura z zamówienia sprzedaży 000036. Jeśli został wybrany załącznik, zostanie wyświetlony oryginalny wpis księgowania, a nie nowy wpis księgowania ze zmiany alokacji. Nie można wyświetlić wpisu wycofania ani nowego wpisu księgowania z poziomu obszaru Rozrachunki z odbiorcami.

Następuje zaksięgowanie drugiego zamówienia sprzedaży. Łączna kwota faktury przedstawionej odbiorcy to 1099,00$ + podatek w kwocie 71,44$ = 1170,44$. Na poniższej ilustracji przedstawiono księgowany wpis księgowania.

[![Strona transakcji na załączniku z księgowanym wpisem księgowania](./media/24_rev-rec-scenarios.png)](./media/24_rev-rec-scenarios.png)

Jako że suma przychodu i sprzedaży jest większa niż 1170,44$, różnica jest księgowana dla kwoty -130,17$. Kwota ta powoduje rozliczenie salda z konta Częściowe rozliczenie przychodu faktury. To saldo jest księgowane w nowym wpisie księgowania po zmianie alokacji.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]