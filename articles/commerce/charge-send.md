---
title: Wysyłka zamówień z innego sklepu za pomocą funkcji Wysyłanie opłaty
description: W tym temacie opisano funkcję Wysyłanie opłaty.
author: ashishmsft
manager: AnnBe
ms.date: 10/10/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-10-10
ms.dyn365.ops.version: Retail July 2017 update
ms.openlocfilehash: 0bbebcc7b2ab89bf2f5db7294acfca1d8a5ad96e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4414932"
---
# <a name="ship-orders-from-another-store-by-using-the-charge-send-feature"></a><span data-ttu-id="835b7-103">Wysyłka zamówień z innego sklepu za pomocą funkcji Wysyłanie opłaty</span><span class="sxs-lookup"><span data-stu-id="835b7-103">Ship orders from another store by using the Charge send feature</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="835b7-104">Funkcja Wysyłanie opłaty w rozwiązaniu Commerce umożliwia złożenie zamówień odbiorców w jednym sklepie i wysłanie ich z innego sklepu.</span><span class="sxs-lookup"><span data-stu-id="835b7-104">With the Charge send feature in Commerce, customer orders can be placed in one store and shipped from another store.</span></span>

<span data-ttu-id="835b7-105">Zamówienia odbiorców w kliencie punktu sprzedaży obsługują różne opcje realizacji.</span><span class="sxs-lookup"><span data-stu-id="835b7-105">Customer orders in the point of sale (POS) client support multiple fulfillment options.</span></span> <span data-ttu-id="835b7-106">Przykłady opcji realizacji:</span><span class="sxs-lookup"><span data-stu-id="835b7-106">Some examples of fulfillment options include:</span></span>

- <span data-ttu-id="835b7-107">Odbiór z tego samego sklepu w innym dniu.</span><span class="sxs-lookup"><span data-stu-id="835b7-107">Pick up from the same store on a different date.</span></span>
- <span data-ttu-id="835b7-108">Odbiór z innego sklepu w tym samym lub innym dniu.</span><span class="sxs-lookup"><span data-stu-id="835b7-108">Pick up from a different store on the same date or a different date.</span></span>
- <span data-ttu-id="835b7-109">Wysyłka do domyślnego magazynu wysyłki przypisanego do sklepu i dostawa w określonym dniu.</span><span class="sxs-lookup"><span data-stu-id="835b7-109">Ship from the default shipping warehouse that is assigned to the store, and deliver on a specific date.</span></span>

<span data-ttu-id="835b7-110">Funkcja Wysyłanie opłaty wykorzystuje następujące operacje punktu sprzedaży: Wyślij wszystkie produkty i Wyślij zaznaczone produkty.</span><span class="sxs-lookup"><span data-stu-id="835b7-110">The Charge send feature uses the following POS operations: Ship all products and Ship selected products.</span></span> <span data-ttu-id="835b7-111">Umożliwia to pracownikowi sklepu wybranie lokalizacji „wyślij z”, z której można zrealizować zamówienie lub wiersz zamówienia.</span><span class="sxs-lookup"><span data-stu-id="835b7-111">This allows the store clerk to select the "ship from" location that the order or order line can be fulfilled from.</span></span> <span data-ttu-id="835b7-112">Domyślnie lokalizacja „wyślij z” to magazyn wysyłki skojarzony ze sklepem.</span><span class="sxs-lookup"><span data-stu-id="835b7-112">By default, the "ship from" location is the shipping warehouse that is associated with the store.</span></span> <span data-ttu-id="835b7-113">Jednakże pracownik sklepu może zmienić tę lokalizację i wybrać dowolny sklep zdefiniowany w grupie lokalizatora sklepów przypisanej do sklepu.</span><span class="sxs-lookup"><span data-stu-id="835b7-113">However, the store clerk can change this location and select any store that is defined in the store locator group that is assigned to the store.</span></span>

<span data-ttu-id="835b7-114">Możliwość wyboru adresów „wyślij do” pozostaje bez zmian.</span><span class="sxs-lookup"><span data-stu-id="835b7-114">The ability to select "ship to" addresses remains unchanged.</span></span>

<span data-ttu-id="835b7-115">Metody wysyłki, których można użyć do realizacji wiersza zamówienia są oparte na konfiguracji prawidłowych trybów dostawy produktów i adresów.</span><span class="sxs-lookup"><span data-stu-id="835b7-115">The shipping methods that can be used to fulfill the order line are based on the configuration of valid modes of delivery for products and addresses.</span></span> <span data-ttu-id="835b7-116">Ponieważ reguły dotyczące prawidłowych trybów dostawy są obsługiwane tylko w Headquarters (HQ), klient punktu sprzedaży wykonuje wywołanie w czasie rzeczywistym, aby pobrać prawidłowe tryby dostawy dla wiersza wysyłki.</span><span class="sxs-lookup"><span data-stu-id="835b7-116">Because the rules about valid of modes of delivery are maintained only in the Headquarters (HQ), the POS client makes a real-time call to fetch the valid modes of delivery for a ship line.</span></span>
