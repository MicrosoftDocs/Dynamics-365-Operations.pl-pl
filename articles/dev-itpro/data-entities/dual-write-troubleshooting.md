---
title: Przewodnik rozwiązywania problemów z integracją danych
description: Ten temat zawiera informacje dotyczące rozwiązywania problemów dotyczących integracji między Microsoft Dynamics 365 for Finance and Operations i Common Data Service.
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
ms.openlocfilehash: ca62a6b3aa64ec2383ee3ded3b7bbf4650a41166
ms.sourcegitcommit: efcc0dee8bde5f8f93f6291e7f059ad426843e57
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/31/2019
ms.locfileid: "1797282"
---
# <a name="troubleshooting-guide-for-data-integration"></a><span data-ttu-id="76a0f-103">Przewodnik rozwiązywania problemów z integracją danych</span><span class="sxs-lookup"><span data-stu-id="76a0f-103">Troubleshooting guide for data integration</span></span>

## <a name="enable-plugin-trace-in-common-data-service-and-check-the-dual-write-plugin-error-details"></a><span data-ttu-id="76a0f-104">Włączanie śledzenia wtyczki w Common Data Service i sprawdzanie szczegółów błędu wtyczki podwójnego zapisu</span><span class="sxs-lookup"><span data-stu-id="76a0f-104">Enable Plugin Trace in Common Data Service and check the dual-write Plugin error details</span></span>

<span data-ttu-id="76a0f-105">Jeśli występu problem lub błąd z synchronizacją podwójnego zapisu, można sprawdzić błędy w dzienniku śledzenia:</span><span class="sxs-lookup"><span data-stu-id="76a0f-105">If you are facing an issue or error with dual-write synchronization, you can inspect the errors in the trace log:</span></span>

1. <span data-ttu-id="76a0f-106">Zanim możliwe będzie sprawdzenie błędów, należy włączyć śledzenie wtyczek, korzystając z instrukcji w temacie pomocy [Rejestrowanie wtyczki](https://docs.microsoft.com/en-us/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs), aby włączyć śledzenie wtyczek.</span><span class="sxs-lookup"><span data-stu-id="76a0f-106">Before you can inspect the errors, you must enable Plugin trace using the instructions in [Register plug-in](https://docs.microsoft.com/en-us/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs) to enable Plugin trace.</span></span> <span data-ttu-id="76a0f-107">Teraz możesz sprawdzić błędy.</span><span class="sxs-lookup"><span data-stu-id="76a0f-107">Now you can inspect the errors.</span></span>
2. <span data-ttu-id="76a0f-108">Zaloguj się do usługi Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="76a0f-108">Login to Dynamics 365 for Sales.</span></span>
3. <span data-ttu-id="76a0f-109">Kliknij ikonę Ustawienia (koło zębate) i wybierz opcję **Ustawienia zaawansowane**.</span><span class="sxs-lookup"><span data-stu-id="76a0f-109">Click on the Settings icon (a gear), and select **Advanced Settings**.</span></span>
4. <span data-ttu-id="76a0f-110">W menu **Ustawienia** wybierz opcję **Dostosowywanie > Dziennik śledzenia wtyczek**.</span><span class="sxs-lookup"><span data-stu-id="76a0f-110">In the **Settings** menu, choose **Customization > Plug-In Trace Log**.</span></span>
5. <span data-ttu-id="76a0f-111">Kliknij nazwę typu **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin**, aby wyświetlić szczegóły błędu.</span><span class="sxs-lookup"><span data-stu-id="76a0f-111">Click the type name **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin** to display the error details.</span></span>

## <a name="check-dual-write-synchronization-errors-in-finance-and-operations"></a><span data-ttu-id="76a0f-112">Sprawdzanie błędów synchronizacji podwójnego zapisu w programie Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="76a0f-112">Check dual-write synchronization errors in Finance and Operations</span></span>

<span data-ttu-id="76a0f-113">Można sprawdzić błędy podczas testowania, wykonując następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="76a0f-113">You can check the errors during testing by following these steps:</span></span>

+ <span data-ttu-id="76a0f-114">Zaloguj się do LifeCycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="76a0f-114">Login to LifeCycle Services (LCS).</span></span>
+ <span data-ttu-id="76a0f-115">Otwórz projekt LCS, który wybrano do sprawdzenia podwójnego zapisu.</span><span class="sxs-lookup"><span data-stu-id="76a0f-115">Open the LCS project that you chose to perform dual-write testing.</span></span>
+ <span data-ttu-id="76a0f-116">Otwórz Środowiska hostowane w chmurze.</span><span class="sxs-lookup"><span data-stu-id="76a0f-116">Go to Cloud Hosted Environments.</span></span>
+ <span data-ttu-id="76a0f-117">Użyj pulpitu zdalnego, aby skorzystać z Finance and Operations VM przy użyciu lokalnego konta wyświetlanego w LCS.</span><span class="sxs-lookup"><span data-stu-id="76a0f-117">Remote desktop to Finance and Operations VM using local account that is displayed in LCS.</span></span>
+ <span data-ttu-id="76a0f-118">Otwórz przeglądarkę zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="76a0f-118">Open the event viewer.</span></span> 
+ <span data-ttu-id="76a0f-119">Przejdź do **Dzienniki aplikacji i usług > Microsoft > Dynamics > AX-DualWriteSync > Operacyjny**.</span><span class="sxs-lookup"><span data-stu-id="76a0f-119">Navigate to **Applications and Services logs > Microsoft > Dynamics > AX-DualWriteSync > Operational**.</span></span> <span data-ttu-id="76a0f-120">Zostaną wyświetlone błędy i szczegóły.</span><span class="sxs-lookup"><span data-stu-id="76a0f-120">The errors and details are displayed.</span></span>

## <a name="how-to-unlink-and-link-another-common-data-service-environment-from-finance-and-operations"></a><span data-ttu-id="76a0f-121">Jak odłączyć i połączyć inne środowisko Common Data Service z programu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="76a0f-121">How to unlink and link another Common Data Service environment from Finance and Operations</span></span>

<span data-ttu-id="76a0f-122">Można aktualizować łącza, wykonując następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="76a0f-122">You can update links by following these steps:</span></span>

+ <span data-ttu-id="76a0f-123">Przejdź do środowiska Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="76a0f-123">Navigate to the Finance and Operations environment.</span></span>
+ <span data-ttu-id="76a0f-124">Otwórz Zarządzanie danymi.</span><span class="sxs-lookup"><span data-stu-id="76a0f-124">Open Data Management.</span></span>
+ <span data-ttu-id="76a0f-125">Kliknij **Łącze do usługi CDS for Apps**.</span><span class="sxs-lookup"><span data-stu-id="76a0f-125">Click on **Link to CDS for apps**.</span></span>
+ <span data-ttu-id="76a0f-126">Zaznacz wszystkie uruchomione mapowania i kliknij przycisk **Zatrzymaj**.</span><span class="sxs-lookup"><span data-stu-id="76a0f-126">Select all the running mappings and click **Stop**.</span></span> 
+ <span data-ttu-id="76a0f-127">Zaznacz wszystkie mapowania i kliknij przycisk **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="76a0f-127">Select all the mappings and click **Delete**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="76a0f-128">Opcja **Usuń** nie pojawi się, jeśli szablon **CustomerV3-Account** jest wybrany.</span><span class="sxs-lookup"><span data-stu-id="76a0f-128">The **Delete** option will not appear if **CustomerV3-Account** template is selected.</span></span> <span data-ttu-id="76a0f-129">W razie potrzeby usuń zaznaczenie.</span><span class="sxs-lookup"><span data-stu-id="76a0f-129">Unselect it if needed.</span></span> <span data-ttu-id="76a0f-130">**CustomerV3-Account** jest starszym obsługiwanym szablonem i współpracuje z rozwiązaniem Prospekt na gotówkę.</span><span class="sxs-lookup"><span data-stu-id="76a0f-130">**CustomerV3-Account** is an older provisioned template and works with the Prospect to Cash solution.</span></span> <span data-ttu-id="76a0f-131">Ponieważ jest on dostępny globalnie, pojawia się pod wszystkimi szablonami.</span><span class="sxs-lookup"><span data-stu-id="76a0f-131">Because it is globally released, it shows up under all templates.</span></span>

+ <span data-ttu-id="76a0f-132">Kliknij **Odłącz środowisko**.</span><span class="sxs-lookup"><span data-stu-id="76a0f-132">Click **Unlink environment**.</span></span>
+ <span data-ttu-id="76a0f-133">Kliknij **Tak**, aby potwierdzić.</span><span class="sxs-lookup"><span data-stu-id="76a0f-133">Click **Yes** for confirmation.</span></span>
+ <span data-ttu-id="76a0f-134">Aby połączyć nowe środowisko, wykonaj kroki opisane w [przewodniku instalacji](https://aka.ms/dualwrite-docs).</span><span class="sxs-lookup"><span data-stu-id="76a0f-134">To link the new environment, follow the steps in the [installation guide](https://aka.ms/dualwrite-docs).</span></span>

