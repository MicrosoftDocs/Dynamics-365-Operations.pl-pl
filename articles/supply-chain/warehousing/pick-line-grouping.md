---
title: Grupowanie wierszy pobrania
description: Ten temat zawiera omówienie grupowania wierszy pobrania.
author: Mirzaab
manager: tfehr
ms.date: 12/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem,WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 7ab8cdd7cad5420aca0de53e59220da9e230d411
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5234640"
---
# <a name="pick-line-grouping"></a>Grupowanie wierszy pobrania

[!include [banner](../includes/banner.md)]

Grupowanie wierszy pobrania sprawia, że wiele wierszy pracy, które mają ten sam element i lokalizację, można łączyć w jednym pobraniu prezentowanym użytkownikowi na urządzeniu przenośnym. Dzięki temu pracownicy magazynu mogą odbierać najbardziej efektywne instrukcje, ale wymagane rozdzielenie wierszy pracy w systemie może być również zachowane (na przykład dla różnych kontenerów, zamówień itd.).

## <a name="turn-on-the-pick-line-grouping-feature"></a>Włącz funkcję grupowania wierszy pobrania

Aby móc używać tej funkcji, należy ją włączyć w systemie. Administratorzy mogą skorzystać z obszaru roboczego [Zarządzania funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba. Ta funkcja jest wymieniona w następujący sposób:

- **Moduł:** *Zarządzanie magazynem*
- **Nazwa funkcji:** *Grupowanie wiersza pobrania*

## <a name="set-up-pick-line-grouping"></a>Konfigurowanie grupowania wierszy pobrania

### <a name="create-a-mobile-device-menu-item"></a>Tworzenie elementu menu urządzenia przenośnego

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W polu **Nazwa elementu menu** wprowadź pozycję *Pobranie wierszy grupy sprzedaży*.
1. W polu **Tytuł** wprowadź pozycję *Pobranie wierszy grupy sprzedaży*. Ten tytuł będzie wyświetlany w menu urządzenia przenośnego.
1. W polu **Tryb** wybierz opcję *Praca*.
1. W opcji **Użyj istniejącej pracy** zaznacz wartość *Tak*.
1. Na skróconej karcie **Ogólne** ustaw następujące wartości:

    - W polu **Sterowane przez** wybierz opcję *Sterowane przez użytkownika*.
    - Ustaw opcję **Generuj numer identyfikacyjny:** na *Tak*.
    - Ustaw opcję *Pobranie grupowe* na **Tak**.
    - Zaakceptuj wartość domyślną dla wszystkich pozostałych opcji.

1. Wykonaj następujące kroki, aby skonfigurować prawidłowe klasy robocze dla elementu menu urządzenia przenośnego:

    1. Na skróconej karcie **Klasy pracy** wybierz pozycję **Nowy**.
    2. W polu **Identyfikator klasy roboczej** możesz wybrać pozycję *Sprzedaż* lub *Pobranie zamówienia sprzedaży*, zależnie od magazynu, którego będziesz używać. W tym scenariuszu wybierz opcję *Pobranie zamówienia sprzedaży*.

        Pole **Typ zlecenia pracy** jest automatycznie ustawiane na *Zamówienia sprzedaży*.

### <a name="set-up-a-mobile-device-menu"></a>Konfigurowanie menu urządzenia przenośnego

Aby dodać utworzony właśnie element menu do menu **Wychodzące**, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Menu urządzenia przenośnego**.
1. W okienku akcji wybierz pozycję **Edytuj**.
1. W okienku listy są pokazywane wszystkie istniejące menu urządzenia przenośnego. Na liście wybierz *Wychodzące*.
1. Na liście **Dostępne menu i elementy menu** znajdź i wybierz element menu *Pobranie wierszy grupy sprzedaży*, który został utworzony.
1. Wybierz przycisk strzałki w prawo, aby przenieść element menu *Pobranie wierszy grupy sprzedaży* na listę **Struktura menu**.
1. Za pomocą przycisków strzałki w górę i w dół przenieś element menu w żądane miejsce w strukturze menu.
1. Na okienku akcji wybierz opcję **Zapisz**.

### <a name="set-up-a-work-template"></a>Konfigurowanie szablonów pracy

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Szablony pracy**.
1. W polu **Typ zlecenia pracy** wybierz opcję *Zamówienia sprzedaży*.
1. W siatce **Omówienie** znajdź i wybierz szablon pracy, który ma być używany z tą funkcją. W tym scenariuszu wybierz szablon *51 Pobranie do lokalizacji przejściowej*.
1. W okienku akcji wybierz pozycję **Edytuj zapytanie**.
1. W oknie dialogowym edytora zapytań, na karcie **Sortowanie** wybierz opcję **Dodaj**, a następnie określ następujące wartości nowego wiersza:

    - W kolumnie **Tabela** wybierz pozycję *Transakcje pracy tymczasowej*.
    - W kolumnie **Tabela pochodna** wybierz pozycję *Transakcje pracy tymczasowej*.
    - W kolumnie **Pole** wybierz pozycję *Numer elementu*.
    - W kolumnie **Kierunek wyszukiwania** wybierz opcję *Rosnąco*.

1. Wybierz przycisk **OK**, aby zamknąć okno dialogowe i zapisać wybrane opcje.
1. Zostanie wyświetlony następujący komunikat: „Grupowanie zostanie zresetowane, czy chcesz kontynuować?” Wybierz przycisk **Tak**, aby kontynuować.

> [!IMPORTANT]
> Aby funkcja grupowania wierszy pobrania mogła działać, wiersze pracy muszą być sortowane według identyfikatora elementu. Jeśli wiersze, które mają te same elementy, nie są sekwencjonowane jeden po drugim, nie zostaną zgrupowane.

## <a name="example"></a>Przykład

### <a name="create-picking-work"></a>Tworzenie pracy pobrania

Aby można było skonfigurować grupowanie wierszy pobrania, należy utworzyć kilka kwalifikujących się prac wychodzących.

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. Wybierz pozycję **Nowe**, aby utworzyć nowe zamówienie sprzedaży.
1. W polu **Konto odbiorcy** zaznacz wartość *US-004*.
1. Na skróconej karcie **Ogólne** w polu **Magazyn** wybierz wartość *51*.
1. Kliknij przycisk **OK**.
1. Na skróconej karcie **Wiersze zamówienia sprzedaży** dodaj sześć następujących wierszy:

    - **Wiersz 1:** w polu **Numer elementu** wybierz wartość *M9200*. W polu **Ilość** wpisz wartość *3*.
    - **Wiersz 2:** w polu **Numer elementu** wybierz wartość *M9201*. W polu **Ilość** wpisz wartość *3*.
    - **Wiersz 3:** w polu **Numer elementu** wybierz wartość *M9202*. W polu **Ilość** wpisz wartość *2*.
    - **Wiersz 4:** w polu **Numer elementu** wybierz wartość *M9200*. W polu **Ilość** wpisz wartość *1*.
    - **Wiersz 5:** w polu **Numer elementu** wybierz wartość *M9200*. W polu **Ilość** wpisz wartość *3*.
    - **Wiersz 6:** w polu **Numer elementu** wybierz wartość *M9202*. W polu **Ilość** wpisz wartość *7*.

    Poniżej znajduje się podsumowanie całkowitych ilości dla każdego elementu:

    - **Element M9200:** *7* szt.
    - **Element M9201:** *3* szt.
    - **Element M9202:** *9* szt.

1. Przed zwolnieniem zleceń do magazynu należy upewnić się, że lokalizacje pobrania mają wystarczającą ilość zapasów dla wszystkich pozycji na wszystkich zamówieniach. Przejrzyj ustawienie **Dyrektywa lokalizacji**, aby określić, które lokalizacje pobrania są używane do pobrania zamówienia sprzedaży. Jeśli używasz pokazowego środowiska danych firmy Contoso dla magazynu *51*, potwierdź, że są dostępne zapasy.

    Teraz musisz zarezerwować zapasy dla każdego wiersza.

1. Na skróconej karcie **Wiersze zamówienia sprzedaży** wybierz jeden z wierszy, które muszą zostać zarezerwowane.
1. W menu **Zapasy** nad siatką wybierz opcję **Rezerwacja**.
1. Na stronie **Rezerwacja**, w okienku akcji, wybierz pozycję **Rezerwacja partii**, aby zastosować rezerwację. Następnie zamknij stronę.
1. Powtórz kroki od 8 do 10 w przypadku pozostałych wierszy, które muszą zostać zarezerwowane.

    Musisz teraz wydać zamówienie sprzedaży do magazynu.

1. W okienku akcji na karcie **Magazyn** wybierz opcję **Zwolnienie do magazynu**.

    Zostanie wyświetlony komunikat informujący o utworzeniu wysyłki i grupy czynności, a następnie o przesłaniu grupy czynności do uruchomienia w partii.

    Po zakończeniu grupy czynności i wszystkich zadań w kierunku od dołu do klienta jest tworzony identyfikator pracy, która ma sześć wierszy. Wiersze są sortowane według numeru elementu.

1. Przejdź do obszaru **Zarządzanie magazynem \> Praca \> Cała praca**, aby wyświetlić utworzoną pracę. Zanotuj wartość **Identyfikatora pracy**. Będziesz go używać w następnej procedurze.

### <a name="initiate-picking-from-the-mobile-device"></a>Inicjowanie pobierania z urządzenia przenośnego

1. Zaloguj się do urządzenia mobilnego jako użytkownik skonfigurowany dla magazynu *51*.
1. Na urządzeniu przenośnym wybierz menu, które zawiera nowy element menu urządzenia przenośnego. W tym scenariuszu wybierz opcję **Wychodzące**.
1. Wybierz element menu **Pobranie wierszy grupy sprzedaży** i zainicjuj pobranie.
1. Wprowadź wartość **identyfikatora pracy** zanotowaną w poprzedniej procedurze.

    Powinien zostać wyświetlony krok pobrania, w którym wszystkie wiersze pobrania dla towaru *M9200* są pogrupowane i otrzymasz instrukcję pobrania *7* sztuk towaru *M9200*.

    > [!IMPORTANT]
    > Na urządzeniu przenośnym praca pobierania dla trzech wierszy pobrania pracy została zsumowana w jednym kroku pobrania dla użytkownika.

1. Potwierdź krok pobrania.
1. Przejdź do strony pracy, aby sprawdzić jej identyfikator, i zwróć uwagę, że wszystkie trzy wiersze pobrania dla elementu *M9200* zostały zamknięte jednocześnie.
1. Wróć na urządzenie przenośne i kontynuuj pobieranie. Powinien zostać pokazany wiersz pracy 4 dla pozycji *M9201*. Ponieważ w zamówieniu był tylko jeden wiersz pracy, nie ma żadnych danych do zagregowania.
1. Potwierdź krok pobrania.
1. Ostatni krok pobrania na urządzeniu przenośnym agreguje ostatnie dwa wiersze pobrania ze zlecenia pracy.
1. Ukończ krok pobrania dla *9* sztuk elementu *M9202*.
1. Potwierdź krok odłożenia i wszelkie dodatkowe pary pobranie/odłożenie, aby ukończyć pracę.

> [!IMPORTANT]
>
> - Wiersze pracy można grupować tylko wtedy, gdy są ustawione w kolejności.
> - Poniższe funkcje nie są obsługiwane:
>
>   - Towary w ilości efektywnej
>
>    Jeśli w pracy znajdują się wszystkie dowolne towary w ilości efektywnej, przed rozpoczęciem pobrania zostanie wyświetlony komunikat o błędzie.
>
>   - Pobranie sztuk
>   - Wiersze pracy z niedokończoną pracą uzupełniania zapasów
>   - Pobranie nadmiarowe
>   - Pobieranie w niedomiarze wraz ze zmianą alokacji pozycji


[!INCLUDE[footer-include](../../includes/footer-banner.md)]