--- 
title: "Przesyłanie i zatwierdzanie budżetu projektu"
description: "W tej procedurze pokazano, jak utworzyć i przesłać budżet projektu."
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjProjectsListPage, ProjTable, ProjBudget, WorkflowSubmitDialog
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: f727e19d3f8c424b1c59e52602b7e907151f4492
ms.contentlocale: pl-pl
ms.lasthandoff: 09/14/2018

---
# <a name="submit-and-approve-project-budget"></a><span data-ttu-id="bcc34-103">Przesyłanie i zatwierdzanie budżetu projektu</span><span class="sxs-lookup"><span data-stu-id="bcc34-103">Submit and approve project budget</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bcc34-104">W tej procedurze pokazano, jak utworzyć i przesłać budżet projektu.</span><span class="sxs-lookup"><span data-stu-id="bcc34-104">This procedure shows you how to create and submit the budget for a project.</span></span> 

<span data-ttu-id="bcc34-105">Podczas tworzenia budżetu projektu można wprowadzić szacowane przychody i koszty projektu, a następnie użyć ich do kontrolowania rzeczywistych transakcji w projekcie.</span><span class="sxs-lookup"><span data-stu-id="bcc34-105">When you create a project budget, you can enter estimated revenues and costs for a project, and then use those to control actual project transactions.</span></span> <span data-ttu-id="bcc34-106">W budżetowaniu projektu wszystkie oryginalne budżety i korekty muszą zostać wysłane do przepływu pracy projektu w celu zatwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="bcc34-106">In project budgeting, all original budgets and revisions must be sent to project workflow for approval.</span></span> <span data-ttu-id="bcc34-107">Przepływ pracy daje większą kontrolę nad procesem i tworzy rekord historii zmian.</span><span class="sxs-lookup"><span data-stu-id="bcc34-107">Workflow gives you increased control over the process and creates a change history record.</span></span>

<span data-ttu-id="bcc34-108">Zadanie utworzono przy użyciu zestawu danych firmy USSI.</span><span class="sxs-lookup"><span data-stu-id="bcc34-108">This task was created using the USSI data set.</span></span>

1. <span data-ttu-id="bcc34-109">Wybierz kolejno opcje Zarządzanie projektami i ich księgowanie> Projekty > Wszystkie projekty.</span><span class="sxs-lookup"><span data-stu-id="bcc34-109">Go to Project management and accounting > Projects > All projects.</span></span>
2. <span data-ttu-id="bcc34-110">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="bcc34-110">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="bcc34-111">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="bcc34-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="bcc34-112">W okienku akcji kliknij pozycję Plan.</span><span class="sxs-lookup"><span data-stu-id="bcc34-112">On the Action Pane, click Plan.</span></span>
5. <span data-ttu-id="bcc34-113">Kliknij opcję Budżet projektu.</span><span class="sxs-lookup"><span data-stu-id="bcc34-113">Click Project budget.</span></span>
6. <span data-ttu-id="bcc34-114">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="bcc34-114">In the Description field, type a value.</span></span>
7. <span data-ttu-id="bcc34-115">Rozwiń sekcję Koszt.</span><span class="sxs-lookup"><span data-stu-id="bcc34-115">Expand the Cost section</span></span>
8. <span data-ttu-id="bcc34-116">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="bcc34-116">Click New.</span></span>
9. <span data-ttu-id="bcc34-117">W polu Typ transakcji zaznacz opcję.</span><span class="sxs-lookup"><span data-stu-id="bcc34-117">In the Transaction type field, select an option.</span></span>
10. <span data-ttu-id="bcc34-118">W polu Kategoria wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="bcc34-118">In the Category field, enter or select a value.</span></span>
11. <span data-ttu-id="bcc34-119">W polu Budżet pierwotny wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="bcc34-119">In the Original budget field, enter a number.</span></span>
12. <span data-ttu-id="bcc34-120">Rozwiń sekcję Przychody.</span><span class="sxs-lookup"><span data-stu-id="bcc34-120">Expand the Revenues section.</span></span>
13. <span data-ttu-id="bcc34-121">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="bcc34-121">Click New.</span></span>
14. <span data-ttu-id="bcc34-122">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="bcc34-122">In the list, mark the selected row.</span></span>
15. <span data-ttu-id="bcc34-123">W polu Typ transakcji zaznacz opcję.</span><span class="sxs-lookup"><span data-stu-id="bcc34-123">In the Transaction type field, select an option.</span></span>
16. <span data-ttu-id="bcc34-124">W polu Kategoria wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="bcc34-124">In the Category field, enter or select a value.</span></span>
17. <span data-ttu-id="bcc34-125">W polu Budżet pierwotny wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="bcc34-125">In the Original budget field, enter a number.</span></span>
18. <span data-ttu-id="bcc34-126">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="bcc34-126">Click Save.</span></span>
19. <span data-ttu-id="bcc34-127">Kliknij opcję Przepływ pracy.</span><span class="sxs-lookup"><span data-stu-id="bcc34-127">Click Workflow.</span></span>
20. <span data-ttu-id="bcc34-128">Kliknij przycisk Prześlij.</span><span class="sxs-lookup"><span data-stu-id="bcc34-128">Click Submit.</span></span>
21. <span data-ttu-id="bcc34-129">W polu Komentarz wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="bcc34-129">In the Comment field, type a value.</span></span>
22. <span data-ttu-id="bcc34-130">Kliknij przycisk Prześlij.</span><span class="sxs-lookup"><span data-stu-id="bcc34-130">Click Submit.</span></span>


