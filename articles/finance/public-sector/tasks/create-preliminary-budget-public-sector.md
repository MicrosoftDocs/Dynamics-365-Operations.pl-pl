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
ms.search.region: Global
ms.search.industry: Service industries
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 40371809f3855e57db4bc12f5466f7cef5cec600
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5235563"
---
# <a name="create-a-preliminary-budget-for-public-sector"></a><span data-ttu-id="be907-103">Tworzenie wstępnego budżetu dla sektora publicznego</span><span class="sxs-lookup"><span data-stu-id="be907-103">Create a preliminary budget for Public sector</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="be907-104">Można utworzyć wpisy do rejestru budżetu wstępnego dla konkretnego modelu budżetu i wartości wymiarów.</span><span class="sxs-lookup"><span data-stu-id="be907-104">You can create preliminary budget register entries for a specific budget model and dimension values.</span></span> <span data-ttu-id="be907-105">Po zatwierdzeniu rzeczywistego budżetu można utworzyć wpisy do rejestru budżetu pierwotnego.</span><span class="sxs-lookup"><span data-stu-id="be907-105">After the actual budget is approved, you can create original budget register entries.</span></span> <span data-ttu-id="be907-106">Ta procedura została utworzona za pomocą danych firmy demonstracyjnej PSUS z sekcji sektora publicznego.</span><span class="sxs-lookup"><span data-stu-id="be907-106">This procedure was created using the PSUS demo company data in the public sector partition.</span></span>

1. <span data-ttu-id="be907-107">Wybierz kolejno opcje Budżetowanie > Wpisy do rejestru budżetu.</span><span class="sxs-lookup"><span data-stu-id="be907-107">Go to Budgeting > Budget register entries.</span></span>
2. <span data-ttu-id="be907-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="be907-108">Click New.</span></span>
3. <span data-ttu-id="be907-109">W polu Model budżetu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="be907-109">In the Budget model field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="be907-110">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="be907-110">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="be907-111">W polu Kod budżetu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="be907-111">In the Budget code field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="be907-112">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="be907-112">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="be907-113">W polu Kod przyczyny kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="be907-113">In the Reason code field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="be907-114">Na liście kliknij żądany rekord.</span><span class="sxs-lookup"><span data-stu-id="be907-114">In the list, click the desired record.</span></span>
9. <span data-ttu-id="be907-115">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="be907-115">Click Save.</span></span>
10. <span data-ttu-id="be907-116">Kliknij przycisk Dodaj wiersz.</span><span class="sxs-lookup"><span data-stu-id="be907-116">Click Add line.</span></span>
    * <span data-ttu-id="be907-117">Opcjonalnie: Jeśli chcesz zmienić datę z podanej w nagłówku, wprowadź nową datę.</span><span class="sxs-lookup"><span data-stu-id="be907-117">Optional: If you want to change the date from the one in the header, enter a new date.</span></span> <span data-ttu-id="be907-118">Data ta określa okres obrachunkowy, w którym budżet będzie rejestrowany.</span><span class="sxs-lookup"><span data-stu-id="be907-118">This date determines the fiscal period that the budget will be recorded to.</span></span> <span data-ttu-id="be907-119">Aby podczas wyświetlania przewodnika po zadaniach wypełnić inne pola, u góry strony kliknij ikonę odblokowania.</span><span class="sxs-lookup"><span data-stu-id="be907-119">When viewing the task guide, to fill out other fields, click Unlock at the top of the page.</span></span>  
11. <span data-ttu-id="be907-120">W polu Struktura konta kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="be907-120">In the Account structure field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="be907-121">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="be907-121">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="be907-122">W polu Wartości wymiarów podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="be907-122">In the Dimension values field, specify the desired values.</span></span>
14. <span data-ttu-id="be907-123">W polu Kwota wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="be907-123">In the Amount field, enter a number.</span></span>
    * <span data-ttu-id="be907-124">Można również wprowadzić typ kwoty.</span><span class="sxs-lookup"><span data-stu-id="be907-124">You can also enter an amount type.</span></span>  
15. <span data-ttu-id="be907-125">W polu Waluta kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="be907-125">In the Currency field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="be907-126">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="be907-126">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="be907-127">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="be907-127">Click Save.</span></span>
18. <span data-ttu-id="be907-128">Kliknij przycisk Aktualizuj salda budżetu.</span><span class="sxs-lookup"><span data-stu-id="be907-128">Click Update budget balances.</span></span>
19. <span data-ttu-id="be907-129">Kliknij przycisk Aktualizuj.</span><span class="sxs-lookup"><span data-stu-id="be907-129">Click Update.</span></span>
    * <span data-ttu-id="be907-130">Aby wyświetlić wyniki aktualizacji, na niebieskim pasku kliknij przycisk Szczegóły komunikatu.</span><span class="sxs-lookup"><span data-stu-id="be907-130">To see the results of the update, click Message details on the blue bar.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]