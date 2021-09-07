---
title: Konfigurowanie środowiska oceny rozwiązania Dynamics 365 Commerce
description: W tym temacie opisano sposób konfigurowania środowiska oceny aplikacji Microsoft Dynamics 365 Commerce po jego aprowizacji.
author: psimolin
ms.date: 08/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 2e98ea9e98380ee63f6cc1eb6dfc7b84d38c7dbb
ms.sourcegitcommit: 259ba130450d8a6d93a65685c22c7eb411982c92
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/24/2021
ms.locfileid: "7416486"
---
# <a name="configure-a-dynamics-365-commerce-evaluation-environment"></a>Konfigurowanie środowiska oceny rozwiązania Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

W tym temacie opisano sposób konfigurowania środowiska oceny aplikacji Microsoft Dynamics 365 Commerce po jego aprowizacji.

Procedury opisane w tym temacie należy wykonać dopiero po zakończeniu aprowizacji środowiska oceny usługi Commerce. Aby uzyskać informacje dotyczące sposobu aprowizowania środowiska oceny usługi Commerce, zobacz [Aprowizowanie środowiska oceny usługi Commerce](provisioning-guide.md).

Po zakończeniu kompleksowej aprowizacji środowiska oceny usługi Commerce wykonać dodatkowe czynności konfiguracyjne po aprowizacji, aby można było rozpocząć ocenę środowiska. Aby wykonać te kroki, należy użyć usług Microsoft Dynamics Lifecycle Services (LCS) i Dynamics 365 Commerce.

## <a name="before-you-start"></a>Przed rozpoczęciem

1. Zaloguj się do [portalu usługi LCS](https://lcs.dynamics.com).
1. Przejdź do projektu.
1. W menu górnym wybierz opcję **Środowiska hostowane w chmurze**.
1. Wybierz swoje środowisko na liście.
1. W obszarze informacji o środowisku po prawej stronie wybierz pozycję **Zaloguj do środowiska**. Nastąpi wysłanie do modułu Commerce Headquarter.
1. Upewnij się, że wybrano firmę **USRT** w prawym górnym rogu.

Podczas wykonywania działań związanych z inicjowaniem obsługi administracyjnej w module Commerce Headquarter należy się upewnić, że firma **USRT** jest zawsze zaznaczona.

## <a name="configure-the-point-of-sale"></a>Konfigurowanie punktu sprzedaży

### <a name="associate-a-worker-with-your-identity"></a>Kojarzenie pracownika z Twoją tożsamością

Aby skojarzyć pracownika z tożsamością, wykonaj następujące kroki w Commerce Headquarters.

1. Korzystając z menu po lewej stronie, przejdź do pozycji **Moduły \> Retail i Commerce \> Pracownicy etatowi \> Pracownicy**.
1. Na liście znajdź i wybierz następujący rekord: **000713 - Andrew Collette**.
1. W okienku akcji wybierz **Commerce**.
1. Wybierz pozycję **Skojarz istniejącą tożsamość**.
1. W polu **Adres e-mail** na prawo od pola **Wyszukaj, używając poczty e-mail** wprowadź swój adres e-mail.
1. Wybierz opcję **Wyszukaj**.
1. Wybierz rekord ze swoją nazwą.
1. Kliknij przycisk **OK**.
1. Wybierz opcję **Zapisz**.

### <a name="activate-cloud-pos"></a>Aktywować punkt sprzedaży w chmurze

Aby aktywować punkt sprzedaży chmury, wykonaj następujące kroki w usłudze LCS.

1. W menu górnym wybierz opcję **Środowiska hostowane w chmurze**.
1. Wybierz swoje środowisko na liście.
1. W obszarze informacji o środowisku po prawej stronie wybierz pozycję **Zaloguj do punktu sprzedaży w chmurze**.
1. Wybierz przycisk **Dalej**, aby otworzyć okno dialogowe **Przed rozpoczęciem**.
1. Pole **Serwer URL** powinno pozostać niezmienione. Wybierz pozycję **Następny**.
1. Zaloguj się przy użyciu konta usługi Microsoft Azure Active Directory (Azure AD).
1. W polu **Nazwa sklepu** wybierz opcję **San Francisco**, a następnie wybierz przycisk **Dalej**.
1. W obszarze **Rejestr i urządzenie** wybierz opcję **SANFRAN-1**.
1. Wybierz **Aktywuj**. Nastąpi wylogowanie i przeniesienia na stronę logowania w punkcie sprzedaży.
1. Teraz możesz zalogować się do środowiska punktu sprzedaży w chmurze przy użyciu identyfikatora operatora **000713** i hasła **123**.

## <a name="set-up-your-site-in-commerce"></a>Konfigurowanie witryny w usłudze Commerce

Aby rozpocząć konfigurowanie witryny oceny w usłudze Commerce, wykonaj następujące kroki.

1. Zaloguj się do konstruktora witryny przy użyciu adresu URL zanotowanego podczas inicjowania usługi handlu elektronicznego w trakcie aprowizacji (zobacz [Inicjowanie usługi handlu elektronicznego](provisioning-guide.md#initialize-e-commerce)).
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
1. Jeśli stan zadania to **W trakcie**, wykonaj następujące kroki:

    1. Wybierz rekord.
    1. W okienku akcji na karcie **Zadanie wsadowe** wybierz pozycję **Zmień status**.
    1. Wybierz pozycję **Anuluj**, a następnie kliknij przycisk **OK**.

Opcjonalnie można również określić interwał cyklu równy jednej (1) minucie dla następujących zadań:

* Przetwarzanie zadania powiadomień pocztą e-mail dla zamówienia sieci sprzedaży
* Zadanie P-0001
* Zadanie synchronizowania zamówień

### <a name="run-full-data-synchronization"></a>Uruchamianie pełnej synchronizacji danych

Aby uruchomić pełną synchronizację danych w aplikacji Commerce, wykonaj następujące kroki w Commerce headquarters.

1. Korzystając z menu po lewej stronie, przejdź do pozycji **Moduły \> Handel detaliczny i inny \> Ustawienia centrali \> Transfer danych w Commerce \> Baza danych kanału**.
1. Wybierz kanał o nazwie **scXXXXXXXXX**.
1. W okienku akcji wybierz **Pełna synchronizacja danych**.
1. Wpisz **9999** jako harmonogram dystrybucji.
1. Kliknij przycisk **OK**.
1. Kliknij przycisk **OK**.

### <a name="test-credit-card-information-to-do-test-purchases"></a>Testowanie informacji o karcie kredytowej w celu dokonania zakupów testowych

Aby przeprowadzić transakcje testowe w witrynie, można użyć następujących testowych informacji o karcie kredytowej:

- **Numer karty:** 4111-1111-1111-1111
- **Data ważności:** 10/30
- **Kod wartości weryfikacji karty (CVV):** 737

> [!IMPORTANT]
> Nigdy w żadnym wypadku nie próbuj używać rzeczywistych informacji o karcie kredytowej w witrynie testowej.

## <a name="next-steps"></a>Następne kroki

Po zakończeniu czynności obsługi administracyjnej i konfiguracji można rozpocząć korzystanie ze środowiska oceny. Użyj adresu URL konstruktora witryn Commerce, aby przejść do środowiska tworzenia. Użyj adresu URL witryny Commerce, aby przejść do środowiska witryny klienta platformy handlu detalicznego.

Aby skonfigurować opcjonalne funkcje środowiska oceny usługi Commerce, zobacz [Konfigurowanie funkcji opcjonalnych środowiska oceny usługi Commerce](cpe-optional-features.md).

> [!NOTE]
> Środowiska oceniania handlu są wstępnie załadowane do dzierżawy Azure Active Directory (Azure AD) B2C (business-to-consumer) w celach demonstracyjnych. Konfigurowanie własnej dzierżawy Azure AD B2C nie jest wymagane w przypadku środowisk oceniania. Jeśli jednak środowisko oceniania jest konfigurowane w celu korzystania z własnej dzierżawy Azure AD, należy dodać ``https://login.commerce.dynamics.com/_msdyn365/authresp`` jako adres URL odpowiedzi w aplikacji Azure AD B2C za pośrednictwem Azure Portal.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie środowiska oceny usługi Dynamics 365 Commerce](cpe-overview.md)

[Ustanowienie środowiska oceny Dynamics 365 Commerce](provisioning-guide.md)

[Konfigurowanie opcjonalnych funkcji środowiska oceny Dynamics 365 Commerce](cpe-optional-features.md)

[Konfigurowanie BOPIS w środowisku oceny Dynamics 365 Commerce](cpe-bopis.md)

[Środowiska oceny usługi Dynamics 365 Commerce — często zadawane pytania](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portal Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Witryna Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)

[Konfigurowanie dzierżawy B2C w module Commerce](set-up-B2C-tenant.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
