---
title: Grupowanie wierszy pobrania
description: Ten temat zawiera omówienie grupowania wierszy pobrania.
author: Mirzaab
manager: tfehr
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem,WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: b3497d43a500898207ed5154721ee0e3a327fb93
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2020
ms.locfileid: "4017743"
---
# <a name="pick-line-grouping"></a>Grupowanie wierszy pobrania

[!include [banner](../includes/banner.md)]

Podczas grupowania wierszy pobrania wiele wierszy pracy, które mają ten sam element i lokalizację, można łączyć w jednym pobraniu prezentowanym użytkownikowi na urządzeniu przenośnym. Dzięki temu pracownicy magazynu mogą odbierać najbardziej efektywne instrukcje, które są możliwe, ale wymagane rozdzielenie wierszy pracy w systemie jest również zachowane (na przykład dla różnych kontenerów i zamówień).

## <a name="set-up-pick-line-grouping"></a>Konfigurowanie grupowania wierszy pobrania

### <a name="create-a-mobile-device-menu-item"></a>Tworzenie elementu menu urządzenia przenośnego

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego** i utwórz nowy element menu o nazwie **Pobieranie wierszy grupy sprzedaży — sterowane przez użytkownika**.
2. W obszarze **Elementy menu urządzenia przenośnego** ustaw następujące wartości:

    - W polu **Nazwa elementu menu** wprowadź pozycję **Pobranie sprzedaży — wiersz grupy**.
    - W polu **Tytuł** wprowadź pozycję **Pobranie sprzedaży — wiersz grupy**.
    - W polu **Tryb** wybierz opcję **Praca**.
    - W opcji **Użyj istniejącej pracy** zaznacz wartość **Tak**.

3. Na skróconej karcie **Ogólne** możesz ustawić następujące wartości:

    - W polu **Sterowane przez** wybierz opcję **Sterowane przez użytkownika**.
    - Ustaw opcję **Generuj numer identyfikacyjny:** na **Tak**.
    - Ustaw opcję **Pobranie grupowe** na **Tak**.

4. Na skróconej karcie **Klasy robocze** wykonaj następujące kroki, aby skonfigurować prawidłowe klasy robocze dla elementu menu urządzenia przenośnego:

    1. Wybierz pozycję **Nowy**.
    2. W polu **Identyfikator klasy roboczej** wybierz pozycję **Sprzedaż** lub **Pobranie zamówienia sprzedaży** , zależnie od magazynu, którego będziesz używać.
    3. W polu **Typ zlecenia pracy** wybierz opcję **Zamówienia sprzedaży**.

### <a name="set-up-a-mobile-device-menu"></a>Konfigurowanie menu urządzenia przenośnego

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Menu urządzenia przenośnego**. 
1. Dodaj element menu, który został właśnie utworzony, do żądanego menu.

### <a name="set-up-a-work-template"></a>Konfigurowanie szablonów pracy

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Szablony pracy**.
1. Znajdź szablon pracy, który ma być używany z tą funkcją. W tym przykładzie wybierz standardowy szablon pracy Contoso **51 Pobranie do lokalizacji przejściowej**.
1. W menu wybierz pozycję **Edytuj zapytanie**.
1. Na karcie **Sortowanie** wybierz pozycję **Dodaj** , a następnie ustaw następujące wartości:

    - W polu **Tabela** wybierz pozycję **Transakcje pracy tymczasowej**.
    - W polu **Tabela pochodna** wybierz pozycję **Transakcje pracy tymczasowej**.
    - W polu **Pole** wybierz pozycję **Numer elementu**.
    - W polu **Kierunek wyszukiwania** wybierz opcję **Rosnąco**.

> [!NOTE]
> Aby funkcja grupowania wierszy pobrania mogła działać, wiersze pracy muszą być sortowane według identyfikatora elementu. Jeśli wiersze, które mają te same elementy, nie są sekwencjonowane jeden po drugim, nie zostaną zgrupowane.

## <a name="example"></a>Przykład

### <a name="create-picking-work"></a>Tworzenie pracy pobrania

Aby można było skonfigurować grupowanie wierszy pobrania, należy utworzyć kilka kwalifikujących się prac wychodzących.

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
2. Wybierz pozycję **Nowe** , aby utworzyć nowe zamówienie sprzedaży. 
3. W polu **Konto klienta** wybierz dowolnego klienta. 
4. Na skróconej karcie **Ogólne** w polu **Magazyn** wybierz wartość **51**. Następnie wybierz opcję **OK**.
5. W obszarze **Wiersze zamówienia sprzedaży** dodaj sześć następujących wierszy:

    - **Wiersz 1:** w polu **Numer elementu** wybierz wartość **M9200**. W polu **Ilość** wpisz wartość **3**.
    - **Wiersz 2:** w polu **Numer elementu** wybierz wartość **M9201**. W polu **Ilość** wpisz wartość **3**. 
    - **Wiersz 3:** w polu **Numer elementu** wybierz wartość **M9202**. W polu **Ilość** wpisz wartość **2**. 
    - **Wiersz 4:** w polu **Numer elementu** wybierz wartość **M9200**. W polu **Ilość** wpisz wartość **1**. 
    - **Wiersz 5:** w polu **Numer elementu** wybierz wartość **M9200**. W polu **Ilość** wpisz wartość **3**.
    - **Wiersz 6:** w polu **Numer elementu** wybierz wartość **M9202**. W polu **Ilość** wpisz wartość **7**. 

    Poniżej znajduje się podsumowanie całkowitych ilości dla każdego elementu:

    - **Element M9200:** 7 sztuk
    - **Element M9201:** 3 sztuki
    - **Element M9202:** 9 sztuk

6. Przed zwolnieniem zleceń do magazynu należy upewnić się, że lokalizacje pobrania mają wystarczającą ilość zapasów dla wszystkich pozycji na wszystkich zamówieniach. Przejrzyj ustawienie **Dyrektywa lokalizacji** , aby określić, które lokalizacje pobrania są używane do pobrania zamówienia sprzedaży.
7. Zarezerwuj zapasy i zwolnij je do magazynu. Tworzony jest identyfikator pracy, który ma sześć wierszy. Wiersze są sortowane według numeru elementu.

### <a name="run-the-mobile-device-flow"></a>Uruchamianie przepływu na urządzeniu przenośnym

1. Na urządzeniu przenośnym wybierz menu, które zawiera nowy element menu urządzenia przenośnego.
1. Wybierz element menu **Pobranie sprzedaży — wiersz grupy** i zainicjuj pobranie.

    Po wybraniu menu i wprowadzeniu identyfikatora pracy zobaczysz krok pobrania, w którym wszystkie wiersze pobrania dla elementu M9200 są zgrupowane. Otrzymasz instrukcję, aby wybrać 7 sztuk elementu M9200.

1. Potwierdź krok pobrania. 
1. Przejdź do ekranu klienta pracy w toku i zwróć uwagę, że wszystkie trzy wiersze pobrania dla elementu M9200 zostały zamknięte jednocześnie.

    Zostanie wyświetlony wiersz pracy 4.

1. Potwierdź krok pobrania.

    Ostatni krok pobrania na urządzeniu przenośnym agreguje ostatnie dwa wiersze pobrania ze zlecenia pracy.

1. Ukończ krok pobrania dla 9 sztuk elementu M9202.
1. Potwierdź krok odłożenia i wszelkie dodatkowe pary pobranie/odłożenie, aby ukończyć pracę.

> [!NOTE]
> - Wiersze pracy można grupować tylko wtedy, gdy są ustawione w kolejności.
> - Poniższe funkcje nie są obsługiwane:
>
>    - Towary w ilości efektywnej. Jeśli w pracy znajdują się wszystkie dowolne towary w ilości efektywnej, przed rozpoczęciem pobrania zostanie wyświetlony komunikat o błędzie.
>    - Pobranie sztuk.
>    - Wiersze pracy z niedokończoną pracą uzupełniania zapasów.
>    - Pobranie nadmiarowe.
>    - Pobieranie w niedomiarze wraz ze zmianą alokacji pozycji
