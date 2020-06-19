---
title: Dostępność zapasów w podwójnym zapisie
description: Ten temat zawiera informacje o sprawdzaniu dostępności zapasów w trybie podwójnego zapisu.
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
ms.openlocfilehash: dd0995eb8c70ed06cdc3c0f6a28b13b117297533
ms.sourcegitcommit: be7e4378c8122c6e7cfc4e7991efbdffee45e006
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2020
ms.locfileid: "3426989"
---
# <a name="inventory-availability"></a><span data-ttu-id="87272-103">Dostępność zapasów</span><span class="sxs-lookup"><span data-stu-id="87272-103">Inventory availability</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="87272-104">Korzystając z dostępności zapasów, można sprawdzić stan zapasów przed dodaniem produktu doformularzy **Oferty**, **Zamówienia** lub **Faktury** w aplikacjach opartych na modelu w Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="87272-104">Using inventory availability, you can check your inventory before you add a product into the **Quotes**, **Orders**, or **Invoices** forms in model-driven apps in Dynamics 365.</span></span> <span data-ttu-id="87272-105">Na przykład sprawdzenie zapasów i określenie daty realizacji jest kluczowym zadaniem w procesie [od prospektu do gotówki](dual-write-prospect-to-cash.md).</span><span class="sxs-lookup"><span data-stu-id="87272-105">For example, checking inventory and determining a fulfullment date is a key task in the [prospect-to-cash](dual-write-prospect-to-cash.md) process.</span></span> <span data-ttu-id="87272-106">Jeśli nie ma wystarczającej ilości zapasów, można oszacować datę dostawy na podstawie przewidywanych przyjęć i problemów z zapasami.</span><span class="sxs-lookup"><span data-stu-id="87272-106">If you don't have enough inventory, you can estimate a delivery date based on projected inventory receipts and issues.</span></span> <span data-ttu-id="87272-107">Można również sprawdzić informacje o dostępności zapasów (ATP), w której można znaleźć ilość ATP w wstępnie zdefiniowanym horyzoncie czasowym.</span><span class="sxs-lookup"><span data-stu-id="87272-107">You can also check the product's available-to-promise (ATP) information, where you can find the ATP quantity in the pre-defined time fence.</span></span>

## <a name="on-hand-inventory"></a><span data-ttu-id="87272-108">Dostępne zapasy</span><span class="sxs-lookup"><span data-stu-id="87272-108">On-hand Inventory</span></span> 

<span data-ttu-id="87272-109">W nagłówku formularzy **Oferty**, **Zamówienia** lub **Faktury** w Dynamics 365 Sales jest dodawany nowy przycisk **Dostępne zapasy**.</span><span class="sxs-lookup"><span data-stu-id="87272-109">In the header of the **Quotes**, **Orders**, or **Invoices** forms in Dynamics 365 Sales, a new button **On-hand Inventory** is added.</span></span> <span data-ttu-id="87272-110">Kliknięcie przycisku powoduje wyświetlenie okna dialogowego, w którym można określić firmę i produkt, dla którego mają zostać sprawdzone dostępne zapasy.</span><span class="sxs-lookup"><span data-stu-id="87272-110">When you click the button, a dialog box appears and you can specify the company and the product for which you want to check the on-hand inventory.</span></span> <span data-ttu-id="87272-111">Usługa zwraca informacje o zapasach z Dynamics 365 Supply Chain Management i pokazuje te same informacje, co [Dostępne zapasy](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span><span class="sxs-lookup"><span data-stu-id="87272-111">It returns the inventory information from Dynamics 365 Supply Chain Management, and shows the same information as [On-hand inventory](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span></span> <span data-ttu-id="87272-112">Informacje te obejmują następujące ilości:</span><span class="sxs-lookup"><span data-stu-id="87272-112">The information includes these quantities:</span></span>

- <span data-ttu-id="87272-113">**Ilość dostępna**</span><span class="sxs-lookup"><span data-stu-id="87272-113">**On-hand Quantity**</span></span>
- <span data-ttu-id="87272-114">**Zarezerowowana ilość dostępna**</span><span class="sxs-lookup"><span data-stu-id="87272-114">**Reserved On-hand Quantity**</span></span>
- <span data-ttu-id="87272-115">**Dostępna ilość dostępna**</span><span class="sxs-lookup"><span data-stu-id="87272-115">**Available On-hand Quantity**</span></span>
- <span data-ttu-id="87272-116">**Ilość zamówiona**</span><span class="sxs-lookup"><span data-stu-id="87272-116">**Orderd Quantity**</span></span>
- <span data-ttu-id="87272-117">**Ilość na zamówienie**</span><span class="sxs-lookup"><span data-stu-id="87272-117">**On-order Quantity**</span></span>
- <span data-ttu-id="87272-118">**Zarezerwowana zamówiona ilość**</span><span class="sxs-lookup"><span data-stu-id="87272-118">**Reserved Ordered Quantity**</span></span>
- <span data-ttu-id="87272-119">**Łączna dostępna ilość**</span><span class="sxs-lookup"><span data-stu-id="87272-119">**Total Available Quantity**</span></span>

## <a name="atp-information"></a><span data-ttu-id="87272-120">Informacje ATP</span><span class="sxs-lookup"><span data-stu-id="87272-120">ATP information</span></span>

<span data-ttu-id="87272-121">W wierszu pozycji formularzy **Oferty**, **Zamówienia** lub **Faktury** w Dynamics 365 Sales jest dodawany nowy przycisk **Informacja ATP**.</span><span class="sxs-lookup"><span data-stu-id="87272-121">On line items of the **Quotes**, **Orders**, or **Invoices** forms in Dynamics 365 Sales, a new button **ATP Information** is added.</span></span> <span data-ttu-id="87272-122">Kliknięcie przycisku powoduje wyświetlenie okna dialogowego, w którym można określić firmę, produkt, oddział zapasów, magazyn zapasów i ilośc zamówienia.</span><span class="sxs-lookup"><span data-stu-id="87272-122">When you click the button, a dialog box appears and you can specify the company, product, inventory Site, inventory warehouse, and order quantity.</span></span> <span data-ttu-id="87272-123">Zwraca **Informacje ATP** z Supply Chain Management i pokazuje ustawienia opisane w [Zobowiązanie do zamówienia](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span><span class="sxs-lookup"><span data-stu-id="87272-123">It returns the **ATP Information** from Supply Chain Management and shows the settings descrbed in [Order promising](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span></span> <span data-ttu-id="87272-124">Informacje obejmują **Ilość ATP**, **Ilość przyjęta**, **Ilość wydana** oraz **Ilość dostępnych zapasów**.</span><span class="sxs-lookup"><span data-stu-id="87272-124">The information includes **ATP quantity**, **Receipt quantity**, **Issue quantity**, and **On-hand quantity**.</span></span>
