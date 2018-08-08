---
title: "Monitorowanie zapasów konsygnacyjnych poprzez współpracę z dostawcami"
description: "Ta procedura przedstawia sposób wykorzystywania portalu współpracy z dostawcami do zobaczenia informacji o poziomie zapasów produktu, które umieszczono w konsygnacji u odbiorcy."
author: mkirknel
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 8e4a620fe5f5ab3c0fae8b04d79e9912111b7ece
ms.contentlocale: pl-pl
ms.lasthandoff: 08/07/2018

---
# <a name="monitor-consignment-inventory-using-vendor-collaboration"></a><span data-ttu-id="642ba-103">Monitorowanie zapasów konsygnacyjnych poprzez współpracę z dostawcami</span><span class="sxs-lookup"><span data-stu-id="642ba-103">Monitor consignment inventory using vendor collaboration</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="642ba-104">Ta procedura przedstawia sposób wykorzystywania portalu współpracy z dostawcami do zobaczenia informacji o poziomie zapasów produktu, które umieszczono w konsygnacji u odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="642ba-104">This procedure shows how to use vendor collaboration to see information about the stock level of product that you have placed in consignment with a customer.</span></span> <span data-ttu-id="642ba-105">Można również monitorować zużycie zapasów, gdy odbiorca przejmie własność zapasów.</span><span class="sxs-lookup"><span data-stu-id="642ba-105">You can also monitor the consumption of the stock when the customer takes ownership of the inventory.</span></span> <span data-ttu-id="642ba-106">Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="642ba-106">You can use this procedure in the USMF demo data company.</span></span> <span data-ttu-id="642ba-107">Ta procedura dotyczy funkcji, która została dodana w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="642ba-107">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>


## <a name="view-consumed-inventory"></a><span data-ttu-id="642ba-108">Wyświetlanie zużytych zapasów</span><span class="sxs-lookup"><span data-stu-id="642ba-108">View consumed inventory</span></span>
1. <span data-ttu-id="642ba-109">Wybierz kolejno opcje Portal współpracy z dostawcami > Zapasy konsygnacyjne > Produkty odebrane z zapasów konsygnacyjnych.</span><span class="sxs-lookup"><span data-stu-id="642ba-109">Go to Vendor collaboration > Consignment inventory > Products received from consignment inventory.</span></span>
    * <span data-ttu-id="642ba-110">Na liście widać wiersze przyjęcia produktów, które zostały wygenerowane podczas zmiany własności zapasów konsygnacyjnych z dostawcy na odbiorcę.</span><span class="sxs-lookup"><span data-stu-id="642ba-110">The list shows the product receipt lines that were generated when ownership of the consignment inventory was changed from the vendor to the customer.</span></span> <span data-ttu-id="642ba-111">Może być konieczne przewinięcie w prawo, aby zobaczyć ilości i inne informacje.</span><span class="sxs-lookup"><span data-stu-id="642ba-111">You might have to scroll to the right to see quantities and other information.</span></span> <span data-ttu-id="642ba-112">Informacje na tej liście służą do generowania faktur dla odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="642ba-112">You can use the information in this list to generate invoices for your customer.</span></span> <span data-ttu-id="642ba-113">Można również wyeksportować dane do programu Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="642ba-113">You can also export the data to Microsoft Excel.</span></span>   
2. <span data-ttu-id="642ba-114">Kliknij opcję Wyświetl zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="642ba-114">Click View purchase order.</span></span>
3. <span data-ttu-id="642ba-115">Rozwiń sekcję Szczegóły wiersza.</span><span class="sxs-lookup"><span data-stu-id="642ba-115">Expand the Line details section.</span></span>
    * <span data-ttu-id="642ba-116">Wiersz jest oznaczony jako Konsygnacja, a sekcja nagłówka pokazuje, że zamówienie zakupu ma stan Otrzymane.</span><span class="sxs-lookup"><span data-stu-id="642ba-116">The line is marked as Consignment, and the header section shows that the purchase order has a status of Received.</span></span>  
4. <span data-ttu-id="642ba-117">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="642ba-117">Close the page.</span></span>

## <a name="view-on-hand-inventory"></a><span data-ttu-id="642ba-118">Wyświetlianie zapasów na stanie</span><span class="sxs-lookup"><span data-stu-id="642ba-118">View on-hand inventory</span></span>
1. <span data-ttu-id="642ba-119">Wybierz kolejno opcje Portal współpracy z dostawcami > Zapasy konsygnacyjne > Dostępne zapasy konsygnacyjne.</span><span class="sxs-lookup"><span data-stu-id="642ba-119">Go to Vendor collaboration > Consignment inventory > On-hand consignment inventory.</span></span>
    * <span data-ttu-id="642ba-120">Strona Dostępne zapasy konsygnacyjne pokazuje zapasy istniejące w magazynie odbiorcy, których jesteś właścicielem.</span><span class="sxs-lookup"><span data-stu-id="642ba-120">The On-hand consignment inventory page shows the stock that you own at the customer’s warehouse.</span></span> <span data-ttu-id="642ba-121">Można pokazać dodatkowe wymiary, takie jak oddział i magazyn, klikając kartę Wyświetl wymiary.</span><span class="sxs-lookup"><span data-stu-id="642ba-121">You can show additional dimensions, such as the site and warehouse, by clicking the Display dimensions tab.</span></span>   

