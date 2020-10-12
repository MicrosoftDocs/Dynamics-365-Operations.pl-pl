---
title: Obsługiwane scenariusze dla konfiguracji podwójnego zapisu
description: W tym temacie opisano scenariusze obsługiwane w konfiguracji podwójnego zapisu.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 08/17/2020
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
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: b4f69e7933bc5a50cccad6911c99cf08d2768578
ms.sourcegitcommit: b3df62842e62234e8eaa16992375582518976131
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/17/2020
ms.locfileid: "3818603"
---
# <a name="supported-scenarios-for-dual-write-setup"></a>Obsługiwane scenariusze dla konfiguracji podwójnego zapisu

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

Można skonfigurować połączenie podwójnego zapisywania między środowiskiem Finance and Operations a środowiskiem Common Data Service.

+ Środowisko **Finance and Operations** stanowi podstawową platformę dla aplikacji **Finance and Operations** (na przykład Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management oraz Dynamics 365 Retail).
+ Środowisko **Common Data Service**stanowi podstawową platformę aplikacji opartych na **modelach w systemie Dynamics 365** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing i Dynamics 365 Project Service Automation).

>[!IMPORTANT]
>Human Resources w Finance and Operations obsługuje połączenia dwukrotnego zapisu, ale aplikacja Dynamics 365 Human Resources nie.

Mechanizm konfiguracji zmienia się w zależności od subskrypcji i środowiska.

+ W przypadku nowych wystąpień aplikacji Finance and Operations konfiguracja podwójnego zapisywania rozpoczyna się w Microsoft Dynamics Lifecycle Services (LCS). Jeśli masz licencję na Power Platform, otrzymasz nowe środowisko Common Data Service, jeśli Twoja dzierżawa nie ma takiego nowego środowiska.
+ W przypadku istniejących aplikacji Finance and Operations wystąpień Konfiguracja dwukrotnego zapisu rozpoczyna się w środowisku Finance and Operations.

Obsługiwane są następujące scenariusze konfiguracji:

+ [Nowe wystąpienie aplikacji Finance and Operations i wystąpienie aplikacji opartej na nowym modelu](#new-new)
+ [Nowe wystąpienie aplikacji Finance and Operations i wystąpienie aplikacji opartej na istniejącym modelu](#new-existing)
+ [Nowe wystąpienie aplikacji Finance and Operations, które ma dane demonstracyjne i wystąpienie aplikacji opartej na nowym modelu](#new-demo-new)
+ [Nowe wystąpienie aplikacji Finance and Operations, które ma dane demonstracyjne i wystąpienie aplikacji opartej na istniejącym modelu](#new-demo-existing)
+ [Istniejące wystąpienie aplikacji Finance and Operations i wystąpienie aplikacji opartej na nowym lub istniejącym modelu](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-model-driven-app-instance"></a><a id="new-new"></a>Nowe wystąpienie aplikacji Finance and Operations i wystąpienie aplikacji opartej na nowym modelu

Aby skonfigurować połączenie podwójnego zapisywania między nowym wystąpieniem aplikacji Finance and Operations, która nie ma danych i nowym wystąpieniem aplikacji opartej na modelu w systemie Dynamics 365, należy wykonać kroki w [konfiguracji podwójnego zapisywania z usług Lifecycle Services](lcs-setup.md). Po zakończeniu konfigurowania połączenia następuje automatyczne wykonywanie następujących akcji:

- Zainicjowano obsługę administracyjną Finance and Operations nowego, pustego środowiska.
- Zainicjowano obsługę administracyjną nowego, pustego wystąpienia aplikacji opartej na modelu, w której zainstalowano rozwiązanie podstawowe programu CRM.
- Dla danych firmy DAT jest ustanawiane połączenie podwójnego odpisu.
- W mapowaniach jednostek włączono obsługę synchronizacji na żywo.

Oba środowiska są następnie gotowe do synchronizacji danych na żywo.

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-model-driven-app-instance"></a><a id="new-existing"></a>Nowe wystąpienie aplikacji Finance and Operations i wystąpienie aplikacji opartej na istniejącym modelu

Aby skonfigurować połączenie podwójnego zapisywania między nowym wystąpieniem aplikacji Finance and Operations, która nie ma danych i istniejącym wystąpieniem aplikacji opartej na modelu w systemie Dynamics 365, należy wykonać kroki w [konfiguracji podwójnego zapisywania z usług Lifecycle Services](lcs-setup.md). Po zakończeniu konfigurowania połączenia następuje automatyczne wykonywanie następujących akcji:

- Zainicjowano obsługę administracyjną Finance and Operations nowego, pustego środowiska.
- Dla danych firmy DAT jest ustanawiane połączenie podwójnego odpisu.
- W mapowaniach jednostek włączono obsługę synchronizacji na żywo.

Oba środowiska są następnie gotowe do synchronizacji danych na żywo.

Aby zsynchronizować istniejące dane Common Data Service z aplikacją Finance and Operations, wykonaj następujące kroki.

1. Utwórz nową firmę w aplikacji Finance and Operations.
2. Dodaj firmę do konfiguracji połączenia z podwójnym zapisem.
3. [Uruchom](bootstrap-company-data.md) dane Common Data Service przy użyciu trzech liter kodu firmy Międzynarodowej Organizacji Normalizacyjnej (ISO).

Ponieważ podwójny zapis jest w trybie synchronizacji na żywo, dane z Common Data Service automatycznie zaczynają się przepływać do aplikacji Finance and Operations.

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-a-new-model-driven-app-instance"></a><a id="new-demo-new"></a>Nowe wystąpienie aplikacji Finance and Operations, które ma dane demonstracyjne i wystąpienie aplikacji opartej na nowym modelu

Aby skonfigurować połączenie podwójnego zapisywania między nowym wystąpieniem aplikacji Finance and Operations z danymi pokazowymi a nowym wystąpieniem aplikacji obsługującej model w systemie Dynamics 365, należy wykonać kroki w [nowym wystąpieniu aplikacji Finance and Operations oraz w sekcji wystąpienia aplikacji opartej na nowym modelu](#new-new), która znajduje się we wcześniejszej części tego tematu. Po zakończeniu konfigurowania połączenia, jeśli chcesz synchronizować dane demonstracyjne z aplikacją obsługującą model, wykonaj następujące kroki.

1. Otwórz aplikację Finance and Operations ze strony usługi LCS, zaloguj się, a następnie przejdź do **Zarządzanie danymi \> Podwójny zapis**.
2. Uruchom funkcję **synchronizacji początkowej** dla jednostek, dla których chcesz synchronizować dane.

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-an-existing-model-driven-app-instance"></a><a id="new-demo-existing"></a>Nowe wystąpienie aplikacji Finance and Operations, które ma dane demonstracyjne i wystąpienie aplikacji opartej na istniejącym modelu

Aby skonfigurować połączenie podwójnego zapisywania między nowym wystąpieniem aplikacji Finance and Operations z danymi pokazowymi a istniejącym wystąpieniem aplikacji obsługującej model w systemie Dynamics 365, należy wykonać kroki w [nowym wystąpieniu aplikacji Finance and Operations oraz w sekcji wystąpienia aplikacji opartej na istniejącym modelu](#new-existing), która znajduje się we wcześniejszej części tego tematu. Po zakończeniu konfigurowania połączenia, jeśli chcesz synchronizować dane demonstracyjne z aplikacją obsługującą model, wykonaj następujące kroki.

1. Otwórz aplikację Finance and Operations ze strony usługi LCS, zaloguj się, a następnie przejdź do **Zarządzanie danymi \> Podwójny zapis**.
2. Uruchom funkcję **synchronizacji początkowej** dla jednostek, dla których chcesz synchronizować dane.

Aby zsynchronizować istniejące dane Common Data Service z aplikacją Finance and Operations, wykonaj następujące kroki.

1. Utwórz nową firmę w aplikacji Finance and Operations.
2. Dodaj firmę do konfiguracji połączenia z podwójnym zapisem.
3. [Uruchom](bootstrap-company-data.md) dane Common Data Service przy użyciu trzech liter kodu firmy ISO.

Ponieważ podwójny zapis jest w trybie synchronizacji na żywo, dane z Common Data Service automatycznie zaczynają się przepływać do aplikacji Finance and Operations.

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-or-existing-model-driven-app-instance"></a><a id="existing-existing"></a>Istniejące wystąpienie aplikacji Finance and Operations i wystąpienie aplikacji opartej na nowym lub istniejącym modelu

Konfiguracja połączenia z podwójnym zapisywaniem między istniejącym wystąpieniem aplikacji Finance and Operations a nowym lub istniejącym wystąpieniem aplikacji opartej na modelu w systemie Dynamics 365 występuje w środowisku finansów i operacji.

1. Skonfiguruj połączenie z aplikacji Finance and Operations.
2. Aby zsynchronizować istniejące dane Common Data Service z aplikacją Finance and Operations, należy [załadować](bootstrap-company-data.md) dane Common Data Service przy użyciu trój-literowego kodu ISO firmy.

Ponieważ podwójny zapis jest w trybie synchronizacji na żywo, dane z Common Data Service automatycznie zaczynają się przepływać do aplikacji Finance and Operations.
