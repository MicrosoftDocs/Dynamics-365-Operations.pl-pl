--- 
title: "Obliczanie amortyzacji środka trwałego we wszystkich firmach"
description: "Ta procedura przedstawia sposób ustawiania i uruchamiania procesu amortyzacji dla wielu firm."
author: saraschi2
manager: AnnBe
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 662554b1b6bed63e5017aad3a292dad7a2f0bcea
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---
# <a name="calculate-fixed-asset-depreciation-across-legal-entities"></a><span data-ttu-id="7a4ac-103">Obliczanie amortyzacji środka trwałego we wszystkich firmach</span><span class="sxs-lookup"><span data-stu-id="7a4ac-103">Calculate fixed asset depreciation across legal entities</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7a4ac-104">Amortyzację środków trwałych można uruchomić w wielu firmach w jednym kroku.</span><span class="sxs-lookup"><span data-stu-id="7a4ac-104">Fixed asset depreciation can be run across legal entities in a single step.</span></span> <span data-ttu-id="7a4ac-105">Ta procedura przedstawia sposób ustawiania i uruchamiania procesu dla wielu firm.</span><span class="sxs-lookup"><span data-stu-id="7a4ac-105">This procedure shows you to how set up and run the process for multiple legal entities.</span></span> <span data-ttu-id="7a4ac-106">Wykorzystuje rolę księgowego.</span><span class="sxs-lookup"><span data-stu-id="7a4ac-106">It uses the accountant role.</span></span>  

<span data-ttu-id="7a4ac-107">To nagranie wykorzystuje firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="7a4ac-107">This recording uses the USMF demo company.</span></span>


<span data-ttu-id="7a4ac-108">Kroki (16) podzadania: ustawianie arkuszy uruchomienia amortyzacji w całej firmie.</span><span class="sxs-lookup"><span data-stu-id="7a4ac-108">Steps (16) Sub-task: Set up cross company depreciation run journals.</span></span> 

1. <span data-ttu-id="7a4ac-109">Najpierw należy ustawić arkusze używane do uruchomienia amortyzacji w całej firmie dla każdej firmy.</span><span class="sxs-lookup"><span data-stu-id="7a4ac-109">First, you must set up the journals to be used in the cross company depreciation run in each legal entity.</span></span> <span data-ttu-id="7a4ac-110">Wybierz kolejno opcje Środki trwałe > Ustawienia > Parametry środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="7a4ac-110">Go to Fixed assets > Setup > Fixed assets parameters.</span></span> 
2. <span data-ttu-id="7a4ac-111">Rozwiń sekcję Propozycje środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="7a4ac-111">Expand the Fixed asset proposals section.</span></span> 
3. <span data-ttu-id="7a4ac-112">Utwórz rekord z nazwą arkusza używanego, który ma być używany dla każdej warstwy księgowania w firmie.</span><span class="sxs-lookup"><span data-stu-id="7a4ac-112">Create a record with the journal name to be used for each posting layer in the legal entity.</span></span> <span data-ttu-id="7a4ac-113">Jeżeli księgi nie są księgowane w księdze głównej, należy wybrać warstwę księgowania Brak z powiązanym arkuszem.</span><span class="sxs-lookup"><span data-stu-id="7a4ac-113">If books do not post to the general ledger, then the None posting layer should be selected with the associated journal.</span></span> <span data-ttu-id="7a4ac-114">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="7a4ac-114">Click Add.</span></span> 
4. <span data-ttu-id="7a4ac-115">W polu Warstwa księgowania wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="7a4ac-115">In the Posting layer field, enter or select a value.</span></span> 
5. <span data-ttu-id="7a4ac-116">Wprowadź lub wybierz wartość w polu Nazwa arkusza.</span><span class="sxs-lookup"><span data-stu-id="7a4ac-116">In the Journal name field, enter or select a value.</span></span> 
6. <span data-ttu-id="7a4ac-117">Powtórz ustawianie arkusza na stronie Parametry środków trwałych w każdej firmie.</span><span class="sxs-lookup"><span data-stu-id="7a4ac-117">Repeat the journal setup on the Fixed asset parameters page in each legal entity.</span></span> 

<span data-ttu-id="7a4ac-118">Podzadanie: obliczanie amortyzacji</span><span class="sxs-lookup"><span data-stu-id="7a4ac-118">Sub-task: Calculate depreciation</span></span>

1. <span data-ttu-id="7a4ac-119">Użyj strony Utwórz propozycję amortyzacji, aby uruchomić amortyzację w firmach.</span><span class="sxs-lookup"><span data-stu-id="7a4ac-119">Use the Create depreciation proposal page to start your depreciation run across legal entities.</span></span> <span data-ttu-id="7a4ac-120">Wybierz kolejno opcje Środki trwałe > Wpisy w arkuszu > Utwórz propozycję amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="7a4ac-120">Go to Fixed assets > Journal entries > Create depreciation proposal.</span></span> 
2. <span data-ttu-id="7a4ac-121">W polu Warstwa księgowania wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="7a4ac-121">In the Posting layer field, enter or select a value.</span></span> 
3. <span data-ttu-id="7a4ac-122">Nazwa arkusza przyjmie wartość domyślną z parametrów środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="7a4ac-122">The journal name will default from the Fixed asset parameters.</span></span> <span data-ttu-id="7a4ac-123">Można ją zmienić tutaj dla bieżącej firmy.</span><span class="sxs-lookup"><span data-stu-id="7a4ac-123">It can be changed here for the current legal entity.</span></span> 
4. <span data-ttu-id="7a4ac-124">Wprowadź datę w polu Do dnia.</span><span class="sxs-lookup"><span data-stu-id="7a4ac-124">In the To date field, enter a date.</span></span> 
5. <span data-ttu-id="7a4ac-125">Wybierz firmy, które mają zostać uwzględnione w uruchomieniu amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="7a4ac-125">Select the legal entities to be included in the depreciation run.</span></span> <span data-ttu-id="7a4ac-126">Na liście będą widoczne tylko firmy z arkuszami ustawionymi dla propozycji środków trwałych na stronie Parametry środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="7a4ac-126">Only legal entities with journals set up for Fixed asset proposals on the Fixed asset parameters page will be shown in the list.</span></span> 
6. <span data-ttu-id="7a4ac-127">Po włączeniu opcja Zaksięguj arkusze automatycznie zaksięguje arkusze amortyzacji po utworzeniu.</span><span class="sxs-lookup"><span data-stu-id="7a4ac-127">When enabled, the Post journals option will automatically post the depreciation journals when they are created.</span></span> <span data-ttu-id="7a4ac-128">Jeżeli nie zostanie wybrana, arkusze zostaną utworzone bez księgowania, co umożliwi przejrzenie szczegółów przed zaksięgowaniem.</span><span class="sxs-lookup"><span data-stu-id="7a4ac-128">When not selected, the journals will be created, but not posted, so you can review the details before posting.</span></span> <span data-ttu-id="7a4ac-129">Wybierz opcję Tak w polu Zaksięguj arkusze.</span><span class="sxs-lookup"><span data-stu-id="7a4ac-129">Select Yes in the Post journals field.</span></span> 
7. <span data-ttu-id="7a4ac-130">Pola filtrowania obejmują wszystkie środki trwałe, grupy i księgi dla firm wybranych do tego uruchomienia amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="7a4ac-130">Filtering fields include all fixed assets, groups, and books for the legal entities selected for this depreciation run.</span></span> 
8. <span data-ttu-id="7a4ac-131">Opcja Przetwarzanie wsadowe jest domyślnie włączona.</span><span class="sxs-lookup"><span data-stu-id="7a4ac-131">The Batch processing option is enabled by default.</span></span> <span data-ttu-id="7a4ac-132">Gdy ta opcja jest włączona, tworzenie i księgowanie arkusza amortyzacji zostanie uruchomione w tle.</span><span class="sxs-lookup"><span data-stu-id="7a4ac-132">When this option is enabled, the depreciation journal creation and posting will run in the background.</span></span> 
9. <span data-ttu-id="7a4ac-133">Kliknij opcję Utwórz arkusz.</span><span class="sxs-lookup"><span data-stu-id="7a4ac-133">Click Create journal.</span></span> 
10. <span data-ttu-id="7a4ac-134">Należy wyświetlić arkusze amortyzacji utworzone w określonych firmach.</span><span class="sxs-lookup"><span data-stu-id="7a4ac-134">You must view the depreciation journals created in the respective legal entities.</span></span> <span data-ttu-id="7a4ac-135">Wybierz kolejno opcje Środki trwałe > Wpisy w arkuszu > Arkusz środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="7a4ac-135">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>

