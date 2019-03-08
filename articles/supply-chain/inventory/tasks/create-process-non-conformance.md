---
title: Tworzenie i przetwarzanie zgodności
description: Ta procedura służy do zarządzania niezgodnościami na podstawie istniejącego zlecenia kontroli jakości.
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 16ed11bce92920fe8240fc85f706a2ac6ab0a04b
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "336297"
---
# <a name="create-and-process-a-conformance"></a><span data-ttu-id="bd714-103">Tworzenie i przetwarzanie zgodności</span><span class="sxs-lookup"><span data-stu-id="bd714-103">Create and process a conformance</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bd714-104">Ta procedura służy do zarządzania niezgodnościami na podstawie istniejącego zlecenia kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="bd714-104">Use this procedure to perform nonconformance management, based on an existing quality order.</span></span> <span data-ttu-id="bd714-105">To nagranie można uruchomić w kontekście firmy demonstracyjnej USMF i użyć sugerowanych wartości.</span><span class="sxs-lookup"><span data-stu-id="bd714-105">You can run this recording in the USMF demo company and can use the suggested values.</span></span> <span data-ttu-id="bd714-106">Zazwyczaj ta procedura jest wykonywana przez pracownika ds. kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="bd714-106">Typically, this procedure is performed by a quality clerk.</span></span>  <span data-ttu-id="bd714-107">Warunkiem wstępnym jest przejście nagrania zadania „Sprawdzenie jakości towarów”.</span><span class="sxs-lookup"><span data-stu-id="bd714-107">As a prerequisite, run the “Inspect the quality of goods” task recording.</span></span> <span data-ttu-id="bd714-108">Aby wykonać zatwierdzenie niezgodności, użytkownik, który uruchomił nagranie zadania, musi mieć przypisaną wartość „Nazwa” na stronie Użytkownicy.</span><span class="sxs-lookup"><span data-stu-id="bd714-108">To process the approval of a nonconformance, the user who runs the task recording must have a “Name” value assigned on the Users page.</span></span> <span data-ttu-id="bd714-109">Aby korzystać z notatek do dokumentu, użytkownik musi mieć również włączoną funkcję Obsługa dokumentu w opcjach użytkownika.</span><span class="sxs-lookup"><span data-stu-id="bd714-109">To use the document notes, the user must also have Document handling activated in the user options.</span></span>


## <a name="select-a-quality-order"></a><span data-ttu-id="bd714-110">Wybieranie zlecenia kontroli jakości</span><span class="sxs-lookup"><span data-stu-id="bd714-110">Select a quality order</span></span>
1. <span data-ttu-id="bd714-111">Przejdź do okna Zlecenia kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="bd714-111">Go to Quality orders.</span></span>
2. <span data-ttu-id="bd714-112">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="bd714-112">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="bd714-113">Wybierz zlecenie kontroli jakości utworzone w nagraniu zadania „Sprawdzenie jakości towarów”.</span><span class="sxs-lookup"><span data-stu-id="bd714-113">Select the quality order that was created from the "Inspect the quality of goods" task recording.</span></span>  

## <a name="create-a-nonconformance"></a><span data-ttu-id="bd714-114">Tworzenie rekordu niezgodności</span><span class="sxs-lookup"><span data-stu-id="bd714-114">Create a nonconformance</span></span>
1. <span data-ttu-id="bd714-115">Kliknij przycisk Informacje.</span><span class="sxs-lookup"><span data-stu-id="bd714-115">Click Inquiries.</span></span>
2. <span data-ttu-id="bd714-116">Kliknij opcję Niezgodności.</span><span class="sxs-lookup"><span data-stu-id="bd714-116">Click Non conformances.</span></span>
3. <span data-ttu-id="bd714-117">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="bd714-117">Click New.</span></span>
4. <span data-ttu-id="bd714-118">W polu Typ problemu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="bd714-118">In the Problem type field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="bd714-119">Wybierz problem, który został znaleziony podczas procesu inspekcji.</span><span class="sxs-lookup"><span data-stu-id="bd714-119">Select the problem that was found during the inspection process.</span></span>  
5. <span data-ttu-id="bd714-120">W polu Typ problemu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="bd714-120">In the Problem type field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="bd714-121">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="bd714-121">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="bd714-122">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="bd714-122">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="bd714-123">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="bd714-123">Click OK.</span></span>

## <a name="approvereject-a-nonconformance"></a><span data-ttu-id="bd714-124">Zatwierdzanie/odrzucanie rekordu niezgodności</span><span class="sxs-lookup"><span data-stu-id="bd714-124">Approve/reject a nonconformance</span></span>
1. <span data-ttu-id="bd714-125">Kliknij przycisk Funkcje.</span><span class="sxs-lookup"><span data-stu-id="bd714-125">Click Functions.</span></span>
2. <span data-ttu-id="bd714-126">Kliknij opcję Zatwierdź niezgodność.</span><span class="sxs-lookup"><span data-stu-id="bd714-126">Click Approve non conformance.</span></span>
    * <span data-ttu-id="bd714-127">W tym przykładzie zatwierdź niezgodność.</span><span class="sxs-lookup"><span data-stu-id="bd714-127">For this example, approve the nonconformance.</span></span> <span data-ttu-id="bd714-128">Zatwierdzone niezgodności można skojarzyć z powiązanymi operacjami w celu zarejestrowania pracy wykonywanej w ramach postępowania z niezgodnością oraz, tak jak w tym nagraniu zadanie, w ramach przetwarzania korekty.</span><span class="sxs-lookup"><span data-stu-id="bd714-128">Approved nonconformances can be associated with related operations to record work that is done as part of the nonconformance handling and, as in this task recording, the processing of correction handling.</span></span>  
3. <span data-ttu-id="bd714-129">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="bd714-129">Click Yes.</span></span>

## <a name="create-a-correction-action"></a><span data-ttu-id="bd714-130">Tworzenie działania naprawczego</span><span class="sxs-lookup"><span data-stu-id="bd714-130">Create a correction action</span></span>
1. <span data-ttu-id="bd714-131">Kliknij opcję Korekty.</span><span class="sxs-lookup"><span data-stu-id="bd714-131">Click Corrections.</span></span>
2. <span data-ttu-id="bd714-132">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="bd714-132">Click New.</span></span>
3. <span data-ttu-id="bd714-133">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="bd714-133">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="bd714-134">W polu Numer pracownika kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="bd714-134">In the Personnel number field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="bd714-135">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="bd714-135">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="bd714-136">Kliknij opcję Wybierz.</span><span class="sxs-lookup"><span data-stu-id="bd714-136">Click Select.</span></span>
7. <span data-ttu-id="bd714-137">Kliknij opcję Dołącz.</span><span class="sxs-lookup"><span data-stu-id="bd714-137">Click Attach.</span></span>
    * <span data-ttu-id="bd714-138">Utwórz notatkę dotyczącą korekty.</span><span class="sxs-lookup"><span data-stu-id="bd714-138">Create a note about the correction.</span></span> <span data-ttu-id="bd714-139">W tym przykładzie działanie polega na skontaktowaniu się z dostawcą w celu omówienia przypadku niezgodności.</span><span class="sxs-lookup"><span data-stu-id="bd714-139">For this example, the action is to contact the vendor to discuss the nonconformance case.</span></span>  
8. <span data-ttu-id="bd714-140">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="bd714-140">Click New.</span></span>
9. <span data-ttu-id="bd714-141">Kliknij opcję Notatka.</span><span class="sxs-lookup"><span data-stu-id="bd714-141">Click Note.</span></span>
    * <span data-ttu-id="bd714-142">Należy zauważyć, że w zależności od konfiguracji raportu mogą być drukowane różne typy dokumentów towarzyszących, które są związane z zarządzaniem niezgodnościami.</span><span class="sxs-lookup"><span data-stu-id="bd714-142">Note that, depending on the report setup, different document types can be printed on the reports that are related to nonconformance management.</span></span>  
10. <span data-ttu-id="bd714-143">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="bd714-143">In the Description field, type a value.</span></span>
11. <span data-ttu-id="bd714-144">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="bd714-144">Close the page.</span></span>

## <a name="maintain-a-correction"></a><span data-ttu-id="bd714-145">Obsługa korekty</span><span class="sxs-lookup"><span data-stu-id="bd714-145">Maintain a correction</span></span>
1. <span data-ttu-id="bd714-146">Kliknij opcję Oznacz jako ukończone.</span><span class="sxs-lookup"><span data-stu-id="bd714-146">Click Mark complete.</span></span>
2. <span data-ttu-id="bd714-147">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="bd714-147">Click OK.</span></span>
3. <span data-ttu-id="bd714-148">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="bd714-148">Close the page.</span></span>

## <a name="close-a-nonconformance"></a><span data-ttu-id="bd714-149">Zamykanie rekordu niezgodności</span><span class="sxs-lookup"><span data-stu-id="bd714-149">Close a nonconformance</span></span>
1. <span data-ttu-id="bd714-150">Kliknij przycisk Funkcje.</span><span class="sxs-lookup"><span data-stu-id="bd714-150">Click Functions.</span></span>
2. <span data-ttu-id="bd714-151">Kliknij opcję Zamknij niezgodność.</span><span class="sxs-lookup"><span data-stu-id="bd714-151">Click Close non conformance.</span></span>
3. <span data-ttu-id="bd714-152">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="bd714-152">Click Yes.</span></span>
4. <span data-ttu-id="bd714-153">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="bd714-153">Close the page.</span></span>
5. <span data-ttu-id="bd714-154">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="bd714-154">Close the page.</span></span>
