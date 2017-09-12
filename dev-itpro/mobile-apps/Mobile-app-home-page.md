---
title: "Strona główna aplikacji mobilnej"
description: "W tym temacie opisano aplikację mobilną Microsoft Dynamics 365 for Unified Operations oraz zamieszczono łącza do zasobów, które mogą pomóc w jej zaimplementowaniu w organizacji."
author: sericks007
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, UnifiedOperations, Platform
ms.custom: 272853
ms.assetid: c99f818f-27b3-4e45-92b4-74272dad0e17
ms.search.region: Global
ms.author: sericks
ms.dyn365.ops.intro: Platform update 4
ms.search.validFrom: 2017-02-28
ms.translationtype: HT
ms.sourcegitcommit: 5230911e1febc66b294f1331846373a472789adf
ms.openlocfilehash: 46a77f2757bee9f688d8c0d23f15cd7eb27ebcb3
ms.contentlocale: pl-pl
ms.lasthandoff: 08/04/2017

---

# <a name="mobile-app-home-page"></a><span data-ttu-id="19d7b-103">Strona główna aplikacji mobilnej</span><span class="sxs-lookup"><span data-stu-id="19d7b-103">Mobile app home page</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="19d7b-104">W tym temacie opisano aplikację mobilną Microsoft Dynamics 365 for Unified Operations oraz zamieszczono łącza do zasobów, które mogą pomóc w jej zaimplementowaniu w organizacji.</span><span class="sxs-lookup"><span data-stu-id="19d7b-104">This topic describes the Microsoft Dynamics 365 for Unified Operations mobile app and provides links to resources that can help you implement it in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="19d7b-105">Poprzednio aplikacja mobilnej nazywała się *Microsoft Dynamics 365 for Finance and Operations*.</span><span class="sxs-lookup"><span data-stu-id="19d7b-105">The mobile app was previously named *Microsoft Dynamics 365 for Finance and Operations*.</span></span>

<a name="overview"></a><span data-ttu-id="19d7b-106">Przegląd</span><span class="sxs-lookup"><span data-stu-id="19d7b-106">Overview</span></span>
--------

<span data-ttu-id="19d7b-107">Aplikacja komórkowa umożliwia organizacji udostępnianie procesów biznesowych na urządzeniach przenośnych.</span><span class="sxs-lookup"><span data-stu-id="19d7b-107">The mobile app enables your organization to make its business processes available on mobile devices.</span></span> <span data-ttu-id="19d7b-108">Gdy administrator systemów informatycznych włączy komórkowe obszary robocze w organizacji, użytkownicy mogą się logować do aplikacji i natychmiast zacząć wykonywać procesy biznesowe na swoich urządzeniach komórkowych.</span><span class="sxs-lookup"><span data-stu-id="19d7b-108">After your IT admin enables the mobile workspaces for your organization, users can sign in to the app and immediately begin to run business processes from their mobile devices.</span></span> <span data-ttu-id="19d7b-109">Aplikacja mobilna zawiera następujące funkcje, które mogą pomóc zwiększyć wydajność pracy:</span><span class="sxs-lookup"><span data-stu-id="19d7b-109">The mobile app includes the following features that can help increase productivity:</span></span>

- <span data-ttu-id="19d7b-110">Użytkownicy mogą przeglądać, edytować i przetwarzać dane biznesowe, nawet jeśli mają przerywaną łączność z siecią albo ich urządzenia przenośne są całkowicie w trybie offline.</span><span class="sxs-lookup"><span data-stu-id="19d7b-110">Users can view, edit, and act on business data, even if they have intermittent network connectivity or their mobile devices are completely offline.</span></span> <span data-ttu-id="19d7b-111">Gdy urządzenie ponownie nawiąże połączenie sieciowe, operacje na danych wykonane w trybie offline są synchronizowane automatycznie z programem Dynamics 365 for Finance and Operations Enterprise Edition lub Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="19d7b-111">When a device reestablishes a network connection, offline data operations are automatically synchronized with Dynamics 365 for Finance and Operations, Enterprise edition, or Microsoft Dynamics 365 for Finance and Operations.</span></span>
- <span data-ttu-id="19d7b-112">Administratorzy IT i programiści mogą tworzyć i publikować mobilne obszary robocze spersonalizowane do organizacji.</span><span class="sxs-lookup"><span data-stu-id="19d7b-112">IT admins or developers can build and publish mobile workspaces that have been tailored to their organization.</span></span> <span data-ttu-id="19d7b-113">Aplikacja wykorzystuje istniejące środowisko oprogramowania.</span><span class="sxs-lookup"><span data-stu-id="19d7b-113">The app uses your existing code assets.</span></span> <span data-ttu-id="19d7b-114">W związku z tym nie jest konieczne ponowne implementowanie procedur sprawdzania poprawności, logiki biznesowej ani konfiguracji zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="19d7b-114">Therefore, you don't have to re-implement your validation procedures, business logic, or security configuration.</span></span>
- <span data-ttu-id="19d7b-115">Administratorzy IT i deweloperzy mogą łatwo projektować komórkowe obszary robocze za pomocą projektanta obszarów roboczych typu „wskaż i kliknij”, który jest zawarty w kliencie internetowym.</span><span class="sxs-lookup"><span data-stu-id="19d7b-115">IT admins or developers can easily design mobile workspaces by using the point-and-click workspace designer that is included with the web client.</span></span>
- <span data-ttu-id="19d7b-116">Administratorzy IT i deweloperzy mogą opcjonalnie optymalizować funkcje offline obszarów roboczych za pomocą struktury rozszerzania logiki biznesowej.</span><span class="sxs-lookup"><span data-stu-id="19d7b-116">IT admins or developers can optionally optimize the offline capabilities of workspaces by using the Business logic extensibility framework.</span></span> <span data-ttu-id="19d7b-117">Ponieważ dane są cały czas przetwarzane, gdy urządzenie jest w trybie offline, scenariusz użytkowania mobilnego pozostaje bogaty funkcjonalnie i płynny, nawet jeśli urządzenia nie mają stałej łączności z siecią.</span><span class="sxs-lookup"><span data-stu-id="19d7b-117">Because data continues to be processed while a device is offline, your mobile scenarios remain rich and fluid, even if devices don't have constant network connectivity.</span></span>

## <a name="elements-of-the-mobile-app"></a><span data-ttu-id="19d7b-118">Elementy aplikacji mobilnej</span><span class="sxs-lookup"><span data-stu-id="19d7b-118">Elements of the mobile app</span></span>
<span data-ttu-id="19d7b-119">Nawigacja w aplikacji mobilnej jest podzielona na cztery podstawowe koncepcje: pulpit nawigacyjny, obszary robocze, strony i akcje.</span><span class="sxs-lookup"><span data-stu-id="19d7b-119">Navigation in the mobile app consists of four basic concepts: the dashboard, workspaces, pages, and actions.</span></span> 

<span data-ttu-id="19d7b-120">[![Koncepcje nawigacyjne w aplikacji mobilnej](./media/mobilephoneapp1-1024x536.png)](./media/mobilephoneapp1.png)</span><span class="sxs-lookup"><span data-stu-id="19d7b-120">[![Navigation concepts in the mobile app](./media/mobilephoneapp1-1024x536.png)](./media/mobilephoneapp1.png)</span></span>

1. <span data-ttu-id="19d7b-121">Po uruchomieniu aplikacji przechodzisz do **pulpitu nawigacyjnego**.</span><span class="sxs-lookup"><span data-stu-id="19d7b-121">When you start the app, you go to the **dashboard**.</span></span>
2. <span data-ttu-id="19d7b-122">Na pulpicie nawigacyjnym widać listę **obszarów roboczych**, które zostały opublikowane.</span><span class="sxs-lookup"><span data-stu-id="19d7b-122">On the dashboard, you can see a list of **workspaces** that have been published.</span></span>
3. <span data-ttu-id="19d7b-123">W każdym obszarze roboczym widać listę **stron** dostępnych dla tego obszaru roboczego.</span><span class="sxs-lookup"><span data-stu-id="19d7b-123">In each workspace, you can see a list of **pages** that are available for that workspace.</span></span>
4. <span data-ttu-id="19d7b-124">Po przejściu do strony można wykonać kilka czynności.</span><span class="sxs-lookup"><span data-stu-id="19d7b-124">After you're on a page, you can perform several actions.</span></span> <span data-ttu-id="19d7b-125">Oto kilka przykładów:</span><span class="sxs-lookup"><span data-stu-id="19d7b-125">Here are some examples:</span></span>

    - <span data-ttu-id="19d7b-126">Wyświetlanie szczegółowych danych.</span><span class="sxs-lookup"><span data-stu-id="19d7b-126">View detailed data.</span></span>
    - <span data-ttu-id="19d7b-127">Przechodzenie do innych stron zawierających pokrewne dane, takie jak szczegóły jednostek lub wiersze.</span><span class="sxs-lookup"><span data-stu-id="19d7b-127">Navigate to other pages for related data, such as entity details or lines.</span></span>
    - <span data-ttu-id="19d7b-128">Wyświetlanie listy **akcji** dostępnych dla tej strony.</span><span class="sxs-lookup"><span data-stu-id="19d7b-128">See a list of **actions** that are available for that page.</span></span> <span data-ttu-id="19d7b-129">Akcje umożliwiają tworzenie nowych i edytowanie istniejących danych.</span><span class="sxs-lookup"><span data-stu-id="19d7b-129">Actions let you create or edit existing data.</span></span>

## <a name="implementation-process"></a><span data-ttu-id="19d7b-130">Projekt wdrażania</span><span class="sxs-lookup"><span data-stu-id="19d7b-130">Implementation process</span></span>
<span data-ttu-id="19d7b-131">Na poniższej ilustracji przedstawiono proces wdrażania mobilnych obszarów roboczych dostarczanych przez Microsoft i niestandardowych mobilnych obszarów roboczych.</span><span class="sxs-lookup"><span data-stu-id="19d7b-131">The following illustration shows the process for implementing both mobile workspaces that are provided by Microsoft and custom mobile workspaces.</span></span> 

![Proces implementacji aplikacji mobilnych](./media/Mobile-implementation-process-5.png)

<span data-ttu-id="19d7b-133">Poniższa tabela zawiera łącza do zasobów, które mogą pomóc we wdrażaniu mobilnych obszarów roboczych dostarczanych przez Microsoft i niestandardowych mobilnych obszarów roboczych.</span><span class="sxs-lookup"><span data-stu-id="19d7b-133">The following table includes links to resources that can help you implement both mobile workspaces that are provided by Microsoft and custom mobile workspaces.</span></span> <span data-ttu-id="19d7b-134">Numery w pierwszej kolumnie odpowiadają ponumerowanym krokom na poprzedniej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="19d7b-134">The numbers in the first column correspond to the numbered steps in the previous illustration.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="19d7b-135">Krok</span><span class="sxs-lookup"><span data-stu-id="19d7b-135">Step</span></span></th>
<th><span data-ttu-id="19d7b-136">Rola</span><span class="sxs-lookup"><span data-stu-id="19d7b-136">Role</span></span></th>
<th><span data-ttu-id="19d7b-137">Akcja</span><span class="sxs-lookup"><span data-stu-id="19d7b-137">Action</span></span></th>
<th><span data-ttu-id="19d7b-138">Zasoby pomagające wykonać akcję</span><span class="sxs-lookup"><span data-stu-id="19d7b-138">Resources to help you complete the action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="19d7b-139">1</span><span class="sxs-lookup"><span data-stu-id="19d7b-139">1</span></span></td>
<td><span data-ttu-id="19d7b-140">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="19d7b-140">System administrator</span></span></td>
<td><span data-ttu-id="19d7b-141">Zaimplementowanie programu Finance and Operations w organizacji.</span><span class="sxs-lookup"><span data-stu-id="19d7b-141">Implement Finance and Operations or Finance and Operations in your organization.</span></span></td>
<td><ul><li><span data-ttu-id="19d7b-142">Jeśli w organizacji jeszcze nie wdrożono wersji oprogramowania Microsoft Dynamics 365, zobacz <a href="../deployment/deploy-demo-environment.md">Wdrażanie środowiska demonstracyjnego</a>.</span><span class="sxs-lookup"><span data-stu-id="19d7b-142">If you haven't yet deployed a version of Microsoft Dynamics 365, see <a href="../deployment/deploy-demo-environment.md">Deploy a demo environment</a>.</span></span></li><li><span data-ttu-id="19d7b-143">Aby wyświetlić listę komórkowych obszarów roboczych, których można używać, zobacz <a href="mobile-workspaces-released.md">Ostatnio wydane mobilne obszary robocze</a>.</span><span class="sxs-lookup"><span data-stu-id="19d7b-143">To see a list of mobile workspaces that can be used, see <a href="mobile-workspaces-released.md">Mobile workspaces recently released</a>.</span></span></li></ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="19d7b-144">2</span><span class="sxs-lookup"><span data-stu-id="19d7b-144">2</span></span></td>
<td><span data-ttu-id="19d7b-145">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="19d7b-145">System administrator</span></span></td>
<td><span data-ttu-id="19d7b-146"><strong>Jeśli w organizacji jest już używany program Microsoft Dynamics 365 for Finance and Operations w wersji 1611:</strong> Pobranie i zainstalowanie aktualizacji KB, które włączą obsługę mobilnych obszarów roboczych dostarczanych przez Microsoft.</span><span class="sxs-lookup"><span data-stu-id="19d7b-146"><strong>If you're using Microsoft Dynamics 365 for Finance and Operations version 1611:</strong> Download and install KBs that enable the mobile workspaces that are provided by Microsoft.</span></span></td>
<td><span data-ttu-id="19d7b-147">Aby uzyskać więcej informacji, zobacz następujące tematy:</span><span class="sxs-lookup"><span data-stu-id="19d7b-147">See the following topics for more information:</span></span>
<ul>

<li><span data-ttu-id="19d7b-148"><a href="/dynamics365/unified-operations/financials/cost-accounting/cost-controlling-mobile-workspace">Mobilny obszar roboczy Kontrola kosztów</a></span><span class="sxs-lookup"><span data-stu-id="19d7b-148"><a href="/dynamics365/unified-operations/financials/cost-accounting/cost-controlling-mobile-workspace">Cost controlling mobile workspaces</a></span></span></li>
<li><span data-ttu-id="19d7b-149"><a href="/dynamics365/unified-operations/supply-chain/inventory/inventory-on-hand-mobile-workspace">Mobilny obszar roboczy Dostępne zapasy</a></span><span class="sxs-lookup"><span data-stu-id="19d7b-149"><a href="/dynamics365/unified-operations/supply-chain/inventory/inventory-on-hand-mobile-workspace">Inventory on-hand mobile workspace</a></span></span></li>
<li><span data-ttu-id="19d7b-150"><a href="/dynamics365/unified-operations/supply-chain/sales-marketing/sales-orders-mobile-workspace">Mobilny obszar roboczy Zamówienia sprzedaży</a></span><span class="sxs-lookup"><span data-stu-id="19d7b-150"><a href="/dynamics365/unified-operations/supply-chain/sales-marketing/sales-orders-mobile-workspace">Sales orders mobile workspaces</a></span></span></li>
<li><span data-ttu-id="19d7b-151"><a href="/dynamics365/unified-operations/supply-chain/procurement/vendor-collaboration-mobile-workspace">Obszar roboczy współpracy z dostawcami za pomocą urządzeń przenośnych</a></span><span class="sxs-lookup"><span data-stu-id="19d7b-151"><a href="/dynamics365/unified-operations/supply-chain/procurement/vendor-collaboration-mobile-workspace">Vendor collaboration mobile workspace</a></span></span></li>
<li><span data-ttu-id="19d7b-152"><a href="/dynamics365/unified-operations/financials/project-management/project-time-entry-mobile-workspace">Mobilny obszar roboczy Wprowadzanie czasu projektu</a></span><span class="sxs-lookup"><span data-stu-id="19d7b-152"><a href="/dynamics365/unified-operations/financials/project-management/project-time-entry-mobile-workspace">Project time entry mobile workspace</a></span></span></li>
<li><span data-ttu-id="19d7b-153"><a href="/dynamics365/unified-operations/financials/expense-management/expense-management-mobile-workspace">Mobilny obszar roboczy Zarządzanie wydatkami</a></span><span class="sxs-lookup"><span data-stu-id="19d7b-153"><a href="/dynamics365/unified-operations/financials/expense-management/expense-management-mobile-workspace">Expense management mobile workspace</a></span></span></li>

</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="19d7b-154">3</span><span class="sxs-lookup"><span data-stu-id="19d7b-154">3</span></span></td>
<td><span data-ttu-id="19d7b-155">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="19d7b-155">System administrator</span></span></td>
<td><span data-ttu-id="19d7b-156">Opublikowanie mobilnych obszarów roboczych dostarczonych przez Microsoft.</span><span class="sxs-lookup"><span data-stu-id="19d7b-156">Publish the mobile workspaces that are provided by Microsoft.</span></span></td>
<td><span data-ttu-id="19d7b-157"><a href="publish-mobile-workspace.md">Publikowanie mobilnego obszaru roboczego</a>
</span><span class="sxs-lookup"><span data-stu-id="19d7b-157"><a href="publish-mobile-workspace.md">Publish a mobile workspace</a>
</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="19d7b-158">4</span><span class="sxs-lookup"><span data-stu-id="19d7b-158">4</span></span></td>
<td><span data-ttu-id="19d7b-159">Programista lub niezależny dostawca oprogramowania (ISV)</span><span class="sxs-lookup"><span data-stu-id="19d7b-159">Developer or independent software vendor (ISV)</span></span></td>
<td><span data-ttu-id="19d7b-160">Utworzenie niestandardowych mobilnych obszarów roboczych za pomocą platformy komórkowej.</span><span class="sxs-lookup"><span data-stu-id="19d7b-160">Use the mobile platform to create custom mobile workspaces.</span></span></td>
<td><span data-ttu-id="19d7b-161"><a href="platform/mobile-platform-home-page.md">Platforma mobilna</a></span><span class="sxs-lookup"><span data-stu-id="19d7b-161"><a href="platform/mobile-platform-home-page.md">Mobile platform</a></span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="19d7b-162">5</span><span class="sxs-lookup"><span data-stu-id="19d7b-162">5</span></span></td>
<td><span data-ttu-id="19d7b-163">Niezależny dostawca oprogramowania</span><span class="sxs-lookup"><span data-stu-id="19d7b-163">ISV</span></span></td>
<td><span data-ttu-id="19d7b-164">Utworzenie wdrażalnego pakietu zawierającego niestandardowe mobilne obszary robocze i przekazanie pakietu do usługi Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="19d7b-164">Create a deployable package that contains custom mobile workspaces, and upload the package to Microsoft Dynamics Lifecycle Services (LCS).</span></span></td>
<td><span data-ttu-id="19d7b-165"><a href="../deployment/create-apply-deployable-package.md">Tworzenie wdrażalnego pakietu</a></span><span class="sxs-lookup"><span data-stu-id="19d7b-165"><a href="../deployment/create-apply-deployable-package.md">Create a deployable package</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="19d7b-166">6</span><span class="sxs-lookup"><span data-stu-id="19d7b-166">6</span></span></td>
<td><span data-ttu-id="19d7b-167">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="19d7b-167">System administrator</span></span></td>
<td><span data-ttu-id="19d7b-168">Zastosowanie wdrażalnego pakietu zawierającego niestandardowe obszary robocze dostarczonego przez niezależnego dostawcę oprogramowania (ISV).</span><span class="sxs-lookup"><span data-stu-id="19d7b-168">Apply the deployable package that contains the custom workspaces that are provided by the independent software vendor (ISV).</span></span></td>
<td><span data-ttu-id="19d7b-169"><a href="../deployment/apply-deployable-package-system.md">Stosowanie wdrażalnego pakietu</a></span><span class="sxs-lookup"><span data-stu-id="19d7b-169"><a href="../deployment/apply-deployable-package-system.md">Apply a deployable package</a></span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="19d7b-170">7</span><span class="sxs-lookup"><span data-stu-id="19d7b-170">7</span></span></td>
<td><span data-ttu-id="19d7b-171">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="19d7b-171">System administrator</span></span></td>
<td><span data-ttu-id="19d7b-172">Opublikowanie niestandardowych mobilnych obszarów roboczych dostarczonych przez niezależnego dostawcę oprogramowania.</span><span class="sxs-lookup"><span data-stu-id="19d7b-172">Publish the custom mobile workspaces that are provided by the ISV.</span></span></td>
<td><span data-ttu-id="19d7b-173"><a href="publish-mobile-workspace.md">Publikowanie mobilnego obszaru roboczego</a></span><span class="sxs-lookup"><span data-stu-id="19d7b-173"><a href="publish-mobile-workspace.md">Publish a mobile workspace</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="19d7b-174">8</span><span class="sxs-lookup"><span data-stu-id="19d7b-174">8</span></span></td>
<td><span data-ttu-id="19d7b-175">Użytkownik</span><span class="sxs-lookup"><span data-stu-id="19d7b-175">User</span></span></td>
<td><span data-ttu-id="19d7b-176">Pobieranie i instalowanie aplikacji mobilnej.</span><span class="sxs-lookup"><span data-stu-id="19d7b-176">Download and install the mobile app.</span></span></td>
<td><ul>
<li><span data-ttu-id="19d7b-177"><a href="https://go.microsoft.com/fwlink/?linkid=850662">Telefony z systemem Android</a></span><span class="sxs-lookup"><span data-stu-id="19d7b-177"><a href="https://go.microsoft.com/fwlink/?linkid=850662">For Android phones</a></span></span></li>
<li><span data-ttu-id="19d7b-178"><a href="https://go.microsoft.com/fwlink/?linkid=850663">Telefony iPhone</a></span><span class="sxs-lookup"><span data-stu-id="19d7b-178"><a href="https://go.microsoft.com/fwlink/?linkid=850663">For iPhones</a></span></span></li></ul>
</td>
</tr>
<tr class="odd">
<td><span data-ttu-id="19d7b-179">9</span><span class="sxs-lookup"><span data-stu-id="19d7b-179">9</span></span></td>
<td><span data-ttu-id="19d7b-180">Użytkownik</span><span class="sxs-lookup"><span data-stu-id="19d7b-180">User</span></span></td>
<td><span data-ttu-id="19d7b-181">Zalogowanie się do aplikacji mobilnej i jej używanie.</span><span class="sxs-lookup"><span data-stu-id="19d7b-181">Sign in, and use the mobile app.</span></span> <span data-ttu-id="19d7b-182">Aplikacja zawiera mobilne obszary robocze, które zostały opublikowane przez administratora systemu.</span><span class="sxs-lookup"><span data-stu-id="19d7b-182">The app includes the mobile workspaces that have been published by the system administrator.</span></span></td>
<td><span data-ttu-id="19d7b-183">Aby wyświetlić listę komórkowych obszarów roboczych dostarczonych przez Microsoft, zobacz <a href="mobile-workspaces-released.md">Ostatnio wydane mobilne obszary robocze</a>.</span><span class="sxs-lookup"><span data-stu-id="19d7b-183">To see a list of mobile workspaces that are provided by Microsoft, see <a href="mobile-workspaces-released.md">Mobile workspaces recently released</a>.</span></span>
</td>
</tr>
</tbody>
</table>

