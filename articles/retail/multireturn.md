---
title: Zwracanie towarów z wielu zamówień i faktur
description: W tym temacie opisano funkcje obsługi zwrotów z wielu zamówień i faktur w rozwiązaniu Microsoft Dynamics 365 for Retail.
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
ms.openlocfilehash: c201311028b11121d626e93859a2b98497c047d1
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1565307"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a><span data-ttu-id="49e51-103">Zwracanie towarów z wielu zamówień i faktur</span><span class="sxs-lookup"><span data-stu-id="49e51-103">Return items across multiple customer orders and invoices</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="49e51-104">W Dynamics 365 for Finance and Operations (wersja 10.0) zwroty mogą być dokonywane dla wielu zamówień i faktur, natomiast w wersjach przed 10.0 zwrotów można było dokonywać tylko dla jednej faktury jednocześnie.</span><span class="sxs-lookup"><span data-stu-id="49e51-104">In Dynamics 365 for Finance and Operations version 10.0, returns can be made across multiple orders and invoices, whereas in releases prior to 10.0, returns could only be processed by a single invoice at a time.</span></span> 

## <a name="configure-retail-to-support-returns-across-multiple-customer-order-and-invoices"></a><span data-ttu-id="49e51-105">Konfigurowanie modułu Retail do obsługi zwrotów z wielu zamówień i faktur</span><span class="sxs-lookup"><span data-stu-id="49e51-105">Configure Retail to support returns across multiple customer order and invoices</span></span>

1. <span data-ttu-id="49e51-106">Przejdź do **Parametry rozwiązania Retail \> Zamówienia odbiorcy**.</span><span class="sxs-lookup"><span data-stu-id="49e51-106">Go to **Retail parameters \> Customer orders**.</span></span>
1. <span data-ttu-id="49e51-107">Włącz parametr **Włącz zawroty z wielu zamówień**.</span><span class="sxs-lookup"><span data-stu-id="49e51-107">Turn on the **Enable returns for multiple orders** parameter.</span></span> 

## <a name="process-returns"></a><span data-ttu-id="49e51-108">Przetwarzanie zwrotów</span><span class="sxs-lookup"><span data-stu-id="49e51-108">Process returns</span></span>

<span data-ttu-id="49e51-109">Po włączeniu tego parametru i zsynchronizowaniu zmian ze sklepami kasjer w sklepie można wybrać wiele zamówień sprzedaży dla danego odbiorcy i dokonać ich zwrotu.</span><span class="sxs-lookup"><span data-stu-id="49e51-109">After the parameter is turned on and the changes are synchronized to the stores, the cashier in the store can select multiple sales orders for a customer for their return.</span></span>

<span data-ttu-id="49e51-110">Gdy zamówienia są wybrane, zostanie wyświetlona lista wszystkich produktów podlegających zwrotowi z wszystkich faktur dla tych zamówień.</span><span class="sxs-lookup"><span data-stu-id="49e51-110">When the orders are selected, a list of all the returnable products across all the invoices for the orders will display.</span></span> <span data-ttu-id="49e51-111">Kasjer może następnie wybrać produkty do zwrotu.</span><span class="sxs-lookup"><span data-stu-id="49e51-111">The cashier can then select the products to return.</span></span> <span data-ttu-id="49e51-112">Dla wszystkich wybranych produktów zostanie utworzone jedno zamówienie zwrotu.</span><span class="sxs-lookup"><span data-stu-id="49e51-112">A single return order will be created for all the selected products.</span></span>
