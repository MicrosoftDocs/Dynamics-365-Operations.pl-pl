---
title: Tworzenie, obliczanie i księgowanie zestawień dla sklepu sieci sprzedaży
description: Ten temat opisuje kolejne kroki ręcznego tworzenia, obliczania i księgowania zestawienia dla sklepu.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailStatementTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4517b9ddeb648b3d789773fc0dcb1ecd3c8be85c
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2019
ms.locfileid: "2024805"
---
# <a name="create-calculate-and-post-statements-for-a-retail-store"></a><span data-ttu-id="ba661-103">Tworzenie, obliczanie i księgowanie zestawień dla sklepu sieci sprzedaży</span><span class="sxs-lookup"><span data-stu-id="ba661-103">Create, calculate, and post statements for a retail store</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="ba661-104">Ten temat opisuje kolejne kroki ręcznego tworzenia, obliczania i księgowania zestawienia dla sklepu.</span><span class="sxs-lookup"><span data-stu-id="ba661-104">This topic describes the manual steps for creating, calculating, and posting a statement for a store.</span></span> <span data-ttu-id="ba661-105">Istnieją także zadania wsadowe, które można skonfigurować na potrzeby tych samych zadań.</span><span class="sxs-lookup"><span data-stu-id="ba661-105">There are also batch jobs that can be configured for the same tasks.</span></span> <span data-ttu-id="ba661-106">Kroki konfigurowania i wykonywania zadań wsadowych znajdują się w innych artykułach.</span><span class="sxs-lookup"><span data-stu-id="ba661-106">The steps for configuring and running the batch jobs can be found in other topics.</span></span> <span data-ttu-id="ba661-107">Aby wykonać tę procedurę, muszą istnieć transakcji, które zostały wykonane w punkcie sprzedaży, a następnie pobrane do systemu Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="ba661-107">To complete this procedure, you must have transactions that were completed in POS and then pulled into Dynamics 365 Retail.</span></span> <span data-ttu-id="ba661-108">Nagranie wykorzystuje dane firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="ba661-108">This recording uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="ba661-109">Wybierz opcję **Finanse sklepu sieciowego** na stronie głównej.</span><span class="sxs-lookup"><span data-stu-id="ba661-109">Select **Retail store financials** from the home page.</span></span>
2. <span data-ttu-id="ba661-110">Wybierz opcję **Nowe zestawienie**.</span><span class="sxs-lookup"><span data-stu-id="ba661-110">Select **New statement**.</span></span>
3. <span data-ttu-id="ba661-111">W polu **Numer sklepu** wybierz opcję z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="ba661-111">In the **Store number** field, select a option from the drop-down.</span></span>
4. <span data-ttu-id="ba661-112">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="ba661-112">Select **OK**.</span></span>
5. <span data-ttu-id="ba661-113">Grupa **Ustawienia** zawiera ustawienia kontrolujące, które transakcje są uwzględniane w zestawieniu i jak są grupowania w wiersze zestawienia.</span><span class="sxs-lookup"><span data-stu-id="ba661-113">The **Setup** group has the settings that control what transactions are included in the statement and how they are grouped into statement lines.</span></span> <span data-ttu-id="ba661-114">Można otworzyć grupę **Ustawienia** i zmienić te ustawienia lub można użyć ustawień domyślnych.</span><span class="sxs-lookup"><span data-stu-id="ba661-114">You can open the **Setup** group and change these settings, or you can use the defaults.</span></span>  
    - <span data-ttu-id="ba661-115">Pole **Metoda zestawienia** określa sposób grupowania wierszy zestawienia.</span><span class="sxs-lookup"><span data-stu-id="ba661-115">The **Statement method** field defines how the statement lines will be grouped.</span></span>  
    - <span data-ttu-id="ba661-116">Wybierz pracownika lub kasę w polu **Pracownicy/kasa**, aby obliczać zestawienie tylko dla określonego pracownika lub kasy.</span><span class="sxs-lookup"><span data-stu-id="ba661-116">Select a staff member or a register in the **staff/register** field if you want to calculate a statement only for the specific staff member or register.</span></span>  
6. <span data-ttu-id="ba661-117">W polu **Metoda zamknięcia** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="ba661-117">In the **Closing method** field, select an option.</span></span>
7. <span data-ttu-id="ba661-118">Wybierz opcję **Oblicz zestawienie** z okienka akcji.</span><span class="sxs-lookup"><span data-stu-id="ba661-118">Select **Calculate statement** from the Action Pane.</span></span>
8. <span data-ttu-id="ba661-119">Wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="ba661-119">Select **Yes**.</span></span>
    - <span data-ttu-id="ba661-120">Po obliczeniu zestawienia powinny być utworzone wiersze z sumami kwot dla każdej użytej metody płatności i metody zestawienia.</span><span class="sxs-lookup"><span data-stu-id="ba661-120">After calculating the statement, there should be lines created with total amounts for each payment method and statement method that was used.</span></span>  
    - <span data-ttu-id="ba661-121">Wprowadź zliczoną kwotę w każdym wierszu, jeśli musi ona być wprowadzona lub zaktualizowana.</span><span class="sxs-lookup"><span data-stu-id="ba661-121">Enter a counted amount in each line if it needs to be entered or updated.</span></span> <span data-ttu-id="ba661-122">Pole zliczenia jest wypełniane kwotami z deklaracji środków płatniczych sporządzonych w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="ba661-122">The counted field is populated with amounts from tender declarations done in POS.</span></span>  
9. <span data-ttu-id="ba661-123">Wybierz opcję **Zaksięguj zestawienie** z okienka akcji.</span><span class="sxs-lookup"><span data-stu-id="ba661-123">Select **Post statement** from the Action Pane.</span></span>
10. <span data-ttu-id="ba661-124">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="ba661-124">Select **Close**.</span></span>
11. <span data-ttu-id="ba661-125">Zamknij okienko.</span><span class="sxs-lookup"><span data-stu-id="ba661-125">Close the pane.</span></span>
12. <span data-ttu-id="ba661-126">Na stronie głównej wybierz opcję **Finanse sklepu sieciowego**.</span><span class="sxs-lookup"><span data-stu-id="ba661-126">At the home page, select **Retail store financials**.</span></span>
13. <span data-ttu-id="ba661-127">Wybierz kartę **Zaksięgowane zestawienia**.</span><span class="sxs-lookup"><span data-stu-id="ba661-127">Select the **Posted statements** tab.</span></span>

