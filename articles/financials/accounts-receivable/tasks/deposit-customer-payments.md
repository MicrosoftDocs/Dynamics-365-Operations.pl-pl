---
title: Deponowanie płatności odbiorców
description: Wpłacanie płatności od odbiorców.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransCustPaym, CustTableLookup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f58cebce20e8516dc918e0bad1e020ffd7f791ee
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "313389"
---
# <a name="deposit-customer-payments"></a><span data-ttu-id="2e91e-103">Deponowanie płatności odbiorców</span><span class="sxs-lookup"><span data-stu-id="2e91e-103">Deposit customer payments</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2e91e-104">Wpłacanie płatności od odbiorców.</span><span class="sxs-lookup"><span data-stu-id="2e91e-104">Deposit customer payments.</span></span> <span data-ttu-id="2e91e-105">W zadaniu wykorzystano firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="2e91e-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="2e91e-106">Wybierz kolejno opcje Rozrachunki z odbiorcami > Płatności > Arkusz płatności.</span><span class="sxs-lookup"><span data-stu-id="2e91e-106">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="2e91e-107">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="2e91e-107">Click New.</span></span>
3. <span data-ttu-id="2e91e-108">W polu Nazwa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="2e91e-108">In the Name field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="2e91e-109">Wybierz arkusz płatności.</span><span class="sxs-lookup"><span data-stu-id="2e91e-109">Select the payment journal.</span></span> 
5. <span data-ttu-id="2e91e-110">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="2e91e-110">Click Lines.</span></span>
6. <span data-ttu-id="2e91e-111">W polu konto zaznacz odbiorcę, dla którego rejestrujesz płatność.</span><span class="sxs-lookup"><span data-stu-id="2e91e-111">In the Account field, select the Customer for whom you are recording the payment.</span></span>
7. <span data-ttu-id="2e91e-112">W polu Kredyt wprowadź kwotę płatności.</span><span class="sxs-lookup"><span data-stu-id="2e91e-112">In the Credit field, enter the amount of the payment.</span></span>
    * <span data-ttu-id="2e91e-113">Można wybrać opcję niewypełniania pola, a obliczania jego wartości przez system po zaznaczeniu opłaconych faktur.</span><span class="sxs-lookup"><span data-stu-id="2e91e-113">You can choose to leave the amount blank, and have the system calculate it by selecting the invoices which were paid.</span></span>  
8. <span data-ttu-id="2e91e-114">W polu Odwołanie do płatności wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="2e91e-114">In the Payment reference field, type a value.</span></span>
    * <span data-ttu-id="2e91e-115">Odwołaniem do płatności może być numeru czeku z wprowadzanej płatności.</span><span class="sxs-lookup"><span data-stu-id="2e91e-115">The payment reference could be the check number for the payment you are entering.</span></span> <span data-ttu-id="2e91e-116">Odwołanie do płatności jest wymagane w celu uwzględnienia płatności na dokumencie wpłaty.</span><span class="sxs-lookup"><span data-stu-id="2e91e-116">The payment reference is required in order to include the payment on a deposit slip.</span></span>  
9. <span data-ttu-id="2e91e-117">Zaznacz opcję Użyj dokumentu wpłaty.</span><span class="sxs-lookup"><span data-stu-id="2e91e-117">Mark the box Use a deposit slip.</span></span>
    * <span data-ttu-id="2e91e-118">Jeśli płatność ma być uwzględniona we wpłacie, zmień to ustawienie na Tak.</span><span class="sxs-lookup"><span data-stu-id="2e91e-118">If the payment should be included in the deposit, change this setting to Yes.</span></span>  
10. <span data-ttu-id="2e91e-119">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="2e91e-119">Click New.</span></span>
11. <span data-ttu-id="2e91e-120">W polu Konto wybierz odbiorcę dla następnej płatności.</span><span class="sxs-lookup"><span data-stu-id="2e91e-120">In the Account field, select the Customer for the next payment.</span></span>
12. <span data-ttu-id="2e91e-121">W polu Kredyt wprowadź kwotę płatności.</span><span class="sxs-lookup"><span data-stu-id="2e91e-121">In the Credit field, enter the payment amount.</span></span>
13. <span data-ttu-id="2e91e-122">W polu Odwołanie do płatności wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="2e91e-122">In the Payment reference field, type a value.</span></span>
14. <span data-ttu-id="2e91e-123">Zaznacz opcję Użyj dokumentu wpłaty.</span><span class="sxs-lookup"><span data-stu-id="2e91e-123">Mark the box Use a deposit slip.</span></span>
15. <span data-ttu-id="2e91e-124">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="2e91e-124">Click Post.</span></span>
    * <span data-ttu-id="2e91e-125">Aby można było wygenerować dokument wpłaty, płatności być zaksięgowane.</span><span class="sxs-lookup"><span data-stu-id="2e91e-125">Payments must be posted before the deposit slip can be generated.</span></span> <span data-ttu-id="2e91e-126">Ma to na celu zagwarantowanie, że płatności nie zmienią się po wygenerowaniu dokumentu wpłaty.</span><span class="sxs-lookup"><span data-stu-id="2e91e-126">This is to ensure that the payments don't change after the deposit slip is generated.</span></span>  
16. <span data-ttu-id="2e91e-127">Kliknij przycisk Funkcje.</span><span class="sxs-lookup"><span data-stu-id="2e91e-127">Click Functions.</span></span>
17. <span data-ttu-id="2e91e-128">Kliknij opcję Dokument wpłaty.</span><span class="sxs-lookup"><span data-stu-id="2e91e-128">Click Deposit slip.</span></span>
18. <span data-ttu-id="2e91e-129">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="2e91e-129">Click OK.</span></span>
    * <span data-ttu-id="2e91e-130">Pierwsza strona jest używana do utworzenia dokumentu wpłaty.</span><span class="sxs-lookup"><span data-stu-id="2e91e-130">The first page is used to create the deposit slip.</span></span>  
19. <span data-ttu-id="2e91e-131">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="2e91e-131">Click OK.</span></span>
    * <span data-ttu-id="2e91e-132">Drugim krokiem jest wydrukowanie dokumentu wpłaty, ale ten krok nie jest wymagany.</span><span class="sxs-lookup"><span data-stu-id="2e91e-132">The second step is to print the deposit slip, but this step is not required.</span></span>  

