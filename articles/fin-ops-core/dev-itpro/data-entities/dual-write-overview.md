---
title: Integracja danych w czasie zbliżonym do rzeczywistego z Common Data Service
description: W tym temacie przedstawiono przegląd integracji danych produktu między Finance and Operations i Common Data Service.
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
ms.openlocfilehash: d70bce4e47c05a7974c1b974fdca17682e5370aa
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550864"
---
# <a name="near-real-time-data-integration-with-common-data-service"></a>Integracja danych w czasie zbliżonym do rzeczywistego z Common Data Service

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

W obecnym świecie cyfrowym ekosystemy biznesowe wykorzystują aplikacje Microsoft Dynamics 365 w całości. Ponieważ dane pochodzące od osób, klientów, z operacji i urządzeń Internetu rzeczy (IoT) trafiają do jednego źródła, istnieje szansa na tworzenie cyfrowych pętli sprzężenia zwrotnego. Aby osiągnąć ten komfort, niezbędna jest integracja między aplikacjami Finance and Operations i aplikacjami Dynamics 365. Niektóre Customer Engagement są zbudowane na Common Data Service. Integracja między danymi aplikacji Finance and Operations z Common Data Service pozwala innym aplikacjom komunikować się w sposób spójny i płynny z rozwiązaniem Finance and Operations.

Aplikacje Finance and Operations i Common Data Service zapewniają synchronizacje niemal w czasie rzeczywistym między aplikacjami Finance and Operations i innymi aplikacjami Dynamics 365 za pomocą schematu podwójnego zapisu. Zasięg jest szeroki i obejmuje 28 obszarów aplikacji. Celem jest zapewnienie środowiska użytkownika „One Dynamics 365” dzięki bezproblemowym przepływom danych, które łączą procesy biznesowe między aplikacjami.

![Diagram poglądowy architektury](media/dual-write-overview.jpg)

Dla klientów dostępne są następujące propozycje wartości:

+ [Hierarchia organizacyjna w usłudze Common Data Service](dual-write-organization.md)
+ [Pojęcie firmy w usługach Common Data Service](dual-write-company.md)
+ [Zintegrowane dane główne odbiorcy](dual-write-customer.md)
+ [Zintegrowane dane główne dostawcy](dual-write-vendor.md)
+ Ujednolicony produkt główny

## <a name="system-requirements"></a>Wymagania systemowe

Synchroniczne, dwukierunkowe przepływy danych niemal w czasie rzeczywistym wymagają następujących wersji:

+ Microsoft Dynamics 365 for Finance and Operations w wersji 10.0.4 (lipiec 2019) z aktualizacją platformy 28 lub nowszą
+ Microsoft Dynamics 365 for Customer Engagement, wersja platformy 9.1 (4.2) lub nowsza

## <a name="setup-instructions"></a>Instrukcje konfiguracji

Wykonaj następujące kroki, aby skonfigurować integrację między aplikacjami Finance and Operations i Common Data Service.
    
1. Aby skonfigurować system podwójnego zapisu, zobacz [szczegółowy poradnik](https://aka.ms/dualwrite-docs) na temat wprowadzenia podwójnego zapisu w wersji próbnej.
2. Pobierz i zainstaluj rozwiązanie z grupy Yammer [Integracja Finance and Operations, Common Data Service i Customer Engagement](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096). Pakiet zawiera pięć rozwiązań:

    + Dynamics365Company
    + CurrencyExchangeRates
    + Dynamics365FinanceAndOperationsCommon
    + Dynamics365FinanceCommon
    + Dynamics365SupplyChainCommon

3. Postępuj zgodnie z kolejnością [wykonywania synchronizacji początkowych danych referencyjnych](dual-write-initial.md).
4. Jeśli wystąpią problemy z synchronizacją podwójnego zapisu, zobacz [Przewodnik rozwiązywania problemów z integracją danych](dual-write-troubleshooting.md).

> [!IMPORTANT]
> Nie można uruchomić równolegle podwójnego zapisu i [Prospekt do gotówki](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/accounts-template-mapping-direct). Jeśli korzystasz z rozwiązania Prospekt na gotówkę, musisz ją odinstalować. Należy również wyłączyć szablony podwójnego zapisu odbiorcy i dostawcy, które są częścią rozwiązania Prospektem na gotówkę.
