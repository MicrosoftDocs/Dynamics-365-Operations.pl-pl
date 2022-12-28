---
title: Konfigurowanie usługi Operational Insights
description: Ten artykuł opisuje, jak skonfigurować i używać funkcji Operational Insights w Microsoft Dynamics 365 Commerce.
author: ashishMSFT
ms.date: 12/07/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: ca0d31e403275d6131fa6d53f0a7b46a7ddb651d
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/08/2022
ms.locfileid: "9832131"
---
# <a name="set-up-operational-insights"></a>Konfigurowanie usługi Operational Insights

[!include [banner](../includes/banner.md)]

Ten artykuł opisuje, jak skonfigurować i używać funkcji Operational Insights w Microsoft Dynamics 365 Commerce.

Operational Insights to funkcja Dynamics 365 Commerce, która zapewnia klientom lepszy wgląd w stan usług i funkcjonalność biznesową poprzez wysyłanie danych telemetrycznych bezpośrednio na należące do klienta konto Application Insights.

Włączając Operational Insights dla swoich środowisk w Commerce headquarters, możesz zebrać listę zdarzeń zarówno z Commerce Scale Unit (CSU), jak i z urządzeń w punktach sprzedaży (POS). Zdarzenia te pomagają lepiej zrozumieć działanie systemów i pozwalają monitorować kluczowe wskaźniki techniczne i biznesowe.

Nawet jeśli nie chcesz zbierać tych danych przez cały czas, możesz skorzystać z możliwości szybkiego włączenia lub wyłączenia zbierania danych dla określonych środowisk. W ten sposób telemetria może pomóc w rozwiązywaniu problemów i usuwaniu usterek w trakcie rozwoju lub na produkcji.

## <a name="access-logs-in-application-insights"></a>Dzienniki dostępu w Application Insights

Aby uzyskać dostęp do dzienników zdarzeń diagnostycznych dla komponentów Commerce CSU i POS za pośrednictwem Application Insights, wykonaj procedury opisane w tym rozdziale.

### <a name="minimum-version-requirements-for-csu"></a>Minimalne wymagania wersji dla CSU

CSU ma następujące minimalne wymagania dotyczące wersji:

- 10.0.23 (wersja Retail Server 9.33.22062.15 i późniejsze)
- 10.0.24 (wersja Retail Server 9.34.22062.14 i późniejsze)
- 10.0.25 (wersja Retail Server 9.35.22062.13 i późniejsze)
- 10.0.26 i późniejsze (wszystkie wersje)

### <a name="enable-diagnostic-events-in-application-insights"></a>Włączanie zdarzeń diagnostycznych w Application Insights

> [!IMPORTANT]
> Jeśli wcześniej korzystałeś z wersji zapoznawczej Operational Insights, musisz wykonać poniższą procedurę, aby włączyć Operational Insights. W ten sposób zapewniasz sobie niezawodny i bezpieczny dostęp do wydarzeń.

Aby włączyć zdarzenia diagnostyczne komponentu Commerce, musisz mieć konto Application Insights. Możesz użyć istniejącego konta lub [stworzyć nowe konto](/azure/azure-monitor/app/create-workspace-resource#create-workspace-based-resource). Ze względu na ochronę danych zalecamy używanie osobnych kont Application Insights dla środowisk produkcyjnych, piaskownicowych i deweloperskich. Po utworzeniu konta musisz włączyć w centrali funkcję **Operational Insights**.

Aby włączyć zdarzenia diagnostyczne w Application Insights, wykonaj poniższe kroki.

1. W centrali otwórz obszar roboczy **Zarządzanie funkcjami** i włącz funkcję **Operational Insights**.
1. Przejdź do pozycji **Administrowanie systemem \> Ustawienia \> Operational Insights**.
1. W zakładce **Konfiguracja** ustaw opcję **Zdarzenia kanału handlowego** na **Tak**.
1. Na karcie **Środowiska** wprowadź wartości **LCS Environment ID** i **Tryb środowiskowy** dla każdego środowiska, w którym planujesz używać Application Insights. Identyfikator każdego środowiska można znaleźć na stronie **Szczegóły środowiska** dla danego środowiska w Microsoft Dynamics Lifecycle Services. Ten krok jest wymagany, aby zapobiec przypadkowemu wysyłaniu zdarzeń diagnostycznych do niewłaściwego środowiska podczas wykonywania operacji kopiowania bazy danych.
1. Na karcie **Rejestr Application Insights** określ wartość **Klucz instrumentu** Application Insights oraz odpowiadającą jej wartość **Tryb środowiska** środowisk, w których planujesz używać każdego konta Application Insights.
1. Po zakończeniu poprzedniej konfiguracji musisz uruchomić zadanie **CDX Job 1110**. Możesz poczekać, aż zadanie zostanie uruchomione według własnego harmonogramu, lub uruchomić je ręcznie.
1. W Lifecycle Services przejdź do **Szczegóły środowiska \> Commerce \> Zarządzanie**, wybierz instancję CSU, a następnie wybierz **Restart**. Powtórz ten krok dla każdego CSU.
1. Powtórz powyższe kroki dla każdego środowiska, w którym planujesz używać Application Insights.

> [!NOTE]
> - Zdarzenia telemetryczne w Operational Insights mogą ulec zmianie. Zalecamy, abyś używał zdarzeń Operational Insights do wstępnej analizy i samodzielnego rozwiązywania problemów, a nie do definiowania pulpitów nawigacyjnych czy alarmów. Jeśli używasz zdarzeń do celów innych niż samodzielne rozwiązywanie problemów, zalecamy, abyś sprawdzał i aktualizował swoje zapytania po każdym wydaniu CSU/POS.
> - Od wersji Commerce 10.0.29 procedury opisane w tym rozdziale umożliwiają również strumieniowe przesyłanie zdarzeń POS Operational Insights na konto Application Insights. Więcej informacji znajdziesz w [Operational Insights dla POS – Wydarzenia i zapytania](https://download.microsoft.com/download/9/2/b/92be35b0-0e24-4a4d-940d-6f4db29791c0/Operational-Insights-Commerce-POS-events-queries.pdf).

#### <a name="use-the-dllhostexeconfig-file-to-control-pos-operational-insights-events"></a>Użyj pliku DLLHost.exe.config do kontroli zdarzeń POS Operational Insights

Aby użyć pliku DLLHost.exe.config do sterowania zdarzeniami POS Operational Insights, wykonaj następujące kroki.

1. W edytorze tekstu otwórz plik **DLLHost.exe.config**, który znaleźć można tutaj: **C:\\Program Files (x86)\\Microsoft Dynamics 365\\70\\Retail Modern POS\\ClientBroker**.
1. W sekcji **diagnosticsSection** usuń element XML "sink", który ma nazwę klasy **Microsoft.Dynamics.Retail.Diagnostics.OperationalInsights.OperationalInsightsLogger**.
1. Zapisz plik.

### <a name="disable-diagnostic-events-in-application-insights"></a>Wyłączanie zdarzeń diagnostycznych w Application Insights

> [!IMPORTANT]
> Jeśli chcesz wyłączyć zdarzenia diagnostyczne i nie wysyłać ich do Application Insights, musisz wykonać następującą procedurę. Nie możesz po prostu wyłączyć tej funkcji w Zarządzaniu funkcjami.

Aby wyłączyć zdarzenia diagnostyczne w Application Insights, wykonaj poniższe kroki.

1. W centrali przejdź do pozycji **Administrowanie systemem \> Operational Insights**.
1. W zakładce **Konfiguracja** ustaw opcję **Zdarzenia kanału handlowego** na **Nie**.
1. Po zakończeniu poprzedniej konfiguracji musisz uruchomić zadanie **CDX Job 1110**. Możesz poczekać, aż zadanie zostanie uruchomione według własnego harmonogramu, lub uruchomić je ręcznie.
1. W Lifecycle Services przejdź do **Szczegóły środowiska \> Commerce \> Zarządzanie**, wybierz instancję CSU, a następnie wybierz **Restart**. Powtórz ten krok dla każdego CSU.
1. Powtórz powyższe kroki dla każdego środowiska, w którym planujesz wyłączyć Application Insights.

Aby wyłączyć zdarzenia diagnostyczne dla pojedynczego środowiska, usuń klucz oprzyrządowania w zakładce **Rejestr Application Insights** na stronie **Operational Insights**. Następnie wykonaj kroki 3 i 4 poprzedniej procedury.

> [!NOTE]
> W wersji Commerce 10.0.29 i nowszych kroki opisane w tym rozdziale wyłączają również strumieniowe przesyłanie zdarzeń POS Operational Insights na konto Application Insights. 
