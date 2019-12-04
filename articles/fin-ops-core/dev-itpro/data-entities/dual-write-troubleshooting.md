---
title: Przewodnik rozwiązywania problemów z integracją danych
description: Ten temat zawiera informacje dotyczące rozwiązywania problemów dotyczących integracji danych między Finance and Operations apps i Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 35c0a1e6342008bc2ee6ff25a1663e199c8cb985
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771032"
---
# <a name="troubleshooting-guide-for-data-integration"></a><span data-ttu-id="e4643-103">Przewodnik rozwiązywania problemów z integracją danych</span><span class="sxs-lookup"><span data-stu-id="e4643-103">Troubleshooting guide for data integration</span></span>

## <a name="enable-plug-in-trace-logs-in-common-data-service-and-inspect-the-dual-write-plug-in-error-details"></a><span data-ttu-id="e4643-104">Włączanie śledzenia wtyczek w Common Data Service i sprawdzanie szczegółów błędu wtyczki podwójnego zapisu</span><span class="sxs-lookup"><span data-stu-id="e4643-104">Enable plug-in trace logs in Common Data Service and inspect the dual-write plug-in error details</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e4643-105">Jeśli wystąpi problem lub błąd podczas synchronizacji z podwójnym zapisywaniem, należy wykonać następujące kroki w celu sprawdzenia błędów w dzienniku śledzenia.</span><span class="sxs-lookup"><span data-stu-id="e4643-105">If you experience an issue or error during dual-write synchronization, follow these steps to inspect the errors in the trace log.</span></span>

1. <span data-ttu-id="e4643-106">Aby można było sprawdzić błędy, należy włączyć dzienniki śledzenia wtyczek.</span><span class="sxs-lookup"><span data-stu-id="e4643-106">Before you can inspect the errors, you must enable plug-in trace logs.</span></span> <span data-ttu-id="e4643-107">Aby uzyskać instrukcje, zobacz sekcję „Wyświetlanie dzienników śledzenia” [Samouczek: Zapisz i zarejestruj wtyczkę](https://docs.microsoft.com/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs).</span><span class="sxs-lookup"><span data-stu-id="e4643-107">For instructions, see the "View trace logs" section of [Tutorial: Write and register a plug-in](https://docs.microsoft.com/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs).</span></span>

    <span data-ttu-id="e4643-108">Teraz możesz zbadać błędy.</span><span class="sxs-lookup"><span data-stu-id="e4643-108">You can now inspect the errors.</span></span>

2. <span data-ttu-id="e4643-109">Zaloguj się do Microsoft Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="e4643-109">Sign in to Microsoft Dynamics 365 Sales.</span></span>
3. <span data-ttu-id="e4643-110">Kliknij przycisk **Ustawienia** (symbol koła zębatego), a następnie kliknij przycisk **Ustawienia zaawansowane**.</span><span class="sxs-lookup"><span data-stu-id="e4643-110">Select the **Settings** button (the gear symbol), and then select **Advanced Settings**.</span></span>
4. <span data-ttu-id="e4643-111">W menu **Ustawienia** wybierz opcję **Dostosowywanie \> Dziennik śledzenia wtyczek**.</span><span class="sxs-lookup"><span data-stu-id="e4643-111">On the **Settings** menu, select **Customization \> Plug-In Trace Log**.</span></span>
5. <span data-ttu-id="e4643-112">Wybierz nazwę typu **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin**, aby wyświetlić szczegóły błędu.</span><span class="sxs-lookup"><span data-stu-id="e4643-112">Select **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin** as the type name to show the error details.</span></span>

## <a name="inspect-dual-write-synchronization-errors"></a><span data-ttu-id="e4643-113">Inspekcja błędów synchronizacji z podwójnym zapisywaniem</span><span class="sxs-lookup"><span data-stu-id="e4643-113">Inspect dual-write synchronization errors</span></span>

<span data-ttu-id="e4643-114">Aby sprawdzić błędy podczas testowania, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="e4643-114">Follow these steps to inspect errors during testing.</span></span>

1. <span data-ttu-id="e4643-115">Zaloguj się do Microsoft Dynamics LifeCycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="e4643-115">Sign in to Microsoft Dynamics Lifecycle Services (LCS).</span></span>
2. <span data-ttu-id="e4643-116">Otwórz projekt usługi LCS, aby przeprowadzić test podwójnego zapisywania.</span><span class="sxs-lookup"><span data-stu-id="e4643-116">Open the LCS project to do dual-write testing for.</span></span>
3. <span data-ttu-id="e4643-117">Wybierz **Środowiska hostowane w chmurze**.</span><span class="sxs-lookup"><span data-stu-id="e4643-117">Select **Cloud-hosted environments**.</span></span>
4. <span data-ttu-id="e4643-118">Utwórz połączenie pulpitu zdalnego z maszyną wirtualną (MW) aplikacji za pomocą konta lokalnego pokazywanego w usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="e4643-118">Make a Remote desktop connection to the application virtual machine (VM) by using local account that is shown in LCS.</span></span>
5. <span data-ttu-id="e4643-119">Otwórz podgląd zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="e4643-119">Open Event Viewer.</span></span> 
6. <span data-ttu-id="e4643-120">Przejdź do **Dzienniki aplikacji i usług \> Microsoft \> Dynamics \> AX-DualWriteSync \> Operacyjny**.</span><span class="sxs-lookup"><span data-stu-id="e4643-120">Go to **Applications and Services Logs \> Microsoft \> Dynamics \> AX-DualWriteSync \> Operational**.</span></span> <span data-ttu-id="e4643-121">Zostaną wyświetlone błędy i szczegóły.</span><span class="sxs-lookup"><span data-stu-id="e4643-121">The errors and details are shown.</span></span>

## <a name="unlink-one-common-data-service-environment-from-the-application-and-link-another-environment"></a><span data-ttu-id="e4643-122">Jak odłączyć i połączyć inne środowisko Common Data Service z aplikacji</span><span class="sxs-lookup"><span data-stu-id="e4643-122">Unlink one Common Data Service environment from the application and link another environment</span></span>

<span data-ttu-id="e4643-123">Aby zaktualizować łącza, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="e4643-123">Follow these steps to update links.</span></span>

1. <span data-ttu-id="e4643-124">Otwórz środowisko aplikacji.</span><span class="sxs-lookup"><span data-stu-id="e4643-124">Go to the application environment.</span></span>
2. <span data-ttu-id="e4643-125">Otwórz Zarządzanie danymi.</span><span class="sxs-lookup"><span data-stu-id="e4643-125">Open Data Management.</span></span>
3. <span data-ttu-id="e4643-126">Wybierz **Łącze do usługi CDS for Apps**.</span><span class="sxs-lookup"><span data-stu-id="e4643-126">Select **Link to CDS for apps**.</span></span>
4. <span data-ttu-id="e4643-127">Zaznacz wszystkie uruchomione mapowania, a następnie wybierz pozycję **Zatrzymaj**.</span><span class="sxs-lookup"><span data-stu-id="e4643-127">Select all the mappings that are running, and then select **Stop**.</span></span>
5. <span data-ttu-id="e4643-128">Zaznacz wszystkie mapowania i wybierz przycisk **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="e4643-128">Select all the mappings, and then select **Delete**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e4643-129">Opcja **Usuń** nie jest dostępna, jeśli szablon **CustomerV3-Account** jest wybrany.</span><span class="sxs-lookup"><span data-stu-id="e4643-129">The **Delete** option isn't available if the **CustomerV3-Account** template is selected.</span></span> <span data-ttu-id="e4643-130">Wyczyść wybór tego szablonu zgodnie z wymaganiami.</span><span class="sxs-lookup"><span data-stu-id="e4643-130">Clear the selection of this template as required.</span></span> <span data-ttu-id="e4643-131">**CustomerV3-Account** jest starszym obsługiwanym szablonem i współpracuje z rozwiązaniem Prospekt na gotówkę.</span><span class="sxs-lookup"><span data-stu-id="e4643-131">**CustomerV3-Account** is an older provisioned template and works with the Prospect to Cash solution.</span></span> <span data-ttu-id="e4643-132">Ponieważ jest on dostępny globalnie, pojawia się pod wszystkimi szablonami.</span><span class="sxs-lookup"><span data-stu-id="e4643-132">Because it's globally released, it appears under all templates.</span></span>

6. <span data-ttu-id="e4643-133">Wybierz **Odłącz środowisko**.</span><span class="sxs-lookup"><span data-stu-id="e4643-133">Select **Unlink environment**.</span></span>
7. <span data-ttu-id="e4643-134">Wybierz **tak**, aby potwierdzić operację.</span><span class="sxs-lookup"><span data-stu-id="e4643-134">Select **Yes** to confirm the operation.</span></span>
8. <span data-ttu-id="e4643-135">Aby połączyć nowe środowisko, wykonaj kroki opisane w [przewodniku instalacji](https://aka.ms/dualwrite-docs).</span><span class="sxs-lookup"><span data-stu-id="e4643-135">To link the new environment, follow the steps in the [installation guide](https://aka.ms/dualwrite-docs).</span></span>
