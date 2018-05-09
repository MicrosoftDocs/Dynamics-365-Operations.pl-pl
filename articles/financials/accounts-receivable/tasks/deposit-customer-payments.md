--- 
title: "Deponowanie płatności odbiorców"
description: "Wpłacanie płatności od odbiorców."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 8e2db9b3d925b75d8f59aa3168537078592cd2f7
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---
# <a name="deposit-customer-payments"></a><span data-ttu-id="28f92-103">Deponowanie płatności odbiorców</span><span class="sxs-lookup"><span data-stu-id="28f92-103">Deposit customer payments</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="28f92-104">Wpłacanie płatności od odbiorców.</span><span class="sxs-lookup"><span data-stu-id="28f92-104">Deposit customer payments.</span></span> <span data-ttu-id="28f92-105">W zadaniu wykorzystano firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="28f92-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="28f92-106">Wybierz kolejno opcje Rozrachunki z odbiorcami > Płatności > Arkusz płatności.</span><span class="sxs-lookup"><span data-stu-id="28f92-106">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="28f92-107">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="28f92-107">Click New.</span></span>
3. <span data-ttu-id="28f92-108">W polu Nazwa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="28f92-108">In the Name field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="28f92-109">Wybierz arkusz płatności.</span><span class="sxs-lookup"><span data-stu-id="28f92-109">Select the payment journal.</span></span> 
5. <span data-ttu-id="28f92-110">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="28f92-110">Click Lines.</span></span>
6. <span data-ttu-id="28f92-111">W polu konto zaznacz odbiorcę, dla którego rejestrujesz płatność.</span><span class="sxs-lookup"><span data-stu-id="28f92-111">In the Account field, select the Customer for whom you are recording the payment.</span></span>
7. <span data-ttu-id="28f92-112">W polu Kredyt wprowadź kwotę płatności.</span><span class="sxs-lookup"><span data-stu-id="28f92-112">In the Credit field, enter the amount of the payment.</span></span>
    * <span data-ttu-id="28f92-113">Można wybrać opcję niewypełniania pola, a obliczania jego wartości przez system po zaznaczeniu opłaconych faktur.</span><span class="sxs-lookup"><span data-stu-id="28f92-113">You can choose to leave the amount blank, and have the system calculate it by selecting the invoices which were paid.</span></span>  
8. <span data-ttu-id="28f92-114">W polu Odwołanie do płatności wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="28f92-114">In the Payment reference field, type a value.</span></span>
    * <span data-ttu-id="28f92-115">Odwołaniem do płatności może być numeru czeku z wprowadzanej płatności.</span><span class="sxs-lookup"><span data-stu-id="28f92-115">The payment reference could be the check number for the payment you are entering.</span></span> <span data-ttu-id="28f92-116">Odwołanie do płatności jest wymagane w celu uwzględnienia płatności na dokumencie wpłaty.</span><span class="sxs-lookup"><span data-stu-id="28f92-116">The payment reference is required in order to include the payment on a deposit slip.</span></span>  
9. <span data-ttu-id="28f92-117">Zaznacz opcję Użyj dokumentu wpłaty.</span><span class="sxs-lookup"><span data-stu-id="28f92-117">Mark the box Use a deposit slip.</span></span>
    * <span data-ttu-id="28f92-118">Jeśli płatność ma być uwzględniona we wpłacie, zmień to ustawienie na Tak.</span><span class="sxs-lookup"><span data-stu-id="28f92-118">If the payment should be included in the deposit, change this setting to Yes.</span></span>  
10. <span data-ttu-id="28f92-119">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="28f92-119">Click New.</span></span>
11. <span data-ttu-id="28f92-120">W polu Konto wybierz odbiorcę dla następnej płatności.</span><span class="sxs-lookup"><span data-stu-id="28f92-120">In the Account field, select the Customer for the next payment.</span></span>
12. <span data-ttu-id="28f92-121">W polu Kredyt wprowadź kwotę płatności.</span><span class="sxs-lookup"><span data-stu-id="28f92-121">In the Credit field, enter the payment amount.</span></span>
13. <span data-ttu-id="28f92-122">W polu Odwołanie do płatności wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="28f92-122">In the Payment reference field, type a value.</span></span>
14. <span data-ttu-id="28f92-123">Zaznacz opcję Użyj dokumentu wpłaty.</span><span class="sxs-lookup"><span data-stu-id="28f92-123">Mark the box Use a deposit slip.</span></span>
15. <span data-ttu-id="28f92-124">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="28f92-124">Click Post.</span></span>
    * <span data-ttu-id="28f92-125">Aby można było wygenerować dokument wpłaty, płatności być zaksięgowane.</span><span class="sxs-lookup"><span data-stu-id="28f92-125">Payments must be posted before the deposit slip can be generated.</span></span> <span data-ttu-id="28f92-126">Ma to na celu zagwarantowanie, że płatności nie zmienią się po wygenerowaniu dokumentu wpłaty.</span><span class="sxs-lookup"><span data-stu-id="28f92-126">This is to ensure that the payments don't change after the deposit slip is generated.</span></span>  
16. <span data-ttu-id="28f92-127">Kliknij przycisk Funkcje.</span><span class="sxs-lookup"><span data-stu-id="28f92-127">Click Functions.</span></span>
17. <span data-ttu-id="28f92-128">Kliknij opcję Dokument wpłaty.</span><span class="sxs-lookup"><span data-stu-id="28f92-128">Click Deposit slip.</span></span>
18. <span data-ttu-id="28f92-129">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="28f92-129">Click OK.</span></span>
    * <span data-ttu-id="28f92-130">Pierwsza strona jest używana do utworzenia dokumentu wpłaty.</span><span class="sxs-lookup"><span data-stu-id="28f92-130">The first page is used to create the deposit slip.</span></span>  
19. <span data-ttu-id="28f92-131">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="28f92-131">Click OK.</span></span>
    * <span data-ttu-id="28f92-132">Drugim krokiem jest wydrukowanie dokumentu wpłaty, ale ten krok nie jest wymagany.</span><span class="sxs-lookup"><span data-stu-id="28f92-132">The second step is to print the deposit slip, but this step is not required.</span></span>  


