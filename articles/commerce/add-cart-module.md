---
title: Moduł koszyka
description: W tym temacie opisano moduły koszyka i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 03/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 598b35b1bd365e761d8d4c5ef214935e60b971f4
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154024"
---
# <a name="cart-module"></a><span data-ttu-id="0c5d6-103">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="0c5d6-103">Cart module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="0c5d6-104">W tym temacie opisano moduły koszyka i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0c5d6-104">This topic covers cart modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="0c5d6-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="0c5d6-105">Overview</span></span>

<span data-ttu-id="0c5d6-106">Moduł koszyka wyświetla towary, które zostały dodane do koszyka, zanim odbiorca przejdzie do procesu realizacji transakcji.</span><span class="sxs-lookup"><span data-stu-id="0c5d6-106">A cart module shows the items that have been added to the cart before the customer proceeds to checkout.</span></span> <span data-ttu-id="0c5d6-107">Ten moduł pokazuje również podsumowanie zamówień i pozwala odbiorcy na zastosowanie lub usunięcie kodów promocyjnych.</span><span class="sxs-lookup"><span data-stu-id="0c5d6-107">The module also shows an order summary and lets the customer apply or remove promotional codes.</span></span>

<span data-ttu-id="0c5d6-108">Moduł koszyk obsługuje wykonanie transakcji zalogowanych uzytkowników i gości.</span><span class="sxs-lookup"><span data-stu-id="0c5d6-108">The cart module supports signed-in checkout and guest checkout.</span></span> <span data-ttu-id="0c5d6-109">Ponadto obsługuje łącze **Powrót do zakupów**.</span><span class="sxs-lookup"><span data-stu-id="0c5d6-109">It also supports a **Back to shopping** link.</span></span> <span data-ttu-id="0c5d6-110">Można skonfigurować marszrutę dla tego łącza w **Ustawienia witryny \> Rozszerzenia \> Marszruty**.</span><span class="sxs-lookup"><span data-stu-id="0c5d6-110">You can configure the route for this link at **Site Settings \> Extensions \> Routes**.</span></span>

<span data-ttu-id="0c5d6-111">Moduł koszyka służy do renderowania danych na podstawie identyfikatora koszyka, który jest plikiem cookie przeglądarki dostępnym w witrynie.</span><span class="sxs-lookup"><span data-stu-id="0c5d6-111">The cart module renders data based on the cart ID, which is a browser cookie available throughout the site.</span></span>

## <a name="cart-module-properties-and-slots"></a><span data-ttu-id="0c5d6-112">Właściwości modułu koszyka i gniazda</span><span class="sxs-lookup"><span data-stu-id="0c5d6-112">Cart module properties and slots</span></span>

<span data-ttu-id="0c5d6-113">Moduł koszyka ma właściwość **Nagłówka**, która może być ustawiona na wartości takie jak **Torba na zakupy** i **Elementy w koszyku**.</span><span class="sxs-lookup"><span data-stu-id="0c5d6-113">The cart module has a **Heading** property that can be set to values such as **Shopping bag** and **Items in your cart**.</span></span> 

## <a name="modules-that-can-be-used-in-a-cart-module"></a><span data-ttu-id="0c5d6-114">Moduły, których można używać w module koszyka</span><span class="sxs-lookup"><span data-stu-id="0c5d6-114">Modules that can be used in a cart module</span></span>

- <span data-ttu-id="0c5d6-115">**Blok zawartości zaawansowanej** — ten moduł obsługuje obsługę komunikacji niestandardowej w module koszyka.</span><span class="sxs-lookup"><span data-stu-id="0c5d6-115">**Text block** – This module supports custom messaging in the cart module.</span></span> <span data-ttu-id="0c5d6-116">Komunikaty są prowadzone przez system zarządzania zawartością (CMS).</span><span class="sxs-lookup"><span data-stu-id="0c5d6-116">The messages are driven by the content management system (CMS).</span></span> <span data-ttu-id="0c5d6-117">Można dodać dowolny komunikat, na przykład „w przypadku problemów z zamówieniem, skontaktuj się z firmą 1-800-Fabrikam”.</span><span class="sxs-lookup"><span data-stu-id="0c5d6-117">Any message can be added, such as "For issues with your order, contact 1-800-Fabrikam."</span></span>
- <span data-ttu-id="0c5d6-118">**Wybór sklepu** — ten moduł pokazuje listę magazynów pobliskich, w których dany towar jest dostępny do odebrania.</span><span class="sxs-lookup"><span data-stu-id="0c5d6-118">**Store selector** – This module shows a list of nearby stores where an item is available for pickup.</span></span> <span data-ttu-id="0c5d6-119">Umożliwia użytkownikom wprowadzenie lokalizacji, w której znajdują się bliskie sklepy.</span><span class="sxs-lookup"><span data-stu-id="0c5d6-119">It lets users enter a location to find stores that are nearby.</span></span> <span data-ttu-id="0c5d6-120">Aby uzyskać więcej informacji na temat tego modułu, należy zapoznać się z tematem [moduł Selector sklepów](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="0c5d6-120">For more information on this module, see [Store Selector module](store-selector.md).</span></span>

## <a name="cart-module-settings"></a><span data-ttu-id="0c5d6-121">Ustawienia modułu koszyka</span><span class="sxs-lookup"><span data-stu-id="0c5d6-121">Cart module settings</span></span>

<span data-ttu-id="0c5d6-122">Moduły koszyka mają następujące ustawienia, które można skonfigurować w **Ustawienia witryny \> Rozszerzenia**:</span><span class="sxs-lookup"><span data-stu-id="0c5d6-122">Cart modules have the following settings that can be configured at **Site Settings \> Extensions**:</span></span>

- <span data-ttu-id="0c5d6-123">**Ilość maksymalna** — To ustawienie jest używane do określania maksymalnej liczby każdej pozycji, którą można dodać do koszyka.</span><span class="sxs-lookup"><span data-stu-id="0c5d6-123">**Maximum quantity** – This property is used to specify the maximum number of each item that can be added to the cart.</span></span> <span data-ttu-id="0c5d6-124">Na przykład sprzedawca może zdecydować, że tylko 10 sztuk każdego produktu może być sprzedawanych w jednej transakcji.</span><span class="sxs-lookup"><span data-stu-id="0c5d6-124">For example, a retailer might decide that only 10 of each product can be sold in a single transaction.</span></span>
- <span data-ttu-id="0c5d6-125">**Sprawdzanie zapasów** — Jeśli wartość jest ustawiona na **prawda**, towar jest dodawany do koszyka dopiero po upewnieniu się, że jest on w zapasach.</span><span class="sxs-lookup"><span data-stu-id="0c5d6-125">**Inventory check** – When the value is set to **True**, an item is added to the cart only after the buy box module makes sure that it's in stock.</span></span> <span data-ttu-id="0c5d6-126">Ta kontrola zapasów jest realizowana dla scenariuszy, w których towar zostanie wysłany, jak i dla scenariuszy, w których zostanie on odebrany w sklepie.</span><span class="sxs-lookup"><span data-stu-id="0c5d6-126">This inventory check is done for scenarios where the item will be shipped and for scenarios where it will be picked up in the store.</span></span> <span data-ttu-id="0c5d6-127">Jeśli wartość jest ustawiona na **fałsz**, nie jest przeprowadzane sprawdzanie zapasów przed dodaniem towaru do koszyka i założenie zamówienia.</span><span class="sxs-lookup"><span data-stu-id="0c5d6-127">If the value is set to **False**, no inventory check is done before an item is added to the cart and the order is placed.</span></span>
- <span data-ttu-id="0c5d6-128">**Bufor zapasów** — ta właściwość służy do określania numeru buforowego zapasów.</span><span class="sxs-lookup"><span data-stu-id="0c5d6-128">**Inventory buffer** – This property is used to specify a buffer number for inventory.</span></span> <span data-ttu-id="0c5d6-129">Zapasy są obsługiwane w czasie rzeczywistym, a w przypadku, gdy wiele odbiorców nakłada zamówienia, może być trudne utrzymywanie dokładnej inwentaryzacji zapasów.</span><span class="sxs-lookup"><span data-stu-id="0c5d6-129">Inventory is maintained in real time, and when many customers place orders, it can be difficult to maintain an accurate inventory count.</span></span> <span data-ttu-id="0c5d6-130">Po zakończeniu sprawdzania zapasów, jeśli zapasy są mniejsze niż kwota bufora, produkt jest traktowany jako wychodzący z zapasów.</span><span class="sxs-lookup"><span data-stu-id="0c5d6-130">When an inventory check is done, if the inventory is less than the buffer amount, the product is treated as out of stock.</span></span> <span data-ttu-id="0c5d6-131">W związku z tym, jeśli sprzedaż będzie się odbywała szybko przez kilka kanałów i inwentaryzacja nie jest w pełni zsynchronizowana, jest mniejsze ryzyko sprzedaży towaru, który jest poza zapasem.</span><span class="sxs-lookup"><span data-stu-id="0c5d6-131">Therefore, when sales occur quickly through several channels, and the inventory count isn't fully synced, there is less risk that an item that is out of stock will be sold.</span></span>
- <span data-ttu-id="0c5d6-132">**Powrót do zakupów** — ta właściwość służy do określania trasy dla łącza **Powrót do zakupów**.</span><span class="sxs-lookup"><span data-stu-id="0c5d6-132">**Back to shopping** – This property is used to specify the route for the **Back to shopping** link.</span></span> <span data-ttu-id="0c5d6-133">Marszrutę można skonfigurować na poziomie witryny, umożliwiając detalistom przejęcie odbiorcy z powrotem na stronę główną lub na inną stronę w witrynie.</span><span class="sxs-lookup"><span data-stu-id="0c5d6-133">The route can be configured at the site level, allowing retailers to take the customer back to the home page or any other page on the site.</span></span>

## <a name="commerce-scale-unit-interaction"></a><span data-ttu-id="0c5d6-134">Interakcja Commerce Scale Unit</span><span class="sxs-lookup"><span data-stu-id="0c5d6-134">Commerce Scale Unit interaction</span></span>

<span data-ttu-id="0c5d6-135">Moduł koszyka pobiera informacje o produktach za pomocą interfejsów API Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="0c5d6-135">The cart module retrieves product information by using Commerce Scale Unit APIs.</span></span> <span data-ttu-id="0c5d6-136">Identyfikator koszyka z pliku cookie przeglądarki jest używany do pobierania wszystkich informacji o produktach z Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="0c5d6-136">The cart ID from the browser cookie is used to retrieve all the product information from Commerce Scale Unit.</span></span>

## <a name="add-a-cart-module-to-a-page"></a><span data-ttu-id="0c5d6-137">Dodawanie modułu koszyka do strony</span><span class="sxs-lookup"><span data-stu-id="0c5d6-137">Add a cart module to a page</span></span>

<span data-ttu-id="0c5d6-138">Aby dodać moduł koszyka do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="0c5d6-138">To add a cart module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="0c5d6-139">Utwórz fragment o nazwie **Fragment koszyka** i dodaj moduł koszyka do nowego fragmentu.</span><span class="sxs-lookup"><span data-stu-id="0c5d6-139">Create a fragment named **Cart fragment**, and add a cart module to the new fragment.</span></span>
1. <span data-ttu-id="0c5d6-140">Dodaj nagłówek do modułu koszyka.</span><span class="sxs-lookup"><span data-stu-id="0c5d6-140">Add a heading to the cart module.</span></span>
1. <span data-ttu-id="0c5d6-141">Dodaj moduł Wybór sklepu do modułu koszyka.</span><span class="sxs-lookup"><span data-stu-id="0c5d6-141">Add a store selector module to the cart module.</span></span>
1. <span data-ttu-id="0c5d6-142">Zapisz fragment, zakończ jego edycję, a następnie go opublikuj.</span><span class="sxs-lookup"><span data-stu-id="0c5d6-142">Save the fragment, finish editing, and then publish the fragment.</span></span>
1. <span data-ttu-id="0c5d6-143">Utwórz szablon o nazwie **Szablon koszyka** i dodaj do niego właśnie utworzony fragment koszyka.</span><span class="sxs-lookup"><span data-stu-id="0c5d6-143">Create a template named **Cart template**, and add the cart fragment that you just created.</span></span>
1. <span data-ttu-id="0c5d6-144">Zapisz szablon, zakończ jego edycję, a następnie go opublikuj.</span><span class="sxs-lookup"><span data-stu-id="0c5d6-144">Save the template, finish editing, and then publish the template.</span></span>
1. <span data-ttu-id="0c5d6-145">Utwórz stronę, która korzysta z nowego szablonu.</span><span class="sxs-lookup"><span data-stu-id="0c5d6-145">Create a page that uses the new template.</span></span>
1. <span data-ttu-id="0c5d6-146">Zapisz i zobacz podgląd strony.</span><span class="sxs-lookup"><span data-stu-id="0c5d6-146">Save and preview the page.</span></span>
1. <span data-ttu-id="0c5d6-147">Zakończ edycję strony, a następnie ją opublikuj.</span><span class="sxs-lookup"><span data-stu-id="0c5d6-147">Finish editing the page, and then publish the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0c5d6-148">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="0c5d6-148">Additional resources</span></span>

[<span data-ttu-id="0c5d6-149">Omówienie zestawu początkowego</span><span class="sxs-lookup"><span data-stu-id="0c5d6-149">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="0c5d6-150">Moduł kontenera</span><span class="sxs-lookup"><span data-stu-id="0c5d6-150">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="0c5d6-151">Moduł wyboru sklepu</span><span class="sxs-lookup"><span data-stu-id="0c5d6-151">Store selector module</span></span>](store-selector.md)

[<span data-ttu-id="0c5d6-152">Moduł pola zakupu</span><span class="sxs-lookup"><span data-stu-id="0c5d6-152">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="0c5d6-153">Moduł realizacji transakcji</span><span class="sxs-lookup"><span data-stu-id="0c5d6-153">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="0c5d6-154">Moduł potwierdzenia zamówienia</span><span class="sxs-lookup"><span data-stu-id="0c5d6-154">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="0c5d6-155">Moduł nagłówka</span><span class="sxs-lookup"><span data-stu-id="0c5d6-155">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="0c5d6-156">Moduł stopki</span><span class="sxs-lookup"><span data-stu-id="0c5d6-156">Footer module</span></span>](author-footer-module.md)
