---
title: Wskazówki dotyczące konfiguracji podwójnego zapisu
description: W tym artykule opisano scenariusze obsługiwane w konfiguracji podwójnego zapisu.
author: RamaKrishnamoorthy
ms.date: 06/28/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 15dfb609b5e25b4faf2b913cc2310df71c88a74d
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/02/2022
ms.locfileid: "9111258"
---
# <a name="guidance-for-dual-write-setup"></a>Wskazówki dotyczące konfiguracji podwójnego zapisu

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]



Można skonfigurować połączenie podwójnego zapisywania między środowiskiem w aplikacjach finansowych i operacyjnych a środowiskiem Dataverse.

+ **Środowisko finansowe i operacyjne** stanowi podstawową platformę dla **aplikacji finansowych i operacyjnych** (na przykład Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce oraz Dynamics 365 Human Resources).
+ **Środowisko Dataverse** stanowi podstawową platformę **aplikacji typu Customer Engagement** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Column Service, Dynamics 365 Marketing i Dynamics 365 Project Service Automation).


> [!IMPORTANT]
> Moduł Human Resources w aplikacji Dynamics 365 Finance obsługuje połączenia dwukrotnego zapisu, ale aplikacja Dynamics 365 Human Resources nie.

Mechanizm konfiguracji zmienia się w zależności od subskrypcji i środowiska:

+ W przypadku nowych wystąpień w aplikacjach finansowych i operacyjnych konfiguracja podwójnego zapisywania rozpoczyna się w Microsoft Dynamics Lifecycle Services (LCS). Jeśli masz licencję na Microsoft Power Platform, otrzymasz nowe środowisko Dataverse, jeśli Twoja dzierżawa nie ma takiego nowego środowiska.
+ W przypadku obecnych wystąpień aplikacji w aplikacjach finansowych i operacyjnych konfiguracja podwójnego zapisywania rozpoczyna się w środowisku w aplikacjach finansowych i operacyjnych.

Przed rozpoczęciem podwójnego zapisywania w jednostce można uruchomić synchronizację początkową umożliwiającą obsługę istniejących danych po obu stronach: w aplikacjach finansowych i operacyjnych i aplikacji do zakontraktowania klientów. Synchronizację początkową można pominąć, jeśli nie ma potrzeby synchronizowania danych między tymi środowiskami.

Synchronizacja początkowa umożliwia skopiowanie istniejących danych z jednej aplikacji na inną dwukierunkową. Istnieje kilka różnych scenariuszy konfiguracji, w zależności od tego, które środowiska są już dostępne, oraz jakiego typu dane znajdują się w nich.

Obsługiwane są następujące scenariusze konfiguracji:

+ [Nowe wystąpienie aplikacji w aplikacjach finansowych i operacyjnych i wystąpienie aplikacji do zakontraktowania odbiorcy](#new-new)
+ [Nowe wystąpienie aplikacji finansowych i operacyjnych i obecne wystąpienie aplikacji do zakontraktowania odbiorcy](#new-existing)
+ [Nowe wystąpienie aplikacji finansowych i operacyjnych, które ma dane i wystąpienie aplikacji do zakontraktowania odbiorcy](#new-data-new)
+ [Nowe wystąpienie aplikacji finansowych i operacyjnych, które ma dane i obecne wystąpienie aplikacji do zakontraktowania odbiorcy](#new-data-existing)
+ [Obecne wystąpienie aplikacji finansowych i operacyjnych i nowe wystąpienie aplikacji do zakontraktowania odbiorcy](#existing-new)
+ [Obecne wystąpienie aplikacji finansowych i operacyjnych i obecne wystąpienie aplikacji do zakontraktowania odbiorcy](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="new-new"></a>Nowe wystąpienie w aplikacji finansowych i operacyjnych i wystąpienie aplikacji do zakontraktowania odbiorcy

Aby skonfigurować połączenie podwójnego zapisywania między nowym wystąpieniem aplikacji finansowych i operacyjnych, która nie ma danych i nowym wystąpieniem aplikacji do zakontraktowania odbiorcy, należy wykonać kroki w [konfiguracji podwójnego zapisywania z usług Lifecycle Services](lcs-setup.md). Po zakończeniu konfigurowania połączenia następuje automatyczne wykonywanie następujących akcji:

- Nowe, puste środowisko w aplikacjach finansowych i operacyjnych jest konfigurowane.
- Zainicjowano obsługę administracyjną nowego, pustego wystąpienia aplikacji do zakontraktowania odbiorcy, w której zainstalowano rozwiązanie podstawowe programu CRM.
- Dla danych firmy DAT jest ustanawiane połączenie podwójnego odpisu.
- W mapowaniach tabeli włączono obsługę synchronizacji na żywo.

Oba środowiska są następnie gotowe do synchronizacji danych na żywo.

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="new-existing"></a>Nowe wystąpienie aplikacji finansowych i operacyjnych i obecne wystąpienie aplikacji do zakontraktowania odbiorcy

Aby skonfigurować połączenie podwójnego zapisywania między nowym wystąpieniem aplikacji finansowych i operacyjnych, która nie ma danych i obecnym wystąpieniem aplikacji do zakontraktowania odbiorcy, należy wykonać kroki w [konfiguracji podwójnego zapisywania z usług Lifecycle Services](lcs-setup.md). Po zakończeniu konfigurowania połączenia następuje automatyczne wykonywanie następujących akcji:

- Nowe, puste środowisko w aplikacjach finansowych i operacyjnych jest konfigurowane.
- Dla danych firmy DAT jest ustanawiane połączenie podwójnego odpisu.
- W mapowaniach tabeli włączono obsługę synchronizacji na żywo.

Oba środowiska są następnie gotowe do synchronizacji danych na żywo.

Aby zsynchronizować istniejące dane Dataverse z aplikacjami finansowymi i operacyjnymi, wykonaj następujące kroki.

1. Utwórz nową firmę w aplikacji finansowych i operacyjnych.
2. Dodaj firmę do konfiguracji połączenia z podwójnym zapisem.
3. [Uruchom](bootstrap-company-data.md) dane Dataverse przy użyciu trzech liter kodu firmy Międzynarodowej Organizacji Normalizacyjnej (ISO).
4. Uruchom funkcję **synchronizacji początkowej** dla tabel, dla których chcesz synchronizować dane.

Aby uzyskać linki do przykładowych i alternatywnych rozwiązań, zajrzyj do sekcji [Przykład](#example) w dalszej części tego artykułu.

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-a-new-customer-engagement-app-instance"></a><a id="new-data-new"></a>Nowe wystąpienie aplikacji finansowych i operacyjnych, które ma dane i wystąpienie aplikacji do zakontraktowania odbiorcy

Aby skonfigurować połączenie podwójnego zapisu między nowym wystąpieniem aplikacji finansowych i operacyjnych z danymi pokazowymi a nowym wystąpieniem aplikacji Customer Engagement, należy wykonać kroki w sekcji [Nowe wystąpienie aplikacji finansowej i operacyjnej i nowe wystąpienie aplikacji Customer Engagement](#new-new), która znajduje się we wcześniejszej części tego artykułu. Po zakończeniu konfigurowania połączenia, jeśli chcesz synchronizować dane z aplikacją do zakontraktowania odbiorcy, wykonaj następujące kroki.

1. Otwórz aplikację finansową i operacyjną ze strony usługi LCS, zaloguj się, a następnie przejdź do **Zarządzanie danymi \> Podwójny zapis**.
2. Uruchom funkcję **synchronizacji początkowej** dla tabel, dla których chcesz synchronizować dane.

Aby uzyskać łącza do przykładowych i alternatywnych rozwiązań, zajrzyj do sekcji [Przykład](#example).

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-an-existing-customer-engagement-app-instance"></a><a id="new-data-existing"></a>Nowe wystąpienie aplikacji finansowych i operacyjnych które ma dane i obecne wystąpienie aplikacji do zakontraktowania odbiorcy

Aby skonfigurować połączenie podwójnego zapisywania między nowym wystąpieniem aplikacji finansowej i operacyjnej z danymi pokazowymi a obecnym wystąpieniem aplikacji Customer Engagement, należy wykonać kroki w sekcji [Nowe wystąpienie aplikacji finansowej i operacyjnej i nowe wystąpienie aplikacji Customer Engagement](#new-existing), która znajduje się we wcześniejszej części tego artykułu. Po zakończeniu konfigurowania połączenia, jeśli chcesz synchronizować dane z aplikacją do zakontraktowania odbiorcy, wykonaj następujące kroki.

1. Otwórz aplikację finansową i operacyjną ze strony usługi LCS, zaloguj się, a następnie przejdź do **Zarządzanie danymi \> Podwójny zapis**.
2. Uruchom funkcję **synchronizacji początkowej** dla tabel, dla których chcesz synchronizować dane.

Aby zsynchronizować istniejące dane Dataverse z aplikacjami finansowymi i operacyjnymi, wykonaj następujące kroki.

1. Utwórz nową firmę w aplikacji finansowych i operacyjnych.
2. Dodaj firmę do konfiguracji połączenia z podwójnym zapisem.
3. [Uruchom](bootstrap-company-data.md) dane Dataverse przy użyciu trzech liter kodu firmy ISO.
4. Uruchom funkcję **synchronizacji początkowej** dla tabel, dla których chcesz synchronizować dane.

Aby uzyskać łącza do przykładowych i alternatywnych rozwiązań, zajrzyj do sekcji [Przykład](#example).

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="existing-new"></a>Obecne wystąpienie aplikacji finansowych i operacyjnych i nowe wystąpienie aplikacji do zakontraktowania odbiorcy

Konfiguracja połączenia z podwójnym zapisywaniem między istniejącym wystąpieniem aplikacji Finanse i Działania a nowym wystąpieniem aplikacji do zakontraktowania odbiorcy występuje w środowisku aplikacji finansowych i operacyjnych.

1. [Skonfiguruj połączenie z aplikacją finansową i operacyjną](enable-dual-write.md).
2. Uruchom funkcję **synchronizacji początkowej** dla tabel, dla których chcesz synchronizować dane.

Aby uzyskać łącza do przykładowych i alternatywnych rozwiązań, zajrzyj do sekcji [Przykład](#example).

## <a name="an-existing-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="existing-existing"></a>Obecne wystąpienie aplikacji finansowych i operacyjnych i obecne wystąpienie aplikacji do zakontraktowania odbiorcy

Konfiguracja połączenia z podwójnym zapisywaniem między istniejącym wystąpieniem aplikacji Finanse i Działania a obecnym wystąpieniem aplikacji do zakontraktowania odbiorcy występuje w środowisku aplikacji finansowych i operacyjnych.

1. [Skonfiguruj połączenie z aplikacją finansową i operacyjną](enable-dual-write.md).
2. Aby zsynchronizować istniejące dane Dataverse z aplikacjami finansowymi i operacyjnymi, należy [załadować](bootstrap-company-data.md) dane Dataverse przy użyciu trój-literowego kodu ISO firmy.
3. Uruchom funkcję **synchronizacji początkowej** dla tabel, dla których chcesz synchronizować dane.

Aby uzyskać łącza do przykładowych i alternatywnych rozwiązań, zajrzyj do sekcji [Przykład](#example).

## <a name="example"></a>Przykład

Aby zapoznać się z przykładem, należy zapoznać się z formularzem [Włączanie odbiorcy v3 — Mapa tabeli kontaktów](enable-entity-map.md#enable-table-map)

W celu rozwiązania alternatywnego opartego na woluminach danych w każdej jednostce, która musi uruchomić synchronizację początkową, należy zapoznać się z [Zagadnienia dotyczące synchronizacji początkowej](initial-sync-guidance.md).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
