---
title: "Możliwości rozszerzania w aplikacji Attract"
description: "W tym temacie opisano, jak można rozszerzyć funkcjonalność aplikacji Microsoft Dynamics 365 for Talent - Attract przy użyciu platformy Microsoft Power Platform."
author: josaw
manager: AnnBe
ms.date: 10/15/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.translationtype: HT
ms.sourcegitcommit: e890e32049e930b70c2d0aac8aa8206ab999418a
ms.openlocfilehash: 0af60a0aea0f7a5de793631445aaebb37dbb0d74
ms.contentlocale: pl-pl
ms.lasthandoff: 10/22/2018

---

# <a name="extensibility-in-attract"></a>Możliwości rozszerzania w aplikacji Attract

[!include[banner](../includes/banner.md)]

Aplikacja Microsoft Dynamics 365 for Talent bazuje na platformie Common Data Service (CDS) dla aplikacji i można rozszerzać jej funkcjonalność na różne sposoby przy użyciu platformy Microsoft Power Platform oraz funkcji dostępnych w usłudze Common Data Service dla aplikacji. W związku z tym system można konfigurować i personalizować za pomocą usług Microsoft PowerApps i Microsoft Flow. Można także uzyskiwać dodatkowe dane analityczne o osobach za pomocą usługi Microsoft Power BI. Ponadto nowe działania niestandardowe, takie jak PowerApps i Treści internetowe (iframe), umożliwiają znacznie większą niż dotąd elastyczność procesu rekrutacji. Za pomocą tych działań można dostosować proces rekrutacji do własnych potrzeb biznesowych i procesów oraz zapewnić zespołowi rekrutacyjnemu i kandydatom maksymalnie płynną, indywidualną obsługę.

## <a name="take-advantage-of-the-microsoft-power-platform"></a>Wykorzystywanie platformy Microsoft Power Platform 

Ponieważ wszystkie dane aplikacji Attract są przechowywane na platformie Common Data Service dla aplikacji, można za pomocą narzędzi platformy Microsoft Power Platform uwzględnić unikatowe potrzeby firmy w aplikacji Attract.

### <a name="powerapps"></a>PowerApps

Usługa PowerApps umożliwia łatwe tworzenie aplikacji, które łączą się z firmowymi danymi w aplikacji Attract oraz używają wyrażeń przypominających wyrażenia z programu Microsoft Excel do dodawania logiki. Aplikacje tworzone za pomocą usługi PowerApps mogą działać w Internecie oraz na urządzeniach z systemami Apple iOS i Google Android.

Na przykład można ułatwić osobom rekrutującym działania na targach kariery organizowanych na wyższych uczelniach, tworząc uproszczoną aplikację, która skanuje życiorysy i wstępnie kojarzy kandydatów ze stanowiskami w aplikacji Attract. Alternatywnie można utworzyć aplikację, która pomaga organizacji spełniać wymogi dotyczące zgodności z przepisami. Aby uzyskać więcej informacji o usłudze PowerApps i jej używaniu do tworzenia aplikacji, zobacz [Integrowanie danych na platformie Common Data Service dla aplikacji](https://docs.microsoft.com/en-us/powerapps).

### <a name="microsoft-flow"></a>Microsoft Flow 

Usługa Microsoft Flow służy do tworzenia zautomatyzowanych przepływów pracy działających na danych aplikacji Attract. Można się łatwo łączyć z setkami popularnych aplikacji i usług bez konieczności samodzielnego pisania kodu źródłowego. Utworzenie przepływów, które na platformie Common Data Service dla aplikacji wchodzą w interakcje z jednostkami Funkcja, Kandydat i Zgłoszenie aplikacji Attract, pozwala zautomatyzować różne czynności. Na przykład gdy kandydat zaakceptuje ofertę, może zostać wysłane powiadomienie do zespołu zajmującego się wdrażaniem do pracy albo opublikowana wiadomości w serwisie Twitter. Aby uzyskać więcej informacji o przepływach, zobacz [Dokumentacja usługi Microsoft Flow](https://docs.microsoft.com/en-us/flow/).

### <a name="power-bi"></a>Power BI

Usługa Power BI umożliwia tworzenie i wyświetlanie niestandardowych raportów i pulpitów nawigacyjnych, które pozwalają na głębszy wgląd w dane w aplikacji Attract. Aby uzyskać więcej informacji o usłudze Power BI oraz o sposobie tworzenia interaktywnych raportów i pulpitów nawigacyjnych, zobacz [Dokumentacja usługi Power BI](https://docs.microsoft.com/en-us/power-bi/).

### <a name="custom-activities"></a>Działania niestandardowe 

Niestandardowe działania, takie jak PowerApps i Treści internetowe (iframe), można dodać na poziomie szablonu procesu rekrutacji na funkcję lub podczas tworzenia nowej funkcji. Działania te pozwalają dostosować proces rekrutacji oraz wprowadzić do aplikacji Attract logikę biznesową unikatową dla organizacji.

#### <a name="powerapps-activity"></a>Działanie PowerApps 

Działanie PowerApps umożliwia twórcy funkcji lub szablonu procesu rekrutacji na funkcję osadzenie aplikacji usługi PowerApps w przepływie rekrutacji. Po utworzeniu i opublikowaniu aplikacji można wprowadzić jej identyfikator w konfiguracjach działań. Za pomocą aplikacji usługi PowerApps można czytać i zapisywać dane do platformy Common Data Service dla aplikacji. Można nawet powiązać aplikację z przepływem. Na przykład masz aplikację, przy użyciu której osoby rekrutujące wypełniają formularze w trakcie prowadzenia rozmów kwalifikacyjnych przez telefon. W tym przypadku można powiązać aplikację z przepływem, który ocenia, czy kandydata można przekazać do dalszego etapu w procesie rekrutacji na funkcję. Tego rodzaju działanie będzie widoczne tylko dla członków zespołu rekrutacyjnego. Aby uzyskać więcej informacji dotyczących sposobu konfigurowania działania PowerApps, zobacz [Działania w aplikacji Attract](./activities-attract.md).

> [!NOTE]
> Działanie PowerApps jest dostępne tylko po zainstalowaniu dodatku kompleksowej obsługi rekrutacji.

#### <a name="web-content-iframe-activity"></a>Działanie Treści internetowe (iframe)

Działanie Treści internetowe (iframe) pozwala osadzić samodzielnie zbudowane niestandardowe rozwiązanie internetowe w procesie rekrutacji lub w portalu kandydata. Działanie umożliwia czytanie i zapisywanie danych bezpośrednio z platformy Common Data Service dla aplikacji. Można także dostosować rozwiązanie, aby wywoływało przepływy lub wykorzystywało funkcje platformy Microsoft Azure. Aby uzyskać więcej informacji dotyczących sposobu konfigurowania działania Treści internetowe, zobacz [Działania w aplikacji Attract](./activities-attract.md).

> [!NOTE]
> Działanie Treści internetowe jest dostępne tylko po zainstalowaniu dodatku kompleksowej obsługi rekrutacji.

