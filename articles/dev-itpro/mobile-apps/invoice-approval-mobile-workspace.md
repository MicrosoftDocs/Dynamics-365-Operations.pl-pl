---
title: Mobilny obszar roboczy Zatwierdzenia faktur
description: Ten temat zawiera informacje o komórkowym obszarze roboczym Zatwierdzenia faktur. Ten obszar roboczy wyświetla listę faktur, które zostały Ci przypisane przez proces przepływu pracy nagłówków faktur od dostawców.
author: abruer
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: ff726670e0fd7566a74e6def73555a7c53b86f97
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "327005"
---
# <a name="invoice-approvals-mobile-workspace"></a><span data-ttu-id="d0a8e-104">Mobilny obszar roboczy Zatwierdzenia faktur</span><span class="sxs-lookup"><span data-stu-id="d0a8e-104">Invoice approvals mobile workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d0a8e-105">Ten temat zawiera informacje o komórkowym obszarze roboczym **Zatwierdzenia faktur**.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-105">This topic provides information about the **Invoice approvals** mobile workspace.</span></span> <span data-ttu-id="d0a8e-106">Ten obszar roboczy wyświetla listę faktur, które zostały Ci przypisane przez proces przepływu pracy nagłówków faktur od dostawców.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-106">This workspace provides a list of invoices that have been assigned to you through the vendor invoice header workflow process.</span></span> 

<span data-ttu-id="d0a8e-107">Ten mobilny obszar roboczy jest przeznaczony do używania w aplikacji komórkowej Microsoft Dynamics 365 for Unified Operations Mobile.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-107">This mobile workspace is intended to be used with the Microsoft Dynamics 365 for Unified Operations mobile app.</span></span>

## <a name="overview"></a><span data-ttu-id="d0a8e-108">Przegląd</span><span class="sxs-lookup"><span data-stu-id="d0a8e-108">Overview</span></span>

<span data-ttu-id="d0a8e-109">Komórkowy obszar roboczy **Zatwierdzenia faktur** pozwala pracownikom i kierownikom ds. rozrachunków z dostawcami wyświetlać faktury, które zostały im przypisane w procesie przepływu pracy nagłówków faktur od dostawców.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-109">The **Invoice approvals** mobile workspace lets Accounts payable clerks and managers view invoices that have been assigned to them as part of the vendor invoice header workflow process.</span></span> <span data-ttu-id="d0a8e-110">Można wyświetlić informacje o fakturze, a nawet szczegóły wiersza i dystrybucji, aby podejmować najbardziej trafne decyzje o zatwierdzeniu.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-110">You can view the invoice information, and even the line and distribution details, to help you make informed approval decisions.</span></span> <span data-ttu-id="d0a8e-111">W obszarze roboczym można podjąć odpowiednie działania, aby przeprowadzić fakturę przez kolejne etapy przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-111">From the workspace, you can take action to move the invoice through the workflow process.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="d0a8e-112">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="d0a8e-112">Prerequisites</span></span>

<span data-ttu-id="d0a8e-113">Aby można było używać tego mobilnego obszaru roboczego, muszą być spełnione następujące wymagania wstępne.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-113">Before you can use this mobile workspace, the following prerequisites must be met.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="d0a8e-114">Wymaganie wstępne</span><span class="sxs-lookup"><span data-stu-id="d0a8e-114">Prerequisite</span></span></th>
<th><span data-ttu-id="d0a8e-115">Rola</span><span class="sxs-lookup"><span data-stu-id="d0a8e-115">Role</span></span></th>
<th><span data-ttu-id="d0a8e-116">opis</span><span class="sxs-lookup"><span data-stu-id="d0a8e-116">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="d0a8e-117">W organizacji musi być wdrożone rozwiązanie Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-117">Microsoft Dynamics 365 for Finance and Operations must be deployed in your organization.</span></span></td>
<td><span data-ttu-id="d0a8e-118">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="d0a8e-118">System administrator</span></span></td>
<td><span data-ttu-id="d0a8e-119">Zobacz <a href="../deployment/deploy-demo-environment.md">Wdrażanie środowiska demonstracyjnego</a>.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-119">See <a href="../deployment/deploy-demo-environment.md">Deploy a demo environment</a>.</span></span>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="d0a8e-120">Mobilny obszar roboczy <strong>Zatwierdzenia faktur</strong> musi być opublikowany.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-120">The <strong>Invoice approvals</strong> mobile workspace must be published.</span></span></td>
<td><span data-ttu-id="d0a8e-121">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="d0a8e-121">System administrator</span></span></td>
<td><span data-ttu-id="d0a8e-122">Zobacz <a href="publish-mobile-workspace.md">Publikowanie mobilnego obszaru roboczego</a>.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-122">See <a href="publish-mobile-workspace.md">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="d0a8e-123">Pobieranie i instalowanie aplikacji mobilnej</span><span class="sxs-lookup"><span data-stu-id="d0a8e-123">Download and install the mobile app</span></span>

<span data-ttu-id="d0a8e-124">Pobierz i zainstaluj aplikację komórkową Dynamics 365 for Unified Operations:</span><span class="sxs-lookup"><span data-stu-id="d0a8e-124">Download and install the Dynamics 365 for Unified Operations mobile app:</span></span>

-   [<span data-ttu-id="d0a8e-125">Telefony Android</span><span class="sxs-lookup"><span data-stu-id="d0a8e-125">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
-   [<span data-ttu-id="d0a8e-126">Telefony iPhone</span><span class="sxs-lookup"><span data-stu-id="d0a8e-126">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="d0a8e-127">Logowanie do aplikacji mobilnej</span><span class="sxs-lookup"><span data-stu-id="d0a8e-127">Sign in to the mobile app</span></span>

1.  <span data-ttu-id="d0a8e-128">Uruchom aplikację na urządzeniu komórkowym.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-128">Start the app on your mobile device.</span></span>
2.  <span data-ttu-id="d0a8e-129">Wprowadź swój adres URL w usłudze Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-129">Enter your Microsoft Dynamics 365 URL.</span></span>
3.  <span data-ttu-id="d0a8e-130">Podczas pierwszego logowania pojawi się monit o podanie nazwy użytkownika i hasła.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-130">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="d0a8e-131">Wprowadź swoje poświadczenia.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-131">Enter your credentials.</span></span>
4.  <span data-ttu-id="d0a8e-132">Po zalogowaniu się zobaczysz obszary robocze dostępne dla firmy.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-132">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="d0a8e-133">Należy zauważyć, że jeśli administrator systemu później opublikuje nowy obszar roboczy, trzeba odświeżyć listę komórkowych obszarów roboczych.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-133">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

    <span data-ttu-id="d0a8e-134">[![Ściąganie w celu odświeżenia](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span><span class="sxs-lookup"><span data-stu-id="d0a8e-134">[![Pull to refresh](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span></span>

## <a name="approve-invoices-by-using-the-invoice-approvals-mobile-workspace"></a><span data-ttu-id="d0a8e-135">Zatwierdzanie faktur w mobilnym obszarze roboczym Zatwierdzenia faktur</span><span class="sxs-lookup"><span data-stu-id="d0a8e-135">Approve invoices by using the Invoice approvals mobile workspace</span></span>
1.  <span data-ttu-id="d0a8e-136">Na urządzeniu przenośnym wybierz obszar roboczy **Zatwierdzenia faktur**.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-136">On your mobile device, select the **Invoice approvals** workspace.</span></span>
2.  <span data-ttu-id="d0a8e-137">Zaznacz fakturę, która została Ci przypisana w procesie przepływu pracy nagłówków faktur od dostawców.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-137">Select the invoice that has been assigned to you by the vendor invoice header workflow process.</span></span>
3.  <span data-ttu-id="d0a8e-138">Na stronie **Szczegóły faktury** przejrzyj informacje z nagłówka faktury, w tym o dostawcy i dacie.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-138">On the **Invoice details** page, review the invoice header information, such as the vendor and date information.</span></span>
4.  <span data-ttu-id="d0a8e-139">Zaznacz wiersz faktury, a zostaną wyświetlone jego bardziej szczegółowe informacje w widoku **Szczegóły wierszy faktury**.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-139">Select a line on the invoice to view more detailed information about it in the **Invoice line details** view.</span></span>
5.  <span data-ttu-id="d0a8e-140">W widoku **Szczegóły wierszy faktury** wybierz opcję **Rozdzielenia**, aby wyświetlić rozdziały wierszy.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-140">In the **Invoice line details** view, select **Distributions** to show the line distributions.</span></span> <span data-ttu-id="d0a8e-141">Tutaj można obejrzeć rozksięgowanie wiersza faktury.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-141">Here, you can view the accounting for the invoice line.</span></span> <span data-ttu-id="d0a8e-142">Wyświetlane informacje obejmują wymiary finansowe i konto główne.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-142">The information that is shown includes the financial dimensions and the main account.</span></span>
6.  <span data-ttu-id="d0a8e-143">Na stronie **Szczegóły faktury** wybierz opcję **Rozdzielenia**, a zostaną wyświetlone wszystkie dystrybucje.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-143">On the **Invoice details** page, select **Distributions** to show all distributions.</span></span> <span data-ttu-id="d0a8e-144">Tutaj można obejrzeć rozksięgowanie całej faktury.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-144">Here, you can view the accounting for the whole invoice.</span></span> <span data-ttu-id="d0a8e-145">Wyświetlane informacje obejmują wymiary finansowe i konta główne.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-145">The information that is shown includes the financial dimensions and the main accounts.</span></span> 
7.  <span data-ttu-id="d0a8e-146">Wybierz opcję **Załączniki**, aby wyświetlić wszelkie notatki lub pliki dołączone do faktury.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-146">Select **Attachments** to view any notes or files that are attached to the invoice.</span></span>
8.  <span data-ttu-id="d0a8e-147">Na stronie **Szczegóły faktury** zaznacz odpowiednią akcję przepływu pracy, aby ukończyć proces przeglądu.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-147">On the **Invoice details** page, select the appropriate workflow action to complete your review process.</span></span>
9.  <span data-ttu-id="d0a8e-148">Wybierz opcję **Gotowe**.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-148">Select **Done**.</span></span>
