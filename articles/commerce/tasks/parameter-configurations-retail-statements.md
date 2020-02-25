---
title: Konfigurowanie parametrów wpływających na zestawienia sieci sprzedaży
description: Ten temat pokazuje konfiguracje parametrów Commerce, które mają wpływ na sposób tworzenia i księgowana zestawień.
author: josaw1
manager: AnnBe
ms.date: 08/01/2019
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
ms.openlocfilehash: d8cae6d2fa7c469f50fa92141a6cb5a0af1df4b0
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "3023664"
---
# <a name="configure-parameters-that-affect-retail-statements"></a><span data-ttu-id="2f196-103">Konfigurowanie parametrów wpływających na zestawienia sieci sprzedaży</span><span class="sxs-lookup"><span data-stu-id="2f196-103">Configure parameters that affect retail statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="2f196-104">Ten temat pokazuje konfiguracje parametrów Commerce, które mają wpływ na sposób tworzenia i księgowana zestawień.</span><span class="sxs-lookup"><span data-stu-id="2f196-104">This topic demonstrates configurations for Commerce parameters that affect how statements get created and posted.</span></span> <span data-ttu-id="2f196-105">Ta procedura wykorzystuje firmę demonstracyjną USRT.</span><span class="sxs-lookup"><span data-stu-id="2f196-105">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="2f196-106">W okienku nawigacji kliknij kolejno opcje **Moduły > Handel detaliczny i inny > Ustawienia Headquarters > Parametry > Parametry komercyjne**.</span><span class="sxs-lookup"><span data-stu-id="2f196-106">In the navigation pane, go to **Modules > Retail and Commerce > Headquarters setup  > Parameters > Commerce parameters**.</span></span>
2. <span data-ttu-id="2f196-107">Wybierz kartę **Księgowanie**.</span><span class="sxs-lookup"><span data-stu-id="2f196-107">Select the **Posting** tab.</span></span>
    - <span data-ttu-id="2f196-108">Wybierz opcję **Tak**, aby księgować kwoty rabatów okresowych.</span><span class="sxs-lookup"><span data-stu-id="2f196-108">Select **Yes** if you want to post the periodic discount amounts specifically.</span></span>  
    - <span data-ttu-id="2f196-109">Wybierz opcję **Standardowe**, aby używać domyślnych kont, lub opcję **Okresowe**, jeśli chcesz zdefiniować, które konta mają być używane dla każdego rabatu okresowego.</span><span class="sxs-lookup"><span data-stu-id="2f196-109">Select **Standard** to use default accounts, or select **Periodic** if you want to define which account to use for each periodic discount.</span></span>  
      - <span data-ttu-id="2f196-110">Wybierz opcję **Podsumowanie**, jeśli wiersze zapasów powinny być agregowane zawsze, gdy jest to możliwe.</span><span class="sxs-lookup"><span data-stu-id="2f196-110">Select **Summary** if inventory lines should get aggregated whenever possible.</span></span>  
      - <span data-ttu-id="2f196-111">Wybierz opcję **Tak**, jeśli faktury i płatności powinny być automatycznie rozliczane w ramach procesu księgowania zestawień.</span><span class="sxs-lookup"><span data-stu-id="2f196-111">Select **Yes** if Invoices and Payments should get automatically settled as part of the Statement posting process.</span></span>  
      - <span data-ttu-id="2f196-112">Wybierz opcję **Tak**, jeśli transakcje przekazania pieniędzy do sejfu powinny być agregowane.</span><span class="sxs-lookup"><span data-stu-id="2f196-112">Select **Yes** if Safe drop transactions should get aggregated.</span></span>  
      - <span data-ttu-id="2f196-113">Wybierz opcję **Tak**, jeśli transakcje przekazania pieniędzy do banku powinny być agregowane.</span><span class="sxs-lookup"><span data-stu-id="2f196-113">Select **Yes** if Bank drop transactions should get aggregated.</span></span>  
      - <span data-ttu-id="2f196-114">Wybierz opcję **Tak**, aby włączyć agregowanie przy księgowaniu zestawień.</span><span class="sxs-lookup"><span data-stu-id="2f196-114">Select **Yes** to turn aggregation on for Statement posting.</span></span>  
      - <span data-ttu-id="2f196-115">Wybierz opcję **Tak**, aby tworzyć i przetwarzać zamówienia równoległe podczas księgowania zestawień.</span><span class="sxs-lookup"><span data-stu-id="2f196-115">Select **Yes** to create and process orders in parallel when statements are posted.</span></span>  
      - <span data-ttu-id="2f196-116">Wprowadź maksymalną liczba zamówień, które mają być przetwarzane w każdym zadaniu wsadowym.</span><span class="sxs-lookup"><span data-stu-id="2f196-116">Enter the maximum orders to be processed in each batch job task.</span></span>  
3. <span data-ttu-id="2f196-117">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="2f196-117">Select **Save**.</span></span>

