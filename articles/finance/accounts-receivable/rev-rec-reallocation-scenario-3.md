---
title: Zmiana alokacji rozpoznawania przychodów — scenariusz 3
description: W tym temacie zostanie omówiony scenariusz zmiany alokacji, w ramach którego do istniejącego, zafakturowanego zamówienia sprzedaży zostanie dodany nowy wiersz. Po dodaniu do umowy nową pozycję można dodać do nowego lub istniejącego zamówienia sprzedaży.
author: kweekley
ms.date: 12/21/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 4242be761ed170155b70211d99eb5018fb254071
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6356180"
---
# <a name="revenue-recognition-reallocation--scenario-3"></a>Zmiana alokacji rozpoznawania przychodów — scenariusz 3

[!include [banner](../includes/banner.md)]

W tym temacie zostanie omówiony scenariusz zmiany alokacji, w ramach którego do istniejącego, zafakturowanego zamówienia sprzedaży zostanie dodany nowy wiersz. Po dodaniu do umowy nową pozycję można dodać do nowego lub istniejącego zamówienia sprzedaży. Ten scenariusz pokazuje także, co dzieje się, gdy Rozrachunki z odbiorcami są aktualizowane ze względu na zmianę alokacji.

W tym scenariuszu dla opcji **Księgowanie korekt faktury do rozrachunków z odbiorcami** jest wybrana wartość **Tak** na karcie **Rozpoznawanie przychodów** na stronie **Parametry księgi głównej** (**Rozpoznawanie przychodów \> Konfiguracja \> Parametry księgi głównej**).

[![Dla opcji Księgowanie korekt faktury do rozrachunków z odbiorcami jest wybrana wartość Tak.](./media/25_rev-rec-scenarios.png)](./media/25_rev-rec-scenarios.png)

Utworzono zamówienie sprzedaży dla odbiorcy US\_SI\_0003. Odbiorca nabywa laptopa (kod towaru S0012) oraz plan pomocy technicznej (kod towaru S0008, „Długotrwała usługa inżynieryjna”) dla laptopa. Przychód z laptopa zostaje natychmiast rozpoznany. Przychód z planu pomocy technicznej zostanie odroczony i rozpoznany w ciągu 12 miesięcy, zgodnie z zakresem dat określonym w umowie.

[![Wiersze zamówień sprzedaży laptopa oraz planu pomocy technicznej.](./media/26_rev-rec-scenarios.png)](./media/26_rev-rec-scenarios.png)

Zamówienie sprzedaży zostaje potwierdzone. Jako że oba towary są skonfigurowane pod kątem alokacji ceny przychodu, cena przychodu jest obliczana po potwierdzeniu zamówienia sprzedaży. Przychód, który zostanie rozpoznany, można sprawdzić na stronie **Alokacja ceny przychodu** (na stronie **Zamówienia sprzedaży**, w okienku akcji, na karcie **Zarządzanie**, w grupie **Rozpoznawanie przychodów** wybierz pozycję **Alokacja ceny przychodu**). Przychód z laptopa w kwocie 1008,01$ zostanie zaksięgowany na koncie przychodów. Przychód z planu pomocy technicznej zostanie zaksięgowany na koncie Przychód odroczony w kwocie 190,99$. Suma cen przychodu musi być równa sumie wierszy skonfigurowanych w celu zarejestrowania alokacji ceny przychodu (1199,00$).

[![Strona alokacji ceny przychodu.](./media/27_rev-rec-scenarios.png)](./media/27_rev-rec-scenarios.png)

Zamówienie sprzedaży jest w pełni zafakturowane. Na poniższej ilustracji przedstawiono wpis księgowania księgowany dla faktury.

[![Wpis księgowania dla w pełni zafakturowanego zamówienia sprzedaży.](./media/28_rev-rec-scenarios.png)](./media/28_rev-rec-scenarios.png)

Tworzony jest również harmonogram rozpoznawania przychodów. Po pewnym czasie dostępne są dwa miesiące rozpoznanego przychodu dla planu pomocy technicznej.

[![Strona harmonogramu rozpoznawania przychodów po upływie dwóch miesięcy.](./media/29_rev-rec-scenarios.png)](./media/29_rev-rec-scenarios.png)

W tym momencie odbiorca decyduje się dodać usługi instalacyjne (kod towaru S0001). Ta pozycja zostaje dodana do istniejącego zamówienia sprzedaży. Odbiorca otrzymuje monit z prośbą o potwierdzenie zamiaru zmodyfikowania w pełni zafakturowanego zamówienia sprzedaży i wybiera opcję **Tak**.

[![Zamówienie sprzedaży po dodaniu wiersza usług instalacyjnych.](./media/30_rev-rec-scenarios.png)](./media/30_rev-rec-scenarios.png)

Jeśli wspomniana nowa pozycja stanowi jedyną zmianę wprowadzaną do umowy odbiorcy, można teraz uruchomić proces zmiany alokacji. W zamówieniu sprzedaży wybierz opcję **Zmień alokację ceny za pomocą nowych wierszy zamówienia**, aby otworzyć stronę **Zmień alokację ceny za pomocą nowych wierszy zamówienia**. Wybierz wszystkie wiersze zamówienia sprzedaży dla tego zamówienia sprzedaży, a następnie wybierz opcję **Aktualizuj zmianę alokacji**. W kolumnie **Kwota po zmianie alokacji** znajduje się nowa cena przychodu dla każdego wiersza zamówienia sprzedaży.

[![Nowe ceny przychodu na stronie Zmień alokację ceny za pomocą nowych wierszy zamówienia.](./media/31_rev-rec-scenarios.png)](./media/31_rev-rec-scenarios.png)

Następnie wybierz **Oczekiwany załącznik**, aby wyświetlić wpisy księgowania. Jako że dla opcji **Księgowanie korekt faktury do rozrachunków z odbiorcami** jest ustawiona wartość **Tak** na stronie **Parametry księgi głównej**, te wpisy księgowania zostaną zaksięgowane w księdze głównej za pośrednictwem dokumentu kredytowego, a nowa faktura zostanie utworzona w obszarze Rozrachunki z odbiorcami.

[![Wpisy księgowania na stronie Oczekiwany załącznik.](./media/32_rev-rec-scenarios.png)](./media/32_rev-rec-scenarios.png)

Na stronie **Oczekiwany załącznik** ostatnie cztery wiersze wycofują oryginalny wpis księgowania z zaksięgowanej faktury. Pierwszych pięć wierszy to nowe wpisy księgowania księgowane dla faktury. Należy pamiętać, że nowa faktura nie jest przedstawiana odbiorcy. Po zmianie alokacji odbiorca nadal jest winny 1276,94$ — jest to kwota, jaka musi zostać zaksięgowana w obszarze Rozrachunki z odbiorcami w nowym wpisie księgowania. Podatkowa transakcja przeciwstawna oraz przychód lub odroczony przychód dają kwotę 995,83$ + 188,69$ + 77,94$ = 1262,46$. Kwota przychodu lub odroczonego przychodu uległa zmianie z powodu zmiany alokacji. Różnica -14,48$ jest księgowana na koncie Częściowe rozliczenie przychodu faktury. To saldo zostanie rozliczone po zaksięgowaniu faktury pod kątem nowej pozycji dodanej do zamówienia sprzedaży.

Aby zakończyć proces zmiany alokacji, wybierz opcję **Przetwarzanie**. Zostaje wprowadzona data księgowania. Po zakończeniu zmiany alokacji na stronie **Alokacja ceny przychodu** zostaje wyświetlona zmiana alokacji ceny dla wszystkich trzech pozycji.

[![Zmiana alokacji ceny dla wszystkich trzech pozycji na stronie Alokacja ceny przychodu.](./media/33_rev-rec-scenarios.png)](./media/33_rev-rec-scenarios.png)

Harmonogram rozpoznawania przychodów także został zaktualizowany na podstawie nowej ceny zmiany alokacji przychodu. Z poziomu zamówienia sprzedaży otwórz stronę **Harmonogram rozpoznawania przychodów**. Poprzednio dla towaru S0008 istniało 13 wierszy (do tego towaru przypisano harmonogram na 12 miesięcy). Teraz jest ich 39, w tym: 13 wierszy oryginalnego harmonogramu, 13 wierszy harmonogramu cofnięcia i 13 wierszy opartych na nowej cenie przychodu.

[![Strona zaktualizowanego harmonogramu rozpoznawania przychodów z 39 wierszami dla pozycji S0008.](./media/34_rev-rec-scenarios.png)](./media/34_rev-rec-scenarios.png)

Jeśli zostanie wybrana opcja **Załącznik**, w arkuszu faktur jest wyświetlany oryginalny wpis księgowania. Aby wyświetlić wpis wycofania oraz nowy wpis księgowania z zamówienia sprzedaży, wybierz opcję **Korekty przychodu** w okienku zadań, a następnie wybierz opcję **Załącznik**.

Następnie otwórz stronę **Wszyscy odbiorcy** (**Rozrachunki z odbiorcami \> Odbiorcy \> Wszyscy odbiorcy**), wybierz odbiorcę **US\_SI\_0003**, a następnie wybierz opcję **Transakcje**. Na stronie **Transakcje odbiorcy** jest widoczna oryginalna faktura (000006), dokument wycofania (000006-1) oraz nowa faktura (000006-2). Oryginalna faktura i dokument wycofania zostają rozliczone względem siebie i dają saldo 0 (zero). Wyświetl załącznik dla każdego dokumentu, aby zobaczyć wpływ na księgę główną.

[![Oryginalna faktura, dokument wycofania i nowa faktura na stronie Transakcje odbiorcy.](./media/35_rev-rec-scenarios.png)](./media/35_rev-rec-scenarios.png)

Zamówienie sprzedaży zostanie ponownie zafakturowane pod kątem dodanej pozycji. Łączna kwota faktury przedstawionej odbiorcy to 300,00$ + podatek w kwocie 19,50$ = 319,50$. Na poniższej ilustracji przedstawiono księgowany wpis księgowania.

[![Strona transakcji na załączniku z księgowanym wpisem księgowania.](./media/36_rev-rec-scenarios.png)](./media/36_rev-rec-scenarios.png)

Jako że suma przychodu i sprzedaży jest większa niż 319,50$, różnica jest księgowana dla kwoty 14,48$. Kwota ta powoduje rozliczenie salda z konta Częściowe rozliczenie przychodu faktury. To saldo zostało zaktualizowane w nowym wpisie księgowania, który został zaksięgowany po zmianie alokacji.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]