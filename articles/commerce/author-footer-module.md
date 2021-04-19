---
title: Moduł stopki
description: W tym temacie opisano moduły stopki i sposób ich tworzenia w Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: d6e7b0ad4fe0723575a0ec55a9b02d110568db58
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797240"
---
# <a name="footer-module"></a><span data-ttu-id="de8c1-103">Moduł stopki</span><span class="sxs-lookup"><span data-stu-id="de8c1-103">Footer module</span></span>  

[!include [banner](includes/banner.md)]

<span data-ttu-id="de8c1-104">W tym temacie opisano moduły stopki i sposób ich tworzenia w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="de8c1-104">This topic covers footer modules and describes how to create them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="de8c1-105">Moduł stopki jest specjalnym kontenerem używanym do obsługi modułów wyświetlanych w stopce strony.</span><span class="sxs-lookup"><span data-stu-id="de8c1-105">The footer module is a special container that is used to host the modules that appear in the page footer.</span></span> <span data-ttu-id="de8c1-106">Na przykład może zawierać łącza do różnych stron w witrynie, takie jak **Skontaktuj się z nami** czy **Zasady sklepu**.</span><span class="sxs-lookup"><span data-stu-id="de8c1-106">For example, it can include links to various pages across the site, such as **Contact Us** and **Store Policies** pages.</span></span>

<span data-ttu-id="de8c1-107">Poniższy obraz pokazuje przykład modułu stopki na stronie witryny.</span><span class="sxs-lookup"><span data-stu-id="de8c1-107">The following image shows an example of a footer module on a site page.</span></span>

![Przykład modułu stopki](./media/ecommerce-footer.PNG)

## <a name="footer-module-properties"></a><span data-ttu-id="de8c1-109">Właściwości modułu stopki</span><span class="sxs-lookup"><span data-stu-id="de8c1-109">Footer module properties</span></span> 

<span data-ttu-id="de8c1-110">Podobnie jak większość kontenerów, moduł stopki obsługuje właściwości nagłówka i szerokości.</span><span class="sxs-lookup"><span data-stu-id="de8c1-110">Like most containers, a footer module supports properties for the heading and the width.</span></span> <span data-ttu-id="de8c1-111">Ponadto obsługuje on dodawanie wielu modułów kategorii stopki.</span><span class="sxs-lookup"><span data-stu-id="de8c1-111">It also supports the addition of multiple footer category modules.</span></span> <span data-ttu-id="de8c1-112">Każdy dodany moduł kategorii stopki jest renderowany jako kolumna w module stopki.</span><span class="sxs-lookup"><span data-stu-id="de8c1-112">Each footer category module that is added is rendered as a column in the footer module.</span></span>

## <a name="modules-available-in-a-footer-module"></a><span data-ttu-id="de8c1-113">Moduły dostępne w module stopki</span><span class="sxs-lookup"><span data-stu-id="de8c1-113">Modules available in a footer module</span></span>

<span data-ttu-id="de8c1-114">**Elementy stopki** — moduł elementów stopki może zawierać nagłówek, obraz i łącze.</span><span class="sxs-lookup"><span data-stu-id="de8c1-114">**Footer items** – A footer items module can contain a heading, an image, and a link.</span></span> <span data-ttu-id="de8c1-115">Nagłówek może być używany zarówno osobno, jak i w połączeniu z obrazem i łączem.</span><span class="sxs-lookup"><span data-stu-id="de8c1-115">The heading can be used either alone or in combination with an image and a link.</span></span> <span data-ttu-id="de8c1-116">Każde łącze w stopce może być skonfigurowane w taki sposób, aby zawierało tylko tekst (na przykład łącza „Skontaktuj się z nami” i „Polityka prywatności”) lub tak, aby zawierał zarówno tekst, jak i obraz (na przykład łącza do nośników społecznościowych).</span><span class="sxs-lookup"><span data-stu-id="de8c1-116">Every link in the footer can be configured so that it has just text (for example, "Contact Us" and "Privacy" links), or so that it has both text and an image (for example, social media links).</span></span>

<span data-ttu-id="de8c1-117">**Powrót do początku** — powrót do początku modułu stanowi łącze umożliwiającego szybką nawigację do góry strony.</span><span class="sxs-lookup"><span data-stu-id="de8c1-117">**Back to top** – A back to top module provides a link for quick navigation to the top of the page.</span></span> <span data-ttu-id="de8c1-118">Wymagany jest cel.</span><span class="sxs-lookup"><span data-stu-id="de8c1-118">A destination is required.</span></span> <span data-ttu-id="de8c1-119">Domyślną wartością docelową jest \#, co zabiera użytkownika na początek strony.</span><span class="sxs-lookup"><span data-stu-id="de8c1-119">The default destination value is \#, which takes the user to the top of the page.</span></span>

## <a name="create-a-footer-module"></a><span data-ttu-id="de8c1-120">Tworzenie modułu stopki</span><span class="sxs-lookup"><span data-stu-id="de8c1-120">Create a footer module</span></span>

1. <span data-ttu-id="de8c1-121">Przejdź do **Fragmenty**, a następnie wybierz opcję **Nowy**, aby stworzyć nowy fragment.</span><span class="sxs-lookup"><span data-stu-id="de8c1-121">Go to **Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="de8c1-122">W oknie dialogowym **Nowy fragment** wybierz moduł **Kontener**, wprowadź nazwę dla fragmentu, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de8c1-122">In the **New fragment** dialog box, select the **Container** module, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="de8c1-123">W gnieździe **Domyślny kontener** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="de8c1-123">In the **Default container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="de8c1-124">W oknie dialogowym **Dodawanie modułu** wybierz moduł **Kategorii stopki** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de8c1-124">In the **Add Module** dialog box, select the **Footer category** module, and then select **OK**.</span></span>
1. <span data-ttu-id="de8c1-125">W gnieździe **Kategoria stopki** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="de8c1-125">In the **Footer category** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="de8c1-126">W oknie dialogowym **Dodawanie modułu** wybierz moduł **Element stopki** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de8c1-126">In the **Add Module** dialog box, select the **Footer item** module, and then select **OK**.</span></span>
1. <span data-ttu-id="de8c1-127">Wybierz gniazdo **Element stopki**, a następnie w okienku właściwości po prawej stronie skonfiguruj nagłówek, łącze i tekst łącza oraz obraz w miarę potrzeb.</span><span class="sxs-lookup"><span data-stu-id="de8c1-127">Select the **Footer item** slot, and then, in the properties pane on the right, configure the heading, link and link text, and image as needed.</span></span>
1. <span data-ttu-id="de8c1-128">Aby dodać więcej elementów, pwtórz kroki od 5 do 7 dla każdego elementu.</span><span class="sxs-lookup"><span data-stu-id="de8c1-128">To add more footer items, repeat steps 5 through 7 for each.</span></span>
1. <span data-ttu-id="de8c1-129">Aby dodać łącze „powrót do góry” w drzewie konspektu wybierz wielokropek (**...**) w gnieździe **Kategoria stopki**, a następnie wybierz pozycję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="de8c1-129">To add a "back to top" link to your footer, select the ellipsis (**...**) in the **Footer category** slot, and then select **Add Module**.</span></span>
1. <span data-ttu-id="de8c1-130">W oknie dialogowym **Dodawanie modułu** wybierz moduł **Powrót do góry** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="de8c1-130">In the **Add Module** dialog box, select the **Back to top** module, and then select **OK**.</span></span>
1. <span data-ttu-id="de8c1-131">Wybierz gniazdo **Powrót do góry**, a następnie w okienku właściwości po prawej stronie skonfiguruj tekst i inne właściwości modułu w miarę potrzeb.</span><span class="sxs-lookup"><span data-stu-id="de8c1-131">Select the **Back to top** slot, and then, in the properties pane on the right, configure the text and other module properties as needed.</span></span>
1. <span data-ttu-id="de8c1-132">Wybierz **Zakończ edycję**, aby zaewidencjonować fragment, a następnie wybierz opcję **Publikuj**, aby go opublikować.</span><span class="sxs-lookup"><span data-stu-id="de8c1-132">Select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="de8c1-133">Aby zagwarantować, że nagłówek ma się pojawiać na każdej stronie, należy wykonać poniższe kroki na każdym szablonie strony utworzonym dla witryny.</span><span class="sxs-lookup"><span data-stu-id="de8c1-133">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="de8c1-134">W gnieździe **Stopka** w module **Strona domyślna** dodaj fragment stopki, który został utworzony.</span><span class="sxs-lookup"><span data-stu-id="de8c1-134">In the **Footer** slot of the **Default page** module, add the footer fragment that you created.</span></span>
1. <span data-ttu-id="de8c1-135">Wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="de8c1-135">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="de8c1-136">Dodanie fragmentu do szablonów stron pomaga zagwarantować, że stopka będzie renderowana na każdej stronie.</span><span class="sxs-lookup"><span data-stu-id="de8c1-136">By adding the fragment to page templates, you help guarantee that the footer is rendered on every page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="de8c1-137">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="de8c1-137">Additional resources</span></span>

[<span data-ttu-id="de8c1-138">Omówienie biblioteki modułów</span><span class="sxs-lookup"><span data-stu-id="de8c1-138">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="de8c1-139">Moduł kontenera</span><span class="sxs-lookup"><span data-stu-id="de8c1-139">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="de8c1-140">Moduł pola zakupu</span><span class="sxs-lookup"><span data-stu-id="de8c1-140">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="de8c1-141">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="de8c1-141">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="de8c1-142">Moduł realizacji transakcji</span><span class="sxs-lookup"><span data-stu-id="de8c1-142">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="de8c1-143">Moduł potwierdzenia zamówienia</span><span class="sxs-lookup"><span data-stu-id="de8c1-143">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="de8c1-144">Moduł nagłówka</span><span class="sxs-lookup"><span data-stu-id="de8c1-144">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="de8c1-145">Moduł stopki</span><span class="sxs-lookup"><span data-stu-id="de8c1-145">Footer module</span></span>](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]