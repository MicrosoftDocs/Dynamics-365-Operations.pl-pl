---
title: "Wymagania systemowe dotyczące wdrożeń w chmurze"
description: "W tym temacie wymieniono wymagania systemowe aktualnej wersji programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition dla wdrożeń chmurowych."
author: sericks007
manager: AnnBe
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 55651
ms.assetid: e564d51d-42d3-47c5-b388-93b8219c692a
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 83637b4b2ccc01950e68569b3b8bee1a7cd69855
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="system-requirements-for-cloud-deployments"></a><span data-ttu-id="a6b82-103">Wymagania systemowe dotyczące wdrożeń w chmurze</span><span class="sxs-lookup"><span data-stu-id="a6b82-103">System requirements for cloud deployments</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="a6b82-104">W tym temacie wymieniono wymagania systemowe aktualnej wersji programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition dla wdrożeń chmurowych.</span><span class="sxs-lookup"><span data-stu-id="a6b82-104">This topic lists the system requirements for the current version of Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, for cloud deployments.</span></span> <span data-ttu-id="a6b82-105">Przed zainstalowaniem programu Finance and Operations w razie potrzeby sprawdź, czy system, na którym pracujesz, co najmniej spełnia minimalne wymagania sieciowe, sprzętowe i programowe.</span><span class="sxs-lookup"><span data-stu-id="a6b82-105">Before you install Finance and Operations, when this step is appropriate, verify that the system that you're working with meets or exceeds the minimum network, hardware, and software requirements.</span></span>

## <a name="supported-web-browsers"></a><span data-ttu-id="a6b82-106">Obsługiwane przeglądarki</span><span class="sxs-lookup"><span data-stu-id="a6b82-106">Supported web browsers</span></span>
<span data-ttu-id="a6b82-107">Aplikacja internetowa może działać w każdej z poniższych przeglądarek w kombinacji z określonym systemem operacyjnym:</span><span class="sxs-lookup"><span data-stu-id="a6b82-107">The web application can run in any of the following web browsers that run on the specified operating systems:</span></span>

-   <span data-ttu-id="a6b82-108">Microsoft Edge (najnowsza publicznie dostępna wersja) w systemie Windows 10</span><span class="sxs-lookup"><span data-stu-id="a6b82-108">Microsoft Edge (latest publicly available version) on Windows 10</span></span>
-   <span data-ttu-id="a6b82-109">Internet Explorer 11 w systemach Windows 10, Windows 8.1 lub Windows 7</span><span class="sxs-lookup"><span data-stu-id="a6b82-109">Internet Explorer 11 on Windows 10, Windows 8.1, or Windows 7</span></span>
-   <span data-ttu-id="a6b82-110">Google Chrome (najnowsza publicznie dostępna wersja) w systemach Windows 10, Windows 8.1, Windows 8 i Windows 7 lub na tablecie Google Nexus 10</span><span class="sxs-lookup"><span data-stu-id="a6b82-110">Google Chrome (latest publicly available version) on Windows 10, Windows 8.1, Windows 8, Windows 7, or Google Nexus 10 tablet</span></span>
-   <span data-ttu-id="a6b82-111">Apple Safari (najnowsze publicznie dostępna wersja) w systemie Mac OS X 10.10 (Yosemite), 10.11 (El Capitan) lub 10.12 (Sierra) albo na iPadzie firmy Apple</span><span class="sxs-lookup"><span data-stu-id="a6b82-111">Apple Safari (latest publicly available version) on Mac OS X 10.10 (Yosemite), 10.11 (El Capitan) or 10.12 (Sierra), or Apple iPad</span></span>

<span data-ttu-id="a6b82-112">Aby znaleźć najnowszą wersję dla każdej przeglądarki, przejdź do witryny producenta oprogramowania.</span><span class="sxs-lookup"><span data-stu-id="a6b82-112">To find the latest release for each web browser, go to the software manufacturer’s website.</span></span> 

> [!NOTE]
> -   <span data-ttu-id="a6b82-113">Aby umożliwić przechwytywanie zrzutów ekranu przez Rejestrator zadań i umieszczanie ich w generowanych dokumentach programu Microsoft Word, należy zainstalować wstępną wersję rozszerzenia dla przeglądarki Chrome.</span><span class="sxs-lookup"><span data-stu-id="a6b82-113">You must install a pre-release Chrome extension to enable Task Recorder to capture screenshots and include them in Microsoft Word documents that are generated.</span></span> <!---For instructions about how to install the extension, see [Screenshot Extension setup](../../dev-itpro/user-interface/task-recorder).-->
> -   <span data-ttu-id="a6b82-114">Edytor przepływu pracy jest uruchamiany jako aplikacja ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="a6b82-114">The Workflow Editor is started as a ClickOnce application.</span></span> <span data-ttu-id="a6b82-115">Aplikacje ClickOnce są obsługiwane tylko w przeglądarkach Microsoft Edge i Internet Explorer (w obsługiwanych wersjach systemu Microsoft Windows).</span><span class="sxs-lookup"><span data-stu-id="a6b82-115">Only Microsoft Edge and Internet Explorer (on a supported version of Microsoft Windows) support ClickOnce applications.</span></span> <span data-ttu-id="a6b82-116">Aplikacja ClickOnce edytora przepływu pracy wymaga zgodnego 64-bitowego systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="a6b82-116">The Workflow Editor ClickOnce application requires a 64-bit-compatible operating system.</span></span>
> -   <span data-ttu-id="a6b82-117">Projektant raportów dla raportowania finansowego jest uruchamiany jako aplikacji ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="a6b82-117">The Report Designer for Financial reporting is started as a ClickOnce application.</span></span> <span data-ttu-id="a6b82-118">Wymaga zgodnego 64-bitowego systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="a6b82-118">It requires a 64-bit-compatible operating system.</span></span> <span data-ttu-id="a6b82-119">Jeśli używasz przeglądarki Chrome, należy zainstalować rozszerzenie ClickOnce, aby można było pobrać klienta Projektanta raportów.</span><span class="sxs-lookup"><span data-stu-id="a6b82-119">If you’re using Chrome, you must install a ClickOnce extension to download the Report Designer client.</span></span> <span data-ttu-id="a6b82-120">Jeśli używasz przeglądarki Chrome w trybie Incognito, upewnij się, że w rozszerzeniu ClickOnce również włączono tryb Incognito.</span><span class="sxs-lookup"><span data-stu-id="a6b82-120">If you use Chrome in Incognito mode, make sure that the ClickOnce extension is also enabled for Incognito mode.</span></span>
> -   <span data-ttu-id="a6b82-121">Aby wyświetlać podgląd plików PDF, zalecamy używanie przeglądarek takich jak Microsoft Edge (nowszej publicznie dostępnej wersji) w systemie Windows 10 lub Google Chrome (nowszej publicznie dostępnej wersji) w systemach Windows 10, Windows 8.1, Windows 8 i Windows 7 lub na tablecie Google Nexus 10.</span><span class="sxs-lookup"><span data-stu-id="a6b82-121">To preview PDF files, we recommend that you use browsers such as Microsoft Edge (latest publicly available version) on Windows 10, or Google Chrome (latest publicly available version) on Windows 10, Windows 8.1, Windows 8, Windows 7, or Google Nexus 10 tablet.</span></span>

### <a name="supported-web-browsers-for-retail-cloud-pos"></a><span data-ttu-id="a6b82-122">Obsługiwane przeglądarki dla aplikacji Retail Cloud POS</span><span class="sxs-lookup"><span data-stu-id="a6b82-122">Supported web browsers for Retail Cloud POS</span></span>

<span data-ttu-id="a6b82-123">Aplikacja Retail Cloud POS może działać w każdej z poniższych przeglądarek w kombinacji z określonym systemem operacyjnym:</span><span class="sxs-lookup"><span data-stu-id="a6b82-123">Retail Cloud POS can run in any of the following web browsers that run on the specified operating systems:</span></span>

-   <span data-ttu-id="a6b82-124">Microsoft Edge (najnowsza publicznie dostępna wersja) w systemie Windows 10</span><span class="sxs-lookup"><span data-stu-id="a6b82-124">Microsoft Edge (latest publicly available version) on Windows 10</span></span>
-   <span data-ttu-id="a6b82-125">Internet Explorer 11 w systemach Windows 10, Windows 8.1 lub Windows 7</span><span class="sxs-lookup"><span data-stu-id="a6b82-125">Internet Explorer 11 on Windows 10, Windows 8.1, or Windows 7</span></span>
-   <span data-ttu-id="a6b82-126">Chrom (najnowsza publicznie dostępna wersja) w systemie Windows 10, Windows 8.1 lub Windows 7</span><span class="sxs-lookup"><span data-stu-id="a6b82-126">Chrome (latest publicly available version) on Windows 10, Windows 8.1, or Windows 7</span></span>

## <a name="network-requirements"></a><span data-ttu-id="a6b82-127">Wymagania sieciowe</span><span class="sxs-lookup"><span data-stu-id="a6b82-127">Network requirements</span></span>
-   <span data-ttu-id="a6b82-128">Program Finance and Operations jest zaprojektowany dla sieci o opóźnieniu nieprzekraczającym 250-300 milisekund (ms).</span><span class="sxs-lookup"><span data-stu-id="a6b82-128">Finance and Operations is designed for networks that have a latency of 250–300 milliseconds (ms) or less.</span></span> <span data-ttu-id="a6b82-129">Jest to opóźnienie na drodze od klienta przeglądarkowego do centrum danych Microsoft Azure zawierającego usługę Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a6b82-129">This latency is the latency from a browser client to the Microsoft Azure datacenter that hosts Finance and Operations.</span></span> <span data-ttu-id="a6b82-130">Zaleca się przetestowanie opóźnienia w sieci na stronie <http://www.azurespeed.com>.</span><span class="sxs-lookup"><span data-stu-id="a6b82-130">We recommend that you test network latency at <http://www.azurespeed.com>.</span></span>
-   <span data-ttu-id="a6b82-131">Wymagania dotyczące przepustowości dla programu Finance and Operations zależą od konkretnego scenariusza.</span><span class="sxs-lookup"><span data-stu-id="a6b82-131">Bandwidth requirements for Finance and Operations depend on your scenario.</span></span> <span data-ttu-id="a6b82-132">Większość typowych scenariuszy wymaga przepustowości powyżej 50 kilobajtów na sekundę (KB/s).</span><span class="sxs-lookup"><span data-stu-id="a6b82-132">Most typical scenarios require a bandwidth of more than 50 kilobytes per second (KBps).</span></span> <span data-ttu-id="a6b82-133">Jednak zalecamy wyższą przepustowość dla scenariuszy z dużymi obciążeniami przesyłania danych, takich jak scenariusze z używaniem obszarów roboczych czy obejmujące rozbudowaną personalizację.</span><span class="sxs-lookup"><span data-stu-id="a6b82-133">However, we recommend more bandwidth for scenarios that have high payload requirements, such as scenarios that involve workspaces or extensive customization.</span></span>

<span data-ttu-id="a6b82-134">Ogólnie rzecz biorąc program Finance and Operations jest zoptymalizowany dla Internetu.</span><span class="sxs-lookup"><span data-stu-id="a6b82-134">In general, Finance and Operations is optimized for the internet.</span></span> <span data-ttu-id="a6b82-135">Liczba rund od klienta przeglądarkowego do centrum danych Azure jest bardzo mała, a wszystkie przesyłane dane są skompresowane.</span><span class="sxs-lookup"><span data-stu-id="a6b82-135">The number of round trips from a browser client to the Azure datacenter is very small, and the whole payload is compressed.</span></span> 

> [!WARNING]
> <span data-ttu-id="a6b82-136">Nie obliczaj wymagań dotyczących przepustowości z lokalizacji klienta poprzez pomnożenie liczby użytkowników przez minimalną wymaganą przepustowość.</span><span class="sxs-lookup"><span data-stu-id="a6b82-136">Don't calculate bandwidth requirements from a client location by multiplying the number of users by the minimum bandwidth requirements.</span></span> <span data-ttu-id="a6b82-137">Równoczesne użytkowanie danej lokalizacji przez wiele osób jest bardzo trudne do obliczenia.</span><span class="sxs-lookup"><span data-stu-id="a6b82-137">The concurrent usage of a given location is very difficult to calculate.</span></span> <span data-ttu-id="a6b82-138">Klienci, którzy się boją, że ciężko będzie im spełnić wymagania dotyczące przepustowości, powinni używać wersji zapoznawczej programu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a6b82-138">Customers who are concerned about bandwidth requirements should use a preview version of Finance and Operations.</span></span>

## <a name="net-framework-requirements"></a><span data-ttu-id="a6b82-139">Wymagania dotyczące środowiska .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a6b82-139">.NET Framework requirements</span></span>
<span data-ttu-id="a6b82-140">Program Finance and Operations wymaga środowiska Microsoft .NET Framework w wersji 4.6.2 dla wszystkich aplikacji ClickOnce, takich jak agent rozsyłania dokumentów.</span><span class="sxs-lookup"><span data-stu-id="a6b82-140">Finance and Operations requires the Microsoft .NET Framework version 4.6.2 for all ClickOnce applications, such as the document routing agent.</span></span> <span data-ttu-id="a6b82-141">Instrukcje instalacji znajdują się w temacie [Instalowanie środowiska .NET Framework](https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="a6b82-141">For installation instructions, see [Installing the .NET Framework](https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).</span></span>

## <a name="supported-microsoft-office-applications"></a><span data-ttu-id="a6b82-142">Obsługiwane aplikacje pakietu Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="a6b82-142">Supported Microsoft Office applications</span></span>
<span data-ttu-id="a6b82-143">Następujące aplikacje pakietu Microsoft Office są obsługiwane we wdrożeniach chmurowych i lokalnych programu Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="a6b82-143">The following Microsoft Office applications are supported in cloud and on-premises deployments of Finance and Operations:</span></span>

-   <span data-ttu-id="a6b82-144">Aby można było uruchamiać dodatki programów Microsoft Excel i Word, musi być zainstalowany pakiet Microsoft Office 2016 dla systemu Windows lub Mac.</span><span class="sxs-lookup"><span data-stu-id="a6b82-144">To run the Microsoft Excel and Word add-ins, you must have Microsoft Office 2016 for Windows or Mac installed.</span></span> <span data-ttu-id="a6b82-145">Aby uzyskać więcej informacji na temat wymagań dotyczących wersji, zobacz [Rozwiązywanie problemów z integracją pakietu Office](../../dev-itpro/office-integration/office-integration-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="a6b82-145">For more information about version requirements, see [Office integration troubleshooting](../../dev-itpro/office-integration/office-integration-troubleshooting.md).</span></span>
-   <span data-ttu-id="a6b82-146">Aby wyświetlać dokumenty generowane przez funkcję Eksportuj do programu Excel lub Eksportuj do programu Word, należy mieć zainstalowany pakiet Microsoft Office 2007 lub nowszy.</span><span class="sxs-lookup"><span data-stu-id="a6b82-146">To view documents that are generated by the Export to Excel or Export to Word functionality, you must have Microsoft Office 2007 or later installed.</span></span>

## <a name="retail-modern-pos-requirements"></a><span data-ttu-id="a6b82-147">Wymagania dotyczące programu Retail Modern POS</span><span class="sxs-lookup"><span data-stu-id="a6b82-147">Retail Modern POS requirements</span></span>

> [!NOTE]
> <span data-ttu-id="a6b82-148">Jeśli aplikacja Retail Modern POS będzie używać bazy danych w trybie offline, komputer musi spełniać wszystkie wymagania systemowe dla programu Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a6b82-148">If Retail Modern POS will use an offline database, the computer must meet all system requirements for Microsoft SQL Server.</span></span> <span data-ttu-id="a6b82-149">Baza danych offline programu Retail Modern POS będzie współpracować z programami Microsoft SQL Server 2012 z dodatkiem Service Pack 3 lub nowszym, Microsoft SQL Server 2014 z dodatkiem Service Pack 2 lub nowszym i Microsoft SQL Server 2016.</span><span class="sxs-lookup"><span data-stu-id="a6b82-149">A Retail Modern POS offline database will work on Microsoft SQL Server 2012 with Service Pack 3 or later, Microsoft SQL Server 2014 with Service Pack 2 or later, and Microsoft SQL Server 2016.</span></span> <span data-ttu-id="a6b82-150">Zalecamy, aby zawsze używać najnowszej dostępnej wersji i instalować wszystkie najnowsze dodatki Service Pack.</span><span class="sxs-lookup"><span data-stu-id="a6b82-150">We recommend that you always use the latest version that is available, and that you install all the latest service packs.</span></span>

### <a name="supported-operating-systems"></a><span data-ttu-id="a6b82-151">Obsługiwane systemy operacyjne</span><span class="sxs-lookup"><span data-stu-id="a6b82-151">Supported operating systems</span></span>

-   <span data-ttu-id="a6b82-152">Aplikacja Retail Modern POS jest 32-bitowa, ale będzie działała w architekturach x86 i x64.</span><span class="sxs-lookup"><span data-stu-id="a6b82-152">Retail Modern POS is a 32-bit application, but it will run on both x86 and x64 architectures.</span></span>
-   <span data-ttu-id="a6b82-153">Aplikacja Retail Modern POS jest obsługiwana w systemie Windows 10 tylko w wydaniach Pro, Enterprise i Enterprise Long Term Servicing Branch (LTSB).</span><span class="sxs-lookup"><span data-stu-id="a6b82-153">Retail Modern POS is supported only on Windows 10 Pro, Enterprise, and Enterprise Long Term Servicing Branch (LTSB) editions.</span></span>

### <a name="minimum-system-requirements"></a><span data-ttu-id="a6b82-154">Minimalne wymagania systemowe</span><span class="sxs-lookup"><span data-stu-id="a6b82-154">Minimum system requirements</span></span>

-   <span data-ttu-id="a6b82-155">Minimalna obsługiwana rozdzielczość wynosi 1280 × 1024 piksele.</span><span class="sxs-lookup"><span data-stu-id="a6b82-155">The minimum supported resolution is 1,280 × 1,024.</span></span>
-   <span data-ttu-id="a6b82-156">Komputer, na którym jest uruchamiany program Retail Modern POS, musi spełniać następujące wymagania:</span><span class="sxs-lookup"><span data-stu-id="a6b82-156">The computer that Retail Modern POS runs on must meet these requirements:</span></span>

    -   <span data-ttu-id="a6b82-157">Musi mieć co najmniej dwurdzeniowy procesor o taktowaniu co najmniej 2 gigaherców (GHz).</span><span class="sxs-lookup"><span data-stu-id="a6b82-157">It must have, at a minimum, a dual-core processor that runs at no less than 2 gigahertz (GHz).</span></span>
    -   <span data-ttu-id="a6b82-158">Musi mieć najmniej 3 gigabajty (GB) pamięci o dostępie swobodnym (RAM).</span><span class="sxs-lookup"><span data-stu-id="a6b82-158">It must have, at a minimum, 3 gigabytes (GB) of random-access memory (RAM).</span></span>
    -   <span data-ttu-id="a6b82-159">Musi mieć dostęp do Internetu.</span><span class="sxs-lookup"><span data-stu-id="a6b82-159">It must have internet access.</span></span>

## <a name="retail-hardware-station-requirements"></a><span data-ttu-id="a6b82-160">Wymagania dotyczące programu Retail hardware station</span><span class="sxs-lookup"><span data-stu-id="a6b82-160">Retail hardware station requirements</span></span>
### <a name="supported-operating-systems"></a><span data-ttu-id="a6b82-161">Obsługiwane systemy operacyjne</span><span class="sxs-lookup"><span data-stu-id="a6b82-161">Supported operating systems</span></span>

-   <span data-ttu-id="a6b82-162">Aplikacja Retail hardware station jest 32-bitowa, ale będzie działała w architekturach x86 i x64.</span><span class="sxs-lookup"><span data-stu-id="a6b82-162">Retail hardware station is a 32-bit application, but it will run on both x86 and x64 architectures.</span></span>
-   <span data-ttu-id="a6b82-163">Aplikacja Retail hardware station jest obsługiwana w następujących systemach operacyjnych:</span><span class="sxs-lookup"><span data-stu-id="a6b82-163">Retail hardware station is supported on the following operating systems:</span></span>

    -   <span data-ttu-id="a6b82-164">Windows 7 w wydaniach Professional, Enterprise i Ultimate</span><span class="sxs-lookup"><span data-stu-id="a6b82-164">Windows 7 Professional, Enterprise, and Ultimate editions</span></span> 
    
        > [!NOTE]
        > <span data-ttu-id="a6b82-165">System Windows 7 jest obsługiwany tylko wtedy, jeśli w systemie ręcznie zainstalowano przeglądarkę Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="a6b82-165">Windows 7 is supported only if Internet Explorer 11 is manually installed on the system.</span></span>

    -   <span data-ttu-id="a6b82-166">Windows 8.1 z aktualizacją 1 w wydaniach Professional, Enterprise i Embedded</span><span class="sxs-lookup"><span data-stu-id="a6b82-166">Windows 8.1 Update 1 Professional, Enterprise, and Embedded editions</span></span>
    -   <span data-ttu-id="a6b82-167">Windows 10 w wydaniach Pro, Enterprise i Enterprise LTSB</span><span class="sxs-lookup"><span data-stu-id="a6b82-167">Windows 10 Pro, Enterprise, and Enterprise LTSB editions</span></span>

### <a name="minimum-system-requirements"></a><span data-ttu-id="a6b82-168">Minimalne wymagania systemowe</span><span class="sxs-lookup"><span data-stu-id="a6b82-168">Minimum system requirements</span></span>

<span data-ttu-id="a6b82-169">Komputer musi spełniać wszystkie wymagania systemowe dotyczące instalowania i używania następujących składników:</span><span class="sxs-lookup"><span data-stu-id="a6b82-169">The computer must meet all system requirements for installing and using the following items:</span></span>

-   <span data-ttu-id="a6b82-170">Internetowe usługi informacyjne (IIS)</span><span class="sxs-lookup"><span data-stu-id="a6b82-170">Internet Information Services (IIS)</span></span>
-   <span data-ttu-id="a6b82-171">Sprzęt innych firm</span><span class="sxs-lookup"><span data-stu-id="a6b82-171">Third-party hardware</span></span>

## <a name="retail-store-scale-unit-requirements"></a><span data-ttu-id="a6b82-172">Wymagania dotyczące programu Retail Store Scale Unit</span><span class="sxs-lookup"><span data-stu-id="a6b82-172">Retail Store Scale Unit requirements</span></span>
### <a name="supported-operating-systems"></a><span data-ttu-id="a6b82-173">Obsługiwane systemy operacyjne</span><span class="sxs-lookup"><span data-stu-id="a6b82-173">Supported operating systems</span></span>

-   <span data-ttu-id="a6b82-174">Aplikacja Retail Store Scale Unit jest 32-bitowa, ale będzie działała w architekturach x86 i x64.</span><span class="sxs-lookup"><span data-stu-id="a6b82-174">Retail Store Scale Unit is a 32-bit application, but it will run on both x86 and x64 architectures.</span></span>
-   <span data-ttu-id="a6b82-175">Aplikacja Retail Store Scale Unit jest obsługiwana w następujących systemach operacyjnych:</span><span class="sxs-lookup"><span data-stu-id="a6b82-175">Retail Store Scale Unit is supported on the following operating systems:</span></span>

    -   <span data-ttu-id="a6b82-176">Windows 7 w wydaniach Professional, Enterprise i Ultimate</span><span class="sxs-lookup"><span data-stu-id="a6b82-176">Windows 7 Professional, Enterprise, and Ultimate editions</span></span>
    -   <span data-ttu-id="a6b82-177">Windows 8.1 z aktualizacją 1 w wydaniach Professional, Enterprise i Embedded</span><span class="sxs-lookup"><span data-stu-id="a6b82-177">Windows 8.1 Update 1 Professional, Enterprise, and Embedded editions</span></span>
    -   <span data-ttu-id="a6b82-178">Windows 10 w wydaniach Pro, Enterprise i Enterprise LTSB</span><span class="sxs-lookup"><span data-stu-id="a6b82-178">Windows 10 Pro, Enterprise, and Enterprise LTSB editions</span></span>

### <a name="minimum-system-requirements"></a><span data-ttu-id="a6b82-179">Minimalne wymagania systemowe</span><span class="sxs-lookup"><span data-stu-id="a6b82-179">Minimum system requirements</span></span>

-   <span data-ttu-id="a6b82-180">4 GB pamięci RAM</span><span class="sxs-lookup"><span data-stu-id="a6b82-180">4 GB of RAM</span></span>
-   <span data-ttu-id="a6b82-181">Procesor o szczytowej szybkości każdego rdzenia 1,6 GHz (co najmniej dwa rdzenie)</span><span class="sxs-lookup"><span data-stu-id="a6b82-181">1.6 GHz peak CPU speed per core (Two cores are the minimum.)</span></span>
-   <span data-ttu-id="a6b82-182">Co najmniej 10 GB wolnego miejsca (baza danych kanałów można wymagać dużej ilości miejsca)</span><span class="sxs-lookup"><span data-stu-id="a6b82-182">At least 10 GB of free space (The channel database can require a large amount of space.)</span></span>

### <a name="recommended-system-requirements"></a><span data-ttu-id="a6b82-183">Zalecane wymagania systemowe</span><span class="sxs-lookup"><span data-stu-id="a6b82-183">Recommended system requirements</span></span>

-   <span data-ttu-id="a6b82-184">6 GB pamięci RAM</span><span class="sxs-lookup"><span data-stu-id="a6b82-184">6 GB of RAM</span></span>
-   <span data-ttu-id="a6b82-185">Procesor i7 o szczytowej szybkości każdego rdzenia 2,4 GHz (lub równoważny) (zalecane są cztery rdzenie)</span><span class="sxs-lookup"><span data-stu-id="a6b82-185">2.4 GHz i7 (or equivalent) peak CPU speed per core (Four cores are recommended.)</span></span>
-   <span data-ttu-id="a6b82-186">Co najmniej 10 GB wolnego miejsca (baza danych kanałów można wymagać dużej ilości miejsca)</span><span class="sxs-lookup"><span data-stu-id="a6b82-186">At least 10 GB of free space (The channel database can require a large amount of space.)</span></span>

## <a name="connector-requirements"></a><span data-ttu-id="a6b82-187">Wymagania dotyczące aplikacji łącznika</span><span class="sxs-lookup"><span data-stu-id="a6b82-187">Connector requirements</span></span>
### <a name="supported-operating-systems"></a><span data-ttu-id="a6b82-188">Obsługiwane systemy operacyjne</span><span class="sxs-lookup"><span data-stu-id="a6b82-188">Supported operating systems</span></span>

-   <span data-ttu-id="a6b82-189">Oprogramowanie łącznika systemu Microsoft Dynamics AX ma dwie osobne wersje instalacyjne — jedną dla usługi Async Server Connector i jedną dla usługi Real-Time Service dla systemu Dynamics AX 2012 R3.</span><span class="sxs-lookup"><span data-stu-id="a6b82-189">The Connector for Microsoft Dynamics AX has two separate installers, one for Async Server Connector service and one for Real-time service for Dynamics AX 2012 R3.</span></span>
-   <span data-ttu-id="a6b82-190">Oba składniki są 32-bitowymi aplikacjami, ale będą działały w architekturach x86 i x64.</span><span class="sxs-lookup"><span data-stu-id="a6b82-190">Both components are 32-bit applications, but they will run on both x86 and x64 architectures.</span></span>
-   <span data-ttu-id="a6b82-191">Oba składniki są obsługiwane w następujących systemach operacyjnych:</span><span class="sxs-lookup"><span data-stu-id="a6b82-191">Both components are supported on the following operating systems:</span></span>

    -   <span data-ttu-id="a6b82-192">Windows 7 w wydaniach Professional, Enterprise i Ultimate</span><span class="sxs-lookup"><span data-stu-id="a6b82-192">Windows 7 Professional, Enterprise, and Ultimate editions</span></span>
    -   <span data-ttu-id="a6b82-193">Windows 8.1 z aktualizacją 1 w wydaniach Professional, Enterprise i Embedded</span><span class="sxs-lookup"><span data-stu-id="a6b82-193">Windows 8.1 Update 1 Professional, Enterprise, and Embedded editions</span></span>
    -   <span data-ttu-id="a6b82-194">Windows 10 w wydaniach Pro, Enterprise i Enterprise LTSB</span><span class="sxs-lookup"><span data-stu-id="a6b82-194">Windows 10 Pro, Enterprise, and Enterprise LTSB editions</span></span>
    -   <span data-ttu-id="a6b82-195">Microsoft Windows Server 2012 R2 i Microsoft Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="a6b82-195">Microsoft Windows Server 2012 R2 and Microsoft Windows Server 2016</span></span>

### <a name="minimum-system-requirements"></a><span data-ttu-id="a6b82-196">Minimalne wymagania systemowe</span><span class="sxs-lookup"><span data-stu-id="a6b82-196">Minimum system requirements</span></span>
-   <span data-ttu-id="a6b82-197">2 GB pamięci RAM (zalecane 4 GB pamięci RAM)</span><span class="sxs-lookup"><span data-stu-id="a6b82-197">2 GB of RAM (4 GB of RAM are recommended.)</span></span>
-   <span data-ttu-id="a6b82-198">Procesor o szczytowej szybkości każdego rdzenia 1,6 GHz (co najmniej dwa rdzenie)</span><span class="sxs-lookup"><span data-stu-id="a6b82-198">1.6 GHz peak CPU speed per core (Two cores are the minimum.)</span></span>
-   <span data-ttu-id="a6b82-199">Co najmniej 10 GB wolnego miejsca (baza danych kanałów można wymagać dużej ilości miejsca)</span><span class="sxs-lookup"><span data-stu-id="a6b82-199">At least 10 GB of free space (The channel database can require a large amount of space.)</span></span>

## <a name="requirements-for-development-on-local-vms"></a><span data-ttu-id="a6b82-200">Wymagania dotyczące instalowania na lokalnych maszynach wirtualnych</span><span class="sxs-lookup"><span data-stu-id="a6b82-200">Requirements for development on local VMs</span></span>
<span data-ttu-id="a6b82-201">Szczegółowe informacje o wymaganiach dotyczących instalowania na lokalnych maszynach wirtualnych (VM) zawiera temat [Maszyny wirtualne uruchamiane lokalnie](../../dev-itpro/dev-tools/access-instances.md).</span><span class="sxs-lookup"><span data-stu-id="a6b82-201">For information about the requirements for development on local virtual machines (VMs), see [VM running on-premises](../../dev-itpro/dev-tools/access-instances.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="a6b82-202">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="a6b82-202">See also</span></span>

[<span data-ttu-id="a6b82-203">Pobieranie kopii ewaluacyjnej programu Dynamics 365 for Finance and Operations Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="a6b82-203">Get an evaluation copy of Dynamics 365 for Finance and Operations, Enterprise edition</span></span>](../../dev-itpro/dev-tools/get-evaluation-copy.md)

