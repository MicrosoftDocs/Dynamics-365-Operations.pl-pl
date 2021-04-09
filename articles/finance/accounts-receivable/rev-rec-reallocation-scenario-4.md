---
title: Zmiana alokacji rozpoznawania przychodów — scenariusz 4
description: W tym temacie zostanie omówiony scenariusz zmiany alokacji, w ramach którego z istniejącego, częściowo zafakturowanego zamówienia sprzedaży zostaje usunięty wiersz. Wynik tego scenariusza jest taki sam niezależnie od tego, czy wiersz został usunięty z zamówienia sprzedaży, czy też zmieniono jego stan na Anulowano.
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
ms.openlocfilehash: 2b53145ac1ef4b277afadb4262fd1e704a2e7662
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5830671"
---
# <a name="revenue-recognition-reallocation--scenario-4"></a>Zmiana alokacji rozpoznawania przychodów — scenariusz 4

[!include [banner](../includes/banner.md)]

W tym temacie zostanie omówiony scenariusz zmiany alokacji, w ramach którego z istniejącego, częściowo zafakturowanego zamówienia sprzedaży zostaje usunięty wiersz. Wynik tego scenariusza jest taki sam niezależnie od tego, czy wiersz został usunięty z zamówienia sprzedaży, czy też zmieniono jego stan na Anulowano.

W tym scenariuszu dla opcji **Księgowanie korekt faktury do rozrachunków z odbiorcami** jest wybrana wartość **Nie** na karcie **Rozpoznawanie przychodów** na stronie **Parametry księgi głównej** (**Rozpoznawanie przychodów \> Konfiguracja \> Parametry księgi głównej**).

[![Dla opcji Księgowanie korekt faktury do rozrachunków z odbiorcami jest wybrana wartość Nie](./media/37_rev-rec-scenarios.png)](./media/37_rev-rec-scenarios.png)

Utworzono zamówienie sprzedaży dla odbiorcy US\_SI\_0003. Odbiorca nabywa laptopa (kod towaru S0012) oraz usługi instalacyjne (kod towaru S0001) i plan pomocy technicznej (kod towaru S0008, „Długotrwała usługa inżynieryjna”) dla laptopa. Przychód z laptopa i usług instalacyjnych zostaje natychmiast rozpoznany. Przychód z planu pomocy technicznej zostanie odroczony i rozpoznany w ciągu 12 miesięcy, zgodnie z zakresem dat określonym w umowie.

[![Wiersze zamówienia sprzedaży laptopa, usług instalacyjnych i planu pomocy technicznej](./media/38_rev-rec-scenarios.png)](./media/38_rev-rec-scenarios.png)

Zamówienie sprzedaży zostaje potwierdzone. Jako że wszystkie trzy towary są skonfigurowane pod kątem alokacji ceny przychodu, cena przychodu jest obliczana po potwierdzeniu zamówienia sprzedaży. Przychód, który zostanie rozpoznany, można sprawdzić na stronie **Alokacja ceny przychodu** (na stronie **Zamówienia sprzedaży**, w okienku akcji, na karcie **Zarządzanie**, w grupie **Rozpoznawanie przychodów** wybierz pozycję **Alokacja ceny przychodu**). Przychód z laptopa w kwocie 995,84$ zostanie zaksięgowany na koncie przychodów. Przychód z usług instalacyjnych także zostanie zaksięgowany na koncie Przychód w kwocie 314,47$. Przychód z planu pomocy technicznej zostanie zaksięgowany na koncie Przychód odroczony w kwocie 188,69$. Suma cen przychodu musi być równa sumie wierszy skonfigurowanych w celu zarejestrowania alokacji ceny przychodu (1499,00$).

[![Strona alokacji ceny przychodu](./media/39_rev-rec-scenarios.png)](./media/39_rev-rec-scenarios.png)

Faktura dla odbiorcy uwzględnia laptopa i plan pomocy technicznej, ale nie usługi instalacyjne. Na poniższej ilustracji przedstawiono wpis księgowania księgowany dla faktury.

[![Wpis księgowania dla zafakturowanego zamówienia sprzedaży](./media/40_rev-rec-scenarios.png)](./media/40_rev-rec-scenarios.png)

Wpis księgowania powoduje zaksięgowanie kwoty 1276,94$ na koncie Rozrachunki z odbiorcami. Faktura ta jest jednak fakturą częściową, dlatego przychód lub przychód odroczony powiększony o podatek nie jest równy kwocie w obszarze Rozrachunki z odbiorcami. Różnica -14,47$ jest księgowana na koncie Częściowe rozliczenie przychodu faktury.

Tworzony jest również harmonogram rozpoznawania przychodów.

[![Strona harmonogramu rozpoznawania przychodów dla faktury częściowej](./media/41_rev-rec-scenarios.png)](./media/41_rev-rec-scenarios.png)

W późniejszym czasie klient postanawia nie nabywać usług instalacyjnych. W związku z tym ten wiersz jest usuwany z zamówienia sprzedaży. Należy pamiętać, że zamówienia sprzedaży nie można ponownie potwierdzić, ponieważ na zamówieniu sprzedaży pozostają tylko zafakturowane wiersze.

[![Zamówienie sprzedaży po usunięciu wiersza usług instalacyjnych](./media/42_rev-rec-scenarios.png)](./media/42_rev-rec-scenarios.png)

Choć zamówienia sprzedaży nie można potwierdzić, można przeprowadzić dla niego zmianę alokacji. W zamówieniu sprzedaży wybierz opcję **Zmień alokację ceny za pomocą nowych wierszy zamówienia**, aby otworzyć stronę **Zmień alokację ceny za pomocą nowych wierszy zamówienia**. Wybierz dwa pozostałe wiersze zamówienia sprzedaży, a następnie wybierz opcję **Aktualizuj zmianę alokacji**. W kolumnie **Kwota po zmianie alokacji** znajduje się nowa cena przychodu dla każdego pozostałego wiersza zamówienia sprzedaży.

[![Nowe ceny przychodu na stronie Zmień alokację ceny za pomocą nowych wierszy zamówienia](./media/43_rev-rec-scenarios.png)](./media/43_rev-rec-scenarios.png)

Następnie wybierz **Oczekiwany załącznik**, aby wyświetlić wpisy księgowania.

[![Wpisy księgowania na stronie Oczekiwany załącznik](./media/44_rev-rec-scenarios.png)](./media/44_rev-rec-scenarios.png)

Na stronie **Oczekiwany załącznik** ostatnich pięć wierszy wycofuje oryginalny wpis księgowania z zaksięgowanej faktury. Pierwsze cztery wiersze to nowe wpisy księgowania księgowane dla faktury. Należy pamiętać, że nowa faktura nie jest przedstawiana odbiorcy. Po zmianie alokacji odbiorca nadal jest winny 1276,94$ — jest to kwota, jaka musi zostać zaksięgowana w obszarze Rozrachunki z odbiorcami w nowym wpisie księgowania. Nowy przychód lub przychód odroczony powiększony o podatek wynosi 1276,94$. W związku z tym nie jest konieczne księgowanie na koncie Częściowe rozliczenie przychodu faktury.

Aby zakończyć proces zmiany alokacji, wybierz opcję **Przetwarzanie**. Zostaje wprowadzona data księgowania. Po zakończeniu zmiany alokacji na stronie **Alokacja ceny przychodu** zostaje wyświetlona zmiana alokacji ceny dla dwóch pozostałych towarów.

[![Zmiana alokacji ceny dla pozostałych pozycji na stronie Alokacja ceny przychodu](./media/45_rev-rec-scenarios.png)](./media/45_rev-rec-scenarios.png)

Harmonogram rozpoznawania przychodów także został zaktualizowany na podstawie nowej ceny zmiany alokacji przychodu. Z poziomu zamówienia sprzedaży otwórz stronę **Harmonogram rozpoznawania przychodów**. Poprzednio dla towaru S0008 istniało 13 wierszy (do tego towaru przypisano harmonogram na 12 miesięcy). Teraz jest ich 39, w tym: 13 wierszy oryginalnego harmonogramu, 13 wierszy harmonogramu cofnięcia i 13 wierszy opartych na nowej cenie przychodu.

[![Strona zaktualizowanego harmonogramu rozpoznawania przychodów z 39 wierszami dla pozycji S0008](./media/46_rev-rec-scenarios.png)](./media/46_rev-rec-scenarios.png)

Jeśli zostanie wybrana opcja **Załącznik**, w arkuszu faktur jest wyświetlany oryginalny wpis księgowania. Aby wyświetlić wpis wycofania oraz nowy wpis księgowania z zamówienia sprzedaży, wybierz opcję **Korekty przychodu** w okienku akcji, a następnie wybierz opcję **Załącznik**.

Następnie otwórz stronę **Wszyscy odbiorcy** (**Rozrachunki z odbiorcami \> Odbiorcy \> Wszyscy odbiorcy**), wybierz odbiorcę **US\_SI\_0003**, a następnie wybierz opcję **Transakcje**. Na stronie **Transakcje odbiorcy** znajduje się tylko faktura oryginalna (000008) wraz z oryginalnym wpisem księgowania. Jako że dla opcji **Księgowanie korekt faktury do rozrachunków z odbiorcami** wybrano wartość **Nie** na stronie **Parametry księgi głównej**, aktualizowana jest tylko księga główna. W związku z tym wpisy wycofania i zaktualizowane wpisy księgowania nie są wyświetlane. Należy zwrócić uwagę na fakt, że wyświetlane są transakcje korekty przychodu utworzone w [scenariuszu 3](rev-rec-reallocation-scenario-3.md).

[![Oryginalny wpis księgowania na stronie Transakcje odbiorcy](./media/47_rev-rec-scenarios.png)](./media/47_rev-rec-scenarios.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]