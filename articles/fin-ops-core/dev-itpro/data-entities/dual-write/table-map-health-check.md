---
title: Kody błędów dla kontroli stanu mapy tabeli
description: Ten temat opisuje kody błędów dla sprawdzania stanu mapy tabeli.
author: nhelgren
ms.date: 10/04/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: nhelgren
ms.search.validFrom: 2021-10-04
ms.openlocfilehash: c2d1f1e39a5ddccddf6fbbf524ff7eb0945b3c32
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2021
ms.locfileid: "7782243"
---
# <a name="errors-codes-for-the-table-map-health-check"></a>Kody błędów dla kontroli stanu mapy tabeli

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ten temat opisuje kody błędów dla sprawdzania stanu mapy tabeli.

## <a name="error-100"></a>Error 100

Komunikat o błędzie: „Minimalna wymagana wersja platformy Finance and Operations w celu uruchomienia rekomendacji Finance and Operations to PU 43”.

Funkcja ta wymaga aktualizacji platformy dla wersji 10.0.19 lub nowszej aplikacji Finance and Operations.

## <a name="error-400"></a>Error 400

Komunikat o błędzie: „Nie znaleziono żadnych danych rejestracji zdarzeń biznesowych dla encji \{Finance and Operations UniqueEntityName\}, co oznacza, że mapa nie jest uruchomiona albo całe mapowanie pól jest jednokierunkowe”.

## <a name="error-500"></a>Error 500

Komunikat o błędzie: „Nie znaleziono żadnych konfiguracji projektu dla \{nazwa projektu\}. Może to być spowodowane tym, że projekt nie jest włączony lub wszystkie mapowania pól są jednokierunkowe z zaangażowania klienta do Finance and Operations”.

Sprawdź mapowania dla mapy tabel. Jeśli są one jednokierunkowe z aplikacji customer engagement do aplikacji Finance and Operations, nie jest generowany ruch do synchronizacji na żywo z aplikacji Finance and Operations do Dataverse.

## <a name="error-900"></a>Error 900

Komunikat o błędzie: „Nieprawidłowy format filtra źródła filtru \{sourceFilter\} dla encji \{Finance and Operations UniqueEntityName\}”.

Filtr źródłowy, który jest określony na mapie tabeli dla aplikacji Finance and Operations nie jest poprawny składniowo. Aby sprawdzić poprawność kryteriów filtrowania, patrz [Rozwiązywanie problemów z synchronizacją na żywo](dual-write-troubleshooting-live-sync.md#live-synchronization-issues-that-are-caused-by-incorrect-query-filter-syntax-on-the-dual-write-maps).

## <a name="error-1000"></a>Error 1000

Komunikat o błędzie: „Zapytanie Entity \{Finance and Operations UniqueEntityName\} używana do synchronizacji na żywo w trybie podwójnego zapisu to \{Finance and Operations EntityFilterQueryString\}. Rekordy, które spełniają kryteria zapytania zostaną pobrane do synchronizacji na żywo”.

Zapytanie o encję, które zostało zwrócone jest zapytaniem zwrotnym SQL dla encji. Sprawdź, czy nie występują wewnętrzne złączenia lub filtry w zapytaniu, które określają dane biznesowe, które są pobierane do synchronizacji na żywo. Złączenia wewnętrzne i filtry są obowiązkowymi warunkami, które muszą być spełnione dla każdego rekordu, który jest pobierany do synchronizacji w trybie podwójnego zapisu.

## <a name="error-1300"></a>Error 1300

Komunikat o błędzie: „Pola wirtualne \{s.EntityFieldName\} dla encji \{Finance and Operations EntityMetadata.EntityProperties.LogicalEntityName\} nie mogą być śledzone dla podwójnego zapisu”.

Pola wirtualne z tabel Finance and Operations nie są włączone do śledzenia. Synchronizacja na żywo może synchronizować dane, ale nie będzie w stanie wychwycić zmian, które są dokonywane na kolumnach.

## <a name="error-1500"></a>Error 1500

Komunikat o błędzie: „Powinno być co najmniej jedno pole zmapowane do pola non lookup na zaangażowaniu klienta, aby umożliwić śledzenie w źródle danych \{datasource.DataSourceName\}”.

Źródło danych encji nie posiada żadnego pola, które jest zmapowane do podwójnego zapisu. Zmiany w tabeli bazowej nie będą śledzone w przypadku podwójnego zapisu.

## <a name="error-1600"></a>Error 1600

Komunikat o błędzie: „Źródło danych: \{datasource.DataSourceName\} dla encji \{Finance and Operations EntityMetadata.EntityProperties.LogicalEntityName\} ma zakres. Tylko rekordy spełniające warunki zakresu są odbierane dla wychodzących”.

Encje w aplikacjach Finance and Operations mogą mieć źródła danych, w których są włączone zakresy filtrów. Zakresy te określają rekordy, które są pobierane w ramach synchronizacji na żywo. Jeśli niektóre rekordy są pomijane w aplikacji Finance and Operations w Dataverse, należy sprawdzić, czy rekordy spełniają kryteria zakresu na podmiocie. Prostym sposobem na wykonanie tego sprawdzenia jest wykonanie zapytania SQL przypominającego poniższy przykład.

```sql
select * from <EntityName> where <filter criteria for the records> on SQL.
```

## <a name="error-1700"></a>Error 1700

Komunikat o błędzie: „Tabela: \{datasourceTable.Key.subscribedTableName\} dla encji \{datasourceTable.Key.entityName\} jest śledzona dla encji \{origTableToEntityMaps.EntityName\}. Te same tabele śledzone dla wielu podmiotów mogą wpływać na wydajność systemu dla transakcji synchronizacji na żywo”.

Jeśli ta sama tabela jest śledzona przez wiele podmiotów, każda zmiana w tabeli spowoduje ocenę podwójnego zapisu dla połączonych podmiotów. Pomimo, że klauzule filtrujące będą wysyłać tylko poprawne rekordy, ocena może spowodować problem z wydajnością, jeśli istnieją długo trwające zapytania lub niezoptymalizowane plany zapytań. Z biznesowego punktu widzenia tego problemu nie da się uniknąć. Jednakże, jeśli istnieje wiele przecinających się tabel w wielu encjach, powinieneś rozważyć uproszczenie encji lub sprawdzić optymalizacje dla zapytań encji.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
