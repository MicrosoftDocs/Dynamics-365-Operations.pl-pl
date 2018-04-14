--- 
title: "Tworzenie reguł zaawansowanych dla arkuszy"
description: "Ta procedura prowadzi przez proces tworzenia zaawansowanych reguł dla arkuszy."
author: aprilolson
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 36f4edd6fa9711022e291ea5ceffbcc9ef55b2a9
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---
# <a name="create-advanced-rules-for-journals"></a><span data-ttu-id="9fc4a-103">Tworzenie reguł zaawansowanych dla arkuszy</span><span class="sxs-lookup"><span data-stu-id="9fc4a-103">Create advanced rules for journals</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9fc4a-104">Ta procedura prowadzi przez proces tworzenia zaawansowanych reguł dla arkuszy.</span><span class="sxs-lookup"><span data-stu-id="9fc4a-104">This procedure steps through creating advanced rules for journals.</span></span> <span data-ttu-id="9fc4a-105">Obejmuje skonfigurowanie kontroli arkusza i ograniczeń księgowania dla użytkowników.</span><span class="sxs-lookup"><span data-stu-id="9fc4a-105">This includes setting up journal control and user posting restrictions.</span></span> <span data-ttu-id="9fc4a-106">Procedura wykorzystuje dane firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="9fc4a-106">This procedure uses the USMF demo data company.</span></span>


## <a name="set-up-journal-control"></a><span data-ttu-id="9fc4a-107">Konfigurowanie kontroli arkusza</span><span class="sxs-lookup"><span data-stu-id="9fc4a-107">Set up journal control</span></span>
1. <span data-ttu-id="9fc4a-108">Wybierz kolejno opcje Księga główna > Konfiguracja arkusza > Nazwy arkuszy.</span><span class="sxs-lookup"><span data-stu-id="9fc4a-108">Go to General ledger > Journal setup > Journal names.</span></span>
2. <span data-ttu-id="9fc4a-109">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="9fc4a-109">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="9fc4a-110">Kliknij opcję Kontrola arkusza.</span><span class="sxs-lookup"><span data-stu-id="9fc4a-110">Click Journal control.</span></span>
4. <span data-ttu-id="9fc4a-111">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="9fc4a-111">Click Add.</span></span>
5. <span data-ttu-id="9fc4a-112">W polu Firmy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="9fc4a-112">In the Company accounts field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="9fc4a-113">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="9fc4a-113">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="9fc4a-114">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="9fc4a-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="9fc4a-115">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="9fc4a-115">Click Add.</span></span>
9. <span data-ttu-id="9fc4a-116">W polu Struktura konta kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="9fc4a-116">In the Account structure field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="9fc4a-117">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="9fc4a-117">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="9fc4a-118">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="9fc4a-118">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="9fc4a-119">W polu Segment kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="9fc4a-119">In the Segment field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="9fc4a-120">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="9fc4a-120">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="9fc4a-121">W polu Od wartości kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="9fc4a-121">In the From value field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="9fc4a-122">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="9fc4a-122">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="9fc4a-123">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="9fc4a-123">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="9fc4a-124">W polu Do wartości kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="9fc4a-124">In the To value field, click the drop-down button to open the lookup.</span></span>
18. <span data-ttu-id="9fc4a-125">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="9fc4a-125">In the list, find and select the desired record.</span></span>
19. <span data-ttu-id="9fc4a-126">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="9fc4a-126">In the list, click the link in the selected row.</span></span>

## <a name="set-up-posting-restrictions"></a><span data-ttu-id="9fc4a-127">Konfigurowanie ograniczeń księgowania</span><span class="sxs-lookup"><span data-stu-id="9fc4a-127">Set up posting restrictions</span></span>
1. <span data-ttu-id="9fc4a-128">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="9fc4a-128">Close the page.</span></span>
2. <span data-ttu-id="9fc4a-129">Kliknij opcję Ograniczenia księgowania.</span><span class="sxs-lookup"><span data-stu-id="9fc4a-129">Click Posting restrictions.</span></span>
3. <span data-ttu-id="9fc4a-130">W ustawieniu Jak chcesz skonfigurować ograniczenia księgowania wybierz opcję Według grupy użytkowników.</span><span class="sxs-lookup"><span data-stu-id="9fc4a-130">In the How do you want to set up posting restrictions, select By user group.</span></span>
4. <span data-ttu-id="9fc4a-131">W drzewie zaznacz grupę, której chcesz pozwolić na księgowanie w tym arkuszu.</span><span class="sxs-lookup"><span data-stu-id="9fc4a-131">In the tree, check 'the group that you want to allow posting for this journal name.'.</span></span>
5. <span data-ttu-id="9fc4a-132">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="9fc4a-132">Click OK.</span></span>


