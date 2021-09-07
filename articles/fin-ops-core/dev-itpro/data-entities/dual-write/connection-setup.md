---
title: Wskazówki dotyczące konfiguracji podwójnego zapisu
description: W tym temacie opisano scenariusze obsługiwane w konfiguracji podwójnego zapisu.
author: RamaKrishnamoorthy
ms.date: 10/12/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 6450ef7b0a59df3a8da2c8bed3aa9c0b14a9cc97
ms.sourcegitcommit: 259ba130450d8a6d93a65685c22c7eb411982c92
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/24/2021
ms.locfileid: "7417064"
---
# <a name="guidance-for-dual-write-setup"></a>Wskazówki dotyczące konfiguracji podwójnego zapisu

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Można skonfigurować połączenie podwójnego zapisywania między środowiskiem Finance and Operations a środowiskiem Dataverse.

+ Środowisko **Finance and Operations** stanowi podstawową platformę dla aplikacji **Finance and Operations** (np. Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce i Dynamics 365 Human Resources).
+ **Środowisko Dataverse** stanowi podstawową platformę **aplikacji typu Customer Engagement** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Column Service, Dynamics 365 Marketing i Dynamics 365 Project Service Automation).

> [!IMPORTANT]
> Moduł Human Resources w Dynamics 365 Finance obsługuje połączenia dwukrotnego zapisu, ale aplikacja Dynamics 365 Human Resources nie.

Mechanizm konfiguracji zmienia się w zależności od subskrypcji i środowiska:

+ W przypadku nowych wystąpień aplikacji Finance and Operations konfiguracja podwójnego zapisywania rozpoczyna się w Microsoft Dynamics Lifecycle Services (LCS). Jeśli masz licencję na Microsoft Power Platform, otrzymasz nowe środowisko Dataverse, jeśli Twoja dzierżawa nie ma takiego nowego środowiska.
+ W przypadku istniejących aplikacji Finance and Operations wystąpień Konfiguracja dwukrotnego zapisu rozpoczyna się w środowisku Finance and Operations.

Przed rozpoczęciem podwójnego zapisywania w jednostce można uruchomić synchronizację początkową umożliwiającą obsługę istniejących danych po obu stronach: aplikacji Finance and Operations i aplikacji do zakontraktowania klientów. Synchronizację początkową można pominąć, jeśli nie ma potrzeby synchronizowania danych między tymi środowiskami.

Synchronizacja początkowa umożliwia skopiowanie istniejących danych z jednej aplikacji na inną dwukierunkową. Istnieje kilka różnych scenariuszy konfiguracji, w zależności od tego, które środowiska są już dostępne, oraz jakiego typu dane znajdują się w nich.

Obsługiwane są następujące scenariusze konfiguracji:

+ [Nowe wystąpienie aplikacji Finance and Operations i wystąpienie aplikacji do zakontraktowania odbiorcy](#new-new)
+ [Nowe wystąpienie aplikacji Finance and Operations i wystąpienie istniejącej aplikacji do zakontraktowania odbiorcy](#new-existing)
+ [Nowe wystąpienie aplikacji Finance and Operations, które ma dane i wystąpienie aplikacji do zakontraktowania odbiorcy](#new-data-new)
+ [Nowe wystąpienie aplikacji Finance and Operations, które ma dane i wystąpienie aplikacji do zakontraktowania odbiorcy](#new-data-existing)
+ [Istniejące wystąpienie aplikacji Finance and Operations i wystąpienie nowej aplikacji do zakontraktowania odbiorcy](#existing-new)
+ [Istniejące wystąpienie aplikacji Finance and Operations i wystąpienie istniejącej aplikacji do zakontraktowania odbiorcy](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="new-new"></a>Nowe wystąpienie aplikacji Finance and Operations i wystąpienie aplikacji do zakontraktowania odbiorcy

Aby skonfigurować połączenie podwójnego zapisywania między nowym wystąpieniem aplikacji Finance and Operations, która nie ma danych i nowym wystąpieniem aplikacji do zakontraktowania odbiorcy, należy wykonać kroki w [konfiguracji podwójnego zapisywania z usług Lifecycle Services](lcs-setup.md). Po zakończeniu konfigurowania połączenia następuje automatyczne wykonywanie następujących akcji:

- Zainicjowano obsługę administracyjną Finance and Operations nowego, pustego środowiska.
- Zainicjowano obsługę administracyjną nowego, pustego wystąpienia aplikacji do zakontraktowania odbiorcy, w której zainstalowano rozwiązanie podstawowe programu CRM.
- Dla danych firmy DAT jest ustanawiane połączenie podwójnego odpisu.
- W mapowaniach tabeli włączono obsługę synchronizacji na żywo.

Oba środowiska są następnie gotowe do synchronizacji danych na żywo.

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="new-existing"></a>Nowe wystąpienie aplikacji Finance and Operations i wystąpienie istniejącej aplikacji do zakontraktowania odbiorcy

Aby skonfigurować połączenie podwójnego zapisywania między nowym wystąpieniem aplikacji Finance and Operations, która nie ma danych i istniejącym wystąpieniem aplikacji do zakontraktowania odbiorcy, należy wykonać kroki w [konfiguracji podwójnego zapisywania z usług Lifecycle Services](lcs-setup.md). Po zakończeniu konfigurowania połączenia następuje automatyczne wykonywanie następujących akcji:

- Zainicjowano obsługę administracyjną Finance and Operations nowego, pustego środowiska.
- Dla danych firmy DAT jest ustanawiane połączenie podwójnego odpisu.
- W mapowaniach tabeli włączono obsługę synchronizacji na żywo.

Oba środowiska są następnie gotowe do synchronizacji danych na żywo.

Aby zsynchronizować istniejące dane Dataverse z aplikacją Finance and Operations, wykonaj następujące kroki.

1. Utwórz nową firmę w aplikacji Finance and Operations.
2. Dodaj firmę do konfiguracji połączenia z podwójnym zapisem.
3. [Uruchom](bootstrap-company-data.md) dane Dataverse przy użyciu trzech liter kodu firmy Międzynarodowej Organizacji Normalizacyjnej (ISO).
4. Uruchom funkcję **synchronizacji początkowej** dla tabel, dla których chcesz synchronizować dane.

Aby uzyskać łącza do przykładowych i alternatywnych rozwiązań, zajrzyj do sekcji [Przykład](#example) w dalszej części tego tematu.

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-a-new-customer-engagement-app-instance"></a><a id="new-data-new"></a>Nowe wystąpienie aplikacji Finance and Operations, które ma dane i wystąpienie aplikacji do zakontraktowania odbiorcy

Aby skonfigurować połączenie podwójnego zapisywania między nowym wystąpieniem aplikacji Finance and Operations z danymi pokazowymi a nowym wystąpieniem aplikacji do zakontraktowania odbiorcy, należy wykonać kroki w [nowym wystąpieniu aplikacji Finance and Operations oraz w sekcji wystąpienia aplikacji do zakontraktowania odbiorcy](#new-new), która znajduje się we wcześniejszej części tego tematu. Po zakończeniu konfigurowania połączenia, jeśli chcesz synchronizować dane z aplikacją do zakontraktowania odbiorcy, wykonaj następujące kroki.

1. Otwórz aplikację Finance and Operations ze strony usługi LCS, zaloguj się, a następnie przejdź do **Zarządzanie danymi \> Podwójny zapis**.
2. Uruchom funkcję **synchronizacji początkowej** dla tabel, dla których chcesz synchronizować dane.

Aby uzyskać łącza do przykładowych i alternatywnych rozwiązań, zajrzyj do sekcji [Przykład](#example).

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-an-existing-customer-engagement-app-instance"></a><a id="new-data-existing"></a>Nowe wystąpienie aplikacji Finance and Operations, które ma dane i wystąpienie aplikacji do zakontraktowania odbiorcy

Aby skonfigurować połączenie podwójnego zapisywania między nowym wystąpieniem aplikacji Finance and Operations z danymi pokazowymi a istniejącym wystąpieniem aplikacji do zakontraktowania odbiorcy, należy wykonać kroki w [nowym wystąpieniu aplikacji Finance and Operations oraz w sekcji istniejącego wystąpienia aplikacji do zakontraktowania odbiorcy](#new-existing), która znajduje się we wcześniejszej części tego tematu. Po zakończeniu konfigurowania połączenia, jeśli chcesz synchronizować dane z aplikacją do zakontraktowania odbiorcy, wykonaj następujące kroki.

1. Otwórz aplikację Finance and Operations ze strony usługi LCS, zaloguj się, a następnie przejdź do **Zarządzanie danymi \> Podwójny zapis**.
2. Uruchom funkcję **synchronizacji początkowej** dla tabel, dla których chcesz synchronizować dane.

Aby zsynchronizować istniejące dane Dataverse z aplikacją Finance and Operations, wykonaj następujące kroki.

1. Utwórz nową firmę w aplikacji Finance and Operations.
2. Dodaj firmę do konfiguracji połączenia z podwójnym zapisem.
3. [Uruchom](bootstrap-company-data.md) dane Dataverse przy użyciu trzech liter kodu firmy ISO.
4. Uruchom funkcję **synchronizacji początkowej** dla tabel, dla których chcesz synchronizować dane.

Aby uzyskać łącza do przykładowych i alternatywnych rozwiązań, zajrzyj do sekcji [Przykład](#example).

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="existing-new"></a>Istniejące wystąpienie aplikacji Finance and Operations i wystąpienie nowej aplikacji do zakontraktowania odbiorcy

Konfiguracja połączenia z podwójnym zapisywaniem między istniejącym wystąpieniem aplikacji Finance and Operations a nowym wystąpieniem aplikacji do zakontraktowania odbiorcy występuje w środowisku Finance and Operation.

1. [Skonfiguruj połączenie z aplikacji Finance and Operations](enable-dual-write.md).
2. Uruchom funkcję **synchronizacji początkowej** dla tabel, dla których chcesz synchronizować dane.

Aby uzyskać łącza do przykładowych i alternatywnych rozwiązań, zajrzyj do sekcji [Przykład](#example).

## <a name="an-existing-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="existing-existing"></a>Istniejące wystąpienie aplikacji Finance and Operations i wystąpienie istniejącej aplikacji do zakontraktowania odbiorcy

Konfiguracja połączenia z podwójnym zapisywaniem między istniejącym wystąpieniem aplikacji Finance and Operations a istniejącym wystąpieniem aplikacji do zakontraktowania odbiorcy występuje w środowisku Finance and Operation.

1. [Skonfiguruj połączenie z aplikacji Finance and Operations](enable-dual-write.md).
2. Aby zsynchronizować istniejące dane Dataverse z aplikacją Finance and Operations, należy [załadować](bootstrap-company-data.md) dane Dataverse przy użyciu trój-literowego kodu ISO firmy.
3. Uruchom funkcję **synchronizacji początkowej** dla tabel, dla których chcesz synchronizować dane.

Aby uzyskać łącza do przykładowych i alternatywnych rozwiązań, zajrzyj do sekcji [Przykład](#example).

## <a name="example"></a>Przykład

Aby zapoznać się z przykładem, należy zapoznać się z formularzem [Włączanie odbiorcy v3 — Mapa tabeli kontaktów](enable-entity-map.md#enable-table-map)

W celu rozwiązania alternatywnego opartego na woluminach danych w każdej jednostce, która musi uruchomić synchronizację początkową, należy zapoznać się z [Zagadnienia dotyczące synchronizacji początkowej](initial-sync-guidance.md).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]