---
title: Konfiguruj środowisko wersji zapoznawczej usługi Dynamics 365 Commerce
description: W tym temacie opisano sposób konfigurowania środowiska wersji zapoznawczej aplikacji Microsoft Dynamics 365 Commerce po jego aprowizacji.
author: psimolin
manager: annbe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: ad05996eaabd3965308370649a27b8bc3080c7ce
ms.sourcegitcommit: f72e90dccc80718e99cab2752eaf8931dcbb915e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/02/2020
ms.locfileid: "3534074"
---
# <a name="configure-a-dynamics-365-commerce-preview-environment"></a>Konfiguruj środowisko wersji zapoznawczej usługi Dynamics 365 Commerce


[!include [banner](includes/banner.md)]

W tym temacie opisano sposób konfigurowania środowiska wersji zapoznawczej aplikacji Microsoft Dynamics 365 Commerce po jego aprowizacji.

## <a name="overview"></a>Omówienie

Procedury opisane w tym temacie należy wykonać dopiero po zakończeniu aprowizacji środowiska wersji zapoznawczej usługi Commerce. Aby uzyskać informacje dotyczące sposobu aprowizowania środowiska wersji zapoznawczej usługi Commerce, zobacz [Aprowizowanie środowiska wersji zapoznawczej usługi Commerce](provisioning-guide.md).

Po zakończeniu kompleksowej aprowizacji środowiska wersji zapoznawczej usługi Commerce wykonać dodatkowe czynności konfiguracyjne po aprowizacji, aby można było rozpocząć ocenę środowiska. Aby wykonać te kroki, należy użyć usług Microsoft Dynamics Lifecycle Services (LCS) i Dynamics 365 Commerce.

## <a name="before-you-start"></a>Przed rozpoczęciem

1. Zaloguj się do [portalu usługi LCS](https://lcs.dynamics.com).
1. Przejdź do projektu.
1. W menu górnym wybierz opcję **Środowiska hostowane w chmurze**.
1. Wybierz swoje środowisko na liście.
1. W obszarze informacji o środowisku po prawej stronie wybierz pozycję **Pełne szczegóły**.
1. Wybierz pozycję **Zaloguj**, aby otworzyć menu, i wybierz opcję **Zaloguj do środowiska**.
1. Upewnij się, że wybrano firmę **USRT** w prawym górnym rogu.

## <a name="configure-the-point-of-sale-in-lcs"></a>Konfigurowanie punktu sprzedaży w usłudze LCS

### <a name="associate-a-worker-with-your-identity"></a>Kojarzenie pracownika z Twoją tożsamością

Aby skojarzyć pracownika z tożsamością w usłudze LCS, wykonaj następujące kroki.

1. Korzystając z menu po lewej stronie, przejdź do pozycji **Moduły \> Retail i Commerce \> Pracownicy etatowi \> Pracownicy**.
1. Na liście znajdź i wybierz następujący rekord: **000713 - Andrew Collette**.
1. W okienku akcji wybierz pozycję **Retail**.
1. Wybierz pozycję **Skojarz istniejącą tożsamość**.
1. W polu **Adres e-mail** na prawo od pola **Wyszukaj, używając poczty e-mail** wprowadź swój adres e-mail.
1. Wybierz opcję **Wyszukaj**.
1. Wybierz rekord ze swoją nazwą.
1. Kliknij przycisk **OK**.
1. Wybierz opcję **Zapisz**.

### <a name="activate-cloud-pos"></a>Aktywować punkt sprzedaży w chmurze

Aby aktywować punkt sprzedaży chmury w usłudze LCS, wykonaj następujące kroki.

1. W menu górnym wybierz opcję **Środowiska hostowane w chmurze**.
1. Wybierz swoje środowisko na liście.
1. W obszarze informacji o środowisku po prawej stronie wybierz pozycję **Pełne szczegóły**.
1. Wybierz pozycję **Zaloguj**, aby otworzyć menu, a następnie wybierz pozycję **Zaloguj się do punktu sprzedaży chmury**, aby otworzyć punkt sprzedaży.
1. Wybierz pozycję **Następny**.
1. Zaloguj się przy użyciu konta usługi Microsoft Azure Active Directory (Azure AD).
1. W polu **Nazwa sklepu** wybierz opcję **San Francisco**.
1. Wybierz pozycję **Następny**.
1. W obszarze **Rejestr i urządzenie** wybierz opcję **SANFRAN-1**.
1. Wybierz **Aktywuj**. Nastąpi wylogowanie i przeniesienia na stronę logowania w punkcie sprzedaży.
1. Teraz możesz zalogować się do środowiska punktu sprzedaży w chmurze przy użyciu identyfikatora operatora **000713** i hasła **123**.

## <a name="set-up-your-site-in-commerce"></a>Konfigurowanie witryny w usłudze Commerce

Aby rozpocząć konfigurowanie witryny w wersji zapoznawczej w usłudze Commerce, wykonaj następujące kroki.

1. Zaloguj się do narzędzia do zarządzania witryną przy użyciu adresu URL zanotowanego podczas inicjowania usługi e-Commerce w trakcie aprowizacji (zobacz [Inicjowanie usługi e-Commerce](provisioning-guide.md#initialize-e-commerce)).
1. Wybierz witrynę **Fabrikam**, aby otworzyć okno dialogowe konfiguracji witryny.
1. Wybierz domenę, która została wprowadzona podczas inicjowania aplikacji e-Commerce.
1. Wybierz opcję **Rozszerzony sklep online Fabrikam** jako kanał domyślny. (Upewnij się, że wybrano **rozszerzony** sklep internetowy).
1. Wybierz wartość **en-us** jako język domyślny.
1. Pozostaw niezmienioną wartość pola **Ścieżka**.
1. Kliknij przycisk **OK**. Zostanie wyświetlona lista stron w witrynie.

## <a name="enable-jobs"></a>Włącz zadania

Aby włączyć zadania w aplikacji Commerce, wykonaj następujące kroki.

1. Zaloguj się do środowiska (HQ).
1. Korzystając z menu po lewej stronie, przejdź do pozycji **Retail i Commerce \> Zapytania i raporty \> Zadania wsadowe**.

    Pozostałe kroki tej procedury muszą zostać zakończone dla każdego z następujących zadań:

    * Przetwarzanie powiadomień pocztą e-mail dla zamówienia sieci sprzedaży
    * Dostępność produktu
    * P-0001
    * Zadanie synchronizowania zamówień

1. Użyj szybkiego filtru, aby wyszukać zadanie według nazwy.
1. Jeśli stan zadania to **Wstrzymane**, wykonaj następujące kroki:

    1. Wybierz rekord.
    1. W okienku akcji na karcie **Zadanie wsadowe** wybierz pozycję **Zmień status**.
    1. Wybierz pozycję **Oczekiwanie** i kliknij przycisk **OK**.

### <a name="run-full-data-synchronization"></a>Uruchamianie pełnej synchronizacji danych

Aby uruchomić pełną synchronizację danych w aplikacji Commerce, wykonaj następujące kroki.

1. Korzystając z menu po lewej stronie, przejdź do pozycji **Moduły \> Handel detaliczny i inny \> Ustawienia centrali \> Transfer danych w Commerce \> Baza danych kanału**.
1. Na liście po lewej stronie jest wybrany kanał **domyślny**. Wybierz inny dostępny kanał. Ten kanał nosi nazwę **scXXXXXXXXX**.
1. W okienku akcji wybierz **Pełna synchronizacja danych**.
1. Wpisz **9999** jako harmonogram dystrybucji.
1. Kliknij przycisk **OK**.
1. Kliknij przycisk **OK**.

### <a name="test-credit-card-information-to-do-test-purchases"></a>Testowanie informacji o karcie kredytowej w celu dokonania zakupów testowych

Aby przeprowadzić transakcje testowe w witrynie, można użyć następujących testowych informacji o karcie kredytowej:

- **Numer karty:** 4111-1111-1111-1111
- **Data ważności:** 10/20
- **Kod wartości weryfikacji karty (CVV):** 737

> [!IMPORTANT]
> Nigdy w żadnym wypadku nie próbuj używać rzeczywistych informacji o karcie kredytowej w witrynie testowej.

## <a name="next-steps"></a>Następne kroki

Po zakończeniu aprowizowania i wykonaniu kroków konfiguracji można przystąpić do oceny środowiska wersji zapoznawczej. Użyj adresu URL narzędzia do zarządzania witryną Commerce, aby przejść do środowiska tworzenia. Użyj adresu URL witryny Commerce, aby przejść do środowiska witryny klienta platformy handlu detalicznego.

Aby skonfigurować opcjonalne funkcje środowiska wersji zapoznawczej usługi Commerce, zobacz [Konfigurowanie funkcji opcjonalnych środowiska wersji zapoznawczej usługi Commerce](cpe-optional-features.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Dynamics 365 Commerce omówienie środowiska wersji zapoznawczej](cpe-overview.md)

[Inicjuj środowisko wersji zapoznawczej Dynamics 365 Commerce](provisioning-guide.md)

[Konfiguruj funkcje opcjonalne środowiska wersji zapoznawczej usługi Dynamics 365 Commerce](cpe-optional-features.md)

[Środowisko wersji zapoznawczej Dynamics 365 Commerce— często zadawane pytania](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portal Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Witryna Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)
