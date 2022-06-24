---
title: Rozliczenia księgi
description: W tym artykule wyjaśniono, jak na stronie Rozliczenia księgi rozliczać transakcji księgi i wycofywać rozliczenia.
author: kweekley
ms.date: 01/31/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerTransSettlement
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-11-30
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: 39fd6c6677565a4b1e9a9bf6f43a4c630cb5e07b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8902495"
---
# <a name="ledger-settlements"></a>Rozliczenia księgi

[!include [banner](../includes/banner.md)]

Rozliczenie księgi głównej to proces dopasowywania transakcji debetowych i kredytowych w księdze głównej. Rozliczenie kwot debetowych i kredytowych służy do uzgodnienia salda konta księgi z wyszczególnionymi transakcjami, które na to saldo się składają.

Rozliczone transakcje mogą być wyłączone z zapytań i raportów. W ten sposób łatwiej jest analizować otwarte transakcje księgi, które składają się na saldo konta księgi.

> [!IMPORTANT] 
> Moduły Accounts payable (AP) i Accounts receivable (AR) również posiadają funkcję rozliczania faktur i płatności. Kiedy następuje rozliczenie w księgach pomocniczych AR i AP, odpowiadające im wpisy w księdze nie są automatycznie rozliczane.

## <a name="ledger-settlement-features"></a>Cechy rozliczenia księgi
W aplikacji Microsoft Dynamics 365 Finance w wersji 10.0.21 opcja **Włącz zaawansowane rozliczanie księgi** została usunięta ze strony **Parametry księgi głównej**. Zaawansowane rozliczanie księgi głównej jest teraz zawsze włączone.
W wersji finansów 10.0.25 wprowadzono funkcję **Świadomość między rozliczeniem księgi a zamknięciem na koniec roku**. Ta funkcja zmienia fundamentalną funkcjonalność zarówno rozliczenia księgi głównej, jak i zamknięcia rocznego księgi głównej. Zanim włączysz tę funkcję w przestrzeni roboczej **Zarządzanie funkcjami**, zobacz: [Świadomość między rozliczeniem księgi a zamknięciem roku](awareness-between-ledger-settlement-year-end-close.md).

## <a name="set-up-ledger-settlement"></a>Tworzenie rozliczenia księgi głównej
Musisz wybrać konta główne, dla których chcesz przeprowadzić rozliczenie księgi. Istnieją dwa sposoby na wybranie tych głównych kont.

1. Wybierz kolejno opcje **Księga główna** > **Ustawienia księgi** > **Parametry księgi głównej**.
2. Na karcie **Rozliczenia księgi** wybierz wykresy kont, z których chcesz wybrać konta główne.
3. Wybierz konta główne, dla których chcesz przeprowadzić rozliczenie księgi. Ponieważ plany kont są globalne, wszystkie firmy, do których przypisane są wybrane plany kont, będą miały te same konta główne wybrane do rozliczenia księgi.

  — lub —

1. Wybierz kolejno opcje **Księga główna** > **Zadania okresowe** > **Rozliczenia księgi**.
2. Wybierz **Konta rozliczeniowe księgi**.
3. W oknie dialogowym wybierz plan kont i konta główne, dla których chcesz przeprowadzić rozliczenie księgi. To okno dialogowe jest skrótem. Wszystkie konta główne, które dodasz tutaj, będą miały swoje odzwierciedlenie także na stronie **Parametry księgi głównej**.

Możesz użyć tych samych podstawowych procedur, aby usunąć konta główne z rozliczenia księgi w dowolnym momencie. Usunięcie konta głównego nie ma wpływu na wcześniejsze rozliczenia księgi. Jednak konto główne i transakcje nie będą już widoczne na stronie **Rozliczenie konta**.

## <a name="settle-transactions"></a><a name="settle-transactions"></a>Rozlicz transakcje
W celu rozliczenia transakcji księgi wykonaj następujące czynności.

1. Wybierz kolejno opcje **Księga główna** > **Zadania okresowe** > **Rozliczenia księgi**.
2. Ustaw filtry w górnej części strony:

    - Wybierz zakres dat. Alternatywnie wybierz kod zakresu dat, aby automatycznie uzupełnić zakres dat. Nie zalecamy wykonywania rozliczenia księgi dla transakcji, które przekraczają rok podatkowy.
    - W razie potrzeby zmień warstwę delegowania. Nie możesz rozliczać transakcji, które znajdują się w różnych warstwach księgowania.
    - Aby pokazać osobno konto główne i wymiary, wybierz zestaw wymiarów finansowych.

3. Wybierz opcję **Wyświetl transakcje**, aby wyświetlić wszystkie transakcje zgodne z ustawionymi filtrami oraz z listą kont określonych podczas konfigurowania listy planu kont w poprzedniej sekcji.

    - Jeśli zmodyfikujesz którykolwiek filtr lub zestaw wymiarów, należy ponownie kliknąć opcję **Wyświetl transakcje**.
    - Aby przefiltrować transakcje do pojedynczego konta głównego, użyj filtru w polu **Konto księgowe**. Nie zalecamy wykonywania rozliczenia księgi głównej dla transakcji, które są księgowane na różnych kontach głównych.

4. Wybierz wiersze do rozliczenia. Wartość w polu **Wybrana kwota** na górze strony zwiększa się lub zmniejsza, aby odzwierciedlić całkowitą kwotę w wybranych liniach.
5. Po zakończeniu wybierania transakcji wybierz opcję **Oznacz wybrane**. Dla każdej wybranej transakcji w kolumnie **Oznaczone** pojawi się znacznik wyboru. Ponadto wartość pola **Oznaczona kwota** nad siatką zwiększy się lub zmniejszy o łączną kwotę w oznaczonych wierszach.
6. Gdy wartość pola **Oznaczona kwota** ma wartość **0** (zero), wybierz opcję **Rozlicz oznaczone transakcje**. Stan oznaczonych transakcji zostanie zaktualizowany na **Rozliczone**.

    > [!IMPORTANT]
    > Wszystkie transakcje, które zaznaczyłeś do rozliczenia dla aktywnej osoby prawnej, zostaną rozliczone, nawet jeśli nie są aktualnie widoczne na stronie rozliczenia księgi, ponieważ zastosowałeś filtr.

## <a name="make-transactions-easier-to-find"></a>Ułatwienie znajdowania transakcji
Strona **Rozliczenia księgi** zawiera funkcje, które ułatwiają zobaczenie transakcji wymaganych do rozliczenia.

- Użyj filtra **Zaznaczone**, aby filtrować transakcje na podstawie tego, czy zaznaczone jest dla nich pole wyboru **Zaznaczone**.
- Użyj filtru **Stan**, aby filtrować transakcje na podstawie ich stanu.
- Wybierz opcję **Sortuj według kwoty bezwzględnej**, aby posortować kwoty według wartości bezwzględnej. W ten sposób możesz grupować obciążenia i uznania, które mają tę samą kwotę.

## <a name="reverse-a-settlement"></a>Wycofywanie rozliczenia
Można cofnąć rozliczenie, która nastąpiło przez pomyłkę.

1. Wykonaj kroki od 1 do 3 w sekcji [Rozlicz transakcje](#settle-transactions), aby wyświetlić odpowiednie transakcje.
2. W filtrze **Stan** wybierz wartość **Rozliczone**.
3. Wybierz linie do odwrócenia.
4. Wybierz **Odwróć zaznaczone transakcje**. Stan wszystkich transakcji o tym samym identyfikatorze rozliczenia zostanie zaktualizowany na **Nierozliczone**.

    > [!IMPORTANT]
    > Wszystkie transakcje, które mają ten sam identyfikator rozliczenia, zostaną odwrócone, nawet jeśli nie są oznaczone. Na przykład cztery wiersze zostały oznaczone i rozliczone. Wszystkie cztery wiersze mają ten sam identyfikator rozliczenia. Jeśli oznaczysz jeden z czterech wierszy i wybierzesz opcję **Odwróć zaznaczone transakcje**, wszystkie cztery wiersze zostaną wycofane.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
