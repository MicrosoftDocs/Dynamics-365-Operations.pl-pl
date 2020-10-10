---
title: Moduł stopki
description: W tym temacie opisano moduły stopki i sposób ich tworzenia w Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
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
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 42a71ea9498461febca80952acc3158517918332
ms.sourcegitcommit: 8028fbc5b9585e87d3331ea02577ff82ede090af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/16/2020
ms.locfileid: "3816968"
---
# <a name="footer-module"></a><span data-ttu-id="43113-103">Moduł stopki</span><span class="sxs-lookup"><span data-stu-id="43113-103">Footer module</span></span>  

[!include [banner](includes/banner.md)]

<span data-ttu-id="43113-104">W tym temacie opisano moduły stopki i sposób ich tworzenia w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="43113-104">This topic covers footer modules and describes how to create them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="43113-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="43113-105">Overview</span></span>

<span data-ttu-id="43113-106">Moduł stopki jest specjalnym kontenerem używanym do obsługi modułów wyświetlanych w stopce strony.</span><span class="sxs-lookup"><span data-stu-id="43113-106">The footer module is a special container that is used to host the modules that appear in the page footer.</span></span> <span data-ttu-id="43113-107">Na przykład może zawierać łącza do różnych stron w witrynie, takie jak **Skontaktuj się z nami** czy **Zasady sklepu**.</span><span class="sxs-lookup"><span data-stu-id="43113-107">For example, it can include links to various pages across the site, such as **Contact Us** and **Store Policies** pages.</span></span>

<span data-ttu-id="43113-108">Poniższy obraz pokazuje przykład modułu stopki na stronie witryny.</span><span class="sxs-lookup"><span data-stu-id="43113-108">The following image shows an example of a footer module on a site page.</span></span>

![Przykład modułu stopki](./media/ecommerce-footer.PNG)

## <a name="footer-module-properties"></a><span data-ttu-id="43113-110">Właściwości modułu stopki</span><span class="sxs-lookup"><span data-stu-id="43113-110">Footer module properties</span></span> 

<span data-ttu-id="43113-111">Podobnie jak większość kontenerów, moduł stopki obsługuje właściwości nagłówka i szerokości.</span><span class="sxs-lookup"><span data-stu-id="43113-111">Like most containers, a footer module supports properties for the heading and the width.</span></span> <span data-ttu-id="43113-112">Ponadto obsługuje on dodawanie wielu modułów kategorii stopki.</span><span class="sxs-lookup"><span data-stu-id="43113-112">It also supports the addition of multiple footer category modules.</span></span> <span data-ttu-id="43113-113">Każdy dodany moduł kategorii stopki jest renderowany jako kolumna w module stopki.</span><span class="sxs-lookup"><span data-stu-id="43113-113">Each footer category module that is added is rendered as a column in the footer module.</span></span>

## <a name="modules-available-in-a-footer-module"></a><span data-ttu-id="43113-114">Moduły dostępne w module stopki</span><span class="sxs-lookup"><span data-stu-id="43113-114">Modules available in a footer module</span></span>

<span data-ttu-id="43113-115">**Elementy stopki** — moduł elementów stopki może zawierać nagłówek, obraz i łącze.</span><span class="sxs-lookup"><span data-stu-id="43113-115">**Footer items** – A footer items module can contain a heading, an image, and a link.</span></span> <span data-ttu-id="43113-116">Nagłówek może być używany zarówno osobno, jak i w połączeniu z obrazem i łączem.</span><span class="sxs-lookup"><span data-stu-id="43113-116">The heading can be used either alone or in combination with an image and a link.</span></span> <span data-ttu-id="43113-117">Każde łącze w stopce może być skonfigurowane w taki sposób, aby zawierało tylko tekst (na przykład łącza „Skontaktuj się z nami” i „Polityka prywatności”) lub tak, aby zawierał zarówno tekst, jak i obraz (na przykład łącza do nośników społecznościowych).</span><span class="sxs-lookup"><span data-stu-id="43113-117">Every link in the footer can be configured so that it has just text (for example, "Contact Us" and "Privacy" links), or so that it has both text and an image (for example, social media links).</span></span>

<span data-ttu-id="43113-118">**Powrót do początku** — powrót do początku modułu stanowi łącze umożliwiającego szybką nawigację do góry strony.</span><span class="sxs-lookup"><span data-stu-id="43113-118">**Back to top** – A back to top module provides a link for quick navigation to the top of the page.</span></span> <span data-ttu-id="43113-119">Wymagany jest cel.</span><span class="sxs-lookup"><span data-stu-id="43113-119">A destination is required.</span></span> <span data-ttu-id="43113-120">Domyślną wartością docelową jest \#, co zabiera użytkownika na początek strony.</span><span class="sxs-lookup"><span data-stu-id="43113-120">The default destination value is \#, which takes the user to the top of the page.</span></span>

## <a name="create-a-footer-module"></a><span data-ttu-id="43113-121">Tworzenie modułu stopki</span><span class="sxs-lookup"><span data-stu-id="43113-121">Create a footer module</span></span>

1. <span data-ttu-id="43113-122">Przejdź do **Fragmenty**, a następnie wybierz opcję **Nowy**, aby stworzyć nowy fragment.</span><span class="sxs-lookup"><span data-stu-id="43113-122">Go to **Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="43113-123">W oknie dialogowym **Nowy fragment** wybierz moduł **Kontener**, wprowadź nazwę dla fragmentu, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="43113-123">In the **New fragment** dialog box, select the **Container** module, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="43113-124">W gnieździe **Domyślny kontener** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="43113-124">In the **Default container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="43113-125">W oknie dialogowym **Dodawanie modułu** wybierz moduł **Kategorii stopki** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="43113-125">In the **Add Module** dialog box, select the **Footer category** module, and then select **OK**.</span></span>
1. <span data-ttu-id="43113-126">W gnieździe **Kategoria stopki** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="43113-126">In the **Footer category** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="43113-127">W oknie dialogowym **Dodawanie modułu** wybierz moduł **Element stopki** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="43113-127">In the **Add Module** dialog box, select the **Footer item** module, and then select **OK**.</span></span>
1. <span data-ttu-id="43113-128">Wybierz gniazdo **Element stopki**, a następnie w okienku właściwości po prawej stronie skonfiguruj nagłówek, łącze i tekst łącza oraz obraz w miarę potrzeb.</span><span class="sxs-lookup"><span data-stu-id="43113-128">Select the **Footer item** slot, and then, in the properties pane on the right, configure the heading, link and link text, and image as needed.</span></span>
1. <span data-ttu-id="43113-129">Aby dodać więcej elementów, pwtórz kroki od 5 do 7 dla każdego elementu.</span><span class="sxs-lookup"><span data-stu-id="43113-129">To add more footer items, repeat steps 5 through 7 for each.</span></span>
1. <span data-ttu-id="43113-130">Aby dodać łącze „powrót do góry” w drzewie konspektu wybierz wielokropek (**...**) w gnieździe **Kategoria stopki**, a następnie wybierz pozycję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="43113-130">To add a "back to top" link to your footer, select the ellipsis (**...**) in the **Footer category** slot, and then select **Add Module**.</span></span>
1. <span data-ttu-id="43113-131">W oknie dialogowym **Dodawanie modułu** wybierz moduł **Powrót do góry** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="43113-131">In the **Add Module** dialog box, select the **Back to top** module, and then select **OK**.</span></span>
1. <span data-ttu-id="43113-132">Wybierz gniazdo **Powrót do góry**, a następnie w okienku właściwości po prawej stronie skonfiguruj tekst i inne właściwości modułu w miarę potrzeb.</span><span class="sxs-lookup"><span data-stu-id="43113-132">Select the **Back to top** slot, and then, in the properties pane on the right, configure the text and other module properties as needed.</span></span>
1. <span data-ttu-id="43113-133">Wybierz **Zakończ edycję**, aby zaewidencjonować fragment, a następnie wybierz opcję **Publikuj**, aby go opublikować.</span><span class="sxs-lookup"><span data-stu-id="43113-133">Select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="43113-134">Aby zagwarantować, że nagłówek ma się pojawiać na każdej stronie, należy wykonać poniższe kroki na każdym szablonie strony utworzonym dla witryny.</span><span class="sxs-lookup"><span data-stu-id="43113-134">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="43113-135">W gnieździe **Stopka** w module **Strona domyślna** dodaj fragment stopki, który został utworzony.</span><span class="sxs-lookup"><span data-stu-id="43113-135">In the **Footer** slot of the **Default page** module, add the footer fragment that you created.</span></span>
1. <span data-ttu-id="43113-136">Wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="43113-136">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="43113-137">Dodanie fragmentu do szablonów stron pomaga zagwarantować, że stopka będzie renderowana na każdej stronie.</span><span class="sxs-lookup"><span data-stu-id="43113-137">By adding the fragment to page templates, you help guarantee that the footer is rendered on every page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="43113-138">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="43113-138">Additional resources</span></span>

[<span data-ttu-id="43113-139">Omówienie biblioteki modułów</span><span class="sxs-lookup"><span data-stu-id="43113-139">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="43113-140">Moduł kontenera</span><span class="sxs-lookup"><span data-stu-id="43113-140">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="43113-141">Moduł pola zakupu</span><span class="sxs-lookup"><span data-stu-id="43113-141">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="43113-142">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="43113-142">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="43113-143">Moduł realizacji transakcji</span><span class="sxs-lookup"><span data-stu-id="43113-143">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="43113-144">Moduł potwierdzenia zamówienia</span><span class="sxs-lookup"><span data-stu-id="43113-144">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="43113-145">Moduł nagłówka</span><span class="sxs-lookup"><span data-stu-id="43113-145">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="43113-146">Moduł stopki</span><span class="sxs-lookup"><span data-stu-id="43113-146">Footer module</span></span>](author-footer-module.md)
