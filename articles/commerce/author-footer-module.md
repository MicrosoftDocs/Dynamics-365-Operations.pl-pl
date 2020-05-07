---
title: Moduł stopki
description: W tym temacie opisano moduły stopki i sposób ich tworzenia w Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 04/14/2020
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
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 51f8d26d6223dcd1f6961058cd9d772a67c69670
ms.sourcegitcommit: 7a1d01122790b904e2d96a7ea9f1d003392358a6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/17/2020
ms.locfileid: "3269643"
---
# <a name="footer-module"></a><span data-ttu-id="6a2bd-103">Moduł stopki</span><span class="sxs-lookup"><span data-stu-id="6a2bd-103">Footer module</span></span>  


[!include [banner](includes/banner.md)]

<span data-ttu-id="6a2bd-104">W tym temacie opisano moduły stopki i sposób ich tworzenia w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6a2bd-104">This topic covers footer modules and describes how to create them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="6a2bd-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="6a2bd-105">Overview</span></span>

<span data-ttu-id="6a2bd-106">Moduł stopki jest specjalnym kontenerem używanym do obsługi modułów wyświetlanych w stopce strony.</span><span class="sxs-lookup"><span data-stu-id="6a2bd-106">The footer module is a special container that is used to host the modules that appear in the page footer.</span></span> <span data-ttu-id="6a2bd-107">Na przykład może zawierać łącza do różnych stron w witrynie, takie jak **Skontaktuj się z nami** czy **Zasady sklepu**.</span><span class="sxs-lookup"><span data-stu-id="6a2bd-107">For example, it can include links to various pages across the site, such as **Contact Us** and **Store Policies** pages.</span></span>

## <a name="footer-module-properties"></a><span data-ttu-id="6a2bd-108">Właściwości modułu stopki</span><span class="sxs-lookup"><span data-stu-id="6a2bd-108">Footer module properties</span></span> 

<span data-ttu-id="6a2bd-109">Podobnie jak większość kontenerów, moduł stopki obsługuje właściwości nagłówka i szerokości.</span><span class="sxs-lookup"><span data-stu-id="6a2bd-109">Like most containers, a footer module supports properties for the heading and the width.</span></span> <span data-ttu-id="6a2bd-110">Ponadto obsługuje on dodawanie wielu modułów kategorii stopki.</span><span class="sxs-lookup"><span data-stu-id="6a2bd-110">It also supports the addition of multiple footer category modules.</span></span> <span data-ttu-id="6a2bd-111">Każdy dodany moduł kategorii stopki jest renderowany jako kolumna w module stopki.</span><span class="sxs-lookup"><span data-stu-id="6a2bd-111">Each footer category module that is added is rendered as a column in the footer module.</span></span>

## <a name="modules-available-in-a-footer-module"></a><span data-ttu-id="6a2bd-112">Moduły dostępne w module stopki</span><span class="sxs-lookup"><span data-stu-id="6a2bd-112">Modules available in a footer module</span></span>

<span data-ttu-id="6a2bd-113">**Elementy stopki** — moduł elementów stopki może zawierać nagłówek, obraz i łącze.</span><span class="sxs-lookup"><span data-stu-id="6a2bd-113">**Footer items** – A footer items module can contain a heading, an image, and a link.</span></span> <span data-ttu-id="6a2bd-114">Nagłówek może być używany zarówno osobno, jak i w połączeniu z obrazem i łączem.</span><span class="sxs-lookup"><span data-stu-id="6a2bd-114">The heading can be used either alone or in combination with an image and a link.</span></span> <span data-ttu-id="6a2bd-115">Każde łącze w stopce może być skonfigurowane w taki sposób, aby zawierało tylko tekst (na przykład łącza „Skontaktuj się z nami” i „Polityka prywatności”) lub tak, aby zawierał zarówno tekst, jak i obraz (na przykład łącza do nośników społecznościowych).</span><span class="sxs-lookup"><span data-stu-id="6a2bd-115">Every link in the footer can be configured so that it has just text (for example, "Contact Us" and "Privacy" links), or so that it has both text and an image (for example, social media links).</span></span>

<span data-ttu-id="6a2bd-116">**Powrót do początku** — powrót do początku modułu stanowi łącze umożliwiającego szybką nawigację do góry strony.</span><span class="sxs-lookup"><span data-stu-id="6a2bd-116">**Back to top** – A back to top module provides a link for quick navigation to the top of the page.</span></span> <span data-ttu-id="6a2bd-117">Wymagany jest cel.</span><span class="sxs-lookup"><span data-stu-id="6a2bd-117">A destination is required.</span></span> <span data-ttu-id="6a2bd-118">Domyślną wartością docelową jest #, co zabiera użytkownika na początek strony.</span><span class="sxs-lookup"><span data-stu-id="6a2bd-118">The default destination value is #, which takes the user to the top of the page.</span></span>

## <a name="author-a-footer-module"></a><span data-ttu-id="6a2bd-119">Tworzenie modułu stopki</span><span class="sxs-lookup"><span data-stu-id="6a2bd-119">Author a footer module</span></span>

1. <span data-ttu-id="6a2bd-120">W okienku nawigacji wybierz pozycję **Fragmenty**, a następnie wybierz opcję **Nowy fragment strony**.</span><span class="sxs-lookup"><span data-stu-id="6a2bd-120">In the navigation pane, select **Fragments**, and then select **New Page Fragment**.</span></span>
1. <span data-ttu-id="6a2bd-121">W oknie dialogowym **Nowy fragment strony** wybierz moduł stopki, wprowadź nazwę dla fragmentu strony, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="6a2bd-121">In the **New Page Fragment** dialog box, select the footer module, enter a name for the page fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="6a2bd-122">W drzewie konspektu z lewej strony wybierz przycisk wielokropka (**...**) dla modułu stopki, a następnie wybierz pozycję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="6a2bd-122">In the outline tree on the left, select the ellipsis button (**...**) for the footer module, and then select **Add Module**.</span></span>
1. <span data-ttu-id="6a2bd-123">W oknie dialogowym **Dodawanie modułu** wybierz moduł kategorii stopki i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="6a2bd-123">In the **Add Module** dialog box, select the footer category module, and then select **OK**.</span></span>
1. <span data-ttu-id="6a2bd-124">W drzewie konspektu wybierz przycisk wielokropka dla kategorii stopki, a następnie wybierz pozycję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="6a2bd-124">In the outline tree, select the ellipsis button for the footer category module, and then select **Add Module**.</span></span>
1. <span data-ttu-id="6a2bd-125">W oknie dialogowym **Dodawanie modułu** wybierz moduł elementu stopki i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="6a2bd-125">In the **Add Module** dialog box, select the footer item module, and then select **OK**.</span></span>
1. <span data-ttu-id="6a2bd-126">W drzewie konspektu wybierz moduł elementu stopki.</span><span class="sxs-lookup"><span data-stu-id="6a2bd-126">In the outline tree, select the footer item module.</span></span> <span data-ttu-id="6a2bd-127">Następnie w okienku właściwości po prawej stronie skonfiguruj nagłówek, łącze i tekst łącza oraz obraz w miarę potrzeb.</span><span class="sxs-lookup"><span data-stu-id="6a2bd-127">Then, in the properties pane on the right, configure the heading, link and link text, and image as you require.</span></span>
1. <span data-ttu-id="6a2bd-128">Aby dodać więcej elementów, pwtórz kroki od 5 do 7.</span><span class="sxs-lookup"><span data-stu-id="6a2bd-128">To add more footer items, repeat steps 5 through 7.</span></span>
1. <span data-ttu-id="6a2bd-129">Aby dodać łącze „powrót do góry” w drzewie konspektu wybierz przycisk wielokropka dla kategorii stopki, a następnie wybierz pozycję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="6a2bd-129">To add a "back to top" link to your footer, select the ellipsis button for the footer category module, and then select **Add Module**.</span></span>
1. <span data-ttu-id="6a2bd-130">W oknie dialogowym **Dodawanie modułu** wybierz moduł powrót do góry i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="6a2bd-130">In the **Add Module** dialog box, select the back to top module, and then select **OK**.</span></span>
1. <span data-ttu-id="6a2bd-131">W drzewie konspektu wybierz moduł powrót do góry.</span><span class="sxs-lookup"><span data-stu-id="6a2bd-131">In the outline tree, select the back to top module.</span></span> <span data-ttu-id="6a2bd-132">Następnie w okienku właściwości po prawej stronie należy skonfigurować moduł powrót do góry w miarę potrzeb</span><span class="sxs-lookup"><span data-stu-id="6a2bd-132">Then, in the properties pane on the right, configure the back to top module as you require.</span></span>
1. <span data-ttu-id="6a2bd-133">Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować fragment strony, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="6a2bd-133">Select **Save**, select **Finish editing** to check in the page fragment, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="6a2bd-134">Na każdym szablonie strony utworzonym dla witryny wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="6a2bd-134">On every page template that has been created for the site, follow these steps.</span></span>

1. <span data-ttu-id="6a2bd-135">W **Głównym** gnieździe na stronie domyślnej w module stopki dodaj fragment stopki, który został utworzony.</span><span class="sxs-lookup"><span data-stu-id="6a2bd-135">In the **Main** slot of the default page, in the footer module, add the footer fragment that you created.</span></span>
1. <span data-ttu-id="6a2bd-136">Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="6a2bd-136">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="6a2bd-137">Dodanie fragmentu strony do szablonów stron pomaga zagwarantować, że stopka będzie renderowana na każdej stronie.</span><span class="sxs-lookup"><span data-stu-id="6a2bd-137">By adding the page fragment to page templates, you help guarantee that the footer is rendered on every page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6a2bd-138">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="6a2bd-138">Additional resources</span></span>

[<span data-ttu-id="6a2bd-139">Omówienie zestawu początkowego</span><span class="sxs-lookup"><span data-stu-id="6a2bd-139">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="6a2bd-140">Moduł kontenera</span><span class="sxs-lookup"><span data-stu-id="6a2bd-140">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="6a2bd-141">Moduł pola zakupu</span><span class="sxs-lookup"><span data-stu-id="6a2bd-141">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="6a2bd-142">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="6a2bd-142">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="6a2bd-143">Moduł realizacji transakcji</span><span class="sxs-lookup"><span data-stu-id="6a2bd-143">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="6a2bd-144">Moduł potwierdzenia zamówienia</span><span class="sxs-lookup"><span data-stu-id="6a2bd-144">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="6a2bd-145">Moduł nagłówka</span><span class="sxs-lookup"><span data-stu-id="6a2bd-145">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="6a2bd-146">Moduł stopki</span><span class="sxs-lookup"><span data-stu-id="6a2bd-146">Footer module</span></span>](author-footer-module.md)
