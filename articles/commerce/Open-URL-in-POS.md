---
title: Otwieranie adresu URL w aplikacji punktu sprzedaży
description: Ten temat zawiera omówienie ulepszeń wprowadzonych w produkcie i funkcji wyszukiwania klientów w rozwiązaniu Dynamics 365 Commerce.
author: AamirAllaq
manager: AnnBe
ms.date: 01/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: 141393
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2018-10-30
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: e4ccb8e03d63a7bd1ab2d118d86633a8c6324d43
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4965459"
---
# <a name="open-url-in-pos"></a><span data-ttu-id="a0a8f-103">Otwieranie adresu URL w aplikacji punktu sprzedaży</span><span class="sxs-lookup"><span data-stu-id="a0a8f-103">Open URL in POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a0a8f-104">W tym temacie opisano, jak można skonfigurować przycisk w punkcie sprzedaży (POS), aby otworzyć adres URL.</span><span class="sxs-lookup"><span data-stu-id="a0a8f-104">This topic describes how you can configure a button in Retail point of sale (POS) to open a URL.</span></span> <span data-ttu-id="a0a8f-105">Ta funkcja nie wymaga dostosowania kodu i może być skonfigurowana przez dowolną osobę, która nie ma roli dewelopera.</span><span class="sxs-lookup"><span data-stu-id="a0a8f-105">This feature does not require a code customization, and can be configured by someone in a non-developer role.</span></span> 

<span data-ttu-id="a0a8f-106">Ta funkcja umożliwia konfigurację przycisku w punkcie sprzedaży, otwieranie adresu URL przy użyciu projektanta siatki przycisków.</span><span class="sxs-lookup"><span data-stu-id="a0a8f-106">This feature allows configuration of a button in POS, using the button grid designer to open a URL.</span></span> <span data-ttu-id="a0a8f-107">Obecnie jest to obsługiwane w następujących konfiguracjach:</span><span class="sxs-lookup"><span data-stu-id="a0a8f-107">Currently, this is supported in the following configurations:</span></span>

- <span data-ttu-id="a0a8f-108">Otwórz w nowym oknie.</span><span class="sxs-lookup"><span data-stu-id="a0a8f-108">Open in new window.</span></span>
- <span data-ttu-id="a0a8f-109">Otwórz w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="a0a8f-109">Open within POS.</span></span>
- <span data-ttu-id="a0a8f-110">Otwórz aplikację macierzystą.</span><span class="sxs-lookup"><span data-stu-id="a0a8f-110">Open a native app.</span></span>

## <a name="open-in-new-window"></a><span data-ttu-id="a0a8f-111">Otwórz w nowym oknie</span><span class="sxs-lookup"><span data-stu-id="a0a8f-111">Open in new window</span></span>

<span data-ttu-id="a0a8f-112">Ta konfiguracja określa, czy należy otworzyć adres URL w nowym oknie lub w ramach aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a0a8f-112">This configuration defines whether to open the URL in a new window or within the app.</span></span> <span data-ttu-id="a0a8f-113">W przypadku skonfigurowania, aby otworzyć adres URL sieci web w aplikacji, panel nawigacji z boku i górny pasek punktu sprzedaży są widoczne i dostępne do interakcji z użytkownikiem.</span><span class="sxs-lookup"><span data-stu-id="a0a8f-113">When configured to open a web URL within the app, the side navigation panel and top bar of POS are visible and available for user interaction.</span></span> <span data-ttu-id="a0a8f-114">W przypadku konfiguracji otwierania w nowym oknie adres URL zostanie otwarty w nowym oknie aplikacji w Modern POS for Windows i na nowej karcie przeglądarki we wszystkich innych klientach punktu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="a0a8f-114">When configured to open in a new window, the URL will open in a new app window on Modern POS for Windows, and in a new browser tab in all other POS clients.</span></span> <span data-ttu-id="a0a8f-115">Aby włączyć tę opcję, należy skonfigurować adres URL z zaznaczoną opcją **Otwórz w nowym oknie**.</span><span class="sxs-lookup"><span data-stu-id="a0a8f-115">To enable this, you must configure the URL with the **Open in new window** option selected.</span></span>

## <a name="open-within-pos"></a><span data-ttu-id="a0a8f-116">Otwórz w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="a0a8f-116">Open within POS</span></span>

<span data-ttu-id="a0a8f-117">Otwieranie adresu URL sieci web w punkcie sprzedaży jest obecnie obsługiwane tylko w systemie Windows Modern POS.</span><span class="sxs-lookup"><span data-stu-id="a0a8f-117">Opening a web URL within POS is currently only supported for Modern POS on Windows.</span></span> <span data-ttu-id="a0a8f-118">Trwa opracowywanie tej funkcji dla innych klientów; będzie dostępna później.</span><span class="sxs-lookup"><span data-stu-id="a0a8f-118">On other clients, this capability is under development and planned for release in future updates.</span></span> <span data-ttu-id="a0a8f-119">Aby włączyć tę opcję, należy skonfigurować adres URL z niezaznaczoną opcją **Otwórz w nowym oknie**.</span><span class="sxs-lookup"><span data-stu-id="a0a8f-119">To enable this, you must configure the URL with the **Open in new window** option not selected.</span></span>

## <a name="open-a-native-app"></a><span data-ttu-id="a0a8f-120">Otwórz aplikację macierzystą.</span><span class="sxs-lookup"><span data-stu-id="a0a8f-120">Open a native app</span></span>

<span data-ttu-id="a0a8f-121">Ta funkcja umożliwia określenie URL innych niż sieci web, aby otworzyć aplikację macierzystą.</span><span class="sxs-lookup"><span data-stu-id="a0a8f-121">This feature also allows you to specify non-web URLs to open a native app.</span></span> <span data-ttu-id="a0a8f-122">Na przykład można określić protokoły, takie jak MailTo, SIP, IM lub MSTEAMS, które następnie są obsługiwane przez odpowiednie aplikacje natywne na urządzeniu hostującym.</span><span class="sxs-lookup"><span data-stu-id="a0a8f-122">For example, you can specify URL protocols such as MailTo, SIP, IM, or MSTEAMS, which can then be handled by respective native apps on the host device.</span></span> <span data-ttu-id="a0a8f-123">Aby włączyć tę opcję, należy skonfigurować adres URL z zaznaczoną opcją **Otwórz w nowym oknie**.</span><span class="sxs-lookup"><span data-stu-id="a0a8f-123">To enable this, you must configure the URL with the **Open in new window** option selected.</span></span>

- <span data-ttu-id="a0a8f-124">Na komputerach z systemem Windows, zobacz [eksport lub import domyślnych skojarzeń aplikacji](https://docs.microsoft.com/windows-hardware/manufacture/desktop/export-or-import-default-application-associations), aby ustawić domyślne powiązania protokołu, jeśli konfigurujesz komputer przy użyciu Deployment Image Servicing and Management (DISM).</span><span class="sxs-lookup"><span data-stu-id="a0a8f-124">For Windows computers, see [Export or Import Default Application Associations](https://docs.microsoft.com/windows-hardware/manufacture/desktop/export-or-import-default-application-associations) to set the default protocol associations if you are setting up your computer using Deployment Image Servicing and Management (DISM).</span></span>
- <span data-ttu-id="a0a8f-125">Jeśli używasz MDM, takich jak Intune do zarządzania na komputerach z systemem Windows, zobacz [CSP zasad - ApplicationDefaults](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults).</span><span class="sxs-lookup"><span data-stu-id="a0a8f-125">If you are using MDM, such as Intune to manage your Windows computers, see [Policy CSP - ApplicationDefaults](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults).</span></span>
- <span data-ttu-id="a0a8f-126">Jeśli jesteś programistą i tworzysz niestandardową witrynę sieci Web, zobacz [uruchamianie aplikacji domyślnej dla identyfikatora URI](https://docs.microsoft.com/windows/uwp/launch-resume/launch-default-app).</span><span class="sxs-lookup"><span data-stu-id="a0a8f-126">If you are a developer building a custom website, see [Launch the default app for a URI](https://docs.microsoft.com/windows/uwp/launch-resume/launch-default-app).</span></span>

## <a name="open-a-native-app-seamlessly"></a><span data-ttu-id="a0a8f-127">Otwórz aplikację macierzystą bez problemów.</span><span class="sxs-lookup"><span data-stu-id="a0a8f-127">Open a native app seamlessly</span></span>

<span data-ttu-id="a0a8f-128">Windows, iOS i Android także umożliwiają łatwiejsze otwarcie aplikacji na podstawie powiązania protokołu aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a0a8f-128">Windows, iOS, and Android also allow opening of apps more seamlessly, based on app protocol association.</span></span> <span data-ttu-id="a0a8f-129">Jeśli aplikacji nie jest jeszcze skonfigurowana do obsługi otwarcia w przeglądarce sieci web, może być konieczne ustawienie tej opcji.</span><span class="sxs-lookup"><span data-stu-id="a0a8f-129">If your app is not already configured to handle opening from a web browser, you may need a developer to configure this.</span></span>

- <span data-ttu-id="a0a8f-130">Dla systemu Windows, zobacz [Włączanie aplikacji dla witryny sieci Web przy użyciu programów obsługi URI](https://docs.microsoft.com/windows/uwp/launch-resume/web-to-app-linking).</span><span class="sxs-lookup"><span data-stu-id="a0a8f-130">For Windows, see [Enable apps for websites using app URI handlers](https://docs.microsoft.com/windows/uwp/launch-resume/web-to-app-linking).</span></span>
- <span data-ttu-id="a0a8f-131">W przypadku iOS zobacz [uniwersalne łącza dla deweloperów](https://developer.apple.com/ios/universal-links/).</span><span class="sxs-lookup"><span data-stu-id="a0a8f-131">For iOS, see [Universal Links for Developers](https://developer.apple.com/ios/universal-links/).</span></span>
- <span data-ttu-id="a0a8f-132">W przypadku systemu Android zobacz [obsługa łączy aplikacji Android](https://developer.android.com/training/app-links/).</span><span class="sxs-lookup"><span data-stu-id="a0a8f-132">For Android, see [Handling Android App Links](https://developer.android.com/training/app-links/).</span></span>

| <span data-ttu-id="a0a8f-133">Klient</span><span class="sxs-lookup"><span data-stu-id="a0a8f-133">Client</span></span>                | <span data-ttu-id="a0a8f-134">Otwórz w nowym oknie</span><span class="sxs-lookup"><span data-stu-id="a0a8f-134">Open in new window</span></span> | <span data-ttu-id="a0a8f-135">Otwórz aplikację macierzystą</span><span class="sxs-lookup"><span data-stu-id="a0a8f-135">Open native app</span></span> | <span data-ttu-id="a0a8f-136">Otwórz w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="a0a8f-136">Open within POS</span></span> | <span data-ttu-id="a0a8f-137">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="a0a8f-137">Details</span></span>                           |
|-----------------------|--------------------|-----------------|-----------------|-----------------------------------|
| <span data-ttu-id="a0a8f-138">Nowoczesny punkt sprzedaży w Windows</span><span class="sxs-lookup"><span data-stu-id="a0a8f-138">Modern POS on Windows</span></span> | <span data-ttu-id="a0a8f-139">✓\*</span><span class="sxs-lookup"><span data-stu-id="a0a8f-139">✓\*</span></span>                | <span data-ttu-id="a0a8f-140">✓</span><span class="sxs-lookup"><span data-stu-id="a0a8f-140">✓</span></span>               | <span data-ttu-id="a0a8f-141">✓</span><span class="sxs-lookup"><span data-stu-id="a0a8f-141">✓</span></span>              | <span data-ttu-id="a0a8f-142">\* Otwiera w nowym oknie nowoczesnego punktu sprzedaży</span><span class="sxs-lookup"><span data-stu-id="a0a8f-142">\* Opens in new Modern POS window</span></span> |
| <span data-ttu-id="a0a8f-143">Cloud POS</span><span class="sxs-lookup"><span data-stu-id="a0a8f-143">Cloud POS</span></span>             | <span data-ttu-id="a0a8f-144">✓\*</span><span class="sxs-lookup"><span data-stu-id="a0a8f-144">✓\*</span></span>                | <span data-ttu-id="a0a8f-145">✓</span><span class="sxs-lookup"><span data-stu-id="a0a8f-145">✓</span></span>               | <span data-ttu-id="a0a8f-146">X</span><span class="sxs-lookup"><span data-stu-id="a0a8f-146">X</span></span>              | <span data-ttu-id="a0a8f-147">\* Otwiera się na nowej karcie przeglądarki</span><span class="sxs-lookup"><span data-stu-id="a0a8f-147">\* Opens in new browser tab</span></span>        |
| <span data-ttu-id="a0a8f-148">Nowoczesny punkt sprzedaży w iOS</span><span class="sxs-lookup"><span data-stu-id="a0a8f-148">Modern POS on iOS</span></span>     | <span data-ttu-id="a0a8f-149">✓\*</span><span class="sxs-lookup"><span data-stu-id="a0a8f-149">✓\*</span></span>                | <span data-ttu-id="a0a8f-150">✓</span><span class="sxs-lookup"><span data-stu-id="a0a8f-150">✓</span></span>               | <span data-ttu-id="a0a8f-151">X</span><span class="sxs-lookup"><span data-stu-id="a0a8f-151">X</span></span>              | <span data-ttu-id="a0a8f-152">\* Otwiera się na nowej karcie przeglądarki</span><span class="sxs-lookup"><span data-stu-id="a0a8f-152">\* Opens in new browser tab</span></span>        |
| <span data-ttu-id="a0a8f-153">Modern POS w systemie Android</span><span class="sxs-lookup"><span data-stu-id="a0a8f-153">Modern POS on Android</span></span> | <span data-ttu-id="a0a8f-154">✓\*</span><span class="sxs-lookup"><span data-stu-id="a0a8f-154">✓\*</span></span>                | <span data-ttu-id="a0a8f-155">✓</span><span class="sxs-lookup"><span data-stu-id="a0a8f-155">✓</span></span>               | <span data-ttu-id="a0a8f-156">X</span><span class="sxs-lookup"><span data-stu-id="a0a8f-156">X</span></span>              | <span data-ttu-id="a0a8f-157">\* Otwiera się na nowej karcie przeglądarki</span><span class="sxs-lookup"><span data-stu-id="a0a8f-157">\* Opens in new browser tab</span></span>        |

## <a name="before-you-begin"></a><span data-ttu-id="a0a8f-158">Przed rozpoczęciem</span><span class="sxs-lookup"><span data-stu-id="a0a8f-158">Before you begin</span></span>

<span data-ttu-id="a0a8f-159">Przed rozpoczęciem zobacz jak skonfigurować [układy ekranu dla punktu sprzedaży (POS)](pos-screen-layouts.md).</span><span class="sxs-lookup"><span data-stu-id="a0a8f-159">Before you begin, review how to configure [Screen layouts for the point of sale (POS)](pos-screen-layouts.md).</span></span>

## <a name="open-url-in-pos"></a><span data-ttu-id="a0a8f-160">Otwieranie adresu URL w aplikacji punktu sprzedaży</span><span class="sxs-lookup"><span data-stu-id="a0a8f-160">Open URL in POS</span></span>

<span data-ttu-id="a0a8f-161">Aby skonfigurować adres URL, który można otworzyć w punkcie sprzedaży, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a0a8f-161">To configure a URL to be opened in POS, perform the following steps.</span></span>

1. <span data-ttu-id="a0a8f-162">W centrali przejdź do **Sprzedaż detaliczna i inna \> Konfiguracja kanału \> Konfiguracja punktu sprzedaży \> Punkt sprzedaży \> Układy ekranu**.</span><span class="sxs-lookup"><span data-stu-id="a0a8f-162">In head office, go to **Retail and Commerce \> Channel Setup \> POS Setup \> POS \> Screen Layouts**.</span></span>
2. <span data-ttu-id="a0a8f-163">Wybierz **Siatki przycisków \> Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="a0a8f-163">Select **Button Grids \> Designer**.</span></span>
3. <span data-ttu-id="a0a8f-164">Utwórz nowy przycisk.</span><span class="sxs-lookup"><span data-stu-id="a0a8f-164">Create a new button.</span></span>
4. <span data-ttu-id="a0a8f-165">Wybierz Właściwości **przycisku**.</span><span class="sxs-lookup"><span data-stu-id="a0a8f-165">Select **Button** properties.</span></span>
5. <span data-ttu-id="a0a8f-166">Wybierz akcję **Otwórz URL**.</span><span class="sxs-lookup"><span data-stu-id="a0a8f-166">Select **Open URL** as the action.</span></span>
6. <span data-ttu-id="a0a8f-167">Wprowadź URL, którego chcesz użyć.</span><span class="sxs-lookup"><span data-stu-id="a0a8f-167">Enter the URL that you want to use.</span></span>
7. <span data-ttu-id="a0a8f-168">Skonfiguruj, czy należy otworzyć adres URL w nowym oknie.</span><span class="sxs-lookup"><span data-stu-id="a0a8f-168">Configure whether to open the URL in a new window.</span></span>
