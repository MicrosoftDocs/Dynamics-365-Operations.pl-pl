--- 
title: "Kopiowanie produktów towarzyszących z istniejącej wersji formuły"
description: "W tej procedurze pokazano sposób kopiowania produktów towarzyszących z istniejącej wersji formuły do innej wersji formuły dla zwolnionego produktu."
author: YuyuScheller
manager: AnnBe
ms.date: 06/06/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: e6ca0de2956e7e2b76f1286b0d01a3a2e3f3d53d
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---
# <a name="copy-co-products-from-an-existing-formula-version"></a><span data-ttu-id="8707e-103">Kopiowanie produktów towarzyszących z istniejącej wersji formuły</span><span class="sxs-lookup"><span data-stu-id="8707e-103">Copy co-products from an existing formula version</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8707e-104">W tej procedurze pokazano sposób kopiowania produktów towarzyszących z istniejącej wersji formuły do innej wersji formuły dla zwolnionego produktu.</span><span class="sxs-lookup"><span data-stu-id="8707e-104">This procedure shows how to copy co-products from an existing formula version to a different formula version for a released product.</span></span> <span data-ttu-id="8707e-105">Warunkiem wstępnym jest istnienie co najmniej jednej wersji formuły skojarzonej z produktami towarzyszącymi.</span><span class="sxs-lookup"><span data-stu-id="8707e-105">It is a prerequisite that there is at least one formula version associated with co-products.</span></span> <span data-ttu-id="8707e-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USP2.</span><span class="sxs-lookup"><span data-stu-id="8707e-106">The demo data company USP2 is used to create this procedure.</span></span>


## <a name="find-a-released-product"></a><span data-ttu-id="8707e-107">Znajdowanie zwolnionego produktu</span><span class="sxs-lookup"><span data-stu-id="8707e-107">Find a released product</span></span>
1. <span data-ttu-id="8707e-108">Przejdź do okna Zwolnione produkty.</span><span class="sxs-lookup"><span data-stu-id="8707e-108">Go to Released products.</span></span>
2. <span data-ttu-id="8707e-109">Kliknij przycisk Pokaż filtry.</span><span class="sxs-lookup"><span data-stu-id="8707e-109">Click Show filters.</span></span>
    * <span data-ttu-id="8707e-110">Masz zamiar dodać pole Typ produkcji w oknie dialogowym Filtr.</span><span class="sxs-lookup"><span data-stu-id="8707e-110">You are about to add the field Production type in the filter dialog box.</span></span>  
3. <span data-ttu-id="8707e-111">Kliknij przycisk Dodaj pole filtru, aby dodać pole Typ produkcji.</span><span class="sxs-lookup"><span data-stu-id="8707e-111">Click Add a filter field to add the field Production type.</span></span>
    * <span data-ttu-id="8707e-112">W następnym kroku należy ręcznie wprowadzić formułę w polu Typ produkcji, a następnie kliknąć przycisk Zastosuj.</span><span class="sxs-lookup"><span data-stu-id="8707e-112">In the next step, you need to manually enter Formula in the Production type field before you select Apply.</span></span> <span data-ttu-id="8707e-113">Spowoduje to ustawienie filtru listy zwolnionych produktów.</span><span class="sxs-lookup"><span data-stu-id="8707e-113">This sets the filter on the list of released products.</span></span>  
4. <span data-ttu-id="8707e-114">W polu Typ produkcji ręcznie wprowadź formułę.</span><span class="sxs-lookup"><span data-stu-id="8707e-114">Manually enter Formula in the Production type field.</span></span>
5. <span data-ttu-id="8707e-115">Kliknij polecenie Zastosuj.</span><span class="sxs-lookup"><span data-stu-id="8707e-115">Click Apply.</span></span>

## <a name="select-a-released-product"></a><span data-ttu-id="8707e-116">Wybór zwalnianego produktu</span><span class="sxs-lookup"><span data-stu-id="8707e-116">Select a released product</span></span>
1. <span data-ttu-id="8707e-117">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="8707e-117">In the list, find and select the desired record.</span></span>
2. <span data-ttu-id="8707e-118">Kliknij opcję Wersje formuły.</span><span class="sxs-lookup"><span data-stu-id="8707e-118">Click Formula versions.</span></span>
    * <span data-ttu-id="8707e-119">W okienku akcji Inżynieria kliknij opcję Wersje formuły.</span><span class="sxs-lookup"><span data-stu-id="8707e-119">On the Engineering Action Pane, click Formula versions.</span></span>  

## <a name="copy-co-products"></a><span data-ttu-id="8707e-120">Kopiowanie produktów towarzyszących</span><span class="sxs-lookup"><span data-stu-id="8707e-120">Copy co-products</span></span>
1. <span data-ttu-id="8707e-121">W okienku akcji kliknij pozycję Wersja formuły.</span><span class="sxs-lookup"><span data-stu-id="8707e-121">On the Action Pane, click Formula version.</span></span>
2. <span data-ttu-id="8707e-122">Kliknij przycisk Produkty towarzyszące.</span><span class="sxs-lookup"><span data-stu-id="8707e-122">Click Co-products.</span></span>
3. <span data-ttu-id="8707e-123">Kliknij opcję Kopiuj.</span><span class="sxs-lookup"><span data-stu-id="8707e-123">Click Copy.</span></span>
4. <span data-ttu-id="8707e-124">W polu Numer towaru wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="8707e-124">In the Item number field, enter or select a value.</span></span>
5. <span data-ttu-id="8707e-125">W polu Wersja formuły wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="8707e-125">In the Formula version field, enter or select a value.</span></span>
6. <span data-ttu-id="8707e-126">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="8707e-126">Click OK.</span></span>
7. <span data-ttu-id="8707e-127">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="8707e-127">Close the page.</span></span>


