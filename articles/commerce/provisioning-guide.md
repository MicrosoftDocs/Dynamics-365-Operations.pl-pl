---
title: Ustanów środowisko piaskownicy usługi Dynamics 365 Commerce
description: W tym artykule opisano, jak ustanowić środowisko piaskownicy usługi Microsoft Dynamics 365 Commerce do użycia w wersji demonstracyjnej lub piaskownicy ze wbudowanymi danymi demonstracyjnymi.
author: psimolin
ms.date: 06/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 3ada30fc9d86d236b71d018ef77f2ae8573f2285
ms.sourcegitcommit: 252cb41c3029b623354698463f7b44a29fd9f184
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/15/2022
ms.locfileid: "9013143"
---
# <a name="provision-a-dynamics-365-commerce-sandbox-environment"></a>Ustanów środowisko piaskownicy usługi Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

W tym artykule opisano, jak ustanowić środowisko piaskownicy usługi Microsoft Dynamics 365 Commerce do użycia w wersji demonstracyjnej ze wbudowanymi danymi demonstracyjnymi. Proces konfigurowania środowiska produkcyjnego jest podobny, ale bardziej rozbudowany, ponieważ wiele wymagań wstępnych środowiska piaskownicy jest już podanych w danych demonstracyjnych.

Przed rozpoczęciem zalecane jest wykonanie szybkiego przeglądu tego artykułu w celu uzyskania informacji na temat wymaganego procesu.

Aby pomyślnie ustanowić środowisko piaskownicy usługi Commerce, należy określić kilka parametrów środowiska oraz Commerce Scale Unit (CSU), które będą używane podczas późniejszego ustanawiania usługi Commerce. Instrukcje w tym artykule opisują wszystkie wymagane kroki do zakończenia aprowizowania i parametry, których należy użyć.

Po pomyślnym ustanowieniu środowiska rozwiązania Commerce istnieje kilka kroków aprowizacji, które należy wykonać, aby przygotować to środowisko do użytku. Niektóre kroki są opcjonalne, w zależności od aspektów systemu, które mają być używane. Opcjonalne kroki można wykonać później.

Aby uzyskać informacje dotyczące sposobu konfigurowania środowiska usługi Commerce po jego aprowizowaniu, zobacz [Konfigurowanie środowiska piaskownicy usługi Commerce](cpe-post-provisioning.md). Aby uzyskać informacje dotyczące sposobu konfigurowania opcjonalnych funkcji środowiska usługi Commerce, zobacz [Konfigurowanie funkcji opcjonalnych środowiska piaskownicy usługi Commerce](cpe-optional-features.md).

## <a name="prerequisites"></a>Wymagania wstępne

Zanim będzie można ustanowienia środowisko usługi Commerce, muszą zostać spełnione następujące wymagania wstępne:

- Masz dostęp do portalu Lifecycle Services (LCS) rozwiązania Microsoft Dynamics.
- Jesteś istniejącym partnerem lub klientem usługi Microsoft Dynamics 365 i masz już utworzony projekt implementacji, który będzie dostępny do użycia w usługach LCS.  
- Utworzono grupę zabezpieczeń usługi Azure Active Directory (Azure AD), która ma być używana jako grupa administratorów rozwiązania Commerce i jest dostępny jej identyfikator.
- Utworzono grupę zabezpieczeń usługi Azure AD, która ma być używana jako grupa moderatorów ocen i recenzji, i jest dostępny jej identyfikator. (Ta grupa zabezpieczeń może być taka sama jak grupa administratorów rozwiązania Commerce).
- Wdrożono wystąpienie centrali w usługach LCS. Aby uzyskać więcej informacji, zobacz [Wdrażanie nowego środowiska](/dynamics365/fin-ops-core/dev-itpro/deployment/deployenvironment-newinfrastructure).

Należy zauważyć, że ta lista nie wymienia wszystkiego. Jeśli napotkasz jakiekolwiek problemy, skontaktuj się z partnerem Microsoft w celu uzyskania pomocy.

## <a name="provision-your-commerce-environment"></a>Ustanawianie środowiska usługi Commerce

Poniższe procedury wyjaśniają, jak ustanowić środowisko rozwiązania Commerce. Po ich pomyślnym ukończeniu środowisko usługi Commerce będzie gotowe do konfiguracji. Wszystkie opisane poniżej kroki są wykonywane w portalu usługi LCS.

### <a name="initialize-the-commerce-scale-unit-cloud"></a>Inicjowanie Commerce Scale Unit (w chmurze)

Aby zainicjować jednostkę CSU, należy wykonać następujące kroki.

1. W portalu LCS wybierz swoje środowisko z listy.
1. W widoku **ŚRODOWISKA** po prawej stronie wybierz pozycję **Pełne szczegóły**. Zostanie wyświetlony widok szczegółów środowiska.
1. W sekcji **Zarządzaj środowiskiem** w obszarze **FUNKCJE ŚRODOWISKA** wybierz pozycję **Zarządzaj**.
1. Na karcie **Commerce Scale Units** wybierz pozycję **Inicjuj**. Zostanie wyświetlony widok **Dodaj jednostkę skalowania**.
1. W polu **REGION** wybierz region, który jest taki sam lub podobny do regionu, do którego wdrożono środowisko.
1. Z listy rozwijanej **Wersja** wybierz najnowszą dostępną wersję.
1. Wybierz pozycję **Inicjuj**.
1. W oknie dialogowym ostrzeżenia z pytaniem o potwierdzenie zainicjowania Commerce Scale Unit wybierz opcję **Tak**. CSU zostało teraz dodane do kolejki w celu zainicjowania obsługi administracyjnej.
1. Przed kontynuowaniem upewnij się, że stan jednostki CSU to **POWODZENIE**. Inicjowanie trwa około dwóch do pięciu godzin.

Jeśli nie możesz znaleźć łącza **Zarządzaj** w widoku Szczegóły środowiska, skontaktuj się z osobą kontaktową z firmą Microsoft w celu uzyskania pomocy.

### <a name="initialize-e-commerce"></a>Inicjalizowanie e-Commerce

Aby zainicjować usługę Commerce, należy wykonać następujące kroki.

1. Na karcie **e-Commerce** wybierz opcję **ustawienia**.
1. W polu **Nazwa środowiska handlu elektronicznego** wprowadź nazwę. Należy mieć świadomość, że nazwa ta będzie widoczne w niektórych adresach URL wskazujących na to wystąpienie handlu elektronicznego.
1. W polu **Nazwa Commerce Scale Unit** wybierz z listy jednostkę CSU. (Lista powinna mieć tylko jedną opcję).

    Pole **Geografia handlu elektronicznego** jest ustawiane automatycznie.

1. Wybierz przycisk **Dalej**, aby kontynuować.
1. W polu **Obsługiwane nazwy hostów** wprowadź dowolną prawidłową domenę, na przykład `www.fabrikam.com`.
1. W polu **Grupa zabezpieczeń usługi AAD dla administratora systemu** wprowadź kilka pierwszych liter nazwy grupy zabezpieczeń, której chcesz użyć, a następnie wybierz symbol lupy, aby wyświetlić wyniki wyszukiwania. Wybierz prawidłową grupę zabezpieczeń na liście.
1.  W polu **Grupa zabezpieczeń usługi AAD dla moderatora ocen i recenzji** wprowadź kilka pierwszych liter nazwy grupy zabezpieczeń, której chcesz użyć, a następnie wybierz symbol lupy, aby wyświetlić wyniki wyszukiwania. Wybierz prawidłową grupę zabezpieczeń na liście.
1. Zostaw opcję **Włącz obsługę ocen i recenzji** ustawioną na wartość **Tak**.
1. Wybierz pozycję **Inicjuj**. Widok **Zarządzanie handlem** jest wyświetlany ponownie, jeśli jest wybrana karta **e-Commerce**. Inicjowanie usługi e-Commerce zostało rozpoczęte.
1. Przed kontynuowaniem poczekaj, aż stan inicjowania usługi Commerce zmieni się na **INICJOWANIE ZAKOŃCZONE POWODZENIEM**.
1. W prawym dolnym rogu sekcji **Linki** zanotuj adresy URL następujących linków:

    * **Witryna usługi e-Commerce** — link do katalogu głównego witryny usługi e-Commerce.
    * **Konstruktor witryn handlu elektronicznego** — link do narzędzia do zarządzania witryną.

## <a name="next-steps"></a>Następne kroki

Aby kontynuować proces aprowizowania i konfigurowania środowiska usługi Commerce, zobacz [Konfigurowanie środowiska piaskownicy usługi Commerce](cpe-post-provisioning.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfiguruj środowisko piaskownicy usługi Dynamics 365 Commerce](cpe-post-provisioning.md)

[Konfigurowanie BOPIS w środowisku piaskownicy Dynamics 365 Commerce](cpe-bopis.md)

[Konfiguruj funkcje opcjonalne środowiska piaskownicy usługi Dynamics 365 Commerce](cpe-optional-features.md)

[Microsoft Lifecycle Services (LCS)](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Commerce Scale Unit (w chmurze)](/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portal Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Witryna Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
