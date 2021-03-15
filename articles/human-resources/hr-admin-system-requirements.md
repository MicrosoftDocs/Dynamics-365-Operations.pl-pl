---
title: Wymagania systemowe
description: W tym artykule opisano wymagania dotyczące rozwiązania Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1e7d7389c1bcf0f6024464e37b36d39efae5b832
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2021
ms.locfileid: "5113826"
---
# <a name="system-requirements"></a>Wymagania systemowe

W tym artykule opisano wymagania dotyczące rozwiązania Microsoft Dynamics 365 Human Resources. Zawiera także opis krajów i regionów, w których jest dostępne rozwiązanie Human Resources oraz informacje na temat języków i lokalizacji danych aplikacji Human Resources.

## <a name="supported-web-browsers"></a>Obsługiwane przeglądarki

Human Resources może działać w każdej z poniższych przeglądarek w kombinacji z określonym systemem operacyjnym: 

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
> * Program Human Resources jest zaprojektowany dla sieci o opóźnieniu nieprzekraczającym 250-300 milisekund (ms). Jest to opóźnienie na drodze od klienta przeglądarki do centrum danych Microsoft Azure zawierającego usługę Human Resources. Zaleca się przetestowanie opóźnienia w sieci na stronie [www.azurespeed.com](https://www.azurespeed.com "Test opóźnienia w łączności z usługą Azure").
> * Wymagania dotyczące przepustowości dla usługi Human Resources zależą od konkretnego scenariusza. Większość typowych scenariuszy wymaga przepustowości powyżej 50 kilobajtów na sekundę (KB/s).
> 
> [!WARNING]
> Nie obliczaj wymagań dotyczących przepustowości z lokalizacji klienta poprzez pomnożenie liczby użytkowników przez minimalną wymaganą przepustowość. Równoczesne użytkowanie danej lokalizacji przez wiele osób jest bardzo trudne do obliczenia. Dla odbiorców, którzy się boją, że ciężko będzie im spełnić wymagania dotyczące przepustowości, użyj wersji próbnej Human Resources.

## <a name="supported-microsoft-office-applications"></a>Obsługiwane aplikacje pakietu Microsoft Office

* Aby można było uruchamiać dodatki programów Microsoft Excel i Word, musi być zainstalowany pakiet Microsoft Office 2016 dla systemu Windows lub Mac. Aby uzyskać więcej szczegółów na temat wymagań dotyczących wersji, zobacz [Rozwiązywanie problemów z integracją pakietu Office](../dev-itpro/office-integration/office-integration-troubleshooting.md "Rozwiązywanie problemów z integracją z pakietem Office").
* Aby wyświetlać dokumenty generowane przez funkcję Eksportuj do programu Excel lub Eksportuj do programu Word, należy mieć zainstalowany pakiet Microsoft Office 2007 lub nowszy.

## <a name="regional-availability-languages-and-localization"></a>Regionalna dostępność, Języki i lokalizacja

Można pobrać plik PDF zawierający listy krajów, regionów i języków obsługiwanych w aplikacji Human Resources [międzynarodowa dostępność Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability). 

> [!NOTE]
> Gdy interfejs użytkownika jest zlokalizowany w innych językach, wszystkie dane użytkownika są przechowywane w języku, w którym zostały wprowadzone. Możesz tworzyć wiadomości e-mail i szablony w innych językach, ale dane, takie jak informacje o harmonogramie, są w tej chwili dostępne tylko w języku angielskim.

Jeśli jesteś programistą zainteresowanym tworzeniem dostosowań specyficznych dla kraju lub regionu lub stworzeniem rozwiązania dla kraju lub regionu, który nie jest obecnie obsługiwany przez firmę Microsoft, zobacz [Globalizacja](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region).


[!INCLUDE[footer-include](../includes/footer-banner.md)]