---
title: Wycofaj konfiguracje w repozytorium globalnym RCS
description: W tym temacie opisano sposób wycofania konfiguracji w repozytorium globalnym RCS.
author: JaneA07
ms.date: 02/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2021-02-02
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 2bd22e991de376cfd93f75158f1f29716d2559e1
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018740"
---
# <a name="discontinue-configurations-in-the-rcs-global-repository"></a><span data-ttu-id="e2149-103">Wycofaj konfiguracje w repozytorium globalnym RCS</span><span class="sxs-lookup"><span data-stu-id="e2149-103">Discontinue configurations in the RCS Global repository</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e2149-104">W tym temacie opisano sposób wycofania konfiguracji w repozytorium globalnym RCS.</span><span class="sxs-lookup"><span data-stu-id="e2149-104">This topic describes how to discontinue configuration in the RCS Global repository.</span></span> <span data-ttu-id="e2149-105">Wcześniej można było usuwać tylko konfiguracje, które nie były już wymagane.</span><span class="sxs-lookup"><span data-stu-id="e2149-105">Previously, it was possible only to delete configurations that were no longer required.</span></span> <span data-ttu-id="e2149-106">Teraz jednak można oznaczyć zwolniną konfigurację jako **Wycofaną** w repozytorium globalnym RCS.</span><span class="sxs-lookup"><span data-stu-id="e2149-106">However now you can mark a released configuration as **Discontinued** in the RCS Global repository.</span></span> <span data-ttu-id="e2149-107">Dzięki tej funkcji możesz również wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="e2149-107">With this functionality, you can also do the following:</span></span> 
 
 - <span data-ttu-id="e2149-108">Jeśli konfiguracja ma zostać przerwana, należy otrzymywać powiadomienia z góry.</span><span class="sxs-lookup"><span data-stu-id="e2149-108">Provide up front notifications when a configuration is planned to be discontinued.</span></span>
 - <span data-ttu-id="e2149-109">Uwzględnij odpowiednie szczegóły dotyczące konfiguracji wymiany.</span><span class="sxs-lookup"><span data-stu-id="e2149-109">Include applicable details about the replacement configuration.</span></span>
 - <span data-ttu-id="e2149-110">Ustaw obsługiwaną **Datę zakończenia** określonej konfiguracji, aby poinformować użytkownika o jej wycofaniu.</span><span class="sxs-lookup"><span data-stu-id="e2149-110">Set a **Supported until** date for the specific configuration to inform the user when it will be discontinued.</span></span>

<span data-ttu-id="e2149-111">Po wycofaniu wersji konfiguracji można określić następujące informacje opcjonalne:</span><span class="sxs-lookup"><span data-stu-id="e2149-111">When you discontinue a configuration version, you can specify the following optional information:</span></span>

  - <span data-ttu-id="e2149-112">**Konfiguracja zastępcza**</span><span class="sxs-lookup"><span data-stu-id="e2149-112">**Replacement configuration**</span></span>
  - <span data-ttu-id="e2149-113">**Zastępcza wersja konfiguracji**</span><span class="sxs-lookup"><span data-stu-id="e2149-113">**Replacement configuration version**</span></span>
  - <span data-ttu-id="e2149-114">**Dowolna uwaga tekstowa**: to pole pozwala na dostęp do łączy dokumentacji lub odwołań</span><span class="sxs-lookup"><span data-stu-id="e2149-114">**Free text note**: Use this field to provide documentation links or references</span></span>
  - <span data-ttu-id="e2149-115">**Obsługiwane do**: W tym polu jest proponowana data, do której będzie obsługiwana bieżąca konfiguracja/wersja.</span><span class="sxs-lookup"><span data-stu-id="e2149-115">**Supported until**: This field provides the proposed date up to which the current configuration/version will be supported.</span></span> <span data-ttu-id="e2149-116">Należy ją zaktualizować ręcznie.</span><span class="sxs-lookup"><span data-stu-id="e2149-116">This date must be updated manually.</span></span>
  
<span data-ttu-id="e2149-117">Aby przerwać konfigurację, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="e2149-117">To discontinue the configuration, complete the following steps.</span></span> 

1. <span data-ttu-id="e2149-118">Określ, czy chcesz przerwać pojedynczą, czy wszystkie wersje o tych samych ustawieniach w jednej operacji, ustawiając opcję **Wszystkie wersje** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="e2149-118">Select whether you want to discontinue a single version or all versions with the same settings in one operation by setting **All versions** to **Yes**.</span></span> 
2. <span data-ttu-id="e2149-119">Ustaw dla parametru **Wycofaj** wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="e2149-119">Set the **Discontinue** parameter to **Yes**.</span></span>
3. <span data-ttu-id="e2149-120">Wybierz **OK**, aby przerwać konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="e2149-120">Select **OK** to discontinue the configurations.</span></span> <span data-ttu-id="e2149-121">Podczas zapisywania zmian zostanie wypełnione pole **Data wycofania**.</span><span class="sxs-lookup"><span data-stu-id="e2149-121">The **Discontinued date** field will be populated when you save the changes.</span></span>

![Wycofaj informacje o konfiguracji](media/Discontinue-details-2.png)
  
<span data-ttu-id="e2149-123">W dowolnym momencie można przywrócić konfigurację na **Udostępniono** lub skorygować informacje o wycofaniu.</span><span class="sxs-lookup"><span data-stu-id="e2149-123">You can revert configuration back to **Shared** or adjust discontinuation information at any time.</span></span> <span data-ttu-id="e2149-124">Po udostępnieniu konfiguracji należy określić **Obsługiwane do** do oraz wszystkie inne informacje dotyczące wycofania, aby wskazać plany przyszłego wycofania.</span><span class="sxs-lookup"><span data-stu-id="e2149-124">If you share a configuration, specify the **Supported until** date and all other information related to the discontinuation to indicate your plans for future discontinuation.</span></span>

<span data-ttu-id="e2149-125">Aby udostępnić informacje dotyczące planowanego przerwania przed zakończeniem konfigurowania, użytkownik może wstępnie wypełnić wszystkie pola związane z wymianą, ale pozostawić parametr **Wycofaj** ustawiony na wartość **Nie**.</span><span class="sxs-lookup"><span data-stu-id="e2149-125">If you want to share information about a planned discontinuation, prior to actually discontinuing the configuration, user is able to prefill all fields related to replacement but leave the **Discontinue** parameter set to **No**.</span></span>

> [!NOTE]
> <span data-ttu-id="e2149-126">Przerwanie nie ogranicza operacji z konfiguracjami.</span><span class="sxs-lookup"><span data-stu-id="e2149-126">Discontinuation doesn't limit operations with configurations.</span></span> <span data-ttu-id="e2149-127">Istnieje możliwość kontynuowania importowania, uruchamiania lub wyprowadzenia konfiguracji. Te pola zawierają informacje.</span><span class="sxs-lookup"><span data-stu-id="e2149-127">You can continue to import, run, or derive the configurations, these fields are informational.</span></span>

## <a name="finance-supports-displaying-this-information-starting-in-version-10014"></a><span data-ttu-id="e2149-128">Funkcje finansowe obsługują wyświetlanie tych informacji w wersji 10.0.14</span><span class="sxs-lookup"><span data-stu-id="e2149-128">Finance supports displaying this information starting in version 10.0.14</span></span>

<span data-ttu-id="e2149-129">Począwszy od wersji 10.0.14, Dynamics 365 Finance obsługuje wyświetlanie informacji o wycofaniu.</span><span class="sxs-lookup"><span data-stu-id="e2149-129">Starting in version 10.0.14, Dynamics 365 Finance supports displaying discontinuation information.</span></span> <span data-ttu-id="e2149-130">Na stronie **Repozytorium globalnym** można wyświetlać aktualne informacje związane z przerwaniem.</span><span class="sxs-lookup"><span data-stu-id="e2149-130">On the **Global repository** page, you can view up to date information related to discontinuation.</span></span> <span data-ttu-id="e2149-131">Domyślnie konfiguracje wycofane są odfiltrowywowane.</span><span class="sxs-lookup"><span data-stu-id="e2149-131">By default, configurations that are discontinued are filtered out.</span></span>
  
<span data-ttu-id="e2149-132">Strona **Konfiguracje zaimportowane** (ERSolutionTable) zawiera konfiguracje, które zostały już wycofane podczas importowania.</span><span class="sxs-lookup"><span data-stu-id="e2149-132">The **Imported configurations** (ERSolutionTable) page, shows configurations that were already discontinued when there were imported.</span></span> <span data-ttu-id="e2149-133">W przypadku konfiguracji, które zostały wycofane po imporcie, informacje o wycofaniu można zsynchronizować, uruchamiając zadanie **Importuj aktualizacje konfiguracji**.</span><span class="sxs-lookup"><span data-stu-id="e2149-133">For those configurations that were discontinued after import, the discontinuation information can be synchronized by running the **Import configurations updates** job.</span></span>


