---
title: Deponowanie płatności odbiorców
description: Wpłacanie płatności od odbiorców.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransCustPaym, CustTableLookup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9221101581a6a130889b7c941ca228070a000c56
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5003163"
---
# <a name="deposit-customer-payments"></a><span data-ttu-id="3567b-103">Deponowanie płatności odbiorców</span><span class="sxs-lookup"><span data-stu-id="3567b-103">Deposit customer payments</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3567b-104">Wpłacanie płatności od odbiorców.</span><span class="sxs-lookup"><span data-stu-id="3567b-104">Deposit customer payments.</span></span> <span data-ttu-id="3567b-105">W zadaniu wykorzystano firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="3567b-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="3567b-106">Wybierz kolejno **Okienko nawigacji > Moduły > Rozrachunki z dostawcami > Płatności > Arkusz płatności**.</span><span class="sxs-lookup"><span data-stu-id="3567b-106">Go to **Navigation pane > Modules > Accounts receivable > Payments > Payment journal**.</span></span>
2. <span data-ttu-id="3567b-107">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="3567b-107">Select **New**.</span></span>
3. <span data-ttu-id="3567b-108">W polu **Nazwa** wybierz opcję **CustPay** z menu rozwijanego.</span><span class="sxs-lookup"><span data-stu-id="3567b-108">In the **Name** field, select **CustPay** in the drop-down menu.</span></span>
4. <span data-ttu-id="3567b-109">Wybierz **Linie**.</span><span class="sxs-lookup"><span data-stu-id="3567b-109">Select **Lines**.</span></span>
5. <span data-ttu-id="3567b-110">W polu **Konto** zaznacz odbiorcę, dla którego rejestrujesz płatność.</span><span class="sxs-lookup"><span data-stu-id="3567b-110">In the **Account** field, select the customer for whom you are recording the payment.</span></span>
6. <span data-ttu-id="3567b-111">W polu **Kredyt** wprowadź kwotę płatności.</span><span class="sxs-lookup"><span data-stu-id="3567b-111">In the **Credit** field, enter the amount of the payment.</span></span> <span data-ttu-id="3567b-112">Można wybrać opcję niewypełniania pola, a obliczania jego wartości przez system po zaznaczeniu opłaconych faktur.</span><span class="sxs-lookup"><span data-stu-id="3567b-112">You can choose to leave the amount blank, and have the system calculate it by selecting the invoices which were paid.</span></span>  
7. <span data-ttu-id="3567b-113">W polu **Odwołanie do płatności** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3567b-113">In the **Payment reference** field, type a value.</span></span> <span data-ttu-id="3567b-114">Odwołaniem do płatności może być numeru czeku z wprowadzanej płatności.</span><span class="sxs-lookup"><span data-stu-id="3567b-114">The payment reference could be the check number for the payment you are entering.</span></span> <span data-ttu-id="3567b-115">Odwołanie do płatności jest wymagane w celu uwzględnienia płatności na dokumencie wpłaty.</span><span class="sxs-lookup"><span data-stu-id="3567b-115">The payment reference is required in order to include the payment on a deposit slip.</span></span>  
8. <span data-ttu-id="3567b-116">Zaznacz opcję Użyj dokumentu wpłaty.</span><span class="sxs-lookup"><span data-stu-id="3567b-116">Mark the box Use a deposit slip.</span></span> <span data-ttu-id="3567b-117">Jeśli płatność ma być uwzględniona we wpłacie, zmień to ustawienie na Tak.</span><span class="sxs-lookup"><span data-stu-id="3567b-117">If the payment should be included in the deposit, change this setting to Yes.</span></span>  
9. <span data-ttu-id="3567b-118">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="3567b-118">Select **New**.</span></span>
10. <span data-ttu-id="3567b-119">W polu **Konto** wybierz odbiorcę dla następnej płatności.</span><span class="sxs-lookup"><span data-stu-id="3567b-119">In the **Account** field, select the customer for the next payment.</span></span>
11. <span data-ttu-id="3567b-120">W polu **Kredyt** wprowadź kwotę płatności.</span><span class="sxs-lookup"><span data-stu-id="3567b-120">In the **Credit** field, enter the payment amount.</span></span>
12. <span data-ttu-id="3567b-121">W polu **Odwołanie do płatności** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3567b-121">In the **Payment reference** field, type a value.</span></span>
13. <span data-ttu-id="3567b-122">Zaznacz opcję **Użyj dokumentu wpłaty**.</span><span class="sxs-lookup"><span data-stu-id="3567b-122">Mark the box **Use a deposit slip**.</span></span>
14. <span data-ttu-id="3567b-123">Wybierz opcję **Zaksięguj**.</span><span class="sxs-lookup"><span data-stu-id="3567b-123">Select **Post**.</span></span> <span data-ttu-id="3567b-124">Aby można było wygenerować dokument wpłaty, płatności być zaksięgowane.</span><span class="sxs-lookup"><span data-stu-id="3567b-124">Payments must be posted before the deposit slip can be generated.</span></span> <span data-ttu-id="3567b-125">Ma to na celu zagwarantowanie, że płatności nie zmienią się po wygenerowaniu dokumentu wpłaty.</span><span class="sxs-lookup"><span data-stu-id="3567b-125">This is to ensure that the payments don't change after the deposit slip is generated.</span></span>  
15. <span data-ttu-id="3567b-126">Wybierz **Funkcje**.</span><span class="sxs-lookup"><span data-stu-id="3567b-126">Select **Functions**.</span></span>
16. <span data-ttu-id="3567b-127">Wybierz **Dokument wpłaty**.</span><span class="sxs-lookup"><span data-stu-id="3567b-127">Select **Deposit slip**.</span></span>
17. <span data-ttu-id="3567b-128">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="3567b-128">Select **OK**.</span></span> <span data-ttu-id="3567b-129">Pierwsza strona jest używana do utworzenia dokumentu wpłaty.</span><span class="sxs-lookup"><span data-stu-id="3567b-129">The first page is used to create the deposit slip.</span></span>  
18. <span data-ttu-id="3567b-130">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="3567b-130">Select **OK**.</span></span> <span data-ttu-id="3567b-131">Drugim krokiem jest wydrukowanie dokumentu wpłaty, ale ten krok nie jest wymagany.</span><span class="sxs-lookup"><span data-stu-id="3567b-131">The second step is to print the deposit slip, but this step is not required.</span></span>  

