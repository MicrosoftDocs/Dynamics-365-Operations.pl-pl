---
title: Dostępność zapasów w podwójnym zapisie
description: Ten temat zawiera informacje o sposobie sprawdzania dostępności zapasów w trybie podwójnego zapisu.
author: yijialuan
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: riluan
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: 227a2062a7985a787f8278c196f7df2fb6f31691
ms.sourcegitcommit: cf709f1421a0bf66ecea493088ecb4eb08004187
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/12/2020
ms.locfileid: "3443879"
---
# <a name="inventory-availability-in-dual-write"></a><span data-ttu-id="b4282-103">Dostępność zapasów w podwójnym zapisie</span><span class="sxs-lookup"><span data-stu-id="b4282-103">Inventory availability in dual-write</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b4282-104">Korzystając z dostępności zapasów, można sprawdzić stan zapasów przed dodaniem produktu do stron **Oferty**, **Zamówienia** lub **Faktury** w Microsoft Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="b4282-104">By using inventory availability, you can check your inventory before you add a product to the **Quotations**, **Orders**, or **Invoices** page in Microsoft Dynamics 365 Sales.</span></span> <span data-ttu-id="b4282-105">Na przykład sprawdzenie zapasów i określenie daty realizacji jest jednym z kluczowych zadań w procesie [od prospektu do gotówki](dual-write-prospect-to-cash.md).</span><span class="sxs-lookup"><span data-stu-id="b4282-105">For example, you check inventory and determine a fulfillment date as one key task in the [prospect-to-cash](dual-write-prospect-to-cash.md) process.</span></span>

<span data-ttu-id="b4282-106">Jeśli nie ma wystarczającej ilości zapasów, można oszacować datę dostawy na podstawie przewidywanych przyjęć i problemów z zapasami.</span><span class="sxs-lookup"><span data-stu-id="b4282-106">If you don't have enough inventory, you can estimate a delivery date, based on projected inventory receipts and issues.</span></span> <span data-ttu-id="b4282-107">Można również sprawdzić informacje o dostępności zapasów (ATP), w której można znaleźć ilość ATP w wstępnie zdefiniowanym horyzoncie czasowym.</span><span class="sxs-lookup"><span data-stu-id="b4282-107">You can also check the product's available-to-promise (ATP) information, where you can find the ATP quantity in the predefined time fence.</span></span>

## <a name="on-hand-inventory"></a><span data-ttu-id="b4282-108">Dostępne zapasy</span><span class="sxs-lookup"><span data-stu-id="b4282-108">On-hand inventory</span></span>

<span data-ttu-id="b4282-109">W Dynamics 365 Sales jest dodany nowy przycisk **Dostępne zapasy** do nagłówka stron **Oferty**, **Zamówienia** i **Faktury**.</span><span class="sxs-lookup"><span data-stu-id="b4282-109">In Dynamics 365 Sales, a new **On-hand Inventory** button has been added to the header of the **Quotes**, **Orders**, and **Invoices** pages.</span></span> <span data-ttu-id="b4282-110">Wybranie tego przycisku powoduje wyświetlenie okna dialogowego, w którym można określić firmę i produkt, dla którego mają zostać sprawdzone dostępne zapasy.</span><span class="sxs-lookup"><span data-stu-id="b4282-110">When you select this button, a dialog box appears, where you can specify the company and the product that you want to check the on-hand inventory for.</span></span> <span data-ttu-id="b4282-111">W tym oknie dialogowym są wyświetlane takie same informacje jak [Dostępne zapasy](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span><span class="sxs-lookup"><span data-stu-id="b4282-111">This dialog box shows the same information as [On-hand inventory](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span></span>

<span data-ttu-id="b4282-112">W oknie dialogowym są zwracane informacje o zapasach z Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b4282-112">The dialog box returns the inventory information from Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="b4282-113">Informacje te obejmują następujące ilości:</span><span class="sxs-lookup"><span data-stu-id="b4282-113">This information includes the following quantities:</span></span>

- <span data-ttu-id="b4282-114">Ilość dostępnych zapasów</span><span class="sxs-lookup"><span data-stu-id="b4282-114">On-hand quantity</span></span>
- <span data-ttu-id="b4282-115">Zarezerowowana dostępna ilość</span><span class="sxs-lookup"><span data-stu-id="b4282-115">Reserved on-hand quantity</span></span>
- <span data-ttu-id="b4282-116">Dostępna ilość na stanie</span><span class="sxs-lookup"><span data-stu-id="b4282-116">Available on-hand quantity</span></span>
- <span data-ttu-id="b4282-117">Ilość zamówiona</span><span class="sxs-lookup"><span data-stu-id="b4282-117">Ordered quantity</span></span>
- <span data-ttu-id="b4282-118">Ilość na zamówienie</span><span class="sxs-lookup"><span data-stu-id="b4282-118">On-order quantity</span></span>
- <span data-ttu-id="b4282-119">Zarezerwowana zamówiona ilość</span><span class="sxs-lookup"><span data-stu-id="b4282-119">Reserved ordered quantity</span></span>
- <span data-ttu-id="b4282-120">Łączna dostępna ilość</span><span class="sxs-lookup"><span data-stu-id="b4282-120">Total available quantity</span></span>

## <a name="atp-information"></a><span data-ttu-id="b4282-121">Informacje ATP</span><span class="sxs-lookup"><span data-stu-id="b4282-121">ATP information</span></span>

<span data-ttu-id="b4282-122">W Sales nowy przyscisk **Informacje ATP** został dodany do wiersza pozycji na stronach **Oferty**, **Zamówienia** i **Faktury**.</span><span class="sxs-lookup"><span data-stu-id="b4282-122">In Sales, a new **ATP Information** button has been added to line items on the **Quotes**, **Orders**, and **Invoices** pages.</span></span> <span data-ttu-id="b4282-123">Wybranie przycisku powoduje wyświetlenie okna dialogowego, w którym można określić firmę, produkt, oddział zapasów, magazyn zapasów i ilośc zamówienia.</span><span class="sxs-lookup"><span data-stu-id="b4282-123">When you select this button, a dialog box appears, where you can specify the company, product, inventory site, inventory warehouse, and order quantity.</span></span> <span data-ttu-id="b4282-124">To okno dialogowe ma takie same ustawienia, które są opisane w obszarze [Zobowiązanie do zamówienia](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span><span class="sxs-lookup"><span data-stu-id="b4282-124">This dialog box has the same settings that are described in [Order promising](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span></span>

<span data-ttu-id="b4282-125">Okno dialogowe zwraca informacje o ATP z Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b4282-125">The dialog box returns the ATP information from Supply Chain Management.</span></span> <span data-ttu-id="b4282-126">Informacje te obejmują następujące ilości:</span><span class="sxs-lookup"><span data-stu-id="b4282-126">This information includes the following quantities:</span></span>

- <span data-ttu-id="b4282-127">Ilość ATP</span><span class="sxs-lookup"><span data-stu-id="b4282-127">ATP quantity</span></span>
- <span data-ttu-id="b4282-128">Ilość przychodu</span><span class="sxs-lookup"><span data-stu-id="b4282-128">Receipt quantity</span></span>
- <span data-ttu-id="b4282-129">Ilość rozchodu</span><span class="sxs-lookup"><span data-stu-id="b4282-129">Issue quantity</span></span>
- <span data-ttu-id="b4282-130">Ilość dostępnych zapasów</span><span class="sxs-lookup"><span data-stu-id="b4282-130">On-hand quantity</span></span>
