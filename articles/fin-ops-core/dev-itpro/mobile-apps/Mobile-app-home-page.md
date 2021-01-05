---
title: Aplikacja mobilna — strona główna
description: W tym temacie opisano aplikację mobilną Finance and Operations (Dynamics 365) i zamieszczono łącza do zasobów, które mogą pomóc w jej zaimplementowaniu w organizacji.
author: ChrisGarty
manager: AnnBe
ms.date: 01/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 272853
ms.assetid: c99f818f-27b3-4e45-92b4-74272dad0e17
ms.search.region: Global
ms.author: cgarty
ms.dyn365.ops.version: Platform update 4
ms.search.validFrom: 2017-02-28
ms.openlocfilehash: e4a9d6424e2d214624c148c0565c88ea4cf4ccf9
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683465"
---
# <a name="mobile-app-home-page"></a><span data-ttu-id="425bd-103">Aplikacja mobilna — strona główna</span><span class="sxs-lookup"><span data-stu-id="425bd-103">Mobile app home page</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="425bd-104">W tym temacie opisano aplikację mobilną **Finance and Operations (Dynamics 365)** i zamieszczono łącza do zasobów, które mogą pomóc w jej zaimplementowaniu w organizacji.</span><span class="sxs-lookup"><span data-stu-id="425bd-104">This topic describes the **Finance and Operations (Dynamics 365)** mobile app and provides links to resources that can help you implement it in your organization.</span></span>

<a name="overview"></a><span data-ttu-id="425bd-105">Przegląd</span><span class="sxs-lookup"><span data-stu-id="425bd-105">Overview</span></span>
--------

<span data-ttu-id="425bd-106">Aplikacja komórkowa umożliwia organizacji udostępnianie procesów biznesowych na urządzeniach przenośnych.</span><span class="sxs-lookup"><span data-stu-id="425bd-106">The mobile app enables your organization to make its business processes available on mobile devices.</span></span> <span data-ttu-id="425bd-107">Gdy administrator systemów informatycznych włączy komórkowe obszary robocze w organizacji, użytkownicy mogą się logować do aplikacji i natychmiast zacząć wykonywać procesy biznesowe na swoich urządzeniach komórkowych.</span><span class="sxs-lookup"><span data-stu-id="425bd-107">After your IT admin enables the mobile workspaces for your organization, users can sign in to the app and immediately begin to run business processes from their mobile devices.</span></span> <span data-ttu-id="425bd-108">Aplikacja mobilna zawiera następujące funkcje, które mogą pomóc zwiększyć wydajność pracy:</span><span class="sxs-lookup"><span data-stu-id="425bd-108">The mobile app includes the following features that can help increase productivity:</span></span>

- <span data-ttu-id="425bd-109">Użytkownicy mogą przeglądać, edytować i przetwarzać dane biznesowe, nawet jeśli mają przerywaną łączność z siecią albo ich urządzenia przenośne są całkowicie w trybie offline.</span><span class="sxs-lookup"><span data-stu-id="425bd-109">Users can view, edit, and act on business data, even if they have intermittent network connectivity or their mobile devices are completely offline.</span></span> <span data-ttu-id="425bd-110">Gdy urządzenie ponownie nawiąże połączenie sieciowe, operacje na danych wykonane w trybie offline są synchronizowane automatycznie.</span><span class="sxs-lookup"><span data-stu-id="425bd-110">When a device reestablishes a network connection, offline data operations are automatically synchronized.</span></span>
- <span data-ttu-id="425bd-111">Administratorzy IT i programiści mogą tworzyć i publikować mobilne obszary robocze spersonalizowane do organizacji.</span><span class="sxs-lookup"><span data-stu-id="425bd-111">IT admins or developers can build and publish mobile workspaces that have been tailored to their organization.</span></span> <span data-ttu-id="425bd-112">Aplikacja wykorzystuje istniejące środowisko oprogramowania.</span><span class="sxs-lookup"><span data-stu-id="425bd-112">The app uses your existing code assets.</span></span> <span data-ttu-id="425bd-113">W związku z tym nie jest konieczne ponowne implementowanie procedur sprawdzania poprawności, logiki biznesowej ani konfiguracji zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="425bd-113">Therefore, you don't have to re-implement your validation procedures, business logic, or security configuration.</span></span>
- <span data-ttu-id="425bd-114">Administratorzy IT i deweloperzy mogą łatwo projektować komórkowe obszary robocze za pomocą projektanta obszarów roboczych typu „wskaż i kliknij”, który jest zawarty w kliencie internetowym.</span><span class="sxs-lookup"><span data-stu-id="425bd-114">IT admins or developers can easily design mobile workspaces by using the point-and-click workspace designer that is included with the web client.</span></span>
- <span data-ttu-id="425bd-115">Administratorzy IT i deweloperzy mogą opcjonalnie optymalizować funkcje offline obszarów roboczych za pomocą struktury rozszerzania logiki biznesowej.</span><span class="sxs-lookup"><span data-stu-id="425bd-115">IT admins or developers can optionally optimize the offline capabilities of workspaces by using the Business logic extensibility framework.</span></span> <span data-ttu-id="425bd-116">Ponieważ dane są cały czas przetwarzane, gdy urządzenie jest w trybie offline, scenariusz użytkowania mobilnego pozostaje bogaty funkcjonalnie i płynny, nawet jeśli urządzenia nie mają stałej łączności z siecią.</span><span class="sxs-lookup"><span data-stu-id="425bd-116">Because data continues to be processed while a device is offline, your mobile scenarios remain rich and fluid, even if devices don't have constant network connectivity.</span></span>

## <a name="elements-of-the-mobile-app"></a><span data-ttu-id="425bd-117">Elementy aplikacji mobilnej</span><span class="sxs-lookup"><span data-stu-id="425bd-117">Elements of the mobile app</span></span>
<span data-ttu-id="425bd-118">Nawigacja w aplikacji mobilnej jest podzielona na cztery podstawowe koncepcje: pulpit nawigacyjny, obszary robocze, strony i akcje.</span><span class="sxs-lookup"><span data-stu-id="425bd-118">Navigation in the mobile app consists of four basic concepts: the dashboard, workspaces, pages, and actions.</span></span> 

<span data-ttu-id="425bd-119">[![Koncepcje nawigacyjne w aplikacji mobilnej](./media/mobilephoneapp1-1024x536.png)](./media/mobilephoneapp1.png)</span><span class="sxs-lookup"><span data-stu-id="425bd-119">[![Navigation concepts in the mobile app](./media/mobilephoneapp1-1024x536.png)](./media/mobilephoneapp1.png)</span></span>

1. <span data-ttu-id="425bd-120">Po uruchomieniu aplikacji przechodzisz do **pulpitu nawigacyjnego**.</span><span class="sxs-lookup"><span data-stu-id="425bd-120">When you start the app, you go to the **dashboard**.</span></span>
2. <span data-ttu-id="425bd-121">Na pulpicie nawigacyjnym widać listę **obszarów roboczych**, które zostały opublikowane.</span><span class="sxs-lookup"><span data-stu-id="425bd-121">On the dashboard, you can see a list of **workspaces** that have been published.</span></span>
3. <span data-ttu-id="425bd-122">W każdym obszarze roboczym widać listę **stron** dostępnych dla tego obszaru roboczego.</span><span class="sxs-lookup"><span data-stu-id="425bd-122">In each workspace, you can see a list of **pages** that are available for that workspace.</span></span>
4. <span data-ttu-id="425bd-123">Po przejściu do strony można wykonać kilka czynności.</span><span class="sxs-lookup"><span data-stu-id="425bd-123">After you're on a page, you can perform several actions.</span></span> <span data-ttu-id="425bd-124">Oto kilka przykładów:</span><span class="sxs-lookup"><span data-stu-id="425bd-124">Here are some examples:</span></span>

    - <span data-ttu-id="425bd-125">Wyświetlanie szczegółowych danych.</span><span class="sxs-lookup"><span data-stu-id="425bd-125">View detailed data.</span></span>
    - <span data-ttu-id="425bd-126">Przechodzenie do innych stron zawierających pokrewne dane, takie jak szczegóły jednostek lub wiersze.</span><span class="sxs-lookup"><span data-stu-id="425bd-126">Navigate to other pages for related data, such as entity details or lines.</span></span>
    - <span data-ttu-id="425bd-127">Wyświetlanie listy **akcji** dostępnych dla tej strony.</span><span class="sxs-lookup"><span data-stu-id="425bd-127">See a list of **actions** that are available for that page.</span></span> <span data-ttu-id="425bd-128">Akcje umożliwiają tworzenie nowych i edytowanie istniejących danych.</span><span class="sxs-lookup"><span data-stu-id="425bd-128">Actions let you create or edit existing data.</span></span>

## <a name="implementation-process"></a><span data-ttu-id="425bd-129">Projekt wdrażania</span><span class="sxs-lookup"><span data-stu-id="425bd-129">Implementation process</span></span>
<span data-ttu-id="425bd-130">Na poniższej ilustracji przedstawiono proces wdrażania mobilnych obszarów roboczych dostarczanych przez Microsoft i niestandardowych mobilnych obszarów roboczych.</span><span class="sxs-lookup"><span data-stu-id="425bd-130">The following illustration shows the process for implementing both mobile workspaces that are provided by Microsoft and custom mobile workspaces.</span></span> 

<span data-ttu-id="425bd-131">[![Proces implementacji aplikacji mobilnych](./media/Mobile-implementation-process-5.png)](./media/Mobile-implementation-process-5.png)</span><span class="sxs-lookup"><span data-stu-id="425bd-131">[![Mobile apps implementation process](./media/Mobile-implementation-process-5.png)](./media/Mobile-implementation-process-5.png)</span></span>

<span data-ttu-id="425bd-132">Poniższa tabela zawiera łącza do zasobów, które mogą pomóc we wdrażaniu mobilnych obszarów roboczych dostarczanych przez Microsoft i niestandardowych mobilnych obszarów roboczych.</span><span class="sxs-lookup"><span data-stu-id="425bd-132">The following table includes links to resources that can help you implement both mobile workspaces that are provided by Microsoft and custom mobile workspaces.</span></span> <span data-ttu-id="425bd-133">Numery w pierwszej kolumnie odpowiadają ponumerowanym krokom na poprzedniej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="425bd-133">The numbers in the first column correspond to the numbered steps in the previous illustration.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="425bd-134">Krok</span><span class="sxs-lookup"><span data-stu-id="425bd-134">Step</span></span></th>
<th><span data-ttu-id="425bd-135">Rola</span><span class="sxs-lookup"><span data-stu-id="425bd-135">Role</span></span></th>
<th><span data-ttu-id="425bd-136">Akcja</span><span class="sxs-lookup"><span data-stu-id="425bd-136">Action</span></span></th>
<th><span data-ttu-id="425bd-137">Zasoby pomagające wykonać akcję</span><span class="sxs-lookup"><span data-stu-id="425bd-137">Resources to help you complete the action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="425bd-138">1</span><span class="sxs-lookup"><span data-stu-id="425bd-138">1</span></span></td>
<td><span data-ttu-id="425bd-139">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="425bd-139">System administrator</span></span></td>
<td><span data-ttu-id="425bd-140">Zaimplementuj aplikację Finance and Operations w organizacji.</span><span class="sxs-lookup"><span data-stu-id="425bd-140">Implement the Finance and Operations app in your organization.</span></span></td>
<td><ul><li><span data-ttu-id="425bd-141">Jeśli w organizacji jeszcze nie wdrożono wersji oprogramowania Microsoft Dynamics 365, zobacz <a href="../deployment/deploy-demo-environment.md">Wdrażanie środowiska demonstracyjnego</a>.</span><span class="sxs-lookup"><span data-stu-id="425bd-141">If you haven&#39;t yet deployed a version of Microsoft Dynamics 365, see <a href="../deployment/deploy-demo-environment.md">Deploy a demo environment</a>.</span></span></li><li><span data-ttu-id="425bd-142">Aby wyświetlić listę komórkowych obszarów roboczych, których można używać, zobacz <a href="mobile-workspaces-released.md">Ostatnio wydane mobilne obszary robocze</a>.</span><span class="sxs-lookup"><span data-stu-id="425bd-142">To see a list of mobile workspaces that can be used, see <a href="mobile-workspaces-released.md">Mobile workspaces recently released</a>.</span></span></li></ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="425bd-143">2</span><span class="sxs-lookup"><span data-stu-id="425bd-143">2</span></span></td>
<td><span data-ttu-id="425bd-144">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="425bd-144">System administrator</span></span></td>
<td><span data-ttu-id="425bd-145"><strong>Jeśli używasz Microsoft Dynamics 365 for Operations w wersji 1611:</strong> Pobranie i zainstalowanie aktualizacji KB, które włączą obsługę mobilnych obszarów roboczych dostarczanych przez Microsoft.</span><span class="sxs-lookup"><span data-stu-id="425bd-145"><strong>If you&#39;re using Microsoft Dynamics 365 for Operations version 1611:</strong> Download and install KBs that enable the mobile workspaces that are provided by Microsoft.</span></span></td>
<td><span data-ttu-id="425bd-146">Aby uzyskać więcej informacji, zobacz następujące tematy:</span><span class="sxs-lookup"><span data-stu-id="425bd-146">See the following topics for more information:</span></span>
<ul>

<li><span data-ttu-id="425bd-147"><a href="../../../finance/cost-accounting/cost-controlling-mobile-workspace.md">Mobilny obszar roboczy Kontrola kosztów</a></span><span class="sxs-lookup"><span data-stu-id="425bd-147"><a href="../../../finance/cost-accounting/cost-controlling-mobile-workspace.md">Cost controlling mobile workspaces</a></span></span></li>
<li><span data-ttu-id="425bd-148"><a href="../../../supply-chain/inventory/inventory-on-hand-mobile-workspace.md">Mobilny obszar roboczy Dostępne zapasy</a></span><span class="sxs-lookup"><span data-stu-id="425bd-148"><a href="../../../supply-chain/inventory/inventory-on-hand-mobile-workspace.md">Inventory on-hand mobile workspace</a></span></span></li>
<li><span data-ttu-id="425bd-149"><a href="../../../supply-chain/sales-marketing/sales-orders-mobile-workspace.md">Mobilny obszar roboczy Zamówienia sprzedaży</a></span><span class="sxs-lookup"><span data-stu-id="425bd-149"><a href="../../../supply-chain/sales-marketing/sales-orders-mobile-workspace.md">Sales orders mobile workspaces</a></span></span></li>
<li><span data-ttu-id="425bd-150"><a href="../../../supply-chain/procurement/vendor-collaboration-mobile-workspace.md">Obszar roboczy współpracy z dostawcami za pomocą urządzeń przenośnych</a></span><span class="sxs-lookup"><span data-stu-id="425bd-150"><a href="../../../supply-chain/procurement/vendor-collaboration-mobile-workspace.md">Vendor collaboration mobile workspace</a></span></span></li>
<li><span data-ttu-id="425bd-151"><a href="../../../finance/project-management/project-time-entry-mobile-workspace.md">Mobilny obszar roboczy Wprowadzanie czasu projektu</a></span><span class="sxs-lookup"><span data-stu-id="425bd-151"><a href="../../../finance/project-management/project-time-entry-mobile-workspace.md">Project time entry mobile workspace</a></span></span></li>
<li><span data-ttu-id="425bd-152"><a href="../../../finance/expense-management/expense-management-mobile-workspace.md">Mobilny obszar roboczy Zarządzanie wydatkami</a></span><span class="sxs-lookup"><span data-stu-id="425bd-152"><a href="../../../finance/expense-management/expense-management-mobile-workspace.md">Expense management mobile workspace</a></span></span></li>

</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="425bd-153">3</span><span class="sxs-lookup"><span data-stu-id="425bd-153">3</span></span></td>
<td><span data-ttu-id="425bd-154">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="425bd-154">System administrator</span></span></td>
<td><span data-ttu-id="425bd-155">Opublikowanie mobilnych obszarów roboczych dostarczonych przez Microsoft.</span><span class="sxs-lookup"><span data-stu-id="425bd-155">Publish the mobile workspaces that are provided by Microsoft.</span></span></td>
<td><span data-ttu-id="425bd-156"><a href="publish-mobile-workspace.md">Publikowanie mobilnego obszaru roboczego</a>
</span><span class="sxs-lookup"><span data-stu-id="425bd-156"><a href="publish-mobile-workspace.md">Publish a mobile workspace</a>
</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="425bd-157">4</span><span class="sxs-lookup"><span data-stu-id="425bd-157">4</span></span></td>
<td><span data-ttu-id="425bd-158">Programista lub niezależny dostawca oprogramowania (ISV)</span><span class="sxs-lookup"><span data-stu-id="425bd-158">Developer or independent software vendor (ISV)</span></span></td>
<td><span data-ttu-id="425bd-159">Utworzenie niestandardowych mobilnych obszarów roboczych za pomocą platformy komórkowej.</span><span class="sxs-lookup"><span data-stu-id="425bd-159">Use the mobile platform to create custom mobile workspaces.</span></span></td>
<td><span data-ttu-id="425bd-160"><a href="platform/mobile-platform-home-page.md">Platforma mobilna</a></span><span class="sxs-lookup"><span data-stu-id="425bd-160"><a href="platform/mobile-platform-home-page.md">Mobile platform</a></span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="425bd-161">5</span><span class="sxs-lookup"><span data-stu-id="425bd-161">5</span></span></td>
<td><span data-ttu-id="425bd-162">Niezależny dostawca oprogramowania</span><span class="sxs-lookup"><span data-stu-id="425bd-162">ISV</span></span></td>
<td><span data-ttu-id="425bd-163">Utworzenie wdrażalnego pakietu zawierającego niestandardowe mobilne obszary robocze i przekazanie pakietu do usługi Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="425bd-163">Create a deployable package that contains custom mobile workspaces, and upload the package to Microsoft Dynamics Lifecycle Services (LCS).</span></span></td>
<td><span data-ttu-id="425bd-164"><a href="../deployment/create-apply-deployable-package.md">Tworzenie wdrażalnego pakietu</a></span><span class="sxs-lookup"><span data-stu-id="425bd-164"><a href="../deployment/create-apply-deployable-package.md">Create a deployable package</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="425bd-165">6</span><span class="sxs-lookup"><span data-stu-id="425bd-165">6</span></span></td>
<td><span data-ttu-id="425bd-166">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="425bd-166">System administrator</span></span></td>
<td><span data-ttu-id="425bd-167">Zastosowanie wdrażalnego pakietu zawierającego niestandardowe obszary robocze dostarczonego przez niezależnego dostawcę oprogramowania (ISV).</span><span class="sxs-lookup"><span data-stu-id="425bd-167">Apply the deployable package that contains the custom workspaces that are provided by the independent software vendor (ISV).</span></span></td>
<td><span data-ttu-id="425bd-168"><a href="../deployment/apply-deployable-package-system.md">Stosowanie wdrażalnego pakietu</a></span><span class="sxs-lookup"><span data-stu-id="425bd-168"><a href="../deployment/apply-deployable-package-system.md">Apply a deployable package</a></span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="425bd-169">7</span><span class="sxs-lookup"><span data-stu-id="425bd-169">7</span></span></td>
<td><span data-ttu-id="425bd-170">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="425bd-170">System administrator</span></span></td>
<td><span data-ttu-id="425bd-171">Opublikowanie niestandardowych mobilnych obszarów roboczych dostarczonych przez niezależnego dostawcę oprogramowania.</span><span class="sxs-lookup"><span data-stu-id="425bd-171">Publish the custom mobile workspaces that are provided by the ISV.</span></span></td>
<td><span data-ttu-id="425bd-172"><a href="publish-mobile-workspace.md">Publikowanie mobilnego obszaru roboczego</a></span><span class="sxs-lookup"><span data-stu-id="425bd-172"><a href="publish-mobile-workspace.md">Publish a mobile workspace</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="425bd-173">8</span><span class="sxs-lookup"><span data-stu-id="425bd-173">8</span></span></td>
<td><span data-ttu-id="425bd-174">Użytkownik</span><span class="sxs-lookup"><span data-stu-id="425bd-174">User</span></span></td>
<td><span data-ttu-id="425bd-175">Pobieranie i instalowanie aplikacji mobilnej.</span><span class="sxs-lookup"><span data-stu-id="425bd-175">Download and install the mobile app.</span></span></td>
<td><span data-ttu-id="425bd-176">
<a href="https://go.microsoft.com/fwlink/?linkid=850662">Finance and Operations aplikacja dla systemu Android</a></span><span class="sxs-lookup"><span data-stu-id="425bd-176">
<a href="https://go.microsoft.com/fwlink/?linkid=850662">Finance and Operations app for Android</a></span></span><BR/><span data-ttu-id="425bd-177">
<a href="https://go.microsoft.com/fwlink/?linkid=850663">Finance and Operations aplikacja dla systemu iOS</a></span><span class="sxs-lookup"><span data-stu-id="425bd-177">
<a href="https://go.microsoft.com/fwlink/?linkid=850663">Finance and Operations app for iOS</a></span></span><BR/>
<span data-ttu-id="425bd-178">(system Windows Phone nie jest obsługiwany)</span><span class="sxs-lookup"><span data-stu-id="425bd-178">(Windows Phone unsupported)</span></span>
</td>
</tr>
<tr class="odd">
<td><span data-ttu-id="425bd-179">9</span><span class="sxs-lookup"><span data-stu-id="425bd-179">9</span></span></td>
<td><span data-ttu-id="425bd-180">Użytkownik</span><span class="sxs-lookup"><span data-stu-id="425bd-180">User</span></span></td>
<td><span data-ttu-id="425bd-181">Zalogowanie się do aplikacji mobilnej i jej używanie.</span><span class="sxs-lookup"><span data-stu-id="425bd-181">Sign in, and use the mobile app.</span></span> <span data-ttu-id="425bd-182">Aplikacja zawiera mobilne obszary robocze, które zostały opublikowane przez administratora systemu.</span><span class="sxs-lookup"><span data-stu-id="425bd-182">The app includes the mobile workspaces that have been published by the system administrator.</span></span></td>
<td><span data-ttu-id="425bd-183">Aby wyświetlić listę komórkowych obszarów roboczych dostarczonych przez Microsoft, zobacz <a href="mobile-workspaces-released.md">Ostatnio wydane mobilne obszary robocze</a>.</span><span class="sxs-lookup"><span data-stu-id="425bd-183">To see a list of mobile workspaces that are provided by Microsoft, see <a href="mobile-workspaces-released.md">Mobile workspaces recently released</a>.</span></span>
</td>
</tr>
</tbody>
</table>

## <a name="troubleshooting"></a><span data-ttu-id="425bd-184">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="425bd-184">Troubleshooting</span></span>
[<span data-ttu-id="425bd-185">Zasoby platformy mobilnej</span><span class="sxs-lookup"><span data-stu-id="425bd-185">Mobile platform resources</span></span>](platform/mobile-platform-home-page.md#troubleshooting-the-app)
