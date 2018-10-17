--- 
title: "Tworzenie pierwotnego budżetu i odwracanie wpisów budżetu wstępnego dla sektora publicznego"
description: "Jeśli tworzysz wpis do budżetu pierwotnego przy użyciu modelu i wartości wymiarów zawierających kwoty budżetu wstępnego, kwoty budżetu wstępnego mogą zostać wycofane."
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BudgetTransaction, BudgetAccountStructureLookup, BudgetTransactionMultiPost
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 9d1c34ac2bd94196b7bad599e9aca7ed942ae9c8
ms.contentlocale: pl-pl
ms.lasthandoff: 09/14/2018

---
# <a name="create-an-original-budget-and-then-reverse-preliminary-budget-entries-in-the-public-sector"></a><span data-ttu-id="88089-103">Tworzenie pierwotnego budżetu i odwracanie wpisów budżetu wstępnego dla sektora publicznego</span><span class="sxs-lookup"><span data-stu-id="88089-103">Create an original budget and then reverse preliminary budget entries in the public sector</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="88089-104">Jeśli tworzysz wpis do budżetu pierwotnego przy użyciu modelu i wartości wymiarów zawierających kwoty budżetu wstępnego, kwoty budżetu wstępnego mogą zostać wycofane.</span><span class="sxs-lookup"><span data-stu-id="88089-104">When you create an original budget entry and use the budget model and dimension values that contain preliminary budget amounts, the preliminary budget amounts can be reversed.</span></span> <span data-ttu-id="88089-105">Ta procedura została utworzona za pomocą danych firmy demonstracyjnej PSUS z sekcji sektora publicznego.</span><span class="sxs-lookup"><span data-stu-id="88089-105">This procedure was created using the PSUS demo company data in the public sector partition.</span></span>

1. <span data-ttu-id="88089-106">Wybierz kolejno opcje Budżetowanie > Wpisy do rejestru budżetu.</span><span class="sxs-lookup"><span data-stu-id="88089-106">Go to Budgeting > Budget register entries.</span></span>
2. <span data-ttu-id="88089-107">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="88089-107">Click New.</span></span>
3. <span data-ttu-id="88089-108">W polu Model budżetu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="88089-108">In the Budget model field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="88089-109">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="88089-109">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="88089-110">W polu Kod budżetu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="88089-110">In the Budget code field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="88089-111">Na liście kliknij opcję Budżet pierwotny.</span><span class="sxs-lookup"><span data-stu-id="88089-111">In the list, click Original budget.</span></span>
7. <span data-ttu-id="88089-112">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="88089-112">Click Save.</span></span>
8. <span data-ttu-id="88089-113">Kliknij przycisk Dodaj wiersz.</span><span class="sxs-lookup"><span data-stu-id="88089-113">Click Add line.</span></span>
9. <span data-ttu-id="88089-114">Opcjonalnie: Jeśli chcesz zmienić datę z podanej w nagłówku, wprowadź nową datę.</span><span class="sxs-lookup"><span data-stu-id="88089-114">Optional: If you want to change the date from the one in the header, enter a new date.</span></span> <span data-ttu-id="88089-115">Data ta określa okres obrachunkowy, w którym budżet będzie rejestrowany.</span><span class="sxs-lookup"><span data-stu-id="88089-115">This date determines the fiscal period that the budget will be recorded to.</span></span>
10. <span data-ttu-id="88089-116">W polu Struktura konta kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="88089-116">In the Account structure field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="88089-117">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="88089-117">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="88089-118">W polu Wartości wymiarów podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="88089-118">In the Dimension values field, specify the desired values.</span></span>
13. <span data-ttu-id="88089-119">W polu Kwota wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="88089-119">In the Amount field, enter a number.</span></span>
14. <span data-ttu-id="88089-120">W polu Waluta kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="88089-120">In the Currency field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="88089-121">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="88089-121">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="88089-122">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="88089-122">Click Save.</span></span>
17. <span data-ttu-id="88089-123">Kliknij przycisk Aktualizuj salda budżetu.</span><span class="sxs-lookup"><span data-stu-id="88089-123">Click Update budget balances.</span></span>
    * <span data-ttu-id="88089-124">Opcjonalnie: Można wybrać opcję Odwróć budżetu wstępny.</span><span class="sxs-lookup"><span data-stu-id="88089-124">Optional: You can select the Reverse preliminary budget option.</span></span> <span data-ttu-id="88089-125">Należy zauważyć, że można wystornować wszystkie wpisy budżetu wstępnego lub tylko te wpisy, które mają określony kod budżetu.</span><span class="sxs-lookup"><span data-stu-id="88089-125">Note that you can reverse all preliminary budget entries, or only the preliminary budget entries that have the budget code that you specify.</span></span>  
    * <span data-ttu-id="88089-126">Aby skonfigurować opcjonalne ustawienia, u góry strony kliknij ikonę odblokowania.</span><span class="sxs-lookup"><span data-stu-id="88089-126">To make optional selections, click the Unlock icon at the top of the page.</span></span>  
18. <span data-ttu-id="88089-127">Kliknij przycisk Aktualizuj.</span><span class="sxs-lookup"><span data-stu-id="88089-127">Click Update.</span></span>


