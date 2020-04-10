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
ms.openlocfilehash: 7892a216d836ebcc297a5b7eb87bc996dd9b91bf
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140850"
---
# <a name="configure-parameters-that-affect-retail-statements"></a><span data-ttu-id="f7742-103">Konfigurowanie parametrów wpływających na zestawienia sieci sprzedaży</span><span class="sxs-lookup"><span data-stu-id="f7742-103">Configure parameters that affect retail statements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f7742-104">Ten temat pokazuje konfiguracje parametrów Commerce, które mają wpływ na sposób tworzenia i księgowana zestawień.</span><span class="sxs-lookup"><span data-stu-id="f7742-104">This topic demonstrates configurations for Commerce parameters that affect how statements get created and posted.</span></span> <span data-ttu-id="f7742-105">Ta procedura wykorzystuje firmę demonstracyjną USRT.</span><span class="sxs-lookup"><span data-stu-id="f7742-105">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="f7742-106">W okienku nawigacji kliknij kolejno opcje **Moduły > Handel detaliczny i inny > Ustawienia Headquarters > Parametry > Parametry komercyjne**.</span><span class="sxs-lookup"><span data-stu-id="f7742-106">In the navigation pane, go to **Modules > Retail and Commerce > Headquarters setup  > Parameters > Commerce parameters**.</span></span>
2. <span data-ttu-id="f7742-107">Wybierz kartę **Księgowanie**.</span><span class="sxs-lookup"><span data-stu-id="f7742-107">Select the **Posting** tab.</span></span>
    - <span data-ttu-id="f7742-108">Wybierz opcję **Tak**, aby księgować kwoty rabatów okresowych.</span><span class="sxs-lookup"><span data-stu-id="f7742-108">Select **Yes** if you want to post the periodic discount amounts specifically.</span></span>  
    - <span data-ttu-id="f7742-109">Wybierz opcję **Standardowe**, aby używać domyślnych kont, lub opcję **Okresowe**, jeśli chcesz zdefiniować, które konta mają być używane dla każdego rabatu okresowego.</span><span class="sxs-lookup"><span data-stu-id="f7742-109">Select **Standard** to use default accounts, or select **Periodic** if you want to define which account to use for each periodic discount.</span></span>  
      - <span data-ttu-id="f7742-110">Wybierz opcję **Podsumowanie**, jeśli wiersze zapasów powinny być agregowane zawsze, gdy jest to możliwe.</span><span class="sxs-lookup"><span data-stu-id="f7742-110">Select **Summary** if inventory lines should get aggregated whenever possible.</span></span>  
      - <span data-ttu-id="f7742-111">Wybierz opcję **Tak**, jeśli faktury i płatności powinny być automatycznie rozliczane w ramach procesu księgowania zestawień.</span><span class="sxs-lookup"><span data-stu-id="f7742-111">Select **Yes** if Invoices and Payments should get automatically settled as part of the Statement posting process.</span></span>  
      - <span data-ttu-id="f7742-112">Wybierz opcję **Tak**, jeśli transakcje przekazania pieniędzy do sejfu powinny być agregowane.</span><span class="sxs-lookup"><span data-stu-id="f7742-112">Select **Yes** if Safe drop transactions should get aggregated.</span></span>  
      - <span data-ttu-id="f7742-113">Wybierz opcję **Tak**, jeśli transakcje przekazania pieniędzy do banku powinny być agregowane.</span><span class="sxs-lookup"><span data-stu-id="f7742-113">Select **Yes** if Bank drop transactions should get aggregated.</span></span>  
      - <span data-ttu-id="f7742-114">Wybierz opcję **Tak**, aby włączyć agregowanie przy księgowaniu zestawień.</span><span class="sxs-lookup"><span data-stu-id="f7742-114">Select **Yes** to turn aggregation on for Statement posting.</span></span>  
      - <span data-ttu-id="f7742-115">Wybierz opcję **Tak**, aby tworzyć i przetwarzać zamówienia równoległe podczas księgowania zestawień.</span><span class="sxs-lookup"><span data-stu-id="f7742-115">Select **Yes** to create and process orders in parallel when statements are posted.</span></span>  
      - <span data-ttu-id="f7742-116">Wprowadź maksymalną liczba zamówień, które mają być przetwarzane w każdym zadaniu wsadowym.</span><span class="sxs-lookup"><span data-stu-id="f7742-116">Enter the maximum orders to be processed in each batch job task.</span></span>  
3. <span data-ttu-id="f7742-117">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f7742-117">Select **Save**.</span></span>

