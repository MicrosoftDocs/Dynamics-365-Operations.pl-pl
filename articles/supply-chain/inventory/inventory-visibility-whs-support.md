---
title: Obsługa dodatku Inventory Visibility dla pozycji WMS
description: Ten artykuł opisuje obsługę widoczności zapasów dla pozycji, które są włączone do procesów magazynowych (pozycje WMS).
author: yufeihuang
ms.date: 11/04/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-03-10
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: bed402ecf20c19e81b2687efd90dba600460971a
ms.sourcegitcommit: 49f8973f0e121eac563876d50bfff00c55344360
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/14/2022
ms.locfileid: "9762762"
---
# <a name="inventory-visibility-support-for-wms-items"></a>Obsługa dodatku Inventory Visibility dla pozycji WMS

[!include [banner](../includes/banner.md)]

Ten artykuł opisuje obsługę widoczności zapasów dla pozycji, które są włączone do procesów magazynowych (WMS). Funkcja, która dodaje tę możliwość do Widoczność zapasów, nosi nazwę *Zaawansowany WMS*.

## <a name="wms-items"></a>Pozycje WMS

Pozycja WMS to pozycja, która jest włączona do procesów WMS i przetwarzana w magazynie, który również jest włączony do WMS.

Więcej informacji na temat WMS i modułu **Zarządzanie magazynem** w Microsoft Dynamics 365 Supply Chain Management można znaleźć w części [Przegląd zarządzania magazynem](../warehousing/warehouse-management-overview.md).

## <a name="scope-of-the-feature"></a>Zakres funkcji

Zaawansowana funkcja WMS dla Widoczności zapasów koncentruje się na obliczeniach ilości na stanie, które są oparte na zapytaniach o stan na stanie. Funkcja ta nie ma na celu umożliwienia ci wykorzystania Widoczności zapasów do ogólnego zarządzania działaniami związanymi z obsługą magazynu. Widoczność zapasów nie ujawnia swoim użytkownikom pojęć związanych z magazynem. Oto kilka przykładów tych koncepcji:

- Hierarchia rezerwacji
- Czy element lub magazyn jest włączony do systemu WMS
- Identyfikator grupy sekwencji jednostek
- Procesy specyficzne dla magazynu, takie jak wysyłki, ładunki, grupy czynności i praca

Widoczność zapasów uzyskuje te informacje na podstawie danych przesyłanych z Supply Chain Management. Dane specyficzne dla WMS (innymi słowy, dane z tabeli `WHSInventReserve`) nie są widoczne dla użytkowników.

Kiedy używasz funkcji Zaawansowane WMS dla Widoczności zapasów, wszystkie wyniki zapytań będą identyczne z wynikami zapytań wykonywanych bezpośrednio w Supply Chain Management. Nie będą one jednak identyczne z wynikami zapytań wykonywanych za pomocą aplikacji mobilnej Warehouse Management, ponieważ aplikacja mobilna wykorzystuje nieco inną logikę obliczeń.

## <a name="when-to-use-the-feature"></a>Kiedy używać funkcji

Zalecamy, abyś używał funkcji WMS dla Widoczności zapasów w scenariuszach, w których spełnione są wszystkie poniższe warunki:

- Synchronizujesz dane dotyczące zarządzania łańcuchem dostaw z Widoczności zapasów.
- Używasz WMS w Supply Chain Management.
- Użytkownicy dokonują rezerwacji dla towarów WMS na poziomach poniżej poziomu magazynu (na przykład na poziomie numeru identyfikacyjnego, ponieważ przetwarzasz pracę magazynową).

W innych scenariuszach wyniki zapytań o stan posiadania będą takie same, niezależnie od tego, czy włączona jest funkcja Zaawansowana widoczność WMS dla zapasów. Ponadto wydajność będzie lepsza, jeśli nie włączysz tej funkcji w tych scenariuszach, ponieważ jest mniej obliczeń i mniejszy narzut.

## <a name="enable-the-wms-feature-for-inventory-visibility"></a>Włącz funkcję WMS dla Widoczności zapasów

Aby włączyć funkcję WMS dla Widoczności zapasów, wykonaj poniższe kroki.

1. Zaloguj się do Supply Chain Management jako administrator.
1. Otwórz i przejdź do obszaru roboczego [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) i włącz następujące funkcje w podanej kolejności:

    1. *Integracja Widoczności zapasów*
    1. *Włącz pozycje magazynowe w Widoczności magazynu*

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Parametry integracji dodatku Widoczność magazynu**.
1. Na karcie **Włącz elementy WMS** ustaw dla opcji **Włącz elementy WMS** wartość *Tak*.
1. Zaloguj się do swojego środowiska Power Apps i otwórz aplikację **Widoczność magazynu**.
1. Otwórz stronę **Konfiguracja**, a następnie na karcie **Zarządzanie funkcjami** włącz funkcję *Zaawansowane WHS*.
1. W Supply Chain Management przejdź do **Zarządzania zapasami \> Zadania okresowe \> Integracja widoczności zapasów**.
1. Na panelu akcji wybierz **Dezaktywuj**, aby tymczasowo wyłączyć widoczność zapasów.
1. Na panelu akcji wybierz **Włącz**, aby ponownie włączyć Widoczność zapasów. Dodatek zostanie przeładowany, a nowa funkcja będzie teraz aktywna. Twoje dane związane z WMS zaczynają być synchronizowane z Widocznością zapasów.

## <a name="query-on-hand-quantities-of-wms-items"></a>Zapytać o ilości na stanie dla pozycji WMS

Aby zapytać o elementy WMS, używasz tego samego [interfejsu programowania aplikacji (API) i składni wiadomości](inventory-visibility-api.md), którego używasz dla elementów niebędących elementami WMS. Nie musisz określać, czy dany przedmiot jest przedmiotem WMS, czy nie jest. Widoczność zapasów automatycznie rozróżnia pozycje na podstawie przechowywanych danych.

Wyniki kwerend dla przedmiotów WMS są zasadniczo takie same jak wyniki dla przedmiotów spoza WMS. Jedyna różnica polega na tym, że następujące miary fizyczne ze źródła danych `fno` są obliczane na podstawie logiki WMS w Supply Chain Management:

- `AvailOrdered`
- `AvailPhysical`
- `ReservOrdered`
- `ReservPhysical`

Wszystkie inne miary fizyczne są obliczane tak samo, jak wtedy, gdy funkcja WMS dla Widoczności zapasów jest wyłączona.

Szczegółowe informacje o tym, jak działają obliczenia stanu posiadania dla pozycji WMS, można znaleźć w białej księdze [Rezerwacje w module do zarządzania magazynem](https://www.microsoft.com/download/details.aspx?id=43284).

## <a name="on-hand-list-view-and-data-entity-for-wms-items"></a>Widok listy dostępnych zapasów i jednostka danych dla pozycji WMS

Strona **Wstępne załadowanie podsumowania widoczności magazynu** zawiera widok jednostki *Wyniki wstępnego ładowania zapytania indeksu dostępnych zapasów*. W przeciwieństwie do jednostki *Podsumowanie zapasów*, jednostka *Wyniki wstępnego ładowania zapytania indeksu dostępnych zapasów* zawiera listę dostępnych zapasów produktów wraz z wybranymi wymiarami. Widoczność magazynu synchronizuje wstępnie załadowane dane zbiorcze co 15 minut.

Jeśli używasz widoczności zapasów z elementami WMS i chcesz wyświetlić listę dostępnych elementów WMS, zalecamy włączenie funkcji *Wstępne ładowanie podsumowania widoczności zapasów* (zobacz także temat [Wstępnie załaduj ujednolicone zapytanie dostępnych zapasów](inventory-visibility-power-platform.md#preload-streamlined-onhand-query)). Odpowiednia jednostka danych Dataverse przechowuje wynik wstępnego ładowania kwerendy, aktualizowany co 15 minut. Nazwa jednostki danych: `Onhand Index Query Preload Result`.

> [!IMPORTANT]
> Encja Dataverse jest tylko do odczytu. Dane w jednostkach Widoczność zapasów można wyświetlać i eksportować, ale **nie można ich modyfikować**.

Zabronione są zmiany ilości pozycji WMS, które są przechowywane w źródle danych Supply Chain Management (`fno`). Takie działanie pasuje do innych funkcji widoczności zapasów. To ograniczenie jest wymuszane, aby zapobiec konfliktom.

## <a name="wms-item-compatibility-for-other-functions-in-inventory-visibility"></a>Zgodność towarów z programem WMS dla innych funkcji w widoczności zapasów

[Obsługiwane są rezerwacje miękkie](inventory-visibility-reservations.md) i [alokacja zapasów](inventory-visibility-allocation.md) pozycji w WMS. W obliczeniach miękkiej rezerwacji i alokacji możesz uwzględnić środki fizyczne związane z WMS.

## <a name="calculate-available-to-promise-quantities"></a>Obliczanie ilości dostępnych do obiecania

Rozwiązanie w pełni obsługuje [dostępne do obiecywania (ATP)](inventory-visibility-available-to-promise.md) dla pozycji WMS. Możesz zdefiniować obliczenia ATP, nie martwiąc się o szczegóły specyficzne dla WMS.
