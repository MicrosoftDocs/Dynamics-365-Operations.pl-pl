---
title: Moduł mapy
description: W tym temacie opisano moduły mapy i sposób ich konfiguracji w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 74991a2979540dab344f39976005250637fab29c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5252589"
---
# <a name="map-module"></a><span data-ttu-id="bd057-103">Moduł mapy</span><span class="sxs-lookup"><span data-stu-id="bd057-103">Map module</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="bd057-104">W tym temacie opisano moduły mapy i sposób ich konfiguracji w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="bd057-104">This topic covers map modules and describes how to configure them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="bd057-105">Moduł mapy pokazuje lokalizacje sklepów na interakcyjnej mapie, która jest renderowana przy użyciu [kontrolki sieci Web usługi Bing Maps V8](https://docs.microsoft.com/bingmaps/v8-web-control/).</span><span class="sxs-lookup"><span data-stu-id="bd057-105">A map module shows the locations of stores on an interactive map that is rendered by using the [Bing Maps V8 Web Control](https://docs.microsoft.com/bingmaps/v8-web-control/).</span></span> <span data-ttu-id="bd057-106">Klucz interfejsu API map usługi Bing jest wymagany i należy go dodać do strony udostępnione parametry Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="bd057-106">A Bing Maps API key is required and must be added to the shared parameters page in Commerce headquarters.</span></span> <span data-ttu-id="bd057-107">Moduły mapy zapewniają różne widoki, takie jak drogi, z powietrza i widok z ulicy, które użytkownicy mogą wybrać, aby wyświetlić lokalizacje mapy.</span><span class="sxs-lookup"><span data-stu-id="bd057-107">Map modules provide different views, such as Road, Aerial, and Streetside, that users can select to view map locations.</span></span> <span data-ttu-id="bd057-108">Pozwalają również na interakcje, takie jak powiększanie i wykorzystywanie lokalizacji użytkownika.</span><span class="sxs-lookup"><span data-stu-id="bd057-108">They also allow for interactions such as zooming and using the user's location.</span></span>

<span data-ttu-id="bd057-109">Moduł mapy działa w połączeniu z modułem selektora sklepów, aby określić lokalizacje geograficzne sklepów, które muszą być renderowane na mapie.</span><span class="sxs-lookup"><span data-stu-id="bd057-109">A map module works in conjunction with the store selector module to determine the geographic locations of stores that must be rendered on a map.</span></span> <span data-ttu-id="bd057-110">Moduły selektora sklepu i mapy współdziałają, gdy użytkownik wybierze sklep w jednym z tych modułów na stronie serwisu.</span><span class="sxs-lookup"><span data-stu-id="bd057-110">Store selector and map modules interact when a user selects a store in one of those modules on a site page.</span></span> <span data-ttu-id="bd057-111">Moduły mapy można rozszerzyć na inne scenariusze, poza interakcją z modułami selektora sklepów.</span><span class="sxs-lookup"><span data-stu-id="bd057-111">Map modules can be extended for other scenarios, beyond interaction with store selector modules.</span></span> <span data-ttu-id="bd057-112">Wymagane jest jednak dostosowanie modułu.</span><span class="sxs-lookup"><span data-stu-id="bd057-112">However, module customization is required.</span></span>

> [!NOTE]
> <span data-ttu-id="bd057-113">Moduł mapy jest dostępny w wydaniu Dynamics 365 Commerce 10.0.13.</span><span class="sxs-lookup"><span data-stu-id="bd057-113">The map module is available in the Dynamics 365 Commerce 10.0.13 release.</span></span>

<span data-ttu-id="bd057-114">Poniższy obraz pokazuje przykład modułu mapy, który jest używany na stronie lokalizacji sklepu.</span><span class="sxs-lookup"><span data-stu-id="bd057-114">The following image shows an example of a map module that is used on a store locations page.</span></span>

![Przykład modułu wyboru sklepu](./media/ecommerce-Storelocator.PNG)

## <a name="module-properties"></a><span data-ttu-id="bd057-116">Właściwości modułu</span><span class="sxs-lookup"><span data-stu-id="bd057-116">Module properties</span></span>

| <span data-ttu-id="bd057-117">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="bd057-117">Property name</span></span>             | <span data-ttu-id="bd057-118">Wartość</span><span class="sxs-lookup"><span data-stu-id="bd057-118">Value</span></span>                 | <span data-ttu-id="bd057-119">opis</span><span class="sxs-lookup"><span data-stu-id="bd057-119">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="bd057-120">Nagłówek</span><span class="sxs-lookup"><span data-stu-id="bd057-120">Heading</span></span> | <span data-ttu-id="bd057-121">Tekst</span><span class="sxs-lookup"><span data-stu-id="bd057-121">Text</span></span> | <span data-ttu-id="bd057-122">Nagłówek modułu.</span><span class="sxs-lookup"><span data-stu-id="bd057-122">The heading for the module.</span></span> |
| <span data-ttu-id="bd057-123">Opcje pinezki: domyślna ikona</span><span class="sxs-lookup"><span data-stu-id="bd057-123">Pushpin options: Default icon</span></span> | <span data-ttu-id="bd057-124">Wizerunek</span><span class="sxs-lookup"><span data-stu-id="bd057-124">Image</span></span> | <span data-ttu-id="bd057-125">Obraz symbolu pinezki używany w sklepach pokazywanych na mapie.</span><span class="sxs-lookup"><span data-stu-id="bd057-125">The pushpin symbol image to use for stores that are shown on a map.</span></span> |
| <span data-ttu-id="bd057-126">Opcje pinezki: aktywna ikona</span><span class="sxs-lookup"><span data-stu-id="bd057-126">Pushpin options: Active icon</span></span> | <span data-ttu-id="bd057-127">Wizerunek</span><span class="sxs-lookup"><span data-stu-id="bd057-127">Image</span></span> | <span data-ttu-id="bd057-128">Obraz symbolu pinezki używany w sklepie wybranym na mapie.</span><span class="sxs-lookup"><span data-stu-id="bd057-128">The pushpin symbol image to use for a store that is selected on a map.</span></span> |
| <span data-ttu-id="bd057-129">Opcje pinezki: kolor domyślnej ikony</span><span class="sxs-lookup"><span data-stu-id="bd057-129">Pushpin options: Default icon color</span></span> | <span data-ttu-id="bd057-130">Ciąg znaków</span><span class="sxs-lookup"><span data-stu-id="bd057-130">Character string</span></span> | <span data-ttu-id="bd057-131">Tekst lub wartość szesnastkowa koloru symboli pinezki na mapie.</span><span class="sxs-lookup"><span data-stu-id="bd057-131">The text or hexadecimal value for the color of pushpin symbols on a map.</span></span> |
| <span data-ttu-id="bd057-132">Opcje pinezki: kolor aktywnej ikony</span><span class="sxs-lookup"><span data-stu-id="bd057-132">Pushpin options: Active icon color</span></span> | <span data-ttu-id="bd057-133">Ciąg znaków</span><span class="sxs-lookup"><span data-stu-id="bd057-133">Character string</span></span> | <span data-ttu-id="bd057-134">Tekst lub wartość szesnastkowa koloru wybranego symboli pinezki na mapie.</span><span class="sxs-lookup"><span data-stu-id="bd057-134">The text or hexadecimal value for the color of selected pushpin symbols on a map.</span></span> |
| <span data-ttu-id="bd057-135">Pokaż indeks</span><span class="sxs-lookup"><span data-stu-id="bd057-135">Show index</span></span> | <span data-ttu-id="bd057-136">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="bd057-136">**True** or **False**</span></span> | <span data-ttu-id="bd057-137">Jeśli dla tej właściwości ustawiono wartość **Prawda**, każdy symbol pinezki wskazujący magazyn będzie zawierał indeks.</span><span class="sxs-lookup"><span data-stu-id="bd057-137">If this property is set to **True**, every pushpin symbol that indicates a store will show an index.</span></span> <span data-ttu-id="bd057-138">Ten indeks będzie pasował do indeksu w widoku listy wyświetlanego przez moduł wyboru sklepu.</span><span class="sxs-lookup"><span data-stu-id="bd057-138">This index will match the index in the list view that the store selector module shows.</span></span> |

## <a name="add-allowed-mapping-urls-to-a-sites-content-security-policy-directives"></a><span data-ttu-id="bd057-139">Dodaj dozwolone mapowanie adresów URL do dyrektyw zasad zabezpieczeń dotyczących zawartości oddziału</span><span class="sxs-lookup"><span data-stu-id="bd057-139">Add allowed mapping URLs to a site's content security policy directives</span></span>

<span data-ttu-id="bd057-140">Aby moduł map mógł współdziałać z Bing Maps, musisz upewnić się, że poniższe adresy URL mapowania są dozwolone zgodnie z polityką bezpieczeństwa treści (CSP) Twojej witryny.</span><span class="sxs-lookup"><span data-stu-id="bd057-140">For the maps module to interact with Bing Maps, you must ensure that the following mapping URLs are allowed per your site's content security policy (CSP).</span></span> <span data-ttu-id="bd057-141">Ta konfiguracja jest wykonywana w narzędziu do tworzenia witryn Commerce przez dodanie dozwolonych adresów URL do różnych dyrektyw CSP witryny (na przykład **img-src**).</span><span class="sxs-lookup"><span data-stu-id="bd057-141">This setup is done in Commerce site builder, by adding allowed URLs to various site CSP directives (for example, **img-src**).</span></span> <span data-ttu-id="bd057-142">Aby uzyskać więcej informacji, zajrzyj do [zasad zabezpieczeń dotyczących zawartości](manage-csp.md).</span><span class="sxs-lookup"><span data-stu-id="bd057-142">For more information, see [Content security policy](manage-csp.md).</span></span> 

- <span data-ttu-id="bd057-143">Do dyrektywy **connect-src** dodaj **&#42;.bing.com**.</span><span class="sxs-lookup"><span data-stu-id="bd057-143">To the **connect-src** directive, add **&#42;.bing.com**.</span></span>
- <span data-ttu-id="bd057-144">Do dyrektywy **img-src**, dodaj **&#42;.virtualearth.net**.</span><span class="sxs-lookup"><span data-stu-id="bd057-144">To the **img-src** directive, add **&#42;.virtualearth.net**.</span></span>
- <span data-ttu-id="bd057-145">Do dyrektywy **script-src**, dodaj **&#42;.bing.com, &#42;.virtualearth.net**.</span><span class="sxs-lookup"><span data-stu-id="bd057-145">To the **script-src** directive, add **&#42;.bing.com, &#42;.virtualearth.net**.</span></span>
- <span data-ttu-id="bd057-146">Do dyrektywy **script style-src**, dodaj **&#42;.bing.com**.</span><span class="sxs-lookup"><span data-stu-id="bd057-146">To the **script style-src** directive, add **&#42;.bing.com**.</span></span>

## <a name="add-a-map-module-to-a-page"></a><span data-ttu-id="bd057-147">Dodawanie modułu mapy do strony</span><span class="sxs-lookup"><span data-stu-id="bd057-147">Add a map module to a page</span></span>

<span data-ttu-id="bd057-148">Aby uzyskać szczegółowe informacje dotyczące konfigurowania modułu mapy na stronie, należy zapoznać się z tematem [Moduł wyboru sklepu](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="bd057-148">For detailed information about how to configure a map module on a page, see [Store selector module](store-selector.md).</span></span> 
 
## <a name="additional-resources"></a><span data-ttu-id="bd057-149">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="bd057-149">Additional resources</span></span>

[<span data-ttu-id="bd057-150">Omówienie biblioteki modułów</span><span class="sxs-lookup"><span data-stu-id="bd057-150">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="bd057-151">Moduł pola zakupu</span><span class="sxs-lookup"><span data-stu-id="bd057-151">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="bd057-152">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="bd057-152">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="bd057-153">Moduł wyboru sklepu</span><span class="sxs-lookup"><span data-stu-id="bd057-153">Store selector module</span></span>](store-selector.md)

[<span data-ttu-id="bd057-154">Zarządzanie Mapami Bing dla swojej organizacji</span><span class="sxs-lookup"><span data-stu-id="bd057-154">Manage Bing Maps for your organization</span></span>](./dev-itpro/manage-bing-maps.md)

[<span data-ttu-id="bd057-155">Kontrolka sieci Web Bing Maps V8</span><span class="sxs-lookup"><span data-stu-id="bd057-155">Bing Maps V8 Web Control</span></span>](https://docs.microsoft.com/bingmaps/v8-web-control/)


[!INCLUDE[footer-include](../includes/footer-banner.md)]