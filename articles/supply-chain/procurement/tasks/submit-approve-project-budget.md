---
title: Przesyłanie i zatwierdzanie budżetu projektu
description: W tej procedurze pokazano, jak utworzyć i przesłać budżet projektu.
author: RichardLuan
manager: tfehr
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage, ProjTable, ProjBudget, WorkflowSubmitDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Service industries
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 72ac6705ef8584ef41980a1cc9490227538de365
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222856"
---
# <a name="submit-and-approve-project-budget"></a><span data-ttu-id="f13f8-103">Przesyłanie i zatwierdzanie budżetu projektu</span><span class="sxs-lookup"><span data-stu-id="f13f8-103">Submit and approve project budget</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f13f8-104">W tej procedurze pokazano, jak utworzyć i przesłać budżet projektu.</span><span class="sxs-lookup"><span data-stu-id="f13f8-104">This procedure shows you how to create and submit the budget for a project.</span></span> 

<span data-ttu-id="f13f8-105">Podczas tworzenia budżetu projektu można wprowadzić szacowane przychody i koszty projektu, a następnie użyć ich do kontrolowania rzeczywistych transakcji w projekcie.</span><span class="sxs-lookup"><span data-stu-id="f13f8-105">When you create a project budget, you can enter estimated revenues and costs for a project, and then use those to control actual project transactions.</span></span> <span data-ttu-id="f13f8-106">W budżetowaniu projektu wszystkie oryginalne budżety i korekty muszą zostać wysłane do przepływu pracy projektu w celu zatwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="f13f8-106">In project budgeting, all original budgets and revisions must be sent to project workflow for approval.</span></span> <span data-ttu-id="f13f8-107">Przepływ pracy daje większą kontrolę nad procesem i tworzy rekord historii zmian.</span><span class="sxs-lookup"><span data-stu-id="f13f8-107">Workflow gives you increased control over the process and creates a change history record.</span></span>

<span data-ttu-id="f13f8-108">Zadanie utworzono przy użyciu zestawu danych firmy USSI.</span><span class="sxs-lookup"><span data-stu-id="f13f8-108">This task was created using the USSI data set.</span></span>

1. <span data-ttu-id="f13f8-109">W **okienku nawigacji** przejdź do **Moduły > Zarządzanie projektami i ich księgowanie > projekty > Wszystkie projekty**.</span><span class="sxs-lookup"><span data-stu-id="f13f8-109">In the **Navigation pane**, go to **Modules > Project management and accounting > Projects > All projects**.</span></span>
2. <span data-ttu-id="f13f8-110">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="f13f8-110">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="f13f8-111">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="f13f8-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="f13f8-112">W **okienku akcji** kliknij pozycję **Plan**.</span><span class="sxs-lookup"><span data-stu-id="f13f8-112">On the **Action Pane**, click **Plan**.</span></span>
5. <span data-ttu-id="f13f8-113">Kliknij opcję **Budżet projektu**.</span><span class="sxs-lookup"><span data-stu-id="f13f8-113">Click **Project budget**.</span></span>
6. <span data-ttu-id="f13f8-114">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="f13f8-114">In the **Description** field, type a value.</span></span>
7. <span data-ttu-id="f13f8-115">Rozwiń skróconą kartę **Koszt**.</span><span class="sxs-lookup"><span data-stu-id="f13f8-115">Expand the **Cost** fastTab.</span></span>
8. <span data-ttu-id="f13f8-116">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="f13f8-116">Click **New**.</span></span>
9. <span data-ttu-id="f13f8-117">W polu **Typ transakcji** zaznacz opcję.</span><span class="sxs-lookup"><span data-stu-id="f13f8-117">In the **Transaction type** field, select an option.</span></span>
10. <span data-ttu-id="f13f8-118">W polu **Kategoria** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f13f8-118">In the **Category** field, enter or select a value.</span></span>
11. <span data-ttu-id="f13f8-119">W polu **Budżet pierwotny** wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="f13f8-119">In the **Original budget** field, enter a number.</span></span>
12. <span data-ttu-id="f13f8-120">Rozwiń skróconą kartę **Przychody**.</span><span class="sxs-lookup"><span data-stu-id="f13f8-120">Expand the **Revenues** fastTab.</span></span>
13. <span data-ttu-id="f13f8-121">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="f13f8-121">Click **New**.</span></span>
14. <span data-ttu-id="f13f8-122">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="f13f8-122">In the list, mark the selected row.</span></span>
15. <span data-ttu-id="f13f8-123">W polu **Typ transakcji** zaznacz opcję.</span><span class="sxs-lookup"><span data-stu-id="f13f8-123">In the **Transaction type** field, select an option.</span></span>
16. <span data-ttu-id="f13f8-124">W polu **Kategoria** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f13f8-124">In the **Category** field, enter or select a value.</span></span>
17. <span data-ttu-id="f13f8-125">W polu **Budżet pierwotny** wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="f13f8-125">In the **Original budget** field, enter a number.</span></span>
18. <span data-ttu-id="f13f8-126">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f13f8-126">Click **Save**.</span></span>
19. <span data-ttu-id="f13f8-127">Kliknij opcję **Przepływ pracy**.</span><span class="sxs-lookup"><span data-stu-id="f13f8-127">Click **Workflow**.</span></span>
20. <span data-ttu-id="f13f8-128">Kliknij przycisk **Prześlij**.</span><span class="sxs-lookup"><span data-stu-id="f13f8-128">Click **Submit**.</span></span>
21. <span data-ttu-id="f13f8-129">W polu **Komentarz** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="f13f8-129">In the **Comment** field, type a value.</span></span>
22. <span data-ttu-id="f13f8-130">Kliknij przycisk **Prześlij**.</span><span class="sxs-lookup"><span data-stu-id="f13f8-130">Click **Submit**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]