---
title: Harmonogramy dostaw
description: "Harmonogramy dostaw umożliwiają śledzenie ilości w wierszu zamówienia, gdy jest używanych wiele dostaw dla jednego zamówienia sprzedaży, oferty sprzedaży lub zamówienia zakupu."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchDeliverySchedule, SalesDeliverySchedule, SalesQuotationDeliverySchedule
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 213984
ms.assetid: 44cac104-c36c-4371-a992-9178b3fd65e9
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 84ae84a567e5f45bc0b20538d04917c6feb21336
ms.contentlocale: pl-pl
ms.lasthandoff: 07/18/2017

---

# <a name="delivery-schedules"></a><span data-ttu-id="ca49c-103">Harmonogramy dostaw</span><span class="sxs-lookup"><span data-stu-id="ca49c-103">Delivery schedules</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="ca49c-104">Harmonogramy dostaw umożliwiają śledzenie ilości w wierszu zamówienia, gdy jest używanych wiele dostaw dla jednego zamówienia sprzedaży, oferty sprzedaży lub zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="ca49c-104">Delivery schedules allow you to track order line quantity when you are using multiple deliveries for a single sales order, sales quotation, or purchase order.</span></span>

<span data-ttu-id="ca49c-105">Harmonogramu dostaw używa się, gdy łączna ilość pozycji w wierszu zamówienia lub oferty musi być dostarczona w wielu wysyłkach.</span><span class="sxs-lookup"><span data-stu-id="ca49c-105">Use a delivery schedule when the total quantity on an order or quotation line must be delivered in multiple shipments.</span></span> <span data-ttu-id="ca49c-106">Każdej wysyłce odpowiada osobny wiersz dostawy.</span><span class="sxs-lookup"><span data-stu-id="ca49c-106">Individual shipments are represented by delivery lines.</span></span> <span data-ttu-id="ca49c-107">Dwa lub więcej wierszy zamówienia tworzą harmonogram dostawy.</span><span class="sxs-lookup"><span data-stu-id="ca49c-107">Two or more delivery lines make up one delivery schedule.</span></span> <span data-ttu-id="ca49c-108">Wiersze dostawy mogą mieć różne daty dostawy, ilości, metody dostawy i wymiary magazynowania, takie jak oddział i magazyn.</span><span class="sxs-lookup"><span data-stu-id="ca49c-108">The delivery lines can have different delivery dates, quantities, modes of delivery, and storage dimensions, such as site and warehouse.</span></span>  

<span data-ttu-id="ca49c-109">**Przykład harmonogramu dostaw**</span><span class="sxs-lookup"><span data-stu-id="ca49c-109">**Example of a delivery schedule**</span></span>

|                                   |                                          |
|-----------------------------------|------------------------------------------|
| <span data-ttu-id="ca49c-110">Suma zamówienia (wiersz oryginalnego zamówienia)</span><span class="sxs-lookup"><span data-stu-id="ca49c-110">Total order (original order line)</span></span> | <span data-ttu-id="ca49c-111">600 krzeseł</span><span class="sxs-lookup"><span data-stu-id="ca49c-111">600 chairs</span></span>                               |
| <span data-ttu-id="ca49c-112">Wymagany harmonogram dostaw</span><span class="sxs-lookup"><span data-stu-id="ca49c-112">Requested delivery schedule</span></span>       | <span data-ttu-id="ca49c-113">100 krzeseł na miesiąc</span><span class="sxs-lookup"><span data-stu-id="ca49c-113">100 chairs per month</span></span>                     |
| <span data-ttu-id="ca49c-114">Żądany przedział czasowy dostaw</span><span class="sxs-lookup"><span data-stu-id="ca49c-114">Requested time frame for delivery</span></span> | <span data-ttu-id="ca49c-115">6 miesięcy, w pierwszym dniu każdego miesiąca</span><span class="sxs-lookup"><span data-stu-id="ca49c-115">6 months, on the first day of each month</span></span> |

<span data-ttu-id="ca49c-116">W tym scenariuszu klient żąda dostawy 600 krzeseł w partiach po 100 sztuk w okresie 6 miesięcy.</span><span class="sxs-lookup"><span data-stu-id="ca49c-116">In this scenario, the customer requests delivery of 600 chairs in batches of 100 chairs over a period of six months.</span></span> <span data-ttu-id="ca49c-117">Aby śledzić wymagania dostawy, można utworzyć harmonogram dostaw.</span><span class="sxs-lookup"><span data-stu-id="ca49c-117">To keep track of the delivery requirements, you create a delivery schedule.</span></span> <span data-ttu-id="ca49c-118">Na stronie harmonogram dostaw można utworzyć sześć osobnych wierszy dostawy.</span><span class="sxs-lookup"><span data-stu-id="ca49c-118">On the delivery schedule page, you create six separate delivery lines.</span></span> <span data-ttu-id="ca49c-119">Każdy wiersz dostawy zawiera 100 krzeseł i wskazuje datę ich dostarczenia do odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="ca49c-119">Each delivery line contains 100 chairs and indicates the delivery date for those 100 chairs.</span></span> <span data-ttu-id="ca49c-120">W tym przypadku każdy wiersz jest przesunięty na pierwsze dni kolejnych sześciu miesięcy.</span><span class="sxs-lookup"><span data-stu-id="ca49c-120">In this case, each line is offset on the first of the month for six consecutive months.</span></span>  

<span data-ttu-id="ca49c-121">Tworząc harmonogram dostaw, typ wiersza oryginalnego zamówienia jest automatycznie zmieniany na **Wiersz zamówienia z wieloma dostawami**.</span><span class="sxs-lookup"><span data-stu-id="ca49c-121">When you create a delivery schedule, the type of the original order line is automatically changed to **Order line with multiple deliveries**.</span></span> <span data-ttu-id="ca49c-122">Wiersz tego typu jest określany jako wiersz handlowy i jest oznaczony ikoną.</span><span class="sxs-lookup"><span data-stu-id="ca49c-122">A line of this type is referred to as a commercial line and is marked by an icon.</span></span> <span data-ttu-id="ca49c-123">Wiersz dostawy jest oznaczony inną ikoną.</span><span class="sxs-lookup"><span data-stu-id="ca49c-123">The delivery line is marked by a different icon.</span></span> <span data-ttu-id="ca49c-124">Jeśli zmienisz ilość w wierszu dostawy, wiersz handlowy zostanie zaktualizowany do łącznej ilości harmonogramu dostawy.</span><span class="sxs-lookup"><span data-stu-id="ca49c-124">If you change a quantity on a delivery line, the commercial line is updated to the total quantity of the delivery schedule.</span></span> <span data-ttu-id="ca49c-125">Jeśli w umowie handlowej zdefiniowano łączny rabat na zamówienie, harmonogram dostaw zapewnia, że zamówienie będzie kwalifikowało się do otrzymania rabatu końcowego, nawet jeśli zostanie podzielone na osobne dostawy.</span><span class="sxs-lookup"><span data-stu-id="ca49c-125">If a trade agreement has defined a total discount for the order, the delivery schedule ensures that your order is eligible for the total order discount, even when the order is split into separate deliveries.</span></span>  

<span data-ttu-id="ca49c-126">Zamówienia z harmonogramem dostaw są przetwarzane na podstawie wierszy dostawy.</span><span class="sxs-lookup"><span data-stu-id="ca49c-126">Orders that have a delivery schedule are processed against the delivery lines.</span></span> <span data-ttu-id="ca49c-127">Przetwarzanie obejmuje księgowanie dokumentów dostawy, dokumentów przyjęcia produktów, i fakturowanie.</span><span class="sxs-lookup"><span data-stu-id="ca49c-127">Processing includes the posting of packing slips, product receipts, and invoicing.</span></span>  

<span data-ttu-id="ca49c-128">Wydruki dokumentów zamówień i ofert z harmonogramem dostaw zawierają tylko wiersze dostaw.</span><span class="sxs-lookup"><span data-stu-id="ca49c-128">Document printouts of orders and quotations that have a delivery schedule show only the delivery lines.</span></span> <span data-ttu-id="ca49c-129">Nie zawierają oryginalnych wierszy (handlowych).</span><span class="sxs-lookup"><span data-stu-id="ca49c-129">They don't show the original lines (commercial lines).</span></span> <span data-ttu-id="ca49c-130">**Uwaga:** w przypadku wykonania czynności opisanych poniżej będą widoczne tylko wiersze dostawy.</span><span class="sxs-lookup"><span data-stu-id="ca49c-130">**Note:** In addition, only the delivery lines are shown when you perform these actions:</span></span>

-   <span data-ttu-id="ca49c-131">Księgowanie</span><span class="sxs-lookup"><span data-stu-id="ca49c-131">Post</span></span>
-   <span data-ttu-id="ca49c-132">Kopiowanie stron</span><span class="sxs-lookup"><span data-stu-id="ca49c-132">Copy pages</span></span>
-   <span data-ttu-id="ca49c-133">Przeglądanie stron listy i raportów</span><span class="sxs-lookup"><span data-stu-id="ca49c-133">Browse list pages and reports</span></span>

<span data-ttu-id="ca49c-134">W przypadku potwierdzenia oferty sprzedaży wyświetlane zamówienia sprzedaży będą zawierały cały harmonogram dostaw, łącznie z wierszami zamówienia, dla których określono wiele dostaw.</span><span class="sxs-lookup"><span data-stu-id="ca49c-134">When you confirm sales quotations, the resulting sales orders show the whole delivery schedule, even the order lines that have multiple deliveries.</span></span> <span data-ttu-id="ca49c-135">Ponadto cały harmonogram dostaw jest widoczny na wszystkich głównych stronach, takich jak zamówienia sprzedaży, oferty sprzedaży i zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="ca49c-135">In addition, the whole delivery schedule is shown on all the major pages, such as sales orders, sales quotations, and purchase orders.</span></span>




