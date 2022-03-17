---
title: Integracja z systemami wykonywania produkcji innych firm
description: W tym temacie wyjaśniono, jak zintegrować Microsoft Dynamics 365 Supply Chain Management z systemem realizacji produkcji (MES) innej firmy.
author: t-benebo
ms.date: 10/01/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-10-01
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 8917c9b265bc3df19517f052e28fb7644057cb46
ms.sourcegitcommit: 19f0e69a131e9e4ff680eac13efa51b04ad55a38
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/22/2022
ms.locfileid: "8330708"
---
# <a name="integrate-with-third-party-manufacturing-execution-systems"></a>Integracja z systemami wykonywania produkcji innych firm

[!include [banner](../includes/banner.md)]

Niektóre organizacje produkcyjne korzystające z Microsoft Dynamics 365 Supply Chain Management używają natywnej funkcji Dynamics 365 do kontrolowania swoich działań produkcyjnych dotyczących maszyn, sprzętu i personelu. Jednak inne organizacje produkcyjne, zwłaszcza te, które mają zaawansowane wymagania produkcyjne, używają zamiast tego systemu realizacji produkcji innej firmy (MES). Organizacje mogą wybrać rozwiązanie MES innej firmy, ponieważ na przykład jest ono specjalnie dostosowane do ich branży.

W zintegrowanym rozwiązaniu wymiana danych jest w pełni automatyczna i odbywa się w najbliższym czasie rzeczywistym. Dlatego dane są przechowywane w obu systemach i nie jest wymagane ręczne wprowadzanie danych. Na przykład podczas rejestrowania zużycia materiałów w systemie MES integracja zapewnia, że to samo zużycie jest także rejestrowane w systemie Dynamics 365. Z tego względu aktualne rekordy zapasów są dostępne dla innych ważnych procesów, takich jak planowanie i sprzedaż.

Dzięki temu łatwiejsze i tańsze rozwiązanie ułatwia użytkownikom Supply Chain Management integrację z usługami MES innych firm. Oferuje następujące funkcje:

- Zdarzenia biznesowe i interfejsy obsługi [kluczowych procesów wytwarzania](#processes-available-for-mes-integration)
- Scentralizowany pulpit nawigacyjny, w którym można śledzić historię przetwarzania zdarzeń oraz rozwiązywać problemy i naprawiać procesy, które nie powiodły się

Na poniższej ilustracji przedstawiono typowy zbiór zdarzeń biznesowych, procesów i komunikatów wymienianych w zintegrowanym rozwiązaniu.

![Typowy scenariusz integracji.](media/3p-mes-scenario.png "Typowy scenariusz integracji.")

## <a name="turn-on-the-mes-integration-feature"></a>Włącz funkcję integracji MES

Zanim będziesz mógł korzystać z tej funkcji, administrator musi ją włączyć w twoim systemie w sposób opisany w poniższej procedurze.

1. Wybierz kolejno opcje **Administrowanie systemem \> Ustawienia \> Konfiguracja licencji**.
1. Upewnij się, że klucz licencyjny **Czas i obecność** jest włączony (ma zaznaczoną opcję). Ten klucz licencyjny jest wymagany, ponieważ kontroluje on funkcjonalność i dane systemu wykonawczego produkcji. Jeśli nie jest ona włączona, wykonaj następujące kroki:
    1. Ustaw system w trybie konserwacji, jak to opisano w sekcji [Tryb konserwacji](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
    1. Na stronie **Konfiguracja licencji** zaznacz pole wyboru **Czas i obecność**.
    1. Wyłącz tryb konserwacji, jak to opisano w sekcji [Tryb konserwacji](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md)
1. Wybierz kolejno opcje **Administrator systemu \> Obszary robocze \> Zarządzanie funkcjami**.
1. Włącz funkcję, która jest wymieniona w następujący sposób (zobacz też [Zarządzanie cechami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)):
    - **Moduł:** *Kontrola produkcji*
    - **Nazwa funkcji:** *integracja systemu w systemie realizacji produkcji*

## <a name="processes-available-for-mes-integration"></a>Procesy dostępne dla integracji MES

Można włączyć dowolny z następujących procesów integracji.

| Nazwa procesu | Opis |
|---|---|
| Zwalnianie zdarzeń biznesowych dla zleceń produkcyjnych i stanu zlecenia produkcyjnego | Ten proces jest zdarzeniem biznesowym, na które może nasłuchiwać program MES, w celu uzyskania informacji o zleceniach produkcyjnych, które powinny zostać wyprodukowane. Dane referencyjne powiązane ze zleceniem produkcyjnym powinny zostać udostępnione z Supply Chain Management do systemu MES za pośrednictwem protokołu Open Data Protocol (OData) lub jednostek danych. |
| Rozpocznij zlecenie produkcyjne | Ten proces dostarcza działowi Supply Chain Management informacji o zleceniach produkcyjnych, które są uruchamiane przy użyciu systemu MES. Zapewnia to, że oba systemy mają aktualny widok wszystkich działań produkcyjnych. |
| Zgłoś ilość wyprodukowaną lub odpadki | Ten proces dostarcza działowi Supply Chain Management informacji o ilościach towarów i błędów zgłoszonych w zadaniu produkcyjnym za pomocą systemu MES. Zapewnia to, że kierownicy hali produkcyjnej mają aktualny wgląd w postęp planu produkcji. |
| Zgłoś zużycie materiałów | Proces ten dostarcza działowi Supply Chain Management informacji z systemu MES o ilości zużywanych materiałów. Udostępnia aktualne ewidencje zapasów dla innych ważnych procesów, takich jak planowanie i sprzedaż. |
| Zgłoś czas zużyty na operację | Ten proces dostarcza działowi Supply Chain Management informacji o czasie używanym do wykonania określonej operacji. |
| Kończenie zlecenia produkcyjnego | Ten proces informuje Supply Chain Management, że system MES zaktualizował zlecenie produkcyjne do ostatecznego statusu *Zakończone*. Ten stan wskazuje, że dla tego zlecenia produkcyjnego nie zostanie wyprodukowana więcej ilości. |

## <a name="monitor-incoming-messages"></a>Monitorowanie komunikatów przychodzących

Aby monitorować wiadomości przychodzące do systemu, otwórz stronę **integracji systemów realizacji produkcji**. Można tam wyświetlać, przetwarzać i rozwiązywać problemy.

## <a name="call-the-api"></a>Wywołaj interfejs API

Aby wywołać interfejs API integracji MES, wyślij żądanie `POST` do następującego adresu URL punktu końcowego:

`/api/services/SysMessageServices/SysMessageService/SendMessage`

Treść wysyłanych żądań powinna przypominać poniższy przykład. Zamień wartości dla `_companyId`, `_messageType` i `_messageContent` w razie potrzeby. Aby uzyskać informacje dotyczące różnych typów wiadomości, które obsługuje interfejs API, oraz sposobu projektowania ich zawartości, zobacz następną sekcję.

```json
{
    "_companyId": "USMF",
    "_messageQueue": "JmgMES3P",
    "_messageType": "ProdProductionOrderReportFinished",
    "_messageContent":
    "{\"ProductionOrderNumber\": \"P000123\", \"ReportFinishedLines\": [{\"ItemNumber\": \"A0001\", \"ReportedGoodQuantity\": 10, \"ReportAsFinishedDate\": \"2021-01-01\"}]}"
}
```

## <a name="api-message-types-and-content"></a>Typy i zawartość komunikatów API

W tej sekcji opisano każdy typ wiadomości, który można wymieniać za pośrednictwem interfejsu API integracji MES.

### <a name="start-production-order-message"></a>Komunikat o uruchomieniu zlecenia produkcyjnego

W *komunikacie o rozpoczęciu zlecenia produkcyjnego* wartość `_messageType` to `ProdProductionOrderStart`. W poniższej tabeli przedstawiono pola, które obsługuje ta wiadomość.

| Nazwa pola | Stan | Typ |
|---|---|---|
| `ProductionOrderNumber` | Wymagana | Ciąg |
| `StartedQuantity` | Opcjonalnie | Rzeczywisty |
| `StartedDate` | Opcjonalnie | Data |
| `AutomaticBOMConsumptionRule` | Opcjonalnie | Enum (FlushingPrincip \| Always \| Never) |

### <a name="report-as-finished-message"></a>Zgłoś jako gotową wiadomość

W przypadku *komunikatu gotowego* wartość `_messageType` to `ProdProductionOrderReportFinished`. W poniższej tabeli przedstawiono pola, które obsługuje ta wiadomość.

| Nazwa pola | Stan | Typ |
|---|---|---|
| `ProductionOrderNumber` | Wymagana | Ciąg |
| `ReportFinishedLines` | Wymagana | Lista wierszy (przynajmniej jedna), z których każda zawiera ładunek opisany w następnej tabeli |

W poniższej tabeli przedstawiono pola, które obsługuje każdy wiersz w sekcji `ReportFinishedLines` komunikatu `ProdProductionOrderReportFinished`.

| Nazwa pola | Stan | Typ |
|---|---|---|
| `LineNumber` | Opcjonalnie | Rzeczywisty |
| `ItemNumber` | Opcjonalnie | Ciąg|
| `ProductionType` | Opcjonalnie | Enum (MainItem \| Formula \| BOM \| Co_Product \| By_Product \| None), extensible |
| `ReportedErrorQuantity` | Opcjonalnie | Rzeczywisty|
| `ReportedGoodQuantity` | Opcjonalnie | Rzeczywisty|
| `ReportedErrorCatchWeightQuantity` | Opcjonalnie | Rzeczywisty |
| `ReportedGoodCatchWeightQuantity` | Opcjonalnie | Rzeczywisty |
| `AcceptError` | Opcjonalnie |Wartość logiczna |
| `ErrorCause` | Opcjonalnie | Enum (None \| Material \| Machine \| OperatingStaff), extensible |
| `ExecutedDateTime` | Opcjonalnie | Data/godzina |
| `ReportAsFinishedDate` | Opcjonalnie | Data |
| `AutomaticBOMConsumptionRule` | Opcjonalnie | Enum (FlushingPrincip \| Always \| Never) |
| `AutomaticRouteConsumptionRule` | Opcjonalnie |Enum (RouteDependent \| Always \| Never) |
| `RespectFlushingPrincipleDuringOverproduction` | Opcjonalnie | Wartość logiczna |
| `ProductionJournalNameId` | Opcjonalnie | Ciąg |
| `PickingListProductionJournalNameId` | Opcjonalnie | Ciąg|
| `RouteCardProductionJournalNameId` | Opcjonalnie | Ciąg |
| `FromOperationNumber` | Opcjonalnie | Wartość całkowita|
| `ToOperationNumber` | Opcjonalnie | Wartość całkowita|
| `InventoryLotId` | Opcjonalnie | Ciąg |
| `BaseValue` | Opcjonalnie | Ciąg |
| `EndJob` | Opcjonalnie | Wartość logiczna |
| `EndPickingList` | Opcjonalnie | Wartość logiczna |
| `EndRouteCard` | Opcjonalnie | Wartość logiczna |
| `PostNow` | Opcjonalnie | Wartość logiczna |
| `AutoUpdate` | Opcjonalnie | Wartość logiczna |
| `ProductColorId` | Opcjonalnie | Ciąg|
| `ProductConfigurationId` | Opcjonalnie | Ciąg |
| `ProductSizeId` | Opcjonalnie | Ciąg |
| `ProductStyleId` | Opcjonalnie | Ciąg |
| `ProductVersionId` | Opcjonalnie | Ciąg |
| `ItemBatchNumber` | Opcjonalnie | Ciąg |
| `ProductSerialNumber` | Opcjonalnie | Ciąg |
| `LicensePlateNumber` | Opcjonalnie | Ciąg |
| `InventoryStatusId` | Opcjonalnie | Ciąg |
| `ProductionWarehouseId` | Opcjonalnie | Ciąg |
| `ProductionSiteId` | Opcjonalnie | Ciąg |
| `ProductionWarehouseLocationId` | Opcjonalnie | Ciąg |
| Od `InventoryDimension1` do `InventoryDimension12` | Opcjonalnie | Ciąg |

12 rozszerzalnych wymiarów (od `InventoryDimension1` do `InventoryDimension12`) wymaga dostosowania i nie zawsze są używane. Aby uzyskać więcej informacji o tych wymiarach, zobacz temat [Dodawanie nowych wymiarów magazynowych za pomocą rozszerzenia](../../fin-ops-core/dev-itpro/extensibility/inventory-dimensions.md).

### <a name="material-consumption-picking-list-message"></a>Komunikat zużycia materiału (lista pobrania)

W przypadku *komunikatu o zużyciu materiału (lista pobrania)* wartość `_messageType` wynosi `ProdProductionOrderPickingList`. W poniższej tabeli przedstawiono pola, które obsługuje ta wiadomość.

| Nazwa pola | Stan | Typ |
|---|---|---|
| `ProductionOrderNumber` | Wymagana | Ciąg |
| `JournalNameId` | Opcjonalnie | Ciąg |
| `PickingListLines` | Wymagana | Lista wierszy (przynajmniej jedna), z których każda zawiera ładunek opisany w następnej tabeli |

W poniższej tabeli przedstawiono pola, które obsługuje każdy wiersz w sekcji `PickingListLines` komunikatu `ProdProductionOrderPickingList`.

| Nazwa pola | Stan | Typ |
|---|---|---|
| `ItemNumber` | Wymagana | Ciąg |
| `ConsumptionBOMQuantity` | Opcjonalnie | Rzeczywisty |
| `ProposalBOMQuantity` | Opcjonalnie | Rzeczywisty |
| `ScrapBOMQuantity` | Opcjonalnie | Rzeczywisty |
| `BOMUnitSymbol` | Opcjonalnie | Ciąg |
| `ConsumptionInventoryQuantity` | Opcjonalnie | Rzeczywisty |
| `ProposalInventoryQuantity` | Opcjonalnie | Rzeczywisty |
| `ConsumptionCatchWeightQuantity` | Opcjonalnie | Rzeczywisty |
| `ProposalCatchWeightQuantity` | Opcjonalnie | Rzeczywisty |
| `ConsumptionDate` | Opcjonalnie | Data |
| `OperationNumber` | Opcjonalnie | Wartość całkowita |
| `LineNumber` | Opcjonalnie | Rzeczywisty |
| `PositionNumber` | Opcjonalnie | Ciąg |
| `IsConsumptionEnded` | Opcjonalnie | Wartość logiczna |
| `ErrorCause` | Opcjonalnie | Enum (None \| Material \| Machine \| OperatingStaff), extensible |
| `InventoryLotId` | Opcjonalnie | Ciąg |

### <a name="time-used-for-operation-route-card-message"></a>Czas używany dla komunikatu operacji (karta marszruty)

Dla czasu *używanego dla komunikatu operacji (karta marszruty)* wartość `_messageType` wynosi `ProdProductionOrderRouteCard`. W poniższej tabeli przedstawiono pola, które obsługuje ta wiadomość.

| Nazwa pola | Stan | Typ |
|---|---|---|
| `ProductionOrderNumber` | Wymagana | Ciąg |
| `JournalNameId` | Opcjonalnie | Ciąg |
| `RouteCardLines` | Wymagana | Lista wierszy (przynajmniej jedna), z których każda zawiera ładunek opisany w następnej tabeli |

W poniższej tabeli przedstawiono pola, które obsługuje każdy wiersz w sekcji `RouteCardLines` komunikatu `ProdProductionOrderRouteCard`.

| Nazwa pola | Stan | Typ |
|---|---|---|
| `OperationNumber` | Wymagana | Wartość całkowita |
| `OperationPriority` | Opcjonalnie | Enum (Primary \| Secondary1 \| Secondary2 \| ... \| Secondary20) |
| `OperationId` | Opcjonalnie | Ciąg |
| `OperationsResourceId` | Opcjonalnie | Ciąg |
| `Worker` | Opcjonalnie | Ciąg |
| `HoursRouteCostCategoryId` | Opcjonalnie | Ciąg |
| `QuantityRouteCostCategoryId` | Opcjonalnie | Ciąg |
| `HourlyRate` | Opcjonalnie | Rzeczywisty |
| `Hours` | Opcjonalnie | Rzeczywisty |
| `GoodQuantity` | Opcjonalnie | Rzeczywisty |
| `ErrorQuantity` | Opcjonalnie | Rzeczywisty |
| `CatchWeightGoodQuantity` | Opcjonalnie | Rzeczywisty |
| `CatchWeightErrorQuantity` | Opcjonalnie | Rzeczywisty |
| `QuantityPrice` | Opcjonalnie | Rzeczywisty |
| `ProcessingPercentage` | Opcjonalnie | Rzeczywisty |
| `ConsumptionDate` | Opcjonalnie | Data |
| `TaskType` | Opcjonalnie | Enum (QueueBefore \| Setup \| Process \| Overlap \| Transport \| QueueAfter \| Burden) |
| `ErrorCause` | Opcjonalnie | Enum (None \| Material \| Machine \| OperatingStaff), extensible |
| `OperationCompleted` | Opcjonalnie | Wartość logiczna |
| `BOMConsumption` | Opcjonalnie | Wartość logiczna |
| `ReportAsFinished` | Opcjonalnie | Wartość logiczna |

### <a name="end-production-order-message"></a>Komunikat o zakończeniu zlecenia produkcyjnego

W *zakończ zlecenie produkcyjne* wartość `_messageType` to `ProdProductionOrderEnd`. W poniższej tabeli przedstawiono pola, które obsługuje ta wiadomość.

| Nazwa pola | Stan | Typ |
|---|---|---|
| `ProductionOrderNumber` | Wymagana | Ciąg |
| `ExecutedDateTime` | Opcjonalnie | Data/godzina |
| `EndedDate` | Opcjonalnie | Data |
| `UseTimeAndAttendanceCost` | Opcjonalnie | Wartość logiczna |
| `AutoReportAsFinished` | Opcjonalnie | Wartość logiczna |
| `AutoUpdate` | Opcjonalnie | Wartość logiczna |

## <a name="receive-feedback-about-the-state-of-a-message"></a>Otrzymywanie informacji zwrotnych o stanie wiadomości

Po wysłaniu przez system MES wiadomości do Supply Chain Management może być istotne, aby dział zarządzania łańcuchem dostaw zwrócił informację zwrotną o stanie wiadomości. Oto kilka przykładów przypadków, w których to zachowanie może mieć znaczenie:

- Nie ma osoby, która byłaby odpowiedzialna za stały nadzór nad integracją MES.
- Osoba odpowiedzialna za nadzór nad integracją MES chce być powiadamiana e-mailem o niepowodzeniu wiadomości, aby wiedziała, że musi podjąć działania.
- W programie MES musi zostać wyświetlony komunikat o błędzie, aby poinformować operatora wydziału lub dział IT o tym, że muszą podjąć akcję.
- MES musi ponownie obliczyć harmonogram zamówień po otrzymaniu komunikatu o niepowodzeniu (na przykład z powodu niepowodzenia uruchomienia zlecenia produkcyjnego).

W takich przypadkach można skorzystać ze standardowej funkcji alertu w Supply Chain Management. Aby uzyskać informacje na temat działania standardowych alertów, zobacz następujące zasoby:

- Temat Pomocy: [Omówienie alertów](../../fin-ops-core/fin-ops/get-started/alerts-overview.md)
- Wideo: [Opcje reguł alertów w Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=cpzimwOjicM&ab_channel=MicrosoftDynamics365)

Na przykład można skonfigurować następujące alerty w celu podania informacji zwrotnych o stanie wiadomości:

- Utwórz zdarzenie biznesowe („Wyślij z zewnątrz”) używane w przypadku komunikatu *Niepowodzenie*.
- Wyślij powiadomienie i wiadomość e-mail do administratora IT lub kierownika ds. produkcji.
