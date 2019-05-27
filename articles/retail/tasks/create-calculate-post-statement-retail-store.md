---
title: Tworzenie, obliczanie i księgowanie zestawienia dla sklepu sieci sprzedaży
description: Ta procedura prowadzi przez kolejne kroki ręcznego tworzenia, obliczania i księgowania zestawienia dla sklepu.
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
ms.openlocfilehash: 9ea30e7e008bfcce77a7ee2f4d7d01a6cf1ababc
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1548331"
---
# <a name="create-calculate-and-post-a-statement-for-a-retail-store"></a><span data-ttu-id="d6522-103">Tworzenie, obliczanie i księgowanie zestawienia dla sklepu sieci sprzedaży</span><span class="sxs-lookup"><span data-stu-id="d6522-103">Create, calculate, and post a statement for a retail store</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="d6522-104">Ta procedura prowadzi przez kolejne kroki ręcznego tworzenia, obliczania i księgowania zestawienia dla sklepu.</span><span class="sxs-lookup"><span data-stu-id="d6522-104">This procedure walks through the manual steps for creating, calculating, and posting a statement for a store.</span></span> <span data-ttu-id="d6522-105">Istnieją także zadania wsadowe, które można skonfigurować na potrzeby tych samych zadań.</span><span class="sxs-lookup"><span data-stu-id="d6522-105">There are also batch jobs that can be configured for the same tasks.</span></span> <span data-ttu-id="d6522-106">Kroki konfigurowania i wykonywania zadań wsadowych znajdują się w innych artykułach.</span><span class="sxs-lookup"><span data-stu-id="d6522-106">The steps for configuring and running the batch jobs can be found in other topics.</span></span> <span data-ttu-id="d6522-107">Aby wykonać tę procedurę, muszą istnieć transakcji, które zostały wykonane w punkcie sprzedaży, a następnie pobrane do systemu Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="d6522-107">To complete this procedure, you must have transactions that were completed in POS and then pulled into Dynamics AX.</span></span> <span data-ttu-id="d6522-108">Nagranie wykorzystuje dane firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="d6522-108">This recording uses the USRT company in demo data.</span></span> <span data-ttu-id="d6522-109">Procedura ta może odwoływać się do Microsoft Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="d6522-109">This procedure may refer to Microsoft Dynamics AX.</span></span> <span data-ttu-id="d6522-110">Należy zwrócić uwagę, że oprogramowanie Dynamics AX nosi obecnie nazwę Microsoft Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="d6522-110">Please note that Dynamics AX is now called Microsoft Dynamics 365 for Operations.</span></span>

1. <span data-ttu-id="d6522-111">Wybierz kolejno opcje Wszystkie obszary robocze > ..</span><span class="sxs-lookup"><span data-stu-id="d6522-111">Go to All workspaces > ..</span></span> <span data-ttu-id="d6522-112">> Finanse sklepu sieciowego.</span><span class="sxs-lookup"><span data-stu-id="d6522-112">> Retail store financials.</span></span>
2. <span data-ttu-id="d6522-113">Kliknij opcję Nowe zestawienie.</span><span class="sxs-lookup"><span data-stu-id="d6522-113">Click New statement.</span></span>
3. <span data-ttu-id="d6522-114">W polu Numer sklepu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="d6522-114">In the Store number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="d6522-115">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="d6522-115">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="d6522-116">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="d6522-116">Click OK.</span></span>
    * <span data-ttu-id="d6522-117">Grupa ustawień zawiera ustawienia kontrolujące, które transakcje są uwzględniane w zestawieniu i jak są grupowania w wiersze zestawienia.</span><span class="sxs-lookup"><span data-stu-id="d6522-117">The Setup group has the settings that control what transactions are included in the statement and how they are grouped into statement lines.</span></span> <span data-ttu-id="d6522-118">Można otworzyć grupę ustawień i zmienić te ustawienia lub można użyć ustawień domyślnych.</span><span class="sxs-lookup"><span data-stu-id="d6522-118">You can open the Setup group and change these settings, or you can use the defaults.</span></span>  
    * <span data-ttu-id="d6522-119">Pole Metoda zestawienia określa sposób grupowania wierszy zestawienia.</span><span class="sxs-lookup"><span data-stu-id="d6522-119">The Statement method field defines how the statement lines will be grouped.</span></span>  
    * <span data-ttu-id="d6522-120">Wybierz pracownika lub kasę, aby obliczać zestawienie tylko dla określonego pracownika lub kasy.</span><span class="sxs-lookup"><span data-stu-id="d6522-120">Select a staff member or a register if you want to calculate a statement only for the specific staff member or register.</span></span>  
6. <span data-ttu-id="d6522-121">W polu Metoda zamknięcia wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="d6522-121">In the Closing method field, select an option.</span></span>
7. <span data-ttu-id="d6522-122">Kliknij opcję Oblicz zestawienie.</span><span class="sxs-lookup"><span data-stu-id="d6522-122">Click Calculate statement.</span></span>
8. <span data-ttu-id="d6522-123">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="d6522-123">Click Yes.</span></span>
    * <span data-ttu-id="d6522-124">Po obliczeniu zestawienia powinny być utworzone wiersze z sumami kwot dla każdej użytej metody płatności i metody zestawienia.</span><span class="sxs-lookup"><span data-stu-id="d6522-124">After calculating the statement, there should be lines created with total amounts for each payment method and statement method that was used.</span></span>  
    * <span data-ttu-id="d6522-125">Wprowadź zliczoną kwotę w każdym wierszu, jeśli musi ona być wprowadzona lub zaktualizowana.</span><span class="sxs-lookup"><span data-stu-id="d6522-125">Enter a counted amount in each line if it needs to be entered or updated.</span></span> <span data-ttu-id="d6522-126">Pole zliczenia jest wypełniane kwotami z deklaracji środków płatniczych sporządzonych w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="d6522-126">The counted field is populated with amounts from tender declarations done in POS.</span></span>  
9. <span data-ttu-id="d6522-127">Kliknij opcję Zaksięguj zestawienie.</span><span class="sxs-lookup"><span data-stu-id="d6522-127">Click Post statement.</span></span>
10. <span data-ttu-id="d6522-128">Kliknij przycisk Zamknij.</span><span class="sxs-lookup"><span data-stu-id="d6522-128">Click Close.</span></span>
11. <span data-ttu-id="d6522-129">Wybierz kolejno opcje Handel detaliczny i inny > Kanały > Finanse sklepu sieciowego.</span><span class="sxs-lookup"><span data-stu-id="d6522-129">Go to Retail and commerce > Channels > Retail store financials.</span></span>
12. <span data-ttu-id="d6522-130">Kliknij kartę Zaksięgowane zestawienia.</span><span class="sxs-lookup"><span data-stu-id="d6522-130">Click the Posted statements tab.</span></span>

