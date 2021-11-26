---
title: Zintegrowana księga
description: W tym temacie opisano integrację danych księgi między aplikacją Finance and Operations i innymi aplikacjami Dynamics 365 przy użyciu usługi Dataverse.
author: tonyafehr
ms.date: 09/06/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: tfehr
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: e41d600464d707d01a0e319dd3cd343b04aa26b7
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2021
ms.locfileid: "7782387"
---
# <a name="integrated-ledger"></a>Zintegrowana księga

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

W aplikacji biznesowej dane księgi określają podstawowe ustawienia dotyczące sposobu prowadzenia działalności firmy. Na przykład dane księgi opisują następujący rok obrachunkowy:, waluty transakcyjne oraz konta, z których korzysta firma. W tym temacie opisano integrację tych podstawowych danych finansowych.

## <a name="templates"></a>Szablony

Dane księgi zawierają kolekcję podstawowych mapowań tabel finansowych, które działają razem podczas interakcji z danymi, jak pokazano w poniższej tabeli.

Aplikacje Finance and Operations | Aplikacje Customer Engagement     | opis
---------------------------------|----------------------------------|------------
[Kursy wymiany w usłudze CDS](mapping-reference.md#123) | msdyn_currencyexchangerates |
[Plan kont](mapping-reference.md#121) | msdyn_chartofaccountses |
[Waluty](mapping-reference.md#218) | transactioncurrencies |
[Para walut kursu wymiany](mapping-reference.md#122) | msdyn_currencyexchangeratepairs |
[Typ kursu wymiany](mapping-reference.md#129) | msdyn_exchangeratetypes |
[Format wymiaru finansowego](mapping-reference.md#130) | msdyn_financialdimensionformats |
[Wymiary finansowe](mapping-reference.md#128) | msdyn_dimensionattributes |
[Jednostka Integracja kalendarza obrachunkowego](mapping-reference.md#132) | msdyn_fiscalcalendars |
[Kalendarzowy okres obrachunkowy](mapping-reference.md#131) | msdyn_fiscalcalendarperiods |
[Jednostka Integracja roku kalendarza obrachunkowego](mapping-reference.md#133) | msdyn_fiscalcalendaryears |
[Ledger](mapping-reference.md#148) | msdyn_ledgers |
[Konto główne](mapping-reference.md#152) | msdyn_mainaccounts |
[Kategorie kont głównych](mapping-reference.md#151) | msdyn_mainaccountcategories |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
