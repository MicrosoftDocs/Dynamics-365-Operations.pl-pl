--- 
title: "Wprowadzanie najważniejszych danych faktury do modułu rozrachunków z dostawcami za pomocą arkusza zatwierdzania"
description: "W tym przewodniku po zadaniach pokazano sposób używania rejestru faktur do tworzenia faktur, a następnie używania arkusza zatwierdzania do aktualizowania kont wydatków."
author: abruer
manager: AnnBe
ms.date: 11/15/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 7a921d7987002310d6a7d7fc78457aaa0cf1d990
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---
# <a name="key-invoice-data-into-accounts-payable-using-an-approval-journal"></a><span data-ttu-id="e1b10-103">Wprowadzanie najważniejszych danych faktury do modułu rozrachunków z dostawcami za pomocą arkusza zatwierdzania</span><span class="sxs-lookup"><span data-stu-id="e1b10-103">Key invoice data into accounts payable using an approval journal</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e1b10-104">W tym przewodniku po zadaniach pokazano sposób używania rejestru faktur do tworzenia faktur, a następnie używania arkusza zatwierdzania do aktualizowania kont wydatków.</span><span class="sxs-lookup"><span data-stu-id="e1b10-104">This task guide will show you how to use the invoice register to create invoices and then use the approval journal to update the expense accounts.</span></span>


## <a name="create-and-post-and-invoice"></a><span data-ttu-id="e1b10-105">Tworzenie i księgowanie faktury</span><span class="sxs-lookup"><span data-stu-id="e1b10-105">Create and post and invoice</span></span>
1. <span data-ttu-id="e1b10-106">Wybierz kolejno opcje Rozrachunki z dostawcami > Faktury > Rejestr faktur.</span><span class="sxs-lookup"><span data-stu-id="e1b10-106">Go to Accounts payable > Invoices > Invoice register.</span></span>
2. <span data-ttu-id="e1b10-107">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e1b10-107">Click New.</span></span>
3. <span data-ttu-id="e1b10-108">Wybierz nazwę rejestru faktur, którego chcesz używać.</span><span class="sxs-lookup"><span data-stu-id="e1b10-108">Select the name of the invoice register that you want to use.</span></span>
4. <span data-ttu-id="e1b10-109">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="e1b10-109">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="e1b10-110">Kliknij przycisk Wiersze, aby otworzyć rejestr i wprowadzić wiersze wydatków.</span><span class="sxs-lookup"><span data-stu-id="e1b10-110">Click on Lines to open the register and enter expense lines.</span></span>
6. <span data-ttu-id="e1b10-111">Wybierz dostawcę.</span><span class="sxs-lookup"><span data-stu-id="e1b10-111">Select a vendor.</span></span> <span data-ttu-id="e1b10-112">Na przykład wprowadź lub wybierz dostawcę US-104.</span><span class="sxs-lookup"><span data-stu-id="e1b10-112">For example, enter or select US-104</span></span>
7. <span data-ttu-id="e1b10-113">W polu Faktura wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e1b10-113">In the Invoice field, type a value.</span></span>
8. <span data-ttu-id="e1b10-114">W polu Opis wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e1b10-114">In the Description field, type a value.</span></span>
9. <span data-ttu-id="e1b10-115">W polu Kredyt wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="e1b10-115">In the Credit field, enter a number.</span></span>
10. <span data-ttu-id="e1b10-116">W polu Zatwierdzone przez kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="e1b10-116">In the Approved by field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="e1b10-117">Zaznacz osobę zatwierdzającą i kliknij przycisk Wybierz, aby ją wybrać.</span><span class="sxs-lookup"><span data-stu-id="e1b10-117">Highlight an approver and click Select to select that approver.</span></span>
12. <span data-ttu-id="e1b10-118">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="e1b10-118">Click Post.</span></span>
13. <span data-ttu-id="e1b10-119">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e1b10-119">Close the page.</span></span>
14. <span data-ttu-id="e1b10-120">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e1b10-120">Close the page.</span></span>

## <a name="approve-an-invoice"></a><span data-ttu-id="e1b10-121">Zatwierdzanie faktury</span><span class="sxs-lookup"><span data-stu-id="e1b10-121">Approve an invoice</span></span>
1. <span data-ttu-id="e1b10-122">Wybierz kolejno opcje Rozrachunki z dostawcami > Faktury > Zatwierdzenie faktury.</span><span class="sxs-lookup"><span data-stu-id="e1b10-122">Go to Accounts payable > Invoices > Invoice approval.</span></span>
2. <span data-ttu-id="e1b10-123">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e1b10-123">Click New.</span></span>
3. <span data-ttu-id="e1b10-124">Wybierz nazwę arkusza zatwierdzania faktur, którego chcesz używać.</span><span class="sxs-lookup"><span data-stu-id="e1b10-124">Select the name of the invoice approval journal that you want to use.</span></span>
4. <span data-ttu-id="e1b10-125">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="e1b10-125">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="e1b10-126">Kliknij przycisk Wiersze, a zostanie wyświetlona strona, gdzie będzie można wybrać faktury do zatwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="e1b10-126">Click lines to display a page where you will be able to select the invoices that you want to approve.</span></span>
6. <span data-ttu-id="e1b10-127">Kliknij przycisk Znajdź załączniki, aby wyświetlić wszystkie faktury gotowe do zatwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="e1b10-127">Select Find Vouchers to display all of the invoices that are ready for approval.</span></span>
7. <span data-ttu-id="e1b10-128">Oznacz utworzoną przez siebie fakturę.</span><span class="sxs-lookup"><span data-stu-id="e1b10-128">Mark the invoice that you created.</span></span>
8. <span data-ttu-id="e1b10-129">Kliknij opcję Wybierz.</span><span class="sxs-lookup"><span data-stu-id="e1b10-129">Click Select.</span></span>
    * <span data-ttu-id="e1b10-130">Załączniki wybrane powyżej zostaną po zaznaczeniu przeniesione do tej listy.</span><span class="sxs-lookup"><span data-stu-id="e1b10-130">The vouchers that you selected above are moved to this list after you select them.</span></span>  
9. <span data-ttu-id="e1b10-131">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="e1b10-131">Click OK.</span></span>
10. <span data-ttu-id="e1b10-132">Kliknij pole Numer konta, aby dodać konto wydatków do faktury.</span><span class="sxs-lookup"><span data-stu-id="e1b10-132">Click on the account number field to add an expense account to the invoice.</span></span>
11. <span data-ttu-id="e1b10-133">Wprowadź numer konta i opuść to pole.</span><span class="sxs-lookup"><span data-stu-id="e1b10-133">Enter an account number and tab off of the field.</span></span> <span data-ttu-id="e1b10-134">Na przykład wpisz 600120.</span><span class="sxs-lookup"><span data-stu-id="e1b10-134">For example, enter 600120.</span></span>
12. <span data-ttu-id="e1b10-135">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="e1b10-135">Click Post.</span></span>
13. <span data-ttu-id="e1b10-136">Kliknij opcję Załącznik, aby wyświetlić zapisy, które zostały zaksięgowane.</span><span class="sxs-lookup"><span data-stu-id="e1b10-136">Click Voucher to view the entries that were posted.</span></span>
    * <span data-ttu-id="e1b10-137">Konto faktur oczekujących na zatwierdzenie zostanie wycofane i zastąpione kontem wydatków rzeczywistych.</span><span class="sxs-lookup"><span data-stu-id="e1b10-137">The Invoice Pending Approval account is reversed and replaced with the actual expense account.</span></span>  


