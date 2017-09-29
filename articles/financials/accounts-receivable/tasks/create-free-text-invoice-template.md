--- 
title: "Tworzenie szablonu faktury niezależnej"
description: "To nagranie wykorzystuje firmę demonstracyjną USMF."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/11/2016
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: e9c9811b348d81cd735c5b75ca48e0a56a8d52be
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-free-text-invoice-template"></a><span data-ttu-id="9412f-103">Tworzenie szablonu faktury niezależnej</span><span class="sxs-lookup"><span data-stu-id="9412f-103">Create a free text invoice template</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9412f-104">To nagranie wykorzystuje firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="9412f-104">This recording uses the USMF demo company.</span></span> <span data-ttu-id="9412f-105">To nagranie jest przeznaczone dla użytkownika, który odpowiada za zarządzanie i przetwarzanie faktur dla odbiorców.</span><span class="sxs-lookup"><span data-stu-id="9412f-105">The recording is intended for the user who is responsible for managing and processing A/R invoices.</span></span>

1. <span data-ttu-id="9412f-106">Wybierz kolejno opcje Rozrachunki z odbiorcami > Faktury > Faktury cykliczne > Szablon faktury niezależnej.</span><span class="sxs-lookup"><span data-stu-id="9412f-106">Go to Accounts receivable > Invoices > Recurring invoices > Free text invoice templates.</span></span>
    * <span data-ttu-id="9412f-107">Ten formularz służy do tworzenia szablonów faktur niezależnych, które mogą zawierać wiersze faktur, opłaty, szablon zasad podziału księgowań oraz informacje o koncie księgowym.</span><span class="sxs-lookup"><span data-stu-id="9412f-107">Use this form to create free text invoice templates that can include invoice lines, charges, an accounting distribution template, and ledger account information.</span></span>  
2. <span data-ttu-id="9412f-108">Kliknij przycisk „Nowy”, aby utworzyć nowy szablon faktury niezależnej.</span><span class="sxs-lookup"><span data-stu-id="9412f-108">Click 'New' to create a new free text invoice template.</span></span>
3. <span data-ttu-id="9412f-109">W polu Nazwa szablonu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="9412f-109">In the Template name field, type a value.</span></span>
    * <span data-ttu-id="9412f-110">Pole „Nazwa szablonu” w sposób unikatowy identyfikuje szablon faktury niezależnej.</span><span class="sxs-lookup"><span data-stu-id="9412f-110">‘Template name’ uniquely identifies a free text invoice template.</span></span> <span data-ttu-id="9412f-111">Żadne dwa szablony nie mogą mieć takiej samej wartości „Nazwa szablonu”.</span><span class="sxs-lookup"><span data-stu-id="9412f-111">No two templates can have the same ‘Template name’.</span></span>  
4. <span data-ttu-id="9412f-112">W polu Opis wprowadź opis szablonu.</span><span class="sxs-lookup"><span data-stu-id="9412f-112">In the Description field, enter a description of the template.</span></span>
5. <span data-ttu-id="9412f-113">Rozwiń kartę Wiersze faktury.</span><span class="sxs-lookup"><span data-stu-id="9412f-113">Expand the Invoice lines tab.</span></span>
6. <span data-ttu-id="9412f-114">W polu Opis wprowadź opis wiersza faktury.</span><span class="sxs-lookup"><span data-stu-id="9412f-114">In the Description field, enter a description of the invoice line.</span></span>
7. <span data-ttu-id="9412f-115">W polu Konto główne wybierz konto przychodów.</span><span class="sxs-lookup"><span data-stu-id="9412f-115">In the Main account field, select a revenue account.</span></span>
    * <span data-ttu-id="9412f-116">Na stronie Profile księgowania odbiorców można wybrać konto transakcji przeciwstawnej dla księgowania łącznej kwoty faktury po stronie kredytowej odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="9412f-116">You can select the offset transaction account of a customer credit for the total invoice amount in the Customer posting profiles page.</span></span>  
8. <span data-ttu-id="9412f-117">W polu Grupa podatków kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="9412f-117">In the Sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="9412f-118">Grupa podatków dla bieżącego wiersza faktury jest domyślną grupą podatków dla konta odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="9412f-118">The sales tax group for the current invoice line is the default sales tax group for the customer account.</span></span>  
9. <span data-ttu-id="9412f-119">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="9412f-119">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="9412f-120">W polu Grupa podatków dla towaru wybierz grupę podatków od towaru dla bieżącego wiersza faktury.</span><span class="sxs-lookup"><span data-stu-id="9412f-120">In the Item tax group field, select the item sales tax group for the current invoice line.</span></span>
11. <span data-ttu-id="9412f-121">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="9412f-121">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="9412f-122">W polu Cena jednostkowa wpisz lub wyświetl cenę za jednostkę towaru w wierszu faktury.</span><span class="sxs-lookup"><span data-stu-id="9412f-122">In the Unit price field, enter or view the price per unit for the invoice line</span></span>
    * <span data-ttu-id="9412f-123">Ta kwota jest mnożona przez wartość w polu Ilość w celu ustalenia kwoty wiersza faktury.</span><span class="sxs-lookup"><span data-stu-id="9412f-123">This amount is multiplied by the Quantity field to determine the invoice line amount.</span></span>  
13. <span data-ttu-id="9412f-124">Dodaj nowy wiersz do szablonu faktury niezależnej.</span><span class="sxs-lookup"><span data-stu-id="9412f-124">Add a new line to free text invoice template.</span></span>
14. <span data-ttu-id="9412f-125">W polu Opis wprowadź opis wiersza faktury.</span><span class="sxs-lookup"><span data-stu-id="9412f-125">In the Description field, enter a description of the invoice line.</span></span>
15. <span data-ttu-id="9412f-126">W polu Konto główne wybierz konto przychodów.</span><span class="sxs-lookup"><span data-stu-id="9412f-126">In the Main account field, select a revenue account.</span></span>
    * <span data-ttu-id="9412f-127">Na stronie Profile księgowania odbiorców można wybrać konto transakcji przeciwstawnej dla księgowania łącznej kwoty faktury po stronie kredytowej odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="9412f-127">You can select the offset transaction account of a customer credit for the total invoice amount in the Customer posting profiles page.</span></span>  
16. <span data-ttu-id="9412f-128">W polu Grupa podatków kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="9412f-128">In the Sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="9412f-129">Grupa podatków dla bieżącego wiersza faktury jest domyślną grupą podatków dla konta odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="9412f-129">The sales tax group for the current invoice line is the default sales tax group for the customer account.</span></span>  
17. <span data-ttu-id="9412f-130">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="9412f-130">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="9412f-131">W polu Grupa podatków dla towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="9412f-131">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="9412f-132">Grupa podatków dla towaru dla bieżącego wiersza faktury.</span><span class="sxs-lookup"><span data-stu-id="9412f-132">The item sales tax group for the current invoice line.</span></span>  
19. <span data-ttu-id="9412f-133">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="9412f-133">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="9412f-134">Wprowadź lub wyświetl liczbę jednostek w wierszu faktury.</span><span class="sxs-lookup"><span data-stu-id="9412f-134">Enter or view the number of units for the invoice line</span></span>
    * <span data-ttu-id="9412f-135">Ta liczba jest mnożona przez wartość w polu Cena jednostkowa w celu ustalenia kwoty wiersza faktury.</span><span class="sxs-lookup"><span data-stu-id="9412f-135">This number is multiplied by the value in the Unit price field to determine the invoice line amount.</span></span>  
21. <span data-ttu-id="9412f-136">Wprowadź lub wyświetl cenę jednostkową dla wiersza faktury.</span><span class="sxs-lookup"><span data-stu-id="9412f-136">Enter or view the price per unit for the invoice line.</span></span> 
    * <span data-ttu-id="9412f-137">Ta kwota jest mnożona przez wartość w polu Ilość w celu ustalenia kwoty wiersza faktury.</span><span class="sxs-lookup"><span data-stu-id="9412f-137">This amount is multiplied by the value in the Quantity field to determine the invoice line amount.</span></span>  
22. <span data-ttu-id="9412f-138">Wyświetl i zmodyfikuj zasady podziału księgowań dla określonego wiersza i jego wierszy podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="9412f-138">View and modify the accounting distributions for an individual line and any child lines.</span></span>
    * <span data-ttu-id="9412f-139">Zasady podziału księgowań określają sposób księgowania kwot, czyli przychodów, podatków lub opłat, na fakturze niezależnej.</span><span class="sxs-lookup"><span data-stu-id="9412f-139">Accounting distributions define how an amount will be accounted for, such as how the revenue, tax, or charges will be accounted for on a free text invoice.</span></span>  
23. <span data-ttu-id="9412f-140">Zaktualizuj zasady podziału księgowań dla wybranego wiersza faktury.</span><span class="sxs-lookup"><span data-stu-id="9412f-140">Update the accounting distributions for the selected invoice line.</span></span>
24. <span data-ttu-id="9412f-141">Kliknij przycisk Zamknij.</span><span class="sxs-lookup"><span data-stu-id="9412f-141">Click Close.</span></span>


