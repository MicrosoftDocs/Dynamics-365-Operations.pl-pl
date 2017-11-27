---
title: "Tworzenie działu i przypisywanie go do hierarchii działów"
description: "Dział to jednostka operacyjna należąca do kategorii lub obszaru funkcjonalnego organizacji. Dział jest odpowiedzialny za określony obszar organizacji, np. sprzedaż, księgowość lub zasoby ludzkie. Działy pozwalają tworzyć raporty dotyczące obszarów funkcyjnych. Działy mogą mieć odpowiedzialność zysków i strat."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HierarchyDesigner, OMOperatingUnit
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.custom: 63213
ms.assetid: 5dbc62fc-0184-4c0e-9856-e735fc68799e
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: cea3ecd66a57780c9ef1b3a3c21f1e5273faa0ef
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="create-a-department-and-associate-it-with-the-department-hierarchy"></a><span data-ttu-id="8de98-106">Tworzenie działu i przypisywanie go do hierarchii działów</span><span class="sxs-lookup"><span data-stu-id="8de98-106">Create a department and associate it with the department hierarchy</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="8de98-107">Dział to jednostka operacyjna należąca do kategorii lub obszaru funkcjonalnego organizacji.</span><span class="sxs-lookup"><span data-stu-id="8de98-107">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="8de98-108">Dział jest odpowiedzialny za określony obszar organizacji, np. sprzedaż, księgowość lub zasoby ludzkie.</span><span class="sxs-lookup"><span data-stu-id="8de98-108">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="8de98-109">Działy pozwalają tworzyć raporty dotyczące obszarów funkcyjnych.</span><span class="sxs-lookup"><span data-stu-id="8de98-109">You can use departments to report on functional areas.</span></span> <span data-ttu-id="8de98-110">Działy mogą mieć odpowiedzialność zysków i strat.</span><span class="sxs-lookup"><span data-stu-id="8de98-110">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="8de98-111">Dział może zawierać grupę centrów kosztów.</span><span class="sxs-lookup"><span data-stu-id="8de98-111">A department might include a group of cost centers.</span></span> <span data-ttu-id="8de98-112">Stanowiska mogą być przypisywane do działów.</span><span class="sxs-lookup"><span data-stu-id="8de98-112">Positions can be assigned to departments.</span></span> <span data-ttu-id="8de98-113">Aby utworzyć dział, kliknij kolejno opcje **Zasoby ludzkie** &gt; **Działy** &gt; **Dział**.</span><span class="sxs-lookup"><span data-stu-id="8de98-113">To create a department, click **Human Resources** &gt; **Departments** &gt; **Department**.</span></span> <span data-ttu-id="8de98-114">W poniższej tabeli przedstawiono dostępne pola.</span><span class="sxs-lookup"><span data-stu-id="8de98-114">The following table describes the fields that are available.</span></span>

| <span data-ttu-id="8de98-115">Pole</span><span class="sxs-lookup"><span data-stu-id="8de98-115">Field</span></span>               | <span data-ttu-id="8de98-116">Opis</span><span class="sxs-lookup"><span data-stu-id="8de98-116">Description</span></span>                                                                                                                                                                                                       |
|---------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="8de98-117">Imię i nazwisko</span><span class="sxs-lookup"><span data-stu-id="8de98-117">Name</span></span>                | <span data-ttu-id="8de98-118">Wprowadź nazwę działu.</span><span class="sxs-lookup"><span data-stu-id="8de98-118">Enter a name for the department.</span></span>                                                                                                                                                                                  |
| <span data-ttu-id="8de98-119">Numer działu</span><span class="sxs-lookup"><span data-stu-id="8de98-119">Department number</span></span>   | <span data-ttu-id="8de98-120">Domyślna wartość może być generowana automatycznie, jeśli kod sekwencji identyfikatorów jest przypisany do odwołania **Numer organizacji** na stronie **Sekwencje identyfikatorów**.</span><span class="sxs-lookup"><span data-stu-id="8de98-120">A default value might be generated automatically if a number sequence code is assigned to the **Organization number** reference on the **Number sequences** page.</span></span>                                                 |
| <span data-ttu-id="8de98-121">Alias</span><span class="sxs-lookup"><span data-stu-id="8de98-121">Search name</span></span>         | <span data-ttu-id="8de98-122">Wprowadź krótką nazwę lub akronim, aby ułatwić szybkie wyszukiwanie działów.</span><span class="sxs-lookup"><span data-stu-id="8de98-122">Enter a name or acronym that can be used to search for the department.</span></span>                                                                                                                                            |
| <span data-ttu-id="8de98-123">Nota</span><span class="sxs-lookup"><span data-stu-id="8de98-123">Memo</span></span>                | <span data-ttu-id="8de98-124">Tutaj możesz wprowadzić dodatkowe informacje.</span><span class="sxs-lookup"><span data-stu-id="8de98-124">Enter any additional information here.</span></span>                                                                                                                                                                            |
| <span data-ttu-id="8de98-125">W hierarchii</span><span class="sxs-lookup"><span data-stu-id="8de98-125">In hierarchy</span></span>        | <span data-ttu-id="8de98-126">Jeśli pole wyboru jest zaznaczone, to znaczy, że ten dział jest uwzględniony w hierarchii działów.</span><span class="sxs-lookup"><span data-stu-id="8de98-126">A selected check box indicates that the department is included in the department hierarchy.</span></span> <span data-ttu-id="8de98-127">Aby uzyskać informacje o tym, jak dodawać działy do hierarchii działów, zobacz informacje w dalszej części tego artykułu.</span><span class="sxs-lookup"><span data-stu-id="8de98-127">For information about how to add a department to the department hierarchy, see the information later in this article.</span></span> |
| <span data-ttu-id="8de98-128">Kod DUNS</span><span class="sxs-lookup"><span data-stu-id="8de98-128">DUNS number</span></span>         | <span data-ttu-id="8de98-129">DUNS to skrót od Data Universal Number System (uniwersalny system numerowania danych).</span><span class="sxs-lookup"><span data-stu-id="8de98-129">DUNS stands for Data Universal Number System.</span></span> <span data-ttu-id="8de98-130">Jest o 9-cyfrowy numer wydawany przez firmę Dun & Bradstreet.</span><span class="sxs-lookup"><span data-stu-id="8de98-130">This is a nine-digit number that is issued by Dun & Bradstreet.</span></span>                                                                                                     |
| <span data-ttu-id="8de98-131">Menedżer</span><span class="sxs-lookup"><span data-stu-id="8de98-131">Manager</span></span>             | <span data-ttu-id="8de98-132">Wpisz osobę zarządzającą działem.</span><span class="sxs-lookup"><span data-stu-id="8de98-132">Enter the persona that manages the department.</span></span>                                                                                                                                                                    |
| <span data-ttu-id="8de98-133">Adresy</span><span class="sxs-lookup"><span data-stu-id="8de98-133">Addresses</span></span>           | <span data-ttu-id="8de98-134">Dodaj informacje adresowe dla działu.</span><span class="sxs-lookup"><span data-stu-id="8de98-134">Add the address information for the department.</span></span> <span data-ttu-id="8de98-135">Na przykład, dodaj adres korespondencyjny budynku, w którym mieści się dział.</span><span class="sxs-lookup"><span data-stu-id="8de98-135">For example, add the mailing address for the building that the department is located in.</span></span>                                                                          |
| <span data-ttu-id="8de98-136">Informacje kontaktowe</span><span class="sxs-lookup"><span data-stu-id="8de98-136">Contact information</span></span> | <span data-ttu-id="8de98-137">Dodaj informacje kontaktowe dla działu.</span><span class="sxs-lookup"><span data-stu-id="8de98-137">Add contact information for the department.</span></span> <span data-ttu-id="8de98-138">Na przykład, dodaj numer telefonu do stanowiska obsługi w dziale.</span><span class="sxs-lookup"><span data-stu-id="8de98-138">For example, add a telephone number for the service desk in the department.</span></span>                                                                                           |

<span data-ttu-id="8de98-139">Aby dodać dział do hierarchii działu, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="8de98-139">To add a department to the department hierarchy, follow these steps.</span></span>

1.  <span data-ttu-id="8de98-140">Kliknij kolejno opcje **Zasoby ludzkie** &gt; **Działy** &gt; **Hierarchia działów**.</span><span class="sxs-lookup"><span data-stu-id="8de98-140">Click **Human Resources** &gt; **Departments** &gt; **Department hierarchy**.</span></span>
2.  <span data-ttu-id="8de98-141">Kliknij **Edycja**, a następnie wybierz organizację, której powinien podlegać dział.</span><span class="sxs-lookup"><span data-stu-id="8de98-141">Click **Edit**, and then select the organization that the department should be under.</span></span>
3.  <span data-ttu-id="8de98-142">Kliknij **Wstaw** i wybierz **Dział** na liście.</span><span class="sxs-lookup"><span data-stu-id="8de98-142">Click **Insert**, and select **Department** in the list.</span></span>
4.  <span data-ttu-id="8de98-143">Z listy działów wybierz dział do dodania do hierarchii.</span><span class="sxs-lookup"><span data-stu-id="8de98-143">In the list of departments that appears, select the department to add to the hierarchy.</span></span>
5.  <span data-ttu-id="8de98-144">Zapisz zmiany.</span><span class="sxs-lookup"><span data-stu-id="8de98-144">Save your changes.</span></span> <span data-ttu-id="8de98-145">Pojawi się komunikat, że utworzono wersję roboczą hierarchii.</span><span class="sxs-lookup"><span data-stu-id="8de98-145">You receive a message that a draft version of the hierarchy has been created.</span></span>
6.  <span data-ttu-id="8de98-146">Po zakończeniu kliknij przycisk **Opublikuj** w projektancie hierarchii.</span><span class="sxs-lookup"><span data-stu-id="8de98-146">When you're ready, click **Publish** in the hierarchy designer.</span></span> <span data-ttu-id="8de98-147">Można wprowadzić datę wejścia w życie, która wskazuje, kiedy hierarchia powinna zostać opublikowana.</span><span class="sxs-lookup"><span data-stu-id="8de98-147">You can enter an effective date that indicates when the hierarchy should be published.</span></span> <span data-ttu-id="8de98-148">Na przykład aby dodać nowy dział na początku następnego roku kalendarzowego, ustaw datę wejścia w życie na 1 stycznia w nowym roku kalendarzowym.</span><span class="sxs-lookup"><span data-stu-id="8de98-148">For example, to add a new department at the beginning of the next calendar year, set the effective date to January 1 of the new calendar year.</span></span> <span data-ttu-id="8de98-149">Zmiany hierarchii zostaną wprowadzone w tym dniu.</span><span class="sxs-lookup"><span data-stu-id="8de98-149">The changes to the hierarchy will take effect on that date.</span></span>





