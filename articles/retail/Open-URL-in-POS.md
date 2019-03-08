---
title: Otwieranie adresu URL w aplikacji punktu sprzedaży
description: Ten temat zawiera omówienie ulepszeń wprowadzonych w produkcie i funkcji wyszukiwania klientów w rozwiązaniu Microsoft Dynamics 365 for Retail.
author: AamirAllaq
manager: AnnBe
ms.date: 01/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.search.scope: Core, Operations, Retail
ms.custom: 141393
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2018-10-30
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: b07406b4e218b45bdde87c4a579814fe0edbc286
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "327097"
---
# <a name="open-url-in-pos"></a><span data-ttu-id="01447-103">Otwieranie adresu URL w aplikacji punktu sprzedaży</span><span class="sxs-lookup"><span data-stu-id="01447-103">Open URL in POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="01447-104">W tym temacie opisano, jak można skonfigurować przycisk w punkcie sprzedaży (POS), aby otworzyć adres URL.</span><span class="sxs-lookup"><span data-stu-id="01447-104">This topic describes how you can configure a button in Retail point of sale (POS) to open a URL.</span></span> <span data-ttu-id="01447-105">Ta funkcja nie wymaga dostosowania kodu i może być skonfigurowana przez dowolną osobę, która nie ma roli dewelopera.</span><span class="sxs-lookup"><span data-stu-id="01447-105">This feature does not require a code customization, and can be configured by someone in a non-developer role.</span></span> <span data-ttu-id="01447-106">Ta funkcja jest dostępna jako część Dynamics 365 for Finance and Operations wersji 8.1.3 (kompilacja 8.1.227.10014) lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="01447-106">This feature is available as part of the Dynamics 365 for Finance and Operations version 8.1.3 release (build 8.1.227.10014) and later.</span></span> 

<span data-ttu-id="01447-107">Ta funkcja umożliwia konfigurację przycisku w punkcie sprzedaży, otwieranie adresu URL przy użyciu projektanta siatki przycisków.</span><span class="sxs-lookup"><span data-stu-id="01447-107">This feature allows configuration of a button in POS, using the button grid designer to open a URL.</span></span> <span data-ttu-id="01447-108">Obecnie jest to obsługiwane w następujących konfiguracjach:</span><span class="sxs-lookup"><span data-stu-id="01447-108">Currently, this is supported in the following configurations:</span></span>

- <span data-ttu-id="01447-109">Otwórz w nowym oknie.</span><span class="sxs-lookup"><span data-stu-id="01447-109">Open in new window.</span></span>
- <span data-ttu-id="01447-110">Otwórz w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="01447-110">Open within POS.</span></span>
- <span data-ttu-id="01447-111">Otwórz aplikację macierzystą.</span><span class="sxs-lookup"><span data-stu-id="01447-111">Open a native app.</span></span>

## <a name="open-in-new-window"></a><span data-ttu-id="01447-112">Otwórz w nowym oknie</span><span class="sxs-lookup"><span data-stu-id="01447-112">Open in new window</span></span>

<span data-ttu-id="01447-113">Ta konfiguracja określa, czy należy otworzyć adres URL w nowym oknie lub w ramach aplikacji.</span><span class="sxs-lookup"><span data-stu-id="01447-113">This configuration defines whether to open the URL in a new window or within the app.</span></span> <span data-ttu-id="01447-114">W przypadku skonfigurowania, aby otworzyć adres URL sieci web w aplikacji, panel nawigacji z boku i górny pasek punktu sprzedaży są widoczne i dostępne do interakcji z użytkownikiem.</span><span class="sxs-lookup"><span data-stu-id="01447-114">When configured to open a web URL within the app, the side navigation panel and top bar of POS are visible and available for user interaction.</span></span> <span data-ttu-id="01447-115">W przypadku konfiguracji otwierania w nowym oknie adres URL zostanie otwarty w nowym oknie aplikacji w Modern POS for Windows i na nowej karcie przeglądarki we wszystkich innych klientach punktu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="01447-115">When configured to open in a new window, the URL will open in a new app window on Modern POS for Windows, and in a new browser tab in all other POS clients.</span></span> <span data-ttu-id="01447-116">Aby włączyć tę opcję, należy skonfigurować adres URL z zaznaczoną opcją **Otwórz w nowym oknie**.</span><span class="sxs-lookup"><span data-stu-id="01447-116">To enable this, you must configure the URL with the **Open in new window** option selected.</span></span>

## <a name="open-within-pos"></a><span data-ttu-id="01447-117">Otwórz w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="01447-117">Open within POS</span></span>

<span data-ttu-id="01447-118">Otwieranie adresu URL sieci web w punkcie sprzedaży jest obecnie obsługiwane tylko w systemie Windows Modern POS.</span><span class="sxs-lookup"><span data-stu-id="01447-118">Opening a web URL within POS is currently only supported for Modern POS on Windows.</span></span> <span data-ttu-id="01447-119">Trwa opracowywanie tej funkcji dla innych klientów; będzie dostępna później.</span><span class="sxs-lookup"><span data-stu-id="01447-119">On other clients, this capability is under development and planned for release in future updates.</span></span> <span data-ttu-id="01447-120">Aby włączyć tę opcję, należy skonfigurować adres URL z niezaznaczoną opcją **Otwórz w nowym oknie**.</span><span class="sxs-lookup"><span data-stu-id="01447-120">To enable this, you must configure the URL with the **Open in new window** option not selected.</span></span>

## <a name="open-a-native-app"></a><span data-ttu-id="01447-121">Otwórz aplikację macierzystą.</span><span class="sxs-lookup"><span data-stu-id="01447-121">Open a native app</span></span>

<span data-ttu-id="01447-122">Ta funkcja umożliwia określenie URL innych niż sieci web, aby otworzyć aplikację macierzystą.</span><span class="sxs-lookup"><span data-stu-id="01447-122">This feature also allows you to specify non-web URLs to open a native app.</span></span> <span data-ttu-id="01447-123">Na przykład można określić protokoły, takie jak MailTo, SIP, IM lub MSTEAMS, które następnie są obsługiwane przez odpowiednie aplikacje natywne na urządzeniu hostującym.</span><span class="sxs-lookup"><span data-stu-id="01447-123">For example, you can specify URL protocols such as MailTo, SIP, IM, or MSTEAMS, which can then be handled by respective native apps on the host device.</span></span> <span data-ttu-id="01447-124">Aby włączyć tę opcję, należy skonfigurować adres URL z zaznaczoną opcją **Otwórz w nowym oknie**.</span><span class="sxs-lookup"><span data-stu-id="01447-124">To enable this, you must configure the URL with the **Open in new window** option selected.</span></span>

- <span data-ttu-id="01447-125">Na komputerach z systemem Windows, zobacz [eksport lub import domyślnych skojarzeń aplikacji](https://docs.microsoft.com/windows-hardware/manufacture/desktop/export-or-import-default-application-associations), aby ustawić domyślne powiązania protokołu, jeśli konfigurujesz komputer przy użyciu Deployment Image Servicing and Management (DISM).</span><span class="sxs-lookup"><span data-stu-id="01447-125">For Windows computers, see [Export or Import Default Application Associations](https://docs.microsoft.com/windows-hardware/manufacture/desktop/export-or-import-default-application-associations) to set the default protocol associations if you are setting up your computer using Deployment Image Servicing and Management (DISM).</span></span>
- <span data-ttu-id="01447-126">Jeśli używasz MDM, takich jak Intune do zarządzania na komputerach z systemem Windows, zobacz [CSP zasad - ApplicationDefaults](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults).</span><span class="sxs-lookup"><span data-stu-id="01447-126">If you are using MDM, such as Intune to manage your Windows computers, see [Policy CSP - ApplicationDefaults](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults).</span></span>
- <span data-ttu-id="01447-127">Jeśli jesteś programistą i tworzysz niestandardową witrynę sieci Web, zobacz [uruchamianie aplikacji domyślnej dla identyfikatora URI](https://docs.microsoft.com/windows/uwp/launch-resume/launch-default-app).</span><span class="sxs-lookup"><span data-stu-id="01447-127">If you are a developer building a custom website, see [Launch the default app for a URI](https://docs.microsoft.com/windows/uwp/launch-resume/launch-default-app).</span></span>

## <a name="open-a-native-app-seamlessly"></a><span data-ttu-id="01447-128">Otwórz aplikację macierzystą bez problemów.</span><span class="sxs-lookup"><span data-stu-id="01447-128">Open a native app seamlessly</span></span>

<span data-ttu-id="01447-129">Windows, iOS i Android także umożliwiają łatwiejsze otwarcie aplikacji na podstawie powiązania protokołu aplikacji.</span><span class="sxs-lookup"><span data-stu-id="01447-129">Windows, iOS, and Android also allow opening of apps more seamlessly, based on app protocol association.</span></span> <span data-ttu-id="01447-130">Jeśli aplikacji nie jest jeszcze skonfigurowana do obsługi otwarcia w przeglądarce sieci web, może być konieczne ustawienie tej opcji.</span><span class="sxs-lookup"><span data-stu-id="01447-130">If your app is not already configured to handle opening from a web browser, you may need a developer to configure this.</span></span>

- <span data-ttu-id="01447-131">Dla systemu Windows, zobacz [Włączanie aplikacji dla witryny sieci Web przy użyciu programów obsługi URI](https://docs.microsoft.com/windows/uwp/launch-resume/web-to-app-linking).</span><span class="sxs-lookup"><span data-stu-id="01447-131">For Windows, see [Enable apps for websites using app URI handlers](https://docs.microsoft.com/windows/uwp/launch-resume/web-to-app-linking).</span></span>
- <span data-ttu-id="01447-132">W przypadku iOS zobacz [uniwersalne łącza dla deweloperów](https://developer.apple.com/ios/universal-links/).</span><span class="sxs-lookup"><span data-stu-id="01447-132">For iOS, see [Universal Links for Developers](https://developer.apple.com/ios/universal-links/).</span></span>
- <span data-ttu-id="01447-133">W przypadku systemu Android zobacz [obsługa łączy aplikacji Android](https://developer.android.com/training/app-links/).</span><span class="sxs-lookup"><span data-stu-id="01447-133">For Android, see [Handling Android App Links](https://developer.android.com/training/app-links/).</span></span>

| <span data-ttu-id="01447-134">Klient</span><span class="sxs-lookup"><span data-stu-id="01447-134">Client</span></span>                | <span data-ttu-id="01447-135">Otwórz w nowym oknie</span><span class="sxs-lookup"><span data-stu-id="01447-135">Open in new window</span></span> | <span data-ttu-id="01447-136">Otwórz aplikację macierzystą</span><span class="sxs-lookup"><span data-stu-id="01447-136">Open native app</span></span> | <span data-ttu-id="01447-137">Otwórz w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="01447-137">Open within POS</span></span> | <span data-ttu-id="01447-138">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="01447-138">Details</span></span>                           |
|-----------------------|--------------------|-----------------|-----------------|-----------------------------------|
| <span data-ttu-id="01447-139">Nowoczesny punkt sprzedaży w Windows</span><span class="sxs-lookup"><span data-stu-id="01447-139">Modern POS on Windows</span></span> | <span data-ttu-id="01447-140">✓\*</span><span class="sxs-lookup"><span data-stu-id="01447-140">✓\*</span></span>                | <span data-ttu-id="01447-141">✓</span><span class="sxs-lookup"><span data-stu-id="01447-141">✓</span></span>               | <span data-ttu-id="01447-142">✓</span><span class="sxs-lookup"><span data-stu-id="01447-142">✓</span></span>              | <span data-ttu-id="01447-143">\* Otwiera w nowym oknie nowoczesnego punktu sprzedaży</span><span class="sxs-lookup"><span data-stu-id="01447-143">\* Opens in new Modern POS window</span></span> |
| <span data-ttu-id="01447-144">Cloud POS</span><span class="sxs-lookup"><span data-stu-id="01447-144">Cloud POS</span></span>             | <span data-ttu-id="01447-145">✓\*</span><span class="sxs-lookup"><span data-stu-id="01447-145">✓\*</span></span>                | <span data-ttu-id="01447-146">✓</span><span class="sxs-lookup"><span data-stu-id="01447-146">✓</span></span>               | <span data-ttu-id="01447-147">X</span><span class="sxs-lookup"><span data-stu-id="01447-147">X</span></span>              | <span data-ttu-id="01447-148">\* Otwiera się na nowej karcie przeglądarki</span><span class="sxs-lookup"><span data-stu-id="01447-148">\* Opens in new browser tab</span></span>        |
| <span data-ttu-id="01447-149">Nowoczesny punkt sprzedaży w iOS</span><span class="sxs-lookup"><span data-stu-id="01447-149">Modern POS on iOS</span></span>     | <span data-ttu-id="01447-150">✓\*</span><span class="sxs-lookup"><span data-stu-id="01447-150">✓\*</span></span>                | <span data-ttu-id="01447-151">✓</span><span class="sxs-lookup"><span data-stu-id="01447-151">✓</span></span>               | <span data-ttu-id="01447-152">X</span><span class="sxs-lookup"><span data-stu-id="01447-152">X</span></span>              | <span data-ttu-id="01447-153">\* Otwiera się na nowej karcie przeglądarki</span><span class="sxs-lookup"><span data-stu-id="01447-153">\* Opens in new browser tab</span></span>        |
| <span data-ttu-id="01447-154">Modern POS w systemie Android</span><span class="sxs-lookup"><span data-stu-id="01447-154">Modern POS on Android</span></span> | <span data-ttu-id="01447-155">✓\*</span><span class="sxs-lookup"><span data-stu-id="01447-155">✓\*</span></span>                | <span data-ttu-id="01447-156">✓</span><span class="sxs-lookup"><span data-stu-id="01447-156">✓</span></span>               | <span data-ttu-id="01447-157">X</span><span class="sxs-lookup"><span data-stu-id="01447-157">X</span></span>              | <span data-ttu-id="01447-158">\* Otwiera się na nowej karcie przeglądarki</span><span class="sxs-lookup"><span data-stu-id="01447-158">\* Opens in new browser tab</span></span>        |

## <a name="before-you-begin"></a><span data-ttu-id="01447-159">Przed rozpoczęciem</span><span class="sxs-lookup"><span data-stu-id="01447-159">Before you begin</span></span>

<span data-ttu-id="01447-160">Przed rozpoczęciem zobacz jak skonfigurować [układy ekranu dla punktu sprzedaży (POS)](pos-screen-layouts.md).</span><span class="sxs-lookup"><span data-stu-id="01447-160">Before you begin, review how to configure [Screen layouts for the point of sale (POS)](pos-screen-layouts.md).</span></span>

## <a name="open-url-in-pos"></a><span data-ttu-id="01447-161">Otwieranie adresu URL w aplikacji punktu sprzedaży</span><span class="sxs-lookup"><span data-stu-id="01447-161">Open URL in POS</span></span>

<span data-ttu-id="01447-162">Aby skonfigurować adres URL, który można otworzyć w punkcie sprzedaży, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="01447-162">To configure a URL to be opened in POS, perform the following steps.</span></span>

1. <span data-ttu-id="01447-163">W centrali przejdź do **Sprzedaż detaliczna \> Konfiguracja kanału \> Konfiguracja punktu sprzedaży \> Punkt sprzedaży \> Układy ekranu**.</span><span class="sxs-lookup"><span data-stu-id="01447-163">In head office, go to **Retail \> Channel Setup \> POS Setup \> POS \> Screen Layouts**.</span></span>
2. <span data-ttu-id="01447-164">Wybierz **Siatki przycisków \> Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="01447-164">Select **Button Grids \> Designer**.</span></span>
3. <span data-ttu-id="01447-165">Utwórz nowy przycisk.</span><span class="sxs-lookup"><span data-stu-id="01447-165">Create a new button.</span></span>
4. <span data-ttu-id="01447-166">Wybierz Właściwości **przycisku**.</span><span class="sxs-lookup"><span data-stu-id="01447-166">Select **Button** properties.</span></span>
5. <span data-ttu-id="01447-167">Wybierz akcję **Otwórz URL**.</span><span class="sxs-lookup"><span data-stu-id="01447-167">Select **Open URL** as the action.</span></span>
6. <span data-ttu-id="01447-168">Wprowadź URL, którego chcesz użyć.</span><span class="sxs-lookup"><span data-stu-id="01447-168">Enter the URL that you want to use.</span></span>
7. <span data-ttu-id="01447-169">Skonfiguruj, czy należy otworzyć adres URL w nowym oknie.</span><span class="sxs-lookup"><span data-stu-id="01447-169">Configure whether to open the URL in a new window.</span></span>
