---
title: Możliwości rozszerzania w aplikacji Attract
description: W tym temacie opisano, jak można rozszerzyć funkcjonalność aplikacji Microsoft Dynamics 365 for Talent - Attract przy użyciu platformy Microsoft Power Platform.
author: andreabichsel
manager: AnnBe
ms.date: 03/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichsew
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 52790fbe500d9f55bc9cc86fba5d54f30b11e559
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "1505871"
---
# <a name="extensibility-in-attract"></a>Możliwości rozszerzania w aplikacji Attract

[!include[banner](../includes/banner.md)]

Aplikacja Microsoft Dynamics 365 for Talent bazuje na platformie Common Data Service dla aplikacji i można rozszerzać jej funkcjonalność na różne sposoby przy użyciu platformy Microsoft Power Platform oraz funkcji dostępnych w usłudze Common Data Service for Apps. W związku z tym system można konfigurować i personalizować za pomocą usług Microsoft PowerApps i Microsoft Flow. Można także uzyskiwać dodatkowe dane analityczne o osobach za pomocą usługi Microsoft Power BI. Ponadto nowe działania niestandardowe, takie jak PowerApps i Treści internetowe (iframe), umożliwiają znacznie większą niż dotąd elastyczność procesu rekrutacji. Za pomocą tych działań można dostosować proces rekrutacji do własnych potrzeb biznesowych i procesów oraz zapewnić zespołowi rekrutacyjnemu i kandydatom maksymalnie płynną, indywidualną obsługę.

## <a name="extending-option-sets-in-attract"></a>Rozszerzanie zestawów opcji w Attract

**Zestaw opcji** (Lista wyboru) jest typem pola, które mogą być uwzględniane w jednostkach. Definiuje zestaw opcji. Kiedy zestaw opcji jest wyświetlany w formularzu, używa formantu listy rozwijanej.  W Attract jest wiele pól będących zestawami opcji.  Wprowadzamy możliwości rozszerzania zestawów opcji, począwszy od pola przyczyny odrzucenia, pola Typ zatrudnienia i pola typu stażu pracy.   Ponadto można dodać zlokalizowane etykiety wyświetlania dla dodawanych opcji. Aby uzyskać więcej informacji, zobacz [etykiety zestawu opcji Dostosuj](https://docs.microsoft.com/en-us/powerapps/developer/common-data-service/customize-labels-support-multiple-languages).

> [!NOTE]
> Dodawanie oferty pracy do funkcji LinkedIn wymaga stosowania pól **Typ zatrudnienia** i **typu stażu pracy** na stronie **Szczegóły stanowiska**. Domyślne wartości tych pól nie są obsługiwane przez LinkedIn i są wyświetlane, gdy oferta jest publikowana. Dlatego, jeśli publikujesz ofertę pracy na LinkedIn i zmienisz istniejące zestawy wartości dla tych pól, oferta zostanie opublikowana, ale LinkedIn nie wyświetli wartości niestandardowych **Typ zatrudnienia** i **typu stażu pracy**.  

Poniżej wymieniono kroki, aby zaktualizować pole **przyczyny odrzucenia** wartościami, które są specyficzne dla firmy.  

1. Aby rozszerzyć zestaw opcji **przyczyny odrzucenia**, przejdź do [witryny administratora PowerApps.](https://admin.powerapps.com).
2. Może zostać wyświetlony monit do zalogowania się do swojego konta. Podaj poświadczenia identyfikatora użytkownika i hasła, które można użyć w celu zalogowania się do Dynamics365 i/lub Office 365, a następnie kliknij **Dalej**.
3. Na karcie **środowiska** wybierz środowisko, którym chcesz zarządzać i dwukrotnie kliknij, aby wyświetlić kartę **szczegóły**.
4. Na karcie **szczegóły** wybierz opcję **Centrum administracyjne usługi Dynamics 365**.
5. Wybierz wystąpienie, które chcesz zmienić i wybierz **Otwórz**.
6. Przejdź do **ustawienia**, a następnie **dostosowania**, a następnie wybierz polecenie **dostosuj system**.
7. Znajdowanie jednostkę, dla której chcesz rozwinąć zestaw opcji, wybierając **Jednostki** i rozwijając grupę. W tym przykładzie będzie to **Jednostka zgłoszenia o pracę**.
8. Przejdź do pola, dla którego chcesz rozszerzyć zestaw opcji, wybierając opcję **Pola**. W tym przykładzie będzie to **msdyn_rejectionreason**. Kliknij dwukrotnie pole.
9. W polu **zestaw opcji** wybierz opcję **edytuj**.
10. Wybierz ikonę **+**.
11. Wprowadź **etykietę**.  (Musi to być niepowtarzalna wartość — bez duplikatów).
12. Wybierz opcję **Zapisz**.
13. Wybierz **Opublikuj** u góry strony.

## <a name="take-advantage-of-the-microsoft-power-platform"></a>Wykorzystywanie platformy Microsoft Power Platform 

Ponieważ wszystkie dane aplikacji Attract są przechowywane na platformie Common Data Service, można za pomocą narzędzi platformy Microsoft Power Platform uwzględnić unikatowe potrzeby firmy w aplikacji Attract.

### <a name="powerapps"></a>PowerApps

Usługa PowerApps umożliwia łatwe tworzenie aplikacji, które łączą się z firmowymi danymi w aplikacji Attract oraz używają wyrażeń przypominających wyrażenia z programu Microsoft Excel do dodawania logiki. Aplikacje tworzone za pomocą usługi PowerApps mogą działać w Internecie oraz na urządzeniach z systemami Apple iOS i Google Android.

Na przykład można ułatwić osobom rekrutującym działania na targach kariery organizowanych na wyższych uczelniach, tworząc uproszczoną aplikację, która skanuje życiorysy i wstępnie kojarzy kandydatów ze stanowiskami w aplikacji Attract. Alternatywnie można utworzyć aplikację, która pomaga organizacji spełniać wymogi dotyczące zgodności z przepisami. Aby uzyskać więcej informacji o usłudze PowerApps i jej używaniu do tworzenia aplikacji, zobacz [Integrowanie danych na platformie Common Data Service](https://docs.microsoft.com/en-us/powerapps).

### <a name="microsoft-flow"></a>Microsoft Flow 

Usługa Microsoft Flow służy do tworzenia zautomatyzowanych przepływów pracy działających na danych aplikacji Attract. Można się łatwo łączyć z setkami popularnych aplikacji i usług bez konieczności samodzielnego pisania kodu źródłowego. Utworzenie przepływów, które na platformie Common Data Service wchodzą w interakcje z jednostkami Funkcja, Kandydat i Zgłoszenie aplikacji Attract, pozwala zautomatyzować różne czynności. Na przykład gdy kandydat zaakceptuje ofertę, może zostać wysłane powiadomienie do zespołu zajmującego się wdrażaniem do pracy albo opublikowana wiadomości w serwisie Twitter. Aby uzyskać więcej informacji o przepływach, zobacz [dokumentację systemu Microsoft Flow](https://docs.microsoft.com/en-us/flow/).

### <a name="power-bi"></a>Power BI

Usługa Power BI umożliwia tworzenie i wyświetlanie niestandardowych raportów i pulpitów nawigacyjnych, które pozwalają na głębszy wgląd w dane w aplikacji Attract. Aby uzyskać więcej informacji o usłudze Power BI oraz o sposobie tworzenia interaktywnych raportów i pulpitów nawigacyjnych, zobacz [Dokumentacja usługi Power BI](https://docs.microsoft.com/en-us/power-bi/).

### <a name="custom-activities"></a>Działania niestandardowe 

Niestandardowe działania, takie jak PowerApps i Treści internetowe (iframe), można dodać na poziomie szablonu procesu rekrutacji na funkcję lub podczas tworzenia nowej funkcji. Działania te pozwalają dostosować proces rekrutacji oraz wprowadzić do aplikacji Attract logikę biznesową unikatową dla organizacji.

#### <a name="powerapps-activity"></a>Działanie PowerApps 

Działanie PowerApps umożliwia twórcy funkcji lub szablonu procesu rekrutacji na funkcję osadzenie aplikacji usługi PowerApps w przepływie rekrutacji. Po utworzeniu i opublikowaniu aplikacji można wprowadzić jej identyfikator w konfiguracjach działań. Za pomocą aplikacji usługi PowerApps można czytać i zapisywać dane do platformy Common Data Service. Można nawet powiązać aplikację z przepływem. Na przykład masz aplikację, przy użyciu której osoby rekrutujące wypełniają formularze w trakcie prowadzenia rozmów kwalifikacyjnych przez telefon. W tym przypadku można powiązać aplikację z przepływem, który ocenia, czy kandydata można przekazać do dalszego etapu w procesie rekrutacji na funkcję. Tego rodzaju działanie będzie widoczne tylko dla członków zespołu rekrutacyjnego. Aby uzyskać więcej informacji dotyczących sposobu konfigurowania działania PowerApps, zobacz [Działania w aplikacji Attract](./activities-attract.md).

> [!NOTE]
> Działanie PowerApps jest dostępne tylko po zainstalowaniu dodatku kompleksowej obsługi rekrutacji.

#### <a name="web-content-iframe-activity"></a>Działanie Treści internetowe (iframe)

Działanie Treści internetowe (iframe) pozwala osadzić samodzielnie zbudowane niestandardowe rozwiązanie internetowe w procesie rekrutacji lub w portalu kandydata. Działanie umożliwia czytanie i zapisywanie danych bezpośrednio z platformy Common Data Service. Można także dostosować rozwiązanie, aby wywoływało przepływy lub wykorzystywało funkcje platformy Microsoft Azure. Aby uzyskać więcej informacji dotyczących sposobu konfigurowania działania Treści internetowe, zobacz [Działania w aplikacji Attract](./activities-attract.md).

> [!NOTE]
> Działanie Treści internetowe jest dostępne tylko po zainstalowaniu dodatku kompleksowej obsługi rekrutacji.
