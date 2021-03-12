---
title: Ustanowienie środowiska oceny rozwiązania Dynamics 365 Commerce
description: W tym temacie opisano sposób aprowizowania środowiska oceny aplikacji Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 12/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
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
ms.openlocfilehash: 8cda79a6be1aca7ad3826b9409e110524e6560e3
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969908"
---
# <a name="provision-a-dynamics-365-commerce-evaluation-environment"></a>Ustanowienie środowiska oceny rozwiązania Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

W tym temacie opisano sposób aprowizowania środowiska oceny aplikacji Microsoft Dynamics 365 Commerce.

Przed rozpoczęciem zalecane jest wykonanie szybkiego przeglądu tego tematu w celu uzyskania informacji na temat wymaganego procesu.

> [!NOTE]
> Środowiska testowe w handlu są zazwyczaj niedostępne i są przyznawane partnerom i odbiorcom na żądanie. Aby uzyskać więcej informacji, skontaktuj się z partnerem firmy Microsoft.

## <a name="overview"></a>Omówienie

Aby pomyślnie aprowizować środowisko oceny rozwiązania Commerce, musisz utworzyć projekt, który ma określoną nazwę i typ produktu. Środowisko i Commerce Scale Unit (CSU) mają także określone parametry, których należy użyć w celu spodziewanego późniejszego aprowizowania na platformie handlu elektronicznego. Instrukcje w tym temacie opisują wszystkie wymagane kroki do zakończenia aprowizowania i parametry, których należy użyć.

Po pomyślnym aprowizowaniu środowiska oceny rozwiązania Commerce istnieje kilka kroków aprowizacji, które należy wykonać, aby przygotować to środowisko do użytku. Niektóre kroki są opcjonalne, w zależności od aspektów systemu, które mają być oceniane. Opcjonalne kroki można wykonać później.

Aby uzyskać informacje dotyczące sposobu konfigurowania środowiska oceny usługi Commerce po jego aprowizowaniu, zobacz [Konfigurowanie środowiska oceny usługi Commerce](cpe-post-provisioning.md). Aby uzyskać informacje dotyczące sposobu konfigurowania opcjonalnych funkcji środowiska oceny usługi Commerce, zobacz [Konfigurowanie funkcji opcjonalnych środowiska oceny usługi Commerce](cpe-optional-features.md).

## <a name="prerequisites"></a>Wymagania wstępne

Zanim będzie można aprowizować środowisko oceny usługi Commerce, muszą zostać spełnione następujące wymagania wstępne:

- Użytkownik został dołączany do programu oceny i uzyskał zdolności produkcyjne dla środowiska oceny.
- Masz dostęp do portalu Lifecycle Services (LCS) rozwiązania Microsoft Dynamics.
- Użytkownik jest istniejącym partnerem Microsoft Dynamics 365 lub odbiorcą i może tworzyć projekt Dynamics 365 Commerce.
- Masz uprawnienia administratora do subskrypcji Microsoft Azure lub jesteś w kontakcie z administratorem subskrypcji, który może pomóc w razie potrzeby.
- Twój identyfikator dzierżawy Azure Active Directory (Azure AD) jest dostępny.
- Utworzono grupę zabezpieczeń usługi Azure AD, która ma być używana jako Grupa administratorów systemu w e-Commerce i jest dostępny jej identyfikator.
- Utworzono grupę zabezpieczeń usługi Azure AD, która ma być używana jako grupa moderatorów ocen i recenzji, i jest dostępny jej identyfikator. (Ta grupa zabezpieczeń może być taka sama jak grupa administratorów systemu e-Commerce).

Należy zauważyć, że ta lista nie wymienia wszystkiego. Jeśli napotkasz jakiekolwiek problemy, skontaktuj się z partnerem Microsoft w celu uzyskania pomocy.

## <a name="provision-your-commerce-evaluation-environment"></a>Aprowizowanie środowiska oceny usługi Commerce

Te procedury wyjaśniają, jak aprowizować środowisko oceny Commerce. Po ich pomyślnym ukończeniu środowisko oceny usługi Commerce będzie gotowe do konfiguracji. Wszystkie działania opisane w tym miejscu są wykonywane w portalu usługi LCS.

### <a name="create-a-new-project"></a>Utwórz nowy projekt

Aby utworzyć nowy projekt w usłudze LCS, należy wykonać następujące kroki.

1. Na stronie głównej usługi LCS wybierz znak plus (**+**), aby utworzyć projekt.
1. W okienku po prawej stronie wykonaj jeden z następujących kroków:

    - Jeśli jesteś partnerem, wybierz pozycję **Wykonaj migrację, twórz rozwiązania i poznaj rozwiązanie**.
    - Jeśli jesteś klientem, wybierz pozycję **Potencjalne przedsprzedaże**.

1. Wprowadź nazwę, opis i branżę.
1. W polu **Nazwa produktu** wybierz pozycję **Dynamics 365 Commerce**.
1. W polu **Wersja produktu** wybierz pozycję **Dynamics 365 Commerce**.
1. W polu **Metodologia** wybierz pozycję **Metodologia implementacji aplikacji Dynamics Retail**.
1. Opcjonalnie: możesz zaimportować role i użytkowników z istniejącego projektu.
1. Wybierz opcję **Utwórz**. Zostanie wyświetlony widok projektu.

### <a name="add-the-azure-connector"></a>Dodawanie łącznika platformy Azure

Aby dodać łącznik Azure Connector do projektu usługi LCS, wykonaj kroki opisane w [Proces przygotowania obsługi Azure Resource Manager (ARM)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/deployment/arm-onboarding).

### <a name="deploy-the-environment"></a>Wdrażanie środowiska

Aby wdrożyć środowisko, wykonaj następujące kroki.

> [!NOTE]
> Być może nie trzeba będzie wykonywać kroków 6, 7 i/lub 8, ponieważ strony z jedną opcją są pomijane. W widoku **Parametry środowiska** potwierdź, że tekst **Dynamics 365 Commerce — demo (10.0.* x* z aktualizacją platformy *xx*)** pojawia się bezpośrednio nad polem **Nazwa środowiska**. Aby uzyskać szczegółowe informacje, zobacz ilustrację wyświetlaną po kroku 8.

1. W menu górnym wybierz opcję **Środowiska hostowane w chmurze**.
1. Wybierz pozycję **Dodaj**, aby dodać środowisko.
1. W polu **wersja aplikacji** wybierz najbardziej aktualną wersję. Jeśli masz określoną potrzebę wybrania wersji aplikacji innej niż wersja najbardziej aktualna, nie wybieraj wersji przed **10.0.14**.
1. W polu **wersja platformy** użyj wersji platformy, która jest automatycznie wybierana dla wybranej wersji aplikacji. 

    ![Wybieranie wersji aplikacji i platformy](./media/project1.png)

1. Wybierz pozycję **Następny**.
1. Wybierz pozycję **Pokaz** jako topologię środowiska.

    ![Wybieranie topologii środowiska 1](./media/project2.png)

1. Na stronie **Wdrażanie środowiska** wprowadź nazwę środowiska. Pozostaw ustawienia zaawansowane niezmienione.

    ![Strona wdrażania środowiska](./media/project4.png)

1. Dostosuj rozmiar maszyny wirtualnej zgodnie z potrzebami. (Zalecamy użycie dla maszyny wirtualnej jednostki magazynowej \[SKU\] **D13 v2**).
1. Zapoznaj się z cenami i warunkami licencjonowania, a następnie zaznacz pole wyboru, aby wskazać, że zgadzasz się z nimi.
1. Wybierz pozycję **Następny**.
1. Sprawdź, czy szczegóły są poprawne, na stronie potwierdzenia wdrożenia, a następnie wybierz pozycję **Wdróż**. Powrócisz do widoku **Środowiska hostowane w chmurze**, a Twoje środowisko powinno pojawić się na liście.

    Żądane środowisko będzie wyświetlane jako kolejkowane, a następnie wdrożone. Zakończenie przepływów pracy środowiska potrwa pewien czas. W związku z tym sprawdź ponownie po około sześciu do dziewięciu godzin.

1. Przed kontynuowaniem upewnij się, że stan środowiska to **Wdrożone**.

### <a name="initialize-the-commerce-scale-unit-cloud"></a>Inicjowanie Commerce Scale Unit (w chmurze)

Aby zainicjować jednostkę CSU, należy wykonać następujące kroki.

1. W widoku **Środowiska hostowane w chmurze** wybierz środowisko na liście.
1. W widoku środowiska po prawej stronie wybierz pozycję **Pełne szczegóły**. Zostanie wyświetlony widok szczegółów środowiska.
1. W obszarze **Funkcje środowiska** wybierz pozycję **Zarządzaj**.
1. Na karcie **Handel** wybierz pozycję **Inicjuj**. Pojawi się widok parametrów inicjacji jednostki CSU.
1. W polu **Region** wybierz region, który jest taki sam lub podobny do regionu, do którego wdrożono środowisko.
1. Pole **Wersja** powinno pozostać niezmienione.
1. Wybierz pozycję **Inicjuj**.
1. Sprawdź, czy szczegóły są poprawne, na stronie potwierdzenia wdrożenia, a następnie wybierz pozycję **Tak**. Widok **Zarządzanie handlem** jest wyświetlany ponownie, jeśli jest wybrana karta **Handel**. CSU zostało dodane do kolejki w celu zainicjowania obsługi administracyjnej.
1. Przed kontynuowaniem upewnij się, że stan jednostki CSU to **Powodzenie**. Inicjowanie trwa około dwóch do pięciu godzin.

Jeśli nie możesz znaleźć łącza **Zarządzaj** w widoku Szczegóły środowiska, skontaktuj się z osobą kontaktową z firmą Microsoft w celu uzyskania pomocy.

Podczas procesu wdrażania może zostać wyświetlony następujący komunikat o błędzie:

> Środowiska ewaluacyjne (demonstracyjne / testowe) muszą zarejestrować aplikację łącznika jednostek skalowania \<application ID\> w Headquarters.

Jeśli inicjalizacja jednostki CSU nie powiedzie się i zostanie wyświetlony ten komunikat o błędzie, zanotuj identyfikator aplikacji, który jest unikatowym identyfikatorem globalnym (GUID), a następnie wykonaj kroki opisane w następnej sekcji, aby zarejestrować aplikację wdrożeniową CSU w siedzibie Commerce headquarters.

### <a name="register-the-csu-deployment-application-in-commerce-headquarters-if-required"></a>Rejestrowanie aplikacji do wdrażania CSU w Commerce Headquarters (w razie potrzeby)

Aby zarejestrować aplikację do wdrażania CSU w Commerce headquarters, wykonaj następujące kroki.

1. W Commerce Headquarters wybierz kolejno opcje **Administrowanie systemem \> Konfiguracja \> aplikacje Azure Active Directory**.
1. W kolumnie **Identyfikator klienta** wprowadź identyfikator aplikacji z otrzymanego komunikatu o błędzie inicjowania CSU.
1. W kolumnie **Nazwa** wprowadź dowolny opisowy tekst (na przykład **Ewaluacja CSU**).
1. W kolumnie **Identyfikator użytkownika** wprowadź wartość **RetailServiceAccount**.
1. Ponów próbę inicjowania i wdrażania CSU z usługi LCS.

### <a name="initialize-e-commerce"></a>Inicjalizowanie e-Commerce

Aby zainicjować usługę e-Commerce, należy wykonać następujące kroki.

1. Na karcie **Handel elektroniczny** przejrzyj zgodę na korzystanie z oceny, a następnie wybierz pozycję **Instalator**.
1. W polu **Nazwa środowiska handlu elektronicznego** wprowadź nazwę. Należy mieć świadomość, że nazwa ta będzie widoczne w niektórych adresach URL wskazujących na to wystąpienie handlu elektronicznego.
1. W polu **Nazwa Commerce Scale Unit** wybierz z listy jednostkę CSU. (Lista powinna mieć tylko jedną opcję).

    Pole **Geografia handlu elektronicznego** jest ustawiane automatycznie.

1. Wybierz przycisk **Dalej**, aby kontynuować.
1. W polu **Obsługiwane nazwy hostów** wprowadź dowolną prawidłową domenę, na przykład `www.fabrikam.com`.
1. W polu **Grupa zabezpieczeń usługi AAD dla administratora systemu** wprowadź kilka pierwszych liter nazwy grupy zabezpieczeń, której chcesz użyć, a następnie wybierz symbol lupy, aby wyświetlić wyniki wyszukiwania. Wybierz prawidłową grupę zabezpieczeń na liście.
1.  W polu **Grupa zabezpieczeń usługi AAD dla moderatora ocen i recenzji** wprowadź kilka pierwszych liter nazwy grupy zabezpieczeń, której chcesz użyć, a następnie wybierz symbol lupy, aby wyświetlić wyniki wyszukiwania. Wybierz prawidłową grupę zabezpieczeń na liście.
1. Zostaw opcję **Włącz obsługę ocen i recenzji** ustawioną na wartość **Tak**.
1. Wybierz pozycję **Inicjuj**. Widok **Zarządzanie handlem** jest wyświetlany ponownie, jeśli jest wybrana karta **e-Commerce**. Inicjowanie usługi e-Commerce zostało rozpoczęte.
1. Przed kontynuowaniem poczekaj, aż stan inicjowania usługi e-Commerce zmieni się na **Inicjowanie powiodło się**.
1. W prawym dolnym rogu sekcji **Linki** zanotuj adresy URL następujących linków:

    * **Witryna usługi e-Commerce** — link do katalogu głównego witryny usługi e-Commerce.
    * **Konstruktor witryn handlu elektronicznego** — link do narzędzia do zarządzania witryną.

## <a name="next-steps"></a>Następne kroki

Aby kontynuować proces aprowizowania i konfigurowania środowiska oceny usługi Commerce, zobacz [Konfigurowanie środowiska oceny usługi Commerce](cpe-post-provisioning.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie środowiska oceny usługi Dynamics 365 Commerce](cpe-overview.md)

[Konfigurowanie środowiska oceny usługi Dynamics 365 Commerce](cpe-post-provisioning.md)

[Konfigurowanie BOPIS w środowisku oceny Dynamics 365 Commerce](cpe-bopis.md)

[Konfigurowanie opcjonalnych funkcji środowiska oceny Dynamics 365 Commerce](cpe-optional-features.md)

[Środowiska oceny usługi Dynamics 365 Commerce — często zadawane pytania](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Commerce Scale Unit (w chmurze)](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portal Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Witryna Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)
