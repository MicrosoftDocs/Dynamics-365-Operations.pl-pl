---
title: Regulatory Configuration Service
description: W tym temacie przedstawiono omówienie możliwości Regulatory Configuration Service (RCS) i wyjaśniono, jak uzyskać dostęp do usługi.
author: JaneA07
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 1eeac7217290e0583fcecdf5b4b5b9153d266240
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019401"
---
# <a name="regulatory-configuration-service"></a>Regulatory Configuration Service

[!include [banner](../includes/banner.md)]

Regulatory Configuration Service (RCS) to autonomiczna usługa zarządzania projektantem i cyklem życia dla funkcji globalizacji bez kodu/z małą ilością kodu. RCS pozwala interesariuszom zajmującym się globalizacją rozszerzać i dostosowywać kluczowe obszary globalizacji, takie jak podatki, e-fakturowanie, sprawozdawczość regulacyjna, bankowość i dokumenty biznesowe bez konieczności angażowania programistów. Takie podejście do globalizacji bez kodu / z małą ilością kodu sprawia, że globalizacja jest łatwiejsza, szybsza i tańsza w tworzeniu lub rozszerzaniu.

RCS zapewnia następujące możliwości:

- Obsługa wszystkich funkcji udostępnianych przez raportowanie elektroniczne (ER).
- Warunek wstępny do skonfigurowania nowych mikrousług globalizacji.
- Obsługa faktur elektronicznych. Aby uzyskać więcej informacji, zajrzyj do [Faktury elektroniczne](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/electronic-invoicing-add-on-dynamics-365-ga).
- Obsługuje obliczanie podatku. Aby uzyskać więcej informacji, zobacz [Usługa podatkowa](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/tax-service-preview).
- Obsługa nowej funkcji globalizacji, która upraszcza zarządzanie cyklem życia funkcji złożonych z wielu komponentów i zapewnia dodatkowe możliwości konfigurowania działań i ustawiania parametrów funkcji. Aby uzyskać więcej informacji, zobacz [Regulatory Configuration Service — uproszczone zarządzanie funkcjami globalizacji dla usług globalizacji](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services).
- Obsługa scentralizowanej publikacji, przechowywania i udostępniania niestandardowych konfiguracji w globalnym repozytorium w celu uproszczenia zarządzania konfiguracją bez konieczności korzystania z usług Microsoft Dynamics Lifecycle Services (LCS).

## <a name="access-rcs"></a>Dostęp do RCS

Możesz zarejestrować się lub zalogować się do RCS ze [strony Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/).

![Rejestracja i logowanie w RCS](media/202103_RCS%20Marketing%20page_updated_1.jpg)

Na stronie **Regulatory Configuration Service** przejrzyj i zaakceptuj dodatkowe warunki korzystania z usługi, a następnie wybierz jeden z następujących przycisków:

- **Zarejestruj się**, jeśli korzystasz z usługi po raz pierwszy i korzystasz z firmowego adresu e-mail, aby zapewnić swojej organizacji środowisko usługowe
- **Zaloguj się**, jeśli wcześniej zarejestrowałeś się w usłudze i chcesz uzyskać dostęp do środowiska organizacji

## <a name="regional-availability"></a>Dostępność regionalna

RCS jest ogólnie dostępny w następujących regionach:

- Stany Zjednoczone
- Indie
- Francja
- Europa

Aby uzyskać pełną listę regionów, zobacz temat [Dynamics 365 oraz Power Platform: Dostępność, lokalizacja danych, język i lokalizacja](https://aka.ms/dynamics_365_international_availability_deck).

## <a name="related-rcs-documentation"></a>Powiązana dokumentacja RCS

Aby uzyskać więcej informacji na temat powiązanych komponentów, zapoznaj się z następującą dokumentacją:

- **Globalne repozytorium:**

    - [Utwórz konfigurację ER i prześlij do repozytorium globalnego](rcs-global-repo-upload.md)
    - [Udostępnianie konfiguracji w globalnym repozytorium](rcs-global-repo-share-configuration.md)
    - [Ulepszone filtrowanie w globalnym repozytorium](enhanced-filtering-global-repo.md)
    - [Pobieranie konfiguracji modułu Raportowanie elektroniczne z globalnego repozytorium](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md)
    - [Wycofywanie konfiguracji w repozytorium globalnym](discontinuing-configurations-rcs-global-repo.md)

- **Funkcje globalizacji:**

    - [Regulatory Configuration Service (RCS) — funkcje globalizacji](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services)