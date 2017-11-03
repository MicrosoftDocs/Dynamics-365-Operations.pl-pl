---
title: "Sprzedaż i zwrot produktów spoza asortymentu"
description: "W aplikacji Dynamics 365 for Retail można sprzedawać i zwracać produkty spoza asortymentu."
author: pdp1207
manager: AnnBe
ms.date: 05/24/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Core, Operations
ms.custom: 
ms.search.region: Global
ms.search.industry: retail
ms.author: prabhup
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: fd00da1242964dddda5c19d46e61da33997e6d02
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="sell-and-return-products-outside-of-an-assortment"></a><span data-ttu-id="240ac-103">Sprzedaż i zwrot produktów spoza asortymentu</span><span class="sxs-lookup"><span data-stu-id="240ac-103">Sell and return products outside of an assortment</span></span>
<span data-ttu-id="240ac-104">Typowy scenariusz u każdego sprzedawcy detalicznego to sprzedaż produktów klientom lub przyjmowanie zwrotów od klientów, nawet jeśli sprzedawcy nie mają tych produktów w sklepie (innymi słowy produkty nie wchodzą w skład asortymentu sklepu).</span><span class="sxs-lookup"><span data-stu-id="240ac-104">A common scenario for any retailer is to sell products to their customers or accept returns from their customers even if they don’t carry the specific products in their store (in other words, the products are not assorted to the store).</span></span>
<span data-ttu-id="240ac-105">Poniżej przedstawiono niektóre typowe scenariusze:</span><span class="sxs-lookup"><span data-stu-id="240ac-105">Here are some typical scenarios:</span></span>

+ <span data-ttu-id="240ac-106">Sprzedawca detaliczny nie posiada wszystkich swoich produktów w określonym sklepie.</span><span class="sxs-lookup"><span data-stu-id="240ac-106">A retailer doesn’t carry all its products in a specific store.</span></span> <span data-ttu-id="240ac-107">Pozostałe produkty są przechowywane w magazynie.</span><span class="sxs-lookup"><span data-stu-id="240ac-107">The remaining products are stored in the warehouse.</span></span> <span data-ttu-id="240ac-108">Pracownik sklepu może pomóc klientowi, wyszukując lub przeglądając produkty w magazynie, dodając je do koszyka, a następnie finalizując transakcję przez wybranie metody dostawy, takiej jak wysyłka na podany adres z magazynu lub osobisty odbiór produktu przez klienta z bieżącego sklepu lub z innego sklepu.</span><span class="sxs-lookup"><span data-stu-id="240ac-108">The store associate can assist the customer by searching or browsing for the products in the warehouse, add them to the cart, and complete the checkout by selecting a delivery method, such as shipping to an address from the warehouse or letting the customer pick up the product from the current store or from another store.</span></span>
+ <span data-ttu-id="240ac-109">Sprzedawca nie ma określonych produktów w sklepie lub nie ma ich w sklepie odwiedzonym przez klienta, ale produkty są dostępne w innych sklepach.</span><span class="sxs-lookup"><span data-stu-id="240ac-109">A retailer doesn’t carry specific products in the store or doesn’t have them in stock at the store the customer visited, but the products are available in other stores.</span></span> <span data-ttu-id="240ac-110">Pracownik sklepu może pomóc klientowi, wyszukując lub przeglądając produkty w sklepie, dodając je do koszyka, a następnie finalizując transakcję przez wybranie metody dostawy.</span><span class="sxs-lookup"><span data-stu-id="240ac-110">The store associate can assist the customer by searching or browsing the products in the other store, add them to the cart, and complete the checkout by selecting a delivery method.</span></span>
+ <span data-ttu-id="240ac-111">Sprzedawca detaliczny ma wiele sklepów w danym mieście lub regionie i nie chce zmuszać klientów, aby zwracali produkty do tego samego sklepu, w którym je kupili.</span><span class="sxs-lookup"><span data-stu-id="240ac-111">A retailer has many stores in and around a specific city or zip code and doesn’t want to force the customers to return products to the same store they were purchased in.</span></span> <span data-ttu-id="240ac-112">Zamiast tego klienci mogą zwracać produkty do dowolnych sklepów.</span><span class="sxs-lookup"><span data-stu-id="240ac-112">Instead, customers can return products to any store.</span></span>


<span data-ttu-id="240ac-113">Te typowe scenariusze są dostępne dla sprzedawców detalicznych używających aplikacji Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="240ac-113">Those common scenarios are available for retailers using Dynamics 365 for Retail.</span></span> <span data-ttu-id="240ac-114">Aplikacja Retail oferuje następujące możliwości:</span><span class="sxs-lookup"><span data-stu-id="240ac-114">With Retail, you can:</span></span>
+ <span data-ttu-id="240ac-115">Wyszukiwanie lub przeglądanie produktów w innych sklepach.</span><span class="sxs-lookup"><span data-stu-id="240ac-115">Search or browse products at other stores.</span></span>
+ <span data-ttu-id="240ac-116">Wyszukiwanie lub przeglądanie wszystkich zwolnionych produktów.</span><span class="sxs-lookup"><span data-stu-id="240ac-116">Search or browse all released products.</span></span>
+ <span data-ttu-id="240ac-117">Tworzenie transakcji zapłaty przy kasie i wychodzenia z produktami ze sklepu lub tworzenie zamówień odbiorców.</span><span class="sxs-lookup"><span data-stu-id="240ac-117">Create cash-and-carry transactions or customer orders.</span></span>
+ <span data-ttu-id="240ac-118">Wybieranie opcji dostawy dla zamówień odbiorców.</span><span class="sxs-lookup"><span data-stu-id="240ac-118">Select delivery options for customer orders.</span></span>
+ <span data-ttu-id="240ac-119">Odbiór produktów w bieżącym sklepie lub innym sklepie.</span><span class="sxs-lookup"><span data-stu-id="240ac-119">Pick up products at the current store or another store.</span></span>
+ <span data-ttu-id="240ac-120">Anulowanie zamówienia w bieżącym sklepie lub innym sklepie.</span><span class="sxs-lookup"><span data-stu-id="240ac-120">Cancel an order at the current store or another store.</span></span>
+ <span data-ttu-id="240ac-121">Zwrot zamówionych towarów z paragonem lub bez w bieżącym lub innym sklepie.</span><span class="sxs-lookup"><span data-stu-id="240ac-121">Return an order with or without the receipt at the current store or another store.</span></span>

