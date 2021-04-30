---
title: Mobilny obszar roboczy Zatwierdzenie zamówienia zakupu
description: Ten temat zawiera informacje dotyczące komórkowego obszaru roboczego Zatwierdzenia zamówienia zakupu, w którym można wyświetlać zamówienia zakupu i reagować na niej poprzez różne czynności. Można na przykład zatwierdzić lub odrzucić zamówienie zakupu.
author: kamaybac
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchVendorPortalRequests
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30211
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 26f0dc3b128daf8c7d8a05d6f3cacc5b7de0c756
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2021
ms.locfileid: "5909116"
---
# <a name="purchase-order-approval-mobile-workspace"></a><span data-ttu-id="03a4d-104">Mobilny obszar roboczy Zatwierdzenie zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="03a4d-104">Purchase order approval mobile workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="03a4d-105">Ten temat zawiera informacje o komórkowym obszarze roboczym **Zatwierdzenie zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="03a4d-105">This topic provides information about the **Purchase order approval** mobile workspace.</span></span> <span data-ttu-id="03a4d-106">W tym obszarze roboczym można wyświetlać zamówienia zakupu i reagować na niej poprzez różne akcje.</span><span class="sxs-lookup"><span data-stu-id="03a4d-106">This workspace lets you view purchase orders and respond to them through actions.</span></span> <span data-ttu-id="03a4d-107">Można na przykład zatwierdzić lub odrzucić zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="03a4d-107">For example, you can approve or reject a purchase order.</span></span>
 
## <a name="overview"></a><span data-ttu-id="03a4d-108">Przegląd</span><span class="sxs-lookup"><span data-stu-id="03a4d-108">Overview</span></span> 
<span data-ttu-id="03a4d-109">Zamówienia zakupu wymagające zatwierdzenia przechodzą przez przepływ pracy zatwierdzania.</span><span class="sxs-lookup"><span data-stu-id="03a4d-109">Purchase orders that requires approval go through an approval workflow.</span></span> <span data-ttu-id="03a4d-110">Przepływ pracy może obejmować różne kroki, które wymagają wykonania różnych operacji przez jedną lub więcej osób.</span><span class="sxs-lookup"><span data-stu-id="03a4d-110">The workflow can include various steps that require that one or more people take action.</span></span> <span data-ttu-id="03a4d-111">Na przykład osoba może być zobowiązana wykonać zadanie lub zatwierdzić zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="03a4d-111">For example, a person might have to complete a task or approve the purchase order.</span></span> 

<span data-ttu-id="03a4d-112">Mobilny obszar roboczy **Zatwierdzenie zamówienia zakupu** pozwala łatwo wyświetlać zamówienia zakupu i na nie reagować z urządzenia komórkowego.</span><span class="sxs-lookup"><span data-stu-id="03a4d-112">The **Purchase order approval** mobile workspace lets you easily view and respond to purchase orders from your mobile device.</span></span> <span data-ttu-id="03a4d-113">Ten obszar roboczy umożliwia także podejmowanie tych samych akcji przepływu pracy, jak na kliencie internetowym.</span><span class="sxs-lookup"><span data-stu-id="03a4d-113">This workspace also lets you take the same workflow actions that you can take from the web client.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="03a4d-114">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="03a4d-114">Prerequisites</span></span>
<span data-ttu-id="03a4d-115">Wymagania wstępne różnią się w zależności od wersji programu Supply Chain Management wdrożonej w organizacji.</span><span class="sxs-lookup"><span data-stu-id="03a4d-115">The prerequisites vary, depending on the version of Supply Chain Management that has been deployed for your organization.</span></span>

### <a name="prerequisites-if-you-use-supply-chain-management"></a><span data-ttu-id="03a4d-116">Warunki wstępne, jeśli jest używane Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="03a4d-116">Prerequisites if you use Supply Chain Management</span></span> 
<span data-ttu-id="03a4d-117">Jeśli w organizacji wdrożono rozwiązanie Supply Chain Management, administrator systemu musi opublikować mobilny obszar roboczy **Zatwierdzenie zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="03a4d-117">If Supply Chain Management has been deployed for your organization, the system administrator must publish the **Purchase order approval** mobile workspace.</span></span> <span data-ttu-id="03a4d-118">Instrukcje znajdziesz w temacie [Publikowanie mobilnego obszaru roboczego](../../fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace.md).</span><span class="sxs-lookup"><span data-stu-id="03a4d-118">For instructions, see [Publish a mobile workspace](../../fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace.md).</span></span>

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a><span data-ttu-id="03a4d-119">Warunki wstępne, jeśli jest używany program Microsoft Dynamics 365 for Operations w wersji 1611 z aktualizacją platformy 3 lub nowszą</span><span class="sxs-lookup"><span data-stu-id="03a4d-119">Prerequisites if you use Microsoft Dynamics 365 for Operations version 1611 with Platform update 3 or later</span></span>
<span data-ttu-id="03a4d-120">Jeśli w organizacji wdrożono oprogramowanie Microsoft Dynamics 365 for Operations w wersji 1611 z aktualizacją platformy 3 lub nowszą, administrator systemu musi wykonać następujące zadania wstępne.</span><span class="sxs-lookup"><span data-stu-id="03a4d-120">If Microsoft Dynamics 365 for Operations version 1611 with Platform update 3 or later has been deployed for your organization, the system administrator must complete the following prerequisites.</span></span> 

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="03a4d-121">Wymaganie wstępne</span><span class="sxs-lookup"><span data-stu-id="03a4d-121">Prerequisite</span></span></th>
<th><span data-ttu-id="03a4d-122">Rola</span><span class="sxs-lookup"><span data-stu-id="03a4d-122">Role</span></span></th>
<th><span data-ttu-id="03a4d-123">opis</span><span class="sxs-lookup"><span data-stu-id="03a4d-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="03a4d-124">Zainstalowanie poprawki KB 4017918.</span><span class="sxs-lookup"><span data-stu-id="03a4d-124">Implement KB 4017918.</span></span></td>
<td><span data-ttu-id="03a4d-125">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="03a4d-125">System administrator</span></span></td>
<td><span data-ttu-id="03a4d-126">KB 4017918 jest aktualizacją platformy języka X++ lub poprawką metadanych, która zawiera mobilny obszar roboczy <strong>Zatwierdzenie zamówienia zakupu</strong>.</span><span class="sxs-lookup"><span data-stu-id="03a4d-126">KB 4017918 is an X++ update or metadata hotfix that contains the <strong>Purchase order approval</strong> mobile workspace.</span></span> <span data-ttu-id="03a4d-127">W celu zainstalowania poprawki KB 4017918 administrator systemu musi wykonać następującą procedurę:</span><span class="sxs-lookup"><span data-stu-id="03a4d-127">To implement KB 4017918, your system administrator must follow these steps.</span></span>
<ol>
<li><span data-ttu-id="03a4d-128"><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/download-hotfix-lcs">Pobierz poprawkę metadanych z usługi Microsoft Dynamics Lifecycle Services (LCS)</a>.</span><span class="sxs-lookup"><span data-stu-id="03a4d-128"><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/download-hotfix-lcs">Download the metadata hotfix from Microsoft Dynamics Lifecycle Services (LCS)</a>.</span></span></li>
<li><span data-ttu-id="03a4d-129"><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Zainstaluj poprawkę metadanych</a>.</span><span class="sxs-lookup"><span data-stu-id="03a4d-129"><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Install the metadata hotfix</a>.</span></span></li>
<li><span data-ttu-id="03a4d-130"><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/create-apply-deployable-package">Utwórz wdrażalny pakiet</a> zawierający model <strong>SCMMobile</strong>, a następnie przekaż ten wdrażalny pakiet do usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="03a4d-130"><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/create-apply-deployable-package">Create a deployable package</a> that contains the <strong>SCMMobile</strong> model, and then upload the deployable package to LCS.</span></span></li>
<li><span data-ttu-id="03a4d-131"><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system">Zastosuj wdrażalny pakiet</a></span><span class="sxs-lookup"><span data-stu-id="03a4d-131"><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system">Apply the deployable package</a>.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="03a4d-132">Opublikowanie mobilnego obszaru roboczego <strong>Zatwierdzenie zamówienia zakupu</strong>.</span><span class="sxs-lookup"><span data-stu-id="03a4d-132">Publish the <strong>Purchase order approval</strong> mobile workspace.</span></span></td>
<td><span data-ttu-id="03a4d-133">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="03a4d-133">System administrator</span></span></td>
<td><span data-ttu-id="03a4d-134">Zobacz <a href="/dynamics365/fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace">Publikowanie mobilnego obszaru roboczego</a>.</span><span class="sxs-lookup"><span data-stu-id="03a4d-134">See <a href="/dynamics365/fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="03a4d-135">Pobieranie i instalowanie aplikacji mobilnej</span><span class="sxs-lookup"><span data-stu-id="03a4d-135">Download and install the mobile app</span></span>
<span data-ttu-id="03a4d-136">Pobieranie i instalowanie aplikacji mobilnej Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="03a4d-136">Download and install the Finance and Operations mobile app:</span></span>

- [<span data-ttu-id="03a4d-137">Telefony Android</span><span class="sxs-lookup"><span data-stu-id="03a4d-137">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
- [<span data-ttu-id="03a4d-138">Telefony iPhone</span><span class="sxs-lookup"><span data-stu-id="03a4d-138">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)


## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="03a4d-139">Logowanie do aplikacji mobilnej</span><span class="sxs-lookup"><span data-stu-id="03a4d-139">Sign in to the mobile app</span></span>

1. <span data-ttu-id="03a4d-140">Uruchom aplikację na urządzeniu komórkowym.</span><span class="sxs-lookup"><span data-stu-id="03a4d-140">Start the app on your mobile device.</span></span>
2. <span data-ttu-id="03a4d-141">Wprowadź swój adres URL w usłudze Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="03a4d-141">Enter your Microsoft Dynamics 365 URL.</span></span>
3. <span data-ttu-id="03a4d-142">Podczas pierwszego logowania pojawi się monit o podanie nazwy użytkownika i hasła.</span><span class="sxs-lookup"><span data-stu-id="03a4d-142">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="03a4d-143">Wprowadź swoje poświadczenia.</span><span class="sxs-lookup"><span data-stu-id="03a4d-143">Enter your credentials.</span></span>
4. <span data-ttu-id="03a4d-144">Po zalogowaniu się zobaczysz obszary robocze dostępne dla firmy.</span><span class="sxs-lookup"><span data-stu-id="03a4d-144">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="03a4d-145">Należy zauważyć, że jeśli administrator systemu później opublikuje nowy obszar roboczy, trzeba odświeżyć listę komórkowych obszarów roboczych.</span><span class="sxs-lookup"><span data-stu-id="03a4d-145">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

![Obszar roboczy Zatwierdzenie zamówienia zakupu na liście dostępnych obszarów roboczych](./media/po-workspaces.png)

## <a name="view-orders-that-are-assigned-to-you"></a><span data-ttu-id="03a4d-147">Wyświetlanie zamówień, które są Ci przypisane</span><span class="sxs-lookup"><span data-stu-id="03a4d-147">View orders that are assigned to you</span></span>
1. <span data-ttu-id="03a4d-148">Na urządzeniu przenośnym wybierz obszar roboczy **Zatwierdzenie zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="03a4d-148">On your mobile device, select the **Purchase order approval** workspace.</span></span>
2. <span data-ttu-id="03a4d-149">Kliknij opcję **Zamówienia przypisane do mnie**, z zostaną wyświetlone wszystkie zamówienia zakupu, którymi musisz się zająć w przepływie pracy zatwierdzania zamówień zakupu.</span><span class="sxs-lookup"><span data-stu-id="03a4d-149">Select **Orders assigned to me** to view all the purchase orders for which you've been asked to take action in the purchase order approval workflow.</span></span>
3. <span data-ttu-id="03a4d-150">Zaznacz zamówienie.</span><span class="sxs-lookup"><span data-stu-id="03a4d-150">Select an order.</span></span> <span data-ttu-id="03a4d-151">Na stronie **Szczegóły zamówienia** zobaczysz informacje nagłówka i wiersze zamówienia.</span><span class="sxs-lookup"><span data-stu-id="03a4d-151">On the **Order details** page, you will see the order header information and lines.</span></span> <span data-ttu-id="03a4d-152">W zadaniu przepływu pracy są również wyświetlane wytyczne postępowania.</span><span class="sxs-lookup"><span data-stu-id="03a4d-152">You can also find guidelines from the workflow task.</span></span>
4. <span data-ttu-id="03a4d-153">Kliknij opcję **Zasady podziału księgowań**, aby otworzyć stronę **Zasady podziału księgowań dotyczące nagłówka**.</span><span class="sxs-lookup"><span data-stu-id="03a4d-153">Select **Accounting distributions** to open the **Header accounting distributions** page.</span></span>
5. <span data-ttu-id="03a4d-154">Wróć do strony **Szczegóły zamówienia** i zaznacz wiersz.</span><span class="sxs-lookup"><span data-stu-id="03a4d-154">Return to the **Order details** page, and select a line.</span></span> <span data-ttu-id="03a4d-155">Z poziomu szczegółów wiersza zamówienia możesz też przeglądać zasady podziału księgowań specyficzne dla wiersza.</span><span class="sxs-lookup"><span data-stu-id="03a4d-155">From the order line details, you can also explore the line-specific accounting distributions.</span></span>

## <a name="complete-an-action-on-the-purchase-order"></a><span data-ttu-id="03a4d-156">Wykonywanie operacji w zamówieniu zakupu</span><span class="sxs-lookup"><span data-stu-id="03a4d-156">Complete an action on the purchase order</span></span>
<span data-ttu-id="03a4d-157">Po przejrzeniu przypisanego Ci zamówienia zakupu i zapoznaniu się z instrukcjami przepływu pracy możesz przystąpić do faktycznego działania.</span><span class="sxs-lookup"><span data-stu-id="03a4d-157">After you've viewed the purchase order that is assigned to you and read the workflow instructions, you should be ready to take action.</span></span>

1. <span data-ttu-id="03a4d-158">Na urządzeniu przenośnym wybierz obszar roboczy **Zatwierdzenie zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="03a4d-158">On your mobile device, select the **Purchase order approval** workspace.</span></span>
2. <span data-ttu-id="03a4d-159">Kliknij opcję **Zamówienia przypisane do mnie**, z zostaną wyświetlone wszystkie zamówienia zakupu, którymi musisz się zająć w przepływie pracy zatwierdzania zamówień zakupu.</span><span class="sxs-lookup"><span data-stu-id="03a4d-159">Select **Orders assigned to me** to view all the purchase orders for which you've been asked to take action in the purchase order approval workflow.</span></span>
3. <span data-ttu-id="03a4d-160">Zaznacz zamówienie i wyświetl stronę szczegółów.</span><span class="sxs-lookup"><span data-stu-id="03a4d-160">Select an order, and view the details page.</span></span>
4. <span data-ttu-id="03a4d-161">Kliknij opcję **Akcje**, aby wyświetlić dostępne akcje.</span><span class="sxs-lookup"><span data-stu-id="03a4d-161">Select **Actions** to show the available actions.</span></span> <span data-ttu-id="03a4d-162">Dostępne czynności zależą od zadania, które Ci przypisano.</span><span class="sxs-lookup"><span data-stu-id="03a4d-162">The actions that are available depend on the task that has been assigned to you.</span></span>

    | <span data-ttu-id="03a4d-163">Czynność zadania</span><span class="sxs-lookup"><span data-stu-id="03a4d-163">Task action</span></span>    | <span data-ttu-id="03a4d-164">Czynność zatwierdzenia</span><span class="sxs-lookup"><span data-stu-id="03a4d-164">Approval action</span></span>  |
    |----------------|------------------|
    | <span data-ttu-id="03a4d-165">Wykonane</span><span class="sxs-lookup"><span data-stu-id="03a4d-165">Complete</span></span>       | <span data-ttu-id="03a4d-166">Zatwierdzanie</span><span class="sxs-lookup"><span data-stu-id="03a4d-166">Approve</span></span>          |
    | <span data-ttu-id="03a4d-167">Powrót</span><span class="sxs-lookup"><span data-stu-id="03a4d-167">Return</span></span>         | <span data-ttu-id="03a4d-168">Odrzuć</span><span class="sxs-lookup"><span data-stu-id="03a4d-168">Reject</span></span>           |
    | <span data-ttu-id="03a4d-169">Żądaj zmiany</span><span class="sxs-lookup"><span data-stu-id="03a4d-169">Request change</span></span> | <span data-ttu-id="03a4d-170">Żądaj zmiany</span><span class="sxs-lookup"><span data-stu-id="03a4d-170">Request change</span></span>   |
    | <span data-ttu-id="03a4d-171">Użytkownik delegowany</span><span class="sxs-lookup"><span data-stu-id="03a4d-171">Delegate</span></span>       | <span data-ttu-id="03a4d-172">Użytkownik delegowany</span><span class="sxs-lookup"><span data-stu-id="03a4d-172">Delegate</span></span>         |

5. <span data-ttu-id="03a4d-173">Wybierz odpowiednią akcję.</span><span class="sxs-lookup"><span data-stu-id="03a4d-173">Select the appropriate action.</span></span>
6. <span data-ttu-id="03a4d-174">Na stronie **Wykonaj zadanie** wprowadź komentarz.</span><span class="sxs-lookup"><span data-stu-id="03a4d-174">On the **Complete task** page, enter a comment.</span></span> <span data-ttu-id="03a4d-175">Należy zauważyć, że po wybraniu akcji **Delegowanie** musisz wybrać użytkownika, któremu zadanie zostanie delegowane.</span><span class="sxs-lookup"><span data-stu-id="03a4d-175">Note that if you select the **Delegate** action, you must select a user to delegate the task to.</span></span>
7. <span data-ttu-id="03a4d-176">Wybierz opcję **Gotowe**.</span><span class="sxs-lookup"><span data-stu-id="03a4d-176">Select **Done**.</span></span> <span data-ttu-id="03a4d-177">Po odświeżeniu obszaru roboczego zamówienie zakupu przestanie być widoczne na liście.</span><span class="sxs-lookup"><span data-stu-id="03a4d-177">After you refresh your workspace, the purchase order will no longer be in your list.</span></span> 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]