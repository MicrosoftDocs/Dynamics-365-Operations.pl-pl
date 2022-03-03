---
title: Zmień pulę pracy w pracy
description: W tym temacie wyjaśniono, jak można używać przycisku Zmień pulę prac dla elementów pracy, aby zmienić pulę pracy istniejącej pracy.
author: mirzaab
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWorkPool,WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 9255b7d2eaf030592207b557b3b6567a1a5bda98
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/09/2022
ms.locfileid: "8102870"
---
# <a name="change-work-pool-on-work"></a>Zmień pulę pracy w pracy

[!include [banner](../includes/banner.md)]

Można używać puli prac do organizacji pracy w grupy. Można na przykład utworzyć pulę pracy do sklasyfikowania pracy, która występuje w określonej lokalizacji magazynu.

Funkcja *Zmień pulę pracy w pracy* powoduje dodanie przycisku **Zmień pulę prac** do okienka akcji dla elementów pracy. Dlatego Menedżer magazynu może łatwo zmienić pulę pracy istniejącej pracy. Ta funkcja pozwala menedżerom szybko reagować na zmiany w hali produkcyjnej magazynu i pomaga poprawić ich zdolność przystosowania się do zmieniających się sytuacji i konieczności przeniesienia pracy do innej puli pracy.

## <a name="turn-the-change-work-pool-on-work-feature-on-or-off"></a>Włącz lub wyłącz funkcję Zmień pulę pracy na pracę

Od wersji 10.0.25 Supply Chain Management ta funkcja jest obowiązkowa i nie można jej wyłączyć. Jeśli używasz wersji starszej niż 10.0.25, administratorzy mogą włączyć lub wyłączyć tę funkcję, wyszukując funkcję *Zmień pulę pracy na pracę* w obszarze roboczym [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="set-up-the-change-work-pool-on-work-feature"></a>Ustaw funkcję Zmień pulę pracy dla pracy

Aby można było korzystać z tej funkcji, muszą być skonfigurowane pule pracy. Można również skonfigurować szablony pracy, aby automatycznie przypisywać pulę. Jeśli użytkownik chce pracować w przykładowym scenariuszu przedstawionym w dalszej części tego tematu, należy skonfigurować system zgodnie z opisem w tej sekcji.

### <a name="set-up-work-pools"></a>Ustawianie pul pracy

Pule pracy umożliwiają organizowanie elementów pracy według typów. Aby pracować z funkcją *Zmień pulę pracy dla pracy*, trzeba mieć co najmniej dwie dostępne pule pracy. Aby wyświetlić i dodać pule pracy, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Pule pracy**.
1. Jeśli użytkownik pracuje z danymi demonstracyjnymi z firmy **USMF** i w dalszej części tego tematu może współpracować z przykładowym scenariuszem, należy dodać dwie pule pracy o następujących ustawieniach:

    - Pula pracy 1:

        - **Identyfikator puli pracy:** *Webshop*
        - **Opis:** *Sklep internetowy*

    - Pula pracy 2:

        - **Identyfikator puli pracy:** *CallCenter*
        - **Opis:** *Call Center*

1. Na okienku akcji wybierz opcję **Zapisz**.

### <a name="set-up-work-templates"></a>Ustaw szablony pracy

Dla każdego z szablonów pracy można określić domyślną pulę pracy, stosownie do potrzeb. Dla każdego odpowiedniego szablonu należy przypisać pulę pracy w kolumnie **Identyfikator puli pracy**. W takim przypadku wszystkie elementy pracy wygenerowane za pomocą danego szablonu automatycznie odziedziczą przypisaną pulę pracy. Jeśli użytkownik pracuje z danymi demonstracyjnymi z firmy **USMF** i w dalszej części tego tematu może współpracować z przykładowym scenariuszem, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Szablony pracy**.
1. W okienku akcji wybierz opcję **Edytuj**, aby umieścić stronę w trybie edycji.
1. Edytuj szablon, ustawiając następujące wartości:

    - **Szablon pracy:** *62 Pobranie do pakowania*
    - **Identyfikator puli pracy:** *Webshop*

1. Wybierz opcję **Zapisz**.

## <a name="example-scenario"></a>Przykładowy scenariusz

W tym scenariuszu przedstawiono sposób zmiany strumienia przetwarzania dla istniejącego elementu pracy przez zmianę jego puli pracy. Używa on danych demonstracyjnych z firmy **USMF** oraz ustawień, które zostały zasugerowane wcześniej w tym temacie.

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a>Utwórz zamówienie sprzedaży i zwolnij je do magazynu

1. Upewnij się, że jest wystarczająca ilość dostępnych zapasów dla pozycji *A0001* i *A0002* w magazynie *62*. Przejdź do **Zarządzanie zapasami \> Zapytania i raporty \> Lista dostępnych**, a następnie zmień filtry, tak jak pokazano poniżej:

    - Wartość **Magazynu** zaczyna się od *62*.
    - Wartość **Identyfikator pozycji** to albo *A001* albo *A002*.

    Dane demonstracyjne powinny zawierać ilość 10 sztuk na każdy.

    Następnie należy utworzyć zamówienie sprzedaży.

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:

    - **Konto odbiorcy:** *US-007*
    - **Magazyn:** *62*

1. Naciśnij przycisk **OK**, aby zamknąć okno dialogowe i utworzyć nowe zamówienie zakupu.
1. Nowe zamówienie zakupu (PO) zostało otwarte. Powinno zawierać pusty wiersz w siatce na skróconej karcie **Wiersze zamówienia sprzedaży**. W nowym wierszu ustaw następujące wartości:

    - **Numer pozycji:** *A0001*
    - **Ilość:** *2*

1. W menu **Zapasy** nad siatką wybierz opcję **Rezerwacja**.
1. Na stronie **Rezerwacja**, w okienku akcji, wybierz pozycję **Rezerwacja partii**, aby zarezerwować zapasy.
1. Zamknij stronę.
1. Na skróconej karcie **Wiersze zamówienia sprzedaży** wybierz opcję **Dodaj wiersz**, aby dodać kolejny wiersz do zamówienia sprzedaży. W nowym wierszu ustaw następujące wartości:

    - **Numer pozycji:** *A0002*
    - **Ilość:** *2*

1. W menu **Zapasy** nad siatką wybierz opcję **Rezerwacja**.
1. Na stronie **Rezerwacja**, w okienku akcji, wybierz pozycję **Rezerwacja partii**, aby zarezerwować zapasy.
1. Zamknij stronę.
1. W okienku akcji na karcie **Magazyn** wybierz opcję **Zwolnienie do magazynu**.
1. Użytkownik otrzymuje komunikaty informacyjne, które zawierają identyfikator grupy czynności oraz identyfikator wysyłki utworzony ze zwolnienia. Zanotuj identyfikator grupy czynności.

### <a name="review-the-outbound-wave"></a>Przegląd wychodzącą grupę czynności

1. Przejdź do **Zarządzanie magazynem \> Wychodzące grupy czynności \> Grupy czynności wysyłki \> Wszystkie grupy czynności**.
1. W siatce wyszukaj identyfikator grupy czynności, który został utworzony na podstawie zwolnienia zamówienia sprzedaży.
1. Wybierz identyfikator grupy czynności, aby wyświetlić szczegóły.
1. Na skróconej karcie **Wiersze grupy czynności** należy upewnić się, że dla zamówienia sprzedaży jest wyświetlany identyfikator wysyłki.

    > [!TIP]
    > Jeśli opcja **Przetwarzanie grupy czynności w czasie uwalniania jej do magazynu** jest ustawiona na *Nie*, należy ręcznie przetworzyć tę operację, wybierając opcję **Przetwarzaj** z karty **Grupa czynności** w okienku akcji, aby utworzyć pracę.

1. Upewnij się, że dana grupa czynności została przetworzona. To przetwarzanie powoduje utworzenie wymaganej pracy.

### <a name="view-work-details-and-change-the-work-pool"></a>Wyświetl szczegóły pracy i zmień pulę pracy

Strona **Szczegóły pracy** służy do wyświetlania pracy, która została utworzona, oraz do zarządzania pulą pracy.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Praca \> Szczegóły pracy**.
1. Umożliwia wybór wiersza dla pracy, która została właśnie utworzona. W kolumnie **Numer zamówienia** zostanie wyświetlony numer zamówienia sprzedaży.

    W polu **Identyfikator puli pracy** zostanie ustawiony Identyfikator puli pracy, który został ustawiony w szablonie pracy.

    > [!TIP]
    > Jeśli pole **Identyfikator puli pracy** nie jest widoczny, dodaj kolumnę do siatki, a następnie odśwież stronę.

1. Aby zmienić pulę pracy skojarzoną z identyfikatorem pracy, w okienku akcji na karcie **Praca** wybierz opcję **Zmień identyfikator puli pracy**.
1. W oknie dialogowym **Zmień pulę pracy**, na skróconej karcie **Parametry** w polu **Identyfikator puli pracy** wybierz pozycję *CallCenter*.
1. Wybierz **OK**, aby zastosować zmianę.
1. Zauważ, że wartość pola **Identyfikator puli pracy** została zmieniona na *CallCenter*.

> [!IMPORTANT]
> Po wyświetleniu okna dialogowego **Zmień pulę pracy** pole **Identyfikator puli pracy** może domyślnie być puste Jeśli pole jest puste po wybraniu opcji **OK** w celu zastosowania zmian, Ppula pracy zostanie całkowicie usunięta z pracy.
>
> Oprócz przełączenia pul pracy można skorzystać z tej procedury, aby dodać pulę pracy do dowolnego elementu pracy, który jej nie ma, lub usunąć pulę pracy z dowolnego elementu pracy, który ją posiada.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]