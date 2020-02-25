---
title: Dodawanie kodu skryptu do stron witryny w celu obsługi telemetrii
description: W tym temacie opisano sposób dodawania kodu skryptów po stronie klienta do stron witryny w celu obsługi zbierania danych telemetrycznych po stronie klienta.
author: bicyclingfool
manager: annbe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 674d00faf1b30f87a0b0062129e1b9fbff955dd4
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001284"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a><span data-ttu-id="e1a23-103">Dodawanie kodu skryptu do stron witryny w celu obsługi telemetrii</span><span class="sxs-lookup"><span data-stu-id="e1a23-103">Add script code to site pages to support telemetry</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="e1a23-104">W tym temacie opisano sposób dodawania kodu skryptów po stronie klienta do stron witryny w celu obsługi zbierania danych telemetrycznych po stronie klienta.</span><span class="sxs-lookup"><span data-stu-id="e1a23-104">This topic describes how to add client-side script code to your site pages to support the collection of client-side telemetry.</span></span>

## <a name="overview"></a><span data-ttu-id="e1a23-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="e1a23-105">Overview</span></span>

<span data-ttu-id="e1a23-106">Narzędzie Web Analytics jest podstawowym narzędziem, które umożliwia zrozumienie, w jaki sposób klienci współpracują z daną witryną, a następnie podejmujmowanie decyzji, które pozwolą zoptymalizować możliwości konwersji.</span><span class="sxs-lookup"><span data-stu-id="e1a23-106">Web analytics are an essential tool when you want to understand how your customers interact with your site and make decisions that will help optimize the experience for maximum conversion.</span></span> <span data-ttu-id="e1a23-107">Dostępnych jest wiele pakietów analiz sieci Web ułatwiających osiągnięcie tych celów, takich jak Google Analytics, Clicky, Moz Analytics, and KISSMetrics.</span><span class="sxs-lookup"><span data-stu-id="e1a23-107">Many web analytics packages are available to help you achieve these goals, such as Google Analytics, Clicky, Moz Analytics, and KISSMetrics.</span></span> <span data-ttu-id="e1a23-108">Większość pakietów analiz sieci Web wymaga dodania kodu skryptu po stronie klienta w elemencie **\<head\>** kodu HTML na wszystkich stronach witryny.</span><span class="sxs-lookup"><span data-stu-id="e1a23-108">Most web analytics packages require that you add client-side script code in the **\<head\>** element of the HTML for all pages of your site.</span></span>

> [!NOTE]
> <span data-ttu-id="e1a23-109">Instrukcje przedstawione w tym temacie dotyczą również innych niestandardowych funkcji po stronie klienta, które Microsoft Dynamics 365 Commerce nie oferuje w sposób macierzysty.</span><span class="sxs-lookup"><span data-stu-id="e1a23-109">The instructions in this topic also apply to other custom client-side functionality that Microsoft Dynamics 365 Commerce doesn't natively offer.</span></span>

## <a name="create-a-reusable-fragment-for-your-script-code"></a><span data-ttu-id="e1a23-110">Tworzenie fragmentu wielokrotnego użytku dla kodu skryptu</span><span class="sxs-lookup"><span data-stu-id="e1a23-110">Create a reusable fragment for your script code</span></span>

<span data-ttu-id="e1a23-111">Po utworzeniu fragmentu kodu skryptu można go użyć do ponownego użycia na wszystkich stronach w witrynie.</span><span class="sxs-lookup"><span data-stu-id="e1a23-111">After you create a fragment for your script code, it can be reused across all pages on your site.</span></span>

1. <span data-ttu-id="e1a23-112">Umożliwia przejście do **Fragmenty \> Nowy fragment strony**.</span><span class="sxs-lookup"><span data-stu-id="e1a23-112">Go to **Fragments \> New page fragment**.</span></span>
2. <span data-ttu-id="e1a23-113">Wybierz opcję **Skrypt zewnętrzny**, wprowadź nazwę fragmentu, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1a23-113">Select **External Script**, enter a name for the fragment, and then select **OK**.</span></span>
3. <span data-ttu-id="e1a23-114">W hierarchii fragmentu wybierz element podrzędny modułu **iniektora skryptu** dla właśnie utworzonego fragmentu.</span><span class="sxs-lookup"><span data-stu-id="e1a23-114">In the fragment hierarchy, select the **script injector** module child of the fragment that you just created.</span></span>
4. <span data-ttu-id="e1a23-115">W okienku właściwości po prawej stronie, dodaj skrypt klienta i określ inne opcje konfiguracji, tak jak są wymagane.</span><span class="sxs-lookup"><span data-stu-id="e1a23-115">In the property pane on the right, add your client-side script, and set other configuration options as you require.</span></span>

## <a name="add-the-fragment-to-templates"></a><span data-ttu-id="e1a23-116">Dodawanie fragmentu do szablonów</span><span class="sxs-lookup"><span data-stu-id="e1a23-116">Add the fragment to templates</span></span>

1. <span data-ttu-id="e1a23-117">Przejdź do **Szablony** i otwórz szablon stron, do których chcesz dodać kod skryptu.</span><span class="sxs-lookup"><span data-stu-id="e1a23-117">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
2. <span data-ttu-id="e1a23-118">W lewym okienku rozwiń hierarchię szablonów, aby wyświetlić gniazdo **nagłówka HTML**.</span><span class="sxs-lookup"><span data-stu-id="e1a23-118">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
3. <span data-ttu-id="e1a23-119">Wybierz przycisk wielokropka (**...**) dla gniazda **nagłówka HTML**, a następnie wybierz opcję **Dodaj fragment**.</span><span class="sxs-lookup"><span data-stu-id="e1a23-119">Select the ellipsis button (**...**) for the **HTML Head** slot, and then select **Add fragment**.</span></span>
4. <span data-ttu-id="e1a23-120">Umożliwia wybór fragmentu utworzonego dla kodu skryptu.</span><span class="sxs-lookup"><span data-stu-id="e1a23-120">Select the fragment that you created for your script code.</span></span>
5. <span data-ttu-id="e1a23-121">Zapisz szablon i zaewidencjonuj go.</span><span class="sxs-lookup"><span data-stu-id="e1a23-121">Save the template, and check it in.</span></span>

> [!NOTE]
> <span data-ttu-id="e1a23-122">Po zakończeniu należy opublikować fragment i szablon główny.</span><span class="sxs-lookup"><span data-stu-id="e1a23-122">After you've finished, you must publish the fragment and the master template.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="e1a23-123">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="e1a23-123">Additional resources</span></span>

[<span data-ttu-id="e1a23-124">Dodawanie logo</span><span class="sxs-lookup"><span data-stu-id="e1a23-124">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="e1a23-125">Wybór motywu witryny</span><span class="sxs-lookup"><span data-stu-id="e1a23-125">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="e1a23-126">Praca z plikami zastępowania CSS</span><span class="sxs-lookup"><span data-stu-id="e1a23-126">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="e1a23-127">Dodawanie ikony favicon</span><span class="sxs-lookup"><span data-stu-id="e1a23-127">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="e1a23-128">Dodawanie wiadomości powitalnej</span><span class="sxs-lookup"><span data-stu-id="e1a23-128">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="e1a23-129">Dodawanie powiadomienia o prawach autorskich</span><span class="sxs-lookup"><span data-stu-id="e1a23-129">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="e1a23-130">Dodawanie języków do witryny</span><span class="sxs-lookup"><span data-stu-id="e1a23-130">Add languages to your site</span></span>](add-languages-to-site.md)

