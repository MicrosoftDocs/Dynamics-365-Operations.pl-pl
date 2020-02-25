---
title: Dodawanie wiadomości powitalnej
description: W tym temacie opisano sposób dodawania wiadomości powitalnej do witryny sieci Web Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: ca10b01268b5dcd4c6fe448d90cd0ebd65a2673b
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001261"
---
# <a name="add-a-welcome-message"></a><span data-ttu-id="df6c3-103">Dodawanie wiadomości powitalnej</span><span class="sxs-lookup"><span data-stu-id="df6c3-103">Add a welcome message</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="df6c3-104">W tym temacie opisano sposób dodawania wiadomości powitalnej do witryny sieci Web Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="df6c3-104">This topic describes how to add a welcome message to your Microsoft Dynamics 365 Commerce website.</span></span>

## <a name="overview"></a><span data-ttu-id="df6c3-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="df6c3-105">Overview</span></span>

<span data-ttu-id="df6c3-106">Wiadomość powitalna witryny e-Commerce może informować odwiedzających o trwającej sprzedaży, aktualizacjach witryn lub dostępności zbiorów sezonowych</span><span class="sxs-lookup"><span data-stu-id="df6c3-106">A welcome message on your e-Commerce website can inform visitors about ongoing sales, site updates, or availability of seasonal collections.</span></span> <span data-ttu-id="df6c3-107">Wiadomość powitalna jest ustawiana za pomocą modułu alertów.</span><span class="sxs-lookup"><span data-stu-id="df6c3-107">The welcome message is set by using the alert module.</span></span>

<span data-ttu-id="df6c3-108">Moduł alertów powinien zostać dodany do gniazda **komunikatów o błędach/informacjach** w fragmencie nagłówka.</span><span class="sxs-lookup"><span data-stu-id="df6c3-108">The alert module should be added to the **Error/Information messages** slot of the header fragment.</span></span> <span data-ttu-id="df6c3-109">Moduł alertów umożliwia określenie wyświetlanego tekstu, koloru tekstu i wyrównania.</span><span class="sxs-lookup"><span data-stu-id="df6c3-109">The alert module lets you specify the text that is shown, the text color, and the alignment.</span></span> <span data-ttu-id="df6c3-110">Pozwala również określić, czy odwiedzający witrynę mogą odrzucić wiadomość.</span><span class="sxs-lookup"><span data-stu-id="df6c3-110">It also lets you specify whether visitors to the site can dismiss the message.</span></span>

<span data-ttu-id="df6c3-111">Gdy wiadomość powitalna zostanie dodana do udostępnionego fragmentu nagłówka, będzie wyświetlana na każdej stronie korzystającej z szablonu, w którym używany jest ten udostępniony fragment nagłówka.</span><span class="sxs-lookup"><span data-stu-id="df6c3-111">When a welcome message is added to a shared header fragment, it will be shown on every page that uses the template where that shared header fragment is used.</span></span>

<span data-ttu-id="df6c3-112">Aby dodać wiadomość powitalną do witryny, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="df6c3-112">To add a welcome message to your site, follow these steps.</span></span>

1. <span data-ttu-id="df6c3-113">W Dynamics 365 Commerce przejdź do swojej witryny.</span><span class="sxs-lookup"><span data-stu-id="df6c3-113">In Dynamics 365 Commerce, go to your site.</span></span>
1. <span data-ttu-id="df6c3-114">Wybierz **Fragmenty**.</span><span class="sxs-lookup"><span data-stu-id="df6c3-114">Select **Fragments**.</span></span>
1. <span data-ttu-id="df6c3-115">Wybierz fragment nagłówka, do którego ma zostać dodana wiadomość.</span><span class="sxs-lookup"><span data-stu-id="df6c3-115">Select the header fragment to add the message to.</span></span>
1. <span data-ttu-id="df6c3-116">W drzewie konspektu rozwiń **komunikaty o błędach/informacjach**.</span><span class="sxs-lookup"><span data-stu-id="df6c3-116">In the outline tree, expand **Error/Information messages**.</span></span>
1. <span data-ttu-id="df6c3-117">Wybierz moduł alertów.</span><span class="sxs-lookup"><span data-stu-id="df6c3-117">Select the alert module.</span></span>

    <span data-ttu-id="df6c3-118">Jeśli moduł alertów jeszcze nie istnieje, wybierz przycisk wielokropka (**...**) obok **komunikaty o błędach/informacjach**, a następnie wybierz opcję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="df6c3-118">If an alert module doesn't yet exist, select the ellipsis button (**...**) next to **Error/Information messages**, and then select **Add module**.</span></span> <span data-ttu-id="df6c3-119">Wybierz moduł alertów, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="df6c3-119">Select the alert module, and then select **OK**.</span></span>

1. <span data-ttu-id="df6c3-120">W okienku właściwości po prawej stronie na karcie **Dane** wybierz pozycję **Dodaj źródło danych**, a następnie wybierz pozycję **Zawartość**.</span><span class="sxs-lookup"><span data-stu-id="df6c3-120">In the property pane on the right, on the **Data** tab, select **Add Data Source**, and then select **Content**.</span></span>
1. <span data-ttu-id="df6c3-121">W polu **wpisany tekst** wprowadź tekst komunikatu powitalnego.</span><span class="sxs-lookup"><span data-stu-id="df6c3-121">In the **Input Text** field, enter the text of the welcome message.</span></span>
1. <span data-ttu-id="df6c3-122">Zapisz fragment nagłówka, zaewidencjonuj go i opublikuj.</span><span class="sxs-lookup"><span data-stu-id="df6c3-122">Save the header fragment, check it in, and publish it.</span></span>

<span data-ttu-id="df6c3-123">Komunikat powitalny będzie teraz wyświetlany u góry każdej strony witryny, która używa wybranego fragmentu nagłówka.</span><span class="sxs-lookup"><span data-stu-id="df6c3-123">The welcome message will now appear at the top of every site page that uses the selected header fragment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="df6c3-124">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="df6c3-124">Additional resources</span></span>

[<span data-ttu-id="df6c3-125">Dodawanie logo</span><span class="sxs-lookup"><span data-stu-id="df6c3-125">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="df6c3-126">Wybór motywu witryny</span><span class="sxs-lookup"><span data-stu-id="df6c3-126">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="df6c3-127">Praca z plikami zastępowania CSS</span><span class="sxs-lookup"><span data-stu-id="df6c3-127">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="df6c3-128">Dodawanie ikony favicon</span><span class="sxs-lookup"><span data-stu-id="df6c3-128">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="df6c3-129">Dodawanie powiadomienia o prawach autorskich</span><span class="sxs-lookup"><span data-stu-id="df6c3-129">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="df6c3-130">Dodawanie języków do witryny</span><span class="sxs-lookup"><span data-stu-id="df6c3-130">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="df6c3-131">Dodawanie kodu skryptu do stron witryny w celu obsługi telemetrii</span><span class="sxs-lookup"><span data-stu-id="df6c3-131">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

