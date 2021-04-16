---
title: Zintegrowana księga
description: W tym temacie opisano integrację danych księgi między aplikacją Finance and Operations i innymi aplikacjami Dynamics 365 przy użyciu usługi Dataverse.
author: robinarh
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: rhaertle
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 5fedcbcd8db2692214ea66b2fbab9f7381e0a622
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748524"
---
# <a name="integrated-ledger"></a>Zintegrowana księga

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



W aplikacji biznesowej dane księgi określają podstawowe ustawienia dotyczące sposobu prowadzenia działalności firmy. Na przykład dane księgi opisują następujący rok obrachunkowy:, waluty transakcyjne oraz konta, z których korzysta firma. W tym temacie opisano integrację tych podstawowych danych finansowych.

## <a name="templates"></a>Szablony

Dane księgi zawierają kolekcję podstawowych mapowań tabel finansowych, które działają razem podczas interakcji z danymi, jak pokazano w poniższej tabeli.

Aplikacje Finance and Operations      | Aplikacja oparta na modelu w systemie Dynamics 365 | opis
---------------------------------|----------------------------------|------------
Waluty                       | transactioncurrencies            |
FiscalCalendar                   | msdyn\_fiscalcalendars        |
FiscalCalendarYear               | msdyn\_fiscalcalendaryears        |
ExchRateType                     | msdyn\_exchangeratetypes        |
ExchangeRateCurrencyPair         | msdyn\_currencyexchangeratepairs        |
FiscalPeriodEntity               | msdyn\_fiscalcalendarperiods        |
MainAccountCategory              | msdyn\_mainaccountcategory        |
Konto główne                      | msdyn\_mainaccounts        |
Księga                           | msdyn\_ledgers        |
ExchangeRates                    | msdyn\_currencyexchangerates        |
FinancialCalendarPeriod          | msdyn\_fiscalcalendarperiods        |
DimensionAttributeEntity         | msdyn\_dimensionattributes        |
DimensionIntegrationFormatEntity | msdyn\_financialdimensionformats        |
LedgerChartOfAccounts            | msdyn\_chartofaccounts        |


[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Currency](includes/Currencies-transactioncurrencies.md)]

[!include [Fiscal calendar](includes/FiscalCalendar-msdyn-fiscalcalendars.md)]

[!include [Fiscal calendar year](includes/FiscalCalendarYear-msdyn-fiscalcalendaryears.md)]

[!include [Exchange rate types](includes/ExchRateType-msdyn-exchangeratetypes.md)]

[!include [Exchange rate pair](includes/ExchangeRateCurrencyPair-msdyn-currencyexchangeratepairs.md)]

[!include [Main account category](includes/MainAccountCategory-msdyn-mainaccountcategory.md)]

[!include [Main account](includes/MainAccount-msdyn-mainaccounts.md)]

[!include [Ledger](includes/Ledger-msdyn-ledgers.md)]

[!include [Exchange rates](includes/ExchangeRates-msdyn-currencyexchangerates.md)]

[!include [Financial Calendar Period](includes/FiscalPeriodEntity-msdyn-fiscalcalendarperiods.md)]

[!include [Dimension attribute](includes/DimensionAttributeEntity-msdyn-dimensionattributes.md)]

[!include [Dimension integration format](includes/DimensionIntegrationFormatEntity-msdyn-financialdimensionformats.md)]

[!include [Chart Of Account](includes/LedgerChartOfAccounts-msdyn-chartofaccounts.md)]






[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]