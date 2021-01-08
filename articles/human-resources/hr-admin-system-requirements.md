---
title: Wymagania systemowe
description: W tym artykule opisano wymagania dotyczące rozwiązania Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
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
ms.openlocfilehash: f68b8f642ada1345e7097b5e7220e222b132b1dd
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420100"
---
# <a name="system-requirements"></a><span data-ttu-id="462bd-103">Wymagania systemowe</span><span class="sxs-lookup"><span data-stu-id="462bd-103">System requirements</span></span>

<span data-ttu-id="462bd-104">W tym artykule opisano wymagania dotyczące rozwiązania Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="462bd-104">This article describes requirements for Microsoft Dynamics 365 Human Resources.</span></span> <span data-ttu-id="462bd-105">Zawiera także opis krajów i regionów, w których jest dostępne rozwiązanie Human Resources oraz informacje na temat języków i lokalizacji danych aplikacji Human Resources.</span><span class="sxs-lookup"><span data-stu-id="462bd-105">It also outlines the countries and regions where Human Resources is available, and information about languages and localization for Human Resources data.</span></span>

## <a name="supported-web-browsers"></a><span data-ttu-id="462bd-106">Obsługiwane przeglądarki</span><span class="sxs-lookup"><span data-stu-id="462bd-106">Supported web browsers</span></span>

<span data-ttu-id="462bd-107">Human Resources może działać w każdej z poniższych przeglądarek w kombinacji z określonym systemem operacyjnym:</span><span class="sxs-lookup"><span data-stu-id="462bd-107">Human Resources can run in any of the following web browsers that run on the specified operating systems:</span></span> 

*   <span data-ttu-id="462bd-108">Microsoft Edge (najnowsza publicznie dostępna wersja) w systemie Windows 10</span><span class="sxs-lookup"><span data-stu-id="462bd-108">Microsoft Edge (latest publicly available version) on Windows 10</span></span>
*   <span data-ttu-id="462bd-109">Internet Explorer 11 w systemach Windows 10, Windows 8.1 lub Windows 7</span><span class="sxs-lookup"><span data-stu-id="462bd-109">Internet Explorer 11 on Windows 10, Windows 8.1, or Windows 7</span></span>
*   <span data-ttu-id="462bd-110">Google Chrome (najnowsza publicznie dostępna wersja)</span><span class="sxs-lookup"><span data-stu-id="462bd-110">Google Chrome (latest publicly available version)</span></span>
*   <span data-ttu-id="462bd-111">Apple Safari (najnowsza publicznie dostępna wersja)</span><span class="sxs-lookup"><span data-stu-id="462bd-111">Apple Safari (latest publicly available version)</span></span>

<span data-ttu-id="462bd-112">Aby znaleźć najnowszą wersję dla każdej przeglądarki, przejdź do witryny producenta oprogramowania.</span><span class="sxs-lookup"><span data-stu-id="462bd-112">To find the latest release for each web browser, go to the software manufacturer’s website.</span></span> 

> [!NOTE]
> * <span data-ttu-id="462bd-113">Aby przechwytywać obrazy generowane z Rejestratora zadań i umieszczać je w dokumentach programu Microsoft Word, musisz mieć zainstalowane rozszerzenie dla przeglądarki Chrome.</span><span class="sxs-lookup"><span data-stu-id="462bd-113">To capture images that are generated from Task Recorder and include them in Microsoft Word documents, you must have a Chrome extension installed.</span></span> 
> * <span data-ttu-id="462bd-114">Edytor przepływu pracy jest uruchamiany jako aplikacja ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="462bd-114">The Workflow Editor is started as a ClickOnce application.</span></span> <span data-ttu-id="462bd-115">Aplikacje ClickOnce są obsługiwane tylko w przeglądarkach Microsoft Edge i Internet Explorer (w obsługiwanych wersjach systemu Microsoft Windows).</span><span class="sxs-lookup"><span data-stu-id="462bd-115">Only Microsoft Edge and Internet Explorer (on a supported version of Microsoft Windows) support ClickOnce applications.</span></span> <span data-ttu-id="462bd-116">Aplikacja ClickOnce edytora przepływu pracy wymaga zgodnego 64-bitowego systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="462bd-116">The Workflow Editor ClickOnce application requires a 64-bit compatible operating system.</span></span>
> * <span data-ttu-id="462bd-117">Aby wyświetlać podgląd plików PDF, zalecamy używanie nowoczesnych przeglądarek, takich jak Microsoft Edge (nowszej publicznie dostępnej wersji) w systemie Windows 10 lub Google Chrome (nowszej publicznie dostępnej wersji) w systemach Windows 10, Windows 8.1, Windows 8 i Windows 7 lub na tablecie Google Nexus 10.</span><span class="sxs-lookup"><span data-stu-id="462bd-117">To preview PDF files, we recommend that you use modern browsers like Microsoft Edge (latest publicly available version) on Windows 10, or Google Chrome (latest publicly available version) on Windows 10, Windows 8.1, Windows 8, Windows 7, or Google Nexus 10 tablet.</span></span>
>   <span data-ttu-id="462bd-118">Wymagania sieciowe</span><span class="sxs-lookup"><span data-stu-id="462bd-118">Network requirements</span></span>
> * <span data-ttu-id="462bd-119">Program Human Resources jest zaprojektowany dla sieci o opóźnieniu nieprzekraczającym 250-300 milisekund (ms).</span><span class="sxs-lookup"><span data-stu-id="462bd-119">Human Resources is designed for networks with latency of 250-300 milliseconds (ms) or less.</span></span> <span data-ttu-id="462bd-120">Jest to opóźnienie na drodze od klienta przeglądarki do centrum danych Microsoft Azure zawierającego usługę Human Resources.</span><span class="sxs-lookup"><span data-stu-id="462bd-120">This is the latency from a browser client to the Microsoft Azure data center that hosts Human Resources.</span></span> <span data-ttu-id="462bd-121">Zaleca się przetestowanie opóźnienia w sieci na stronie [www.azurespeed.com](https://www.azurespeed.com "Test opóźnienia w łączności z usługą Azure").</span><span class="sxs-lookup"><span data-stu-id="462bd-121">We recommend that you test network latency at [www.azurespeed.com](https://www.azurespeed.com "Azure Latency Test").</span></span>
> * <span data-ttu-id="462bd-122">Wymagania dotyczące przepustowości dla usługi Human Resources zależą od konkretnego scenariusza.</span><span class="sxs-lookup"><span data-stu-id="462bd-122">Bandwidth requirements for Human Resources depend on your scenario.</span></span> <span data-ttu-id="462bd-123">Większość typowych scenariuszy wymaga przepustowości powyżej 50 kilobajtów na sekundę (KB/s).</span><span class="sxs-lookup"><span data-stu-id="462bd-123">Most typical scenarios require a bandwidth of more than 50 kilobytes per second (KBps).</span></span>
> 
> [!WARNING]
> <span data-ttu-id="462bd-124">Nie obliczaj wymagań dotyczących przepustowości z lokalizacji klienta poprzez pomnożenie liczby użytkowników przez minimalną wymaganą przepustowość.</span><span class="sxs-lookup"><span data-stu-id="462bd-124">Don't compute bandwidth requirements from a client location by multiplying the number of users by the minimum bandwidth requirements.</span></span> <span data-ttu-id="462bd-125">Równoczesne użytkowanie danej lokalizacji przez wiele osób jest bardzo trudne do obliczenia.</span><span class="sxs-lookup"><span data-stu-id="462bd-125">The concurrent usage of a given location is very difficult to calculate.</span></span> <span data-ttu-id="462bd-126">Dla odbiorców, którzy się boją, że ciężko będzie im spełnić wymagania dotyczące przepustowości, użyj wersji próbnej Human Resources.</span><span class="sxs-lookup"><span data-stu-id="462bd-126">For customers who are concerned about bandwidth requirements, use a trial version of Human Resources.</span></span>

## <a name="supported-microsoft-office-applications"></a><span data-ttu-id="462bd-127">Obsługiwane aplikacje pakietu Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="462bd-127">Supported Microsoft Office applications</span></span>

* <span data-ttu-id="462bd-128">Aby można było uruchamiać dodatki programów Microsoft Excel i Word, musi być zainstalowany pakiet Microsoft Office 2016 dla systemu Windows lub Mac.</span><span class="sxs-lookup"><span data-stu-id="462bd-128">To run the Microsoft Excel and Word add-ins, you must have Microsoft Office 2016 for Windows or Mac installed.</span></span> <span data-ttu-id="462bd-129">Aby uzyskać więcej szczegółów na temat wymagań dotyczących wersji, zobacz [Rozwiązywanie problemów z integracją pakietu Office](../dev-itpro/office-integration/office-integration-troubleshooting.md "Rozwiązywanie problemów z integracją z pakietem Office").</span><span class="sxs-lookup"><span data-stu-id="462bd-129">For more details about version requirements, see [Office integration troubleshooting](../dev-itpro/office-integration/office-integration-troubleshooting.md "Office integration troubleshooting").</span></span>
* <span data-ttu-id="462bd-130">Aby wyświetlać dokumenty generowane przez funkcję Eksportuj do programu Excel lub Eksportuj do programu Word, należy mieć zainstalowany pakiet Microsoft Office 2007 lub nowszy.</span><span class="sxs-lookup"><span data-stu-id="462bd-130">To view documents that are generated by the Export to Excel or Export to Word functionality, you must have Microsoft Office 2007 or later installed.</span></span>

## <a name="regional-availability-languages-and-localization"></a><span data-ttu-id="462bd-131">Regionalna dostępność, Języki i lokalizacja</span><span class="sxs-lookup"><span data-stu-id="462bd-131">Regional availability, languages, and localization</span></span>

<span data-ttu-id="462bd-132">Można pobrać plik PDF zawierający listy krajów, regionów i języków obsługiwanych w aplikacji Human Resources [międzynarodowa dostępność Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability).</span><span class="sxs-lookup"><span data-stu-id="462bd-132">You can download a PDF file of the countries, regions, and languages Human Resources supports at [International availability of Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability).</span></span> 

> [!NOTE]
> <span data-ttu-id="462bd-133">Gdy interfejs użytkownika jest zlokalizowany w innych językach, wszystkie dane użytkownika są przechowywane w języku, w którym zostały wprowadzone.</span><span class="sxs-lookup"><span data-stu-id="462bd-133">While the user interface is localized into other languages, all user data is stored in the language in which it was entered.</span></span> <span data-ttu-id="462bd-134">Możesz tworzyć wiadomości e-mail i szablony w innych językach, ale dane, takie jak informacje o harmonogramie, są w tej chwili dostępne tylko w języku angielskim.</span><span class="sxs-lookup"><span data-stu-id="462bd-134">You can create emails and templates in other languages, but data such as scheduling information is only available in English at this time.</span></span>

<span data-ttu-id="462bd-135">Jeśli jesteś programistą zainteresowanym tworzeniem dostosowań specyficznych dla kraju lub regionu lub stworzeniem rozwiązania dla kraju lub regionu, który nie jest obecnie obsługiwany przez firmę Microsoft, zobacz [Globalizacja](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region).</span><span class="sxs-lookup"><span data-stu-id="462bd-135">If you're a developer interested in creating country- or region-specific customizations, or in creating a solution for a country or region not currently supported by Microsoft, see [Globalization](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region).</span></span>
