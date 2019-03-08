---
title: Mobilny obszar roboczy Zatwierdzenie zamówienia zakupu
description: Ten temat zawiera informacje dotyczące komórkowego obszaru roboczego Zatwierdzenia zamówienia zakupu, w którym można wyświetlać zamówienia zakupu i reagować na niej poprzez różne czynności. Można na przykład zatwierdzić lub odrzucić zamówienie zakupu.
author: mkirknel
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchVendorPortalRequests
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 30211
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 75a38b99fe0aee7d4dd386191be236e54097e867
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "348855"
---
# <a name="purchase-order-approval-mobile-workspace"></a><span data-ttu-id="cafc2-104">Mobilny obszar roboczy Zatwierdzenie zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="cafc2-104">Purchase order approval mobile workspace</span></span>

[!include [banner](../includes/banner.md)]

[!include [retail name](../includes/retail-name.md)]

<span data-ttu-id="cafc2-105">Ten temat zawiera informacje o komórkowym obszarze roboczym **Zatwierdzenie zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="cafc2-105">This topic provides information about the **Purchase order approval** mobile workspace.</span></span> <span data-ttu-id="cafc2-106">W tym obszarze roboczym można wyświetlać zamówienia zakupu i reagować na niej poprzez różne akcje.</span><span class="sxs-lookup"><span data-stu-id="cafc2-106">This workspace lets you view purchase orders and respond to them through actions.</span></span> <span data-ttu-id="cafc2-107">Można na przykład zatwierdzić lub odrzucić zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="cafc2-107">For example, you can approve or reject a purchase order.</span></span>
 
## <a name="overview"></a><span data-ttu-id="cafc2-108">Przegląd</span><span class="sxs-lookup"><span data-stu-id="cafc2-108">Overview</span></span> 
<span data-ttu-id="cafc2-109">Zamówienia zakupu wymagające zatwierdzenia przechodzą przez przepływ pracy zatwierdzania.</span><span class="sxs-lookup"><span data-stu-id="cafc2-109">Purchase orders that requires approval go through an approval workflow.</span></span> <span data-ttu-id="cafc2-110">Przepływ pracy może obejmować różne kroki, które wymagają wykonania różnych operacji przez jedną lub więcej osób.</span><span class="sxs-lookup"><span data-stu-id="cafc2-110">The workflow can include various steps that require that one or more people take action.</span></span> <span data-ttu-id="cafc2-111">Na przykład osoba może być zobowiązana wykonać zadanie lub zatwierdzić zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="cafc2-111">For example, a person might have to complete a task or approve the purchase order.</span></span> 

<span data-ttu-id="cafc2-112">Mobilny obszar roboczy **Zatwierdzenie zamówienia zakupu** pozwala łatwo wyświetlać zamówienia zakupu i na nie reagować z urządzenia komórkowego.</span><span class="sxs-lookup"><span data-stu-id="cafc2-112">The **Purchase order approval** mobile workspace lets you easily view and respond to purchase orders from your mobile device.</span></span> <span data-ttu-id="cafc2-113">Ten obszar roboczy umożliwia także podejmowanie tych samych akcji przepływu pracy, jak na kliencie internetowym programu Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cafc2-113">This workspace also lets you take the same workflow actions that you can take from the Microsoft Dynamics 365 for Finance and Operations, web client.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cafc2-114">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="cafc2-114">Prerequisites</span></span>
<span data-ttu-id="cafc2-115">Wymagania wstępne różnią się w zależności od wersji programu Finance and Operations wdrożonej w organizacji.</span><span class="sxs-lookup"><span data-stu-id="cafc2-115">The prerequisites vary, depending on the version of Finance and Operations that has been deployed for your organization.</span></span>

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations"></a><span data-ttu-id="cafc2-116">Warunki wstępne w przypadku korzystania z Microsoft Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="cafc2-116">Prerequisites if you use Microsoft Dynamics 365 for Finance and Operations</span></span> 
<span data-ttu-id="cafc2-117">Jeśli w organizacji wdrożono oprogramowanie Microsoft Dynamics 365 for Finance and Operations, administrator systemu musi opublikować mobilny obszar roboczy **Zatwierdzenie zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="cafc2-117">If Microsoft Dynamics 365 for Finance and Operations has been deployed for your organization, the system administrator must publish the **Purchase order approval** mobile workspace.</span></span> <span data-ttu-id="cafc2-118">Instrukcje znajdziesz w temacie [Publikowanie mobilnego obszaru roboczego](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span><span class="sxs-lookup"><span data-stu-id="cafc2-118">For instructions, see [Publish a mobile workspace](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span></span>

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a><span data-ttu-id="cafc2-119">Warunki wstępne, jeśli jest używany program Microsoft Dynamics 365 for Operations w wersji 1611 z aktualizacją platformy 3 lub nowszą</span><span class="sxs-lookup"><span data-stu-id="cafc2-119">Prerequisites if you use Microsoft Dynamics 365 for Operations version 1611 with Platform update 3 or later</span></span>
<span data-ttu-id="cafc2-120">Jeśli w organizacji wdrożono oprogramowanie Microsoft Dynamics 365 for Operations w wersji 1611 z aktualizacją platformy 3 lub nowszą, administrator systemu musi wykonać następujące zadania wstępne.</span><span class="sxs-lookup"><span data-stu-id="cafc2-120">If Microsoft Dynamics 365 for Operations version 1611 with Platform update 3 or later has been deployed for your organization, the system administrator must complete the following prerequisites.</span></span> 

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="cafc2-121">Wymaganie wstępne</span><span class="sxs-lookup"><span data-stu-id="cafc2-121">Prerequisite</span></span></th>
<th><span data-ttu-id="cafc2-122">Rola</span><span class="sxs-lookup"><span data-stu-id="cafc2-122">Role</span></span></th>
<th><span data-ttu-id="cafc2-123">opis</span><span class="sxs-lookup"><span data-stu-id="cafc2-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="cafc2-124">Zainstalowanie poprawki KB 4017918.</span><span class="sxs-lookup"><span data-stu-id="cafc2-124">Implement KB 4017918.</span></span></td>
<td><span data-ttu-id="cafc2-125">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="cafc2-125">System administrator</span></span></td>
<td><span data-ttu-id="cafc2-126">KB 4017918 jest aktualizacją platformy języka X++ lub poprawką metadanych, która zawiera mobilny obszar roboczy <strong>Zatwierdzenie zamówienia zakupu</strong>.</span><span class="sxs-lookup"><span data-stu-id="cafc2-126">KB 4017918 is an X++ update or metadata hotfix that contains the <strong>Purchase order approval</strong> mobile workspace.</span></span> <span data-ttu-id="cafc2-127">W celu zainstalowania poprawki KB 4017918 administrator systemu musi wykonać następującą procedurę:</span><span class="sxs-lookup"><span data-stu-id="cafc2-127">To implement KB 4017918, your system administrator must follow these steps.</span></span>
<ol>
<li><span data-ttu-id="cafc2-128"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Pobierz poprawkę metadanych z usługi Microsoft Dynamics Lifecycle Services (LCS)</a>.</span><span class="sxs-lookup"><span data-stu-id="cafc2-128"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Download the metadata hotfix from Microsoft Dynamics Lifecycle Services (LCS)</a>.</span></span></li>
<li><span data-ttu-id="cafc2-129"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Zainstaluj poprawkę metadanych</a>.</span><span class="sxs-lookup"><span data-stu-id="cafc2-129"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Install the metadata hotfix</a>.</span></span></li>
<li><span data-ttu-id="cafc2-130"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Utwórz wdrażalny pakiet</a> zawierający model <strong>SCMMobile</strong>, a następnie przekaż ten wdrażalny pakiet do usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="cafc2-130"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Create a deployable package</a> that contains the <strong>SCMMobile</strong> model, and then upload the deployable package to LCS.</span></span></li>
<li><span data-ttu-id="cafc2-131"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Zastosuj wdrażalny pakiet</a></span><span class="sxs-lookup"><span data-stu-id="cafc2-131"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Apply the deployable package</a>.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cafc2-132">Opublikowanie mobilnego obszaru roboczego <strong>Zatwierdzenie zamówienia zakupu</strong>.</span><span class="sxs-lookup"><span data-stu-id="cafc2-132">Publish the <strong>Purchase order approval</strong> mobile workspace.</span></span></td>
<td><span data-ttu-id="cafc2-133">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="cafc2-133">System administrator</span></span></td>
<td><span data-ttu-id="cafc2-134">Zobacz <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publikowanie mobilnego obszaru roboczego</a>.</span><span class="sxs-lookup"><span data-stu-id="cafc2-134">See <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="cafc2-135">Pobieranie i instalowanie aplikacji mobilnej</span><span class="sxs-lookup"><span data-stu-id="cafc2-135">Download and install the mobile app</span></span>
<span data-ttu-id="cafc2-136">Pobierz i zainstaluj aplikację komórkową Microsoft Dynamics 365 for Unified Operations Mobile:</span><span class="sxs-lookup"><span data-stu-id="cafc2-136">Download and install the Microsoft Dynamics 365 for Unified Operations mobile app:</span></span>

- [<span data-ttu-id="cafc2-137">Telefony Android</span><span class="sxs-lookup"><span data-stu-id="cafc2-137">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
- [<span data-ttu-id="cafc2-138">Telefony iPhone</span><span class="sxs-lookup"><span data-stu-id="cafc2-138">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)


## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="cafc2-139">Logowanie do aplikacji mobilnej</span><span class="sxs-lookup"><span data-stu-id="cafc2-139">Sign in to the mobile app</span></span>

1. <span data-ttu-id="cafc2-140">Uruchom aplikację na urządzeniu komórkowym.</span><span class="sxs-lookup"><span data-stu-id="cafc2-140">Start the app on your mobile device.</span></span>
2. <span data-ttu-id="cafc2-141">Wprowadź swój adres URL w usłudze Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="cafc2-141">Enter your Microsoft Dynamics 365 URL.</span></span>
3. <span data-ttu-id="cafc2-142">Podczas pierwszego logowania pojawi się monit o podanie nazwy użytkownika i hasła.</span><span class="sxs-lookup"><span data-stu-id="cafc2-142">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="cafc2-143">Wprowadź swoje poświadczenia.</span><span class="sxs-lookup"><span data-stu-id="cafc2-143">Enter your credentials.</span></span>
4. <span data-ttu-id="cafc2-144">Po zalogowaniu się zobaczysz obszary robocze dostępne dla firmy.</span><span class="sxs-lookup"><span data-stu-id="cafc2-144">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="cafc2-145">Należy zauważyć, że jeśli administrator systemu później opublikuje nowy obszar roboczy, trzeba odświeżyć listę komórkowych obszarów roboczych.</span><span class="sxs-lookup"><span data-stu-id="cafc2-145">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

![Obszar roboczy Zatwierdzenie zamówienia zakupu na liście dostępnych obszarów roboczych](./media/po-workspaces.png)

## <a name="view-orders-that-are-assigned-to-you"></a><span data-ttu-id="cafc2-147">Wyświetlanie zamówień, które są Ci przypisane</span><span class="sxs-lookup"><span data-stu-id="cafc2-147">View orders that are assigned to you</span></span>
1. <span data-ttu-id="cafc2-148">Na urządzeniu przenośnym wybierz obszar roboczy **Zatwierdzenie zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="cafc2-148">On your mobile device, select the **Purchase order approval** workspace.</span></span>
2. <span data-ttu-id="cafc2-149">Kliknij opcję **Zamówienia przypisane do mnie**, z zostaną wyświetlone wszystkie zamówienia zakupu, którymi musisz się zająć w przepływie pracy zatwierdzania zamówień zakupu.</span><span class="sxs-lookup"><span data-stu-id="cafc2-149">Select **Orders assigned to me** to view all the purchase orders for which you've been asked to take action in the purchase order approval workflow.</span></span>
3. <span data-ttu-id="cafc2-150">Zaznacz zamówienie.</span><span class="sxs-lookup"><span data-stu-id="cafc2-150">Select an order.</span></span> <span data-ttu-id="cafc2-151">Na stronie **Szczegóły zamówienia** zobaczysz informacje nagłówka i wiersze zamówienia.</span><span class="sxs-lookup"><span data-stu-id="cafc2-151">On the **Order details** page, you will see the order header information and lines.</span></span> <span data-ttu-id="cafc2-152">W zadaniu przepływu pracy są również wyświetlane wytyczne postępowania.</span><span class="sxs-lookup"><span data-stu-id="cafc2-152">You can also find guidelines from the workflow task.</span></span>
4. <span data-ttu-id="cafc2-153">Kliknij opcję **Zasady podziału księgowań**, aby otworzyć stronę **Zasady podziału księgowań dotyczące nagłówka**.</span><span class="sxs-lookup"><span data-stu-id="cafc2-153">Select **Accounting distributions** to open the **Header accounting distributions** page.</span></span>
5. <span data-ttu-id="cafc2-154">Wróć do strony **Szczegóły zamówienia** i zaznacz wiersz.</span><span class="sxs-lookup"><span data-stu-id="cafc2-154">Return to the **Order details** page, and select a line.</span></span> <span data-ttu-id="cafc2-155">Z poziomu szczegółów wiersza zamówienia możesz też przeglądać zasady podziału księgowań specyficzne dla wiersza.</span><span class="sxs-lookup"><span data-stu-id="cafc2-155">From the order line details, you can also explore the line-specific accounting distributions.</span></span>

## <a name="complete-an-action-on-the-purchase-order"></a><span data-ttu-id="cafc2-156">Wykonywanie operacji w zamówieniu zakupu</span><span class="sxs-lookup"><span data-stu-id="cafc2-156">Complete an action on the purchase order</span></span>
<span data-ttu-id="cafc2-157">Po przejrzeniu przypisanego Ci zamówienia zakupu i zapoznaniu się z instrukcjami przepływu pracy możesz przystąpić do faktycznego działania.</span><span class="sxs-lookup"><span data-stu-id="cafc2-157">After you've viewed the purchase order that is assigned to you and read the workflow instructions, you should be ready to take action.</span></span>

1. <span data-ttu-id="cafc2-158">Na urządzeniu przenośnym wybierz obszar roboczy **Zatwierdzenie zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="cafc2-158">On your mobile device, select the **Purchase order approval** workspace.</span></span>
2. <span data-ttu-id="cafc2-159">Kliknij opcję **Zamówienia przypisane do mnie**, z zostaną wyświetlone wszystkie zamówienia zakupu, którymi musisz się zająć w przepływie pracy zatwierdzania zamówień zakupu.</span><span class="sxs-lookup"><span data-stu-id="cafc2-159">Select **Orders assigned to me** to view all the purchase orders for which you've been asked to take action in the purchase order approval workflow.</span></span>
3. <span data-ttu-id="cafc2-160">Zaznacz zamówienie i wyświetl stronę szczegółów.</span><span class="sxs-lookup"><span data-stu-id="cafc2-160">Select an order, and view the details page.</span></span>
4. <span data-ttu-id="cafc2-161">Kliknij opcję **Akcje**, aby wyświetlić dostępne akcje.</span><span class="sxs-lookup"><span data-stu-id="cafc2-161">Select **Actions** to show the available actions.</span></span> <span data-ttu-id="cafc2-162">Dostępne czynności zależą od zadania, które Ci przypisano.</span><span class="sxs-lookup"><span data-stu-id="cafc2-162">The actions that are available depend on the task that has been assigned to you.</span></span>

    | <span data-ttu-id="cafc2-163">Czynność zadania</span><span class="sxs-lookup"><span data-stu-id="cafc2-163">Task action</span></span>    | <span data-ttu-id="cafc2-164">Czynność zatwierdzenia</span><span class="sxs-lookup"><span data-stu-id="cafc2-164">Approval action</span></span>  |
    |----------------|------------------|
    | <span data-ttu-id="cafc2-165">Wykonane</span><span class="sxs-lookup"><span data-stu-id="cafc2-165">Complete</span></span>       | <span data-ttu-id="cafc2-166">Zatwierdzanie</span><span class="sxs-lookup"><span data-stu-id="cafc2-166">Approve</span></span>          |
    | <span data-ttu-id="cafc2-167">Powrót</span><span class="sxs-lookup"><span data-stu-id="cafc2-167">Return</span></span>         | <span data-ttu-id="cafc2-168">Odrzuć</span><span class="sxs-lookup"><span data-stu-id="cafc2-168">Reject</span></span>           |
    | <span data-ttu-id="cafc2-169">Żądaj zmiany</span><span class="sxs-lookup"><span data-stu-id="cafc2-169">Request change</span></span> | <span data-ttu-id="cafc2-170">Żądaj zmiany</span><span class="sxs-lookup"><span data-stu-id="cafc2-170">Request change</span></span>   |
    | <span data-ttu-id="cafc2-171">Użytkownik delegowany</span><span class="sxs-lookup"><span data-stu-id="cafc2-171">Delegate</span></span>       | <span data-ttu-id="cafc2-172">Użytkownik delegowany</span><span class="sxs-lookup"><span data-stu-id="cafc2-172">Delegate</span></span>         |

5. <span data-ttu-id="cafc2-173">Wybierz odpowiednią akcję.</span><span class="sxs-lookup"><span data-stu-id="cafc2-173">Select the appropriate action.</span></span>
6. <span data-ttu-id="cafc2-174">Na stronie **Wykonaj zadanie** wprowadź komentarz.</span><span class="sxs-lookup"><span data-stu-id="cafc2-174">On the **Complete task** page, enter a comment.</span></span> <span data-ttu-id="cafc2-175">Należy zauważyć, że po wybraniu akcji **Delegowanie** musisz wybrać użytkownika, któremu zadanie zostanie delegowane.</span><span class="sxs-lookup"><span data-stu-id="cafc2-175">Note that if you select the **Delegate** action, you must select a user to delegate the task to.</span></span>
7. <span data-ttu-id="cafc2-176">Wybierz opcję **Gotowe**.</span><span class="sxs-lookup"><span data-stu-id="cafc2-176">Select **Done**.</span></span> <span data-ttu-id="cafc2-177">Po odświeżeniu obszaru roboczego zamówienie zakupu przestanie być widoczne na liście.</span><span class="sxs-lookup"><span data-stu-id="cafc2-177">After you refresh your workspace, the purchase order will no longer be in your list.</span></span> 
