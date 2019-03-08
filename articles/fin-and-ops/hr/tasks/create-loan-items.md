---
title: Tworzenie przedmiotów pożyczek
description: Przedmioty pożyczek są rekordami, które pomagają śledzić fizyczne przedmioty, takie jak telefony lub komputery, które firma pożycza pracownikom.
author: kherr75
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmLoanType, DefaultDashboard, HcmLoanItem, HcmWorkerLookUp
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e17005bda302c58f5a6560fe9c4eda04e918c92f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "341840"
---
# <a name="create-loan-items"></a><span data-ttu-id="45f2b-103">Tworzenie przedmiotów pożyczek</span><span class="sxs-lookup"><span data-stu-id="45f2b-103">Create loan items</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="45f2b-104">Przedmioty pożyczek są rekordami, które pomagają śledzić fizyczne przedmioty, takie jak telefony lub komputery, które firma pożycza pracownikom.</span><span class="sxs-lookup"><span data-stu-id="45f2b-104">Loan items are records that help you track physical items, such as phones or computers, that your company lends to workers.</span></span> <span data-ttu-id="45f2b-105">Każdy przedmiot fizyczny musi mieć odpowiadający mu przedmiot pożyczki.</span><span class="sxs-lookup"><span data-stu-id="45f2b-105">Each physical item must have a corresponding loan item.</span></span> <span data-ttu-id="45f2b-106">Każdy rekord przedmiotu pożyczki powinien opisywać wypożyczany przedmiot, osobę odpowiedzialną za wypożyczenie oraz możliwą liczbę dni wypożyczenia przedmiotu.</span><span class="sxs-lookup"><span data-stu-id="45f2b-106">Each loan item record should describe what is being loaned, who is responsible for the loan, and the number of days the item can be on loan.</span></span> <span data-ttu-id="45f2b-107">Można utworzyć wiele przedmiotów pożyczki, takich jak klucze, karty dostępu lub mundury, w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="45f2b-107">You can create multiple loan items, such as keys, access cards, or uniforms, at the same time.</span></span> <span data-ttu-id="45f2b-108">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="45f2b-108">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-loan-types"></a><span data-ttu-id="45f2b-109">Tworzenie typów pożyczek</span><span class="sxs-lookup"><span data-stu-id="45f2b-109">Create Loan types</span></span>
1. <span data-ttu-id="45f2b-110">Wybierz kolejno opcje Zasoby ludzkie > Pracownicy > Przedmioty pożyczek > Typy pożyczek.</span><span class="sxs-lookup"><span data-stu-id="45f2b-110">Go to Human resources > Workers > Loan items > Loan types.</span></span>
2. <span data-ttu-id="45f2b-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="45f2b-111">Click New.</span></span>
3. <span data-ttu-id="45f2b-112">W polu Typ pożyczki wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="45f2b-112">In the Loan type field, type a value.</span></span>
4. <span data-ttu-id="45f2b-113">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="45f2b-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="45f2b-114">Wprowadź liczbę dni, po upływie których przedmioty przypisane do tego typu pożyczki mogą stanowić zaległość.</span><span class="sxs-lookup"><span data-stu-id="45f2b-114">Enter the number of days that items assigned to this loan type can be overdue.</span></span> 
6. <span data-ttu-id="45f2b-115">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="45f2b-115">Click Save.</span></span>
7. <span data-ttu-id="45f2b-116">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="45f2b-116">Close the page.</span></span>
8. <span data-ttu-id="45f2b-117">Odśwież stronę.</span><span class="sxs-lookup"><span data-stu-id="45f2b-117">Refresh the page.</span></span>

## <a name="create-loan-items"></a><span data-ttu-id="45f2b-118">Tworzenie przedmiotów pożyczek</span><span class="sxs-lookup"><span data-stu-id="45f2b-118">Create Loan items</span></span>
1. <span data-ttu-id="45f2b-119">Wybierz kolejno opcje Zasoby ludzkie > Pracownicy > Przedmioty pożyczek > Przedmioty pożyczek.</span><span class="sxs-lookup"><span data-stu-id="45f2b-119">Go to Human resources > Workers > Loan items > Loan items.</span></span>
2. <span data-ttu-id="45f2b-120">Kliknij opcję Tworzenie przedmiotów pożyczek.</span><span class="sxs-lookup"><span data-stu-id="45f2b-120">Click Create loan items.</span></span>
3. <span data-ttu-id="45f2b-121">W polu Ilość wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="45f2b-121">In the Qty. field, enter a number.</span></span>
4. <span data-ttu-id="45f2b-122">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="45f2b-122">In the Description field, type a value.</span></span>
5. <span data-ttu-id="45f2b-123">W polu Typ pożyczki kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="45f2b-123">In the Loan type field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="45f2b-124">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="45f2b-124">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="45f2b-125">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="45f2b-125">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="45f2b-126">Wprowadź liczbę dni, przez jaką przedmiot może być wypożyczony.</span><span class="sxs-lookup"><span data-stu-id="45f2b-126">Enter the number of days the item can be on loan.</span></span>
    * <span data-ttu-id="45f2b-127">Domyślna wartość pola Planowany zwrot na stronie Sprzęt wypożyczony jest obliczana przez dodanie tej liczby do daty bieżącej.</span><span class="sxs-lookup"><span data-stu-id="45f2b-127">The default value for the Planned return field on the Loaned equipment page is calculated as the current date plus this number.</span></span>  
9. <span data-ttu-id="45f2b-128">W polu Osoba odpowiedzialna kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="45f2b-128">In the Person in charge field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="45f2b-129">Kliknij opcję Wybierz.</span><span class="sxs-lookup"><span data-stu-id="45f2b-129">Click Select.</span></span>
11. <span data-ttu-id="45f2b-130">W polu Wartość początkowa wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="45f2b-130">In the Starting value field, enter a number.</span></span>
12. <span data-ttu-id="45f2b-131">W polu Interwał wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="45f2b-131">In the Interval field, enter a number.</span></span>
13. <span data-ttu-id="45f2b-132">W polu Format wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="45f2b-132">In the Format field, type a value.</span></span>
    * <span data-ttu-id="45f2b-133">Na przykład jeśli numerem początkowym przedmiotu pożyczki jest 10, wprowadź dwa symbole liczb w polu Format.</span><span class="sxs-lookup"><span data-stu-id="45f2b-133">For example, if the starting number for a loan item is 10, enter two number symbols symbols in the Format field.</span></span>  
14. <span data-ttu-id="45f2b-134">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="45f2b-134">Click OK.</span></span>
15. <span data-ttu-id="45f2b-135">Odśwież stronę.</span><span class="sxs-lookup"><span data-stu-id="45f2b-135">Refresh the page.</span></span>

