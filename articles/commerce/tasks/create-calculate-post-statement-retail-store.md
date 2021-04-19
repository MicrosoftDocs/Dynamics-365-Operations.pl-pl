---
title: Tworzenie, obliczanie i księgowanie zestawień dla sklepu sieci sprzedaży
description: Ten temat opisuje kolejne kroki ręcznego tworzenia, obliczania i księgowania zestawienia dla sklepu.
author: jashanno
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailStatementTable
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 58900ca4d3f6893689822a8cc5657d8c91772f65
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798544"
---
# <a name="create-calculate-and-post-statements-for-a-retail-store"></a><span data-ttu-id="c3ada-103">Tworzenie, obliczanie i księgowanie zestawień dla sklepu sieci sprzedaży</span><span class="sxs-lookup"><span data-stu-id="c3ada-103">Create, calculate, and post statements for a retail store</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c3ada-104">Ten temat opisuje kolejne kroki ręcznego tworzenia, obliczania i księgowania zestawienia dla sklepu.</span><span class="sxs-lookup"><span data-stu-id="c3ada-104">This topic describes the manual steps for creating, calculating, and posting a statement for a store.</span></span> <span data-ttu-id="c3ada-105">Istnieją także zadania wsadowe, które można skonfigurować na potrzeby tych samych zadań.</span><span class="sxs-lookup"><span data-stu-id="c3ada-105">There are also batch jobs that can be configured for the same tasks.</span></span> <span data-ttu-id="c3ada-106">Kroki konfigurowania i wykonywania zadań wsadowych znajdują się w innych artykułach.</span><span class="sxs-lookup"><span data-stu-id="c3ada-106">The steps for configuring and running the batch jobs can be found in other topics.</span></span> <span data-ttu-id="c3ada-107">Aby wykonać tę procedurę, muszą istnieć transakcji, które zostały wykonane w punkcie sprzedaży, a następnie pobrane do systemu Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c3ada-107">To complete this procedure, you must have transactions that were completed in POS and then pulled into Dynamics 365 Commerce.</span></span> <span data-ttu-id="c3ada-108">Nagranie wykorzystuje dane firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="c3ada-108">This recording uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="c3ada-109">Wybierz opcję **Finanse sklepu** na stronie głównej.</span><span class="sxs-lookup"><span data-stu-id="c3ada-109">Select **Store financials** from the home page.</span></span>
2. <span data-ttu-id="c3ada-110">Wybierz opcję **Nowe zestawienie**.</span><span class="sxs-lookup"><span data-stu-id="c3ada-110">Select **New statement**.</span></span>
3. <span data-ttu-id="c3ada-111">W polu **Numer sklepu** wybierz opcję z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="c3ada-111">In the **Store number** field, select a option from the drop-down.</span></span>
4. <span data-ttu-id="c3ada-112">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="c3ada-112">Select **OK**.</span></span>
5. <span data-ttu-id="c3ada-113">Grupa **Ustawienia** zawiera ustawienia kontrolujące, które transakcje są uwzględniane w zestawieniu i jak są grupowania w wiersze zestawienia.</span><span class="sxs-lookup"><span data-stu-id="c3ada-113">The **Setup** group has the settings that control what transactions are included in the statement and how they are grouped into statement lines.</span></span> <span data-ttu-id="c3ada-114">Można otworzyć grupę **Ustawienia** i zmienić te ustawienia lub można użyć ustawień domyślnych.</span><span class="sxs-lookup"><span data-stu-id="c3ada-114">You can open the **Setup** group and change these settings, or you can use the defaults.</span></span>  
    - <span data-ttu-id="c3ada-115">Pole **Metoda zestawienia** określa sposób grupowania wierszy zestawienia.</span><span class="sxs-lookup"><span data-stu-id="c3ada-115">The **Statement method** field defines how the statement lines will be grouped.</span></span>  
    - <span data-ttu-id="c3ada-116">Wybierz pracownika lub kasę w polu **Pracownicy/kasa**, aby obliczać zestawienie tylko dla określonego pracownika lub kasy.</span><span class="sxs-lookup"><span data-stu-id="c3ada-116">Select a staff member or a register in the **staff/register** field if you want to calculate a statement only for the specific staff member or register.</span></span>  
6. <span data-ttu-id="c3ada-117">W polu **Metoda zamknięcia** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="c3ada-117">In the **Closing method** field, select an option.</span></span>
7. <span data-ttu-id="c3ada-118">Wybierz opcję **Oblicz zestawienie** z okienka akcji.</span><span class="sxs-lookup"><span data-stu-id="c3ada-118">Select **Calculate statement** from the Action Pane.</span></span>
8. <span data-ttu-id="c3ada-119">Wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="c3ada-119">Select **Yes**.</span></span>
    - <span data-ttu-id="c3ada-120">Po obliczeniu zestawienia powinny być utworzone wiersze z sumami kwot dla każdej użytej metody płatności i metody zestawienia.</span><span class="sxs-lookup"><span data-stu-id="c3ada-120">After calculating the statement, there should be lines created with total amounts for each payment method and statement method that was used.</span></span>  
    - <span data-ttu-id="c3ada-121">Wprowadź zliczoną kwotę w każdym wierszu, jeśli musi ona być wprowadzona lub zaktualizowana.</span><span class="sxs-lookup"><span data-stu-id="c3ada-121">Enter a counted amount in each line if it needs to be entered or updated.</span></span> <span data-ttu-id="c3ada-122">Pole zliczenia jest wypełniane kwotami z deklaracji środków płatniczych sporządzonych w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c3ada-122">The counted field is populated with amounts from tender declarations done in POS.</span></span>  
9. <span data-ttu-id="c3ada-123">Wybierz opcję **Zaksięguj zestawienie** z okienka akcji.</span><span class="sxs-lookup"><span data-stu-id="c3ada-123">Select **Post statement** from the Action Pane.</span></span>
10. <span data-ttu-id="c3ada-124">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="c3ada-124">Select **Close**.</span></span>
11. <span data-ttu-id="c3ada-125">Zamknij okienko.</span><span class="sxs-lookup"><span data-stu-id="c3ada-125">Close the pane.</span></span>
12. <span data-ttu-id="c3ada-126">Na stronie głównej wybierz opcję **Finanse sklepu**.</span><span class="sxs-lookup"><span data-stu-id="c3ada-126">At the home page, select **Store financials**.</span></span>
13. <span data-ttu-id="c3ada-127">Wybierz kartę **Zaksięgowane zestawienia**.</span><span class="sxs-lookup"><span data-stu-id="c3ada-127">Select the **Posted statements** tab.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]