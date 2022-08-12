---
title: Kody błędów dla kontroli stanu mapy tabeli
description: Ten artykuł opisuje kody błędów dla kontroli kondycji mapy tabeli.
author: RamaKrishnamoorthy
ms.date: 05/31/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-10-04
ms.openlocfilehash: 16c79a788b66830b77b2cdfb33fd2416c530f7d2
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/02/2022
ms.locfileid: "9111575"
---
# <a name="errors-codes-for-the-table-map-health-check"></a>Kody błędów dla kontroli stanu mapy tabeli

[!include [banner](../../includes/banner.md)]



Ten artykuł opisuje kody błędów dla kontroli kondycji mapy tabeli.

## <a name="error-100"></a>Error 100

Komunikat o błędzie: „Minimalna wymagana wersja aplikacji finansowych i operacyjnych w celu uruchomienia rekomendacji aplikacji finansowych i operacyjnych to PU 43”.

Funkcja ta wymaga aktualizacji platformy dla wersji 10.0.19 lub nowszej aplikacji finansowych i operacyjnych.

## <a name="error-400"></a>Error 400

Komunikat o błędzie: „Nie znaleziono żadnych danych rejestracji zdarzeń biznesowych dla encji \{ aplikacje finansowe i operacyjne UniqueEntityName\}, co oznacza, że mapa nie jest uruchomiona albo całe mapowanie pól jest jednokierunkowe”.

## <a name="error-500"></a>Error 500

Komunikat o błędzie: „Nie znaleziono żadnych konfiguracji projektu dla \{nazwa projektu\}. Może to być spowodowane tym, że projekt nie został włączony lub wszystkie mapowania pól są jednokierunkowe z zaangażowania klienta do aplikacji finansowych i operacyjnych”.

Sprawdź mapowania dla mapy tabel. Jeśli są one jednokierunkowe z aplikacji Customer Engagement do aplikacji finansowych i operacyjnych, nie jest generowany ruch do synchronizacji na żywo z aplikacji finansowych i operacyjnych do usługi Dataverse.

## <a name="error-900"></a>Error 900

Komunikat o błędzie: „Nieprawidłowy format filtra źródła filtru \{sourceFilter\} dla encji \{ aplikacji finansowych i operacyjnych UniqueEntityName\}”.

Filtr źródłowy, który jest określony na mapie tabeli dla aplikacji finansowych i operacyjnych nie jest poprawny składniowo. Aby sprawdzić poprawność kryteriów filtrowania, patrz [Rozwiązywanie problemów z synchronizacją na żywo](dual-write-troubleshooting-live-sync.md#live-synchronization-issues-that-are-caused-by-incorrect-query-filter-syntax-on-the-dual-write-maps).

## <a name="error-1000"></a>Error 1000

Komunikat o błędzie: „Zapytanie encji\{ aplikacji finansowych i operacyjnych UniqueEntityName\} używana do synchronizacji na żywo w trybie podwójnego zapisu to \{aplikacje finansowe i operacyjne EntityFilterQueryString\}. Rekordy, które spełniają kryteria zapytania zostaną pobrane do synchronizacji na żywo”.

Zapytanie o encję, które zostało zwrócone jest zapytaniem zwrotnym SQL dla encji. Sprawdź, czy nie występują wewnętrzne złączenia lub filtry w zapytaniu, które określają dane biznesowe, które są pobierane do synchronizacji na żywo. Złączenia wewnętrzne i filtry są obowiązkowymi warunkami, które muszą być spełnione dla każdego rekordu, który jest pobierany do synchronizacji w trybie podwójnego zapisu.

## <a name="error-1300"></a>Error 1300

Komunikat o błędzie: „Pola wirtualne \{s.EntityFieldName\} dla encji \{ aplikacje finansowe i operacyjne EntityMetadata.EntityProperties.LogicalEntityName\} nie mogą być śledzone dla podwójnego zapisu”.

Pola wirtualne z tabel aplikacji finansowych i operacyjnych nie są włączone do śledzenia. Synchronizacja na żywo może synchronizować dane, ale nie będzie w stanie wychwycić zmian, które są dokonywane na kolumnach.

## <a name="error-1500"></a>Error 1500

Komunikat o błędzie: „Powinno być co najmniej jedno pole zmapowane do pola non lookup na zaangażowaniu klienta, aby umożliwić śledzenie w źródle danych \{datasource.DataSourceName\}”.

Źródło danych encji nie posiada żadnego pola, które jest zmapowane do podwójnego zapisu. Zmiany w tabeli bazowej nie będą śledzone w przypadku podwójnego zapisu.

## <a name="error-1600"></a>Error 1600

Komunikat o błędzie: „Źródło danych: \{datasource.DataSourceName\} dla encji \{aplikacji finansowych i operacyjnych EntityMetadata.EntityProperties.LogicalEntityName\} ma zakres. Tylko rekordy spełniające warunki zakresu są odbierane dla wychodzących”.

Encje w aplikacjach finansowych i operacyjnych mogą mieć źródła danych, w których są włączone zakresy filtrów. Zakresy te określają rekordy, które są pobierane w ramach synchronizacji na żywo. Jeśli niektóre rekordy są pomijane w aplikacjach finansowych i operacyjnych w Dataverse, należy sprawdzić, czy rekordy spełniają kryteria zakresu na podmiocie. Prostym sposobem na wykonanie tego sprawdzenia jest wykonanie zapytania SQL przypominającego poniższy przykład.

```sql
select * from <EntityName> where <filter criteria for the records> on SQL.
```

## <a name="error-1700"></a>Error 1700

Komunikat o błędzie: „Tabela: \{datasourceTable.Key.subscribedTableName\} dla encji \{datasourceTable.Key.entityName\} jest śledzona dla encji \{origTableToEntityMaps.EntityName\}. Te same tabele śledzone dla wielu podmiotów mogą wpływać na wydajność systemu dla transakcji synchronizacji na żywo”.

Jeśli ta sama tabela jest śledzona przez wiele podmiotów, każda zmiana w tabeli spowoduje ocenę podwójnego zapisu dla połączonych podmiotów. Pomimo, że klauzule filtrujące będą wysyłać tylko poprawne rekordy, ocena może spowodować problem z wydajnością, jeśli istnieją długo trwające zapytania lub niezoptymalizowane plany zapytań. Z biznesowego punktu widzenia tego problemu nie da się uniknąć. Jednakże, jeśli istnieje wiele przecinających się tabel w wielu encjach, powinieneś rozważyć uproszczenie encji lub sprawdzić optymalizacje dla zapytań encji.

## <a name="error-1800"></a>Error 1800
Komunikat o błędzie: „Źródło danych: element {} dla encji CustCustomerV3Entity zawiera wartość zakresu. Wartości zakresów w encji mogą wpływać na operacje typu upsert dla rekordów przychodzących z usługi Dataverse do aplikacji finansowych i operacyjnych. Przetestuj aktualizacje rekordów z usługi Dataverse do aplikacji finansowych i operacyjnych przy użyciu rekordów, które nie spełniają kryteriów filtrowania, aby zweryfikować ustawienia”.

Jeśli istnieje zakres określony dla encji w aplikacjach finansowych i operacyjnych, synchronizacja danych przychodzących z usługi Dataverse do aplikacji finansowych i operacyjnych powinna być testowana pod kątem zachowania aktualizacji w rekordach, które nie spełniają kryteriów zakresu. Każdy rekord, który nie pasuje do zakresu, będzie traktowany przez encję jako operacja wstawiania. Jeśli w tabeli podstawowej istnieje rekord, wstawienie nie powiedzie się. Zaleca się przetestowanie tego przypadku użycia dla wszystkich scenariuszy przed wdrożeniem w środowisku produkcyjnym.

## <a name="error-1900"></a>Error 1900
Komunikat o błędzie: „Encja: ma następującą liczbę źródeł danych: {}, które nie są śledzone pod celu wychodzącego podwójnego zapisu. Może to wpływać na wydajność zapytań dotyczących synchronizacji na żywo. Zmień model encji w aplikacjach finansowych i operacyjnych, aby usunąć nieużywane źródła danych i tabele, lub zaimplementuj metodę getEntityRecordIdsImpactedByTableChange, aby zoptymalizować zapytania środowiska uruchomieniowego”.

Jeśli istnieje wiele źródeł danych, które nie są używane do śledzenia w ramach rzeczywistej synchronizacji na żywo z aplikacji finansowych i operacyjnych, wydajność encji może wywierać wpływ na synchronizację na żywo. Aby zoptymalizować śledzone tabele, należy użyć metody getEntityRecordIdsImpactedByTableChange.

## <a name="error-5000"></a>Error 5000
Komunikat o błędzie:„ Synchroniczne dodatki plug-in zostały zarejestrowane dla zdarzeń zarządzania danymi dla kont encji. Mogą one wpływać na wydajność importu synchronizacji początkowej i synchronizacji na żywo do usługi Dataverse. Aby uzyskać najlepszą wydajność, zmień dodatki plug-in na przetwarzanie asynchroniczne. Lista zarejestrowanych dodatków plug-in {}”.

Synchroniczne dodatki plug-in w wncji usługi Dataverse mogą wpływać na wydajność synchronizacji na żywo i synchronizacji początkowej, ponieważ zwiększają obciążenie transakcji pracą. Zaleca się wyłączenie dodatków plug-in lub przekształcenie ich w rozwiązania asynchroniczne, jeśli podczas synchronizacji początkowej lub synchronizacji na żywo dla określonej encji ładowanie odbywa się zbyt wolno.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

