---
title: Wymagania systemowe
description: W tym temacie podano wymagania systemowe programu Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 15770595a0639c03df1138ec25010ca8168bd9a8
ms.sourcegitcommit: 49f7528d3268abe15e40f719956e1ec8696a6f4e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/18/2021
ms.locfileid: "7393480"
---
# <a name="system-requirements"></a>Wymagania systemowe

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie podano wymagania systemowe programu Microsoft Dynamics 365 Human Resources. Zawiera także opis krajów i regionów, w których jest dostępne rozwiązanie Human Resources oraz informacje na temat języków i lokalizacji danych aplikacji Human Resources.

## <a name="supported-web-browsers"></a>Obsługiwane przeglądarki

Dostęp do programu Microsoft Dynamics 365 Human Resources można uzyskać w każdej z poniższych przeglądarek w kombinacji z określonym systemem operacyjnym: 

*   Microsoft Edge (najnowsza publicznie dostępna wersja) w systemie Windows 10
*   Internet Explorer 11 w systemach Windows 10, Windows 8.1 lub Windows 7
*   Google Chrome (najnowsza publicznie dostępna wersja)
*   Apple Safari (najnowsza publicznie dostępna wersja)

Aby znaleźć najnowszą wersję dla każdej przeglądarki, przejdź do witryny producenta oprogramowania. 

## <a name="special-considerations"></a>Specjalne uwagi

* Aby umożliwić przechwytywanie zrzutów ekranu przez Rejestrator zadań i umieszczanie ich w generowanych dokumentach programu Microsoft Word, należy zainstalować wstępną wersję rozszerzenia dla przeglądarki Chrome.
* Edytor przepływu pracy jest uruchamiany jako aplikacja ClickOnce. Aplikacje ClickOnce są obsługiwane tylko w przeglądarkach Microsoft Edge i Internet Explorer (w obsługiwanych wersjach systemu Microsoft Windows). Aplikacja ClickOnce edytora przepływu pracy wymaga zgodnego 64-bitowego systemu operacyjnego.
* Aby wyświetlać podgląd plików PDF, zalecamy używanie nowoczesnych przeglądarek, takich jak Microsoft Edge (nowszej publicznie dostępnej wersji) w systemie Windows 10 lub Google Chrome (nowszej publicznie dostępnej wersji) w systemach Windows 10, Windows 8.1, Windows 8 i Windows 7 lub na tablecie Google Nexus 10.

## <a name="network-requirements"></a>Wymagania sieciowe

* Program Human Resources jest zaprojektowany dla sieci o opóźnieniu nieprzekraczającym 250-300 milisekund (ms). Jest to opóźnienie na drodze od klienta przeglądarki do centrum danych Microsoft Azure zawierającego usługę Human Resources. Zaleca się przetestowanie opóźnienia w sieci na stronie [www.azurespeed.com](https://www.azurespeed.com "Test opóźnienia w łączności z usługą Azure").
* Wymagania dotyczące przepustowości dla usługi Human Resources zależą od konkretnego scenariusza. W typowych scenariuszach wymagana jest przepustowość powyżej 50 kilobajtów na sekundę (KB/s).
 
> [!WARNING]
> Nie obliczaj wymagań dotyczących przepustowości z lokalizacji klienta poprzez pomnożenie liczby użytkowników przez minimalną wymaganą przepustowość. Równoczesne użytkowanie danej lokalizacji przez wiele osób jest bardzo trudne do obliczenia. Dla odbiorców, którzy się boją, że ciężko będzie im spełnić wymagania dotyczące przepustowości, użyj wersji próbnej Human Resources.

## <a name="supported-microsoft-office-applications"></a>Obsługiwane aplikacje pakietu Microsoft Office

* Aby można było uruchamiać dodatki programów Microsoft Excel i Word, musi być zainstalowany pakiet Microsoft Office 2016 dla systemu Windows lub Mac. Aby uzyskać więcej szczegółów na temat wymagań dotyczących wersji, zobacz [Rozwiązywanie problemów z integracją pakietu Office](../fin-ops-core/dev-itpro/office-integration/office-integration-troubleshooting.md "Rozwiązywanie problemów z integracją z pakietem Office").
* Aby wyświetlać dokumenty generowane przez funkcję Eksportuj do programu Excel lub Eksportuj do programu Word, należy mieć zainstalowany pakiet Microsoft Office 2007 lub nowszy.

## <a name="regional-availability-languages-and-localization"></a>Regionalna dostępność, Języki i lokalizacja

Można pobrać plik PDF zawierający listy krajów, regionów i języków obsługiwanych w aplikacji Human Resources [międzynarodowa dostępność Microsoft Dynamics 365](/dynamics365/get-started/availability). 

> [!NOTE]
> Gdy interfejs użytkownika jest zlokalizowany w innych językach, wszystkie dane użytkownika są przechowywane w języku, w którym zostały wprowadzone. Możesz tworzyć wiadomości e-mail i szablony w innych językach, ale dane, takie jak informacje o harmonogramie, są w tej chwili dostępne tylko w języku angielskim.

Jeśli jesteś programistą zainteresowanym tworzeniem dostosowań specyficznych dla kraju lub regionu lub stworzeniem rozwiązania dla kraju lub regionu, który nie jest obecnie obsługiwany przez firmę Microsoft, zobacz [Globalizacja](/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
