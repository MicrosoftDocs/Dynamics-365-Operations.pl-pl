---
title: Definiowanie wymiarów finansowych
description: W tym przewodniku po zadaniach pokazano dodawanie wymiaru finansowego opartego na jednostce oraz niestandardowego wymiaru finansowego.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionDetails,  DimensionAttributeTableExtensionActivate, DimensionValueDetails
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c5cfe92b8733a0a6d76e074cc31eec3f3935b512
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "1530875"
---
# <a name="define-financial-dimensions"></a><span data-ttu-id="07c2e-103">Definiowanie wymiarów finansowych</span><span class="sxs-lookup"><span data-stu-id="07c2e-103">Define financial dimensions</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="07c2e-104">W tym przewodniku po zadaniach pokazano dodawanie wymiaru finansowego opartego na jednostce oraz niestandardowego wymiaru finansowego.</span><span class="sxs-lookup"><span data-stu-id="07c2e-104">This task guide demonstrates adding an entity backed financial dimension and a custom financial dimension.</span></span>  <span data-ttu-id="07c2e-105">W przewodniku jest wykorzystywana firma demonstracyjna USMF.</span><span class="sxs-lookup"><span data-stu-id="07c2e-105">The guide uses the USMF demo company.</span></span>


## <a name="create-an-entity-backed-financial-dimension"></a><span data-ttu-id="07c2e-106">Tworzenie wymiaru finansowego opartego na jednostce</span><span class="sxs-lookup"><span data-stu-id="07c2e-106">Create an entity backed financial dimension</span></span>
1. <span data-ttu-id="07c2e-107">Wybierz kolejno opcje Księga główna > Plan kont > Wymiary > Wymiary finansowe.</span><span class="sxs-lookup"><span data-stu-id="07c2e-107">Go to General ledger > Chart of accounts > Dimensions > Financial dimensions.</span></span>
2. <span data-ttu-id="07c2e-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="07c2e-108">Click New.</span></span>
3. <span data-ttu-id="07c2e-109">W polu Formularz wartości użytkownika wybierz zdefiniowaną w systemie jednostkę, na podstawie której zostanie utworzony wymiar finansowy.</span><span class="sxs-lookup"><span data-stu-id="07c2e-109">In the User values form field, select a system-defined entity to base the financial dimension on.</span></span> 
4. <span data-ttu-id="07c2e-110">W polu Nazwa wymiaru wpisz wartość, która będzie opisywać wymiar finansowy.</span><span class="sxs-lookup"><span data-stu-id="07c2e-110">In the Dimension name field, type a value to describe the financial dimension.</span></span>
    * <span data-ttu-id="07c2e-111">Nazwa może być inna niż nazwa jednostki zdefiniowana przez system, ale nie może zawierać spacji ani znaków specjalnych.</span><span class="sxs-lookup"><span data-stu-id="07c2e-111">The name can be different than the system-defined entity but cannot contain spaces or special characters.</span></span>  
5. <span data-ttu-id="07c2e-112">Kliknij Aktywacja.</span><span class="sxs-lookup"><span data-stu-id="07c2e-112">Click Activate.</span></span>
    * <span data-ttu-id="07c2e-113">Aktywowanie wymiaru finansowego aktualizuje tabelę o nazwę wymiaru finansowego i kasuje usunięte wymiary.</span><span class="sxs-lookup"><span data-stu-id="07c2e-113">Activating the financial dimension updates the table with the financial dimension name and removes deleted dimensions.</span></span> <span data-ttu-id="07c2e-114">Można wprowadzić wartości wymiarów przed aktywacją wymiaru finansowego, ale nie można używać wymiaru finansowego, dopóki nie zostanie aktywowany.</span><span class="sxs-lookup"><span data-stu-id="07c2e-114">You can enter dimension values before you activate a financial dimension, but a financial dimension cannot be used until it is activated.</span></span>  
6. <span data-ttu-id="07c2e-115">W komunikacie o aktywacji kliknij przycisk Zamknij.</span><span class="sxs-lookup"><span data-stu-id="07c2e-115">Click Close on the activation message.</span></span>
7. <span data-ttu-id="07c2e-116">Kliknij Aktywacja.</span><span class="sxs-lookup"><span data-stu-id="07c2e-116">Click Activate.</span></span>
    * <span data-ttu-id="07c2e-117">Aktywację wymiaru można zaplanować do wykonania wsadowego w określonym dniu i godzinie.</span><span class="sxs-lookup"><span data-stu-id="07c2e-117">Dimension activation can be scheduled to run by batch at a specific date and time.</span></span>  
8. <span data-ttu-id="07c2e-118">Kliknij opcję Wartości wymiarów.</span><span class="sxs-lookup"><span data-stu-id="07c2e-118">Click Dimension values.</span></span>
    * <span data-ttu-id="07c2e-119">Niektóre wartości wymiarów są przypisane do określonej firmy.</span><span class="sxs-lookup"><span data-stu-id="07c2e-119">Some dimension values are company specific.</span></span> <span data-ttu-id="07c2e-120">Oznaką, że są one specyficzne dla firmy, jest wyświetlanie nazwy firmy na liście wartości wymiarów.</span><span class="sxs-lookup"><span data-stu-id="07c2e-120">You can verify if they are company specific by if the company name is showing in the dimension values list.</span></span>  

## <a name="create-a-custom-financial-dimension"></a><span data-ttu-id="07c2e-121">Tworzenie niestandardowego wymiaru finansowego</span><span class="sxs-lookup"><span data-stu-id="07c2e-121">Create a custom financial dimension</span></span>
1. <span data-ttu-id="07c2e-122">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="07c2e-122">Close the page.</span></span>
2. <span data-ttu-id="07c2e-123">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="07c2e-123">Click New.</span></span>
3. <span data-ttu-id="07c2e-124">W polu Użyj wartości wybierz opcję Wymiar niestandardowy.</span><span class="sxs-lookup"><span data-stu-id="07c2e-124">In the Use values from field, select Custom dimension.</span></span>
4. <span data-ttu-id="07c2e-125">W polu Nazwa wymiaru wpisz wartość, która będzie opisywać wymiar finansowy.</span><span class="sxs-lookup"><span data-stu-id="07c2e-125">In the Dimension name field, type a value to describe the financial dimension.</span></span>
    * <span data-ttu-id="07c2e-126">Nazwa nie może zawierać spacji ani znaków specjalnych.</span><span class="sxs-lookup"><span data-stu-id="07c2e-126">The name cannot contain spaces or special characters.</span></span>  
    * <span data-ttu-id="07c2e-127">Można również określić maskę konta, aby ograniczyć typ i ilość informacji, które można wprowadzić dla wartości wymiarów,.</span><span class="sxs-lookup"><span data-stu-id="07c2e-127">You can also specify an account mask to limit the amount and type of information that you can enter for dimension values.</span></span>   
    * <span data-ttu-id="07c2e-128">Można wprowadzić znaki, które pozostają takie same dla każdej wartości wymiaru, takie jak litery lub łącznik.</span><span class="sxs-lookup"><span data-stu-id="07c2e-128">You can enter characters that remain the same for each dimension value, such as letters or a hyphen.</span></span> <span data-ttu-id="07c2e-129">Można także wprowadzić znaki cyfr (#) i handlowe „i” (&) jako symbole zastępcze liter i cyfr, które zmieniają się za każdym razem, gdy wartość wymiaru jest tworzona.</span><span class="sxs-lookup"><span data-stu-id="07c2e-129">You can also enter number signs (#) and ampersands (&) as placeholders for letters and numbers that will change every time that a dimension value is created.</span></span> <span data-ttu-id="07c2e-130">Znak cyfry (#) służy jako symbol zastępczy dla cyfr a znak handlowe „i” jako symbol zastępczy dla liter.</span><span class="sxs-lookup"><span data-stu-id="07c2e-130">Use a number sign (#) as a placeholder for a number and an ampersand (&) as a placeholder for a letter.</span></span>  <span data-ttu-id="07c2e-131">Przykład: Aby ograniczyć wartość wymiaru do liter CC i trzech cyfr, należy wprowadzić CC-### jako maskę formatu.</span><span class="sxs-lookup"><span data-stu-id="07c2e-131">Example: To limit the dimension value to the letters CC and three numbers, you enter CC-### as the format mask.</span></span>  
5. <span data-ttu-id="07c2e-132">Kliknij Aktywacja.</span><span class="sxs-lookup"><span data-stu-id="07c2e-132">Click Activate.</span></span>
    * <span data-ttu-id="07c2e-133">Aktywowanie wymiaru finansowego aktualizuje tabelę o nazwę wymiaru finansowego i kasuje usunięte wymiary.</span><span class="sxs-lookup"><span data-stu-id="07c2e-133">Activating the financial dimension updates the table with the financial dimension name and removes deleted dimensions.</span></span> <span data-ttu-id="07c2e-134">Można wprowadzić wartości wymiarów przed aktywacją wymiaru finansowego, ale nie można używać wymiaru finansowego, dopóki nie zostanie aktywowany.</span><span class="sxs-lookup"><span data-stu-id="07c2e-134">You can enter dimension values before you activate a financial dimension, but a financial dimension cannot be used until it is activated.</span></span>  
6. <span data-ttu-id="07c2e-135">Kliknij Aktywacja.</span><span class="sxs-lookup"><span data-stu-id="07c2e-135">Click Activate.</span></span>
    * <span data-ttu-id="07c2e-136">Aktywację wymiaru można zaplanować do wykonania wsadowego w określonym dniu i godzinie.</span><span class="sxs-lookup"><span data-stu-id="07c2e-136">Dimension activation can be scheduled to run by batch at a specific date and time.</span></span>  
7. <span data-ttu-id="07c2e-137">Kliknij opcję Wartości wymiarów.</span><span class="sxs-lookup"><span data-stu-id="07c2e-137">Click Dimension values.</span></span>
8. <span data-ttu-id="07c2e-138">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="07c2e-138">Click New.</span></span>
9. <span data-ttu-id="07c2e-139">W polu Wartość wymiaru wpisz nazwę, która będzie opisywać wartość wymiaru finansowego.</span><span class="sxs-lookup"><span data-stu-id="07c2e-139">In the Dimension value field, type a name to describe your financial dimension value.</span></span>
10. <span data-ttu-id="07c2e-140">W polu Opis wprowadź opis przedstawiający wartość wymiaru finansowego.</span><span class="sxs-lookup"><span data-stu-id="07c2e-140">In the Description field, type a description that describes your financial dimension value.</span></span>

