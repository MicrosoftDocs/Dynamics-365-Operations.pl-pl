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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: riluan
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: 4d1022eec633bf0a9edb4d5b26982853cec836d7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4456231"
---
# <a name="inventory-availability-in-dual-write"></a><span data-ttu-id="4f277-103">Dostępność zapasów w podwójnym zapisie</span><span class="sxs-lookup"><span data-stu-id="4f277-103">Inventory availability in dual-write</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4f277-104">Korzystając z dostępności zapasów, można sprawdzić stan zapasów przed dodaniem produktu do stron **Oferty**, **Zamówienia** lub **Faktury** w Microsoft Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="4f277-104">By using inventory availability, you can check your inventory before you add a product to the **Quotations**, **Orders**, or **Invoices** page in Microsoft Dynamics 365 Sales.</span></span> <span data-ttu-id="4f277-105">Na przykład sprawdzenie zapasów i określenie daty realizacji jest jednym z kluczowych zadań w procesie [od prospektu do gotówki](dual-write-prospect-to-cash.md).</span><span class="sxs-lookup"><span data-stu-id="4f277-105">For example, you check inventory and determine a fulfillment date as one key task in the [prospect-to-cash](dual-write-prospect-to-cash.md) process.</span></span>

<span data-ttu-id="4f277-106">Jeśli nie ma wystarczającej ilości zapasów, można oszacować datę dostawy na podstawie przewidywanych przyjęć i problemów z zapasami.</span><span class="sxs-lookup"><span data-stu-id="4f277-106">If you don't have enough inventory, you can estimate a delivery date, based on projected inventory receipts and issues.</span></span> <span data-ttu-id="4f277-107">Można również sprawdzić informacje o dostępności zapasów (ATP), w której można znaleźć ilość ATP w wstępnie zdefiniowanym horyzoncie czasowym.</span><span class="sxs-lookup"><span data-stu-id="4f277-107">You can also check the product's available-to-promise (ATP) information, where you can find the ATP quantity in the predefined time fence.</span></span>

## <a name="on-hand-inventory"></a><span data-ttu-id="4f277-108">Dostępne zapasy</span><span class="sxs-lookup"><span data-stu-id="4f277-108">On-hand inventory</span></span>

<span data-ttu-id="4f277-109">W Dynamics 365 Sales jest dodany nowy przycisk **Dostępne zapasy** do nagłówka stron **Oferty**, **Zamówienia** i **Faktury**.</span><span class="sxs-lookup"><span data-stu-id="4f277-109">In Dynamics 365 Sales, a new **On-hand Inventory** button has been added to the header of the **Quotes**, **Orders**, and **Invoices** pages.</span></span> <span data-ttu-id="4f277-110">Wybranie tego przycisku powoduje wyświetlenie okna dialogowego, w którym można określić firmę i produkt, dla którego mają zostać sprawdzone dostępne zapasy.</span><span class="sxs-lookup"><span data-stu-id="4f277-110">When you select this button, a dialog box appears, where you can specify the company and the product that you want to check the on-hand inventory for.</span></span> <span data-ttu-id="4f277-111">W tym oknie dialogowym są wyświetlane takie same informacje jak [Dostępne zapasy](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span><span class="sxs-lookup"><span data-stu-id="4f277-111">This dialog box shows the same information as [On-hand inventory](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span></span>

<span data-ttu-id="4f277-112">W oknie dialogowym są zwracane informacje o zapasach z Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="4f277-112">The dialog box returns the inventory information from Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="4f277-113">Informacje te obejmują następujące ilości:</span><span class="sxs-lookup"><span data-stu-id="4f277-113">This information includes the following quantities:</span></span>

- <span data-ttu-id="4f277-114">Ilość dostępnych zapasów</span><span class="sxs-lookup"><span data-stu-id="4f277-114">On-hand quantity</span></span>
- <span data-ttu-id="4f277-115">Zarezerowowana dostępna ilość</span><span class="sxs-lookup"><span data-stu-id="4f277-115">Reserved on-hand quantity</span></span>
- <span data-ttu-id="4f277-116">Dostępna ilość na stanie</span><span class="sxs-lookup"><span data-stu-id="4f277-116">Available on-hand quantity</span></span>
- <span data-ttu-id="4f277-117">Ilość zamówiona</span><span class="sxs-lookup"><span data-stu-id="4f277-117">Ordered quantity</span></span>
- <span data-ttu-id="4f277-118">Ilość na zamówienie</span><span class="sxs-lookup"><span data-stu-id="4f277-118">On-order quantity</span></span>
- <span data-ttu-id="4f277-119">Zarezerwowana zamówiona ilość</span><span class="sxs-lookup"><span data-stu-id="4f277-119">Reserved ordered quantity</span></span>
- <span data-ttu-id="4f277-120">Łączna dostępna ilość</span><span class="sxs-lookup"><span data-stu-id="4f277-120">Total available quantity</span></span>

## <a name="atp-information"></a><span data-ttu-id="4f277-121">Informacje ATP</span><span class="sxs-lookup"><span data-stu-id="4f277-121">ATP information</span></span>

<span data-ttu-id="4f277-122">W Sales nowy przyscisk **Informacje ATP** został dodany do wiersza pozycji na stronach **Oferty**, **Zamówienia** i **Faktury**.</span><span class="sxs-lookup"><span data-stu-id="4f277-122">In Sales, a new **ATP Information** button has been added to line items on the **Quotes**, **Orders**, and **Invoices** pages.</span></span> <span data-ttu-id="4f277-123">Wybranie przycisku powoduje wyświetlenie okna dialogowego, w którym można określić firmę, produkt, oddział zapasów, magazyn zapasów i ilośc zamówienia.</span><span class="sxs-lookup"><span data-stu-id="4f277-123">When you select this button, a dialog box appears, where you can specify the company, product, inventory site, inventory warehouse, and order quantity.</span></span> <span data-ttu-id="4f277-124">To okno dialogowe ma takie same ustawienia, które są opisane w obszarze [Zobowiązanie do zamówienia](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span><span class="sxs-lookup"><span data-stu-id="4f277-124">This dialog box has the same settings that are described in [Order promising](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span></span>

<span data-ttu-id="4f277-125">Okno dialogowe zwraca informacje o ATP z Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="4f277-125">The dialog box returns the ATP information from Supply Chain Management.</span></span> <span data-ttu-id="4f277-126">Informacje te obejmują następujące ilości:</span><span class="sxs-lookup"><span data-stu-id="4f277-126">This information includes the following quantities:</span></span>

- <span data-ttu-id="4f277-127">Ilość ATP</span><span class="sxs-lookup"><span data-stu-id="4f277-127">ATP quantity</span></span>
- <span data-ttu-id="4f277-128">Ilość przychodu</span><span class="sxs-lookup"><span data-stu-id="4f277-128">Receipt quantity</span></span>
- <span data-ttu-id="4f277-129">Ilość rozchodu</span><span class="sxs-lookup"><span data-stu-id="4f277-129">Issue quantity</span></span>
- <span data-ttu-id="4f277-130">Ilość dostępnych zapasów</span><span class="sxs-lookup"><span data-stu-id="4f277-130">On-hand quantity</span></span>
