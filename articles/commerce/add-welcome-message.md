---
title: Dodawanie wiadomości powitalnej
description: W tym temacie opisano sposób dodawania wiadomości powitalnej do witryny sieci Web Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3e61f43eca7d1343d020e1c01b5b1140f07b63c6
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797390"
---
# <a name="add-a-welcome-message"></a><span data-ttu-id="c4187-103">Dodawanie wiadomości powitalnej</span><span class="sxs-lookup"><span data-stu-id="c4187-103">Add a welcome message</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c4187-104">W tym temacie opisano sposób dodawania wiadomości powitalnej do witryny sieci Web Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c4187-104">This topic describes how to add a welcome message to your Microsoft Dynamics 365 Commerce website.</span></span>

<span data-ttu-id="c4187-105">Wiadomość powitalna witryny e-Commerce może informować odwiedzających o trwającej sprzedaży, aktualizacjach witryn lub dostępności zbiorów sezonowych</span><span class="sxs-lookup"><span data-stu-id="c4187-105">A welcome message on your e-Commerce website can inform visitors about ongoing sales, site updates, or availability of seasonal collections.</span></span> <span data-ttu-id="c4187-106">Wiadomość powitalna jest ustawiana za pomocą modułu alertów.</span><span class="sxs-lookup"><span data-stu-id="c4187-106">The welcome message is set by using the alert module.</span></span>

<span data-ttu-id="c4187-107">Moduł alertów powinien zostać dodany do gniazda **komunikatów o błędach/informacjach** w fragmencie nagłówka.</span><span class="sxs-lookup"><span data-stu-id="c4187-107">The alert module should be added to the **Error/Information messages** slot of the header fragment.</span></span> <span data-ttu-id="c4187-108">Moduł alertów umożliwia określenie wyświetlanego tekstu, koloru tekstu i wyrównania.</span><span class="sxs-lookup"><span data-stu-id="c4187-108">The alert module lets you specify the text that is shown, the text color, and the alignment.</span></span> <span data-ttu-id="c4187-109">Pozwala również określić, czy odwiedzający witrynę mogą odrzucić wiadomość.</span><span class="sxs-lookup"><span data-stu-id="c4187-109">It also lets you specify whether visitors to the site can dismiss the message.</span></span>

<span data-ttu-id="c4187-110">Gdy wiadomość powitalna zostanie dodana do udostępnionego fragmentu nagłówka, będzie wyświetlana na każdej stronie korzystającej z szablonu, w którym używany jest ten udostępniony fragment nagłówka.</span><span class="sxs-lookup"><span data-stu-id="c4187-110">When a welcome message is added to a shared header fragment, it will be shown on every page that uses the template where that shared header fragment is used.</span></span>

<span data-ttu-id="c4187-111">Aby dodać wiadomość powitalną do witryny, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="c4187-111">To add a welcome message to your site, follow these steps.</span></span>

1. <span data-ttu-id="c4187-112">Przejdź do swojej witryny w module konstruktora witryn Commerce.</span><span class="sxs-lookup"><span data-stu-id="c4187-112">In Commerce site builder, go to your site.</span></span>
1. <span data-ttu-id="c4187-113">Wybierz **Fragmenty**.</span><span class="sxs-lookup"><span data-stu-id="c4187-113">Select **Fragments**.</span></span>
1. <span data-ttu-id="c4187-114">Wybierz fragment nagłówka, do którego ma zostać dodana wiadomość.</span><span class="sxs-lookup"><span data-stu-id="c4187-114">Select the header fragment to add the message to.</span></span>
1. <span data-ttu-id="c4187-115">W drzewie konspektu rozwiń **komunikaty o błędach/informacjach**.</span><span class="sxs-lookup"><span data-stu-id="c4187-115">In the outline tree, expand **Error/Information messages**.</span></span>
1. <span data-ttu-id="c4187-116">Wybierz moduł alertów, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4187-116">Select the alert module, and then select **OK**.</span></span> <span data-ttu-id="c4187-117">Jeśli moduł alertów jeszcze nie istnieje, najpierw wybierz przycisk wielokropka (**...**) obok **komunikaty o błędach/informacjach**, a następnie wybierz opcję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="c4187-117">If an alert module doesn't yet exist, first select the ellipsis button (**...**) next to **Error/Information messages**, and then select **Add module**.</span></span>
1. <span data-ttu-id="c4187-118">W okienku właściwości po prawej stronie na karcie **Dane** wybierz pozycję **Dodaj źródło danych**, a następnie wybierz pozycję **Zawartość**.</span><span class="sxs-lookup"><span data-stu-id="c4187-118">In the property pane on the right, on the **Data** tab, select **Add Data Source**, and then select **Content**.</span></span>
1. <span data-ttu-id="c4187-119">W polu **wpisany tekst** wprowadź tekst komunikatu powitalnego.</span><span class="sxs-lookup"><span data-stu-id="c4187-119">In the **Input Text** field, enter the text of the welcome message.</span></span>
1. <span data-ttu-id="c4187-120">Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować fragment nagłówka, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="c4187-120">Select **Save**, select **Finish editing** to check in the header fragment, and then select **Publish** to publish it.</span></span> 

<span data-ttu-id="c4187-121">Komunikat powitalny będzie teraz wyświetlany u góry każdej strony witryny, która używa wybranego fragmentu nagłówka.</span><span class="sxs-lookup"><span data-stu-id="c4187-121">The welcome message will now appear at the top of every site page that uses the selected header fragment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c4187-122">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="c4187-122">Additional resources</span></span>

[<span data-ttu-id="c4187-123">Dodawanie logo</span><span class="sxs-lookup"><span data-stu-id="c4187-123">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="c4187-124">Wybór motywu witryny</span><span class="sxs-lookup"><span data-stu-id="c4187-124">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="c4187-125">Praca z plikami zastępowania CSS</span><span class="sxs-lookup"><span data-stu-id="c4187-125">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="c4187-126">Dodawanie ikony favicon</span><span class="sxs-lookup"><span data-stu-id="c4187-126">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="c4187-127">Dodawanie powiadomienia o prawach autorskich</span><span class="sxs-lookup"><span data-stu-id="c4187-127">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="c4187-128">Dodawanie języków do witryny</span><span class="sxs-lookup"><span data-stu-id="c4187-128">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="c4187-129">Dodawanie kodu skryptu do stron witryny w celu obsługi telemetrii</span><span class="sxs-lookup"><span data-stu-id="c4187-129">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
