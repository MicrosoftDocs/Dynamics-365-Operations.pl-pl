---
title: Moduł mapy
description: W tym temacie opisano moduły mapy i sposób ich konfiguracji w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: a0f5d902289c5867095e34a135c50d342f3c4f13
ms.sourcegitcommit: 078befcd7f3531073ab2c08b365bcf132d6477b0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/31/2020
ms.locfileid: "3647020"
---
# <a name="map-module"></a><span data-ttu-id="3ff3b-103">Moduł mapy</span><span class="sxs-lookup"><span data-stu-id="3ff3b-103">Map module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="3ff3b-104">W tym temacie opisano moduły mapy i sposób ich konfiguracji w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3ff3b-104">This topic covers map modules and describes how to configure them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="3ff3b-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="3ff3b-105">Overview</span></span>

<span data-ttu-id="3ff3b-106">Moduł mapy pokazuje lokalizacje sklepów na interakcyjnej mapie, która jest renderowana przy użyciu [kontrolki sieci Web usługi Bing Maps V8](https://docs.microsoft.com/bingmaps/v8-web-control/).</span><span class="sxs-lookup"><span data-stu-id="3ff3b-106">A map module shows the locations of stores on an interactive map that is rendered by using the [Bing Maps V8 Web Control](https://docs.microsoft.com/bingmaps/v8-web-control/).</span></span> <span data-ttu-id="3ff3b-107">Klucz interfejsu API map usługi Bing jest wymagany i należy go dodać do strony udostępnione parametry Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="3ff3b-107">A Bing Maps API key is required and must be added to the shared parameters page in Commerce headquarters.</span></span> <span data-ttu-id="3ff3b-108">Moduły mapy zapewniają różne widoki, takie jak drogi, z powietrza i widok z ulicy, które użytkownicy mogą wybrać, aby wyświetlić lokalizacje mapy.</span><span class="sxs-lookup"><span data-stu-id="3ff3b-108">Map modules provide different views, such as Road, Aerial, and Streetside, that users can select to view map locations.</span></span> <span data-ttu-id="3ff3b-109">Pozwalają również na interakcje, takie jak powiększanie i wykorzystywanie lokalizacji użytkownika.</span><span class="sxs-lookup"><span data-stu-id="3ff3b-109">They also allow for interactions such as zooming and using the user's location.</span></span>

<span data-ttu-id="3ff3b-110">Moduł mapy działa w połączeniu z modułem selektora sklepów, aby określić lokalizacje geograficzne sklepów, które muszą być renderowane na mapie.</span><span class="sxs-lookup"><span data-stu-id="3ff3b-110">A map module works in conjunction with the store selector module to determine the geographic locations of stores that must be rendered on a map.</span></span> <span data-ttu-id="3ff3b-111">Moduły selektora sklepu i mapy współdziałają, gdy użytkownik wybierze sklep w jednym z tych modułów na stronie serwisu.</span><span class="sxs-lookup"><span data-stu-id="3ff3b-111">Store selector and map modules interact when a user selects a store in one of those modules on a site page.</span></span> <span data-ttu-id="3ff3b-112">Moduły mapy można rozszerzyć na inne scenariusze, poza interakcją z modułami selektora sklepów.</span><span class="sxs-lookup"><span data-stu-id="3ff3b-112">Map modules can be extended for other scenarios, beyond interaction with store selector modules.</span></span> <span data-ttu-id="3ff3b-113">Wymagane jest jednak dostosowanie modułu.</span><span class="sxs-lookup"><span data-stu-id="3ff3b-113">However, module customization is required.</span></span>

<span data-ttu-id="3ff3b-114">Moduł mapy został wprowadzony w module Commerce Version 10.0.13.</span><span class="sxs-lookup"><span data-stu-id="3ff3b-114">The map module was introduced in Commerce version 10.0.13.</span></span>

<span data-ttu-id="3ff3b-115">Poniższy obraz pokazuje przykład modułu mapy, który jest używany na stronie lokalizacji sklepu.</span><span class="sxs-lookup"><span data-stu-id="3ff3b-115">The following image shows an example of a map module that is used on a store locations page.</span></span>

![Przykład modułu wyboru sklepu](./media/ecommerce-Storelocator.PNG)

## <a name="module-properties"></a><span data-ttu-id="3ff3b-117">Właściwości modułu</span><span class="sxs-lookup"><span data-stu-id="3ff3b-117">Module properties</span></span>

| <span data-ttu-id="3ff3b-118">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="3ff3b-118">Property name</span></span>             | <span data-ttu-id="3ff3b-119">Wartość</span><span class="sxs-lookup"><span data-stu-id="3ff3b-119">Value</span></span>                 | <span data-ttu-id="3ff3b-120">opis</span><span class="sxs-lookup"><span data-stu-id="3ff3b-120">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="3ff3b-121">Nagłówek</span><span class="sxs-lookup"><span data-stu-id="3ff3b-121">Heading</span></span> | <span data-ttu-id="3ff3b-122">Tekst</span><span class="sxs-lookup"><span data-stu-id="3ff3b-122">Text</span></span> | <span data-ttu-id="3ff3b-123">Nagłówek modułu.</span><span class="sxs-lookup"><span data-stu-id="3ff3b-123">The heading for the module.</span></span> |
| <span data-ttu-id="3ff3b-124">Opcje pinezki: domyślna ikona</span><span class="sxs-lookup"><span data-stu-id="3ff3b-124">Pushpin options: Default icon</span></span> | <span data-ttu-id="3ff3b-125">Wizerunek</span><span class="sxs-lookup"><span data-stu-id="3ff3b-125">Image</span></span> | <span data-ttu-id="3ff3b-126">Obraz symbolu pinezki używany w sklepach pokazywanych na mapie.</span><span class="sxs-lookup"><span data-stu-id="3ff3b-126">The pushpin symbol image to use for stores that are shown on a map.</span></span> |
| <span data-ttu-id="3ff3b-127">Opcje pinezki: aktywna ikona</span><span class="sxs-lookup"><span data-stu-id="3ff3b-127">Pushpin options: Active icon</span></span> | <span data-ttu-id="3ff3b-128">Wizerunek</span><span class="sxs-lookup"><span data-stu-id="3ff3b-128">Image</span></span> | <span data-ttu-id="3ff3b-129">Obraz symbolu pinezki używany w sklepie wybranym na mapie.</span><span class="sxs-lookup"><span data-stu-id="3ff3b-129">The pushpin symbol image to use for a store that is selected on a map.</span></span> |
| <span data-ttu-id="3ff3b-130">Opcje pinezki: kolor domyślnej ikony</span><span class="sxs-lookup"><span data-stu-id="3ff3b-130">Pushpin options: Default icon color</span></span> | <span data-ttu-id="3ff3b-131">Ciąg znaków</span><span class="sxs-lookup"><span data-stu-id="3ff3b-131">Character string</span></span> | <span data-ttu-id="3ff3b-132">Tekst lub wartość szesnastkowa koloru symboli pinezki na mapie.</span><span class="sxs-lookup"><span data-stu-id="3ff3b-132">The text or hexadecimal value for the color of pushpin symbols on a map.</span></span> |
| <span data-ttu-id="3ff3b-133">Opcje pinezki: kolor aktywnej ikony</span><span class="sxs-lookup"><span data-stu-id="3ff3b-133">Pushpin options: Active icon color</span></span> | <span data-ttu-id="3ff3b-134">Ciąg znaków</span><span class="sxs-lookup"><span data-stu-id="3ff3b-134">Character string</span></span> | <span data-ttu-id="3ff3b-135">Tekst lub wartość szesnastkowa koloru wybranego symboli pinezki na mapie.</span><span class="sxs-lookup"><span data-stu-id="3ff3b-135">The text or hexadecimal value for the color of selected pushpin symbols on a map.</span></span> |
| <span data-ttu-id="3ff3b-136">Pokaż indeks</span><span class="sxs-lookup"><span data-stu-id="3ff3b-136">Show index</span></span> | <span data-ttu-id="3ff3b-137">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="3ff3b-137">**True** or **False**</span></span> | <span data-ttu-id="3ff3b-138">Jeśli dla tej właściwości ustawiono wartość **Prawda**, każdy symbol pinezki wskazujący magazyn będzie zawierał indeks.</span><span class="sxs-lookup"><span data-stu-id="3ff3b-138">If this property is set to **True**, every pushpin symbol that indicates a store will show an index.</span></span> <span data-ttu-id="3ff3b-139">Ten indeks będzie pasował do indeksu w widoku listy wyświetlanego przez moduł wyboru sklepu.</span><span class="sxs-lookup"><span data-stu-id="3ff3b-139">This index will match the index in the list view that the store selector module shows.</span></span> |

## <a name="add-allowed-mapping-urls-to-a-sites-content-security-policy-directives"></a><span data-ttu-id="3ff3b-140">Dodaj dozwolone mapowanie adresów URL do dyrektyw zasad zabezpieczeń dotyczących zawartości oddziału</span><span class="sxs-lookup"><span data-stu-id="3ff3b-140">Add allowed mapping URLs to a site's content security policy directives</span></span>

<span data-ttu-id="3ff3b-141">Aby moduł map mógł współdziałać z Bing Maps, musisz upewnić się, że poniższe adresy URL mapowania są dozwolone (nazywane również „białą listą”) zgodnie z polityką bezpieczeństwa treści (CSP) Twojej witryny.</span><span class="sxs-lookup"><span data-stu-id="3ff3b-141">For the maps module to interact with Bing Maps, you must ensure that the following mapping URLs are allowed (also known as "whitelisted") per your site's content security policy (CSP).</span></span> <span data-ttu-id="3ff3b-142">Ta konfiguracja jest wykonywana w narzędziu do tworzenia witryn Commerce przez dodanie dozwolonych adresów URL do różnych dyrektyw CSP witryny (na przykład **img-src**).</span><span class="sxs-lookup"><span data-stu-id="3ff3b-142">This setup is done in Commerce site builder, by adding allowed URLs to various site CSP directives (for example, **img-src**).</span></span> <span data-ttu-id="3ff3b-143">Aby uzyskać więcej informacji, zajrzyj do [zasad zabezpieczeń dotyczących zawartości](manage-csp.md).</span><span class="sxs-lookup"><span data-stu-id="3ff3b-143">For more information, see [Content security policy](manage-csp.md).</span></span> 

- <span data-ttu-id="3ff3b-144">Do dyrektywy **connect-src** dodaj **&#42;.bing.com**.</span><span class="sxs-lookup"><span data-stu-id="3ff3b-144">To the **connect-src** directive, add **&#42;.bing.com**.</span></span>
- <span data-ttu-id="3ff3b-145">Do dyrektywy **img-src**, dodaj **&#42;.virtualearth.net**.</span><span class="sxs-lookup"><span data-stu-id="3ff3b-145">To the **img-src** directive, add **&#42;.virtualearth.net**.</span></span>
- <span data-ttu-id="3ff3b-146">Do dyrektywy **script-src**, dodaj **&#42;.bing.com, &#42;.virtualearth.net**.</span><span class="sxs-lookup"><span data-stu-id="3ff3b-146">To the **script-src** directive, add **&#42;.bing.com, &#42;.virtualearth.net**.</span></span>
- <span data-ttu-id="3ff3b-147">Do dyrektywy **script style-src**, dodaj **&#42;.bing.com**.</span><span class="sxs-lookup"><span data-stu-id="3ff3b-147">To the **script style-src** directive, add **&#42;.bing.com**.</span></span>

## <a name="add-a-map-module-to-a-page"></a><span data-ttu-id="3ff3b-148">Dodawanie modułu mapy do strony</span><span class="sxs-lookup"><span data-stu-id="3ff3b-148">Add a map module to a page</span></span>

<span data-ttu-id="3ff3b-149">Aby uzyskać szczegółowe informacje dotyczące konfigurowania modułu mapy na stronie, należy zapoznać się z tematem [Moduł wyboru sklepu](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="3ff3b-149">For detailed information about how to configure a map module on a page, see [Store selector module](store-selector.md).</span></span> 
 
## <a name="additional-resources"></a><span data-ttu-id="3ff3b-150">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="3ff3b-150">Additional resources</span></span>

[<span data-ttu-id="3ff3b-151">Omówienie zestawu początkowego</span><span class="sxs-lookup"><span data-stu-id="3ff3b-151">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="3ff3b-152">Moduł pola zakupu</span><span class="sxs-lookup"><span data-stu-id="3ff3b-152">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="3ff3b-153">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="3ff3b-153">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="3ff3b-154">Moduł wyboru sklepu</span><span class="sxs-lookup"><span data-stu-id="3ff3b-154">Store selector module</span></span>](store-selector.md)

[<span data-ttu-id="3ff3b-155">Zarządzanie Mapami Bing dla swojej organizacji</span><span class="sxs-lookup"><span data-stu-id="3ff3b-155">Manage Bing Maps for your organization</span></span>](./dev-itpro/manage-bing-maps.md)

[<span data-ttu-id="3ff3b-156">Kontrolka sieci Web Bing Maps V8</span><span class="sxs-lookup"><span data-stu-id="3ff3b-156">Bing Maps V8 Web Control</span></span>](https://docs.microsoft.com/bingmaps/v8-web-control/)
