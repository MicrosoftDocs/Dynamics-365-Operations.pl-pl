--- 
title: "Tworzenie, obliczanie i księgowanie zestawień dla sklepu sieci sprzedaży"
description: "Ta procedura prowadzi przez kolejne kroki ręcznego tworzenia, obliczania i księgowania zestawienia dla sklepu."
author: jashanno
manager: AnnBe
ms.date: 11/15/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: 1c31c849c4c72762f0fdeb3f1d256cd3529394b2
ms.contentlocale: pl-pl
ms.lasthandoff: 08/09/2018

---
# <a name="create-calculate-and-post-statements-for-a-retail-store"></a><span data-ttu-id="0f6d6-103">Tworzenie, obliczanie i księgowanie zestawień dla sklepu sieci sprzedaży</span><span class="sxs-lookup"><span data-stu-id="0f6d6-103">Create, calculate, and post statements for a retail store</span></span>

[!include [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="0f6d6-104">Ta procedura prowadzi przez kolejne kroki ręcznego tworzenia, obliczania i księgowania zestawienia dla sklepu.</span><span class="sxs-lookup"><span data-stu-id="0f6d6-104">This procedure walks through the manual steps for creating, calculating, and posting a statement for a store.</span></span> <span data-ttu-id="0f6d6-105">Istnieją także zadania wsadowe, które można skonfigurować na potrzeby tych samych zadań.</span><span class="sxs-lookup"><span data-stu-id="0f6d6-105">There are also batch jobs that can be configured for the same tasks.</span></span> <span data-ttu-id="0f6d6-106">Kroki konfigurowania i wykonywania zadań wsadowych znajdują się w innych artykułach.</span><span class="sxs-lookup"><span data-stu-id="0f6d6-106">The steps for configuring and running the batch jobs can be found in other topics.</span></span> <span data-ttu-id="0f6d6-107">Aby wykonać tę procedurę, muszą istnieć transakcji, które zostały wykonane w punkcie sprzedaży, a następnie pobrane do systemu Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="0f6d6-107">To complete this procedure, you must have transactions that were completed in POS and then pulled into Dynamics AX.</span></span> <span data-ttu-id="0f6d6-108">Nagranie wykorzystuje dane firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="0f6d6-108">This recording uses the USRT company in demo data.</span></span> <span data-ttu-id="0f6d6-109">Ta procedura może się odwoływać do systemu Microsoft Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="0f6d6-109">This procedure may refer to Microsoft Dynamics AX.</span></span> <span data-ttu-id="0f6d6-110">Należy zwrócić uwagę, że oprogramowanie Dynamics AX nosi obecnie nazwę Microsoft Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="0f6d6-110">Please note that Dynamics AX is now called Microsoft Dynamics 365 for Operations.</span></span>

1. <span data-ttu-id="0f6d6-111">Wybierz kolejno opcje Wszystkie obszary robocze > ..</span><span class="sxs-lookup"><span data-stu-id="0f6d6-111">Go to All workspaces > ..</span></span> <span data-ttu-id="0f6d6-112">> Finanse sklepu sieciowego.</span><span class="sxs-lookup"><span data-stu-id="0f6d6-112">> Retail store financials.</span></span>
2. <span data-ttu-id="0f6d6-113">Kliknij opcję Nowe zestawienie.</span><span class="sxs-lookup"><span data-stu-id="0f6d6-113">Click New statement.</span></span>
3. <span data-ttu-id="0f6d6-114">W polu Numer sklepu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="0f6d6-114">In the Store number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="0f6d6-115">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="0f6d6-115">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="0f6d6-116">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="0f6d6-116">Click OK.</span></span>
    * <span data-ttu-id="0f6d6-117">Grupa ustawień zawiera ustawienia kontrolujące, które transakcje są uwzględniane w zestawieniu i jak są grupowania w wiersze zestawienia.</span><span class="sxs-lookup"><span data-stu-id="0f6d6-117">The Setup group has the settings that control what transactions are included in the statement and how they are grouped into statement lines.</span></span> <span data-ttu-id="0f6d6-118">Można otworzyć grupę ustawień i zmienić te ustawienia lub można użyć ustawień domyślnych.</span><span class="sxs-lookup"><span data-stu-id="0f6d6-118">You can open the Setup group and change these settings, or you can use the defaults.</span></span>  
    * <span data-ttu-id="0f6d6-119">Pole Metoda zestawienia określa sposób grupowania wierszy zestawienia.</span><span class="sxs-lookup"><span data-stu-id="0f6d6-119">The Statement method field defines how the statement lines will be grouped.</span></span>  
    * <span data-ttu-id="0f6d6-120">Wybierz pracownika lub kasę, aby obliczać zestawienie tylko dla określonego pracownika lub kasy.</span><span class="sxs-lookup"><span data-stu-id="0f6d6-120">Select a staff member or a register if you want to calculate a statement only for the specific staff member or register.</span></span>  
6. <span data-ttu-id="0f6d6-121">W polu Metoda zamknięcia wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="0f6d6-121">In the Closing method field, select an option.</span></span>
7. <span data-ttu-id="0f6d6-122">Kliknij opcję Oblicz zestawienie.</span><span class="sxs-lookup"><span data-stu-id="0f6d6-122">Click Calculate statement.</span></span>
8. <span data-ttu-id="0f6d6-123">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="0f6d6-123">Click Yes.</span></span>
    * <span data-ttu-id="0f6d6-124">Po obliczeniu zestawienia powinny być utworzone wiersze z sumami kwot dla każdej użytej metody płatności i metody zestawienia.</span><span class="sxs-lookup"><span data-stu-id="0f6d6-124">After calculating the statement, there should be lines created with total amounts for each payment method and statement method that was used.</span></span>  
    * <span data-ttu-id="0f6d6-125">Wprowadź zliczoną kwotę w każdym wierszu, jeśli musi ona być wprowadzona lub zaktualizowana.</span><span class="sxs-lookup"><span data-stu-id="0f6d6-125">Enter a counted amount in each line if it needs to be entered or updated.</span></span> <span data-ttu-id="0f6d6-126">Pole zliczenia jest wypełniane kwotami z deklaracji środków płatniczych sporządzonych w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="0f6d6-126">The counted field is populated with amounts from tender declarations done in POS.</span></span>  
9. <span data-ttu-id="0f6d6-127">Kliknij opcję Zaksięguj zestawienie.</span><span class="sxs-lookup"><span data-stu-id="0f6d6-127">Click Post statement.</span></span>
10. <span data-ttu-id="0f6d6-128">Kliknij przycisk Zamknij.</span><span class="sxs-lookup"><span data-stu-id="0f6d6-128">Click Close.</span></span>
11. <span data-ttu-id="0f6d6-129">Wybierz kolejno opcje Handel detaliczny i inny > Kanały > Finanse sklepu sieciowego.</span><span class="sxs-lookup"><span data-stu-id="0f6d6-129">Go to Retail and commerce > Channels > Retail store financials.</span></span>
12. <span data-ttu-id="0f6d6-130">Kliknij kartę Zaksięgowane zestawienia.</span><span class="sxs-lookup"><span data-stu-id="0f6d6-130">Click the Posted statements tab.</span></span>


