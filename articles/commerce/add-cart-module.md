---
title: Moduł koszyka
description: W tym temacie opisano moduły koszyka i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: f6dd8fb56f7342eb9c877eda503a92f4a31e5863
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025443"
---
# <a name="cart-module"></a><span data-ttu-id="232b9-103">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="232b9-103">Cart module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="232b9-104">W tym temacie opisano moduły koszyka i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="232b9-104">This topic covers cart modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="232b9-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="232b9-105">Overview</span></span>

<span data-ttu-id="232b9-106">Moduł koszyka służy do wyświetlania towarów, które zostały dodane do koszyka, zanim odbiorca przejdzie do procesu realizacji transakcji.</span><span class="sxs-lookup"><span data-stu-id="232b9-106">A cart module is used to show the items that have been added to the cart before the customer proceeds to checkout.</span></span> <span data-ttu-id="232b9-107">Dotyczy to na przykład wszystkich towarów, które zostały dodane do koszyka i podsumowania zamówień.</span><span class="sxs-lookup"><span data-stu-id="232b9-107">For example, it includes all the items that have been added to the cart and an order summary.</span></span> <span data-ttu-id="232b9-108">Umożliwia także stosowanie lub usuwanie kodów promocyjnych przez odbiorcę.</span><span class="sxs-lookup"><span data-stu-id="232b9-108">It also lets the customer apply or remove promotional codes.</span></span>

<span data-ttu-id="232b9-109">Moduł koszyk obsługuje wykonanie transakcji zalogowanych uzytkowników i gości.</span><span class="sxs-lookup"><span data-stu-id="232b9-109">The cart module supports signed-in checkout and guest checkout.</span></span> <span data-ttu-id="232b9-110">Ponadto obsługuje łącze **Powrót do zakupów**.</span><span class="sxs-lookup"><span data-stu-id="232b9-110">It also supports a **Back to shopping** link.</span></span> <span data-ttu-id="232b9-111">Można skonfigurować marszrutę dla tego łącza w **Ustawienia witryny \> Rozszerzenia \> Marszruty**.</span><span class="sxs-lookup"><span data-stu-id="232b9-111">You can configure the route for this link at **Site Settings \> Extensions \> Routes**.</span></span>

<span data-ttu-id="232b9-112">Moduł koszyka renderuje dane na podstawie identyfikatora koszyka.</span><span class="sxs-lookup"><span data-stu-id="232b9-112">The cart module renders data based on the cart ID.</span></span> <span data-ttu-id="232b9-113">Identyfikator koszyka to plik cookie przeglądarki dostępny w witrynie.</span><span class="sxs-lookup"><span data-stu-id="232b9-113">The cart ID is a browser cookie that is available throughout the site.</span></span>

## <a name="cart-module-properties-and-slots"></a><span data-ttu-id="232b9-114">Właściwości modułu koszyka i gniazda</span><span class="sxs-lookup"><span data-stu-id="232b9-114">Cart module properties and slots</span></span>

<span data-ttu-id="232b9-115">Moduł koszyka ma właściwość **Nagłówka**, która może być ustawiona na wartości takie jak **Torba na zakupy** i **Elementy w koszyku**.</span><span class="sxs-lookup"><span data-stu-id="232b9-115">The cart module has a **Heading** property that can be set to values such as **Shopping bag** and **Items in your cart**.</span></span> 

## <a name="modules-that-can-be-used-in-a-cart-module"></a><span data-ttu-id="232b9-116">Moduły, których można używać w module koszyka</span><span class="sxs-lookup"><span data-stu-id="232b9-116">Modules that can be used in a cart module</span></span>

- <span data-ttu-id="232b9-117">**Blok zawartości zaawansowanej** — ten moduł obsługuje obsługę komunikacji niestandardowej w module koszyka.</span><span class="sxs-lookup"><span data-stu-id="232b9-117">**Text block** – This module supports custom messaging in the cart module.</span></span> <span data-ttu-id="232b9-118">Komunikaty są prowadzone przez system zarządzania zawartością (CMS).</span><span class="sxs-lookup"><span data-stu-id="232b9-118">The messages are driven by the content management system (CMS).</span></span> <span data-ttu-id="232b9-119">Można dodać dowolny komunikat, na przykład „w przypadku problemów z zamówieniem, skontaktuj się z firmą 1-800-Fabrikam”.</span><span class="sxs-lookup"><span data-stu-id="232b9-119">Any message can be added, such as "For issues with your order, contact 1-800-Fabrikam."</span></span>
- <span data-ttu-id="232b9-120">**Wybór sklepu** — ten moduł pokazuje listę magazynów pobliskich, w których dany towar jest dostępny do odebrania.</span><span class="sxs-lookup"><span data-stu-id="232b9-120">**Store selector** – This module shows a list of nearby stores where an item is available for pickup.</span></span> <span data-ttu-id="232b9-121">Umożliwia użytkownikom wprowadzenie lokalizacji, w której znajdują się bliskie sklepy.</span><span class="sxs-lookup"><span data-stu-id="232b9-121">It lets users enter a location to find stores that are nearby.</span></span> <span data-ttu-id="232b9-122">Moduł wyboru sklepu jest zintegrowany z aplikacją do geokodowania Bing Maps Geocoding (API) służy do konwersji lokalizacji na szerokość i długość geograficzną.</span><span class="sxs-lookup"><span data-stu-id="232b9-122">The store selector module is integrated with the Bing Maps Geocoding application programming interface (API) to convert the location to a latitude and longitude.</span></span> <span data-ttu-id="232b9-123">Klucz interfejsu API map usługi Bing jest wymagany i należy go dodać do strony udostępnione parametry sieci sprzedaży w Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="232b9-123">A Bing Maps API key is required and must be added to the Retail shared parameters page in Dynamics 365 Retail.</span></span> <span data-ttu-id="232b9-124">Ten moduł obsługuje dwie właściwości, **Promień wyszukiwania** i **Łącze Warunki świadczenia usługi**.</span><span class="sxs-lookup"><span data-stu-id="232b9-124">This module supports two properties, **Search radius** and **Terms of service link**.</span></span> <span data-ttu-id="232b9-125">Właściwość **Promień wyszukiwania** definiuje promień wyszukiwania dla sklepów w milach.</span><span class="sxs-lookup"><span data-stu-id="232b9-125">The **Search radius** property defines the search radius for stores, in miles.</span></span> <span data-ttu-id="232b9-126">Jeśli nie określono żadnej wartości, używany jest domyślny promień wyszukiwania, 50 mil.</span><span class="sxs-lookup"><span data-stu-id="232b9-126">If no value is specified, the default search radius, 50 miles, is used.</span></span> <span data-ttu-id="232b9-127">Jeśli używana jest mapa usług Bing lub usługa zewnętrzna, **Łącze Warunki świadczenia usługi** może być używana do udostępniania łącza do warunków świadczenia usługi.</span><span class="sxs-lookup"><span data-stu-id="232b9-127">If Bings Maps or any external service is used, the **Terms of service link** property can be used to provide a link to the terms of service.</span></span> <span data-ttu-id="232b9-128">Dla usługi Bing Maps jest wymagane łącze Warunki świadczenia usługi.</span><span class="sxs-lookup"><span data-stu-id="232b9-128">A terms of service link is required for the Bing Maps service.</span></span> 

## <a name="cart-module-settings"></a><span data-ttu-id="232b9-129">Ustawienia modułu koszyka</span><span class="sxs-lookup"><span data-stu-id="232b9-129">Cart module settings</span></span>

<span data-ttu-id="232b9-130">Moduły koszyka mają następujące ustawienia, które można skonfigurować w **Ustawienia witryny \> Rozszerzenia**:</span><span class="sxs-lookup"><span data-stu-id="232b9-130">Cart modules have the following settings that can be configured at **Site Settings \> Extensions**:</span></span>

- <span data-ttu-id="232b9-131">**Ilość maksymalna** — To ustawienie jest używane do określania maksymalnej liczby każdej pozycji, którą można dodać do koszyka.</span><span class="sxs-lookup"><span data-stu-id="232b9-131">**Maximum quantity** – This property is used to specify the maximum number of each item that can be added to the cart.</span></span> <span data-ttu-id="232b9-132">Na przykład sprzedawca może zdecydować, że tylko 10 sztuk każdego produktu może być sprzedawanych w jednej transakcji.</span><span class="sxs-lookup"><span data-stu-id="232b9-132">For example, a retailer might decide that only 10 of each product can be sold in a single transaction.</span></span>
- <span data-ttu-id="232b9-133">**Sprawdzanie zapasów** — Jeśli wartość jest ustawiona na **prawda**, towar jest dodawany do koszyka dopiero po upewnieniu się, że jest on w zapasach.</span><span class="sxs-lookup"><span data-stu-id="232b9-133">**Inventory check** – When the value is set to **True**, an item is added to the cart only after the buy box module makes sure that it's in stock.</span></span> <span data-ttu-id="232b9-134">Ta kontrola zapasów jest realizowana zarówno dla scenariuszy, w których towar zostanie wysłany, jak i dla scenariuszy, w których zostanie on odebrany w sklepie.</span><span class="sxs-lookup"><span data-stu-id="232b9-134">This inventory check is done both for scenarios where the item will be shipped and for scenarios where it will be picked up in the store.</span></span> <span data-ttu-id="232b9-135">Jeśli wartość jest ustawiona na **fałsz**, nie jest przeprowadzane sprawdzanie zapasów przed dodaniem towaru do koszyka i założenie zamówienia.</span><span class="sxs-lookup"><span data-stu-id="232b9-135">If the value is set to **False**, no inventory check is done before an item is added to the cart and the order is placed.</span></span>
- <span data-ttu-id="232b9-136">**Bufor zapasów** — ta właściwość służy do określania numeru buforowego zapasów.</span><span class="sxs-lookup"><span data-stu-id="232b9-136">**Inventory buffer** – This property is used to specify a buffer number for inventory.</span></span> <span data-ttu-id="232b9-137">Zapasy są obsługiwane w czasie rzeczywistym, a w przypadku, gdy wiele odbiorców nakłada zamówienia, może być trudne utrzymywanie dokładnej inwentaryzacji zapasów.</span><span class="sxs-lookup"><span data-stu-id="232b9-137">Inventory is maintained in real time, and when many customers place orders, it can be difficult to maintain an accurate inventory count.</span></span> <span data-ttu-id="232b9-138">Po zakończeniu sprawdzania zapasów, jeśli zapasy są mniejsze niż kwota bufora, produkt jest traktowany jako wychodzący z zapasów.</span><span class="sxs-lookup"><span data-stu-id="232b9-138">When an inventory check is done, if the inventory is less than the buffer amount, the product is treated as out of stock.</span></span> <span data-ttu-id="232b9-139">W związku z tym, jeśli sprzedaż będzie się odbywała szybko przez kilka kanałów i inwentaryzacja nie jest w pełni zsynchronizowana, jest mniejsze ryzyko sprzedaży towaru, który jest poza zapasem.</span><span class="sxs-lookup"><span data-stu-id="232b9-139">Therefore, when sales occur quickly through several channels, and the inventory count isn't fully synced, there is less risk that an item that is out of stock will be sold.</span></span>
- <span data-ttu-id="232b9-140">**Powrót do zakupów** — ta właściwość służy do określania trasy dla łącza **Powrót do zakupów**.</span><span class="sxs-lookup"><span data-stu-id="232b9-140">**Back to shopping** – This property is used to specify the route for the **Back to shopping** link.</span></span> <span data-ttu-id="232b9-141">Tę trasę można skonfigurować na poziomie witryny.</span><span class="sxs-lookup"><span data-stu-id="232b9-141">This route can be configured at the site level.</span></span> <span data-ttu-id="232b9-142">Odbiorcy tej konfiguracji przebiorą odbiorcę z powrotem na stronę główną lub na inną stronę w witrynie.</span><span class="sxs-lookup"><span data-stu-id="232b9-142">This configuration lets retailers take the customer back to the home page or any other page on the site.</span></span>

## <a name="commerce-scale-unit-interaction"></a><span data-ttu-id="232b9-143">Interakcja Commerce Scale Unit</span><span class="sxs-lookup"><span data-stu-id="232b9-143">Commerce Scale Unit interaction</span></span>

<span data-ttu-id="232b9-144">Moduł koszyka pobiera informacje o produktach za pomocą interfejsów API Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="232b9-144">The cart module retrieves product information by using Commerce Scale Unit APIs.</span></span> <span data-ttu-id="232b9-145">Identyfikator koszyka z pliku cookie przeglądarki jest używany do pobierania wszystkich informacji o produktach z Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="232b9-145">The cart ID from the browser cookie is used to retrieve all the product information from Commerce Scale Unit.</span></span>

## <a name="add-a-cart-module-to-a-page"></a><span data-ttu-id="232b9-146">Dodawanie modułu koszyka do strony</span><span class="sxs-lookup"><span data-stu-id="232b9-146">Add a cart module to a page</span></span>

<span data-ttu-id="232b9-147">Aby dodać moduł koszyka do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="232b9-147">To add a cart module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="232b9-148">Utwórz fragment o nazwie **Fragment koszyka** i dodaj do niego moduł koszyka.</span><span class="sxs-lookup"><span data-stu-id="232b9-148">Create a fragment that is named **Cart fragment**, and add a cart module to it.</span></span>
1. <span data-ttu-id="232b9-149">Dodaj nagłówek do modułu koszyka.</span><span class="sxs-lookup"><span data-stu-id="232b9-149">Add a heading to the cart module.</span></span>
1. <span data-ttu-id="232b9-150">Dodaj moduł Wybór sklepu do modułu koszyka.</span><span class="sxs-lookup"><span data-stu-id="232b9-150">Add a store selector module to the cart module.</span></span>
1. <span data-ttu-id="232b9-151">Zapisz fragment, zakończ jego edycję, a następnie go opublikuj.</span><span class="sxs-lookup"><span data-stu-id="232b9-151">Save the fragment, finish editing it, and publish it.</span></span>
1. <span data-ttu-id="232b9-152">Utwórz szablon o nazwie **Szablon koszyka** i dodaj do niego właśnie utworzony fragment koszyka.</span><span class="sxs-lookup"><span data-stu-id="232b9-152">Create a template that is named **Cart template**, and add the cart fragment that you just created to it.</span></span>
1. <span data-ttu-id="232b9-153">Zapisz szablon, zakończ jego edycję, a następnie go opublikuj.</span><span class="sxs-lookup"><span data-stu-id="232b9-153">Save the template, finish editing it, and publish it.</span></span>
1. <span data-ttu-id="232b9-154">Utwórz stronę, która korzysta z nowego szablonu.</span><span class="sxs-lookup"><span data-stu-id="232b9-154">Create a page that uses the new template.</span></span>
1. <span data-ttu-id="232b9-155">Zapisz i zobacz podgląd strony.</span><span class="sxs-lookup"><span data-stu-id="232b9-155">Save and preview the page.</span></span>
1. <span data-ttu-id="232b9-156">Zakończ edytowanie strony i opublikuj go.</span><span class="sxs-lookup"><span data-stu-id="232b9-156">Finish editing the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="232b9-157">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="232b9-157">Additional resources</span></span>

[<span data-ttu-id="232b9-158">Omówienie zestawu początkowego</span><span class="sxs-lookup"><span data-stu-id="232b9-158">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="232b9-159">Moduł kontenera</span><span class="sxs-lookup"><span data-stu-id="232b9-159">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="232b9-160">Moduł pola zakupu</span><span class="sxs-lookup"><span data-stu-id="232b9-160">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="232b9-161">Moduł realizacji transakcji</span><span class="sxs-lookup"><span data-stu-id="232b9-161">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="232b9-162">Moduł potwierdzenia zamówienia</span><span class="sxs-lookup"><span data-stu-id="232b9-162">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="232b9-163">Moduł nagłówka</span><span class="sxs-lookup"><span data-stu-id="232b9-163">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="232b9-164">Moduł stopki</span><span class="sxs-lookup"><span data-stu-id="232b9-164">Footer module</span></span>](author-footer-module.md)
