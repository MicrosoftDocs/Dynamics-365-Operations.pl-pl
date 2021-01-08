---
title: Kopiowanie formuły
description: Ta procedura skupia się na tworzenie formuły zawierającej te same składniki co istniejąca formuła, ale z drobnymi różnicami.
author: ShylaThompson
manager: tfehr
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 26524f886a8af545869bacef4d57bfc14c0ed225
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4434950"
---
# <a name="copy-a-formula"></a><span data-ttu-id="16aac-103">Kopiowanie formuły</span><span class="sxs-lookup"><span data-stu-id="16aac-103">Copy a formula</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="16aac-104">Ta procedura skupia się na tworzenie formuły zawierającej te same składniki co istniejąca formuła, ale z drobnymi różnicami.</span><span class="sxs-lookup"><span data-stu-id="16aac-104">This procedure focuses on creating a formula that includes the same ingredients as an existing formula, but with minor differences.</span></span> <span data-ttu-id="16aac-105">Aby utworzyć wiersze formuły, możesz użyć funkcji kopiowania w celu skopiowania istniejącej formuły zawierającej najwięcej składników, których potrzebujesz.</span><span class="sxs-lookup"><span data-stu-id="16aac-105">To create the formula lines, you can use the Copy function to copy an existing formula that has most of the ingredients that you need.</span></span> <span data-ttu-id="16aac-106">Następnie można wprowadzić niezbędne zmiany w poszczególnych wierszach nowej wersji.</span><span class="sxs-lookup"><span data-stu-id="16aac-106">You can then make any necessary changes to the individual lines in the new version.</span></span> <span data-ttu-id="16aac-107">Używając funkcji kopiowania, nie trzeba utworzyć wielu formuł, które są prawie jednakowe.</span><span class="sxs-lookup"><span data-stu-id="16aac-107">By using the Copy function, you do not have to create multiple formulas that are almost identical.</span></span> <span data-ttu-id="16aac-108">Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USP2.</span><span class="sxs-lookup"><span data-stu-id="16aac-108">The demo data company used to create this task is USP2.</span></span>


## <a name="create-a-formula"></a><span data-ttu-id="16aac-109">Tworzenie formuły</span><span class="sxs-lookup"><span data-stu-id="16aac-109">Create a formula</span></span>
1. <span data-ttu-id="16aac-110">Wybierz kolejno opcje Zarządzanie informacjami o produktach > Listy składowe (BOM) i formuły > Formuły.</span><span class="sxs-lookup"><span data-stu-id="16aac-110">Go to Product information management > Bills of materials and formulas > Formulas.</span></span>
2. <span data-ttu-id="16aac-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="16aac-111">Click New.</span></span>
3. <span data-ttu-id="16aac-112">W polu Formuła wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="16aac-112">In the Formula field, type a value.</span></span>
4. <span data-ttu-id="16aac-113">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="16aac-113">In the Name field, type a value.</span></span>
    * <span data-ttu-id="16aac-114">Nadaj formule sugestywną nazwę.</span><span class="sxs-lookup"><span data-stu-id="16aac-114">Type a meaningful name for the formula.</span></span>  
5. <span data-ttu-id="16aac-115">W polu Oddział kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="16aac-115">In the Site field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="16aac-116">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="16aac-116">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="16aac-117">W polu Grupa towarów kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="16aac-117">In the Item group field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="16aac-118">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="16aac-118">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="16aac-119">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="16aac-119">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="16aac-120">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="16aac-120">Click Save.</span></span>

## <a name="copy-formula-lines"></a><span data-ttu-id="16aac-121">Kopiowanie wierszy formuły</span><span class="sxs-lookup"><span data-stu-id="16aac-121">Copy formula lines</span></span>
1. <span data-ttu-id="16aac-122">W okienku akcji kliknij pozycję Formuła.</span><span class="sxs-lookup"><span data-stu-id="16aac-122">On the Action Pane, click Formula.</span></span>
2. <span data-ttu-id="16aac-123">Kliknij opcję Kopiuj.</span><span class="sxs-lookup"><span data-stu-id="16aac-123">Click Copy.</span></span>
3. <span data-ttu-id="16aac-124">W polu Numer towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="16aac-124">In the Item number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="16aac-125">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="16aac-125">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="16aac-126">W polu Wersja formuły kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="16aac-126">In the Formula version field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="16aac-127">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="16aac-127">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="16aac-128">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="16aac-128">Click OK.</span></span>

## <a name="adjust-copied-formula-lines"></a><span data-ttu-id="16aac-129">Korygowanie skopiowanych wierszy formuły</span><span class="sxs-lookup"><span data-stu-id="16aac-129">Adjust copied formula lines</span></span>
1. <span data-ttu-id="16aac-130">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="16aac-130">In the list, mark the selected row.</span></span>
2. <span data-ttu-id="16aac-131">Kliknij przycisk Usuń.</span><span class="sxs-lookup"><span data-stu-id="16aac-131">Click Delete.</span></span>
3. <span data-ttu-id="16aac-132">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="16aac-132">Click Yes.</span></span>

## <a name="approve-formula"></a><span data-ttu-id="16aac-133">Zatwierdź formułę</span><span class="sxs-lookup"><span data-stu-id="16aac-133">Approve formula</span></span>
1. <span data-ttu-id="16aac-134">W okienku akcji kliknij pozycję Formuła.</span><span class="sxs-lookup"><span data-stu-id="16aac-134">On the Action Pane, click Formula.</span></span>
2. <span data-ttu-id="16aac-135">Kliknij przycisk Zatwierdź formułę.</span><span class="sxs-lookup"><span data-stu-id="16aac-135">Click Approve formula.</span></span>
3. <span data-ttu-id="16aac-136">W polu Zatwierdzone przez kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="16aac-136">In the Approved by field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="16aac-137">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="16aac-137">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="16aac-138">Kliknij opcję Wybierz.</span><span class="sxs-lookup"><span data-stu-id="16aac-138">Click Select.</span></span>
6. <span data-ttu-id="16aac-139">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="16aac-139">Click OK.</span></span>

