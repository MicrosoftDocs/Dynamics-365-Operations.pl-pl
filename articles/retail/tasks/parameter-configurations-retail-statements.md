---
title: Konfiguracje parametrów dla zestawień sieci sprzedaży
description: Ta procedura pokazuje konfiguracje parametrów sprzedaży detalicznej, które mają wpływ na sposób tworzenia i księgowana zestawień sieci sprzedaży.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6dacd2b80ca0d51d81d2bdf5bc2636b47da621ee
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "352627"
---
# <a name="parameter-configurations-for-retail-statements"></a><span data-ttu-id="99ad2-103">Konfiguracje parametrów dla zestawień sieci sprzedaży</span><span class="sxs-lookup"><span data-stu-id="99ad2-103">Parameter configurations for Retail statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="99ad2-104">Ta procedura pokazuje konfiguracje parametrów sprzedaży detalicznej, które mają wpływ na sposób tworzenia i księgowana zestawień sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="99ad2-104">This procedure demonstrates configurations for Retail parameters that affect how Retail statements get created and posted.</span></span> <span data-ttu-id="99ad2-105">Ta procedura wykorzystuje firmę demonstracyjną USRT.</span><span class="sxs-lookup"><span data-stu-id="99ad2-105">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="99ad2-106">Wybierz kolejno opcje Handel detaliczny i inny > Ustawienia centrali > Parametry > Parametry sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="99ad2-106">Go to Retail and commerce > Headquarters setup  > Parameters > Retail parameters.</span></span>
2. <span data-ttu-id="99ad2-107">Kliknij kartę Księgowanie.</span><span class="sxs-lookup"><span data-stu-id="99ad2-107">Click the Posting tab.</span></span>
    * <span data-ttu-id="99ad2-108">Wybierz opcję „Tak”, aby księgować kwoty rabatów okresowych.</span><span class="sxs-lookup"><span data-stu-id="99ad2-108">Select "Yes" if you want to post the periodic discount amounts specifically.</span></span>  
    * <span data-ttu-id="99ad2-109">Wybierz opcję „Standardowe”, aby używać domyślnych kont, lub opcję „Okresowe”, jeśli chcesz zdefiniować, które konta mają być używane dla każdego rabatu okresowego.</span><span class="sxs-lookup"><span data-stu-id="99ad2-109">Select "Standard" to use default accounts, or select "Periodic" if you want to define which account to use for each periodic discount.</span></span>  
    * <span data-ttu-id="99ad2-110">Wybierz opcję „Podsumowanie”, jeśli wiersze zapasów powinny być agregowane zawsze, gdy jest to możliwe.</span><span class="sxs-lookup"><span data-stu-id="99ad2-110">Select "Summary" if inventory lines should get aggregated whenever possible.</span></span>  
    * <span data-ttu-id="99ad2-111">Wybierz opcję „Tak”, jeśli faktury i płatności powinny być automatycznie rozliczane w ramach procesu księgowania zestawień.</span><span class="sxs-lookup"><span data-stu-id="99ad2-111">Select "Yes" if Invoices and Payments should get automatically settled as part of the Statement posting process.</span></span>  
    * <span data-ttu-id="99ad2-112">Wybierz opcję „Tak”, jeśli transakcje przekazania pieniędzy do sejfu powinny być agregowane.</span><span class="sxs-lookup"><span data-stu-id="99ad2-112">Select "Yes" if Safe drop transactions should get aggregated.</span></span>  
    * <span data-ttu-id="99ad2-113">Wybierz opcję „Tak”, jeśli transakcje przekazania pieniędzy do banku powinny być agregowane.</span><span class="sxs-lookup"><span data-stu-id="99ad2-113">Select "Yes" if Bank drop transactions should get aggregated.</span></span>  
    * <span data-ttu-id="99ad2-114">Wybierz opcję „Tak”, aby włączyć agregowanie przy księgowaniu zestawień.</span><span class="sxs-lookup"><span data-stu-id="99ad2-114">Select "Yes" to turn aggregation on for Statement posting.</span></span>  
    * <span data-ttu-id="99ad2-115">Wybierz opcję „Tak”, aby tworzyć i przetwarzać zamówienia równoległe podczas księgowania zestawień.</span><span class="sxs-lookup"><span data-stu-id="99ad2-115">Select "Yes" to create and process orders in parallel when statements are posted.</span></span>  
    * <span data-ttu-id="99ad2-116">Wprowadź maksymalną liczba zamówień, które mają być przetwarzane w każdym zadaniu wsadowym.</span><span class="sxs-lookup"><span data-stu-id="99ad2-116">Enter the maximum orders to be processed in each batch job task.</span></span>  
3. <span data-ttu-id="99ad2-117">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="99ad2-117">Click Save.</span></span>

