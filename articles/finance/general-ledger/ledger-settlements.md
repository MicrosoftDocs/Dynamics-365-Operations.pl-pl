---
title: Rozliczenia księgi
description: W tym temacie wyjaśniono, jak na stronie Rozliczenia księgi rozliczać transakcji księgi i wycofywać rozliczenia.
author: mikefalkner
manager: aolson
ms.date: 09/28/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransSettlement
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-11-30
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: d41a69bed3d1340736cc7df35aa3ded032d4d79d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446711"
---
# <a name="ledger-settlements"></a>Rozliczenia księgi

[!include [banner](../includes/banner.md)]

Funkcjonalność rozliczeń księgi pozwala uzgadniać transakcje debetowe i kredytowe w księdze głównej i następnie oznaczać je jako rozliczone. W ten sposób można uzyskać pewność, że powiązane transakcje zostały wzajemnie zbilansowane. Można również wycofywać rozliczenia, jeśli zostały dokonane przez pomyłkę.

## <a name="enable-advanced-ledger-settlements"></a>Włączanie funkcjonalności zaawansowanego rozliczania księgi

Na stronie zaawansowanych rozliczeń księgi znajdują się dodatkowe funkcje filtrowania i wybierania transakcji. Aby włączyć stronę zaawansowanych rozliczeń księgi, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Księga główna** \> **Ustawienia księgi** \> **Parametry księgi głównej**. 
2. Na karcie **Rozliczenia księgi** ustaw opcję **Zaawansowane rozliczenie księgi** na **Tak**, aby włączyć funkcjonalność zaawansowanego rozliczania księgi. Strona z zaawansowanymi ustawieniami **Rozliczenia księgi** będzie używana po wybraniu opcji **Rozliczenia księgi** w oknie **Zadania okresowe**. 
3. Musisz wprowadzić listę kont, które mają być używane to rozliczeń księgi dla każdego planu kont. Ta lista jest używana do filtrowania transakcji wyświetlanych na stronie **Rozliczenia księgi**. Na liście **Plan kont** wybierz plan kont, a następnie wybierz opcję **Nowy**, aby dodać nowe konta do listy.

## <a name="settle-transactions-by-using-the-advanced-ledger-settlements-page"></a>Rozliczanie transakcji za pomocą strony zaawansowanych rozliczeń księgi

W celu rozliczenia transakcji księgi wykonaj następujące czynności.

1. Wybierz kolejno opcje **Księga główna** \> **Zadania okresowe** \> **Rozliczenia księgi**.
2. Ustaw filtry w górnej części strony:

    - Wybierz zakres dat lub kliknij opcję **Kod zakresu dat**, aby przedział został wypełniony automatycznie.
    - W razie potrzeby zmień warstwę księgowania.
    - Aby osobno wyświetlać konto księgowe i wymiary, wybierz zestaw wymiarów finansowych.

3. Wybierz opcję **Wyświetl transakcje**, aby wyświetlić wszystkie transakcje zgodne z ustawionymi filtrami oraz z listą kont określonych podczas konfigurowania listy planu kont w poprzedniej sekcji. Jeśli zmodyfikujesz którykolwiek filtr lub zestaw wymiarów, należy ponownie kliknąć opcję **Wyświetl transakcje**.
4. Wybierz jeden lub więcej wierszy, które chcesz objąć rozliczeniem. Wartość pola **Wybrana kwota** u góry strony zwiększy się lub zmniejszy o łączną kwotę w zaznaczonych wierszach.
5. Po zakończeniu wybierania transakcji wybierz opcję **Oznacz wybrane**. Dla każdej wybranej transakcji w kolumnie **Oznaczone** pojawi się znacznik wyboru. Ponadto wartość pola **Oznaczona kwota** nad siatką zwiększy się lub zmniejszy o łączną kwotę w oznaczonych wierszach.
6. Gdy pole **Oznaczona kwota** ma wartość **0** (zero), wybierz opcję **Rozlicz oznaczone transakcje**. Stan oznaczonych transakcji zostanie zaktualizowany na **Rozliczone**.

## <a name="make-transactions-easier-to-find"></a>Ułatwienie znajdowania transakcji

Strona **Rozliczenia księgi** zawiera funkcje, które ułatwiają zobaczenie transakcji potrzebnych do rozliczenia.

- Przycisk **Usuń oznaczenie wybranych** czyści pole **Oznaczone** we wszystkich zaznaczonych wierszach.
- Filtr **Oznaczone** umożliwia filtrowanie transakcji na podstawie tego, czy ich pole **Oznaczone** jest zaznaczone, czy wyczyszczone.
- Filtr **Stan** umożliwia filtrowanie transakcji w oparciu o to, czy ich stan to **Rozliczone**, czy **Nie rozliczono**.
- Przycisk **Sortuj według kwoty bezwzględnej** pozwala sortować kwoty według wartości bezwzględnych, dzięki czemu można pogrupować pozycje debetowe i kredytowe mające te same kwoty.

## <a name="reverse-a-settlement"></a>Wycofywanie rozliczenia

Można cofnąć rozliczenie, która nastąpiło przez pomyłkę.

1. Wykonaj kroki od 1 do 3 w sekcji „Rozliczanie transakcji za pomocą strony zaawansowanych rozliczeń księgi”, aby wyświetlić żądane transakcje.
2. W filtrze **Stan** wybierz wartość **Rozliczone**.
3. Wybierz jeden lub więcej wierszy, które chcesz objąć wycofaniem. Wartość pola **Wybrana kwota** u góry strony zwiększy się lub zmniejszy o łączną kwotę w zaznaczonych wierszach.
4. Po zakończeniu wybierania transakcji wybierz opcję **Oznacz wybrane**. Dla każdej wybranej transakcji w kolumnie **Oznaczone** pojawi się znacznik wyboru. Ponadto wartość pola **Oznaczona kwota** u góry strony zwiększy się lub zmniejszy o łączną kwotę w oznaczonych wierszach.
5. Gdy pole **Oznaczona kwota** ma wartość **0** (zero), wybierz opcję **Wycofaj oznaczone transakcje**. Stan oznaczonych transakcji zostanie zaktualizowany na **Nie rozliczono**.

## <a name="update-the-list-of-accounts-that-are-included-in-the-list-of-transactions"></a>Aktualizowanie listy kont uwzględnionych na liście transakcji

Wybierz opcję **Konta rozliczenia księgi**, aby otworzyć okno dialogowe służące do edytowania kont uwzględnionych na liście transakcji. Kliknij przycisk **Nowy**, aby dodać nowe konta do listy. Ta lista jest używana do filtrowania transakcji wyświetlanych na stronie **Rozliczenia księgi**.
