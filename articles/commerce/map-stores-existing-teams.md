---
title: Mapowanie sklepów i zespołów w przypadku, gdy istnieją już inne zespoły w usłudze Microsoft Teams
description: W tym temacie opisano, jak mapować sklepy i odpowiadające im zespoły w centrali Dynamics 365 Commerce, jeśli Twoja organizacja już utworzyła zespoły w Microsoft Teams przed integracją Commerce.
author: gvrmohanreddy
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: ccc2cbf11e405facf310d93e5458cfe12a43146d
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020226"
---
# <a name="map-stores-and-teams-if-there-are-pre-existing-teams-in-microsoft-teams"></a><span data-ttu-id="ce3f1-103">Mapowanie sklepów i zespołów w przypadku, gdy istnieją już inne zespoły w usłudze Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ce3f1-103">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ce3f1-104">W tym temacie opisano, jak mapować sklepy i odpowiadające im zespoły w centrali Dynamics 365 Commerce, jeśli Twoja organizacja już utworzyła zespoły w Microsoft Teams przed integracją Commerce.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-104">This topic covers how to map stores and corresponding teams in Dynamics 365 Commerce headquarters if your organization has already created teams in Microsoft Teams before Commerce integration.</span></span>

<span data-ttu-id="ce3f1-105">Twoja organizacja może mieć zespoły utworzone dla niektórych lub wszystkich sklepów przed integracją Dynamics 365 Commerce i Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-105">Your organization may have teams created for some or all of your stores before integrating Dynamics 365 Commerce and Microsoft Teams.</span></span> <span data-ttu-id="ce3f1-106">W takim przypadku, aby ustanowić synchronizację zadań między Commerce POS i Microsoft Teams, musisz zapewnić mapowanie sklepów i odpowiedniego zespołu w siedzibie Commerce.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-106">If this is the case, to establish task synchronization between Commerce POS and Microsoft Teams you must provide the mapping of stores and corresponding team in Commerce headquarters.</span></span>

## <a name="map-stores-and-corresponding-teams-in-commerce-headquarters"></a><span data-ttu-id="ce3f1-107">Mapowanie sklepów i odpowiadających im zespołów w centrali usługi Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="ce3f1-107">Map stores and corresponding teams in Commerce headquarters</span></span> 

<span data-ttu-id="ce3f1-108">Aby zmapować sklepy i odpowiadające im zespoły w centrali Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-108">To map stores and corresponding teams in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="ce3f1-109">Wybierz kolejno opcje **Administrowanie systemem \> Obszar roboczy \> Zarządzanie danymi**.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-109">Go to **System Administration \> Workspace \> Data management**.</span></span>
1. <span data-ttu-id="ce3f1-110">Wybierz opcję **Eksportuj**.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-110">Select **Export**.</span></span> 
1. <span data-ttu-id="ce3f1-111">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-111">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="ce3f1-112">W obszarze **Nazwa grupy** wprowadź nazwę „Mapowanie zespołów eksportu”.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-112">Under **Group name**, enter "Export Teams mapping".</span></span>
1. <span data-ttu-id="ce3f1-113">Na skróconej karcie **Wybrane jednostki** wybierz pozycję **Dodaj jednostkę**.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-113">On the **Selected entities** FastTab, select **Add entity**.</span></span> <span data-ttu-id="ce3f1-114">Zostanie wyświetlone okno dialogowe **Dodaj jednostkę**.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-114">The **Add entity** dialog box appears.</span></span>  
1. <span data-ttu-id="ce3f1-115">Na liście rozwijanej **Nazwa jednostki** wybierz opcję **Mapowanie zespołów między źródłem i zespołem**.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-115">In the **Entity name** drop-down list, select **Teams mapping between source and team**.</span></span>
1. <span data-ttu-id="ce3f1-116">Z listy rozwijanej **Format danych docelowych** wybierz format **CSV**.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-116">In the **Target data format** drop-down list, select **CSV**.</span></span>
1. <span data-ttu-id="ce3f1-117">Wybierz opcję **Dodaj**, a następnie opcję **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-117">Select **Add**, and then select **Close**.</span></span>
1. <span data-ttu-id="ce3f1-118">W lewym górnym rogu okienka akcji wybierz pozycję **Eksportuj teraz**.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-118">On the top left under the Action Pane, select **Export now**.</span></span>
1. <span data-ttu-id="ce3f1-119">W obszarze **Stan przetwarzania jednostki** wybierz pozycję **Pobierz plik**.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-119">Under **Entity processing status**, select **Download file**.</span></span>
1. <span data-ttu-id="ce3f1-120">W eksportowanych plikach CSV wprowadź wartości parametrów **SOURCETYPE**, **SOURCEID** i **TEAMID** następująco:</span><span class="sxs-lookup"><span data-stu-id="ce3f1-120">In the exported CSV file, enter values for **SOURCETYPE**, **SOURCEID**, and **TEAMID** as follows:</span></span>
    - <span data-ttu-id="ce3f1-121">W przypadku typu **SOURCETYPE** wprowadź nazwę „RetailStore”.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-121">For **SOURCETYPE**, enter "RetailStore".</span></span> 
    - <span data-ttu-id="ce3f1-122">W przypadku kodu **SOURCEID** wprowadź numer sklepu (na przykład „000135” dla sklepu San Francisco).</span><span class="sxs-lookup"><span data-stu-id="ce3f1-122">For **SOURCEID**, enter the store number (for example, "000135" for the San Francisco store).</span></span> <span data-ttu-id="ce3f1-123">Numery sklepów można znaleźć w **Retail i Commerce \> Kanały \> Sklepy**.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-123">You can find store numbers at **Retail and Commerce \> Channels \> Stores**.</span></span>
    - <span data-ttu-id="ce3f1-124">Dla identyfikatora **TEAMID** wprowadź odpowiedni identyfikator zespołu Microsoft Teams (na przykład „5f8bc92b-6aa8-451e-85d1-3949c01ddc6c”).</span><span class="sxs-lookup"><span data-stu-id="ce3f1-124">For **TEAMID**, enter the corresponding team ID from Microsoft Teams (for example, "5f8bc92b-6aa8-451e-85d1-3949c01ddc6c").</span></span> <span data-ttu-id="ce3f1-125">Informacje o identyfikatorze zespołu można znaleźć [admin.teams.microsoft.com](https://admin.teams.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="ce3f1-125">You can find team ID information at [admin.teams.microsoft.com](https://admin.teams.microsoft.com).</span></span>
1. <span data-ttu-id="ce3f1-126">Zapisz plik CSV na komputerze lokalnym.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-126">Save the CSV file to your local machine.</span></span>
1. <span data-ttu-id="ce3f1-127">Wybierz kolejno opcje **Administrowanie systemem \> Obszar roboczy \> Zarządzanie danymi**, a następnie wybrać **Importuj**.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-127">Go to **System Administration \> Workspace \> Data management**, and then select **Import**.</span></span>
1. <span data-ttu-id="ce3f1-128">Na skróconej karcie **Wybrane jednostki** wybierz pozycję **Dodaj plik**.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-128">On the **Selected entities** FastTab, select **Add file**.</span></span> <span data-ttu-id="ce3f1-129">Zostanie wyświetlone okno dialogowe **Dodaj plik**.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-129">The **Add file** dialog box appears.</span></span>
1. <span data-ttu-id="ce3f1-130">Na liście rozwijanej **Nazwa jednostki** wybierz opcję **Mapowanie zespołów między źródłem i zespołem**.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-130">In the **Entity name** drop-down list, select **Teams mapping between source and team**.</span></span>
1. <span data-ttu-id="ce3f1-131">Z listy rozwijanej **Format danych źródłowych** wybierz format **CSV**.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-131">In the **Source data format** drop-down list, select **CSV**.</span></span>
1. <span data-ttu-id="ce3f1-132">Wybierz opcję **Przekaż i dodaj**, wybierz uprzednio zapisany plik CSV, a następnie wybierz opcję **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-132">Select **Upload and add**, select the CSV file that you saved previously, and then select **Open**.</span></span>
1. <span data-ttu-id="ce3f1-133">W oknie dialogowym **Dodaj plik** wybierz **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-133">In the **Add file** dialog box, select **Close**.</span></span>
1. <span data-ttu-id="ce3f1-134">W okienku akcji wybierz opcję **Zapisz**, a następnie wybierz opcję **Importuj**.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-134">On the Action Pane, select **Save** , and then select **Import**.</span></span>

<span data-ttu-id="ce3f1-135">Poniższy przykładowy obraz przedstawia grupę **Mapowanie zespołów eksportu** w aplikacji Commerce z wyróżnionymi elementami **Dodaj jednostkę** i nagłówkami wyeksportowanych plików CSV.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-135">The following example image shows the **Export teams mapping** group in Commerce with **Add entity** elements and the exported CSV file headers highlighted.</span></span>

![Eksportuj zespoły mapujące grupę w Commerce z dodanymi elementami encji i wyróżnionymi nagłówkami wyeksportowanych plików CSV](media/d365-commerce-data-mgmt-export-entity.png)

> [!NOTE]
> <span data-ttu-id="ce3f1-137">Aby zsynchronizować zarządzanie zadaniami, po ukończeniu tych działań wykonaj kroki opisane w teksie [Synchronizuj zarządzanie zadaniami między Microsoft Teams i POS](synchronize-tasks-teams-pos.md).</span><span class="sxs-lookup"><span data-stu-id="ce3f1-137">After you complete the preceeding steps, follow the steps in [Synchronize task management between Microsoft Teams and POS](synchronize-tasks-teams-pos.md) to synchronize task management.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="ce3f1-138">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="ce3f1-138">Additional resources</span></span>

[<span data-ttu-id="ce3f1-139">Omówienie integracji Dynamics 365 Commerce i Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ce3f1-139">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>](commerce-teams-integration.md)

[<span data-ttu-id="ce3f1-140">Włączanie integracji Dynamics 365 Commerce i Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ce3f1-140">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>](enable-teams-integration.md)

[<span data-ttu-id="ce3f1-141">Obsługa Microsoft Teams z Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="ce3f1-141">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>](provision-teams-from-commerce.md)

[<span data-ttu-id="ce3f1-142">Synchronizowanie zarządzania zadaniami między punktami sprzedaży usług Microsoft Teams i Dynamics 365 Commerce POS</span><span class="sxs-lookup"><span data-stu-id="ce3f1-142">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>](synchronize-tasks-teams-pos.md)

[<span data-ttu-id="ce3f1-143">Zarządzanie rolami użytkowników w usłudze Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ce3f1-143">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="ce3f1-144">Integracja z usługami Dynamics 365 Commerce i Microsoft Teams - FAQ</span><span class="sxs-lookup"><span data-stu-id="ce3f1-144">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>](teams-integration-faq.md)
