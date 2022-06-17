---
title: Edycja i przeprowadzanie inspekcji transakcji kasowych i przeniesienia oraz zarządzania gotówką
description: W tym artykule opisano sposób edytowania i przeprowadzania inspekcji transakcji kasowych i przeniesienia oraz zarządzania gotówką w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: cab28dee425110f47a4e2ec5a737778dd567d786
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873338"
---
# <a name="edit-and-audit-cash-and-carry-and-cash-management-transactions"></a>Edycja i przeprowadzanie inspekcji transakcji kasowych i przeniesienia oraz zarządzania gotówką

[!include [banner](../includes/banner.md)]

W tym artykule opisano sposób edytowania i przeprowadzania inspekcji transakcji kasowych i przeniesienia oraz zarządzania gotówką w rozwiązaniu Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Klienci korzystający z rozwiązania Dynamics 365 Commerce używają w punkcie sprzedaży (POS) zarówno aplikacji naszej firmy, jak i aplikacji pochodzących od innych firm. W przypadku naszej aplikacji transakcje sklepu są pobierane z kanałów do centrali Commerce w toku procesu wsadowego. W przypadku aplikacji innych firm transakcje są pobierane do centrali Commerce w toku integracji. W obu przypadkach po pobraniu transakcji do centrali Commerce należy wykonać proces sprawdzania spójności. Ten proces przeprowadza wiele weryfikacji transakcji, by tylko pomyślnie zweryfikowane transakcje zostały pobrane do zestawienia, które zostanie zaksięgowane w centrali Commerce.

Transakcje Commerce mogą nie przejść weryfikacji z różnych powodów. Błąd w kodzie integracji lub w aplikacji POS może spowodować brak spójności danych. Błąd użytkownika także może spowodować brak spójności danych. Przykładem takiej sytuacji jest usunięcie produktu po jego synchronizacji z kanałem lub zamknięcie okresu obrachunkowego bez zaksięgowania transakcji za dany okres. Choć takie transakcje zostają oflagowane i wyłączone z zestawień, mogą zakłócić codzienny proces księgowania do działu finansowego klienta. W rozwiązaniu Commerce można edytować transakcje, których weryfikacja się nie powiodła, jednocześnie przeprowadzając inspekcje wszystkich zmian.

## <a name="edit-transactions"></a>Edycja transakcji

W wersji 10.0.5 rozwiązania Commerce można edytować tylko transakcje kasowe i przeniesienia, jak sprzedaż i zwroty. Zamówienia klienta i zamówienia online nie mogą być edytowane. W wersji 10.0.6 i nowszych rozwiązania Commerce można również edytować transakcje zarządzania gotówką.

Aby edytować transakcje w centrali Commerce, wykonaj kroki opisane poniżej.

1. Zainstaluj [Microsoft Dynamics Office Add-in](https://appsource.microsoft.com/product/office/WA104379629?tab=Overview).
1. W centrali Commerce otwórz obszar roboczy **Finanse sklepu**. Kafelek **Weryfikacje transakcji zakończone niepowodzeniem** oferuje wstępnie filtrowany widok strony transakcji, która nie spełniła co najmniej jednej reguły weryfikacji.
1. Otwórz stronę transakcji, wybierz zapis, którego weryfikacja się nie powiodła, wybierz pozycję **Dodatek pakietu Office**, a następnie wybierz pozycję **Edytuj wybraną transakcję**. Zostanie otwarty plik programu Excel ze szczegółowymi informacjami dotyczącymi wybranej transakcji. Ten plik zawiera następujące arkusze:

    - **Wiersze** — ten arkusz zawiera nagłówek i wiersze produktów dla transakcji oraz dane dotyczące transakcji.
    - **Płatności** — ten arkusz zawiera wiersze szczegółów płatności dla transakcji.
    - **Rabaty** — ten arkusz zawiera szczegóły dotyczące rabatów dla transakcji.
    - **Podatki** — ten arkusz zawiera szczegóły dotyczące podatków dla transakcji.
    - **Opłaty** — ten arkusz zawiera dane dotyczące opłat dla transakcji.

1. W pliku programu Excel możesz zmodyfikować odpowiednie pola, a następnie przekazać dane z powrotem do centrali Commerce, korzystając z funkcji publikowania aplikacji dodatkowej Dynamics Excel. Po opublikowaniu danych zmiany staną się widoczne w systemie. W trakcie publikacji nie jest przeprowadzana weryfikacja zmian wprowadzonych przez użytkownika.
1. Pełen dziennik inspekcji zmian można wyświetlić, wybierając opcję **Wyświetl dziennik inspekcji** na nagłówku **Transakcja sprzedaży detalicznej** dla zmian na poziomie nagłówka i w odpowiednim obszarze i rekordzie na stosownej stronie transakcji. Na przykład wszystkie zmiany związane z wierszami sprzedaży będą wyświetlane na stronie **Transakcje sprzedaży**, a wszystkie zmiany związane z płatnościami będą wyświetlane na stronie **Transakcje płatności**. Dla zmian są obsługiwane następujące szczegóły inspekcji:

    - Data i godzina modyfikacji
    - Pole
    - Stara wartość
    - Nowa wartość
    - Zmodyfikowane przez

1. Po wprowadzeniu i opublikowaniu zmian uruchom opcję **Sprawdź poprawność transakcji w sklepie**, by upewnić się, że dokonane zmiany są spójne i prawidłowe.

> [!NOTE]
> Edycja jest dozwolona wyłącznie dla transakcji, których weryfikacja się nie powiodła. Jeśli chcesz edytować transakcję, której weryfikacja zakończyła się pomyślnie, zmień stan weryfikacji danej transakcji na **Błąd** lub **Brak**, a następnie opublikuj zmianę. Po wykonaniu tej czynności można przeprowadzić edycję danych w nagłówku lub w innych rekordach podrzędnych transakcji i opublikować nagłówek lub rekordy.

## <a name="bulk-edit-transactions-that-are-linked-to-a-statement"></a>Edycja zbiorcza transakcji połączonych z zestawieniem

Rozwiązanie Commerce w wersji 10.0.6 i nowszych obsługuje opcję edycji zbiorczej transakcji na poziomie zestawienia.

Aby edytować zbiorczo transakcje połączone z zestawieniem w centrali Commerce, wykonaj kroki opisane poniżej.

1. Otwórz stronę **Zestawienia** i wybierz zestawienie zawierające transakcje, które powinny zostać poddane edycji.
1. Wybierz przycisk **Otwórz w pakiecie Microsoft Office**.
1. W zależności od tego, jakie dane mają zostać poddane edycji, wybierz jedną z następujących opcji:

    - **Edytuj transakcje kasowe i przeniesienia** — ta opcja umożliwia edytowanie wszystkich transakcji kasowych i przeniesienia, które należą do zestawienia. Dostępne są następujące arkusze programu Excel:

        - **Transakcja** — ten arkusz zawiera wszystkie informacje na poziomie nagłówka dla transakcji sprzedaży.
        - **Transakcja sprzedaży** — ten arkusz zawiera wszystkie informacje na poziomie wiersza dla transakcji sprzedaży.
        - **Transakcje płatności** — ten arkusz zawiera wszystkie informacje wiersza płatności dla transakcji sprzedaży.
        - **Transakcje rabatu** — ten arkusz zawiera wszystkie informacje wiersza rabatu dla transakcji sprzedaży.
        - **Transakcje podatku** — ten arkusz zawiera wszystkie informacje wiersza podatków dla transakcji sprzedaży.
        - **Transakcje opłat** — ten arkusz zawiera wszystkie informacje wiersza opłat dla transakcji sprzedaży.

    - **Edytuj transakcje zarządzania gotówką** — ta opcja umożliwia edytowanie wszystkich transakcji zarządzania gotówką, które należą do zestawienia. Dostępne są następujące arkusze programu Excel:

        - **Transakcja** — ten arkusz zawiera wszystkie informacje na poziomie nagłówka dla transakcji zarządzania gotówką.
        - **Transakcje wpłat bankowych** — ten arkusz zawiera wszystkie szczegóły transakcji przekazania pieniędzy do banku.
        - **Transakcje wpływające na kwotę w kasecie kasowej** — ten arkusz zawiera wszystkie szczegóły transakcji wpływających na kwotę w kasecie kasowej.
        - **Deklaracja środków płatniczych** — ten arkusz zawiera wszystkie szczegóły transakcji deklaracji środków płatniczych.
        - **Transakcje przychodów/wydatków** — ten arkusz zawiera wszystkie szczegóły wiersza transakcji przychodów/wydatków.
        - **Transakcje płatności** — ten arkusz zawiera wszystkie informacje dotyczące płatności dla operacji **Zapłać fakturę**, a także transakcję przychodów/wydatków.

1. Edytuj odpowiednie transakcje.

    > [!NOTE]
    > Weryfikacje nie są przeprowadzane, gdy publikowane są transakcje edytowane zbiorczo. Należy się upewnić, że wszystkie zmiany są dokładne i że zachowana jest wierność danych we wszystkich arkuszach. Na przykład jeśli chcesz zmienić datę transakcji, by móc zarządzać scenariuszami, gdzie okres obrachunkowy lub magazynowy dla otwartych transakcji jest zamknięty, musisz zmienić datę we wszystkich arkuszach programu Excel, które zawierają kolumnę **Data biznesowa**. Aby zweryfikować transakcje po ich edycji, możesz wybrać opcję **Ponownie sprawdź poprawność transakcji** na stronie **Zestawienia**. Zanim zaksięgujesz zestawienie, poczekaj na zakończenie zadania sprawdzania poprawności.

1. Jeśli agregacja została już wygenerowana, otwórz stronę **Zagregowane transakcje** i wybierz pozycję **Wygeneruj ponownie dokument XML z zamówieniem sprzedaży**.

## <a name="bulk-edit-transactions-that-arent-linked-to-a-statement"></a>Edycja zbiorcza transakcji, które nie są połączone z zestawieniem

W wersji 10.0.10 i nowszych rozwiązania Commerce dostępna jest opcja służąca do edycji zbiorczej transakcji, których weryfikacja się nie powiodła, ale które nie są połączone z zestawieniem.

Aby edytować zbiorczo transakcje, które nie są połączone z zestawieniem w centrali Commerce, wykonaj kroki opisane poniżej.

1. Otwórz stronę **Wszystkie sklepy** i wybierz sklep, dla którego mają być edytowane transakcje.
1. Wybierz przycisk **Otwórz w pakiecie Microsoft Office**, a następnie wybierz opcję **Edytuj transakcje kasowe i przeniesienia**.
1. Edytuj odpowiednie transakcje, a następnie opublikuj je.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Edycja i przeprowadzanie inspekcji transakcji zamówień online i asynchronicznych zamówień odbiorcy](edit-order-trans.md)

[Edytowanie wymiarów finansowych dla transakcji sprzedaży detalicznej](edit-financial-dim.md)

[Tworzenie skoroszytu programu Excel w celu edytowania transakcji detalicznych](create-excel-edit.md)

[Dodawanie pól do skoroszytu programu Excel w celu edytowania transakcji detalicznych](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]