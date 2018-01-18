--- 
title: "Konfiguracje parametrów dla zestawień sieci sprzedaży"
description: "Ta procedura pokazuje konfiguracje parametrów sprzedaży detalicznej, które mają wpływ na sposób tworzenia i księgowana zestawień sieci sprzedaży."
author: josaw1
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9b080ff46a0fbc73ed4f8fa3f03d71e9d758cc2
ms.openlocfilehash: 61540297a2ebbbc76657734140b8add009db67ca
ms.contentlocale: pl-pl
ms.lasthandoff: 01/17/2018

---
# <a name="parameter-configurations-for-retail-statements"></a><span data-ttu-id="962f1-103">Konfiguracje parametrów dla zestawień sieci sprzedaży</span><span class="sxs-lookup"><span data-stu-id="962f1-103">Parameter configurations for Retail statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="962f1-104">Ta procedura pokazuje konfiguracje parametrów sprzedaży detalicznej, które mają wpływ na sposób tworzenia i księgowana zestawień sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="962f1-104">This procedure demonstrates configurations for Retail parameters that affect how Retail statements get created and posted.</span></span> <span data-ttu-id="962f1-105">Ta procedura wykorzystuje firmę demonstracyjną USRT.</span><span class="sxs-lookup"><span data-stu-id="962f1-105">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="962f1-106">Wybierz kolejno opcje Handel detaliczny i inny > Ustawienia centrali > Parametry > Parametry sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="962f1-106">Go to Retail and commerce > Headquarters setup  > Parameters > Retail parameters.</span></span>
2. <span data-ttu-id="962f1-107">Kliknij kartę Księgowanie.</span><span class="sxs-lookup"><span data-stu-id="962f1-107">Click the Posting tab.</span></span>
    * <span data-ttu-id="962f1-108">Wybierz opcję „Tak”, aby księgować kwoty rabatów okresowych.</span><span class="sxs-lookup"><span data-stu-id="962f1-108">Select "Yes" if you want to post the periodic discount amounts specifically.</span></span>  
    * <span data-ttu-id="962f1-109">Wybierz opcję „Standardowe”, aby używać domyślnych kont, lub opcję „Okresowe”, jeśli chcesz zdefiniować, które konta mają być używane dla każdego rabatu okresowego.</span><span class="sxs-lookup"><span data-stu-id="962f1-109">Select "Standard" to use default accounts, or select "Periodic" if you want to define which account to use for each periodic discount.</span></span>  
    * <span data-ttu-id="962f1-110">Wybierz opcję „Podsumowanie”, jeśli wiersze zapasów powinny być agregowane zawsze, gdy jest to możliwe.</span><span class="sxs-lookup"><span data-stu-id="962f1-110">Select "Summary" if inventory lines should get aggregated whenever possible.</span></span>  
    * <span data-ttu-id="962f1-111">Wybierz opcję „Tak”, jeśli faktury i płatności powinny być automatycznie rozliczane w ramach procesu księgowania zestawień.</span><span class="sxs-lookup"><span data-stu-id="962f1-111">Select "Yes" if Invoices and Payments should get automatically settled as part of the Statement posting process.</span></span>  
    * <span data-ttu-id="962f1-112">Wybierz opcję „Tak”, jeśli transakcje przekazania pieniędzy do sejfu powinny być agregowane.</span><span class="sxs-lookup"><span data-stu-id="962f1-112">Select "Yes" if Safe drop transactions should get aggregated.</span></span>  
    * <span data-ttu-id="962f1-113">Wybierz opcję „Tak”, jeśli transakcje przekazania pieniędzy do banku powinny być agregowane.</span><span class="sxs-lookup"><span data-stu-id="962f1-113">Select "Yes" if Bank drop transactions should get aggregated.</span></span>  
    * <span data-ttu-id="962f1-114">Wybierz opcję „Tak”, aby włączyć agregowanie przy księgowaniu zestawień.</span><span class="sxs-lookup"><span data-stu-id="962f1-114">Select "Yes" to turn aggregation on for Statement posting.</span></span>  
    * <span data-ttu-id="962f1-115">Wybierz opcję „Tak”, aby tworzyć i przetwarzać zamówienia równoległe podczas księgowania zestawień.</span><span class="sxs-lookup"><span data-stu-id="962f1-115">Select "Yes" to create and process orders in parallel when statements are posted.</span></span>  
    * <span data-ttu-id="962f1-116">Wprowadź maksymalną liczba zamówień, które mają być przetwarzane w każdym zadaniu wsadowym.</span><span class="sxs-lookup"><span data-stu-id="962f1-116">Enter the maximum orders to be processed in each batch job task.</span></span>  
3. <span data-ttu-id="962f1-117">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="962f1-117">Click Save.</span></span>


