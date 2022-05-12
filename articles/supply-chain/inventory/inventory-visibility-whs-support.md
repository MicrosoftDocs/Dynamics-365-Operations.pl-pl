---
title: Obsługa dodatku Inventory Visibility dla pozycji WHS
description: Ten temat opisuje obsługę widoczności zapasów dla pozycji, które są włączone do zaawansowanych procesów magazynowych (pozycje WHS).
author: yufeihuang
ms.date: 03/10/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-03-10
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: cfbff05697f4159cb74d110887b8029f28fbf96b
ms.sourcegitcommit: 1050e58e621d9a0454895ed07c286936f8c03320
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/21/2022
ms.locfileid: "8625394"
---
# <a name="inventory-visibility-support-for-whs-items"></a>Obsługa dodatku Inventory Visibility dla pozycji WHS

[!include [banner](../includes/banner.md)]

Ten temat opisuje obsługę widoczności zapasów dla pozycji, które są włączone do zaawansowanych procesów magazynowych (pozycje WHS). Funkcja, która dodaje tę możliwość do Widoczność zapasów, nosi nazwę *Zaawansowany WHS*.

## <a name="whs-items"></a>Pozycje WHS

Pozycja WHS to pozycja, która jest włączona do zaawansowanych procesów magazynowych (WHS) i przetwarzana w magazynie, który również jest włączony do WHS.

Więcej informacji na temat WHS i modułu **Zarządzanie magazynem** w Microsoft Dynamics 365 Supply Chain Management można znaleźć w części [Przegląd zarządzania magazynem](../warehousing/warehouse-management-overview.md).

## <a name="scope-of-the-feature"></a>Zakres funkcji

Zaawansowana funkcja WHS dla Widoczności zapasów koncentruje się na obliczeniach ilości na stanie, które są oparte na zapytaniach o stan na stanie. Funkcja ta nie ma na celu umożliwienia ci wykorzystania Widoczności zapasów do ogólnego zarządzania działaniami związanymi z obsługą magazynu. Widoczność zapasów nie ujawnia swoim użytkownikom pojęć związanych z magazynem. Oto kilka przykładów tych koncepcji:

- Hierarchia rezerwacji
- Czy element lub magazyn jest włączony do systemu WHS
- Identyfikator grupy sekwencji jednostek
- Procesy specyficzne dla magazynu, takie jak wysyłki, ładunki, grupy czynności i praca

Widoczność zapasów uzyskuje te informacje na podstawie danych przesyłanych z Supply Chain Management. Dane specyficzne dla WHS (innymi słowy, dane z tabeli `WHSInventReserve`) nie są widoczne dla użytkowników.

Kiedy używasz funkcji Zaawansowane WHS dla Widoczności zapasów, wszystkie wyniki zapytań będą identyczne z wynikami zapytań wykonywanych bezpośrednio w Supply Chain Management. Nie będą one jednak identyczne z wynikami zapytań wykonywanych za pomocą aplikacji mobilnej Warehouse Management, ponieważ aplikacja mobilna wykorzystuje nieco inną logikę obliczeń.

## <a name="when-to-use-the-feature"></a>Kiedy używać funkcji

Zalecamy, abyś używał funkcji Zaawansowane WHS dla Widoczności zapasów w scenariuszach, w których spełnione są wszystkie poniższe warunki:

- Synchronizujesz dane dotyczące zarządzania łańcuchem dostaw z Widoczności zapasów.
- Używasz WHS w Supply Chain Management.
- Użytkownicy dokonują rezerwacji pozycji WHS na poziomach innych niż poziom magazynu (np. dlatego, że korzystasz z pracy magazynu).

W innych scenariuszach wyniki zapytań o stan posiadania będą takie same, niezależnie od tego, czy włączona jest funkcja Zaawansowana widoczność WHS dla zapasów. Ponadto wydajność będzie lepsza, jeśli nie włączysz tej funkcji w tych scenariuszach, ponieważ jest mniej obliczeń i mniejszy narzut.

## <a name="enable-the-advanced-whs-feature-for-inventory-visibility"></a>Włącz funkcję zaawansowanego WHS dla Widoczności zapasów

Aby włączyć Zaawansowaną funkcję WHS dla Widoczności zapasów, wykonaj poniższe kroki.

1. Zaloguj się do Supply Chain Management jako administrator.
1. Otwórz i przejdź do obszaru roboczego [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) i włącz następujące funkcje w podanej kolejności:

    1. *Integracja Widoczności zapasów*
    1. *Włącz pozycje magazynowe w Widoczności magazynu*

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Parametry integracji dodatku Widoczność magazynu**.
1. Na karcie **Włącz elementy WHS** ustaw dla opcji **Włącz elementy WHS** wartość *Tak*.
1. Zaloguj się w rozwiązaniu Power Apps.
1. Otwórz stronę **Konfiguracja**, a następnie na karcie **Zarządzanie funkcjami** włącz funkcję *Zaawansowane WHS*.
1. W Supply Chain Management przejdź do **Zarządzania zapasami \> Zadania okresowe \> Integracja widoczności zapasów**.
1. Na panelu akcji wybierz **Dezaktywuj**, aby tymczasowo wyłączyć widoczność zapasów.
1. Na panelu akcji wybierz **Włącz**, aby ponownie włączyć Widoczność zapasów. Dodatek zostanie przeładowany, a nowa funkcja będzie teraz aktywna. Twoje dane związane z WHS zaczynają być synchronizowane z Widocznością zapasów.

## <a name="query-on-hand-quantities-of-whs-items"></a>Zapytać o ilości na stanie dla pozycji WHS

Aby zapytać o elementy WHS, używasz tego samego [interfejsu programowania aplikacji (API) i składni wiadomości](inventory-visibility-api.md), którego używasz dla elementów niebędących elementami WHS. Nie musisz określać, czy dany przedmiot jest przedmiotem WHS, czy nie jest. Widoczność zapasów automatycznie rozróżnia pozycje na podstawie przechowywanych danych.

Wyniki kwerend dla przedmiotów WHS są zasadniczo takie same jak wyniki dla przedmiotów spoza WHS. Jedyna różnica polega na tym, że następujące miary fizyczne ze źródła danych `fno` są obliczane na podstawie logiki WHS w Supply Chain Management:

- `AvailOrdered`
- `AvailPhysical`
- `ReservOrdered`
- `ReservPhysical`

Wszystkie inne miary fizyczne są obliczane tak samo, jak wtedy, gdy funkcja Zaawansowane WHS dla Widoczności zapasów jest wyłączona.

Szczegółowe informacje o tym, jak działają obliczenia stanu posiadania dla pozycji WHS, można znaleźć w białej księdze [Rezerwacje w module do zarządzania magazynem](https://www.microsoft.com/download/details.aspx?id=43284).

Jednostki danych eksportowane do Dataverse nie mogą jeszcze aktualizować ilości dla pozycji WHS. Ilości wyświetlane w jednostkach danych są poprawne zarówno dla pozycji nieobjętych systemem WHS, jak i dla ilości, na które nie ma wpływu logika WHS (czyli miar z wyjątkiem `AvailPhysical`, `AvailOrdered`, `ReservPhysical` i `ReservOrdered` w źródle danych `fno`).

Zabronione są zmiany ilości pozycji WHS, które są przechowywane w źródle danych Supply Chain Management. Podobnie jak w przypadku innych funkcji Widoczności zasobów, ograniczenie to jest wymuszone, aby zapobiec konfliktom.

## <a name="soft-reservations-on-whs-items-in-inventory-visibility"></a>Miękkie rezerwacje na elementy WHS w Widoczności zapasów

Ogólnie rzecz biorąc, [miękkie rezerwacje](inventory-visibility-reservations.md) na pozycjach WHS są obsługiwane. W obliczeniach miękkiej rezerwacji możesz uwzględnić środki fizyczne związane z WHS. 

Ze względu na znane ograniczenie, obliczanie *dostępności dla rezerwacji* nie jest obecnie obsługiwane dla elementów WHS. Dlatego, jeśli powyżej bieżącego wymiaru, w którym ma miejsce rezerwacja miękka, znajduje się rezerwacja, wyliczenie *dostępności na rezerwację* jest nieprawidłowe. Miękkie rezerwacje nie będą miały wpływu, gdy opcja **ifCheckAvailForReserv** zostanie wyłączona w [API miękkich rezerwacji](inventory-visibility-api.md#create-one-reservation-event).

Ograniczenie to dotyczy także funkcji i dostosowań, które są oparte na miękkich rezerwacjach (takich jak alokacja).

## <a name="calculate-available-to-promise-quantities"></a>Obliczanie ilości dostępnych do obiecania

Rozwiązanie w pełni obsługuje [dostępne do obiecywania (ATP)](inventory-visibility-available-to-promise.md) dla pozycji WHS. Możesz zdefiniować obliczenia ATP, nie martwiąc się o szczegóły specyficzne dla WHS.
