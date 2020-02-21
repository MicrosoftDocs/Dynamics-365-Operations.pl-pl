---
title: Zwróć produkty w ramach wielu zamówień klientów i faktur
description: W tym temacie opisano funkcje obsługi zwrotów z wielu zamówień i faktur w rozwiązaniu Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 03/05/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: c5f17424f0837344030f9ce2d2d037cde08c4e49
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "3004465"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a><span data-ttu-id="963b7-103">Zwracanie pozycji w ramach wielu zamówień i faktur odbiorców</span><span class="sxs-lookup"><span data-stu-id="963b7-103">Return items across multiple customer orders and invoices</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="963b7-104">Zwrotów można dokonać z wielu zamówień i faktur.</span><span class="sxs-lookup"><span data-stu-id="963b7-104">Returns can be made across multiple orders and invoices.</span></span> 

## <a name="configure-commerce-to-support-returns-across-multiple-customer-order-and-invoices"></a><span data-ttu-id="963b7-105">Konfigurowanie modułu Commerce do obsługi zwrotów z wielu zamówień i faktur</span><span class="sxs-lookup"><span data-stu-id="963b7-105">Configure Commerce to support returns across multiple customer order and invoices</span></span>

1. <span data-ttu-id="963b7-106">Przejdź do **Parametry rozwiązania Commerce \> Zamówienia odbiorcy**.</span><span class="sxs-lookup"><span data-stu-id="963b7-106">Go to **Commerce parameters \> Customer orders**.</span></span>
1. <span data-ttu-id="963b7-107">Włącz parametr **Włącz zwroty z wielu zamówień**.</span><span class="sxs-lookup"><span data-stu-id="963b7-107">Turn on the **Enable returns for multiple orders** parameter.</span></span> 

## <a name="process-returns"></a><span data-ttu-id="963b7-108">Przetwarzanie zwrotów</span><span class="sxs-lookup"><span data-stu-id="963b7-108">Process returns</span></span>

<span data-ttu-id="963b7-109">Po włączeniu tego parametru i zsynchronizowaniu zmian ze sklepami kasjer w sklepie można wybrać wiele zamówień sprzedaży dla danego odbiorcy i dokonać ich zwrotu.</span><span class="sxs-lookup"><span data-stu-id="963b7-109">After the parameter is turned on and the changes are synchronized to the stores, the cashier in the store can select multiple sales orders for a customer for their return.</span></span>

<span data-ttu-id="963b7-110">Gdy zamówienia są wybrane, zostanie wyświetlona lista wszystkich produktów podlegających zwrotowi z wszystkich faktur dla tych zamówień.</span><span class="sxs-lookup"><span data-stu-id="963b7-110">When the orders are selected, a list of all the returnable products across all the invoices for the orders will display.</span></span> <span data-ttu-id="963b7-111">Kasjer może następnie wybrać produkty do zwrotu.</span><span class="sxs-lookup"><span data-stu-id="963b7-111">The cashier can then select the products to return.</span></span> <span data-ttu-id="963b7-112">Dla wszystkich wybranych produktów zostanie utworzone jedno zamówienie zwrotu.</span><span class="sxs-lookup"><span data-stu-id="963b7-112">A single return order will be created for all the selected products.</span></span>
