---
title: Edycja i przeprowadzanie inspekcji transakcji zamówień online i asynchronicznych zamówień klienta
description: W tym artykule opisano sposób edytowania i przeprowadzania inspekcji transakcji zamówień online i asynchronicznych zamówień odbiorcy w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 10/21/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.industry: Retail
ms.openlocfilehash: dbeeff47446c1617da44f34ae56f333717f577a1
ms.sourcegitcommit: 18b7a02c497709e8d9c7b943d82f1fcc3dafa4cd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/21/2022
ms.locfileid: "9712117"
---
# <a name="edit-and-audit-online-order-and-asynchronous-customer-order-transactions"></a>Edycja i przeprowadzanie inspekcji transakcji zamówień online i asynchronicznych zamówień klienta

[!include [banner](../includes/banner.md)]

W tym artykule opisano sposób edytowania i przeprowadzania inspekcji transakcji zamówień online i asynchronicznych zamówień odbiorcy w rozwiązaniu Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Między wersjami 10.0.5 i 10.0.6 rozwiązania Commerce dodano do niego obsługę edycji transakcji kasowych i przeniesienia (takich jak sprzedaż i zwroty) oraz transakcji zarządzania gotówką (takich jak przyjęcie do kasy i pobranie środków płatniczych). W wersji 10.0.7 rozwiązania Commerce dodano obsługę edycji transakcji zamówień online i asynchronicznych transakcji zamówienia odbiorców.

## <a name="edit-and-audit-order-transactions"></a>Edycja i przeprowadzanie inspekcji transakcji zamówień

Aby edytować transakcje zamówień i przeprowadzać ich inspekcję w centrali Commerce headquarters, wykonaj kroki opisane poniżej.

1. Zainstaluj [Microsoft Dynamics Office Add-in](https://appsource.microsoft.com/product/office/WA104379629?tab=Overview).
1. Na skróconej karcie **Zamówienie** na karcie **Zamówienia odbiorcy** na stronie **Parametry rozwiązania Commerce** określ kod wstrzymania dla opcji **Kod wstrzymania dla błędów synchronizacji zamówień**.
2. Wstrzymanie innych zadań synchronizacji zamówień, które będą kolidować z czasem edycji i inspekcji.
3. Otwórz obszar roboczy **Finanse sklepu**. Kafelki **Błędy synchronizacji zamówień online** i **Błędy synchronizacji zamówień odbiorcy** oferują wstępnie przefiltrowany widok strony transakcji sprzedaży detalicznej. W każdym z tych widoków można sprawdzić rekordy transakcji, których weryfikacja się nie powiodła, dla odpowiedniego typu zamówień.
4. Otwórz stronę **Błędy synchronizacji zamówień online** lub **Błędy synchronizacji zamówień odbiorcy**. Wybierz rekord, aby wyświetlić szczegóły błędu synchronizacji. Na skróconej karcie **Stan synchronizacji** są widoczne następujące szczegóły błędu:

    - Stan zamówienia oczekującego
    - Szczegóły błędu zamówienia
    - Data i godzina modyfikacji
    - Liczba ponownych prób

1. Jeśli szczegóły błędu wskazują na konieczność naprawienia rekordu, wybierz pozycję **Dodatek pakietu Office**, a następnie wybierz pozycję **Edytuj wybraną transakcję**. Zostanie otwarty plik programu Excel ze szczegółowymi informacjami dotyczącymi wybranej transakcji.

    - Jeśli edytowana transakcja to transakcja zamówienia online, plik programu Excel będzie zawierać następujące arkusze:

        - **Transakcja** — ten arkusz zawiera szczegóły nagłówka dotyczące transakcji.
        - **Transakcja sprzedaży** — ten arkusz zawiera szczegóły wiersza dotyczące transakcji.
        - **Transakcje płatności** — ten arkusz zawiera wiersze szczegółów płatności dla transakcji.
        - **Transakcje rabatu** — ten arkusz zawiera szczegóły dotyczące rabatów dla transakcji.
        - **Transakcje podatku** — ten arkusz zawiera szczegóły dotyczące podatku dla transakcji.
        - **Transakcje opłat** — ten arkusz zawiera dane dotyczące opłat dla transakcji.

    - Jeśli edytowana transakcja to transakcja asynchronicznego zamówienia odbiorcy, plik programu Excel będzie zawierać następujące arkusze:

        - **Wiersze** — ten arkusz zawiera szczegóły nagłówka i wiersza dotyczące transakcji.
        - **Płatności** — ten arkusz zawiera wiersze szczegółów płatności dla transakcji.
        - **Rabaty** — ten arkusz zawiera szczegóły dotyczące rabatów dla transakcji.
        - **Podatki** — ten arkusz zawiera szczegóły dotyczące podatków dla transakcji.
        - **Opłaty** — ten arkusz zawiera dane dotyczące opłat dla transakcji.

1. W polu **Stan zamówienia oczekującego** w pliku programu Excel wprowadź wartość **Edycja**, a następnie opublikuj zmianę. Dzięki temu podczas przetwarzania w czasie wykonywania zadania **Synchronizacja zamówienia** uruchamianego w trybie wsadowym ten rekord nie zostanie pominięty.
1. W pliku programu Excel możesz zmodyfikować odpowiednie pola, a następnie przekazać dane z powrotem do centrali Commerce, korzystając z funkcji publikowania aplikacji dodatkowej Dynamics Excel. Po opublikowaniu danych zmiany staną się widoczne w systemie. W trakcie publikacji nie jest przeprowadzana weryfikacja zmian wprowadzonych przez użytkownika.
    > [!NOTE]
    > Jeśli nie można znaleźć pola, które należy edytować, wykonaj poniższe kroki, aby dodać brakujące pole w arkuszu.
    >   1. Wybierz **Projekt** w łączniku danych.
    >   1. Wybierz ikonę ołówka obok tabeli, do której chcesz dodać pole.
    >   1. Wybierz pole w obszarze **Dostępne pola**, a następnie wybierz **Dodaj**.
    >   1. Dodaj tyle pól, ile potrzeba, a następnie wybierz opcję **Aktualizuj**.
    >   1. Po zakończeniu aktualizacji może być konieczne wybranie przycisku **Odśwież**, aby zaktualizować wartości.

3. Pełen dziennik inspekcji zmian można wyświetlić, wybierając opcję **Wyświetl dziennik inspekcji** na nagłówku **Transakcja sprzedaży detalicznej** dla zmian na poziomie nagłówka i w odpowiednim obszarze i rekordzie na stosownej stronie transakcji. Na przykład wszystkie zmiany związane z wierszami sprzedaży będą wyświetlane na stronie **Transakcje sprzedaży**, a wszystkie zmiany związane z płatnościami będą wyświetlane na stronie **Transakcje płatności**. Dla zmian są obsługiwane następujące szczegóły inspekcji:

    - Data i godzina modyfikacji
    - Pole
    - Stara wartość
    - Nowa wartość
    - Zmodyfikowane przez

1. Po dokonaniu i opublikowaniu zmian wybierz pozycję **Synchronizacja zamówienia**, aby natychmiast rozpocząć proces synchronizacji. Możesz również poczekać na przetworzenie transakcji w ramach procesu synchronizacji uruchomionego w trybie wsadowym.

Pomyślnie zsynchronizowane zamówienia zostają domyślnie wstrzymane w oparciu o kod wstrzymania zdefiniowany w parametrach rozwiązania Commerce. Wstrzymanie zleceń musi zostać usunięte, zanim zamówienia będą mogły zostać przekazane do dalszego przetworzenia w celu umożliwienia realizacji zamówień lub wykonania innych operacji.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Edycja i przeprowadzanie inspekcji transakcji kasowych i przeniesienia oraz zarządzania gotówką](edit-cash-trans.md)

[Edytowanie wymiarów finansowych dla transakcji sprzedaży detalicznej](edit-financial-dim.md)

[Tworzenie skoroszytu programu Excel w celu edytowania transakcji detalicznych](create-excel-edit.md)

[Dodawanie pól do skoroszytu programu Excel w celu edytowania transakcji detalicznych](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
