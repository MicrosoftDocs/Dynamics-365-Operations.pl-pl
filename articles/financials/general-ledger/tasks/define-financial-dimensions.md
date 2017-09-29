--- 
title: "Definiowanie wymiarów finansowych"
description: W tym przewodniku po zadaniach pokazano dodawanie wymiaru finansowego opartego na jednostce oraz niestandardowego wymiaru finansowego.
author: aprilolson
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
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 0b72acf763f0f6dbc64c3e00986bc9eb0e366bb5
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="define-financial-dimensions"></a><span data-ttu-id="e4f4f-103">Definiowanie wymiarów finansowych</span><span class="sxs-lookup"><span data-stu-id="e4f4f-103">Define financial dimensions</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e4f4f-104">W tym przewodniku po zadaniach pokazano dodawanie wymiaru finansowego opartego na jednostce oraz niestandardowego wymiaru finansowego.</span><span class="sxs-lookup"><span data-stu-id="e4f4f-104">This task guide demonstrates adding an entity backed financial dimension and a custom financial dimension.</span></span>  <span data-ttu-id="e4f4f-105">W przewodniku jest wykorzystywana firma demonstracyjna USMF.</span><span class="sxs-lookup"><span data-stu-id="e4f4f-105">The guide uses the USMF demo company.</span></span>


## <a name="create-an-entity-backed-financial-dimension"></a><span data-ttu-id="e4f4f-106">Tworzenie wymiaru finansowego opartego na jednostce</span><span class="sxs-lookup"><span data-stu-id="e4f4f-106">Create an entity backed financial dimension</span></span>
1. <span data-ttu-id="e4f4f-107">Wybierz kolejno opcje Księga główna > Plan kont > Wymiary > Wymiary finansowe.</span><span class="sxs-lookup"><span data-stu-id="e4f4f-107">Go to General ledger > Chart of accounts > Dimensions > Financial dimensions.</span></span>
2. <span data-ttu-id="e4f4f-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e4f4f-108">Click New.</span></span>
3. <span data-ttu-id="e4f4f-109">W polu Użyj wartości z wybierz zdefiniowaną w systemie jednostkę, na podstawie której zostanie utworzony wymiar finansowy.</span><span class="sxs-lookup"><span data-stu-id="e4f4f-109">In the User values from field, select a system-defined entity to base the financial dimension on.</span></span> 
4. <span data-ttu-id="e4f4f-110">W polu Nazwa wymiaru wpisz wartość, która będzie opisywać wymiar finansowy.</span><span class="sxs-lookup"><span data-stu-id="e4f4f-110">In the Dimension name field, type a value to describe the financial dimension.</span></span>
    * <span data-ttu-id="e4f4f-111">Nazwa może być inna niż nazwa jednostki zdefiniowana przez system, ale nie może zawierać spacji ani znaków specjalnych.</span><span class="sxs-lookup"><span data-stu-id="e4f4f-111">The name can be different than the system-defined entity but cannot contain spaces or special characters.</span></span>  
5. <span data-ttu-id="e4f4f-112">Kliknij Aktywacja.</span><span class="sxs-lookup"><span data-stu-id="e4f4f-112">Click Activate.</span></span>
    * <span data-ttu-id="e4f4f-113">Aktywowanie wymiaru finansowego aktualizuje tabelę o nazwę wymiaru finansowego i kasuje usunięte wymiary.</span><span class="sxs-lookup"><span data-stu-id="e4f4f-113">Activating the financial dimension updates the table with the financial dimension name and removes deleted dimensions.</span></span> <span data-ttu-id="e4f4f-114">Można wprowadzić wartości wymiarów przed aktywacją wymiaru finansowego, ale nie można używać wymiaru finansowego, dopóki nie zostanie aktywowany.</span><span class="sxs-lookup"><span data-stu-id="e4f4f-114">You can enter dimension values before you activate a financial dimension, but a financial dimension cannot be used until it is activated.</span></span>  
6. <span data-ttu-id="e4f4f-115">W komunikacie o aktywacji kliknij przycisk Zamknij.</span><span class="sxs-lookup"><span data-stu-id="e4f4f-115">Click Close on the activation message.</span></span>
7. <span data-ttu-id="e4f4f-116">Kliknij Aktywacja.</span><span class="sxs-lookup"><span data-stu-id="e4f4f-116">Click Activate.</span></span>
    * <span data-ttu-id="e4f4f-117">Aktywację wymiaru można zaplanować do wykonania wsadowego w określonym dniu i godzinie.</span><span class="sxs-lookup"><span data-stu-id="e4f4f-117">Dimension activation can be scheduled to run by batch at a specific date and time.</span></span>  
8. <span data-ttu-id="e4f4f-118">Kliknij opcję Wartości wymiarów.</span><span class="sxs-lookup"><span data-stu-id="e4f4f-118">Click Dimension values.</span></span>
    * <span data-ttu-id="e4f4f-119">Niektóre wartości wymiarów są przypisane do określonej firmy.</span><span class="sxs-lookup"><span data-stu-id="e4f4f-119">Some dimension values are company specific.</span></span> <span data-ttu-id="e4f4f-120">Oznaką, że są one specyficzne dla firmy, jest wyświetlanie nazwy firmy na liście wartości wymiarów.</span><span class="sxs-lookup"><span data-stu-id="e4f4f-120">You can verify if they are company specific by if the company name is showing in the dimension values list.</span></span>  

## <a name="create-a-custom-financial-dimension"></a><span data-ttu-id="e4f4f-121">Tworzenie niestandardowego wymiaru finansowego</span><span class="sxs-lookup"><span data-stu-id="e4f4f-121">Create a custom financial dimension</span></span>
1. <span data-ttu-id="e4f4f-122">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e4f4f-122">Close the page.</span></span>
2. <span data-ttu-id="e4f4f-123">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e4f4f-123">Click New.</span></span>
3. <span data-ttu-id="e4f4f-124">W polu Użyj wartości z wybierz opcję <Custom dimension>.</span><span class="sxs-lookup"><span data-stu-id="e4f4f-124">In the Use values from field, select <Custom dimension>.</span></span>
4. <span data-ttu-id="e4f4f-125">W polu Nazwa wymiaru wpisz wartość, która będzie opisywać wymiar finansowy.</span><span class="sxs-lookup"><span data-stu-id="e4f4f-125">In the Dimension name field, type a value to describe the financial dimension.</span></span>
    * <span data-ttu-id="e4f4f-126">Nazwa nie może zawierać spacji ani znaków specjalnych.</span><span class="sxs-lookup"><span data-stu-id="e4f4f-126">The name cannot contain spaces or special characters.</span></span>  
    * <span data-ttu-id="e4f4f-127">Można również określić maskę konta, aby ograniczyć typ i ilość informacji, które można wprowadzić dla wartości wymiarów,.</span><span class="sxs-lookup"><span data-stu-id="e4f4f-127">You can also specify an account mask to limit the amount and type of information that you can enter for dimension values.</span></span>   
    * <span data-ttu-id="e4f4f-128">Można wprowadzić znaki, które pozostają takie same dla każdej wartości wymiaru, takie jak litery lub łącznik.</span><span class="sxs-lookup"><span data-stu-id="e4f4f-128">You can enter characters that remain the same for each dimension value, such as letters or a hyphen.</span></span> <span data-ttu-id="e4f4f-129">Można także wprowadzić znaki cyfr (#) i handlowe „i” (&) jako symbole zastępcze liter i cyfr, które zmieniają się za każdym razem, gdy wartość wymiaru jest tworzona.</span><span class="sxs-lookup"><span data-stu-id="e4f4f-129">You can also enter number signs (#) and ampersands (&) as placeholders for letters and numbers that will change every time that a dimension value is created.</span></span> <span data-ttu-id="e4f4f-130">Znak cyfry (#) służy jako symbol zastępczy dla cyfr a znak handlowe „i” jako symbol zastępczy dla liter.</span><span class="sxs-lookup"><span data-stu-id="e4f4f-130">Use a number sign (#) as a placeholder for a number and an ampersand (&) as a placeholder for a letter.</span></span>  <span data-ttu-id="e4f4f-131">Przykład: Aby ograniczyć wartość wymiaru do liter CC i trzech cyfr, należy wprowadzić CC-### jako maskę formatu.</span><span class="sxs-lookup"><span data-stu-id="e4f4f-131">Example: To limit the dimension value to the letters CC and three numbers, you enter CC-### as the format mask.</span></span>  
5. <span data-ttu-id="e4f4f-132">Kliknij Aktywacja.</span><span class="sxs-lookup"><span data-stu-id="e4f4f-132">Click Activate.</span></span>
    * <span data-ttu-id="e4f4f-133">Aktywowanie wymiaru finansowego aktualizuje tabelę o nazwę wymiaru finansowego i kasuje usunięte wymiary.</span><span class="sxs-lookup"><span data-stu-id="e4f4f-133">Activating the financial dimension updates the table with the financial dimension name and removes deleted dimensions.</span></span> <span data-ttu-id="e4f4f-134">Można wprowadzić wartości wymiarów przed aktywacją wymiaru finansowego, ale nie można używać wymiaru finansowego, dopóki nie zostanie aktywowany.</span><span class="sxs-lookup"><span data-stu-id="e4f4f-134">You can enter dimension values before you activate a financial dimension, but a financial dimension cannot be used until it is activated.</span></span>  
6. <span data-ttu-id="e4f4f-135">Kliknij Aktywacja.</span><span class="sxs-lookup"><span data-stu-id="e4f4f-135">Click Activate.</span></span>
    * <span data-ttu-id="e4f4f-136">Aktywację wymiaru można zaplanować do wykonania wsadowego w określonym dniu i godzinie.</span><span class="sxs-lookup"><span data-stu-id="e4f4f-136">Dimension activation can be scheduled to run by batch at a specific date and time.</span></span>  
7. <span data-ttu-id="e4f4f-137">Kliknij opcję Wartości wymiarów.</span><span class="sxs-lookup"><span data-stu-id="e4f4f-137">Click Dimension values.</span></span>
8. <span data-ttu-id="e4f4f-138">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e4f4f-138">Click New.</span></span>
9. <span data-ttu-id="e4f4f-139">W polu Wartość wymiaru wpisz nazwę, która będzie opisywać wartość wymiaru finansowego.</span><span class="sxs-lookup"><span data-stu-id="e4f4f-139">In the Dimension value field, type a name to describe your financial dimension value.</span></span>
10. <span data-ttu-id="e4f4f-140">W polu Opis wprowadź opis przedstawiający wartość wymiaru finansowego.</span><span class="sxs-lookup"><span data-stu-id="e4f4f-140">In the Description field, type a description that describes your financial dimension value.</span></span>


