---
title: Tworzenie i przypisywanie struktur reguł zaawansowanych
description: W tym temacie wyjaśniono, jak utworzyć i przypisać strukturę reguły zaawansowanej do struktury konta.
author: aprilolson
manager: AnnBe
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountRuleStructure, DimensionCreateAccountRuleStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate, DimensionConfigureAccountStructure, DimensionConfigureAccountRule, DimensionCreateAccountRule, DimensionSelectAccountRuleStructure
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cff07c13553ea140f537160da7f93820d5e3f77a
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2175587"
---
# <a name="create-and-assign-advanced-rule-structures"></a><span data-ttu-id="72fd1-103">Tworzenie i przypisywanie struktur reguł zaawansowanych</span><span class="sxs-lookup"><span data-stu-id="72fd1-103">Create and assign advanced rule structures</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="72fd1-104">W tym temacie wyjaśniono, jak utworzyć i przypisać strukturę reguły zaawansowanej do struktury konta.</span><span class="sxs-lookup"><span data-stu-id="72fd1-104">This topic explains how to create and assign an advanced rule structure to an account structure.</span></span> <span data-ttu-id="72fd1-105">W przewodniku jest wykorzystywana firma demonstracyjna USMF.</span><span class="sxs-lookup"><span data-stu-id="72fd1-105">This guide uses the USMF demo company.</span></span>

## <a name="create-an-advanced-rule-structure"></a><span data-ttu-id="72fd1-106">Utwórz strukturę reguły zaawansowanej</span><span class="sxs-lookup"><span data-stu-id="72fd1-106">Create an advanced rule structure</span></span>
1. <span data-ttu-id="72fd1-107">Wybierz kolejno opcje **Okienko nawigacji > Moduły > Księga główna > Plan kont > Struktury > Struktury reguł zaawansowanych**.</span><span class="sxs-lookup"><span data-stu-id="72fd1-107">Go to **Navigation pane > Modules > General ledger > Chart of accounts > Structures > Advanced rule structures**.</span></span>
2. <span data-ttu-id="72fd1-108">Wybierz **Nowe**, aby otworzyć listę rozwijania.</span><span class="sxs-lookup"><span data-stu-id="72fd1-108">Select **New** to open the drop dialog.</span></span>
3. <span data-ttu-id="72fd1-109">W polu **Struktura reguły zaawansowanej** wprowadź nazwę opisującą strukturę reguły.</span><span class="sxs-lookup"><span data-stu-id="72fd1-109">In the **Advanced rule structure** field, type a name to describe the rule structure.</span></span>
4. <span data-ttu-id="72fd1-110">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="72fd1-110">Select **OK**.</span></span>
5. <span data-ttu-id="72fd1-111">Wybierz opcję **Dodaj segment**.</span><span class="sxs-lookup"><span data-stu-id="72fd1-111">Select **Add segment**.</span></span>
6. <span data-ttu-id="72fd1-112">Na liście segmentów wybierz wymiar finansowy.</span><span class="sxs-lookup"><span data-stu-id="72fd1-112">In the list of segments, select a financial dimension.</span></span> <span data-ttu-id="72fd1-113">Na przykład **Sklep**.</span><span class="sxs-lookup"><span data-stu-id="72fd1-113">For example, **Store**.</span></span>  
7. <span data-ttu-id="72fd1-114">Wybierz opcję **Dodaj segment**.</span><span class="sxs-lookup"><span data-stu-id="72fd1-114">Select **Add segment**.</span></span>
8. <span data-ttu-id="72fd1-115">Wybierz **Aktywuj**.</span><span class="sxs-lookup"><span data-stu-id="72fd1-115">Select **Activate**.</span></span>

## <a name="apply-an-advanced-rule-structure-to-an-account-structure"></a><span data-ttu-id="72fd1-116">Stosowanie struktury reguły zaawansowanej do struktury konta</span><span class="sxs-lookup"><span data-stu-id="72fd1-116">Apply an advanced rule structure to an account structure</span></span>
1. <span data-ttu-id="72fd1-117">Wybierz kolejno opcje **Okienko nawigacji > Moduły > Księga główna > Plan kont > Struktury > Konfigurowanie struktur kont**.</span><span class="sxs-lookup"><span data-stu-id="72fd1-117">Go to **navigation pane > Modules > General ledger > Chart of accounts > Structures > Configure account structures**.</span></span>
2. <span data-ttu-id="72fd1-118">Na liście znajdź i wybierz strukturę konta, do której chcesz zastosować regułę zaawansowaną.</span><span class="sxs-lookup"><span data-stu-id="72fd1-118">In the list, find and select the account structure you want to apply the advanced rule to.</span></span>
3. <span data-ttu-id="72fd1-119">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="72fd1-119">Select **Edit**.</span></span> <span data-ttu-id="72fd1-120">Można także wybrać opcję **Reguły zaawansowane**, a pojawi się monit o przełączenie struktury konta do **Trybu roboczego**.</span><span class="sxs-lookup"><span data-stu-id="72fd1-120">You can also select **Advanced rules** and you will be prompted to put the account structure in **Draft mode**.</span></span>  
4. <span data-ttu-id="72fd1-121">Wybierz opcję **Reguły zaawansowane**.</span><span class="sxs-lookup"><span data-stu-id="72fd1-121">Select **Advanced rules**.</span></span>
5. <span data-ttu-id="72fd1-122">Wybierz **Nowe**, aby otworzyć listę rozwijania.</span><span class="sxs-lookup"><span data-stu-id="72fd1-122">Select **New** to open the drop dialog.</span></span>
6. <span data-ttu-id="72fd1-123">W polu **Reguła zaawansowana** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="72fd1-123">In the **Advanced rule** field, type a value.</span></span>
7. <span data-ttu-id="72fd1-124">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="72fd1-124">In the **Name** field, type a value.</span></span>
8. <span data-ttu-id="72fd1-125">Wybierz opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="72fd1-125">Select **Create**.</span></span>
9. <span data-ttu-id="72fd1-126">Wybierz opcję **Dodaj nowe kryteria**.</span><span class="sxs-lookup"><span data-stu-id="72fd1-126">Select **Add new criteria**.</span></span>
10. <span data-ttu-id="72fd1-127">W polu **Gdzie** wybierz konto główne lub wymiar finansowy.</span><span class="sxs-lookup"><span data-stu-id="72fd1-127">In the **Where** field, select main account or a financial dimension.</span></span>
11. <span data-ttu-id="72fd1-128">W polu **Operator** wybierz opcję, taką jak **zawiera się między** lub **zawiera**.</span><span class="sxs-lookup"><span data-stu-id="72fd1-128">In the **Operator** field, select an option, such as **is between** and **includes**.</span></span>
12. <span data-ttu-id="72fd1-129">W polu **Wartość** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="72fd1-129">In the **Value** field, type a value.</span></span>
13. <span data-ttu-id="72fd1-130">W polu **za pomocą** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="72fd1-130">In the **through** field, type a value.</span></span>
14. <span data-ttu-id="72fd1-131">Wybierz przycisk **Dodaj**, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="72fd1-131">Select **Add** to open the drop dialog.</span></span>
15. <span data-ttu-id="72fd1-132">Na liście znajdź strukturę reguły zaawansowanej, która ma być używana po spełnieniu wprowadzonych kryteriów.</span><span class="sxs-lookup"><span data-stu-id="72fd1-132">In the list, find the advanced rule structure you want to use when the criteria you entered is met.</span></span>
16. <span data-ttu-id="72fd1-133">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="72fd1-133">Select **Add**.</span></span>
17. <span data-ttu-id="72fd1-134">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="72fd1-134">Close the page.</span></span>
18. <span data-ttu-id="72fd1-135">Wybierz **Aktywuj**.</span><span class="sxs-lookup"><span data-stu-id="72fd1-135">Select **Activate**.</span></span>

