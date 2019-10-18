---
title: Tworzenie wstępnego budżetu dla sektora publicznego
description: Można utworzyć wpisy do rejestru budżetu wstępnego dla konkretnego modelu budżetu i wartości wymiarów.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetTransaction, BudgetAccountStructureLookup, BudgetTransactionMultiPost
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 800b7009f023bd2a0d8437b81d82c0e9de770841
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174381"
---
# <a name="create-a-preliminary-budget-for-public-sector"></a><span data-ttu-id="5aee6-103">Tworzenie wstępnego budżetu dla sektora publicznego</span><span class="sxs-lookup"><span data-stu-id="5aee6-103">Create a preliminary budget for Public sector</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5aee6-104">Można utworzyć wpisy do rejestru budżetu wstępnego dla konkretnego modelu budżetu i wartości wymiarów.</span><span class="sxs-lookup"><span data-stu-id="5aee6-104">You can create preliminary budget register entries for a specific budget model and dimension values.</span></span> <span data-ttu-id="5aee6-105">Po zatwierdzeniu rzeczywistego budżetu można utworzyć wpisy do rejestru budżetu pierwotnego.</span><span class="sxs-lookup"><span data-stu-id="5aee6-105">After the actual budget is approved, you can create original budget register entries.</span></span> <span data-ttu-id="5aee6-106">Ta procedura została utworzona za pomocą danych firmy demonstracyjnej PSUS z sekcji sektora publicznego.</span><span class="sxs-lookup"><span data-stu-id="5aee6-106">This procedure was created using the PSUS demo company data in the public sector partition.</span></span>

1. <span data-ttu-id="5aee6-107">Wybierz kolejno opcje Budżetowanie > Wpisy do rejestru budżetu.</span><span class="sxs-lookup"><span data-stu-id="5aee6-107">Go to Budgeting > Budget register entries.</span></span>
2. <span data-ttu-id="5aee6-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="5aee6-108">Click New.</span></span>
3. <span data-ttu-id="5aee6-109">W polu Model budżetu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="5aee6-109">In the Budget model field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="5aee6-110">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="5aee6-110">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="5aee6-111">W polu Kod budżetu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="5aee6-111">In the Budget code field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="5aee6-112">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="5aee6-112">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="5aee6-113">W polu Kod przyczyny kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="5aee6-113">In the Reason code field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="5aee6-114">Na liście kliknij żądany rekord.</span><span class="sxs-lookup"><span data-stu-id="5aee6-114">In the list, click the desired record.</span></span>
9. <span data-ttu-id="5aee6-115">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="5aee6-115">Click Save.</span></span>
10. <span data-ttu-id="5aee6-116">Kliknij przycisk Dodaj wiersz.</span><span class="sxs-lookup"><span data-stu-id="5aee6-116">Click Add line.</span></span>
    * <span data-ttu-id="5aee6-117">Opcjonalnie: Jeśli chcesz zmienić datę z podanej w nagłówku, wprowadź nową datę.</span><span class="sxs-lookup"><span data-stu-id="5aee6-117">Optional: If you want to change the date from the one in the header, enter a new date.</span></span> <span data-ttu-id="5aee6-118">Data ta określa okres obrachunkowy, w którym budżet będzie rejestrowany.</span><span class="sxs-lookup"><span data-stu-id="5aee6-118">This date determines the fiscal period that the budget will be recorded to.</span></span> <span data-ttu-id="5aee6-119">Aby podczas wyświetlania przewodnika po zadaniach wypełnić inne pola, u góry strony kliknij ikonę odblokowania.</span><span class="sxs-lookup"><span data-stu-id="5aee6-119">When viewing the task guide, to fill out other fields, click Unlock at the top of the page.</span></span>  
11. <span data-ttu-id="5aee6-120">W polu Struktura konta kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="5aee6-120">In the Account structure field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="5aee6-121">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="5aee6-121">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="5aee6-122">W polu Wartości wymiarów podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="5aee6-122">In the Dimension values field, specify the desired values.</span></span>
14. <span data-ttu-id="5aee6-123">W polu Kwota wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="5aee6-123">In the Amount field, enter a number.</span></span>
    * <span data-ttu-id="5aee6-124">Można również wprowadzić typ kwoty.</span><span class="sxs-lookup"><span data-stu-id="5aee6-124">You can also enter an amount type.</span></span>  
15. <span data-ttu-id="5aee6-125">W polu Waluta kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="5aee6-125">In the Currency field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="5aee6-126">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="5aee6-126">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="5aee6-127">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="5aee6-127">Click Save.</span></span>
18. <span data-ttu-id="5aee6-128">Kliknij przycisk Aktualizuj salda budżetu.</span><span class="sxs-lookup"><span data-stu-id="5aee6-128">Click Update budget balances.</span></span>
19. <span data-ttu-id="5aee6-129">Kliknij przycisk Aktualizuj.</span><span class="sxs-lookup"><span data-stu-id="5aee6-129">Click Update.</span></span>
    * <span data-ttu-id="5aee6-130">Aby wyświetlić wyniki aktualizacji, na niebieskim pasku kliknij przycisk Szczegóły komunikatu.</span><span class="sxs-lookup"><span data-stu-id="5aee6-130">To see the results of the update, click Message details on the blue bar.</span></span>  

