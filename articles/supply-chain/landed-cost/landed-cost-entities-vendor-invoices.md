---
title: Jednostki faktur od dostawcy
description: Ten artykuł zawiera informacje o jednostkach faktur dostawców, które umożliwiają skonfigurowanie kodów typów kosztów dla kosztów wewnętrznych lub kosztów pochodzących z zewnątrz.
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
ms.openlocfilehash: 171b383e1549babd76fd18e4932436a66aa62cc1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873935"
---
# <a name="vendor-invoice-entities"></a>Podmioty wystawiające faktury

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until GA with 10.0.28 -->

Moduł **Koszty stałe** umożliwia skonfigurowanie kodów rodzajów kosztów dla kosztów wewnętrznych lub kosztów pochodzących z zewnątrz. Jeśli koszt jest zewnętrzny w stosunku do firmy, oczekuje się faktury od dostawcy usługi. Taka faktura jest przetwarzana jako arkusz faktur, który może być powiązany z podróżą, a wartość faktury może być rozłożona na jeden lub więcej kosztów podróży.

Jednostki faktur dostawców umożliwiają przypisanie wartości linii arkusza do jednego lub więcej kosztów podróży, które mają ten sam kod typu kosztu.

Koszt może zostać przypisany tylko wtedy, gdy istnieje nagłówek arkusza faktury i linie arkusza faktury.

## <a name="vendor-voyage-cost-allocations-itmledgerjournalcostlinesvoyagesentity"></a>Alokacje kosztów podróży dostawcy (ITMLedgerJournalCostLinesVoyagesEntity)

Jednostka danych alokacji kosztów podróży dostawcy umożliwia alokację linii faktury dostawcy na jeden lub więcej kosztów, które są stosowane w obszarze kosztów podróży. Ta funkcjonalność jest obsługiwana przez encję `ITMLedgerJournalCostLinesVoyagesEntity`. Poniższa tabela zawiera listę pól i mapowań, które składają się na tę encję.

| Nazwisko | Mapowanie | Typ danych | Klucz | Wymagana |
|---|---|---|---|---|
| Zaalokowana kwota | ITMLedgerJournalCostLines.Amount | Numeric(32, 6) | Nie | Nie |
| Numer wiersza transakcji kosztów | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Tak** | Nie |
| Numer wiersza arkusza | ITMLedgerJournalCostLines.RefRecId | Numeric(32, 16) | **Tak** | Nie |
| Numer arkusza | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Tak** | Nie |
| Podróż | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Tak** | Nie |

## <a name="vendor-shipping-container-cost-allocations-itmledgerjournalcostlinescontainersentity"></a>Alokacja kosztów kontenerów wysyłkowych dostawcy (ITMLedgerJournalCostLinesContainersEntity)

Jednostka danych "Alokacje kosztów kontenera wysyłkowego sprzedawcy" umożliwia przypisanie linii faktury sprzedawcy do jednego lub więcej kosztów, które są stosowane w obszarze kosztów kontenera wysyłkowego. Ta funkcjonalność jest obsługiwana przez encję `ITMLedgerJournalCostLinesContainersEntity`. Poniższa tabela zawiera listę pól i mapowań, które składają się na tę encję.

| Nazwisko | Mapowanie | Typ danych | Klucz | Wymagana |
|---|---|---|---|---|
| Zaalokowana kwota | ITMLedgerJournalCostLines.Amount | Numeric(32, 6) | Nie | Nie |
| Kontener wysyłkowy | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Tak** | Nie |
| Numer wiersza transakcji kosztów | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Tak** | Nie |
| Numer wiersza arkusza | ITMLedgerJournalCostLines.RefRecId | Numeric(32, 16) | **Tak** | Nie |
| Numer arkusza | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Tak** | Nie |
| Podróż | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Tak** | Nie |

## <a name="vendor-folio-cost-allocations-itmledgerjournalcostlinesfoliosentity"></a>Przypisanie kosztów do folio sprzedawcy (ITMLedgerJournalCostLinesFoliosEntity)

Jednostka danych alokacji kosztów folio dostawcy umożliwia alokację linii faktury dostawcy na jeden lub więcej kosztów, które są stosowane w obszarze kosztów folio. Ta funkcjonalność jest obsługiwana przez encję `ITMLedgerJournalCostLinesFoliosEntity`. Poniższa tabela zawiera listę pól i mapowań, które składają się na tę encję.

| Nazwisko | Mapowanie | Typ danych | Klucz | Wymagana |
|---|---|---|---|---|
| Zaalokowana kwota | ITMLedgerJournalCostLines.Amount | Numeric(32, 6) | Nie | Nie |
| Numer wiersza transakcji kosztów | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Tak** | Nie |
| Folio | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Tak** | Nie |
| Numer wiersza arkusza | ITMLedgerJournalCostLines.RefRecId | Numeric(32, 16) | **Tak** | Nie |
| Numer arkusza | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Tak** | Nie |

## <a name="vendor-purchase-order-cost-allocations-itmledgerjournalcostlinespurchtableentity"></a>Alokacja kosztów zamówienia zakupu dostawcy (ITMLedgerJournalCostLinesPurchTableEntity)

Jednostka danych alokacji kosztów zamówienia zakupu umożliwia przypisanie linii faktury dostawcy do jednego lub więcej kosztów, które są stosowane w obszarze kosztów zamówienia zakupu. Ta funkcjonalność jest obsługiwana przez encję `ITMLedgerJournalCostLinesPurchTableEntity`. Poniższa tabela zawiera listę pól i mapowań, które składają się na tę encję.

| Nazwisko | Mapowanie | Typ danych | Klucz | Wymagana |
|---|---|---|---|---|
| Zaalokowana kwota | ITMLedgerJournalCostLines.Amount | Numeric(32, 6) | Nie | Nie |
| Numer wiersza transakcji kosztów | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Tak** | Nie |
| Numer wiersza arkusza | ITMLedgerJournalCostLines.RefRecId | Numeric(32, 16) | **Tak** | Nie |
| Numer arkusza | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Tak** | Nie |
| Zamówienie zakupu | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Tak** | Nie |

## <a name="vendor-item-cost-allocations-itmledgerjournalcostlinespurchlineentity"></a>Alokacje kosztów produktu dostawcy (ITMLedgerJournalCostLinesPurchLineEntity)

Jednostka danych alokacji kosztów elementu dostawcy umożliwia alokację linii faktury dostawcy na jeden lub więcej kosztów, które są stosowane w obszarze kosztów elementu. Obszar kosztów pozycji obejmuje koszty w linii zamówienia zakupu. Ta funkcjonalność jest obsługiwana przez encję `ITMLedgerJournalCostLinesPurchLineEntity`. Poniższa tabela zawiera listę pól i mapowań, które składają się na tę encję.

| Nazwisko | Mapowanie | Typ danych | Klucz | Wymagana |
|---|---|---|---|---|
| Zaalokowana kwota | ITMLedgerJournalCostLines.Amount | Numeric(32, 6) | Nie | Nie |
| Numer wiersza transakcji kosztów | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Tak** | Nie |
| Numer wiersza arkusza | ITMLedgerJournalCostLines.RefRecId | Numeric(32, 16) | **Tak** | Nie |
| Numer arkusza | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Tak** | Nie |
| Zamówienie zakupu | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Tak** | Nie |
| Numer wiersza zamówienia zakupu | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Tak** | Nie |

## <a name="vendor-transfer-order-line-cost-allocations-itmledgerjournalcostlinestransferlineentity"></a>Alokacje kosztów wiersza zamówienia przeniesienia dostawcy (ITMLedgerJournalCostLinesTransferLineEntity)

Jednostka danych alokacji kosztów linii zamówienia transferowego sprzedawcy umożliwia alokację linii faktury sprzedawcy na jeden lub więcej kosztów, które są stosowane w obszarze kosztów linii transferowej. Ta funkcjonalność jest obsługiwana przez encję `ITMLedgerJournalCostLinesTransferLineEntity`. Poniższa tabela zawiera listę pól i mapowań, które składają się na tę encję.

| Nazwisko | Mapowanie | Typ danych | Klucz | Wymagana |
|---|---|---|---|---|
| Zaalokowana kwota | ITMLedgerJournalCostLines.Amount | Numeric(32, 6) | Nie | Nie |
| Numer wiersza transakcji kosztów | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Tak** | Nie |
| Numer wiersza arkusza | ITMLedgerJournalCostLines.RefRecId | Numeric(32, 16) | **Tak** | Nie |
| Numer arkusza | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Tak** | Nie |
| Zamówienie przeniesienia | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Tak** | Nie |
| Numer linii zlecenia transferu | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Tak** | Nie |

### <a name="reference-table"></a>Tabela odwołań

Linie kosztów podróży są bezpośrednio powiązane z rekordem transakcji kosztowej. Rekord ten zawiera wartość **Identyfikatora tabeli referencyjnej**. Wartość ta jest unikalna dla każdego obszaru kosztów (podróż, kontener morski itd.). Gdy w danych tworzonych za pomocą encji danych znajdują się odniesienia do konkretnych numerów tabel, encje są dzielone na podstawie wartości **Identyfikatora tabeli odniesienia**.

Wartości dla tabeli referencyjnej (`RefTableId`) i typu transakcji (`TransType`) są niejawne przy wyborze wiersza zakupu Koszt z wyładunkiem lub jednostki Wiersz przeniesienia kosztu z wyładunkiem.

## <a name="vendor-invoice-journal-lines-vendorinvoicejournallineentity"></a>Wiersze arkusza faktury sprzedawcy (VendorInvoiceJournalLineEntity)

Zanim wartość linii arkusza będzie mogła zostać przypisana do jednego lub więcej kosztów w module **Koszty osierocone**, linia arkusza musi być powiązana z obszarem kosztów. Aby wesprzeć tę funkcjonalność, moduł **Koszt wyładunku** dodaje kilka nowych pól do tabeli linii arkusza (`LedgerJournalTrans`).

### <a name="fields-added-to-the-vendor-invoice-journal-line-entity"></a>Pola dodane do elementu linii arkusza faktury sprzedawcy

Poniższa tabela zawiera listę pól, które moduł **Koszty z wyładunkiem** dodaje do elementu linii arkusza faktury sprzedawcy (`VendorInvoiceJournalLineEntity`). Te pola umożliwiają systemowi tworzenie linii arkusza i przypisywanie do nich kosztów.

| Nazwisko | Mapowanie | Typ danych | Klucz | Wymagana |
|---|---|---|---|---|
| Obszar kosztu | LedgerJournalTrans.ITMCostArea | Liczba całkowita | Nie | Nie |
| Kod typu kosztu | LedgerJournalTrans.ITMCostTypeId | Nvarchar(20) | Nie | Nie |

### <a name="mainoffset-account"></a>Konto główne/offsetowe

Konto główne/offsetowe dla linii arkusza faktury, która jest związana z podróżą po kosztach wyładunku, jest określane przez kod typu kosztu. Kiedy kod rodzaju kosztu jest umieszczony w linii arkusza faktury, konto rozliczeniowe dla tego kodu będzie używane albo jako konto główne, albo jako konto kompensacyjne, w zależności od scenariusza:

- **arkusz jednoliniowy** – Jeśli zdefiniowane jest konto główne (innymi słowy, konto sprzedawcy) i podany jest kod rodzaju kosztu, wartość konta rozliczeniowego dla tego kodu rodzaju kosztu zostanie wprowadzona na konto kompensacyjne.
- **arkusz wielowierszowy** – jeśli konto główne nie jest zdefiniowane, ale podany jest kod rodzaju kosztu, na koncie głównym zostanie wprowadzona wartość konta rozliczeniowego dla tego kodu rodzaju kosztu. Linia arkusza, która zasila konto sprzedawcy, nie będzie miała odniesienia do kodu typu kosztu.

## <a name="sequencing"></a>Harmonogram

Ze względu na zależności między tabelami arkusz i wiersze arkusza, rekord podróży musi być utworzony jako pierwszy. Wiersze podróży można utworzyć dopiero po utworzeniu podróży, kontenera wysyłkowego i folio.

Aby przypisać fakturę za podróż, system musi przetworzyć jednostki w następującej kolejności:

1. Nagłówek arkusza faktur (`VendInvoiceJournalHeaderEntity`)
1. Wiersz arkusza faktur (`VendInvoiceJournalLineEntity`)
1. Alokacja kosztów wyładunku (`ITMLedgerJournalEntities`)
