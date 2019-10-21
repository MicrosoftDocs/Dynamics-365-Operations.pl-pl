---
title: Wymagania systemowe i zasady aktualizacji rozwiązania Talent
description: W tym temacie podano wymagania dotyczące programu Dynamics 365 Talent. Opisano w nim także zasady aktualizacji.
author: andreabichsel
manager: AnnBe
ms.date: 05/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 63213
ms.assetid: 5dbc62fc-0184-4c0e-9856-e735fc68799e
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: b8bf44fc76be968b0b04fd894c39b4c19fd374ce
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2019
ms.locfileid: "2024167"
---
# <a name="talent-system-requirements-and-update-policy"></a>Wymagania systemowe i zasady aktualizacji rozwiązania Talent

[!include [banner](includes/banner.md)]

W tym temacie opisano wymagania dotyczące rozwiązania Microsoft Dynamics 365 Talent, w tym Attract, Onboard i Core HR. Zawiera także opis krajów i regionów, w których jest dostępne rozwiązanie Talent oraz informacje na temat języków i lokalizacji danych aplikacji Talent. Ponadto temat ten zawiera zasady aktualizacji dla aplikacji Talent.

## <a name="supported-web-browsers"></a>Obsługiwane przeglądarki

Microsoft Dynamics 365 Talent może działać w każdej z poniższych przeglądarek w kombinacji z określonym systemem operacyjnym: 

*   Microsoft Edge (najnowsza publicznie dostępna wersja) w systemie Windows 10
*   Internet Explorer 11 w systemach Windows 10, Windows 8.1 lub Windows 7
*   Google Chrome (najnowsza publicznie dostępna wersja)
*   Apple Safari (najnowsza publicznie dostępna wersja)

Aby znaleźć najnowszą wersję dla każdej przeglądarki, przejdź do witryny producenta oprogramowania. 

> [!NOTE]
> * Aby przechwytywać obrazy generowane z Rejestratora zadań i umieszczać je w dokumentach programu Microsoft Word, musisz mieć zainstalowane rozszerzenie dla przeglądarki Chrome. 
> * Edytor przepływu pracy jest uruchamiany jako aplikacja ClickOnce. Aplikacje ClickOnce są obsługiwane tylko w przeglądarkach Microsoft Edge i Internet Explorer (w obsługiwanych wersjach systemu Microsoft Windows). Aplikacja ClickOnce edytora przepływu pracy wymaga zgodnego 64-bitowego systemu operacyjnego.
> * Aby wyświetlać podgląd plików PDF, zalecamy używanie nowoczesnych przeglądarek, takich jak Microsoft Edge (nowszej publicznie dostępnej wersji) w systemie Windows 10 lub Google Chrome (nowszej publicznie dostępnej wersji) w systemach Windows 10, Windows 8.1, Windows 8 i Windows 7 lub na tablecie Google Nexus 10.
>   Wymagania sieciowe
> * Program Dynamics 365 Talent jest zaprojektowany dla sieci o opóźnieniu nieprzekraczającym 250-300 milisekund (ms). Jest to opóźnienie na drodze od klienta przeglądarkowego do centrum danych Microsoft Azure zawierającego usługę Talent. Zaleca się przetestowanie opóźnienia w sieci na stronie [www.azurespeed.com](https://www.azurespeed.com "Test opóźnienia w łączności z usługą Azure").
> * Wymagania dotyczące przepustowości dla usługi Talent zależą od konkretnego scenariusza. Większość typowych scenariuszy wymaga przepustowości powyżej 50 kilobajtów na sekundę (KB/s).
> 
> [!WARNING]
> Nie obliczaj wymagań dotyczących przepustowości z lokalizacji klienta poprzez pomnożenie liczby użytkowników przez minimalną wymaganą przepustowość. Równoczesne użytkowanie danej lokalizacji przez wiele osób jest bardzo trudne do obliczenia. Dla odbiorców, którzy się boją, że ciężko będzie im spełnić wymagania dotyczące przepustowości, użyj wersji próbnej Talent.

## <a name="supported-microsoft-office-applications"></a>Obsługiwane aplikacje pakietu Microsoft Office

* Aby można było uruchamiać dodatki programów Microsoft Excel i Word, musi być zainstalowany pakiet Microsoft Office 2016 dla systemu Windows lub Mac. Aby uzyskać więcej szczegółów na temat wymagań dotyczących wersji, zobacz [Rozwiązywanie problemów z integracją pakietu Office](../dev-itpro/office-integration/office-integration-troubleshooting.md "Rozwiązywanie problemów z integracją pakietu Office").
* Aby wyświetlać dokumenty generowane przez funkcję Eksportuj do programu Excel lub Eksportuj do programu Word, należy mieć zainstalowany pakiet Microsoft Office 2007 lub nowszy.

## <a name="regional-availability-languages-and-localization"></a>Regionalna dostępność, Języki i lokalizacja

Można pobrać plik PDF zawierający listy krajów, regionów i języków obsługiwanych w aplikacji Talent [międzynarodowa dostępność Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability). 

> [!NOTE]
> Gdy interfejs użytkownika jest zlokalizowany w innych językach, wszystkie dane użytkownika są przechowywane w języku, w którym zostały wprowadzone. Możesz tworzyć wiadomości e-mail i szablony w innych językach, ale dane, takie jak informacje o harmonogramie, są w tej chwili dostępne tylko w języku angielskim.

Jeśli jesteś programistą zainteresowanym tworzeniem dostosowań specyficznych dla kraju lub regionu lub stworzeniem rozwiązania dla kraju lub regionu, który nie jest obecnie obsługiwany przez firmę Microsoft, zobacz [Globalizacja](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region).

## <a name="update-policy"></a>Zasady aktualizacji

Talent jest udostępniany jako rozwiązanie chmurowe. Aktualizacje Talent są dodawane w sposób ciągły i stosowane automatycznie przez firmę Microsoft.

Aktualizacje są publikowane regularnie i dla wszystkich środowisk. Talent jest wspierany zgodnie z [zasadami cyklu życia pomocy technicznej Microsoft](https://support.microsoft.com/gp/lifecycle#gp/OSSLpolicy "Cykl życia pomocy technicznej Microsoft"), które określają spójny i przewidywalny harmonogram dostępności wsparcia technicznego dla produktów.
