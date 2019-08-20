---
title: Integracja danych prawie czasu rzeczywistego między programami Finance and Operations i Common Data Service.
description: Ten temat zawiera omówienie integracji między Microsoft Dynamics 365 for Finance and Operations i Common Data Service.
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
ms.openlocfilehash: aa614c8e6a79a3f7a4f8f2f99f1f1bd1a67ac921
ms.sourcegitcommit: efcc0dee8bde5f8f93f6291e7f059ad426843e57
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/31/2019
ms.locfileid: "1797235"
---
# <a name="near-real-time-data-integration-between-finance-and-operations-and-common-data-service"></a>Integracja danych prawie czasu rzeczywistego między programami Finance and Operations i Common Data Service.

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

W obecnym świecie cyfrowym ekosystemy biznesowe wykorzystują pakiet Microsoft Dynamics 365 w całości. Ponieważ dane pochodzące od osób, klientów, z operacji i urządzeń Internetu rzeczy (IoT) trafiają do jednego źródła, istnieje szansa na tworzenie cyfrowych pętli sprzężenia zwrotnego. Aby osiągnąć ten komfort, niezbędna jest integracja między Dynamics 365 for Finance and Operations i Dynamics 365 pod kątem aplikacji Customer Engagement. Aplikacje Customer Engagement są zbudowane na Common Data Service. Integracja między danymi programu Finance and Operations z Common Data Service pozwala aplikacjom Customer Engagement komunikować się w sposób spójny i płynny z programem Finance and Operations.

Finance and Operations i Common Data Service zapewniają synchronizacje niemal w czasie rzeczywistym między aplikacjami Finance and Operations i Customer Engagement za pomocą schematu podwójnego zapisu. Zasięg jest szeroki i obejmuje 28 obszarów Finance and Operations. Celem jest zapewnienie środowiska użytkownika „One Dynamics 365” dzięki bezproblemowym przepływom danych, które łączą procesy biznesowe między aplikacjami.

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

Wykonaj następujące kroki, aby skonfigurować integrację między programami Finance and Operations i Common Data Service.
    
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
