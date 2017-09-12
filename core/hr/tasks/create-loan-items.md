--- 
title: "Tworzenie przedmiotów pożyczek"
description: "Przedmioty pożyczek są rekordami, które pomagają śledzić fizyczne przedmioty, takie jak telefony lub komputery, które firma pożycza pracownikom."
author: kherr75
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 65655283c70c99b5d64289b319ecc69f6e414221
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="create-loan-items"></a><span data-ttu-id="f0474-103">Tworzenie przedmiotów pożyczek</span><span class="sxs-lookup"><span data-stu-id="f0474-103">Create loan items</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f0474-104">Przedmioty pożyczek są rekordami, które pomagają śledzić fizyczne przedmioty, takie jak telefony lub komputery, które firma pożycza pracownikom.</span><span class="sxs-lookup"><span data-stu-id="f0474-104">Loan items are records that help you track physical items, such as phones or computers, that your company lends to workers.</span></span> <span data-ttu-id="f0474-105">Każdy przedmiot fizyczny musi mieć odpowiadający mu przedmiot pożyczki.</span><span class="sxs-lookup"><span data-stu-id="f0474-105">Each physical item must have a corresponding loan item.</span></span> <span data-ttu-id="f0474-106">Każdy rekord przedmiotu pożyczki powinien opisywać wypożyczany przedmiot, osobę odpowiedzialną za wypożyczenie oraz możliwą liczbę dni wypożyczenia przedmiotu.</span><span class="sxs-lookup"><span data-stu-id="f0474-106">Each loan item record should describe what is being loaned, who is responsible for the loan, and the number of days the item can be on loan.</span></span> <span data-ttu-id="f0474-107">Można utworzyć wiele przedmiotów pożyczki, takich jak klucze, karty dostępu lub mundury, w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="f0474-107">You can create multiple loan items, such as keys, access cards, or uniforms, at the same time.</span></span> <span data-ttu-id="f0474-108">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="f0474-108">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-loan-types"></a><span data-ttu-id="f0474-109">Tworzenie typów pożyczek</span><span class="sxs-lookup"><span data-stu-id="f0474-109">Create Loan types</span></span>
1. <span data-ttu-id="f0474-110">Wybierz kolejno opcje Zasoby ludzkie > Pracownicy > Przedmioty pożyczek > Typy pożyczek.</span><span class="sxs-lookup"><span data-stu-id="f0474-110">Go to Human resources > Workers > Loan items > Loan types.</span></span>
2. <span data-ttu-id="f0474-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="f0474-111">Click New.</span></span>
3. <span data-ttu-id="f0474-112">W polu Typ pożyczki wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="f0474-112">In the Loan type field, type a value.</span></span>
4. <span data-ttu-id="f0474-113">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="f0474-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="f0474-114">Wprowadź liczbę dni, po upływie których przedmioty przypisane do tego typu pożyczki mogą stanowić zaległość.</span><span class="sxs-lookup"><span data-stu-id="f0474-114">Enter the number of days that items assigned to this loan type can be overdue.</span></span> 
6. <span data-ttu-id="f0474-115">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="f0474-115">Click Save.</span></span>
7. <span data-ttu-id="f0474-116">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f0474-116">Close the page.</span></span>
8. <span data-ttu-id="f0474-117">Odśwież stronę.</span><span class="sxs-lookup"><span data-stu-id="f0474-117">Refresh the page.</span></span>

## <a name="create-loan-items"></a><span data-ttu-id="f0474-118">Tworzenie przedmiotów pożyczek</span><span class="sxs-lookup"><span data-stu-id="f0474-118">Create Loan items</span></span>
1. <span data-ttu-id="f0474-119">Wybierz kolejno opcje Zasoby ludzkie > Pracownicy > Przedmioty pożyczek > Przedmioty pożyczek.</span><span class="sxs-lookup"><span data-stu-id="f0474-119">Go to Human resources > Workers > Loan items > Loan items.</span></span>
2. <span data-ttu-id="f0474-120">Kliknij opcję Tworzenie przedmiotów pożyczek.</span><span class="sxs-lookup"><span data-stu-id="f0474-120">Click Create loan items.</span></span>
3. <span data-ttu-id="f0474-121">W polu Ilość</span><span class="sxs-lookup"><span data-stu-id="f0474-121">In the Qty.</span></span> <span data-ttu-id="f0474-122">wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="f0474-122">field, enter a number.</span></span>
4. <span data-ttu-id="f0474-123">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="f0474-123">In the Description field, type a value.</span></span>
5. <span data-ttu-id="f0474-124">W polu Typ pożyczki kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="f0474-124">In the Loan type field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="f0474-125">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="f0474-125">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="f0474-126">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="f0474-126">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="f0474-127">Wprowadź liczbę dni, przez jaką przedmiot może być wypożyczony.</span><span class="sxs-lookup"><span data-stu-id="f0474-127">Enter the number of days the item can be on loan.</span></span>
    * <span data-ttu-id="f0474-128">Domyślna wartość pola Planowany zwrot na stronie Sprzęt wypożyczony jest obliczana przez dodanie tej liczby do daty bieżącej.</span><span class="sxs-lookup"><span data-stu-id="f0474-128">The default value for the Planned return field on the Loaned equipment page is calculated as the current date plus this number.</span></span>  
9. <span data-ttu-id="f0474-129">W polu Osoba odpowiedzialna kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="f0474-129">In the Person in charge field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="f0474-130">Kliknij opcję Wybierz.</span><span class="sxs-lookup"><span data-stu-id="f0474-130">Click Select.</span></span>
11. <span data-ttu-id="f0474-131">W polu Wartość początkowa wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="f0474-131">In the Starting value field, enter a number.</span></span>
12. <span data-ttu-id="f0474-132">W polu Interwał wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="f0474-132">In the Interval field, enter a number.</span></span>
13. <span data-ttu-id="f0474-133">W polu Format wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="f0474-133">In the Format field, type a value.</span></span>
    * <span data-ttu-id="f0474-134">Na przykład jeśli numerem początkowym przedmiotu pożyczki jest 10, wprowadź dwa symbole liczb w polu Format.</span><span class="sxs-lookup"><span data-stu-id="f0474-134">For example, if the starting number for a loan item is 10, enter two number symbols symbols in the Format field.</span></span>  
14. <span data-ttu-id="f0474-135">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="f0474-135">Click OK.</span></span>
15. <span data-ttu-id="f0474-136">Odśwież stronę.</span><span class="sxs-lookup"><span data-stu-id="f0474-136">Refresh the page.</span></span>


