---
title: Encje transakcji kosztowych
description: Ten temat dostarcza informacji o encjach transakcji kosztowych, które umożliwiają podział wartości kosztu pomiędzy zawartość obszaru kosztów poprzez wybór metody podziału.
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
ms.openlocfilehash: 41a9525cb766907b7de97f1e856a3b640d7718ac
ms.sourcegitcommit: 611202adaa080250636efabb3b3b32b850d92d04
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/28/2022
ms.locfileid: "8813107"
---
# <a name="cost-transaction-entities"></a>Encje transakcji kosztowych

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until GA with 10.0.28 -->

## <a name="apportionment"></a>Przydział

Koszt wyładunku umożliwia podział wartości kosztu pomiędzy zawartość obszaru kosztów (podróż, kontener morski itd.) poprzez wybór metody podziału. Metoda podziału jest ustawiana w ramach konfiguracji kosztów automatycznych, która jest oparta na regułach biznesowych. Jest on uwzględniany jako część kosztów, gdy tworzona jest linia podróży.

### <a name="configure-the-apportionment-mapping-for-use-with-data-entities"></a>Skonfiguruj mapowanie aportu do użycia z encjami danych

Kiedy koszt jest tworzony z zewnętrznego źródła, takiego jak spedytor, to zewnętrzne źródło nie może określić preferowanej metody podziału wartości kosztu. Mapowanie podziału definiuje domyślną metodę podziału dla każdego kodu rodzaju kosztu. Dostęp do tabeli odwzorowania aportu można uzyskać na stronie **Odwzorowanie podziału** w Microsoft Dynamics 365 Supply Chain Management (**Koszt wyładunku \> Konfiguracja kosztu \> Mapowanie przydziału**).

Jeśli zdefiniowano kombinację odwzorowującą, a koszt pasujący do kodu rodzaju kosztu jest tworzony za pomocą podmiotu transakcji kosztowej, odwzorowana metoda podziału zostanie użyta zamiast wartości, która została przekazana podmiotowi.

Jeśli w tabeli odwzorowania nie ma żadnej wartości, ale wartość została dostarczona do encji, zostanie ona użyta.

Jeśli żadna wartość nie istnieje ani w tabeli odwzorowania, ani w rekordzie, który został przesłany do encji, tworzenie nie powiedzie się.

### <a name="apportionment-mapping-itmapportionmentmapping"></a>Odwzorowanie podziału (ITMApportionmentMapping)

Podmiot odwzorowujący podział (`ITMApportionmentMapping`) tworzy relacje odwzorowujące podział i umożliwia użytkownikom tworzenie lub aktualizowanie rekordów.

| Nazwisko | Mapowanie | Typ danych | Klucz | Wymagana |
|---|---|---|---|---|
| Metoda przydziału | ITMApportionmentMapping.ApportionmentMethod | Liczba całkowita | Nie | Nie |
| Kod typu kosztu | ITMApportionmentMapping.ShipCostTypeId | Nvarchar(20) | **Tak** | Nie |

## <a name="voyage-costs-itmcosttransvoyageentity"></a>Koszty podróży (ITMCostTransVoyageEntity)

Encja kosztu podróży (`ITMCostTransVoyageEntity`) tworzy transakcje kosztowe podróży, które są stosowane na poziomie podróży. Podczas procesu importu system używa wartości **Kategoria** i **Metoda podziału**, które są zawarte w encji, aby określić, w jaki sposób wartość kosztu jest rozdzielana na zawartość rejsu.

| Nazwisko | Mapowanie | Typ danych | Klucz | Wymagana |
|---|---|---|---|---|
| Metoda przydziału | ITMCostTrans.ApportionmentMethod | Liczba całkowita | Nie | Nie |
| Wartość kosztowa | ITMCostTrans.CostValue | Numeric(32, 6) | Nie | Nie |
| Waluta | ITMCostTrans.CurrencyCode | Nvarchar(3) | Nie | **Tak** |
| Numer wiersza | ITMCostTrans.LineNum | Numeric(32, 16) | **Tak** | Nie |
| Typ kosztu połączonego | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | Nie | Nie |
| Koszt minimalny | ITMCostTrans.MinCostAmount | Numeric(32, 6) | Nie | Nie |
| Kategoria | ITMCostTrans.ShipCostCategory | Liczba całkowita | Nie | Nie |
| Kod typu kosztu | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | Nie | Nie |
| Firma | ITMCostTrans.ShipDataArea | Nvarchar(4) | Nie | **Tak** |
| Podróż | ITMCostTrans.TransRecId | Nvarchar(20) | **Tak** | Nie |
| Grupa podatków dla pozycji | ITMCostTrans.TaxItemGroup | Nvarchar(10) | Nie | Nie |

## <a name="shipping-container-costs-itmcosttransshippingcontainerentity"></a>Koszty kontenera wysyłkowego (ITMCostTransShippingContainerEntity)

Encja Koszt kontenera wysyłkowego (`ITMCostTransShippingContainerEntity`) tworzy koszty kontenerów wysyłkowych, które są stosowane na poziomie kontenera wysyłkowego. Podczas procesu importu system używa wartości **Kategoria** i **Metoda podziału**, które są zawarte w encji, aby określić, w jaki sposób wartość kosztu jest rozdzielana na kontener transportowy.

Pola **Agregacja**, **Odcinek** i **Połączony etap** są specyficzne dla rekordów, w których **Obszar kosztów** ma wartość *Kontener wysyłkowy*. Dlatego nie są one obecne w jednostkach danych dla innych obszarów kosztów.

| Nazwisko | Mapowanie | Typ danych | Klucz | Wymagana |
|---|---|---|---|---|
| Agreguj | ITMCostTrans.AggregatedCost | Liczba całkowita | Nie | Nie |
| Metoda przydziału | ITMCostTrans.ApportionmentMethod | Liczba całkowita | Nie | Nie |
| Wartość kosztowa | ITMCostTrans.CostValue | Numeric(32, 6) | Nie | Nie |
| Waluta | ITMCostTrans.CurrencyCode | Nvarchar(3) | Nie | **Tak** |
| Numer wiersza | ITMCostTrans.LineNum | Numeric(32, 16) | **Tak** | Nie |
| Typ kosztu połączonego | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | Nie | Nie |
| Połączony etap | ITMCostTrans.LinkLegId | Nvarchar(20) | Nie | Nie |
| Koszt minimalny | ITMCostTrans.MinCostAmount | Numeric(32, 6) | Nie | Nie |
| Kontener wysyłkowy | ITMCostTrans.TransRecId | Nvarchar(20) | **Tak** | Nie |
| Kategoria | ITMCostTrans.ShipCostCategory | Liczba całkowita | Nie | Nie |
| Kod typu kosztu | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | Nie | Nie |
| Firma | ITMCostTrans.ShipDataArea | Nvarchar(4) | Nie | **Tak** |
| Podróż | ITMCostTrans.TransRecId | Nvarchar(20) | **Tak** | Nie |
| Etap | ITMCostTrans.ShipLegId | Nvarchar(20) | Nie | Nie |
| Grupa podatków dla pozycji | ITMCostTrans.TaxItemGroup | Nvarchar(10) | Nie | Nie |

## <a name="folio-costs-itmcosttransfolioentity"></a>Koszty folio (ITMCostTransFolioEntity)

Jednostka kosztów folio (`ITMCostTransFolioEntity`) tworzy rekordy transakcji kosztów, które dotyczą poziomu folio. Podczas procesu importu system używa wartości **Kategoria** i **Metoda podziału**, które są zawarte w encji, aby określić, w jaki sposób wartość kosztu jest rozdzielana dla każdego folio.

| Nazwisko | Mapowanie | Typ danych | Klucz | Wymagana |
|---|---|---|---|---|
| Metoda przydziału | ITMCostTrans.ApportionmentMethod | Liczba całkowita | Nie | Nie |
| Wartość kosztowa | ITMCostTrans.CostValue | Numeric(32, 6) | Nie | Nie |
| Waluta | ITMCostTrans.CurrencyCode | Nvarchar(3) | Nie | **Tak** |
| Numer wiersza | ITMCostTrans.LineNum | Numeric(32, 16) | **Tak** | Nie |
| Typ kosztu połączonego | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | Nie | Nie |
| Koszt minimalny | ITMCostTrans.MinCostAmount | Numeric(32, 6) | Nie | Nie |
| Kategoria | ITMCostTrans.ShipCostCategory | Liczba całkowita | Nie | Nie |
| Kod typu kosztu | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | Nie | Nie |
| Firma | ITMCostTrans.ShipDataArea | Nvarchar(4) | Nie | **Tak** |
| Folio | ITMCostTrans.TransRecId | Nvarchar(20) | **Tak** | Nie |
| Grupa podatków dla pozycji | ITMCostTrans.TaxItemGroup | Nvarchar(10) | Nie | Nie |

## <a name="purchase-order-costs-itmcosttranspurchaseentity"></a>Koszty zamówienia zakupu (ITMCostTransPurchaseEntity)

Encja Koszt zamówienia zakupu (`ITMCostTransPurchaseEntity`) tworzy transakcje kosztowe dotyczące nagłówka zamówienia zakupu. Podczas procesu importu system używa wartości **Kategoria** i **Metoda podziału**, które są zawarte w encji, aby określić, w jaki sposób wartość kosztu jest rozdzielana dla każdego folio.

| Nazwisko | Mapowanie | Typ danych | Klucz | Wymagana |
|---|---|---|---|---|
| Metoda przydziału | ITMCostTrans.ApportionmentMethod | Liczba całkowita | Nie | Nie |
| Wartość kosztowa | ITMCostTrans.CostValue | Numeric(32, 6) | Nie | Nie |
| Waluta | ITMCostTrans.CurrencyCode | Nvarchar(3) | Nie | **Tak** |
| Numer wiersza | ITMCostTrans.LineNum | Numeric(32, 16) | **Tak** | Nie |
| Typ kosztu połączonego | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | Nie | Nie |
| Koszt minimalny | ITMCostTrans.MinCostAmount | Numeric(32, 6) | Nie | Nie |
| Zamówienie zakupu | ITMCostTrans.TransRecId | Nvarchar(20) | **Tak** | Nie |
| Kategoria | ITMCostTrans.ShipCostCategory | Liczba całkowita | Nie | Nie |
| Kod typu kosztu | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | Nie | Nie |
| Firma | ITMCostTrans.ShipDataArea | Nvarchar(4) | Nie | **Tak** |
| Grupa podatków dla pozycji | ITMCostTrans.TaxItemGroup | Nvarchar(10) | Nie | Nie |

## <a name="item-costs-itmcosttransitementity"></a>Koszty towaru (ITMCostTransItemEntity)

Encja kosztu pozycji (`ITMCostTransItemEntity`) tworzy transakcje kosztowe, które odnoszą się do poziomu pozycji. Ta encja jest specyficzna dla pozycji na wierszach zamówień zakupu. Wartość kosztu jest w całości stosowana do linii.

Pola **Kwota korekty** i **Korekta wartości** są specyficzne dla obszarów kosztów na poziomie linii. Dlatego nie są one obecne w jednostkach danych dla innych obszarów kosztów.

| Nazwisko | Mapowanie | Typ danych | Klucz | Wymagana |
|---|---|---|---|---|
| Kwota korekty | ITMCostTrans.AdjustmentAmount | Numeric(32, 6) | Nie | Nie |
| Wartość kosztowa | ITMCostTrans.CostValue | Numeric(32, 6) | Nie | Nie |
| Waluta | ITMCostTrans.CurrencyCode | Nvarchar(3) | Nie | **Tak** |
| Numer wiersza | ITMCostTrans.LineNum | Numeric(32, 16) | **Tak** | Nie |
| Typ kosztu połączonego | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | Nie | Nie |
| Koszt minimalny | ITMCostTrans.MinCostAmount | Numeric(32, 6) | Nie | Nie |
| Zamówienie zakupu | ITMCostTrans.TransRecId | Nvarchar(20) | **Tak** | Nie |
| Numer wiersza zamówienia zakupu | ITMCostTrans.TransRecId | Nvarchar(20) | **Tak** | Nie |
| Kategoria | ITMCostTrans.ShipCostCategory | Liczba całkowita | Nie | Nie |
| Kod typu kosztu | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | Nie | Nie |
| Firma | ITMCostTrans.ShipDataArea | Nvarchar(4) | Nie | **Tak** |
| Grupa podatków dla pozycji | ITMCostTrans.TaxItemGroup | Nvarchar(10) | Nie | Nie |
| Korekta wartości | ITMCostTrans.ValueAdjustmentMethod | Liczba całkowita | Nie | Nie |

## <a name="transfer-line-costs-itmcosttranstransferlineentity"></a>Przeniesienie kosztów wiersza (ITMCostTransTransferLineEntity)

Encja koszt dla wiersza przeniesienia (`ITMCostTransTransferLineEntity`) tworzy transakcje kosztowe dotyczące poziomu wiersza zamówienia przeniesienia. Wartość tych kosztów jest odnoszona w całości do linii zlecenia transferu.

Pola **Kwota korekty** i **Korekta wartości** są specyficzne dla obszarów kosztów na poziomie linii. Dlatego nie są one obecne w jednostkach danych dla innych obszarów kosztów.

| Nazwisko | Mapowanie | Typ danych | Klucz | Wymagana |
|---|---|---|---|---|
| Kwota korekty | ITMCostTrans.AdjustmentAmount | Numeric(32, 6) | Nie | Nie |
| Wartość kosztowa | ITMCostTrans.CostValue | Numeric(32, 6) | Nie | Nie |
| Waluta | ITMCostTrans.CurrencyCode | Nvarchar(3) | Nie | **Tak** |
| Numer wiersza | ITMCostTrans.LineNum | Numeric(32, 16) | **Tak** | Nie |
| Typ kosztu połączonego | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | Nie | Nie |
| Koszt minimalny | ITMCostTrans.MinCostAmount | Numeric(32, 6) | Nie | Nie |
| Kategoria | ITMCostTrans.ShipCostCategory | Liczba całkowita | Nie | Nie |
| Kod typu kosztu | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | Nie | Nie |
| Firma | ITMCostTrans.ShipDataArea | Nvarchar(4) | Nie | **Tak** |
| Zamówienie przeniesienia | ITMCostTrans.TransRecId | Nvarchar(20) | **Tak** | Nie |
| Numer linii zlecenia transferu | ITMCostTrans.TransRecId | Nvarchar(20) | **Tak** | Nie |
| Grupa podatków dla pozycji | ITMCostTrans.TaxItemGroup | Nvarchar(10) | Nie | Nie |
| Korekta wartości | ITMCostTrans.ValueAdjustmentMethod | Liczba całkowita | Nie | Nie |

### <a name="transaction-table"></a>Tabela transakcji

Rekord transakcji kosztowej jest powiązany z obszarem kosztów poprzez przypisanie numeru tabeli transakcji (`TransTableId`). Gdy wymagane są konkretne numery identyfikacyjne tabel, jednostki są dzielone na podstawie tych wartości, tak by dla każdego obszaru kosztów istniała jedna jednostka.

Wartość dla tabeli transakcji (`TransTableId`) jest domyślnie przypisana do wyboru podmiotu transakcji kosztowej.

### <a name="calculated-fields"></a>Pola obliczeniowe

Poniższe pola nie są dostępne do wstawienia lub aktualizacji, gdy używana jest jednostka transakcji kosztowej, ponieważ te pola są ustawiane tylko wtedy, gdy podejmowane są określone działania na rekordzie rejsu:

- **Koszty szacowane** — To pole jest ustawiane w momencie zaksięgowania faktury za podróż (zlecenia zakupu) lub otrzymania przelewu.
- **Koszty szacowane; waluta** — To pole jest ustawiane w momencie zaksięgowania faktury za podróż (zlecenia zakupu) lub otrzymania przelewu.
- **Koszt rzeczywisty** — To pole jest ustawiane, gdy faktura sprzedawcy jest księgowana. Jest to związane z kosztami.

### <a name="find-auto-costs"></a>Znajdź koszty automatyczne

Przycisk **Znajdź automatyczne koszty** dostępny dla każdego obszaru kosztów (rejs, kontener wysyłkowy itd.) umożliwia aktualizację transakcji kosztowych dla danego obszaru kosztów na podstawie informacji zawartych w tabelach konfiguracyjnych. Kiedy wybierzesz przycisk dla obszaru kosztów, system wyczyści istniejące koszty dla tego obszaru kosztów i utworzy nowe rekordy w oparciu o aktualną konfigurację tabel automatycznego ustawiania kosztów.

Rekordy transakcji kosztowych, które są tworzone przez użycie encji danych, są oznaczane jako zaimportowane. Te rekordy nie zostaną usunięte, gdy wybierzesz **Znajdź auto koszty**, ponieważ nie zostaną one ponownie utworzone z tabel ustawień auto kosztów. Jednak rekord transakcji kosztowej, który jest oznaczony jako zaimportowany, może zostać usunięty.

### <a name="linked-fields"></a>Połączone pola

Każda transakcja kosztowa może być powiązana z innym rekordem w tym samym obszarze kosztowym. To powiązanie jest tworzone poprzez pole **Typ kosztu powiązanego**. Umożliwia obliczanie wartości kosztu jako procentu innego kosztu.

Pole **Typ kosztu powiązanego** może zostać zatwierdzone tylko wtedy, gdy rekord, do którego się odwołujemy, jest przetwarzany jako pierwszy lub gdy już istnieje w tabeli. Ten sam wymóg dotyczy pola **Połączony etap**, które jest używane tylko dla kosztów w obszarze kosztów kontenera wysyłkowego.
