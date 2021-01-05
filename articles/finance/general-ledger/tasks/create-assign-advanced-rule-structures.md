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
ms.openlocfilehash: cb18b96d6d7db84262f8fcfadb15afa80e2fa3d8
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446681"
---
# <a name="create-and-assign-advanced-rule-structures"></a><span data-ttu-id="3aa05-103">Tworzenie i przypisywanie struktur reguł zaawansowanych</span><span class="sxs-lookup"><span data-stu-id="3aa05-103">Create and assign advanced rule structures</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3aa05-104">W tym temacie wyjaśniono, jak utworzyć i przypisać strukturę reguły zaawansowanej do struktury konta.</span><span class="sxs-lookup"><span data-stu-id="3aa05-104">This topic explains how to create and assign an advanced rule structure to an account structure.</span></span> <span data-ttu-id="3aa05-105">W przewodniku jest wykorzystywana firma demonstracyjna USMF.</span><span class="sxs-lookup"><span data-stu-id="3aa05-105">This guide uses the USMF demo company.</span></span>

## <a name="create-an-advanced-rule-structure"></a><span data-ttu-id="3aa05-106">Utwórz strukturę reguły zaawansowanej</span><span class="sxs-lookup"><span data-stu-id="3aa05-106">Create an advanced rule structure</span></span>
1. <span data-ttu-id="3aa05-107">Wybierz kolejno opcje **Okienko nawigacji > Moduły > Księga główna > Plan kont > Struktury > Struktury reguł zaawansowanych**.</span><span class="sxs-lookup"><span data-stu-id="3aa05-107">Go to **Navigation pane > Modules > General ledger > Chart of accounts > Structures > Advanced rule structures**.</span></span>
2. <span data-ttu-id="3aa05-108">Wybierz **Nowe**, aby otworzyć listę rozwijania.</span><span class="sxs-lookup"><span data-stu-id="3aa05-108">Select **New** to open the drop dialog.</span></span>
3. <span data-ttu-id="3aa05-109">W polu **Struktura reguły zaawansowanej** wprowadź nazwę opisującą strukturę reguły.</span><span class="sxs-lookup"><span data-stu-id="3aa05-109">In the **Advanced rule structure** field, type a name to describe the rule structure.</span></span>
4. <span data-ttu-id="3aa05-110">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="3aa05-110">Select **OK**.</span></span>
5. <span data-ttu-id="3aa05-111">Wybierz opcję **Dodaj segment**.</span><span class="sxs-lookup"><span data-stu-id="3aa05-111">Select **Add segment**.</span></span>
6. <span data-ttu-id="3aa05-112">Na liście segmentów wybierz wymiar finansowy.</span><span class="sxs-lookup"><span data-stu-id="3aa05-112">In the list of segments, select a financial dimension.</span></span> <span data-ttu-id="3aa05-113">Na przykład **Sklep**.</span><span class="sxs-lookup"><span data-stu-id="3aa05-113">For example, **Store**.</span></span>  
7. <span data-ttu-id="3aa05-114">Wybierz opcję **Dodaj segment**.</span><span class="sxs-lookup"><span data-stu-id="3aa05-114">Select **Add segment**.</span></span>
8. <span data-ttu-id="3aa05-115">Wybierz **Aktywuj**.</span><span class="sxs-lookup"><span data-stu-id="3aa05-115">Select **Activate**.</span></span>

## <a name="apply-an-advanced-rule-structure-to-an-account-structure"></a><span data-ttu-id="3aa05-116">Stosowanie struktury reguły zaawansowanej do struktury konta</span><span class="sxs-lookup"><span data-stu-id="3aa05-116">Apply an advanced rule structure to an account structure</span></span>
1. <span data-ttu-id="3aa05-117">Wybierz kolejno opcje **Okienko nawigacji > Moduły > Księga główna > Plan kont > Struktury > Konfigurowanie struktur kont**.</span><span class="sxs-lookup"><span data-stu-id="3aa05-117">Go to **navigation pane > Modules > General ledger > Chart of accounts > Structures > Configure account structures**.</span></span>
2. <span data-ttu-id="3aa05-118">Na liście znajdź i wybierz strukturę konta, do której chcesz zastosować regułę zaawansowaną.</span><span class="sxs-lookup"><span data-stu-id="3aa05-118">In the list, find and select the account structure you want to apply the advanced rule to.</span></span>
3. <span data-ttu-id="3aa05-119">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="3aa05-119">Select **Edit**.</span></span> <span data-ttu-id="3aa05-120">Można także wybrać opcję **Reguły zaawansowane**, a pojawi się monit o przełączenie struktury konta do **Trybu roboczego**.</span><span class="sxs-lookup"><span data-stu-id="3aa05-120">You can also select **Advanced rules** and you will be prompted to put the account structure in **Draft mode**.</span></span>  
4. <span data-ttu-id="3aa05-121">Wybierz opcję **Reguły zaawansowane**.</span><span class="sxs-lookup"><span data-stu-id="3aa05-121">Select **Advanced rules**.</span></span>
5. <span data-ttu-id="3aa05-122">Wybierz **Nowe**, aby otworzyć listę rozwijania.</span><span class="sxs-lookup"><span data-stu-id="3aa05-122">Select **New** to open the drop dialog.</span></span>
6. <span data-ttu-id="3aa05-123">W polu **Reguła zaawansowana** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3aa05-123">In the **Advanced rule** field, type a value.</span></span>
7. <span data-ttu-id="3aa05-124">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3aa05-124">In the **Name** field, type a value.</span></span>
8. <span data-ttu-id="3aa05-125">Wybierz opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="3aa05-125">Select **Create**.</span></span>
9. <span data-ttu-id="3aa05-126">Wybierz opcję **Dodaj nowe kryteria**.</span><span class="sxs-lookup"><span data-stu-id="3aa05-126">Select **Add new criteria**.</span></span>
10. <span data-ttu-id="3aa05-127">W polu **Gdzie** wybierz konto główne lub wymiar finansowy.</span><span class="sxs-lookup"><span data-stu-id="3aa05-127">In the **Where** field, select main account or a financial dimension.</span></span>
11. <span data-ttu-id="3aa05-128">W polu **Operator** wybierz opcję, taką jak **zawiera się między** lub **zawiera**.</span><span class="sxs-lookup"><span data-stu-id="3aa05-128">In the **Operator** field, select an option, such as **is between** and **includes**.</span></span>
12. <span data-ttu-id="3aa05-129">W polu **Wartość** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3aa05-129">In the **Value** field, type a value.</span></span>
13. <span data-ttu-id="3aa05-130">W polu **za pomocą** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3aa05-130">In the **through** field, type a value.</span></span>
14. <span data-ttu-id="3aa05-131">Wybierz przycisk **Dodaj**, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="3aa05-131">Select **Add** to open the drop dialog.</span></span>
15. <span data-ttu-id="3aa05-132">Na liście znajdź strukturę reguły zaawansowanej, która ma być używana po spełnieniu wprowadzonych kryteriów.</span><span class="sxs-lookup"><span data-stu-id="3aa05-132">In the list, find the advanced rule structure you want to use when the criteria you entered is met.</span></span>
16. <span data-ttu-id="3aa05-133">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="3aa05-133">Select **Add**.</span></span>
17. <span data-ttu-id="3aa05-134">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3aa05-134">Close the page.</span></span>
18. <span data-ttu-id="3aa05-135">Wybierz **Aktywuj**.</span><span class="sxs-lookup"><span data-stu-id="3aa05-135">Select **Activate**.</span></span>

