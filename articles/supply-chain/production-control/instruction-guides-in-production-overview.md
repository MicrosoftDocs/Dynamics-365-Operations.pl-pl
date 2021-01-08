---
title: Udostępnianie przewodników po rzeczywistości mieszanej pracownikom produkcji
description: W tym temacie opisano sposób integrowania modułu zarządzania produkcją w systemie Microsoft Dynamics 365 Supply Chain Management z Dynamics 365 Guides.
author: cabeln
manager: tfehr
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkGuidesManufacturing
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 61943
ms.assetid: a3847f07-fca4-4140-a26f-d83c6ac68dde
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: cabeln
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.15
ms.openlocfilehash: 727a3bc50ea55259c7260a9d060dac59473ee3c1
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645151"
---
# <a name="provide-mixed-reality-guides-for-workers-in-production"></a><span data-ttu-id="69b64-103">Udostępnianie przewodników po rzeczywistości mieszanej pracownikom produkcji</span><span class="sxs-lookup"><span data-stu-id="69b64-103">Provide mixed-reality Guides for workers in production</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="69b64-104">Pracownicy w procesach produkcyjnych będą korzystać z odpowiednich instrukcji, które są dostępne w odpowiednim czasie w kontekście ich pracy.</span><span class="sxs-lookup"><span data-stu-id="69b64-104">Workers in production processes will benefit from relevant instructions that are provided at the right time in the context of their work.</span></span> <span data-ttu-id="69b64-105">*Instrukcje* dotyczą kilku typów pracy, w tym: montażu, usług, operacji, certyfikacji i bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="69b64-105">*Instructions* apply in several domains of work, including: assembly, service, operations, certification, and safety.</span></span> <span data-ttu-id="69b64-106">We wszystkich tych podstawowych funkcjach biznesowych, instrukcje ciągłego szkolenia mogą pomóc pracownikom zrobić więcej i pracować lepiej.</span><span class="sxs-lookup"><span data-stu-id="69b64-106">Across all of these core business functions, ongoing training instructions can help empower workers to achieve more and work better.</span></span>

## <a name="introduction"></a><span data-ttu-id="69b64-107">Wprowadzenie</span><span class="sxs-lookup"><span data-stu-id="69b64-107">Introduction</span></span>

<span data-ttu-id="69b64-108">Instrukcje można udostępniać na różne sposoby.</span><span class="sxs-lookup"><span data-stu-id="69b64-108">You can provide instructions in different ways.</span></span> <span data-ttu-id="69b64-109">Jeden skuteczny system, który jest dostarczany jako gotowy, wykorzystuje system [Dynamics 365 Guides](https://dynamics.microsoft.com/mixed-reality/guides/).</span><span class="sxs-lookup"><span data-stu-id="69b64-109">One efficient system that ships out of the box uses [Dynamics 365 Guides](https://dynamics.microsoft.com/mixed-reality/guides/).</span></span>

<span data-ttu-id="69b64-110">Dynamics 365 Guides umożliwia szkolenie pracowników za pomocą praktycznych kursów.</span><span class="sxs-lookup"><span data-stu-id="69b64-110">Dynamics 365 Guides can help empower your employees with hands-on learning.</span></span> <span data-ttu-id="69b64-111">Standardowe procesy można definiować, stosując instrukcje krok po kroku, które nauczą pracownikom korzystania z wymaganych narzędzi i części oraz pokażą pracowników, jak używać tych narzędzi podczas pracy.</span><span class="sxs-lookup"><span data-stu-id="69b64-111">You can define standardized processes with step-by-step instructions that guide your employees to the tools and parts they need and show employees how to use these tools in real work situations.</span></span>

<span data-ttu-id="69b64-112">Można dołączać przewodniki do różnych aspektów kontroli produkcji, w tym:</span><span class="sxs-lookup"><span data-stu-id="69b64-112">You can attach guides to various aspects of production control including:</span></span>

- [<span data-ttu-id="69b64-113">Zasoby</span><span class="sxs-lookup"><span data-stu-id="69b64-113">Resources</span></span>](#resources)
- [<span data-ttu-id="69b64-114">Grupy zasobów</span><span class="sxs-lookup"><span data-stu-id="69b64-114">Resource groups</span></span>](#resource-groups)
- [<span data-ttu-id="69b64-115">Zwolnione produkty</span><span class="sxs-lookup"><span data-stu-id="69b64-115">Released products</span></span>](#released-products)
- [<span data-ttu-id="69b64-116">Formuły</span><span class="sxs-lookup"><span data-stu-id="69b64-116">Formulas</span></span>](#formulas)
- [<span data-ttu-id="69b64-117">Wersje formuły</span><span class="sxs-lookup"><span data-stu-id="69b64-117">Formula versions</span></span>](#formula-versions)
- [<span data-ttu-id="69b64-118">List składowych (BOM)</span><span class="sxs-lookup"><span data-stu-id="69b64-118">Bills of material (BOMs)</span></span>](#bom)
- [<span data-ttu-id="69b64-119">Wersji BOM</span><span class="sxs-lookup"><span data-stu-id="69b64-119">BOM versions</span></span>](#bom-versions)
- [<span data-ttu-id="69b64-120">Marszruty</span><span class="sxs-lookup"><span data-stu-id="69b64-120">Routes</span></span>](#routes)
- [<span data-ttu-id="69b64-121">Wersje marszruty</span><span class="sxs-lookup"><span data-stu-id="69b64-121">Route versions</span></span>](#route-versions)
- [<span data-ttu-id="69b64-122">Relacji operacji marszrut</span><span class="sxs-lookup"><span data-stu-id="69b64-122">Route operation relations</span></span>](#route-operation-relations)

> [!NOTE]
> <span data-ttu-id="69b64-123">Można także dołączać przewodniki do zarządzania środkami trwałymi.</span><span class="sxs-lookup"><span data-stu-id="69b64-123">You can also attach Guides with Asset Management.</span></span> <span data-ttu-id="69b64-124">Aby uzyskać więcej informacji o opcji, zobacz temat [Integracja Dynamics 365 Supply Chain Management (zarządzanie składnikami majątku) z Dynamics 365 Guides](../asset-management/asset-management-guides-integration.md).</span><span class="sxs-lookup"><span data-stu-id="69b64-124">For more information about that option, see [Integrate Dynamics 365 Supply Chain Management (Asset Management) with Dynamics 365 Guides](../asset-management/asset-management-guides-integration.md).</span></span>

<span data-ttu-id="69b64-125">Jeśli pracownik pierwszej linii wybiera zadanie w wydziale produkcyjnym w module Supply Chain Management widzi [odpowiednie przewodniki](#logic) na karcie zadań.</span><span class="sxs-lookup"><span data-stu-id="69b64-125">When a first-line worker chooses a job on the shop floor through Supply Chain Management, the worker can see [the relevant guides](#logic) on the job card.</span></span> <span data-ttu-id="69b64-126">Gdy pracownik wybiera określony przewodnik, na ekranie jest wyświetlany kod QR dla tego przewodnika.</span><span class="sxs-lookup"><span data-stu-id="69b64-126">When the worker chooses a specific guide, a QR code for that guide is shown on the screen.</span></span> <span data-ttu-id="69b64-127">Następnie pracownik używa okularów HoloLens do skanowania kodu QR, który uruchamia przewodniki i pokazuje wymagane instrukcje.</span><span class="sxs-lookup"><span data-stu-id="69b64-127">The worker then uses their HoloLens to scan the QR code, which launches Guides and shows the required instructions.</span></span>

<span data-ttu-id="69b64-128">W poniższych podsekcjach opisano kilka wybranych scenariuszy, w których firmy mogą zobaczyć największą wartość przy użyciu przewodników w celu przedstawienia instrukcji dotyczących produkcji.</span><span class="sxs-lookup"><span data-stu-id="69b64-128">The following subsections describe a few selected scenarios where companies across industries can see the biggest value when using Guides to present instructions for manufacturing.</span></span>

### <a name="assembly"></a><span data-ttu-id="69b64-129">Zestaw</span><span class="sxs-lookup"><span data-stu-id="69b64-129">Assembly</span></span>

<span data-ttu-id="69b64-130">![Używanie przewodników w zadaniach montażu](media/instruction-guides-hero-assembly.png "Używanie przewodników w zadaniach naprawy")</span><span class="sxs-lookup"><span data-stu-id="69b64-130">![Use Guides in assembly tasks](media/instruction-guides-hero-assembly.png "Use Guides in service tasks")</span></span>

<span data-ttu-id="69b64-131">Instrukcje w operacjach montażu pokazują pracownikom potrzebne narzędzia i części oraz sposób ich użycia w rzeczywistej sytuacji.</span><span class="sxs-lookup"><span data-stu-id="69b64-131">Instructions in assembly operations show workers the tools and parts they need and how to use them in real work situations.</span></span>

<span data-ttu-id="69b64-132">Menedżerowie produkcji mogą tworzyć i przypisywać przewodniki, na przykład dla [marszrut produkcji](routes-operations.md), [relacji operacji](routes-operations.md#operation-relations)lub [listy BOM](bill-of-material-bom.md).</span><span class="sxs-lookup"><span data-stu-id="69b64-132">Production managers can create and assign Guides, for example, for [production routes](routes-operations.md), [operation relations](routes-operations.md#operation-relations), or [bills of material](bill-of-material-bom.md).</span></span> <span data-ttu-id="69b64-133">Pracownicy mogą znaleźć odpowiednie instrukcje na temat czynności związanych z produkcją w wydziale produkcyjnym.</span><span class="sxs-lookup"><span data-stu-id="69b64-133">Workers will find the relevant instructions on the respective operation experience on the shop floor.</span></span>

### <a name="service"></a><span data-ttu-id="69b64-134">Serwis</span><span class="sxs-lookup"><span data-stu-id="69b64-134">Service</span></span>

<span data-ttu-id="69b64-135">![Używanie przewodników w zadaniach naprawy](media/instruction-guides-hero-service.png "Używanie przewodników w zadaniach naprawy")</span><span class="sxs-lookup"><span data-stu-id="69b64-135">![Use Guides in service tasks](media/instruction-guides-hero-service.png "Use Guides in service tasks")</span></span>

<span data-ttu-id="69b64-136">Wyposaż techników w szczegółowe instrukcje w miejscu pracy, eliminując konieczność planowania dodatkowych wizyt.</span><span class="sxs-lookup"><span data-stu-id="69b64-136">Equip technicians with guided instructions at the job site, eliminating the need to schedule additional visits.</span></span>

<span data-ttu-id="69b64-137">Menedżerowie serwisu mogą przypisywać przewodniki na przykład do konkretnych [produktów](../../commerce/product.md), które opisują procedury oceny jakości.</span><span class="sxs-lookup"><span data-stu-id="69b64-137">Service managers can assign Guides, for example, to specific [products](../../commerce/product.md) that walk through routines of quality assessment.</span></span>

### <a name="quality"></a><span data-ttu-id="69b64-138">Jakość</span><span class="sxs-lookup"><span data-stu-id="69b64-138">Quality</span></span>

<span data-ttu-id="69b64-139">![Używanie przewodników w zadaniach kontroli jakości](media/instruction-guides-hero-quality.png "Używanie przewodników w zadaniach kontroli jakości")</span><span class="sxs-lookup"><span data-stu-id="69b64-139">![Use Guides in quality assurance tasks](media/instruction-guides-hero-quality.png "Use Guides in quality assurance tasks")</span></span>

<span data-ttu-id="69b64-140">Wdrażaj nowe procesy i zapewniaj zwiększoną spójność zmianie wiedzy pracownika w powtarzalne narzędzie.</span><span class="sxs-lookup"><span data-stu-id="69b64-140">Rollout new processes and ensure increased consistency by turning employee knowledge into a repeatable tool.</span></span>

<span data-ttu-id="69b64-141">Menedżerowie ds. kontroli jakość mogą przypisywać przewodniki na przykład do konkretnych [produktów](../../commerce/product.md), które opisują procedury oceny jakości.</span><span class="sxs-lookup"><span data-stu-id="69b64-141">Quality assurance managers can assign guides, for example, to [products](../../commerce/product.md) that walk through routines of quality assessment.</span></span>

### <a name="certifications"></a><span data-ttu-id="69b64-142">Certyfikacje</span><span class="sxs-lookup"><span data-stu-id="69b64-142">Certifications</span></span>

<span data-ttu-id="69b64-143">![Używanie przewodników w zadaniach związanych z certyfikacją](media/instruction-guides-hero-certification.png "Używanie przewodników w zadaniach związanych z certyfikacją")</span><span class="sxs-lookup"><span data-stu-id="69b64-143">![Use Guides for certification related tasks](media/instruction-guides-hero-certification.png "Use Guides for certification related tasks")</span></span>

<span data-ttu-id="69b64-144">Zapewnij, że każdy pracownik spełnia wysokie standardy, szybko określając kto i gdzie potrzebuje pomocy.</span><span class="sxs-lookup"><span data-stu-id="69b64-144">Ensure every employee meets high standards by quickly identifying who needs help and where.</span></span>

### <a name="safety"></a><span data-ttu-id="69b64-145">Bezpieczeństwo</span><span class="sxs-lookup"><span data-stu-id="69b64-145">Safety</span></span>

<span data-ttu-id="69b64-146">![Używanie przewodników w instrukcjach bezpieczeństwa pracy](media/instruction-guides-hero-safety.png "Używanie przewodników w instrukcjach bezpieczeństwa pracy")</span><span class="sxs-lookup"><span data-stu-id="69b64-146">![Use Guides in work safety instructions](media/instruction-guides-hero-safety.png "Use Guides in work safety instructions")</span></span>

<span data-ttu-id="69b64-147">Przed rozpoczęciem pracy w danym środowisku udostępnij instrukcje, które posłużą do wykonania niebezpiecznych procedur.</span><span class="sxs-lookup"><span data-stu-id="69b64-147">Provide instructions that walk through dangerous procedures virtually before attempting in the physical environment.</span></span> <span data-ttu-id="69b64-148">Dzięki podejściu opartym na rzeczywistości mieszanej pracownicy mogą wykonać niebezpieczne procedury wirtualnie.</span><span class="sxs-lookup"><span data-stu-id="69b64-148">With a mixed reality approach, workers can experience dangerous procedures virtually.</span></span>

<span data-ttu-id="69b64-149">Menedżerowie produkcji mogą zapewnić dedykowane instrukcje obsługi materiałów niebezpiecznych lub delikatnych, przypisując instrukcje do [towarów](../../commerce/product.md), [marszrut](routes-operations.md)i [operacji](routes-operations.md#operation-relations).</span><span class="sxs-lookup"><span data-stu-id="69b64-149">Production managers can provide dedicated handling instructions for hazardous material handling or delicate handling procedures by assigning instructions to [product items](../../commerce/product.md), [routes](routes-operations.md), and [operations](routes-operations.md#operation-relations).</span></span>

## <a name="get-started-with-instructions-and-guides"></a><span data-ttu-id="69b64-150">Rozpoczynanie pracy z instrukcjami i przewodnikami</span><span class="sxs-lookup"><span data-stu-id="69b64-150">Get started with instructions and Guides</span></span>

<span data-ttu-id="69b64-151">Aby włączyć instrukcje w procesach produkcyjnych, Supply Chain Management zapewnia gotową integrację z systemem Dynamics 365 Guides.</span><span class="sxs-lookup"><span data-stu-id="69b64-151">To enable instructions in production processes, Supply Chain Management provides an out-of-the-box integration with Dynamics 365 Guides.</span></span> <span data-ttu-id="69b64-152">Licencjonowana i zainstalowana instancja Guides jest wymagana do tworzenia, obsługiwania i przypisywania instrukcji typu „rzeczywistość mieszana” do środków produkcji i pracy.</span><span class="sxs-lookup"><span data-stu-id="69b64-152">A licensed and installed application instance of Guides is required to build, maintain, and assign mixed reality instructions to production assets and work.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="69b64-153">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="69b64-153">Prerequisites</span></span>

<span data-ttu-id="69b64-154">Aby można było użyć tej funkcji, system musi zawierać następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="69b64-154">To use this feature, your system must include the following:</span></span>

- <span data-ttu-id="69b64-155">Dynamics 365 Supply Chain Management, wersja 10.0.15 lub nowsza</span><span class="sxs-lookup"><span data-stu-id="69b64-155">Dynamics 365 Supply Chain Management version 10.0.15 or later</span></span>
- <span data-ttu-id="69b64-156">[Podwójny zapis](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write) dla aplikacji Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="69b64-156">[Dual-write](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write) for Supply Chain Management apps.</span></span>
- <span data-ttu-id="69b64-157">[Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) w wersji 400.0.1.48 lub nowszej</span><span class="sxs-lookup"><span data-stu-id="69b64-157">[Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) version 400.0.1.48 or later</span></span>

### <a name="turn-on-the-feature"></a><span data-ttu-id="69b64-158">Włączanie funkcji</span><span class="sxs-lookup"><span data-stu-id="69b64-158">Turn on the feature</span></span>

<span data-ttu-id="69b64-159">Aby funkcja była dostępna w systemie, należy włączyć jej klucze konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="69b64-159">To make the feature available on your system, you must enable its configuration keys.</span></span> <span data-ttu-id="69b64-160">Wystarczy zrobić to tylko raz.</span><span class="sxs-lookup"><span data-stu-id="69b64-160">You only need to do this once.</span></span> <span data-ttu-id="69b64-161">W tym celu administrator musi wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="69b64-161">To do this, an administrator must do the following:</span></span>

1. <span data-ttu-id="69b64-162">Ustaw system w trybie konserwacji, jak to opisano w sekcji [Tryb konserwacji](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="69b64-162">Place your system into maintenance mode as described in [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>
1. <span data-ttu-id="69b64-163">Wybierz kolejno opcje **Administrowanie systemem \> Ustawienia \> Konfiguracja licencji**.</span><span class="sxs-lookup"><span data-stu-id="69b64-163">Go to **System administration \> Setup \> License configuration**.</span></span>
1. <span data-ttu-id="69b64-164">Rozwiń Sekcję **Rzeczywistość mieszana**, a następnie zaznacz pole wyboru **Przewodnik w rzeczywistości mieszanej**.</span><span class="sxs-lookup"><span data-stu-id="69b64-164">Expand the **Mixed reality** section and then select the **Mixed reality guide** check box.</span></span>
1. <span data-ttu-id="69b64-165">Rozwiń sekcję **Zarządzanie produkcją**, a następnie zaznacz pole wyboru **Instrukcje produkcji**.</span><span class="sxs-lookup"><span data-stu-id="69b64-165">Expand the **Production management** section and then select the **Production instructions** check box.</span></span>
1. <span data-ttu-id="69b64-166">Wyłącz tryb konserwacji, jak to opisano w sekcji [Tryb konserwacji](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="69b64-166">Turn off maintenance mode as described in [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>
  
## <a name="configure-how-guides-appear-on-the-shop-floor"></a><span data-ttu-id="69b64-167">Konfigurowanie sposobu wyświetlania przewodników w wydziale produkcyjnym</span><span class="sxs-lookup"><span data-stu-id="69b64-167">Configure how Guides appear on the shop floor</span></span>

<span data-ttu-id="69b64-168">Aby skonfigurować sposób wyświetlania przewodników w wydziale produkcyjnym, przejdź do opcji **Rzeczywistość mieszana \> Dynamics 365 Guides \> Konfiguruj integrację przewodników**.</span><span class="sxs-lookup"><span data-stu-id="69b64-168">To configure how Guides appear on the shop floor, go to **Mixed Reality \> Dynamics 365 Guides \> Configure Guides integration**.</span></span>

<span data-ttu-id="69b64-169">![Konfigurowanie integracji przewodników dla produkcji](media/instruction-guides-configure-integration.png "Konfigurowanie integracji przewodników dla produkcji")</span><span class="sxs-lookup"><span data-stu-id="69b64-169">![Configure Guide integration for manufacturing](media/instruction-guides-configure-integration.png "Configure Guide integration for manufacturing")</span></span>

<span data-ttu-id="69b64-170">Ustaw wartości w następujących polach:</span><span class="sxs-lookup"><span data-stu-id="69b64-170">Set the following fields:</span></span>

- <span data-ttu-id="69b64-171">**Adres URL Microsoft Dataverse** — umożliwia określenie adresu URL środowiska Microsoft Dataverse, w którym tworzone są przewodniki.</span><span class="sxs-lookup"><span data-stu-id="69b64-171">**Microsoft Dataverse URL** - Specify the URL for the Microsoft Dataverse environment where you create your Guides.</span></span> <span data-ttu-id="69b64-172">Format to „contoso.crm4.dynamics.com”, gdzie pierwszą część adresu URL zwykle stanowi nazwa organizacji (np. „contoso.”), druga część jest specyficzna dla obszaru danych danego środowiska (np. „crm4.”), a ostatnia część to domena (np. „dynamics.com”).</span><span class="sxs-lookup"><span data-stu-id="69b64-172">The format is "contoso.crm4.dynamics.com", where the first part of the URL is typically named after your organization (such as "contoso."), the second part is specific to the data region of your environment (such as "crm4."), and the last part is the domain (such as "dynamics.com").</span></span> <span data-ttu-id="69b64-173">Jednym ze sposobów znalezienia odpowiedniego adresu URL jest przejście do witryny [home.dynamics.com](https://home.dynamics.com/), a następnie otwarcie aplikacji Guides.</span><span class="sxs-lookup"><span data-stu-id="69b64-173">One way to find the right URL is to go to [home.dynamics.com](https://home.dynamics.com/) and then open your Guides app.</span></span> <span data-ttu-id="69b64-174">Po otwarciu przewodników na pasku adresu przeglądarki widoczny będzie adres URL (należy wziąć pod uwagę tylko podstawowy adres URL, który powinien być podobny do powyższego przykładu).</span><span class="sxs-lookup"><span data-stu-id="69b64-174">When Guides opens, you will see the URL in the address bar of your browser (only take the base URL, which should resemble the previous example).</span></span> <span data-ttu-id="69b64-175">Ta wartość jest używana do tworzenia adresów dla przewodników i zostanie zaszyfrowana w kodach QR.</span><span class="sxs-lookup"><span data-stu-id="69b64-175">This value is used to compose addresses for your guides and will be encoded into the QR codes."</span></span>
- <span data-ttu-id="69b64-176">**Rozmiar kodu QR** — umożliwia ustawienie rozmiaru renderowanego kodu QR.</span><span class="sxs-lookup"><span data-stu-id="69b64-176">**QR code size** - Set the size of the rendered QR code.</span></span> <span data-ttu-id="69b64-177">Zalecamy wybór rozmiaru, który wypełni większość ekranu, ale nie cały.</span><span class="sxs-lookup"><span data-stu-id="69b64-177">We recommend choosing a size that will fill most of your display screen, but not more.</span></span> <span data-ttu-id="69b64-178">Zazwyczaj *15* jest dobrą wartością.</span><span class="sxs-lookup"><span data-stu-id="69b64-178">Typically, *15* is a good value.</span></span>
- <span data-ttu-id="69b64-179">**Poziom korekcji błędów kodu QR** — umożliwia ustawienie stopnia szczegółowości kodu QR.</span><span class="sxs-lookup"><span data-stu-id="69b64-179">**QR code error correction level** - Set the granularity of the QR code.</span></span> <span data-ttu-id="69b64-180">Wyższa dokładność może zwiększyć niezawodność kodu, ale **rozmiar kodu QR** musi być na tyle duży, aby obsługiwał poziom szczegółowości wymagany na wybranym poziomie korekty.</span><span class="sxs-lookup"><span data-stu-id="69b64-180">Higher granularity can help increase the code's reliability, but your **QR code size** must be large enough to support the level of detail required by your selected correction level.</span></span>

> [!TIP]
> - <span data-ttu-id="69b64-181">Wyświetlenie kodów QR, które są zbyt duże może trwać nieco dłużej. Zostaną przeskalowane w celu dopasowania do ekranu.</span><span class="sxs-lookup"><span data-stu-id="69b64-181">QR codes sizes that are too large for your display will take a bit longer to render and then be scaled down to fit your display.</span></span> <span data-ttu-id="69b64-182">Nie są one przydatne.</span><span class="sxs-lookup"><span data-stu-id="69b64-182">These do not provide a benefit.</span></span>
> - <span data-ttu-id="69b64-183">Zbyt małe kody QR mogą zmniejszyć zdolność HoloLens do prawidłowego odczytywania kodu w niektórych środowiskach.</span><span class="sxs-lookup"><span data-stu-id="69b64-183">QR code sizes that are too small may decrease the ability of HoloLens to read the code properly in some environments.</span></span>
> - <span data-ttu-id="69b64-184">Zaleca się przetestowanie ustawień dla każdego urządzenia, które będzie wyświetlać kody QR użytkownikom HoloLens.</span><span class="sxs-lookup"><span data-stu-id="69b64-184">We recommend that you test the settings for each device that will display QR codes for HoloLens users.</span></span> <span data-ttu-id="69b64-185">Wybierz ustawienia, które zapewniają wystarczającą czytelność w środowisku wydziału produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="69b64-185">Choose settings that provide sufficient readability in your shop floor environment.</span></span>  

## <a name="get-an-overview-of-all-guide-assignments"></a><span data-ttu-id="69b64-186">Przegląd wszystkich przypisań przewodnika</span><span class="sxs-lookup"><span data-stu-id="69b64-186">Get an overview of all Guide assignments</span></span>

<span data-ttu-id="69b64-187">Strona **Wszystkie przewodniki** umożliwia wyświetlenie listy wszystkich dostępnych przewodników w organizacji oraz wszystkich przydziałów do procesów produkcyjnych i zasobów.</span><span class="sxs-lookup"><span data-stu-id="69b64-187">Use the **All Guides** page to see the list of all available Guides in your organization and all assignments to your production processes and resources.</span></span> <span data-ttu-id="69b64-188">Aby ją otworzyć, należy przejść do **Rzeczywistość mieszana \> Przewodniki \> Wszystkie przewodniki**.</span><span class="sxs-lookup"><span data-stu-id="69b64-188">To open it, go to **Mixed reality \> Guides \> All Guides**.</span></span> <span data-ttu-id="69b64-189">Na liście u góry są widoczne wszystkie dostępne przewodniki i można je filtrować, korzystając z pola w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="69b64-189">The list at the top shows all the available Guides and you can use the field here to filter the list.</span></span> <span data-ttu-id="69b64-190">Lista na dole zawiera wszystkie przypisania przewodników oraz pasek narzędzi służący do zarządzania nimi.</span><span class="sxs-lookup"><span data-stu-id="69b64-190">The list at the bottom shows all Guide assignments and provides a toolbar for managing them.</span></span>

<span data-ttu-id="69b64-191">![Zarządzanie przewodnikami](media/instruction-guides-allguides.png "Zarządzanie przewodnikami")</span><span class="sxs-lookup"><span data-stu-id="69b64-191">![Manage Guides](media/instruction-guides-allguides.png "Manage Guides")</span></span>

<span data-ttu-id="69b64-192">W poniższych sekcjach opisano typy obiektów, do których można przypisać przewodniki.</span><span class="sxs-lookup"><span data-stu-id="69b64-192">The following sections describe the types of objects that you can assign Guides to.</span></span> <span data-ttu-id="69b64-193">Każdy przypisany przewodnik zawiera instrukcje, które są automatycznie dołączane do odpowiednich zadań produkcyjnych i będą dostępne w wydziale produkcyjnym.</span><span class="sxs-lookup"><span data-stu-id="69b64-193">Each assigned guide provides instructions that are automatically attached to the respective production jobs and will be available on the shop floor.</span></span>

## <a name="associate-a-guide-to-a-resource"></a><a name="resources"></a><span data-ttu-id="69b64-194">Kojarzenie przewodnika z zasobem</span><span class="sxs-lookup"><span data-stu-id="69b64-194">Associate a Guide to a resource</span></span>

<span data-ttu-id="69b64-195">Umożliwia dodanie przewodnika do [zasobu](operations-resources.md) w celu udostępnienia przewodnika w kontekście odpowiednich zadań produkcyjnych.</span><span class="sxs-lookup"><span data-stu-id="69b64-195">Add a Guide to a [resource](operations-resources.md) to offer the Guide in the context of relevant production jobs.</span></span>

### <a name="typical-scenario-using-resources"></a><span data-ttu-id="69b64-196">Typowy scenariusz korzystający z zasobów</span><span class="sxs-lookup"><span data-stu-id="69b64-196">Typical scenario using resources</span></span>

<span data-ttu-id="69b64-197">Można na przykład dołączyć przewodnik z ogólnymi informacjami o bezpieczeństwie maszyny lub instrukcje obsługi do zasobu typu maszyna.</span><span class="sxs-lookup"><span data-stu-id="69b64-197">For example, you could attach a Guide with general machine security or handling instructions to a resource of type machine.</span></span> <span data-ttu-id="69b64-198">Następnie przewodnik będzie dostępny we wszystkich zadaniach wykonywanych na tej maszynie.</span><span class="sxs-lookup"><span data-stu-id="69b64-198">Then, the Guide will be available on every job that is performed on the machine.</span></span>

### <a name="add-a-guide-to-a-resource"></a><span data-ttu-id="69b64-199">Dodawanie przewodnika do zasobu</span><span class="sxs-lookup"><span data-stu-id="69b64-199">Add a Guide to a resource</span></span>

<span data-ttu-id="69b64-200">Aby dodać przewodnik do zasobu:</span><span class="sxs-lookup"><span data-stu-id="69b64-200">To add a Guide to a resource:</span></span>

1. <span data-ttu-id="69b64-201">Wybierz kolejno opcje **Kontrola produkcji \> Ustawienia \> Zasoby \> Zasoby**.</span><span class="sxs-lookup"><span data-stu-id="69b64-201">Go to **Production control \> Setup \> Resources \> Resources**.</span></span>
1. <span data-ttu-id="69b64-202">Z okienka listy wybierz zasób, do którego chcesz przypisać przewodnik.</span><span class="sxs-lookup"><span data-stu-id="69b64-202">From the list pane, select the resource you want to assign a Guide to.</span></span>
1. <span data-ttu-id="69b64-203">Rozwiń skróconą kartę **Skojarzone przewodniki**.</span><span class="sxs-lookup"><span data-stu-id="69b64-203">Expand the **Associated Guides** FastTab.</span></span>
1. <span data-ttu-id="69b64-204">Wybierz opcję **Dodaj** na pasku narzędzi **Skojarzone przewodniki**.</span><span class="sxs-lookup"><span data-stu-id="69b64-204">Select **Add** from the **Associated Guides** toolbar.</span></span> <span data-ttu-id="69b64-205">Nowy wiersz zostanie dodany do siatki.</span><span class="sxs-lookup"><span data-stu-id="69b64-205">A new line is added to the grid.</span></span>
1. <span data-ttu-id="69b64-206">W przypadku nowego wiersza należy użyć listy rozwijanej w kolumnie **Nazwa**, aby wybrać przewodnik, który ma zostać przypisany.</span><span class="sxs-lookup"><span data-stu-id="69b64-206">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span> <span data-ttu-id="69b64-207">W przypadku dużej liczby przewodników można filtrować listę, aby znaleźć odpowiedni.</span><span class="sxs-lookup"><span data-stu-id="69b64-207">If you have a large number of Guides, then you can filter the list to find the one you are looking for.</span></span>
    <span data-ttu-id="69b64-208">![Zarządzanie przewodnikami](media/instruction-guides-allguides.png "Zarządzanie przewodnikami")</span><span class="sxs-lookup"><span data-stu-id="69b64-208">![Manage Guides](media/instruction-guides-allguides.png "Manage Guides")</span></span>

## <a name="associate-a-guide-to-a-resource-group"></a><a name="resource-groups"></a><span data-ttu-id="69b64-209">Kojarzenie przewodnika z grupą zasobów</span><span class="sxs-lookup"><span data-stu-id="69b64-209">Associate a Guide to a resource group</span></span>

<span data-ttu-id="69b64-210">Można dodać Przewodnik do [grup zasobów](tasks/define-discrete-manufacturing-resource-group.md), jeśli są one używane do zarządzania grupami maszyn, linii produkcyjnych lub komórek roboczych.</span><span class="sxs-lookup"><span data-stu-id="69b64-210">You can add a guide to [resource groups](tasks/define-discrete-manufacturing-resource-group.md) if you use them to manage groups of machines, production lines, or work cells.</span></span>

### <a name="typical-scenarios-using-resource-groups"></a><span data-ttu-id="69b64-211">Typowe scenariusze korzystające z grup zasobów</span><span class="sxs-lookup"><span data-stu-id="69b64-211">Typical scenarios using resource groups</span></span>

<span data-ttu-id="69b64-212">**Przykład 1:** zdefiniowano grupę zasobów dla tego samego modelu kilku maszyn.</span><span class="sxs-lookup"><span data-stu-id="69b64-212">**Example 1:** You have defined a resource group for several machines of the same model.</span></span> <span data-ttu-id="69b64-213">Zamiast przypisywać odpowiedni przewodnik obsługi modelu maszyny do każdego odpowiedniego zasobu, można przypisać przewodnik do grupy zasobów odpowiadającej danemu modelowi maszyny.</span><span class="sxs-lookup"><span data-stu-id="69b64-213">Instead of assigning the relevant handling instruction guide for the machine model to every relevant resource, you could instead assign the Guide to the resource group that reflects that machine model.</span></span>

<span data-ttu-id="69b64-214">**Przykład 2:** zdefiniowano grupę zasobów dla komórki roboczej, która zawiera różne maszyny, i istnieje przewodnik zawierający ogólne instrukcje dotyczące obsługi komórki roboczej.</span><span class="sxs-lookup"><span data-stu-id="69b64-214">**Example 2:** You have defined a resource group for a work cell that contains different machines and you have a Guide that provides general instructions for how to maintain the work cell.</span></span> <span data-ttu-id="69b64-215">Przewodnik ma zastosowanie do każdego działania produkcyjnego w tej komórce roboczej.</span><span class="sxs-lookup"><span data-stu-id="69b64-215">The Guide applies to any production activity in this work cell.</span></span>

### <a name="add-a-guide-to-a-resource-group"></a><span data-ttu-id="69b64-216">Dodawanie przewodnika do grupy zasobów</span><span class="sxs-lookup"><span data-stu-id="69b64-216">Add a Guide to a resource group</span></span>

<span data-ttu-id="69b64-217">Aby dodać przewodnik do grupy zasobów:</span><span class="sxs-lookup"><span data-stu-id="69b64-217">To add a Guide to a resource group:</span></span>

1. <span data-ttu-id="69b64-218">Wybierz kolejno opcje **Kontrola produkcji \> Ustawienia \> Zasoby \> Grupy zasobów**.</span><span class="sxs-lookup"><span data-stu-id="69b64-218">Go to **Production control \> Setup \> Resources \> Resource groups**.</span></span>
1. <span data-ttu-id="69b64-219">Z okienka listy wybierz grupę zasobów, do której chcesz przypisać przewodnik.</span><span class="sxs-lookup"><span data-stu-id="69b64-219">From the list pane, select the resource group you want to assign a Guide to.</span></span>
1. <span data-ttu-id="69b64-220">Rozwiń skróconą kartę **Skojarzone przewodniki**.</span><span class="sxs-lookup"><span data-stu-id="69b64-220">Expand the **Associated Guides** FastTab.</span></span>
1. <span data-ttu-id="69b64-221">Wybierz opcję **Dodaj** na pasku narzędzi **Skojarzone przewodniki**.</span><span class="sxs-lookup"><span data-stu-id="69b64-221">Select **Add** from the **Associated Guides** toolbar.</span></span> <span data-ttu-id="69b64-222">Nowy wiersz zostanie dodany do siatki.</span><span class="sxs-lookup"><span data-stu-id="69b64-222">A new line is added to the grid.</span></span>
1. <span data-ttu-id="69b64-223">W przypadku nowego wiersza należy użyć listy rozwijanej w kolumnie **Nazwa**, aby wybrać przewodnik, który ma zostać przypisany.</span><span class="sxs-lookup"><span data-stu-id="69b64-223">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span> <span data-ttu-id="69b64-224">W przypadku dużej liczby przewodników można filtrować listę, aby znaleźć odpowiedni.</span><span class="sxs-lookup"><span data-stu-id="69b64-224">If you have a large number of Guides, then you can filter the list to find the one you are looking for.</span></span>
    <span data-ttu-id="69b64-225">![Dodawanie przewodnika do grupy zasobów](media/instruction-guides-resourcegroup.png "Dodawanie przewodnika do grupy zasobów")</span><span class="sxs-lookup"><span data-stu-id="69b64-225">![Adding a Guide to a resource group](media/instruction-guides-resourcegroup.png "Adding a Guide to a resource group")</span></span>

## <a name="associate-a-guide-to-a-released-product"></a><a name="released-products"></a><span data-ttu-id="69b64-226">Kojarzenie przewodnika ze zwolnionym produktem</span><span class="sxs-lookup"><span data-stu-id="69b64-226">Associate a Guide to a released product</span></span>

<span data-ttu-id="69b64-227">Można dodać przewodnik do dowolnego [zwolnionego produktu](../pim/tasks/create-released-product-single-company.md).</span><span class="sxs-lookup"><span data-stu-id="69b64-227">You can add a guide to any [released product](../pim/tasks/create-released-product-single-company.md).</span></span>

### <a name="typical-scenario-using-released-products"></a><span data-ttu-id="69b64-228">Typowy scenariusz używający zwolnionych produktów</span><span class="sxs-lookup"><span data-stu-id="69b64-228">Typical scenario using released products</span></span>

<span data-ttu-id="69b64-229">Przewodniki na poziomie produktu wspomagają pracownikom wydziału produkcyjnego instrukcjami dotyczącymi działania lub obsługi określonego zwolnionego produktu lub towaru.</span><span class="sxs-lookup"><span data-stu-id="69b64-229">Product-level Guides help shop floor workers with instructions relevant to operating or handling a specific released product or item.</span></span>

### <a name="add-a-guide-to-a-released-product"></a><span data-ttu-id="69b64-230">Dodawanie przewodnika do zwolnionego produktu</span><span class="sxs-lookup"><span data-stu-id="69b64-230">Add a Guide to a released product</span></span>

<span data-ttu-id="69b64-231">Aby dodać przewodnik do zwolnionego produktu:</span><span class="sxs-lookup"><span data-stu-id="69b64-231">To add a Guide to a released product:</span></span>

1. <span data-ttu-id="69b64-232">Przejdź do **Zarządzanie informacjami o produkcji \> Produkty \> Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="69b64-232">Go to **Production information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="69b64-233">Otwórz produkt, do którego chcesz przypisać przewodnik.</span><span class="sxs-lookup"><span data-stu-id="69b64-233">Open the product you want to assign a Guide to.</span></span>
1. <span data-ttu-id="69b64-234">W okienku akcji otwórz kartę **Inżynier** i z grupy **Widok** wybierz pozycję **Skojarzone przewodniki**.</span><span class="sxs-lookup"><span data-stu-id="69b64-234">On the Action Pane, open the **Engineer** tab and from the **View** group, select **Associated Guides**.</span></span>
1. <span data-ttu-id="69b64-235">Zostanie wyświetlona strona **Skojarzone przewodniki** dla wybranego produktu.</span><span class="sxs-lookup"><span data-stu-id="69b64-235">The **Associated Guides** page opens for your selected product.</span></span>
1. <span data-ttu-id="69b64-236">W okienku akcji wybierz opcję **Dodaj**, aby dodać nowy wiersz do tabeli.</span><span class="sxs-lookup"><span data-stu-id="69b64-236">Select **Add** on the Action Pane to add a new line to the grid.</span></span> 
1. <span data-ttu-id="69b64-237">W przypadku nowego wiersza należy użyć listy rozwijanej w kolumnie **Nazwa**, aby wybrać przewodnik, który ma zostać przypisany.</span><span class="sxs-lookup"><span data-stu-id="69b64-237">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span>
    <span data-ttu-id="69b64-238">![Dodawanie przewodnika do zwolnionego produktu](media/instruction-guides-ReleasedProduct-AddGuides.png "Dodawanie przewodnika do zwolnionego produktu")</span><span class="sxs-lookup"><span data-stu-id="69b64-238">![Adding a Guide to a released product](media/instruction-guides-ReleasedProduct-AddGuides.png "Adding a Guide to a released product")</span></span>

## <a name="associate-a-guide-to-a-formula"></a><a name="formulas"></a><span data-ttu-id="69b64-239">Kojarzenie przewodnika z formułą</span><span class="sxs-lookup"><span data-stu-id="69b64-239">Associate a Guide to a formula</span></span>

<span data-ttu-id="69b64-240">Można dodać przewodnik do dowolnej [formuły](bill-of-material-bom.md#formulas-co-products-and-by-products).</span><span class="sxs-lookup"><span data-stu-id="69b64-240">You can add a guide to any [formula](bill-of-material-bom.md#formulas-co-products-and-by-products).</span></span>

### <a name="typical-scenario-using-formulas"></a><span data-ttu-id="69b64-241">Typowy scenariusz korzystający z formuł</span><span class="sxs-lookup"><span data-stu-id="69b64-241">Typical scenario using formulas</span></span>
  
<span data-ttu-id="69b64-242">Przewodniki na poziomie formuły dostarczają pracownikom wydziału produkcyjnego instrukcje obsługi w kontekście formuły lub receptury.</span><span class="sxs-lookup"><span data-stu-id="69b64-242">Formula-level Guides provide shop floor workers with guided handling instructions in the context of a formula or recipe.</span></span> <span data-ttu-id="69b64-243">Przewodniki można również przypisywać do wersji formuły.</span><span class="sxs-lookup"><span data-stu-id="69b64-243">Guides can also be assigned to versions of a formula.</span></span>

> [!NOTE]
> <span data-ttu-id="69b64-244">Istnieje możliwość przypisania wskazówek dotyczących procesów produkcyjnych na podstawie formuły do marszruty, wersji marszruty lub relacji operacji marszruty.</span><span class="sxs-lookup"><span data-stu-id="69b64-244">You can assign guidance relevant for production processes based on a formula to a route, route version, or route operation relations.</span></span>  

> <span data-ttu-id="69b64-245">Nie można obecnie dołączać przewodników do pojedynczych wierszy formuły.</span><span class="sxs-lookup"><span data-stu-id="69b64-245">Guides can't currently be attached to individual formula lines.</span></span>

### <a name="add-a-guide-to-a-formula"></a><span data-ttu-id="69b64-246">Dodawanie przewodnika do formuły</span><span class="sxs-lookup"><span data-stu-id="69b64-246">Add a Guide to a formula</span></span>

<span data-ttu-id="69b64-247">Aby dodać przewodnik do formuły:</span><span class="sxs-lookup"><span data-stu-id="69b64-247">To add a Guide to a formula:</span></span>

1. <span data-ttu-id="69b64-248">Wybierz kolejno opcje **Zarządzanie informacjami o produkcji \> Listy składowe (BOM) i formuły \> Formuły**.</span><span class="sxs-lookup"><span data-stu-id="69b64-248">Go to **Production information management \> Bills of materials and formulas \> Formulas**.</span></span>
1. <span data-ttu-id="69b64-249">Otwórz formułę, do której chcesz przypisać przewodnik.</span><span class="sxs-lookup"><span data-stu-id="69b64-249">Open the formula you want to assign a Guide to.</span></span>
1. <span data-ttu-id="69b64-250">Otwórz kartę **Nagłówek** nad górną skróconą kartą.</span><span class="sxs-lookup"><span data-stu-id="69b64-250">Open the **Header** tab above the top FastTab.</span></span>
1. <span data-ttu-id="69b64-251">Rozwiń skróconą kartę **Skojarzone przewodniki**.</span><span class="sxs-lookup"><span data-stu-id="69b64-251">Expand the **Associated Guides** FastTab.</span></span>
1. <span data-ttu-id="69b64-252">Wybierz opcję **Dodaj** na pasku narzędzi **Skojarzone przewodniki**.</span><span class="sxs-lookup"><span data-stu-id="69b64-252">Select **Add** from the **Associated Guides** toolbar.</span></span> <span data-ttu-id="69b64-253">Nowy wiersz zostanie dodany do siatki.</span><span class="sxs-lookup"><span data-stu-id="69b64-253">A new line is added to the grid.</span></span>
1. <span data-ttu-id="69b64-254">W przypadku nowego wiersza należy użyć listy rozwijanej w kolumnie **Nazwa**, aby wybrać przewodnik, który ma zostać przypisany.</span><span class="sxs-lookup"><span data-stu-id="69b64-254">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span>
    <span data-ttu-id="69b64-255">![Dodawanie przewodnika do formuły](media/instruction-guides-Formula.png "Dodawanie przewodnika do formuły")</span><span class="sxs-lookup"><span data-stu-id="69b64-255">![Adding a Guide to a formula](media/instruction-guides-Formula.png "Adding a Guide to a formula")</span></span>

## <a name="associate-a-guide-to-a-formula-version"></a><a name="formula-versions"></a><span data-ttu-id="69b64-256">Kojarzenie przewodnika z wersją formuły</span><span class="sxs-lookup"><span data-stu-id="69b64-256">Associate a Guide to a formula version</span></span>

<span data-ttu-id="69b64-257">Można dodać przewodnik do dowolnej [wersji formuły](bill-of-material-bom.md#bom-and-formula-versions).</span><span class="sxs-lookup"><span data-stu-id="69b64-257">You can add a guide to any [formula version](bill-of-material-bom.md#bom-and-formula-versions).</span></span>

### <a name="typical-scenario-using-formula-versions"></a><span data-ttu-id="69b64-258">Typowy scenariusz korzystający z wersji formuły</span><span class="sxs-lookup"><span data-stu-id="69b64-258">Typical scenario using formula versions</span></span>

<span data-ttu-id="69b64-259">Przewodniki dołączone do poszczególnych wersji formuły udostępniają pracownikom wydziału produkcyjnego instrukcje dotyczące produkcji tej wersji receptury formuły.</span><span class="sxs-lookup"><span data-stu-id="69b64-259">Guides attached to an individual version of a formula provide shop floor workers with instructions that walk through the production of that version of the formula recipe.</span></span>

> [!TIP]
> <span data-ttu-id="69b64-260">Istnieje możliwość przypisania wskazówek dotyczących procesów produkcyjnych na podstawie tej wersji formuły do marszruty, wersji marszruty lub relacji operacji marszruty.</span><span class="sxs-lookup"><span data-stu-id="69b64-260">You can assign guidance relevant for production processes based on this formula version to a route, route version, or route operation relations.</span></span>  

> [!NOTE]
> <span data-ttu-id="69b64-261">Nie można obecnie dołączać przewodników do pojedynczych wierszy formuły.</span><span class="sxs-lookup"><span data-stu-id="69b64-261">Guides can't currently be attached to individual formula lines.</span></span>

### <a name="add-a-guide-to-a-formula-version"></a><span data-ttu-id="69b64-262">Dodawanie przewodnika do wersji formuły</span><span class="sxs-lookup"><span data-stu-id="69b64-262">Add a Guide to a formula version</span></span>

<span data-ttu-id="69b64-263">Aby dodać przewodnik do wersji formuły:</span><span class="sxs-lookup"><span data-stu-id="69b64-263">To add a Guide to a formula version:</span></span>

1. <span data-ttu-id="69b64-264">Wybierz kolejno opcje **Zarządzanie informacjami o produkcji \> Listy składowe (BOM) i formuły \> Formuły**.</span><span class="sxs-lookup"><span data-stu-id="69b64-264">Go to **Production information management \> Bills of materials and formulas \> Formulas**.</span></span>
1. <span data-ttu-id="69b64-265">Otwórz formułę zawierającą wersję, do której chcesz przypisać przewodnik.</span><span class="sxs-lookup"><span data-stu-id="69b64-265">Open the formula that includes a version that you want to assign a Guide to.</span></span>
1. <span data-ttu-id="69b64-266">Otwórz kartę **Nagłówek** nad górną skróconą kartą.</span><span class="sxs-lookup"><span data-stu-id="69b64-266">Open the **Header** tab above the top FastTab.</span></span>
1. <span data-ttu-id="69b64-267">Na skróconej karcie **Wersje formuły** wybierz wersję, do której chcesz przypisać przewodnik.</span><span class="sxs-lookup"><span data-stu-id="69b64-267">On the **Formula versions** FastTab, select the version you want to assign a Guide to.</span></span>
1. <span data-ttu-id="69b64-268">Na pasku narzędzi **Wersje formuły** wybierz opcję **Skojarzone przewodniki**.</span><span class="sxs-lookup"><span data-stu-id="69b64-268">On the **Formula versions** toolbar, select **Associated Guides**.</span></span>
    <span data-ttu-id="69b64-269">![Otwieranie przewodników skojarzonych z wybraną wersją formuły](media/instruction-guides-FormulaVersion.png "Otwieranie przewodników skojarzonych z wybraną wersją formuły")</span><span class="sxs-lookup"><span data-stu-id="69b64-269">![Open the Guides associated with a selected formula version](media/instruction-guides-FormulaVersion.png "Open the Guides associated with a selected formula version")</span></span>
1. <span data-ttu-id="69b64-270">Zostanie wyświetlona strona **Skojarzone przewodniki** dla wybranej wersji formuły.</span><span class="sxs-lookup"><span data-stu-id="69b64-270">The **Associated Guides** page opens for your formula version.</span></span>
1. <span data-ttu-id="69b64-271">W okienku akcji wybierz opcję **Dodaj**, aby dodać nowy wiersz do tabeli.</span><span class="sxs-lookup"><span data-stu-id="69b64-271">Select **Add** on the Action Pane to add a new line to the grid.</span></span> 
1. <span data-ttu-id="69b64-272">W przypadku nowego wiersza należy użyć listy rozwijanej w kolumnie **Nazwa**, aby wybrać przewodnik, który ma zostać przypisany.</span><span class="sxs-lookup"><span data-stu-id="69b64-272">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span>
    <span data-ttu-id="69b64-273">![Dodawanie przewodnika do wersji formuły](media/instruction-guides-FormulaVersionAddGuide.png "Dodawanie przewodnika do wersji formuły")</span><span class="sxs-lookup"><span data-stu-id="69b64-273">![Adding a Guide to a formula version](media/instruction-guides-FormulaVersionAddGuide.png "Adding a Guide to a formula version")</span></span>

## <a name="associate-a-guide-to-a-bill-of-materials"></a><a name="bom"></a><span data-ttu-id="69b64-274">Kojarzenie przewodnika z listą składową (BOM)</span><span class="sxs-lookup"><span data-stu-id="69b64-274">Associate a Guide to a bill of materials</span></span>

<span data-ttu-id="69b64-275">Można dodać przewodnik do dowolnej [listy składowej](bill-of-material-bom.md) (BOM).</span><span class="sxs-lookup"><span data-stu-id="69b64-275">You can add a guide to any [bill of materials](bill-of-material-bom.md) (BOM).</span></span>

### <a name="typical-scenario-using-bills-of-materials"></a><span data-ttu-id="69b64-276">Typowy scenariusz korzystający z listy składowej</span><span class="sxs-lookup"><span data-stu-id="69b64-276">Typical scenario using bills of materials</span></span>

<span data-ttu-id="69b64-277">Przewodniki dołączone do BOM zapewniają pracownikom wydziału produkcji instrukcje opisujące sposób przygotowywania i obsługi materiałów z BOM.</span><span class="sxs-lookup"><span data-stu-id="69b64-277">Guides attached to a BOM provide shop floor workers with instructions that explain how to prepare and handle material from a BOM.</span></span> <span data-ttu-id="69b64-278">Przewodniki można również przypisywać do BOM.</span><span class="sxs-lookup"><span data-stu-id="69b64-278">Guides can also be assigned to versions of a BOM.</span></span>

> [!NOTE]
> <span data-ttu-id="69b64-279">Nie można obecnie dołączać przewodników do pojedynczych wierszy BOM.</span><span class="sxs-lookup"><span data-stu-id="69b64-279">Guides can't currently be attached to individual BOM lines.</span></span>

### <a name="add-a-guide-to-a-bill-of-materials"></a><span data-ttu-id="69b64-280">Dodawanie przewodnika do listy składowej (BOM)</span><span class="sxs-lookup"><span data-stu-id="69b64-280">Add a Guide to a bill of materials</span></span>

<span data-ttu-id="69b64-281">Aby dodać przewodnik do listy składowej (BOM):</span><span class="sxs-lookup"><span data-stu-id="69b64-281">To add a Guide to a bill of material:</span></span>

1. <span data-ttu-id="69b64-282">Wybierz kolejno opcje **Zarządzenie informacjami o produkcji \> Lista składowe (BOM) i formuły \> Listy składowe (BOM)**.</span><span class="sxs-lookup"><span data-stu-id="69b64-282">Go to **Production information management \> Bills of materials and formulas \> Bills of materials**.</span></span>
1. <span data-ttu-id="69b64-283">Otwórz listę składową (BOM), do której chcesz przypisać przewodnik.</span><span class="sxs-lookup"><span data-stu-id="69b64-283">Open the bill of materials that you want to assign a Guide to.</span></span>
1. <span data-ttu-id="69b64-284">Otwórz kartę **Nagłówek** nad górną skróconą kartą.</span><span class="sxs-lookup"><span data-stu-id="69b64-284">Open the **Header** tab above the top FastTab.</span></span>
1. <span data-ttu-id="69b64-285">Rozwiń skróconą kartę **Skojarzone przewodniki**.</span><span class="sxs-lookup"><span data-stu-id="69b64-285">Expand the **Associated Guides** FastTab.</span></span>
1. <span data-ttu-id="69b64-286">Wybierz opcję **Dodaj** na pasku narzędzi **Skojarzone przewodniki**.</span><span class="sxs-lookup"><span data-stu-id="69b64-286">Select **Add** from the **Associated Guides** toolbar.</span></span> <span data-ttu-id="69b64-287">Nowy wiersz zostanie dodany do siatki.</span><span class="sxs-lookup"><span data-stu-id="69b64-287">A new line is added to the grid.</span></span>
1. <span data-ttu-id="69b64-288">W przypadku nowego wiersza należy użyć listy rozwijanej w kolumnie **Nazwa**, aby wybrać przewodnik, który ma zostać przypisany.</span><span class="sxs-lookup"><span data-stu-id="69b64-288">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span>
    <span data-ttu-id="69b64-289">![Dodawanie przewodnika do BOM](media/instruction-guides-BOM.png "Dodawanie przewodnika do listy składowej (BOM)")</span><span class="sxs-lookup"><span data-stu-id="69b64-289">![Adding a Guide to a BOM](media/instruction-guides-BOM.png "Adding a Guide to a BOM")</span></span>

## <a name="associate-a-guide-to-a-bill-of-materials-version"></a><a name="bom-versions"></a><span data-ttu-id="69b64-290">Kojarzenie przewodnika z wersją listy składowej (BOM)</span><span class="sxs-lookup"><span data-stu-id="69b64-290">Associate a Guide to a bill of materials version</span></span>

<span data-ttu-id="69b64-291">Można dodać przewodnik do dowolnej [wersji listy składowej](bill-of-material-bom.md#bom-and-formula-versions) (BOM).</span><span class="sxs-lookup"><span data-stu-id="69b64-291">You can add a guide to any [bill of materials version](bill-of-material-bom.md#bom-and-formula-versions).</span></span>

### <a name="typical-scenario-using-bill-of-materials-versions"></a><span data-ttu-id="69b64-292">Typowy scenariusz korzystający z listy składowej (BOM)</span><span class="sxs-lookup"><span data-stu-id="69b64-292">Typical scenario using bill of materials versions</span></span>

<span data-ttu-id="69b64-293">Przewodniki dołączone do poszczególnych wersji BOM dostarczają pracownikom warsztatów instrukcje, które opisują sposób przygotowania i obsługi materiałów dla wersji BOM, która różni się od ogólnej listy BOM lub innych jej wersji.</span><span class="sxs-lookup"><span data-stu-id="69b64-293">Guides attached to an individual BOM version provide shop floor workers with instructions that explain how to prepare and handle material for a version of a BOM that is different from the generic BOM or other versions of it.</span></span>

> [!NOTE]
> <span data-ttu-id="69b64-294">Nie można obecnie dołączać przewodników do pojedynczych wierszy BOM.</span><span class="sxs-lookup"><span data-stu-id="69b64-294">Guides can't currently be attached to individual BOM lines.</span></span>

### <a name="add-a-guide-to-a-bill-of-materials-version"></a><span data-ttu-id="69b64-295">Dodawanie przewodnika do wersji listy składowej (BOM)</span><span class="sxs-lookup"><span data-stu-id="69b64-295">Add a Guide to a bill of materials version</span></span>

<span data-ttu-id="69b64-296">Aby dodać przewodnik do wersji listy składowej (BOM):</span><span class="sxs-lookup"><span data-stu-id="69b64-296">To add a Guide to a bill of materials version:</span></span>

1. <span data-ttu-id="69b64-297">Wybierz kolejno opcje **Zarządzenie informacjami o produkcji \> Lista składowe (BOM) i formuły \> Listy składowe (BOM)**.</span><span class="sxs-lookup"><span data-stu-id="69b64-297">Go to **Production information management \> Bills of materials and formulas \> Bills of materials**.</span></span>
1. <span data-ttu-id="69b64-298">Otwórz BOM zawierającą wersję, do której chcesz przypisać przewodnik.</span><span class="sxs-lookup"><span data-stu-id="69b64-298">Open the BOM that includes a version that you want to assign a Guide to.</span></span>
1. <span data-ttu-id="69b64-299">Otwórz kartę **Nagłówek** nad górną skróconą kartą.</span><span class="sxs-lookup"><span data-stu-id="69b64-299">Open the **Header** tab above the top FastTab.</span></span>
1. <span data-ttu-id="69b64-300">Na skróconej karcie **Wersje BOM** wybierz wersję, do której chcesz przypisać przewodnik.</span><span class="sxs-lookup"><span data-stu-id="69b64-300">On the **BOM versions** FastTab, select the version you want to assign a Guide to.</span></span>
1. <span data-ttu-id="69b64-301">Na pasku narzędzi **Wersje BOM** wybierz opcję **Skojarzone przewodniki**.</span><span class="sxs-lookup"><span data-stu-id="69b64-301">On the **BOM versions** toolbar, select **Associated Guides**.</span></span>
    <span data-ttu-id="69b64-302">![Otwieranie przewodników skojarzonych z wybraną wersją BOM](media/instruction-guides-BOMVersion.png "Otwieranie przewodników skojarzonych z wybraną wersją BOM")</span><span class="sxs-lookup"><span data-stu-id="69b64-302">![Open the Guides associated with a selected BOM version](media/instruction-guides-BOMVersion.png "Open the Guides associated with a selected BOM version")</span></span>
1. <span data-ttu-id="69b64-303">Zostanie wyświetlona strona **Skojarzone przewodniki** dla wybranej wersji BOM.</span><span class="sxs-lookup"><span data-stu-id="69b64-303">The **Associated Guides** page opens for your BOM version.</span></span>
1. <span data-ttu-id="69b64-304">W okienku akcji wybierz opcję **Dodaj**, aby dodać nowy wiersz do tabeli.</span><span class="sxs-lookup"><span data-stu-id="69b64-304">Select **Add** on the Action Pane to add a new line to the grid.</span></span>
1. <span data-ttu-id="69b64-305">W przypadku nowego wiersza należy użyć listy rozwijanej w kolumnie **Nazwa**, aby wybrać przewodnik, który ma zostać przypisany.</span><span class="sxs-lookup"><span data-stu-id="69b64-305">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span>
    <span data-ttu-id="69b64-306">![Dodawanie przewodnika do wersji BOM](media/instruction-guides-BOMVersionAddGuide.png "Dodawanie przewodnika do wersji BOM")</span><span class="sxs-lookup"><span data-stu-id="69b64-306">![Adding a Guide to a BOM version](media/instruction-guides-BOMVersionAddGuide.png "Adding a Guide to a BOM version")</span></span>

## <a name="associate-a-guide-to-a-route"></a><a name="routes"></a><span data-ttu-id="69b64-307">Kojarzenie przewodnika z marszrutą</span><span class="sxs-lookup"><span data-stu-id="69b64-307">Associate a Guide to a route</span></span>

<span data-ttu-id="69b64-308">Można dodać przewodnik do dowolnej [marszruty](routes-operations.md).</span><span class="sxs-lookup"><span data-stu-id="69b64-308">You can add a guide to any [route](routes-operations.md).</span></span>

### <a name="typical-scenario-using-routes"></a><span data-ttu-id="69b64-309">Typowy scenariusz korzystający z marszrut</span><span class="sxs-lookup"><span data-stu-id="69b64-309">Typical scenario using routes</span></span>

<span data-ttu-id="69b64-310">Marszruty służą zwykle do określania sposobu, w jaki dany zwolniony produkt jest produkowany na podstawie BOM lub wersji BOM oraz za pomocą zestawu zasobów lub grup zasobów.</span><span class="sxs-lookup"><span data-stu-id="69b64-310">Routes are typically used to specify how a certain released product shall be produced based on a BOM or BOM version and with a set of resources or resource groups.</span></span>

<span data-ttu-id="69b64-311">Przypisz przewodnik do marszruty, aby zapewnić instrukcje krok po kroku dotyczące odpowiedniego procesu produkcji.</span><span class="sxs-lookup"><span data-stu-id="69b64-311">Assign a Guide to a route to provide step-by-step instructions for the respective production process.</span></span>

### <a name="add-a-guide-to-a-route"></a><span data-ttu-id="69b64-312">Dodawanie przewodnika do marszruty</span><span class="sxs-lookup"><span data-stu-id="69b64-312">Add a Guide to a route</span></span>

<span data-ttu-id="69b64-313">Aby dodać przewodnik do marszruty:</span><span class="sxs-lookup"><span data-stu-id="69b64-313">To add a Guide to a route:</span></span>

1. <span data-ttu-id="69b64-314">Przejdź do **Kontrola produkcji \> Wszystkie marszruty**.</span><span class="sxs-lookup"><span data-stu-id="69b64-314">Go to **Production control \> All routes**.</span></span>
1. <span data-ttu-id="69b64-315">Otwórz marszrutę, do której chcesz przypisać przewodnik.</span><span class="sxs-lookup"><span data-stu-id="69b64-315">Open the route that you want to assign a Guide to.</span></span>
1. <span data-ttu-id="69b64-316">Rozwiń skróconą kartę **Skojarzone przewodniki**.</span><span class="sxs-lookup"><span data-stu-id="69b64-316">Expand the **Associated Guides** FastTab.</span></span>
1. <span data-ttu-id="69b64-317">Wybierz opcję **Dodaj** na pasku narzędzi **Skojarzone przewodniki**.</span><span class="sxs-lookup"><span data-stu-id="69b64-317">Select **Add** from the **Associated Guides** toolbar.</span></span> <span data-ttu-id="69b64-318">Nowy wiersz zostanie dodany do siatki.</span><span class="sxs-lookup"><span data-stu-id="69b64-318">A new line is added to the grid.</span></span>
1. <span data-ttu-id="69b64-319">W przypadku nowego wiersza należy użyć listy rozwijanej w kolumnie **Nazwa**, aby wybrać przewodnik, który ma zostać przypisany.</span><span class="sxs-lookup"><span data-stu-id="69b64-319">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span>
    <span data-ttu-id="69b64-320">![Dodawanie przewodnika do marszruty](media/instruction-guides-Route.png "Dodawanie przewodnika do marszruty")</span><span class="sxs-lookup"><span data-stu-id="69b64-320">![Adding a Guide to a route](media/instruction-guides-Route.png "Adding a Guide to a route")</span></span>

## <a name="associate-a-guide-to-a-route-version"></a><a name="route-versions"></a><span data-ttu-id="69b64-321">Kojarzenie przewodnika z wersją marszruty</span><span class="sxs-lookup"><span data-stu-id="69b64-321">Associate a Guide to a route version</span></span>

<span data-ttu-id="69b64-322">Można dodać przewodnik do dowolnej [wersji marszruty](routes-operations.md#route-versions).</span><span class="sxs-lookup"><span data-stu-id="69b64-322">You can add a guide to any [route version](routes-operations.md#route-versions).</span></span>

### <a name="typical-scenario-using-route-versions"></a><span data-ttu-id="69b64-323">Typowy scenariusz korzystający z wersji marszruty</span><span class="sxs-lookup"><span data-stu-id="69b64-323">Typical scenario using route versions</span></span>

<span data-ttu-id="69b64-324">Wersje marszrut są zwykle używane do określania wariantów procesów produkcyjnych na podstawie istniejącej marszruty.</span><span class="sxs-lookup"><span data-stu-id="69b64-324">Routes versions are typically used to specify variants of production processes based on an existing route.</span></span> <span data-ttu-id="69b64-325">Do każdej wersji marszruty można przypisać różne przewodniki.</span><span class="sxs-lookup"><span data-stu-id="69b64-325">You can assign different Guides to each route version.</span></span>

### <a name="add-a-guide-to-a-route-version"></a><span data-ttu-id="69b64-326">Dodawanie przewodnika do wersji marszruty</span><span class="sxs-lookup"><span data-stu-id="69b64-326">Add a Guide to a route version</span></span>

<span data-ttu-id="69b64-327">Aby dodać przewodnik do wersji marszruty:</span><span class="sxs-lookup"><span data-stu-id="69b64-327">To add a Guide to a route version:</span></span>

1. <span data-ttu-id="69b64-328">Przejdź do **Kontrola produkcji \> Wszystkie marszruty**.</span><span class="sxs-lookup"><span data-stu-id="69b64-328">Go to **Production control \> All routes**.</span></span>
1. <span data-ttu-id="69b64-329">Otwórz marszrutę, do której chcesz przypisać przewodnik.</span><span class="sxs-lookup"><span data-stu-id="69b64-329">Open the route that you want to assign a Guide to.</span></span>
1. <span data-ttu-id="69b64-330">Na skróconej karcie **Wersje** wybierz wersję, do której chcesz przypisać przewodnik.</span><span class="sxs-lookup"><span data-stu-id="69b64-330">On the **Versions** FastTab, select the version you want to assign a Guide to.</span></span>
1. <span data-ttu-id="69b64-331">Na pasku narzędzi **Wersje** wybierz opcję **Skojarzone przewodniki**.</span><span class="sxs-lookup"><span data-stu-id="69b64-331">On the **Versions** toolbar, select **Associated Guides**.</span></span>
    <span data-ttu-id="69b64-332">![Otwieranie przewodników skojarzonych z wybraną wersją marszruty](media/instruction-guides-RouteVersion.png "Otwieranie przewodników skojarzonych z wybraną wersją marszruty")</span><span class="sxs-lookup"><span data-stu-id="69b64-332">![Open the Guides associated with a selected route version](media/instruction-guides-RouteVersion.png "Open the Guides associated with a selected route version")</span></span>
1. <span data-ttu-id="69b64-333">Zostanie wyświetlona strona **Skojarzone przewodniki** dla wybranej wersji BOM.</span><span class="sxs-lookup"><span data-stu-id="69b64-333">The **Associated Guides** page opens for your BOM version.</span></span>
1. <span data-ttu-id="69b64-334">W okienku akcji wybierz opcję **Dodaj**, aby dodać nowy wiersz do tabeli.</span><span class="sxs-lookup"><span data-stu-id="69b64-334">Select **Add** on the Action Pane to add a new line to the grid.</span></span>
1. <span data-ttu-id="69b64-335">W przypadku nowego wiersza należy użyć listy rozwijanej w kolumnie **Nazwa**, aby wybrać przewodnik, który ma zostać przypisany.</span><span class="sxs-lookup"><span data-stu-id="69b64-335">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span>
    <span data-ttu-id="69b64-336">![Dodawanie przewodnika do wersji marszruty](media/instruction-guides-RouteVersionAddGuide.png "Dodawanie przewodnika do wersji marszruty")</span><span class="sxs-lookup"><span data-stu-id="69b64-336">![Adding a Guide to a route version](media/instruction-guides-RouteVersionAddGuide.png "Adding a Guide to a route version")</span></span>

## <a name="associate-a-guide-to-a-route-operation-relation"></a><a name="route-operation-relations"></a><span data-ttu-id="69b64-337">Kojarzenie przewodnika z relacją operacji marszruty</span><span class="sxs-lookup"><span data-stu-id="69b64-337">Associate a Guide to a route operation relation</span></span>

<span data-ttu-id="69b64-338">Można dodać przewodnik do dowolnej [relacji operacji marszruty](routes-operations.md#operation-relations).</span><span class="sxs-lookup"><span data-stu-id="69b64-338">You can add a guide to any [route operation relation](routes-operations.md#operation-relations).</span></span>

### <a name="typical-scenario-using-route-operation-relations"></a><span data-ttu-id="69b64-339">Typowy scenariusz używający relacji operacji marszruty</span><span class="sxs-lookup"><span data-stu-id="69b64-339">Typical scenario using route operation relations</span></span>

<span data-ttu-id="69b64-340">Relacje operacji są najbardziej szczegółowym sposobem dodawania wskazówek do procesu produktu oraz związanych z nim operacji.</span><span class="sxs-lookup"><span data-stu-id="69b64-340">Operation relations are the most specific way to add guidance to a product process and its related operations.</span></span> <span data-ttu-id="69b64-341">Można określić wytyczne dla każdej operacji w marszrucie i określić różne wskazówki dla każdego typu kontekstu relacji określonego dla marszruty, na przykład dla określonych towarów, konfiguracji itp.</span><span class="sxs-lookup"><span data-stu-id="69b64-341">You can specify guidance for each operation in a route and specify different guidance for any type of relation context specified for a route, such as for specific items, configurations, and more.</span></span> <span data-ttu-id="69b64-342">Można również określić etapy operacji, na które mają być stosowane wskazówki (np. ustawienia, kolejkowanie, proces lub transport).</span><span class="sxs-lookup"><span data-stu-id="69b64-342">You can also specify to which stages in the operation the guidance applies (such as setup, queueing, process, or transport).</span></span>

> [!NOTE]
> <span data-ttu-id="69b64-343">Jeśli dla kilku relacji operacji w marszrucie zostaną określone przewodniki, w oddziale produkcyjnym dla wygenerowanych zadań będą wyświetlane tylko informacje o przewodniku z najbardziej szczegółowej relacji.</span><span class="sxs-lookup"><span data-stu-id="69b64-343">If you specify guides for several operation relations of a route, among those guides, only the guide from the most specific relation will be show on the shop floor for the generated job.</span></span>

### <a name="add-a-guide-to-a-route-operation-relation"></a><span data-ttu-id="69b64-344">Dodawanie przewodnika do relacji operacji marszruty</span><span class="sxs-lookup"><span data-stu-id="69b64-344">Add a Guide to a route operation relation</span></span>

<span data-ttu-id="69b64-345">Aby dodać przewodnik do relacji operacji marszruty:</span><span class="sxs-lookup"><span data-stu-id="69b64-345">To add a Guide to a route operation relation:</span></span>

1. <span data-ttu-id="69b64-346">Przejdź do **Kontrola produkcji \> Wszystkie marszruty**.</span><span class="sxs-lookup"><span data-stu-id="69b64-346">Go to **Production control \> All routes**.</span></span>
1. <span data-ttu-id="69b64-347">Otwórz marszrutę, do której chcesz przypisać przewodnik.</span><span class="sxs-lookup"><span data-stu-id="69b64-347">Open the route that you want to assign a Guide to.</span></span>
1. <span data-ttu-id="69b64-348">W okienku akcji otwórz kartę **Marszruta** i z grupy **Obsługa** wybierz pozycję **Szczegóły marszruty**.</span><span class="sxs-lookup"><span data-stu-id="69b64-348">On the Action Pane, open the **Route** tab and from the **Maintain** group, select **Route details**.</span></span>
1. <span data-ttu-id="69b64-349">Zostanie otwarta strona **Szczegóły marszruty** dla wybranej marszruty.</span><span class="sxs-lookup"><span data-stu-id="69b64-349">The **Route details** page opens for your selected rout.</span></span>
1. <span data-ttu-id="69b64-350">W górnej tabeli wybierz operację, dla której chcesz podać wskazówki.</span><span class="sxs-lookup"><span data-stu-id="69b64-350">In the top grid, select the operation you want to provide guidance for.</span></span>
1. <span data-ttu-id="69b64-351">W dolnej tabeli wybierz określoną relację (lub ogólną relację **Wszystkie**).</span><span class="sxs-lookup"><span data-stu-id="69b64-351">In the bottom grid, select a specific relation (or the generic **All** relation).</span></span>
    <span data-ttu-id="69b64-352">![Wybór operacji, a następnie jej relacji](media/instruction-guides-RouteOperationRelation.png "Wybór operacji, a następnie jej relacji")</span><span class="sxs-lookup"><span data-stu-id="69b64-352">![Select an operation and then a relation](media/instruction-guides-RouteOperationRelation.png "Select an operation and then a relation")</span></span>
1. <span data-ttu-id="69b64-353">Nad dolną tabelą otwórz kartę **Skojarzone przewodniki**. ![Karta Skojarzone przewodniki](media/instruction-guides-RouteOperationRelation-AddGuide.png "Karta Skojarzone przewodniki")</span><span class="sxs-lookup"><span data-stu-id="69b64-353">Above the bottom gird, open the **Associated Guides** tab.  ![The Associated Guides tab](media/instruction-guides-RouteOperationRelation-AddGuide.png "The Associated Guides tab")</span></span>
1. <span data-ttu-id="69b64-354">Wybierz opcję **Dodaj** z paska narzędzi u góry dolnej tabeli, aby dodać nowy wiersz do tabeli.</span><span class="sxs-lookup"><span data-stu-id="69b64-354">Select **Add** from the toolbar at the top of the bottom grid to add a new line to the grid.</span></span>
1. <span data-ttu-id="69b64-355">W przypadku nowego wiersza należy użyć listy rozwijanej w kolumnie **Nazwa**, aby wybrać przewodnik, który ma zostać przypisany.</span><span class="sxs-lookup"><span data-stu-id="69b64-355">For the new row, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span> <span data-ttu-id="69b64-356">W pozostałej części wiersza zaznacz pole wyboru dla każdego kontekstu, w którym ma być dostępny wybrany przewodnik.</span><span class="sxs-lookup"><span data-stu-id="69b64-356">In the rest of the row, select the check box for each context where the selected Guide should be available.</span></span>

> [!NOTE]
> <span data-ttu-id="69b64-357">Można dodać jedną lub więcej przewodników dla każdego etapu operacji.</span><span class="sxs-lookup"><span data-stu-id="69b64-357">You can add one or more guides for each stage of each operation.</span></span>

## <a name="select-guides-from-the-shop-floor-execution-interface"></a><span data-ttu-id="69b64-358">Wybór przewodnika z interfejsu obsługi wydziału produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="69b64-358">Select guides from the shop floor execution interface</span></span>

<span data-ttu-id="69b64-359">Gdy pracownik otwiera listę zadań w interfejsie obsługi wydziału produkcyjnego, moduł Supply Chain Management znajduje odpowiednie przewodniki dla pokazanych zadań.</span><span class="sxs-lookup"><span data-stu-id="69b64-359">When a worker opens a job list on the shop floor execution interface, Supply Chain Management finds the relevant guides for the jobs shown.</span></span> <span data-ttu-id="69b64-360">Użyj przycisku **Przewodniki**, aby wyświetlić odpowiednie przewodniki.</span><span class="sxs-lookup"><span data-stu-id="69b64-360">Use the **Guides** button to view the relevant guides.</span></span>

<span data-ttu-id="69b64-361">![Przycisk Przewodniki w interfejsie obsługi wydziału produkcyjnego](media/instruction-guides-Shopfloor1.png "Przycisk Przewodniki w interfejsie obsługi wydziału produkcyjnego")</span><span class="sxs-lookup"><span data-stu-id="69b64-361">![Guides button in the shop floor execution interface](media/instruction-guides-Shopfloor1.png "Guides button in the shop floor execution interface")</span></span>

<span data-ttu-id="69b64-362">Następnie załóż odpowiednie HoloLens i uzyskaj dostęp do odpowiedniego przewodnika, patrząc na kod QR i włączając odpowiedni przewodnik.</span><span class="sxs-lookup"><span data-stu-id="69b64-362">Then put on a HoloLens and access the respective guide by glancing at the QR code and activating the respective Guide.</span></span>

<span data-ttu-id="69b64-363">![Kod QR dostępu do przewodników przy użyciu HoloLens](media/instruction-guides-Shopfloor2.png "Kod QR dostępu do przewodników przy użyciu HoloLens")</span><span class="sxs-lookup"><span data-stu-id="69b64-363">![QR code to access guides using a HoloLens](media/instruction-guides-Shopfloor2.png "QR code to access guides using a HoloLens")</span></span>

## <a name="resolving-the-logic-for-selecting-guides"></a><a name="logic"></a><span data-ttu-id="69b64-364">Rozpoznawanie logiki wybierania przewodników</span><span class="sxs-lookup"><span data-stu-id="69b64-364">Resolving the logic for selecting Guides</span></span>

<span data-ttu-id="69b64-365">Można dodać przewodniki do następujących danych produkcyjnych:</span><span class="sxs-lookup"><span data-stu-id="69b64-365">You can add Guides to the following production data:</span></span>

- [<span data-ttu-id="69b64-366">Zasoby</span><span class="sxs-lookup"><span data-stu-id="69b64-366">Resources</span></span>](#resources)
- [<span data-ttu-id="69b64-367">Grupy zasobów</span><span class="sxs-lookup"><span data-stu-id="69b64-367">Resource groups</span></span>](#resource-groups)
- [<span data-ttu-id="69b64-368">Zwolnione produkty</span><span class="sxs-lookup"><span data-stu-id="69b64-368">Released products</span></span>](#released-products)
- [<span data-ttu-id="69b64-369">Formuły</span><span class="sxs-lookup"><span data-stu-id="69b64-369">Formulas</span></span>](#formulas)
- [<span data-ttu-id="69b64-370">Wersje formuły</span><span class="sxs-lookup"><span data-stu-id="69b64-370">Formula versions</span></span>](#formula-versions)
- [<span data-ttu-id="69b64-371">List składowych (BOM)</span><span class="sxs-lookup"><span data-stu-id="69b64-371">Bills of material (BOMs)</span></span>](#bom)
- [<span data-ttu-id="69b64-372">Wersji BOM</span><span class="sxs-lookup"><span data-stu-id="69b64-372">BOM versions</span></span>](#bom-versions)
- [<span data-ttu-id="69b64-373">Marszruty</span><span class="sxs-lookup"><span data-stu-id="69b64-373">Routes</span></span>](#routes)
- [<span data-ttu-id="69b64-374">Wersje marszruty</span><span class="sxs-lookup"><span data-stu-id="69b64-374">Route versions</span></span>](#route-versions)
- [<span data-ttu-id="69b64-375">Relacji operacji marszrut</span><span class="sxs-lookup"><span data-stu-id="69b64-375">Route operation relations</span></span>](#route-operation-relations)

<span data-ttu-id="69b64-376">Jeśli moduł Supply Chain Management generuje zadania dla wydziału produkcyjnego, system pobierze odpowiednie przewodniki z tych źródeł.</span><span class="sxs-lookup"><span data-stu-id="69b64-376">When Supply Chain Management generates the jobs for the production floor, it will collect the relevant Guides from those sources.</span></span> <span data-ttu-id="69b64-377">Zwróć uwagę na następujące ważne reguły.</span><span class="sxs-lookup"><span data-stu-id="69b64-377">Take note of the following important rules.</span></span>

- <span data-ttu-id="69b64-378">W przypadku dołączania wersji BOM lub wersji formuły do marszruty lub zlecenia produkcyjnego wszystkie przewodniki dołączone do tej wersji, a także do nadrzędnego BOM lub formuły w tej wersji zostaną wyświetlone w zadaniu.</span><span class="sxs-lookup"><span data-stu-id="69b64-378">If you attach a BOM version or formula version to a route or production order, then any Guides attached to this version, and also the Guides attached to the parent BOM or formula of that version, will be shown on the job.</span></span>
- <span data-ttu-id="69b64-379">W przypadku dołączania wersji marszruty do zlecenia produkcyjnego wszystkie przewodniki dołączone do tej wersji, a także do nadrzędnej marszruty w tej wersji zostaną wyświetlone w zadaniu.</span><span class="sxs-lookup"><span data-stu-id="69b64-379">If you attach a route version to a production order, then any Guides attached to this version, and also the Guides attached to the parent route of that version, will be shown on the job.</span></span>
- <span data-ttu-id="69b64-380">W przypadku zdefiniowania kilku relacji operacji marszruty, które obejmują relację *Wszystkie* i przypisywania do nich przewodników w danym zadaniu będą wyświetlana tylko przewodniki z najbardziej szczegółowej relacji.</span><span class="sxs-lookup"><span data-stu-id="69b64-380">If you define several route operation relations that include the *All* relation and assign Guides to those, only the Guides from the most specific relation will be shown for the job.</span></span>  

<span data-ttu-id="69b64-381">![Diagram rozpoznawania odpowiednich przewodników](media/instruction-guides-Resolve.png "Diagram rozpoznawania odpowiednich przewodników")</span><span class="sxs-lookup"><span data-stu-id="69b64-381">![Diagram on resolving the relevant Guides](media/instruction-guides-Resolve.png "Diagram on resolving the relevant Guides")</span></span>
