---
title: Jednostki tworzenia podróży
description: Ten artykuł zawiera informacje o podmiotach tworzących podróże, które grupują jednostki danych wymagane do utworzenia działającej podróży.
author: yufeihuang
ms.date: 05/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-05-27
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 6234dfa61a5859e2ecaca75594c69c49ba326629
ms.sourcegitcommit: 5b34b41ae74269ba639e2876bc5862ef468da1cc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/15/2022
ms.locfileid: "9167680"
---
# <a name="voyage-creation-entities"></a>Podmioty tworzące podróże

[!include [banner](../includes/banner.md)]

Elementy danych dotyczące tworzenia podróży grupują elementy danych, które są wymagane do utworzenia działającej podróży. Ty lub twój spedytor możecie użyć tych elementów danych do stworzenia rekordów linii podróży, kontenera morskiego, folio i linii podróży, które odnoszą się do istniejących linii zleceń kupna lub transferowych.

## <a name="voyages-itmtableentity"></a>Podróż (ITMTableEntity)

Podróż reprezentuje podróż towarów przychodzących i służy jako najwyższy poziom obszaru kosztów w obszarze Koszt z wyładunkiem. Zawiera informacje na poziomie nagłówka, które dotyczą statku, portu pochodzenia i portu przeznaczenia. Ta funkcjonalność jest obsługiwana przez encję `ITMTableEntity`. Poniższa tabela zawiera listę pól i mapowań, które składają się na tę encję.

| Nazwisko | Mapowanie | Typ danych | Klucz | Wymagana |
|---|---|---|---|---|
| Metoda dostawy | ITMTable.DlvModeId | Nvarchar(10) | Nie | Nie |
| Polecony broker | ITMTable.ITMBrokerAdvised | Data/godzina | Nie | Nie |
| Termin odbiorcy | ITMTable.ITMCustomerAppointment | Data/godzina | Nie | Nie |
| Dostarczono do magazynu | ITMTable.ITMDelAtWarehouse | Data/godzina | Nie | Nie |
| Instrukcje dotyczące dostawy | ITMTable.ITMDeliveryInstructions | Data/godzina | Nie | Nie |
| Data wyjazdu | ITMTable.ITMDepartureDate | Data/godzina | Nie | Nie |
| Zwolnione towary | ITMTable.ITMGoodsReleased | Data/godzina | Nie | Nie |
| Data lokalnego transportu | ITMTable.ITMLocalTransportDate | Data/godzina | Nie | Nie |
| Godzina lokalnego transportu | ITMTable.ITMLocalTransportTime | Liczba całkowita | Nie | Nie |
| Wysłano oryginalny list przewozowy | ITMTable.ITMOriginalBOLSebt | Data/godzina | Nie | Nie |
| Otrzymano oryginalne dokumenty | ITMTable.ITMOriginalDocsReceived | Data/godzina | Nie | Nie |
| Stan zamówienia zakupu | ITMTable.ITMPurchStatus | Liczba całkowita | Nie | Nie |
| Data weryfikacji | ITMTable.ITMVerificationDate | Data/godzina | Nie | Nie |
| Identyfikator wpisu płatności celnych | ITMTable.ShipCustomsEntryId | Nvarchar(20) | Nie | Nie |
| Data wysyłki | ITMTable.ShipDate | Data/godzina | Nie | Nie |
| Opis | ITMTable.ShipDescription | Nvarchar(60) | Nie | Nie |
| Otrzymano dokumenty | ITMTable.ShipDocReceived | Liczba całkowita | Nie | Nie |
| Szacowana data dostawy | ITMTable.ShipEstDlvDate | Data/godzina | Nie | Nie |
| Szacowany czas przybycia w porcie wysyłki | ITMTable.ShipEstPortDate | Data/godzina | Nie | Nie |
| Port źródłowy | ITMTable.ShipFromPort | Nvarchar(20) | Nie | Nie |
| Spedytorski lotniczy list przewozowy/list przewozowy | ITMTable.ShipHAWB | Nvarchar(20) | Nie | Nie |
| Podróż | ITMTable.ShipId | Nvarchar(20) | **Tak** | **Tak** |
| Odwołanie do rezerwacji | ITMTable.ShipIdExternal | Nvarchar(20) | Nie | Nie |
| Szablon podróży | ITMTable.ShipJourwnaId | Nvarchar(20) | Nie | Nie |
| Lokalny spedytor | ITMTable.ShipLocalForwarder | Nvarchar(20) | Nie | Nie |
| Kapitański lotniczy list przewozowy/list przewozowy | ITMTable.ShipMAWB | Nvarchar(20) | Nie | Nie |
| Miara | ITMTable.ShipMeasurement | Numeric(32, 6) | Nie | Nie |
| Jednostka miary | ITMTable.ShipMeasurementUnit | Liczba całkowita | Nie | Nie |
| Liczba palet | ITMTable.ShipNoOfPallets | Liczba całkowita | Nie | Nie |
| Oczekująca podróż | ITMTable.ShipPending | Liczba całkowita | Nie | Nie |
| Uwagi | ITMTable.ShipRemarks | Nvarchar(MAX) | Nie | Nie |
| Wynajem | ITMTable.ShipRental | Liczba całkowita | Nie | Nie |
| Stan podróży | ITMTable.ShipStatusId | Nvarchar(20) | Nie | Nie |
| Kwota w liczbach | ITMTable.ShipTallyInNumber | Nvarchar(20) | Nie | Nie |
| Port docelowy | ITMTable.ShipToPort | Nvarchar(20) | Nie | Nie |
| Data szacowania | ITMTable.ShipValuationDate | Data/godzina | Nie | Nie |
| Firma przewozowa | ITMTable.ShipVendAccount | Nvarchar(20) | Nie | Nie |
| Statek | ITMTable.ShipVesselId | Nvarchar(20) | Nie | **Tak** |
| Identyfikator podróży zewnętrznej | ITMTable.ShipVoyage | Nvarchar(20) | Nie | Nie |

### <a name="number-sequences-for-voyages"></a>Sekwencje liczbowe dla podróży

Wspólna sekwencja numerów dla podróży kontroluje przydzielanie identyfikatorów podróży.

Wartość, która jest przekazywana do encji danych jako **Identyfikator podróży** (`ShipId`), jest używana do identyfikacji istniejącego rekordu do aktualizacji. Jeśli ten rekord nie istnieje, zachowanie zależy od tego, czy przypisana sekwencja numerów jest skonfigurowana tak, by umożliwić ręczne wprowadzanie danych:

- Jeśli włączona jest opcja ręcznego wprowadzania danych, tworzony jest nowy rekord, który wykorzystuje przekazaną wartość.
- Jeśli ręczne wprowadzanie nie jest włączone, zamiast przekazywanej wartości zostanie użyty następny numer w przypisanej sekwencji numerów.

Podczas sesji importu zachowywana jest wartość tymczasowa, która jest importowana jako identyfikator podróży. Zapewnia to, że kontener wysyłkowy i wiersze podróży, które odwołują się do symbolu zastępczego, są uwzględniane w podróży i że są aktualizowane w celu odzwierciedlenia wartości przypisanej z sekwencji numerów.

### <a name="automatic-cost-transactions"></a>Automatyczne transakcje kosztowe

Koszty automatyczne można dodać do podróży ze strony **Koszty automatyczne** w Microsoft Dynamics 365 Supply Chain Management (**Koszt z wyładunkiem \> Ustawienia kalkulacji kosztów \> Koszty automatyczne**). Zapisy dla kosztów automatycznych mogą być także tworzone przy użyciu jednostek danych transakcji kosztowych dla każdego obszaru kosztów, który obsługuje Koszt z wyładunkiem.

Koszty automatyczne, które są skonfigurowane w Supply Chain Management, są stosowane do rejsu, gdy tworzona jest linia rejsu. Żadne koszty nie będą widoczne w rekordzie, dopóki rekord nagłówkowy nie zostanie skojarzony z informacjami o linii.

## <a name="shipping-containers-itmcontainersentity"></a>Kontenery wysyłkowe (ITMContainersEntity)

Kontener przesyłki to fizyczny pojemnik, w którym przewożone są towary. Tym fizycznym pojemnikiem może być kontener towarowy w przypadku frachtu morskiego lub pojedyncza paleta w przypadku frachtu lotniczego. Pojemnik wysyłkowy zawiera informacje na poziomie nagłówka, które są związane z identyfikatorem pojemnika wysyłkowego, numerem plomby i typem pojemnika wysyłkowego. (Typ kontenera wysyłkowego dostarcza informacji o wymiarach.) Ta funkcjonalność jest obsługiwana przez encję `ITMContainersEntity`. Poniższa tabela zawiera listę pól i mapowań, które składają się na tę encję.

| Nazwisko | Mapowanie | Typ danych | Klucz | Wymagana |
|---|---|---|---|---|
| Data wyjazdu | ITMContainers.ITMDepartureDate | Data/godzina | Nie | Nie |
| Data lokalnego transportu | ITMContainers.ITMLocalTransportDate | Data/godzina | Nie | Nie |
| Godzina lokalnego transportu | ITMContainers.ITMLocalTransportTime | Liczba całkowita | Nie | Nie |
| Oryginalna podróż | ITMContainers.OrigShipId | Nvarchar(20) | Nie | Nie |
| Rzeczywista waga | ITMContainers.ShipActualWeight | Numeric(32, 6) | Nie | Nie |
| Polecony broker | ITMContainers.ShipBrokerAdvised | Data/godzina | Nie | Nie |
| Kontener wysyłkowy | ITMContainers.ShipContainerId | Nvarchar(20) | **Tak** | **Tak** |
| Typ kontenera wysyłkowego | ITMContainers.ShipContainerTypeId | Nvarchar(20) | Nie | Nie |
| Typ jednostki | ITMContainers.ShipContainerUnitTypeId | Nvarchar(10) | Nie | Nie |
| Przekonwertowane na wynajem | ITMContainers.ShipConvertedToRental | Liczba całkowita | Nie | Nie |
| Termin odbiorcy | ITMContainers.ShipCustomerAppointment | Data/godzina | Nie | Nie |
| Data wysyłki | ITMContainers.ShipDate | Data/godzina | Nie | Nie |
| Dostarczono do magazynu | ITMContainers.ShipDelAtWarehouse | Data/godzina | Nie | Nie |
| Instrukcje dotyczące dostawy | ITMContainers.ShipDeliveryInstructions | Data/godzina | Nie | Nie |
| Data zastosowania certyfikatu egzaminu | ITMContainers.ShipECAppliedDate | Data/godzina | Nie | Nie |
| Data wygaśnięcia certyfikatu egzaminu | ITMContainers.ShipECExpiryDate | Data/godzina | Nie | Nie |
| Identyfikator certyfikatu egzaminu | ITMContainers.ShipECNum | Nvarchar(20) | Nie | Nie |
| Data otrzymania certyfikatu egzaminu | ITMContainers.ShipECReceivedDate | Data/godzina | Nie | Nie |
| Szacowana data dostawy | ITMContainers.ShipEstDlvDate | Data/godzina | Nie | Nie |
| Szacowany czas przybycia w porcie wysyłki | ITMContainers.ShipEstPortDate | Data/godzina | Nie | Nie |
| Oczekiwana data załadunku | ITMContainers.ShipExpectedLoadingDate | Data/godzina | Nie | Nie |
| Port źródłowy | ITMContainers.ShipFromPort | Nvarchar(20) | Nie | Nie |
| Opis towarów | ITMContainers.ShipGoodsDesc | Nvarchar(60) | Nie | Nie |
| Zwolnione towary | ITMContainers.ShipGoodsReleased | Data/godzina | Nie | Nie |
| Jednostka śledzenia GPS | ITMContainers.ShipGPSUnit | Nvarchar(30) | Nie | Nie |
| Spedytorski lotniczy list przewozowy/list przewozowy | ITMContainers.ShipHAWB | Nvarchar(20) | Nie | Nie |
| Podróż | ITMContainers.ShipId | Nvarchar(20) | **Tak** | **Tak** |
| Szablon podróży | ITMContainers.ShipJourneyId | Nvarchar(20) | Nie | Nie |
| Lokalny spedytor | ITMContainers.ShipLocalForwarder | Nvarchar(20) | Nie | Nie |
| Miara | ITMContainers.ShipMeasurement | Numeric(32, 6) | Nie | Nie |
| Jednostka miary | ITMContainers.ShipMeasurementUnit | Liczba całkowita | Nie | Nie |
| Liczba kartonów | ITMContainers.ShipNoOfCartons | Numeric(32, 6) | Nie | Nie |
| Wysłano oryginalny list przewozowy | ITMContainers.ShipOriginalBOLSebt | Data/godzina | Nie | Nie |
| Otrzymano oryginalne dokumenty | ITMContainers.ShipOriginalDocsReceived | Data/godzina | Nie | Nie |
| Identyfikator naszej plomby | ITMContainers.ShipOurSealNum | Nvarchar(20) | Nie | Nie |
| Wykorzystano | ITMContainers.ShipPendingUsed | Liczba całkowita | Nie | Nie |
| Stan zamówienia zakupu | ITMContainers.ShipPurchStatus | Liczba całkowita | Nie | Nie |
| Typ systemu chłodzenia | ITMContainers.ShipRefrigerationTypeId | Nvarchar(10) | Nie | Nie |
| Uwagi | ITMContainers.ShipRemarks | Nvarchar(MAX) | Nie | Nie |
| Wynajem | ITMContainers.ShipRental | Liczba całkowita | Nie | Nie |
| Z możliwością zwrotu | ITMContainers.ShipReturnable | Liczba całkowita | Nie | Nie |
| Stan podróży | ITMContainers.ShipStatusId | Nvarchar(20) | Nie | Nie |
| Identyfikator plomby firmy przewozowej | ITMContainers.ShipTheirSealNum | Nvarchar(20) | Nie | Nie |
| Port docelowy | ITMContainers.ShipToPort | Nvarchar(20) | Nie | Nie |
| Data weryfikacji | ITMContainers.ShipVerificationDate | Data/godzina | Nie | Nie |
| Statek | ITMContainers.ShipVesselId | Nvarchar(20) | Nie | **Tak** |

### <a name="voyage-id-validation"></a>Weryfikacja identyfikatora podróży

Identyfikator kontenera wysyłkowego nie jest kontrolowany przez sekwencję numerów. Jest wyjątkowy tylko w kontekście podróży, w której jest używany.

Jeśli encja kontenera morskiego (`ITMContainersEntity`) jest używana niezależnie od encji podróży (`ITMTableEntity`), wartość **Identyfikatora podróży** (`ShipId`) musi być zgodna z istniejącym rekordem w tabeli rejsów. W przeciwnym razie import nie powiedzie się.

Jeśli encja kontenera wysyłkowego (`ITMContainersEntity`) i encja podróży (`ITMTableEntity`) są używane jako część tej samej sesji importowej, encja podróży musi poprzedzać utworzenie kontenera wysyłkowego. W przeciwnym razie wartość **Identyfikator podróży** (`ShipId`) nie może zostać pomyślnie zweryfikowana. Jeśli dla wartości **Identyfikator podróży** (`ShipId`) użyto wartości zastępczej, skojarzenie może być utworzone tylko wtedy, gdy ten symbol zastępczy jest użyty jako wartość **Identyfikatora podróży** (`ShipId`) w encji kontenera wysyłkowego.

### <a name="other-field-validations"></a>Inne weryfikacje pól

Poniższa tabela pokazuje pola w tabeli kontenerów wysyłkowych (`ITMContainers`), które są walidowane względem tabel ustawień kosztu z wyładunkiem. Pokazuje również encje danych koszt z wyładunkiem, których spedytor może użyć do odczytania istniejących wartości i upewnienia się, że w twoim środowisku otrzymywane są prawidłowe wartości.

| Pole w tabeli ITMContainers | Jednostka danych koszt wyładunku |
|---|---|
| Typ kontenera wysyłkowego | ITMShippingContainerTypeEntity |
| Opis towarów | ITMGoodsDescriptionEntity |
| Typ systemu chłodzenia | ITMShippingContainerRefrigerationTypeEntity |

## <a name="folios-itmfolioentity"></a>Folio (ITMFolioEntity)

Folio reprezentuje grupę elementów w kontenerze wysyłkowym na potrzeby deklaracji celnych. Folio zawiera informacje na poziomie nagłówka, które są związane z agentem celnym oraz opis towarów. Ta funkcjonalność jest obsługiwana przez encję `ITMFolioEntity`. Poniższa tabela zawiera listę pól i mapowań, które składają się na tę encję.

| Nazwisko | Mapowanie | Typ danych | Klucz | Wymagana |
|---|---|---|---|---|
| Polecony broker | ITMFolioTable.ShipBrokerAdvised | Data/godzina | Nie | Nie |
| Identyfikator kontrolny ładunku | ITMFolioTable.ShipCargoControlNumber | Nvarchar(20) | Nie | Nie |
| Termin odbiorcy | ITMFolioTable.ShipCustomerAppointment | Data/godzina | Nie | Nie |
| Broker urzędu celnego | ITMFolioTable.ShipCustomsBroker | Nvarchar(20) | Nie | Nie |
| Identyfikator płatności celnych | ITMFolioTable.ShipCustomsId | Nvarchar(60) | Nie | Nie |
| Firma | ITMFolioTable.ShipDataArea | Nvarchar(4) | Nie | **Tak** |
| Dostarczono do magazynu | ITMFolioTable.ShipDelAtWarehouse | Data/godzina | Nie | Nie |
| Instrukcje dotyczące dostawy | ITMFolioTable.ShipDeliveryInstructions | Data/godzina | Nie | Nie |
| Otrzymano dokumenty | ITMFolioTable.ShipDocReceived | Liczba całkowita | Nie | Nie |
| Szacowana data dostawy | ITMFolioTable.ShipEstDlvDate | Data/godzina | Nie | Nie |
| Szacowany czas przybycia w porcie wysyłki | ITMFolioTable.ShipEstPortDate | Data/godzina | Nie | Nie |
| Eksporter | ITMFolioTable.ShipExporterId | Nvarchar(20) | Nie | Nie |
| Nazwisko | ITMFolioTable.ShipExporterName | Nvarchar(60) | Nie | Nie |
| Data folio | ITMFolioTable.ShipFolioDate | Data/godzina | Nie | Nie |
| Folio | ITMFolioTable.ShipFolioId | Nvarchar(20) | **Tak** | **Tak** |
| Port źródłowy | ITMFolioTable.ShipFromPort | Nvarchar(20) | Nie | Nie |
| Opis towarów | ITMFolioTable.ShipGoodsDesc | Nvarchar(60) | Nie | Nie |
| Zwolnione towary | ITMFolioTable.ShipGoodsReleased | Data/godzina | Nie | Nie |
| Spedytorski lotniczy list przewozowy/list przewozowy | ITMFolioTable.ShipHAWB | Nvarchar(20) | Nie | Nie |
| Podróż | ITMFolioTable.ShipId | Nvarchar(20) | Nie | **Tak** |
| Miara | ITMFolioTable.ShipMeasurement | Numeric(32, 6) | Nie | Nie |
| Jednostka miary | ITMFolioTable.ShipMeasurementUnit | Liczba całkowita | Nie | Nie |
| Liczba kartonów | ITMFolioTable.ShipNoOfCartons | Numeric(32, 6) | Nie | Nie |
| Wysłano oryginalny list przewozowy | ITMFolioTable.ShipOriginalBOLSebt | Data/godzina | Nie | Nie |
| Otrzymano oryginalne dokumenty | ITMFolioTable.ShipOriginalDocsReceived | Data/godzina | Nie | Nie |
| Stan zamówienia zakupu | ITMFolioTable.ShipPurchStatus | Liczba całkowita | Nie | Nie |
| Uwagi | ITMFolioTable.ShipRemarks | Nvarchar(MAX) | Nie | Nie |
| Stan podróży | ITMFolioTable.ShipStatusId | Nvarchar(20) | Nie | Nie |
| Kod taryfy | ITMFolioTable.ShipTariffCode | Nvarchar(10) | Nie | Nie |
| Port docelowy | ITMFolioTable.ShipToPort | Nvarchar(20) | Nie | Nie |
| Data szacowania | ITMFolioTable.ShipValuationDate | Data/godzina | Nie | Nie |
| Data weryfikacji | ITMFolioTable.ShipVerificationDate | Data/godzina | Nie | Nie |
| Konto dostawcy | ITMFolioTable.VendAccount | Nvarchar(20) | Nie | Nie |

### <a name="number-sequences-for-folios"></a>Sekwencje liczbowe dla folio

Sekwencja numerów folio kontroluje przydzielanie identyfikatorów folio.

Wartość, która jest przekazywana do encji danych jako **Identyfikator folio** (`FolioId`), jest używana do identyfikacji istniejącego rekordu do aktualizacji. Jeśli ten rekord nie istnieje, zachowanie zależy od tego, czy przypisana sekwencja numerów jest skonfigurowana tak, by umożliwić ręczne wprowadzanie danych:

- Jeśli włączona jest opcja ręcznego wprowadzania danych, tworzony jest nowy rekord, który wykorzystuje przekazaną wartość.
- Jeśli ręczne wprowadzanie nie jest włączone, zamiast przekazywanej wartości zostanie użyty następny numer w przypisanej sekwencji numerów.

Podczas sesji importu zachowywana jest wartość tymczasowa, która jest importowana jako identyfikator folio. Takie zachowanie zapewnia, że linie podróży, które odwołują się do tego miejsca, są poprawnie skojarzone i że są one aktualizowane tak, by odzwierciedlały wartość przypisaną z sekwencji numerów.

### <a name="field-validations"></a>Weryfikacje pola

Pole **Opis towaru** w tabeli folio (`ITMFolioTable`) jest weryfikowane względem tabeli konfiguracja kosztu z wyładunkiem o tej samej nazwie. Spedytor może użyć encji danych `ITMGoodsDescriptionEntity` koszt z wyładunkiem, aby odczytać istniejące wartości i upewnić się, że w twoim środowisku otrzymywane są prawidłowe wartości.

## <a name="voyage-lines-for-purchase-orders-itmpurchaselineentity"></a>Wiersze podróży dla zamówień zakupu (ITMPurchaseLineEntity)

Wiersz podróży reprezentuje pojedynczy wiersz zamówienia zakupu, który jest uwzględniona w podróży. Zależność ta jest ustalana poprzez pola **Numer zamówienia zakupu** i **Numer wiersza zakupu**. Linia rejsu odwołuje się do każdego poprzedniego rekordu, który został utworzony dla danej podróży, kontenera wysyłkowego i folio. Ta funkcjonalność jest obsługiwana przez encję `ITMPurchaseLineEntity`. Poniższa tabela zawiera listę pól i mapowań, które składają się na tę encję.

| Nazwisko | Mapowanie | Typ danych | Klucz | Wymagana |
|---|---|---|---|---|
| Waluta | ITMLine.CurrencyCode | Nvarchar(3) | Nie | Nie |
| Kwota netto | ITMLine.LineAmountMST | Numeric(32, 6) | Nie | Nie |
| Numer wiersza zakupu | ITMLine.RefRecId | Numeric(32, 6) | **Tak** | Nie |
| Kontener wysyłkowy | ITMLine.ShipContainerId | Liczba całkowita | Nie | Nie |
| Firma | ITMLine.ShipDataArea | Nvarchar(20) | **Tak** | Nie |
| Zadeklarowana ilość | ITMLine.ShipDeclaredQty | Nvarchar(4) | Nie | Nie |
| Folio | ITMLine.ShipFolioId | Numeric(32, 6) | Nie | Nie |
| Podróż | ITMLine.ShipId | Nvarchar(20) | **Tak** | Nie |
| Numer towaru | ITMLine.ShipItemId | Nvarchar(20) | Nie | Nie |
| Miara | ITMLine.ShipMeasurement | Nvarchar(20) | Nie | Nie |
| Jednostka miary | ITMLine.ShipMeasurementUnit | Numeric(32, 6) | Nie | Nie |
| Liczba kartonów | ITMLine.ShipNoOfCartons | Liczba całkowita | Nie | Nie |
| Pozycja | ITMLine.ShipPosition | Numeric(32, 6) | Nie | Nie |
| Ilość | ITMLine.ShipQty | Liczba całkowita | Nie | Nie |
| Numer zamówienia zakupu | ITMLine.TransRefId | Numeric(32, 6) | **Tak** | Nie |
| Jednostka | ITMLine.UnitId | Liczba całkowita | Nie | Nie |
| Głośność | ITMLine.Volume | Nvarchar(10) | Nie | Nie |
| Masa | ITMLine.Weight | Numeric(32, 6) | Nie | Nie |

## <a name="voyage-lines-for-transfer-orders-itmtransferlineentity"></a>Wiersze podróży dla zleceń transferu (ITMTransferLineEntity)

Wiersz podróży reprezentuje pojedynczy wiersz zamówienia transferu, który jest uwzględniona w podróży. Zależność ta jest ustalana poprzez pola **Numer zamówienia transferu** i **Numer wiersza transferu**. Linia rejsu odwołuje się do każdego poprzedniego rekordu, który został utworzony dla danej podróży, kontenera wysyłkowego i folio. Ta funkcjonalność jest obsługiwana przez encję `ITMTransferLineEntity`. Poniższa tabela zawiera listę pól i mapowań, które składają się na tę encję.

| Nazwisko | Mapowanie | Typ danych | Klucz | Wymagana |
|---|---|---|---|---|
| Waluta | ITMLine.CurrencyCode | Nvarchar(3) | Nie | Nie |
| Kwota netto | ITMLine.LineAmountMST | Numeric(32, 6) | Nie | Nie |
| Kontener wysyłkowy | ITMLine.ShipContainerId | Liczba całkowita | Nie | Nie |
| Firma | ITMLine.ShipDataArea | Nvarchar(20) | **Tak** | Nie |
| Zadeklarowana ilość | ITMLine.ShipDeclaredQty | Nvarchar(4) | Nie | Nie |
| Folio | ITMLine.ShipFolioId | Numeric(32, 6) | Nie | Nie |
| Podróż | ITMLine.ShipId | Nvarchar(20) | **Tak** | Nie |
| Numer towaru | ITMLine.ShipItemId | Nvarchar(20) | Nie | Nie |
| Miara | ITMLine.ShipMeasurement | Nvarchar(20) | Nie | Nie |
| Jednostka miary | ITMLine.ShipMeasurementUnit | Numeric(32, 6) | Nie | Nie |
| Liczba kartonów | ITMLine.ShipNoOfCartons | Liczba całkowita | Nie | Nie |
| Pozycja | ITMLine.ShipPosition | Numeric(32, 6) | Nie | Nie |
| Ilość | ITMLine.ShipQty | Liczba całkowita | Nie | Nie |
| Numer wiersza przeniesienia | ITMLine.TransferLineNumber | Numeric(32, 6) | **Tak** | Nie |
| Numer zamówienia przeniesienia | ITMLine.TransRefId | Numeric(32, 6) | **Tak** | Nie |
| Jednostka | ITMLine.UnitId | Liczba całkowita | Nie | Nie |
| Głośność | ITMLine.Volume | Nvarchar(10) | Nie | Nie |
| Masa | ITMLine.Weight | Numeric(32, 6) | Nie | Nie |

### <a name="reference-table"></a>Tabela odwołań

Wiersze podróży są tworzone przez skojarzenie z otwartym wierszem zamówienia przychodzącego. Ten wiersz może znajdować się na zleceniu zakupu lub może być transakcją odbiorczą na zleceniu transferu. Pole `RefTableId` w tabeli linii rejsu (`ITMLine`) określa, z jakim typem zamówienia związana jest dana linia poprzez odniesienie do numeru tabeli. Jeśli w tabeli, w której tworzone są dane, znajdują się określone numery tabel, encje są dzielone na podstawie tych wartości.

Wartości dla tabeli referencyjnej (`RefTableId`) i typu transakcji (`TransType`) są niejawne przy wyborze encji wiersza zakupu Koszt z wyładunkiem lub jednostki Wiersz przeniesienia kosztu z wyładunkiem.

### <a name="validation"></a>Walidacja

Wiersz podróży odwołuje się bezpośrednio do rekordu podróży, rekordu kontenera wysyłkowego i rekordu folio. Jeśli encja wiersza zakupu (`ITMPurchaseLinesEntity`) lub encja wiersza transferu (`ITMPurchaseLinesEntity`) jest używana niezależnie od encji używanych do tworzenia tych rekordów referencyjnych, wartości **Identyfikatora podróży** (`ShipId`), **Kontenera wysyłkowego** (`ShipContainerId`) i **Folio** (`ShipFolioId`) muszą być zgodne z istniejącym rekordem w odpowiednich tabelach. W przeciwnym razie import nie powiedzie się.

Jeśli którykolwiek z tych wierszy jest używany w ramach tej samej sesji importowej, te inne encje muszą poprzedzać utworzenie wiersza podróży. W przeciwnym razie wartości nie będą mogły zostać pomyślnie zwalidowane. Jeśli dla numeru podróży lub folio użyto wartości zastępczej, skojarzenie może być utworzone tylko wtedy, gdy ta sama wartość jest użyta dla numeru podróży lub folio w encji wiersza podróży.

Jeśli linia zlecenia zakupu lub zlecenia transferu jest już przypisana do istniejącego wiersza podróży, nowy wiersz nie zostanie utworzony. Zanim wiersz zamówienia może zostać przypisany do nowej podróży, musi zostać usunięty z bieżącej.

### <a name="order-line-identification"></a>Identyfikacja wiersza zamówienia

Linie rejsu odwołują się bezpośrednio do referencyjnych wartości **Identyfikator rekordu** (`RefRecId`), **Identyfikator wymiaru zapasów** (`InventDimId`) i **Identyfikator transakcji zapasów** (`InventTransId`). Wartości te nie muszą już być uwzględniane podczas używania encji danych. Zamiast tego musi być dołączony numer wiersza zamówienia. Numer wiersza zamówienia i numer zamówienia umożliwiają identyfikowanie każdej z tych wartości odwołania.

### <a name="voyage-line-quantity"></a>Wiersz podróży, ilość

Ponieważ linia rejsu jest bezpośrednio związana z linią zamówienia, wartość **ilości** (`ShipQty`), która jest wprowadzana przy użyciu encji, wymaga, by wartości te były zgodne. Walidacja jest przeprowadzana dla ilości z wiersza zamówienia lub wiersza transferu. Jeśli walidacja nie powiedzie się, rekord nie zostanie przetworzony.

### <a name="calculated-fields"></a>Pola obliczeniowe

Pola obliczeniowe **Waga** i **Objętość** przyjmują wartości otrzymane przez jednostkę danych. Jeśli nie podano żadnych wartości, do aktualizacji tych pól zostaną użyte wartości systemowe, o ile są one dostępne. W przypadku kosztu z wyładunkiem wartości są obliczane w następujący sposób:

- *Waga* = *ilość* × *waga brutto elementu*
- *Objętość* = *ilość* × (*głębokość brutto elementu* × *wysokość brutto elementu* × *szerokość brutto elementu*)

## <a name="sequencing"></a>Harmonogram

Ze względu na zależności między tabelami, rekord podróży musi być utworzony jako pierwszy. Wiersz podróży można utworzyć dopiero po utworzeniu podróży, kontenera wysyłkowego i folio.

Aby utworzyć podróż bez ostrzeżeń o walidacji, system musi przetworzyć encje w następującej kolejności:

1. Podróże (`ITMTableEntity`)
1. Kontenery wysyłkowe (`ITMContainersEntity`)
1. Folio (`ITMFolioTableEntity`)
1. Wiersze podróży (`ITMPurchaseLinesEntity` lub `ITMTransferLinesEntity`)
