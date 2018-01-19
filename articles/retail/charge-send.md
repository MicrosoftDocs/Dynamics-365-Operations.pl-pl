---
title: "Wysyłanie zamówienia z innego sklepu"
description: "W tym temacie opisano funkcję Wysyłanie opłaty."
author: ashishmsft
manager: AnnBe
ms.date: 10/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-10-10
ms.dyn365.ops.version: Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: ceea24519d641c676521771cee274feb64ca7783
ms.openlocfilehash: 43c8c185bd180f0de209b071bf93325fc24e517c
ms.contentlocale: pl-pl
ms.lasthandoff: 01/19/2018

---

# <a name="ship-an-order-from-a-different-store"></a><span data-ttu-id="43c40-103">Wysyłanie zamówienia z innego sklepu</span><span class="sxs-lookup"><span data-stu-id="43c40-103">Ship an order from a different store</span></span>

<span data-ttu-id="43c40-104">Funkcja Wysyłanie opłaty w rozwiązaniu Dynamics 365 for Retail umożliwia złożenie zamówień odbiorców w jednym sklepie i wysłanie ich z innego sklepu.</span><span class="sxs-lookup"><span data-stu-id="43c40-104">With the Charge send feature in Dynamics 365 for Retail, customer orders can be placed in one store and shipped from another store.</span></span> <span data-ttu-id="43c40-105">Zamówienia odbiorców w kliencie punktu sprzedaży obsługują różne opcje realizacji.</span><span class="sxs-lookup"><span data-stu-id="43c40-105">Customer orders in the point of sale (POS) client support multiple fulfillment options.</span></span> <span data-ttu-id="43c40-106">Przykłady opcji realizacji:</span><span class="sxs-lookup"><span data-stu-id="43c40-106">Some examples of fulfillment options include:</span></span>
-   <span data-ttu-id="43c40-107">Odbiór z tego samego sklepu w innym dniu.</span><span class="sxs-lookup"><span data-stu-id="43c40-107">Pick up from the same store on a different date.</span></span>
-   <span data-ttu-id="43c40-108">Odbiór z innego sklepu w tym samym lub innym dniu.</span><span class="sxs-lookup"><span data-stu-id="43c40-108">Pick up from a different store on the same date or a different date.</span></span>
-   <span data-ttu-id="43c40-109">Wysyłka do domyślnego magazynu wysyłki przypisanego do sklepu i dostawa w określonym dniu.</span><span class="sxs-lookup"><span data-stu-id="43c40-109">Ship from the default shipping warehouse that is assigned to the store, and deliver on a specific date.</span></span>

<span data-ttu-id="43c40-110">Funkcja Wysyłanie opłaty wykorzystuje następujące operacje punktu sprzedaży: Wyślij wszystkie produkty i Wyślij zaznaczone produkty.</span><span class="sxs-lookup"><span data-stu-id="43c40-110">The Charge send feature uses the following POS operations: Ship all products and Ship selected products.</span></span> <span data-ttu-id="43c40-111">Umożliwia to pracownikowi sklepu wybranie lokalizacji „wyślij z”, z której można zrealizować zamówienie lub wiersz zamówienia.</span><span class="sxs-lookup"><span data-stu-id="43c40-111">This allows the store clerk to select the “ship from” location that the order or order line can be fulfilled from.</span></span> <span data-ttu-id="43c40-112">Domyślnie lokalizacja „wyślij z” to magazyn wysyłki skojarzony ze sklepem.</span><span class="sxs-lookup"><span data-stu-id="43c40-112">By default, the “ship from” location is the shipping warehouse that is associated with the store.</span></span> <span data-ttu-id="43c40-113">Jednakże pracownik sklepu może zmienić tę lokalizację i wybrać dowolny sklep zdefiniowany w grupie lokalizatora sklepów przypisanej do sklepu.</span><span class="sxs-lookup"><span data-stu-id="43c40-113">However, the store clerk can change this location and select any store that is defined in the store locator group that is assigned to the store.</span></span> 

<span data-ttu-id="43c40-114">Możliwość wyboru adresów „wyślij do” pozostaje bez zmian.</span><span class="sxs-lookup"><span data-stu-id="43c40-114">The ability to select “ship to” addresses remains unchanged.</span></span> 

<span data-ttu-id="43c40-115">Metody wysyłki, których można użyć do realizacji wiersza zamówienia są oparte na konfiguracji prawidłowych trybów dostawy produktów i adresów.</span><span class="sxs-lookup"><span data-stu-id="43c40-115">The shipping methods that can be used to fulfill the order line are based on the configuration of valid modes of delivery for products and addresses.</span></span> <span data-ttu-id="43c40-116">Ponieważ reguły dotyczące prawidłowych trybów dostawy są obsługiwane tylko w Centrali sieci sprzedaży (HQ), klient punktu sprzedaży wykonuje wywołanie w czasie rzeczywistym, aby pobrać prawidłowe tryby dostawy dla wiersza wysyłki.</span><span class="sxs-lookup"><span data-stu-id="43c40-116">Because the rules about valid of modes of delivery are maintained only in the Retail headquarters (HQ), the POS client makes a real-time call to fetch the valid modes of delivery for a ship line.</span></span> 


