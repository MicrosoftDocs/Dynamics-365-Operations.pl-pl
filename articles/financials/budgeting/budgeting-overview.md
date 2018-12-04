---
title: "Budżetowanie — strona główna"
description: "Ten temat zawiera omówienie składników funkcji budżetowania, narzędzi budżetowania oraz funkcji raportowania dostępnych w rozwiązaniu Microsoft Dynamics 365 for Finance and Operations."
author: ShylaThompson
manager: AnnBe
ms.date: 08/09/2017
ms.topic: index-page
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BudgetPlanningWorkspace
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 106043
ms.assetid: 702f692e-ad1c-4798-8d3e-c3cf8591d3fa
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: efe348d9967ab7594afd22a3ebb4df76dc6607f8
ms.contentlocale: pl-pl
ms.lasthandoff: 03/26/2018

---

# <a name="budgeting-home-page"></a>Budżetowanie — strona główna

[!include [banner](../includes/banner.md)]

Ten temat zawiera omówienie składników funkcji budżetowania, narzędzi budżetowania oraz funkcji raportowania dostępnych w rozwiązaniu Finance and Operations. 

<a name="components-of-budgeting-functionality"></a>Składniki funkcji budżetowania
-------------------------------------

Cykl planowania zasobów dla firmy zwykle obejmuje działania dotyczące planowania, budżetowania i prognozowania.

[![Składniki funkcji budżetowania](./media/budgeting-functionality-components.jpg)](./media/budgeting-functionality-components.jpg)

Procesy długoterminowego planowania strategicznego oraz planowania budżetu rocznego są obsługiwane za pomocą dokumentu planu budżetu. Dokumenty planu budżetu są ściśle zintegrowane z programem Microsoft Excel. Użytkownicy mogą konfigurować nieograniczoną liczbę scenariuszy pieniężnych i ilościowych oraz definiować hierarchie organizacyjne budżetowania do obsługi metod budżetowania od góry do dołu i od dołu do góry. Po określeniu i zatwierdzeniu budżetu w rozwiązaniu Finance and Operations należy przekonwertować plan budżetu na wpis do rejestru budżetu. Wpisy do rejestru budżetu zawierają narzędzia do obsługi budżetu i przechowywania kwot, które można śledzić za pomocą kodów budżetu. Wpisy do rejestru budżetu umożliwiają poprawianie pierwotnych budżetów, wykonywanie przeniesień i przenoszenie na następny okres kwot budżetu z poprzedniego roku. Na podstawie przyjętego budżetu firma może włączyć kontrolę budżetu. Poziom kontroli zależy od kultury organizacyjnej oraz poziomu dojrzałości organizacji. Organizacje o mniejszej dojrzałości mogą pozostawiać budżet „taki, jaki jest” i w sytuacji, gdy budżet nie spełnia oczekiwań, działać reaktywnie, a nie proaktywnie. Inne organizacje mogą włączyć zasady kontroli budżetu, które uniemożliwiają użytkownikom kupowanie, jeśli w budżecie nie ma dostępnych środków.

Organizacje bardzo dojrzałe mogą wykształcić kulturę organizacyjną, w której pracownicy etatowi znają cele organizacyjne i realizują je za pomocą zasad, takich jak „Należy rozważyć spotkania online zamiast podróży”. Rozwiązanie Finance and Operations zawiera strukturę kontroli budżetu umożliwiającą kierownictwu firmy wybranie modelu twardej kontroli (który uniemożliwia księgowanie powyżej wysokości budżetu) lub miękkiej kontroli (w którym użytkownicy są ostrzegani o ryzyku przekroczenia budżetu, ale mogą sami podejmować decyzje dotyczące dalszego postępowania). Można również stosować prognozy kroczące. Prognoza krocząca polega na regularnym porównywaniu budżetu z wartościami rzeczywistymi i jest używana do definiowania skuteczności wykonywania budżetu przez firmę. Prognoza krocząca służy także do identyfikowania trendów. W rozwiązaniu Finance and Operations prognozy kroczące są obsługiwane za pomocą dokumentu planu budżetu jako działania planowania początkowego. Prognozy kroczące mogą być wykonywane równolegle z planowaniem dla nachodzącego cyklu budżetu.

-   [Budżetowanie podstawowe: omówienie i konfiguracja](basic-budgeting-overview-configuration.md)
-   [Kontrola budżetu: omówienie i konfiguracja](budget-control-overview-configuration.md)
-   [Planowanie budżetu: omówienie i konfiguracja](budget-planning-overview-configuration.md)
-   [Prognozy dotyczące stanowisk](position-forecasting.md)
-   [Dokumenty uzasadnienia planowania budżetu](budget-planning-justification-docs.md)
-   [Szablony programu Microsoft Excel do planowania budżetu](budget-planning-excel-templates.md)

## <a name="budgeting-tools-in-finance-and-operations"></a>Narzędzia budżetowania w rozwiązaniu Finance and Operations
[![Narzędzia budżetowania](./media/budgeting-tools.jpg)](./media/budgeting-tools.jpg) 

Dodatkowe funkcje planowania i budżetowania są dostępne w całym rozwiązaniu Finance and Operations i są zintegrowane z budżetami księgi.

-   **Budżety pracowników** — Budżetowanie pracowników zawiera funkcję planowania składników kosztów budżetu dla stanowisk, grup wynagrodzeń itd.
-   **Budżety środków trwałych** — Na podstawie informacji dotyczących środków trwałych można obliczyć planowaną amortyzację i rejestrować inne planowane transakcje dotyczące środków trwałych.
-   **Budżety projektów** — W module projektów można tworzyć szczegółowe prognozy projektów. Prognozy projektów będą zawierać szczegóły dotyczące planowanych godzin, wydatków, opłat i towarów.
-   **Prognozowanie popytu** — Na podstawie danych historycznych transakcji można oszacować przyszły popyt na zapasy i tworzyć prognozy popytu.

Aby uzyskać informacje dotyczące przenoszenia danych planowania z innych modułów do planów budżetów, zobacz [Integracja modułu Planowanie budżetu z innymi modułami](budget-planning-integration-other-modules.md).

## <a name="user-interface-and-reporting-capabilities"></a>Interfejs użytkownika i funkcje raportowania
W rozwiązaniu Finance and Operations użytkownicy mogą tworzyć plany budżetu bezpośrednio w kliencie rozwiązania Finance and Operations (przy użyciu konfigurowalnej strony dokumentu planu budżetu) lub za pomocą programu Excel. Program Excel oferuje kilka dodatkowych funkcji. Można na przykład użyć zewnętrznych danych jako źródła planu budżetu, wykonywać niestandardowe obliczenia oraz używać tabel przestawnych i wykresów. Można skonfigurować większość zmiennych używanych w procesie planowania budżetu. 

Na przykład można określić, kto wykonuje budżetowanie, co jest ujęte w budżecie i jak wygląda proces. Mimo że program Excel umożliwia planowanie budżetu, rozwiązanie Finance and Operations jest jedynym źródłem wiarygodnych informacji i pozwala uniknąć problemów z kontrolą budżetu. Okresowe procesy mogą być używane do wprowadzania danych początkowych budżetowania do planu budżetu. Na potrzeby raportowania rozwiązanie Finance and Operations oferuje zestaw stron standardowych zapytań, które umożliwiają wyświetlanie i analizowanie danych budżetowania. Dane planu budżetu można wyświetlić za pomocą programu Management Reporter, a poszczególne scenariusze planu budżetu mogą być wyświetlane jako kolumny w raporcie tego programu.







