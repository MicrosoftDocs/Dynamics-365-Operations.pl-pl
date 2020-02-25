---
title: Integracja danych w czasie zbliżonym do rzeczywistego z Common Data Service
description: Ten temat zawiera omówienie integracji między Finance and Operations i Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 1c09b0c0bb695e7695acb7a8821ffb99ae1f6f06
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019962"
---
# <a name="near-real-time-data-integration-with-common-data-service"></a>Integracja danych w czasie zbliżonym do rzeczywistego z Common Data Service

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

W obecnym świecie cyfrowym ekosystemy biznesowe wykorzystują aplikacje Microsoft Dynamics 365 w całości. Ponieważ dane pochodzące od osób, klientów, z operacji i urządzeń Internetu rzeczy (IoT) trafiają do jednego źródła, istnieje szansa na tworzenie cyfrowych pętli sprzężenia zwrotnego. Aby osiągnąć ten komfort, niezbędna jest integracja między aplikacjami Finance and Operations i aplikacjami Dynamics 365. Niektóre Customer Engagement są zbudowane na Common Data Service. Integracja między aplikacjami Finance and Operations z innymi aplikacjami Common Data Service pozwala innym aplikacją komunikować się płynnie i jasno z Finance and Operations.

Aplikacje Finance and Operations i Common Data Service zapewniają synchronizacje niemal w czasie rzeczywistym między aplikacjami Finance and Operations i innymi aplikacjami Dynamics 365 za pomocą schematu podwójnego zapisu. Zasięg jest szeroki i obejmuje 28 obszarów aplikacji. Celem jest zapewnienie środowiska użytkownika „One Dynamics 365” dzięki bezproblemowym przepływom danych, które łączą procesy biznesowe między aplikacjami.

![Diagram poglądowy architektury](media/dual-write-overview.jpg)

Dla klientów dostępne są następujące propozycje:

+ [Hierarchia organizacyjna w usłudze Common Data Service](organization-mapping.md)
+ [Pojęcie firmy w usługach Common Data Service](company-data.md)
+ [Zintegrowane dane główne odbiorcy](customer-mapping.md)
+ [Zintegrowana księga](ledger-mapping.md)
+ [Ujednolicone działanie produktu](product-mapping.md)
+ [Zintegrowane dane główne dostawcy](vendor-mapping.md)
+ [Zintegrowane oddziały i magazyny](sites-warehouses-mapping.md)
+ [Zintegrowane dane główne podatków](tax-mapping.md)

## <a name="system-requirements"></a>Wymagania systemowe

Synchroniczne, dwukierunkowe przepływy danych niemal w czasie rzeczywistym wymagają następujących wersji:

+ Microsoft Dynamics 365 for Finance and Operations w wersji 10.0.4 (lipiec 2019) z aktualizacją platformy 28 lub nowszą
+ Microsoft Dynamics 365 for Customer Engagement, wersja platformy 9.1 (4.2) lub nowsza

## <a name="setup-instructions"></a>Instrukcje konfiguracji

Aby skonfigurować integrację między aplikacjami Finance and Operations i Common Data Service, wykonaj następujące czynności:
    
1. Aby skonfigurować system podwójnego zapisu, zobacz [szczegółowy poradnik](https://aka.ms/dualwrite-docs) na temat wprowadzenia podwójnego zapisu w wersji próbnej.
2. Pobierz i zainstaluj rozwiązanie z grupy [integracji aplikacji Fin Ops i CDS/CE za pośrednictwem Dual-Write](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096) w serwisie Yammer. Pakiet zawiera pięć rozwiązań:

    + Dynamics365Company
    + CurrencyExchangeRates
    + Dynamics365FinanceAndOperationsCommon
    + Dynamics365FinanceCommon
    + Dynamics365SupplyChainCommon

3. Postępuj zgodnie z kolejnością [wykonywania synchronizacji początkowych danych referencyjnych](initial-sync.md).
4. Jeśli wystąpią problemy z synchronizacją podwójnego zapisu, zobacz [Przewodnik rozwiązywania problemów z integracją danych](dual-write-troubleshooting.md).

> [!IMPORTANT]
> Nie można uruchomić równolegle podwójnego zapisu i [Prospekt do gotówki](../../../../supply-chain/sales-marketing/prospect-to-cash.md). Jeśli korzystasz z rozwiązania Prospekt na gotówkę, musisz ją odinstalować. Należy również wyłączyć szablony podwójnego zapisu odbiorcy i dostawcy, które są częścią rozwiązania Prospektem na gotówkę.
