---
title: "Definicje księgowania"
description: "Ten artykuł zawiera informacje o definicjach księgowania oraz o sposobach ich tworzenia i łączenia. Dla obsługiwanych typów księgowania i dokumentów można używać definicji księgowania zamiast profili księgowania do klasyfikacji kont głównych i wymiarów finansowych dla zapisów księgowych."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: JournalizingDefinition, JournalizingDefinitionTrans, LedgerParameters
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 15741
ms.assetid: 1495e7e0-2e39-464c-8da9-f55b1ca1c6bb
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 88e9d1e593f58e8fc9e12ddac7664b6e67ecda6a
ms.contentlocale: pl-pl
ms.lasthandoff: 08/07/2018

---

# <a name="posting-definitions"></a><span data-ttu-id="444b6-104">Definicje księgowania</span><span class="sxs-lookup"><span data-stu-id="444b6-104">Posting definitions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="444b6-105">Ten artykuł zawiera informacje o definicjach księgowania oraz o sposobach ich tworzenia i łączenia.</span><span class="sxs-lookup"><span data-stu-id="444b6-105">This article provides information about posting definitions, and how to define and link them.</span></span> <span data-ttu-id="444b6-106">Dla obsługiwanych typów księgowania i dokumentów można używać definicji księgowania zamiast profili księgowania do klasyfikacji kont głównych i wymiarów finansowych dla zapisów księgowych.</span><span class="sxs-lookup"><span data-stu-id="444b6-106">For supported posting types and documents, you can use posting definitions instead of posting profiles to classify main accounts and financial dimensions on accounting entries.</span></span>

<span data-ttu-id="444b6-107">Dla obsługiwanych typów księgowania i dokumentów można używać definicji księgowania zamiast profili księgowania do klasyfikacji kont głównych i wymiarów finansowych dla zapisów księgowych.</span><span class="sxs-lookup"><span data-stu-id="444b6-107">For supported posting types and documents, you can use posting definitions instead of posting profiles to classify main accounts and financial dimensions on accounting entries.</span></span> <span data-ttu-id="444b6-108">Obsługiwane dokumenty i typy księgowania można wyświetlić na stronie **Definicje księgowania transakcji**.</span><span class="sxs-lookup"><span data-stu-id="444b6-108">You can view the supported documents and posting types on the **Transaction posting definitions** page.</span></span> 

<span data-ttu-id="444b6-109">Aby rozpocząć korzystanie z definicji księgowania, należy wybrać opcję **Użyj definicji księgowania** na stronie **Parametry księgi głównej**.</span><span class="sxs-lookup"><span data-stu-id="444b6-109">To start using posting definitions, select the **Use posting definitions** option on the **General ledger parameters** page.</span></span> <span data-ttu-id="444b6-110">Nawet jeśli korzystasz z definicji księgowania, nadal musisz zdefiniować profile księgowania dla inicjowanych wpisów i nieobsługiwanych typów księgowania i dokumentów.</span><span class="sxs-lookup"><span data-stu-id="444b6-110">Even when you use posting definitions, you must still define posting profiles for the originating entries and non-supported posting types and documents.</span></span> 

<span data-ttu-id="444b6-111">Definicje księgowania są wymagane do obsługi księgowania przyszłych zobowiązań wiążących dla zamówień zakupu i oraz przyszłych zobowiązań niewiążących dla zapotrzebowań na zakup.</span><span class="sxs-lookup"><span data-stu-id="444b6-111">You must use posting definitions in order to enable encumbrance accounting for purchase orders and pre-encumbrance accounting for purchase requisitions.</span></span>

## <a name="defining-posting-definitions"></a><span data-ttu-id="444b6-112">Określanie definicji księgowania</span><span class="sxs-lookup"><span data-stu-id="444b6-112">Defining posting definitions</span></span>
<span data-ttu-id="444b6-113">Użyj strony **Definicje księgowania**, aby określić kryteria uzgadniania i zdefiniować wpisy, które mają być generowane po wystąpieniu uzgodnienia.</span><span class="sxs-lookup"><span data-stu-id="444b6-113">Use the **Posting definitions** page to specify the match criteria and define the entries that should be generated when a match occurs.</span></span> <span data-ttu-id="444b6-114">Kryteria uzgadniania są obliczane dla inicjowanych wpisów jako zasady podziału księgowań.</span><span class="sxs-lookup"><span data-stu-id="444b6-114">The match criteria are evaluated for the originating entries as accounting distributions.</span></span> 

<span data-ttu-id="444b6-115">Na stronie **Definicje księgowania** możesz też przypisać numery priorytetów do wierszy wpisu, aby ustalić kolejność oceniania wierszy.</span><span class="sxs-lookup"><span data-stu-id="444b6-115">On the **Posting definitions** page, you can also assign priority numbers to entry lines to control the order in which the lines are evaluated.</span></span> <span data-ttu-id="444b6-116">Wiersze z najniższym priorytetem są oceniany jako pierwsze.</span><span class="sxs-lookup"><span data-stu-id="444b6-116">The lines that have the lowest priority number are evaluated first.</span></span> <span data-ttu-id="444b6-117">Na przykład oceniane są wszystkie wiersze z priorytetem 1, następnie wiersze z priorytetem 2 itd.</span><span class="sxs-lookup"><span data-stu-id="444b6-117">For example, all lines that have a priority of 1 are evaluated, and then lines that have a priority of 2, and so on.</span></span> <span data-ttu-id="444b6-118">Jeśli zostanie znaleziony odpowiednik, kryteria dopasowania są ignorowane.</span><span class="sxs-lookup"><span data-stu-id="444b6-118">When a match is found, the other match criteria are ignored.</span></span> <span data-ttu-id="444b6-119">Oprócz tego tylko kryteria w grupie spełniających pierwotnej transakcji spowodować wpisu wygenerowanego</span><span class="sxs-lookup"><span data-stu-id="444b6-119">Additionally, only the criteria in the group that match the originating transaction create generated entries.</span></span> 

<span data-ttu-id="444b6-120">Można sprawdzić poprawność definicji księgowania za pomocą kreatora **Testu definicji księgowania**.</span><span class="sxs-lookup"><span data-stu-id="444b6-120">You can validate your posting definitions by using the **Test posting definition** wizard.</span></span> <span data-ttu-id="444b6-121">Po zdefiniowaniu wpisu, z którego pochodzi próbka do definicji księgowania, pojawią się wygenerowane wpisy.</span><span class="sxs-lookup"><span data-stu-id="444b6-121">After you define a sample originating entry for a posting definition, you'll see the generated entries.</span></span> 

<span data-ttu-id="444b6-122">Możesz używać wersji definicji księgowania razem z datami obowiązywania.</span><span class="sxs-lookup"><span data-stu-id="444b6-122">You can use posting definition versions together with effective dates.</span></span> <span data-ttu-id="444b6-123">Na przykład możesz utworzyć przyszłą wersji definicji księgowania do księgowania na innym koncie księgowym w nowym roku obrachunkowym.</span><span class="sxs-lookup"><span data-stu-id="444b6-123">For example, you can create a future version of a posting definition to post to a different ledger account in a new fiscal year.</span></span> 

<span data-ttu-id="444b6-124">Użyj strony **Definicje księgowania transakcji**, aby przypisać definicje księgowania do typów transakcji.</span><span class="sxs-lookup"><span data-stu-id="444b6-124">Use the **Transaction posting definitions** page to assign posting definitions to transaction types.</span></span>

## <a name="linking-posting-definitions"></a><span data-ttu-id="444b6-125">Łączenie definicji księgowania</span><span class="sxs-lookup"><span data-stu-id="444b6-125">Linking posting definitions</span></span>
<span data-ttu-id="444b6-126">Można tworzyć połączenia między definicjami księgowania podczas tworzenia nowej definicji księgowania.</span><span class="sxs-lookup"><span data-stu-id="444b6-126">You can link from one posting definition to another when you create posting definitions.</span></span> <span data-ttu-id="444b6-127">Kryteria definicji, z którą tworzone jest połączenie, są następnie uwzględniane oprócz kryteriów bieżącej definicji księgowania.</span><span class="sxs-lookup"><span data-stu-id="444b6-127">The criteria for the definition that you linked to are then considered in addition to the criteria for the current posting definition.</span></span> <span data-ttu-id="444b6-128">Ta funkcja pomaga zaoszczędzić czas, ponieważ nie trzeba ponownie wprowadzić kryteriów na skróconej karcie **Wpisy** na stronie **Definicje księgowania** dla bieżącej definicji księgowania, jeśli te wiersze zostały już wpisane w innej definicji.</span><span class="sxs-lookup"><span data-stu-id="444b6-128">This feature helps save you time, because you don't have to reenter criteria on the **Entries** FastTab on the **Posting definitions** page for the current posting definition if you already entered those lines for another definition.</span></span> 

<span data-ttu-id="444b6-129">Na wykresach lub w tabelach możesz uwzględnić dowolne łącza, których można użyć.</span><span class="sxs-lookup"><span data-stu-id="444b6-129">In the diagrams or tables, include any links that you might use.</span></span> <span data-ttu-id="444b6-130">Aby uniknąć konfliktów z bieżącą definicją księgowania, upewnij się, że wiersze we wszystkich definicjach księgowania, z którym tworzone jest połączenie, są niepowtarzalne.</span><span class="sxs-lookup"><span data-stu-id="444b6-130">To avoid conflicts with the current posting definition, make sure that the lines in any posting definitions that you link to are unique.</span></span> 

<span data-ttu-id="444b6-131">Przy tworzeniu połączeń w definicjach księgowania obowiązują następujące ograniczenia:</span><span class="sxs-lookup"><span data-stu-id="444b6-131">The following restrictions apply when you create links in posting definitions:</span></span>

-   <span data-ttu-id="444b6-132">Definicja księgowania może łączyć się z inną definicją księgowania lub być połączona z inną definicją księgowania, ale nie może spełniać obu tych warunków jednocześnie.</span><span class="sxs-lookup"><span data-stu-id="444b6-132">A given posting definition can either link to another posting definition or be linked to from another posting definition, but not both.</span></span> <span data-ttu-id="444b6-133">Definicja księgowania może być połączona z wieloma innymi definicjami księgowania.</span><span class="sxs-lookup"><span data-stu-id="444b6-133">However, a posting definition can link to multiple posting definitions.</span></span>
-   <span data-ttu-id="444b6-134">Można konfigurować łącza tylko między definicjami księgowania znajdującymi się w tym samym module.</span><span class="sxs-lookup"><span data-stu-id="444b6-134">You can set up links only among posting definitions that are in the same module.</span></span>
-   <span data-ttu-id="444b6-135">Definicję księgowania można przypisać do dowolnego typu transakcji, ale typ transakcji musi znajdować się w tym samym module co definicja księgowania.</span><span class="sxs-lookup"><span data-stu-id="444b6-135">You can assign a posting definition to any transaction type, but the transaction type must be in the same module as the posting definition.</span></span> <span data-ttu-id="444b6-136">Użyj strony **Definicje księgowania transakcji**, aby zobaczyć, w jakim modelu jest typ transakcji.</span><span class="sxs-lookup"><span data-stu-id="444b6-136">Use the **Transaction posting definitions** page to see what module a transaction type is in.</span></span>


<span data-ttu-id="444b6-137">Aby uzyskać więcej informacji, zobacz [Przykłady definicji księgowania](example-posting-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="444b6-137">For more information, see [Posting definitions examples](example-posting-definitions.md).</span></span> 



