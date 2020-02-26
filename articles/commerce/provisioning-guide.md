---
title: Inicjuj środowisko wersji zapoznawczej Dynamics 365 Commerce
description: W tym temacie opisano sposób aprowizowania środowiska wersji zapoznawczej aplikacji Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 01/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: cbd4c118de2e91c8849461b20a01403049a07e66
ms.sourcegitcommit: 4ed1d8ad8a0206a4172dbb41cc43f7d95073059c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/04/2020
ms.locfileid: "3024643"
---
# <a name="provision-a-dynamics-365-commerce-preview-environment"></a>Inicjuj środowisko wersji zapoznawczej Dynamics 365 Commerce


[!include [banner](includes/banner.md)]

W tym temacie opisano sposób aprowizowania środowiska wersji zapoznawczej aplikacji Dynamics 365 Commerce.

Przed rozpoczęciem zalecane jest wykonanie szybkiego przeglądu tego tematu w celu uzyskania informacji na temat wymaganego procesu.

> [!NOTE]
> Jeśli nie przyznano Ci jeszcze dostępu do wersji zapoznawczej rozwiązania Dynamics 365 Commerce, możesz poprosić o dostęp do wersji zapoznawczej z witryny internetowej [Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite).

## <a name="overview"></a>Omówienie

Aby pomyślnie aprowizować środowisko wersji zapoznawczej rozwiązania Commerce, musisz utworzyć projekt, który ma określoną nazwę i typ produktu. Środowisko i jednostka skali handlu (CSU) mają także określone parametry, których należy użyć w celu późniejszego aprowizowania na platformie e-Commerce. Instrukcje w tym temacie opisują wszystkie wymagane kroki do zakończenia aprowizowania i parametry, których należy użyć.

Po pomyślnym aprowizowaniu środowiska wersji zapoznawczej rozwiązania Commerce istnieje kilka kroków aprowizacji, które należy wykonać, aby przygotować to środowisko. Niektóre kroki są opcjonalne, w zależności od aspektów systemu, które mają być oceniane. Opcjonalne kroki można wykonać później.

Aby uzyskać informacje dotyczące sposobu konfigurowania środowiska wersji zapoznawczej usługi Commerce po jego aprowizowaniu, zobacz [Konfigurowanie środowiska wersji zapoznawczej usługi Commerce](cpe-post-provisioning.md). Aby uzyskać informacje dotyczące sposobu konfigurowania opcjonalnych funkcji środowiska wersji zapoznawczej usługi Commerce, zobacz [Konfigurowanie funkcji opcjonalnych środowiska wersji zapoznawczej usługi Commerce](cpe-optional-features.md).

Jeśli masz pytania dotyczące kroków aprowizowania lub występują problemy, poinformuj Microsoft na [grupie dotyczącej wersji zapoznawczej usługi Microsoft Dynamics 365 Commerce w usłudze Yammer](https://aka.ms/Dynamics365CommercePreviewYammer).

## <a name="prerequisites"></a>Wymagania wstępne

Zanim będzie można aprowizować środowisko wersji zapoznawczej usługi Commerce, muszą zostać spełnione następujące wymagania wstępne:

- Masz dostęp do portalu Lifecycle Services (LCS) rozwiązania Microsoft Dynamics.
- Użytkownik jest istniejącym partnerem Microsoft Dynamics 365 lub odbiorcą i może tworzyć projekt Dynamics 365 Commerce.
- Użytkownik został zaakceptowany w programie wersji zapoznawczej usługi Dynamics 365 Commerce.
- Użytkownik ma uprawnienia wymagane do tworzenia projektu dla opcji **Wykonaj migrację, twórz rozwiązania i poznaj rozwiązanie**.
- Użytkownik jest członkiem roli **Menedżer środowiska** lub **Właściciel projektu** w projekcie, w którym środowisko będzie aprowizowane.
- Użytkownik na uprawnienia administratora do subskrypcji platformy Microsoft Azure lub skontaktuj się z administratorem subskrypcji, który może wykonać dwa kroki wymagające uprawnień administratora w Twoim imieniu.
- Twój identyfikator dzierżawy Azure Active Directory (Azure AD) jest dostępny.
- Utworzono grupę zabezpieczeń usługi Azure AD, która ma być używana jako Grupa administratorów systemu w e-Commerce i jest dostępny jej identyfikator.
- Utworzono grupę zabezpieczeń usługi Azure AD, która ma być używana jako grupa moderatorów ocen i recenzji, i jest dostępny jej identyfikator. (Ta grupa zabezpieczeń może być taka sama jak grupa administratorów systemu e-Commerce).

## <a name="provision-your-commerce-preview-environment"></a>Aprowizowanie środowiska wersji zapoznawczej usługi Commerce

Te procedury wyjaśniają, jak aprowizować środowisko wersji zapoznawczej Commerce. Po ich pomyślnym ukończeniu środowisko wersji zapoznawczej usługi Commerce będzie gotowe do konfiguracji. Wszystkie działania opisane w tym miejscu są wykonywane w portalu usługi LCS.

> [!IMPORTANT]
> Dostęp do wersji zapoznawczej jest powiązany z kontem i organizacją usługi LCS określoną w aplikacji Commerce w wersji zapoznawczej. Do aprowizowania konta środowiska wersji zapoznawczej usługi Commerce. Jeśli potrzebujesz użyć innego konta lub dzierżawy usługi LCS dla środowiska wersji zapoznawczej usługi Commerce, prześlij te szczegóły do firmy Microsoft. Aby uzyskać informacje kontaktowe, zobacz sekcję [Obsługa środowiska wersji zapoznawczej usługi Commerce](#commerce-preview-environment-support) w dalszej części tego tematu.

### <a name="confirm-that-preview-features-are-available-and-turned-on-in-lcs"></a>Potwierdź, że funkcje w wersji zapoznawczej są dostępne i włączone w usługach LCS

Aby potwierdzić, że funkcje w wersji zapoznawczej są dostępne i włączone w usługach LCS, wykonaj następujące kroki.

1. Zaloguj się do [portalu LCS](https://lcs.dynamics.com) przy użyciu tego samego konta LCS, którego użyto do żądania dostępu do wersji zapoznawczej.
1. Na stronie głównej usługi LCS przewiń do prawej strony i wybierz kafelek **Zarządzanie funkcjami w wersji zapoznawczej**.

    ![Kafelek podglądu zarządzania](./media/preview1.png)

1. Przewiń w dół do pozycji **Prywatne funkcje w wersji zapoznawczej** i upewnij się, że następujące funkcje są dostępne i włączone:

    - Ocena e-Commerce
    - Środowiska podglądu programu Commerce

    ![Funkcje w prywatnej wersji Preview](./media/preview2.png)

1. Jeśli te funkcje nie są wyświetlane na liście, skontaktuj się z Microsoft i podaj służbowy adres e-mail, konto LCS i szczegóły dzierżawy. Aby uzyskać informacje kontaktowe, zobacz sekcję [Obsługa środowiska wersji zapoznawczej usługi Commerce](#commerce-preview-environment-support).

### <a name="create-a-new-project"></a>Utwórz nowy projekt

Aby utworzyć nowy projekt w usłudze LCS, należy wykonać następujące kroki.

1. Na stronie głównej usługi LCS wybierz znak plus (**+**), aby utworzyć projekt.
1. W okienku po prawej stronie wykonaj jeden z następujących kroków:

    - Jeśli jesteś partnerem, wybierz pozycję **Wykonaj migrację, twórz rozwiązania i poznaj rozwiązanie**.
    - Jeśli jesteś klientem, wybierz pozycję **Potencjalne przedsprzedaże**.

1. Wprowadź nazwę, opis i branżę.
1. W polu **Nazwa produktu** wybierz pozycję **Dynamics 365 Retail**.
1. W polu **Wersja produktu** wybierz pozycję **Dynamics 365 Retail**.
1. W polu **Metodologia** wybierz pozycję **Metodologia implementacji aplikacji Dynamics Retail**.
1. Opcjonalnie: możesz zaimportować role i użytkowników z istniejącego projektu.
1. Wybierz opcję **Utwórz**. Zostanie wyświetlony widok projektu.

### <a name="add-the-azure-connector"></a>Dodawanie łącznika platformy Azure

Aby dodać łącznik platformy Azure do projektu usługi LCS, wykonaj następujące kroki.

1. Wykonaj jeden z następujących kroków:

    - Jeśli jesteś partnerem, wybierz kafelek **Ustawienia projektu** na końcu po prawej stronie.
    - Jeśli jesteś klientem, wybierz z górnego menu pozycję **Ustawienia projektu**.

1. Wybierz **łączniki Azure**.
1. Wybierz pozycję **Dodaj**, aby dodać łącznik platformy Azure.
1. Należy wprowadzić nazwę.
1. Wprowadź identyfikator subskrypcji platformy Azure.
1. Włącz opcję **Konfiguruj do użycia usługi Azure Resource Manager (ARM)**.
1. Sprawdź, czy wartość **Domena (lub identyfikator) dzierżawcy usługi AAD w ramach subskrypcji Azure** jest poprawna. W razie potrzeby skonsultuj się z administratorem subskrypcji platformy Azure.
1. Wybierz pozycję **Następny**.
1. Postępuj zgodnie z instrukcjami wyświetlanymi na stronie, aby przydzielić wymagane prawa dostępu aplikacji do Twojej subskrypcji. W razie potrzeby skonsultuj się z administratorem subskrypcji platformy Azure.

    1. Zaloguj się do witryny [Azure Portal](https://portal.azure.com/).
    1. Upewnij się, że wybrano poprawny katalog, a następnie w menu po lewej stronie wybierz pozycję **Subskrypcje**.
    1. Znajdź poprawną subskrypcję na liście i wybierz ją. Użyj funkcji wyszukiwania zgodnie z potrzebami.
    1. W menu wybierz pozycję **Kontrola dostępu (IAM)**.
    1. Po prawej stronie w obszarze **Dodaj przypisanie roli** wybierz pozycję **Dodaj**. Pojawi się okienko **Dodawanie przypisania roli**.
    1. W polu **Rola** wybierz pozycję **Współautor**.
    1. W polu **Przypisz dostęp do** pozostaw wartość domyślną, **Użytkownik, grupa lub jednostka usługi Azure AD**.
    1. W obszarze **Wybierz** wprowadź wartość **b96b7e94-b82e-4e71-99a0-cf7fb188acea**.
    1. Wybierz z listy pozycję **Usługi wdrażania Dynamics \[wsfed-enabled\]**.
    1. Wybierz opcję **Zapisz**.

1. Wybierz pozycję **Następny**.
1. Postępuj zgodnie z instrukcjami wyświetlanymi na stronie, aby przydzielić wymagane prawa dostępu aplikacji do Twojej subskrypcji. W razie potrzeby skonsultuj się z administratorem subskrypcji platformy Azure.
1. Wybierz pozycję **Następny**.
1. W polu **Region platformy Azure** wybierz pozycję **Wschodnie stany USA**, **Wschodnie stany USA 2**, **Zachodnie stany USA** lub **Zachodnie stany USA 2**.
1. Wybierz pozycję **Połącz**. Program łącznik Azure powinien pojawić się na liście.

### <a name="import-the-commerce-preview-demo-base-extension"></a>Importowanie podstawowego rozszerzenia pokazu wersji zapoznawczej usługi Commerce

Aby zaimportować podstawowe rozszerzenie pokazu wersji zapoznawczej usługi Commerce do projektu, wykonaj następujące kroki.

1. Otwórz stronę główną projektu, wybierając nazwę projektu u góry.
1. Wykonaj jeden z następujących kroków:

    - Jeśli jesteś partnerem, wybierz kafelek **Biblioteka składników majątku** na końcu po prawej stronie.
    - Jeśli jesteś klientem, wybierz z górnego menu pozycję **Biblioteka składników majątku**.

1. Z listy po lewej stronie wybierz pozycję **Wdrażalny pakiet oprogramowania**.
1. Wybierz opcję **Importuj**.
1. W obszarze **Biblioteka udostępnionych elementów zawartości** wybierz pozycję **Rozszerzenie podstawowe pokazu wersji zapoznawczej usługi Commerce** na liście składników majątku.
1. Wybierz pozycję **Wybierz**. Wrócisz do biblioteki składników majątku, a rozszerzenie powinno pojawić się na liście.

Na poniższej ilustracji przedstawiono akcje, które należy podjąć na stronie **Biblioteka składników majątku** w usłudze LCS.

![Importowanie podstawowego rozszerzenia pokazu wersji zapoznawczej usługi Commerce](./media/import.png)

### <a name="deploy-the-environment"></a>Wdrażanie środowiska

Aby wdrożyć środowisko, wykonaj następujące kroki.

> [!NOTE]
> Być może nie trzeba będzie wykonywać kroków 6, 7 i/lub 8, ponieważ strony z jedną opcją są pomijane. W widoku **Parametry środowiska** potwierdź, że tekst **Dynamics 365 Commerce — demo (10.0.* x* z aktualizacją platformy *xx*)** pojawia się bezpośrednio nad polem **Nazwa środowiska**. Aby uzyskać szczegółowe informacje, zobacz ilustrację wyświetlaną po kroku 8.

1. W menu górnym wybierz opcję **Środowiska hostowane w chmurze**.
1. Wybierz pozycję **Dodaj**, aby dodać środowisko.
1. W polu **wersja aplikacji** wybierz najbardziej aktualną wersję. Jeśli masz określoną potrzebę wybrania wersji aplikacji innej niż wersja najbardziej aktualna, nie wybieraj wersji przed **10.0.8**.
1. W polu **wersja platformy** użyj wersji platformy, która jest automatycznie wybierana dla wybranej wersji aplikacji. 

    ![Wybieranie wersji aplikacji i platformy](./media/project1.png)

1. Wybierz pozycję **Następny**.
1. Wybierz pozycję **Pokaz** jako topologię środowiska.

    ![Wybieranie topologii środowiska 1](./media/project2.png)

1. Wybierz **Dynamics 365 Commerce — Demo** jako topologię środowiska. Jeśli wcześniej skonfigurowano jeden łącznik platformy Azure, zostanie on użyty dla tego środowiska. Jeśli skonfigurowano wiele łączników platformy Azure, można wybrać łącznik do użycia: **Wschodnie stany USA**, **Wschodnie stany USA 2**, **Zachodnie stany USA** lub **Zachodnie stany USA 2**. (Aby uzyskać najlepszą kompleksową wydajność, zalecamy wybranie pozycji **Zachodnie stany USA 2**).

    ![Wybieranie topologii środowiska 2](./media/project3.png)

1. Na stronie **Wdrażanie środowiska** wprowadź nazwę środowiska. Pozostaw ustawienia zaawansowane niezmienione.

    ![Strona wdrażania środowiska](./media/project4.png)

1. Dostosuj rozmiar maszyny wirtualnej zgodnie z potrzebami. (Zalecamy użycie dla maszyny wirtualnej jednostki magazynowej \[SKU\] **D13 v2**).
1. Zapoznaj się z cenami i warunkami licencjonowania, a następnie zaznacz pole wyboru, aby wskazać, że zgadzasz się z nimi.
1. Wybierz pozycję **Następny**.
1. Sprawdź, czy szczegóły są poprawne, na stronie potwierdzenia wdrożenia, a następnie wybierz pozycję **Wdróż**. Powrócisz do widoku **Środowiska hostowane w chmurze**, a Twoje środowisko powinno pojawić się na liście.

    Żądane środowisko będzie wyświetlane jako kolejkowane, a następnie wdrożone. Zakończenie przepływów pracy środowiska potrwa pewien czas. W związku z tym sprawdź ponownie po około sześciu do dziewięciu godzin.

1. Przed kontynuowaniem upewnij się, że stan środowiska to **Wdrożone**.

### <a name="initialize-the-commerce-scale-unit-csu"></a>Inicjowanie jednostki skali handlu (CSU)

Aby zainicjować jednostkę CSU, należy wykonać następujące kroki.

1. W widoku **Środowiska hostowane w chmurze** wybierz środowisko na liście.
1. W widoku środowiska po prawej stronie wybierz pozycję **Pełne szczegóły**. Zostanie wyświetlony widok szczegółów środowiska.
1. W obszarze **Funkcje środowiska** wybierz pozycję **Zarządzaj**.
1. Na karcie **Handel** wybierz pozycję **Inicjuj**. Pojawi się widok parametrów inicjacji jednostki CSU.
1. W polu **Region** wybierz pozycję **Wschodnie stany USA**, **Wschodnie stany USA 2**, **Zachodnie stany USA** lub **Zachodnie stany USA 2**.
1. W polu **Wersja** wybierz pozycję **Określ wersję** na liście, a następnie wpisz ciąg **9.18.20014.4** w wyświetlonym polu. Pamiętaj, aby w tym miejscu dokładnie określić wskazaną wersję. W przeciwnym razie trzeba będzie później zaktualizować jednostkę RCSU do poprawnej wersji.
1. Włącz opcję **Zastosuj rozszerzenie**.
1. Na liście rozszerzeń wybierz pozycję **Podstawowe rozszerzenie pokazu wersji zapoznawczej usługi Commerce**.
1. Wybierz pozycję **Inicjuj**.
1. Sprawdź, czy szczegóły są poprawne, na stronie potwierdzenia wdrożenia, a następnie wybierz pozycję **Tak**. Widok **Zarządzanie handlem** jest wyświetlany ponownie, jeśli jest wybrana karta **Handel**. CSU zostało dodane do kolejki w celu zainicjowania obsługi administracyjnej.
1. Przed kontynuowaniem upewnij się, że stan jednostki CSU to **Powodzenie**. Inicjowanie trwa około dwóch do pięciu godzin.

### <a name="initialize-e-commerce"></a>Inicjalizowanie e-Commerce

Aby zainicjować usługę e-Commerce, należy wykonać następujące kroki.

1. Na karcie **e-Commerce** przejrzyj zgodę na korzystanie z wersji zapoznawczej, a następnie wybierz pozycję **Instalator**.
1. W polu **Nazwa dzierżawy usługi e-Commerce** wprowadź nazwę. Należy jednak mieć świadomość, że nazwa ta będzie widoczne w niektórych adresach URL wskazujących na to wystąpienie usługi e-Commerce.
1. W polu **Nazwa jednostki skali handlu** wybierz z listy jednostkę CSU. (Lista powinna mieć tylko jedną opcję).

    Pole **Region geograficzny usługi e-Commerce** jest ustawiane automatycznie, a jego wartości nie można zmienić.

1. Wybierz przycisk **Dalej**, aby kontynuować.
1. W polu **Obsługiwane nazwy hostów** wprowadź dowolną prawidłową domenę, na przykład `www.fabrikam.com`.
1.  W polu **Grupa zabezpieczeń usługi AAD dla administratora systemu** wprowadź kilka pierwszych liter nazwy grupy zabezpieczeń, której chcesz użyć. Wybierz ikonę lupy, aby wyświetlić wyniki wyszukiwania. Wybierz prawidłową grupę zabezpieczeń z listy.
2.  W polu **Grupa zabezpieczeń usługi AAD dla moderatora ocen i recenzji** wprowadź kilka pierwszych liter nazwy grupy zabezpieczeń, której chcesz użyć. Wybierz ikonę lupy, aby wyświetlić wyniki wyszukiwania. Wybierz prawidłową grupę zabezpieczeń z listy.
1. Pozostaw pozycję **Włącz obsługę ocen i recenzji**.
1. Wybierz pozycję **Inicjuj**. Widok **Zarządzanie handlem** jest wyświetlany ponownie, jeśli jest wybrana karta **e-Commerce**. Inicjowanie usługi e-Commerce zostało rozpoczęte.
1. Przed kontynuowaniem poczekaj, aż stan inicjowania usługi e-Commerce zmieni się na **Inicjowanie powiodło się**.
1. W prawym dolnym rogu sekcji **Linki** zanotuj adresy URL następujących linków:

    * **Witryna usługi e-Commerce** — link do katalogu głównego witryny usługi e-Commerce.
    * **Narzędzie do zarządzania witryną usługi e-Commerce** — link do narzędzia do zarządzania witryną.

## <a name="commerce-preview-environment-support"></a>Obsługa środowiska wersji zapoznawczej usługi Commerce

Jeśli wystąpią problemy podczas wykonywania kroków dotyczących aprowizacji, odwiedź [grupę wersji zapoznawczej usługi Microsoft Dynamics 365 Commerce w serwisie Yammer](https://aka.ms/Dynamics365CommercePreviewYammer) w celu uzyskania pomocy.

Jeśli podczas próby uzyskania dostępu do grupy w serwisie Yammer wystąpią problemy, możesz skontaktować się z firmą Microsoft pocztą elektroniczną pod adresem <Dynamics365Commerce@microsoft.com>. Ten adres e-mail nie jest aktywnie monitorowany. W związku z tym należy oczekiwać opóźnienia odpowiedzi.

## <a name="next-steps"></a>Następne kroki

Aby kontynuować proces aprowizowania i konfigurowania środowiska wersji zapoznawczej usługi Commerce, zobacz [Konfigurowanie środowiska wersji zapoznawczej usługi Commerce](cpe-post-provisioning.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Dynamics 365 Commerce omówienie środowiska wersji zapoznawczej](cpe-overview.md)

[Konfiguruj środowisko wersji zapoznawczej usługi Dynamics 365 Commerce](cpe-post-provisioning.md)

[Konfiguruj funkcje opcjonalne środowiska wersji zapoznawczej usługi Dynamics 365 Commerce](cpe-optional-features.md)

[Środowisko wersji zapoznawczej Dynamics 365 Commerce— często zadawane pytania](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portal Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Witryna Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)

