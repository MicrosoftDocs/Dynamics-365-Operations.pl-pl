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
ms.openlocfilehash: 916f3cfca3bae7a073ce4e956a12080ee01c8d31
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/31/2022
ms.locfileid: "8061285"
---
# <a name="errors-codes-for-the-table-map-health-check"></a>Kody błędów dla kontroli stanu mapy tabeli

[!include [banner](../../includes/banner.md)]



Ten temat opisuje kody błędów dla sprawdzania stanu mapy tabeli.

## <a name="error-100"></a>Error 100

Komunikat o błędzie: „Minimalna wymagana wersja platformy Finanse i Działania w celu uruchomienia rekomendacji Finanse i Działania to PU 43”.

Funkcja ta wymaga aktualizacji platformy dla wersji 10.0.19 lub nowszej aplikacji Finanse i Działania.

## <a name="error-400"></a>Error 400

Komunikat o błędzie: „Nie znaleziono żadnych danych rejestracji zdarzeń biznesowych dla encji \{Finanse i Działania UniqueEntityName\}, co oznacza, że mapa nie jest uruchomiona albo całe mapowanie pól jest jednokierunkowe”.

## <a name="error-500"></a>Error 500

Komunikat o błędzie: „Nie znaleziono żadnych konfiguracji projektu dla \{nazwa projektu\}. Może to być spowodowane tym, że projekt nie jest włączony lub wszystkie mapowania pól są jednokierunkowe z zaangażowania klienta do Finanse i Działania”.

Sprawdź mapowania dla mapy tabel. Jeśli są one jednokierunkowe z aplikacji customer engagement do aplikacjiFinanse i Działania , nie jest generowany ruch do synchronizacji na żywo z aplikacji Finanse i Działania do Dataverse.

## <a name="error-900"></a>Error 900

Komunikat o błędzie: „Nieprawidłowy format filtra źródła filtru \{sourceFilter\} dla encji \{Finanse i Działania UniqueEntityName\}”.

Filtr źródłowy, który jest określony na mapie tabeli dla aplikacji Finanse i Działania nie jest poprawny składniowo. Aby sprawdzić poprawność kryteriów filtrowania, patrz [Rozwiązywanie problemów z synchronizacją na żywo](dual-write-troubleshooting-live-sync.md#live-synchronization-issues-that-are-caused-by-incorrect-query-filter-syntax-on-the-dual-write-maps).

## <a name="error-1000"></a>Error 1000

Komunikat o błędzie: „Zapytanie Entity \{Finanse i Działania UniqueEntityName\} używana do synchronizacji na żywo w trybie podwójnego zapisu to \{Finanse i Działania EntityFilterQueryString\}. Rekordy, które spełniają kryteria zapytania zostaną pobrane do synchronizacji na żywo”.

Zapytanie o encję, które zostało zwrócone jest zapytaniem zwrotnym SQL dla encji. Sprawdź, czy nie występują wewnętrzne złączenia lub filtry w zapytaniu, które określają dane biznesowe, które są pobierane do synchronizacji na żywo. Złączenia wewnętrzne i filtry są obowiązkowymi warunkami, które muszą być spełnione dla każdego rekordu, który jest pobierany do synchronizacji w trybie podwójnego zapisu.

## <a name="error-1300"></a>Error 1300

Komunikat o błędzie: „Pola wirtualne \{s.EntityFieldName\} dla encji \{Finanse i Działania EntityMetadata.EntityProperties.LogicalEntityName\} nie mogą być śledzone dla podwójnego zapisu”.

Pola wirtualne z tabel Finanse i Działania nie są włączone do śledzenia. Synchronizacja na żywo może synchronizować dane, ale nie będzie w stanie wychwycić zmian, które są dokonywane na kolumnach.

## <a name="error-1500"></a>Error 1500

Komunikat o błędzie: „Powinno być co najmniej jedno pole zmapowane do pola non lookup na zaangażowaniu klienta, aby umożliwić śledzenie w źródle danych \{datasource.DataSourceName\}”.

Źródło danych encji nie posiada żadnego pola, które jest zmapowane do podwójnego zapisu. Zmiany w tabeli bazowej nie będą śledzone w przypadku podwójnego zapisu.

## <a name="error-1600"></a>Error 1600

Komunikat o błędzie: „Źródło danych: \{datasource.DataSourceName\} dla encji \{Finanse i Działania EntityMetadata.EntityProperties.LogicalEntityName\} ma zakres. Tylko rekordy spełniające warunki zakresu są odbierane dla wychodzących”.

Encje w aplikacjach Finanse i Działania mogą mieć źródła danych, w których są włączone zakresy filtrów. Zakresy te określają rekordy, które są pobierane w ramach synchronizacji na żywo. Jeśli niektóre rekordy są pomijane w aplikacji Finanse i Działania w Dataverse, należy sprawdzić, czy rekordy spełniają kryteria zakresu na podmiocie. Prostym sposobem na wykonanie tego sprawdzenia jest wykonanie zapytania SQL przypominającego poniższy przykład.

```sql
select * from <EntityName> where <filter criteria for the records> on SQL.
```

## <a name="error-1700"></a>Error 1700

Komunikat o błędzie: „Tabela: \{datasourceTable.Key.subscribedTableName\} dla encji \{datasourceTable.Key.entityName\} jest śledzona dla encji \{origTableToEntityMaps.EntityName\}. Te same tabele śledzone dla wielu podmiotów mogą wpływać na wydajność systemu dla transakcji synchronizacji na żywo”.

Jeśli ta sama tabela jest śledzona przez wiele podmiotów, każda zmiana w tabeli spowoduje ocenę podwójnego zapisu dla połączonych podmiotów. Pomimo, że klauzule filtrujące będą wysyłać tylko poprawne rekordy, ocena może spowodować problem z wydajnością, jeśli istnieją długo trwające zapytania lub niezoptymalizowane plany zapytań. Z biznesowego punktu widzenia tego problemu nie da się uniknąć. Jednakże, jeśli istnieje wiele przecinających się tabel w wielu encjach, powinieneś rozważyć uproszczenie encji lub sprawdzić optymalizacje dla zapytań encji.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
