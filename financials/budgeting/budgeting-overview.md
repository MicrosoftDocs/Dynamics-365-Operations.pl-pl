---
title: "Budżetowanie — strona główna"
description: "Ten temat zawiera omówienie budżetowania składników funkcji narzędzia budżetowe i raportowania w programie Microsoft Dynamics 365 dla operacji."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: index-page
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 106043
ms.assetid: 702f692e-ad1c-4798-8d3e-c3cf8591d3fa
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: b21fd97426b331726c12ea29f89817a46dd445c3
ms.openlocfilehash: f7b4efc06b8e64c05da026850b41cb5b68c33ec3
ms.lasthandoff: 03/31/2017


---

# <a name="budgeting-home-page"></a>Budżetowanie — strona główna

Ten temat zawiera omówienie budżetowania składników funkcji narzędzia budżetowe i raportowania w programie Microsoft Dynamics 365 dla operacji.

<a name="components-of-budgeting-functionality"></a>Składniki funkcji budżetowania
-------------------------------------

Cykl planowania zasobów dla firmy zwykle obejmuje działania dotyczące planowania, budżetowania i prognozowania.
[![Budżetowanie składników funkcji](./media/budgeting-functionality-components.jpg)](./media/budgeting-functionality-components.jpg) procesów zarówno długoterminowe planowanie strategiczne i planowanie budżetu rocznego są obsługiwane za pośrednictwem dokumentu planu budżetu. Dokumenty planu budżetu są ściśle zintegrowane z programem Microsoft Excel. Użytkownicy mogą konfigurować nieograniczoną liczbę scenariuszy pieniężnych i ilościowych oraz definiować hierarchie organizacyjne budżetowania do obsługi metod budżetowania od góry do dołu i od+ dołu w górę. Po określeniu i zatwierdzeniu budżetu w programie Microsoft Dynamics 365 for Operations konwertujesz plan budżetu na wpis do rejestru budżetu. Wpisy do rejestru budżetu zawierają narzędzia do obsługi budżetu i przechowywania kwot możliwych do śledzenia za pomocą kodów budżetu. Wpisy do rejestru budżetu umożliwiają poprawianie pierwotnych budżetów, wykonywanie transferów i przenoszenie na następny okres kwot budżetu z poprzedniego roku. W oparciu o przyjęty budżet firma może włączyć kontrolę budżetu. Poziom kontroli zależy od kultury organizacyjnej oraz poziomu dojrzałości organizacji. Organizacje o mniejszej dojrzałości mogą pozostawiać budżetu „takim jaki jest” i w razie, gdy budżet nie spełnia oczekiwań, działać reaktywnie, a nie proaktywnie. Inne organizacje mogą włączyć zasady kontroli budżetu, które uniemożliwiają użytkownikom kupowanie, jeśli w budżecie nie ma dostępnych środków. Wreszcie organizacje bardzo dojrzały może ustanowić kultury organizacyjnej, gdzie pracownicy są wykształcone temat celów organizacyjnych i wykonaj te cele poprzez zasady, takie jak "Rozważ spotkania online zamiast podróży." Dynamics 365 dla operacji zawiera ramy kontroli budżetu, która pozwala wybrać obu formantów twarde, (która zapobiega komentarze, wykraczających ponad budżet) firmy zarządzania lub kontroli miękkie (gdzie użytkownicy są ostrzegani spowoduje przekroczenie środków budżetowych dostępnych ale może wybrać dla siebie sposób dalszego postępowania). Wreszcie można użyć toczenia prognoz. Prognoza krocząca jest regularne porównanie budżetu do wartości rzeczywiste i jest używane do definiowania jak firma działa z budżetem. Prognoza krocząca służy także do identyfikowania tendencji. W programie Microsoft Dynamics 365 for Operations prognozy kroczące są obsługiwane za pomocą dokumentu planu budżetu jako działania planowania początkowego. Prognozy kroczące mogą być wykonywane równolegle z planowaniem dla nachodzącego cyklu budżetowego.

-   [Budżetowanie podstawowe: omówienie i konfiguracja](basic-budgeting-overview-configuration.md)
-   [Kontrola budżetu: omówienie i konfiguracja](budget-control-overview-configuration.md)
-   [Planowanie budżetu: omówienie i konfiguracja](budget-planning-overview-configuration.md)
-   [Prognozowanie stanowisk](position-forecasting.md)
-   [Dokumenty uzasadniające planowania budżetu](budget-planning-justification-docs.md)
-   [Szablony programu Microsoft Excel do planowania budżetu](budget-planning-excel-templates.md)

## <a name="budgeting-tools-in-dynamics-365-for-operations"></a>Narzędzia budżetowania w programie Dynamics 365 for Operations
[![Narzędzia budżetowe](./media/budgeting-tools.jpg)](./media/budgeting-tools.jpg) 

Dodatkowe funkcje planowania i budżetowania są dostępne w całym programie Dynamics 365 for Operations i zintegrowane z budżetami księgi.

-   **Budżety siły roboczej** — Budżetowanie siły roboczej zawiera funkcję planowania składnika kosztu budżetu dla stanowisk, grupy wynagrodzeń itd.
-   **Budżety środków trwałych** — W oparciu o informacje dotyczące środków trwałych można obliczyć planowaną amortyzację i rejestrować inne planowane transakcje dotyczące środków trwałych.
-   **Budżety projektów** — W module projektów można tworzyć szczegółowe prognoz projektów. Prognozy projektów będą zawierać szczegóły o planowanych godzinach, wydatkach, opłatach i towarach.
-   ** Przewidywania potrzeb ** – na podstawie danych historycznych transakcji, można oszacować zapasów przyszłego popytu i tworzenie prognoz popytu.

Aby uzyskać informacje dotyczące przenoszenia danych planowania z innych modułów do planów budżetów, zobacz [Integracja modułu Planowanie budżetu z innymi modułami](budget-planning-integration-other-modules.md).

## <a name="user-interface-and-reporting-capabilities"></a>Interfejs użytkownika i funkcje raportowania
W programie Dynamics 365 for Operations użytkownicy mogą tworzyć plany budżetu bezpośrednio na kliencie Dynamics 365 for Operations (przy użyciu konfigurowalnej strony dokumentu planu budżetu) lub za pomocą programu Excel. Program Excel oferuje kilka dodatkowych funkcji. Można na przykład można użyć zewnętrznych danych jako źródła planu budżetu, wykonywać niestandardowe obliczenia oraz używać tabel przestawnych i wykresów programu Microsoft. Większość zmiennych w procesie planowania budżetu można skonfigurować. Na przykład można określić, kto wykonuje budżetowanie, co jest ujęte w budżecie, i jak wygląda proces. Mimo iż program Excel umożliwia planowanie budżetu, to program Dynamics 365 for Operations jest jedynym źródłem wiarygodnych informacji i pozwala uniknąć problemów z kontrolą budżetu. Okresowe procesy mogą służyć do wprowadzania do planu budżetu danych początkowych dla budżetowania. Na potrzeby raportowania program Dynamics 365 for Operations udostępnia zestaw stron standardowych zapytań, które umożliwiają wyświetlanie i analizowanie danych budżetowania. Dane planu budżetu można wyświetlić za pomocą programu Management Reporter, a poszczególne scenariusze planu budżetu mogą być wyświetlane jako kolumny w raporcie tego programu.





