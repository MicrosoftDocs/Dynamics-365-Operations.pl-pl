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
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1572818"
---
# <a name="create-and-process-a-conformance"></a><span data-ttu-id="130c8-103">Tworzenie i przetwarzanie zgodności</span><span class="sxs-lookup"><span data-stu-id="130c8-103">Create and process a conformance</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="130c8-104">Ta procedura służy do zarządzania niezgodnościami na podstawie istniejącego zlecenia kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="130c8-104">Use this procedure to perform nonconformance management, based on an existing quality order.</span></span> <span data-ttu-id="130c8-105">To nagranie można uruchomić w kontekście firmy demonstracyjnej USMF i użyć sugerowanych wartości.</span><span class="sxs-lookup"><span data-stu-id="130c8-105">You can run this recording in the USMF demo company and can use the suggested values.</span></span> <span data-ttu-id="130c8-106">Zazwyczaj ta procedura jest wykonywana przez pracownika ds. kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="130c8-106">Typically, this procedure is performed by a quality clerk.</span></span>  <span data-ttu-id="130c8-107">Warunkiem wstępnym jest przejście nagrania zadania „Sprawdzenie jakości towarów”.</span><span class="sxs-lookup"><span data-stu-id="130c8-107">As a prerequisite, run the “Inspect the quality of goods” task recording.</span></span> <span data-ttu-id="130c8-108">Aby wykonać zatwierdzenie niezgodności, użytkownik, który uruchomił nagranie zadania, musi mieć przypisaną wartość „Nazwa” na stronie Użytkownicy.</span><span class="sxs-lookup"><span data-stu-id="130c8-108">To process the approval of a nonconformance, the user who runs the task recording must have a “Name” value assigned on the Users page.</span></span> <span data-ttu-id="130c8-109">Aby korzystać z notatek do dokumentu, użytkownik musi mieć również włączoną funkcję Obsługa dokumentu w opcjach użytkownika.</span><span class="sxs-lookup"><span data-stu-id="130c8-109">To use the document notes, the user must also have Document handling activated in the user options.</span></span>


## <a name="select-a-quality-order"></a><span data-ttu-id="130c8-110">Wybieranie zlecenia kontroli jakości</span><span class="sxs-lookup"><span data-stu-id="130c8-110">Select a quality order</span></span>
1. <span data-ttu-id="130c8-111">Przejdź do okna Zlecenia kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="130c8-111">Go to Quality orders.</span></span>
2. <span data-ttu-id="130c8-112">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="130c8-112">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="130c8-113">Wybierz zlecenie kontroli jakości utworzone w nagraniu zadania „Sprawdzenie jakości towarów”.</span><span class="sxs-lookup"><span data-stu-id="130c8-113">Select the quality order that was created from the "Inspect the quality of goods" task recording.</span></span>  

## <a name="create-a-nonconformance"></a><span data-ttu-id="130c8-114">Tworzenie rekordu niezgodności</span><span class="sxs-lookup"><span data-stu-id="130c8-114">Create a nonconformance</span></span>
1. <span data-ttu-id="130c8-115">Kliknij przycisk Informacje.</span><span class="sxs-lookup"><span data-stu-id="130c8-115">Click Inquiries.</span></span>
2. <span data-ttu-id="130c8-116">Kliknij opcję Niezgodności.</span><span class="sxs-lookup"><span data-stu-id="130c8-116">Click Non conformances.</span></span>
3. <span data-ttu-id="130c8-117">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="130c8-117">Click New.</span></span>
4. <span data-ttu-id="130c8-118">W polu Typ problemu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="130c8-118">In the Problem type field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="130c8-119">Wybierz problem, który został znaleziony podczas procesu inspekcji.</span><span class="sxs-lookup"><span data-stu-id="130c8-119">Select the problem that was found during the inspection process.</span></span>  
5. <span data-ttu-id="130c8-120">W polu Typ problemu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="130c8-120">In the Problem type field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="130c8-121">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="130c8-121">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="130c8-122">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="130c8-122">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="130c8-123">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="130c8-123">Click OK.</span></span>

## <a name="approvereject-a-nonconformance"></a><span data-ttu-id="130c8-124">Zatwierdzanie/odrzucanie rekordu niezgodności</span><span class="sxs-lookup"><span data-stu-id="130c8-124">Approve/reject a nonconformance</span></span>
1. <span data-ttu-id="130c8-125">Kliknij przycisk Funkcje.</span><span class="sxs-lookup"><span data-stu-id="130c8-125">Click Functions.</span></span>
2. <span data-ttu-id="130c8-126">Kliknij opcję Zatwierdź niezgodność.</span><span class="sxs-lookup"><span data-stu-id="130c8-126">Click Approve non conformance.</span></span>
    * <span data-ttu-id="130c8-127">W tym przykładzie zatwierdź niezgodność.</span><span class="sxs-lookup"><span data-stu-id="130c8-127">For this example, approve the nonconformance.</span></span> <span data-ttu-id="130c8-128">Zatwierdzone niezgodności można skojarzyć z powiązanymi operacjami w celu zarejestrowania pracy wykonywanej w ramach postępowania z niezgodnością oraz, tak jak w tym nagraniu zadanie, w ramach przetwarzania korekty.</span><span class="sxs-lookup"><span data-stu-id="130c8-128">Approved nonconformances can be associated with related operations to record work that is done as part of the nonconformance handling and, as in this task recording, the processing of correction handling.</span></span>  
3. <span data-ttu-id="130c8-129">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="130c8-129">Click Yes.</span></span>

## <a name="create-a-correction-action"></a><span data-ttu-id="130c8-130">Tworzenie działania naprawczego</span><span class="sxs-lookup"><span data-stu-id="130c8-130">Create a correction action</span></span>
1. <span data-ttu-id="130c8-131">Kliknij opcję Korekty.</span><span class="sxs-lookup"><span data-stu-id="130c8-131">Click Corrections.</span></span>
2. <span data-ttu-id="130c8-132">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="130c8-132">Click New.</span></span>
3. <span data-ttu-id="130c8-133">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="130c8-133">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="130c8-134">W polu Numer pracownika kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="130c8-134">In the Personnel number field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="130c8-135">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="130c8-135">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="130c8-136">Kliknij opcję Wybierz.</span><span class="sxs-lookup"><span data-stu-id="130c8-136">Click Select.</span></span>
7. <span data-ttu-id="130c8-137">Kliknij opcję Dołącz.</span><span class="sxs-lookup"><span data-stu-id="130c8-137">Click Attach.</span></span>
    * <span data-ttu-id="130c8-138">Utwórz notatkę dotyczącą korekty.</span><span class="sxs-lookup"><span data-stu-id="130c8-138">Create a note about the correction.</span></span> <span data-ttu-id="130c8-139">W tym przykładzie działanie polega na skontaktowaniu się z dostawcą w celu omówienia przypadku niezgodności.</span><span class="sxs-lookup"><span data-stu-id="130c8-139">For this example, the action is to contact the vendor to discuss the nonconformance case.</span></span>  
8. <span data-ttu-id="130c8-140">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="130c8-140">Click New.</span></span>
9. <span data-ttu-id="130c8-141">Kliknij opcję Notatka.</span><span class="sxs-lookup"><span data-stu-id="130c8-141">Click Note.</span></span>
    * <span data-ttu-id="130c8-142">Należy zauważyć, że w zależności od konfiguracji raportu mogą być drukowane różne typy dokumentów towarzyszących, które są związane z zarządzaniem niezgodnościami.</span><span class="sxs-lookup"><span data-stu-id="130c8-142">Note that, depending on the report setup, different document types can be printed on the reports that are related to nonconformance management.</span></span>  
10. <span data-ttu-id="130c8-143">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="130c8-143">In the Description field, type a value.</span></span>
11. <span data-ttu-id="130c8-144">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="130c8-144">Close the page.</span></span>

## <a name="maintain-a-correction"></a><span data-ttu-id="130c8-145">Obsługa korekty</span><span class="sxs-lookup"><span data-stu-id="130c8-145">Maintain a correction</span></span>
1. <span data-ttu-id="130c8-146">Kliknij opcję Oznacz jako ukończone.</span><span class="sxs-lookup"><span data-stu-id="130c8-146">Click Mark complete.</span></span>
2. <span data-ttu-id="130c8-147">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="130c8-147">Click OK.</span></span>
3. <span data-ttu-id="130c8-148">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="130c8-148">Close the page.</span></span>

## <a name="close-a-nonconformance"></a><span data-ttu-id="130c8-149">Zamykanie rekordu niezgodności</span><span class="sxs-lookup"><span data-stu-id="130c8-149">Close a nonconformance</span></span>
1. <span data-ttu-id="130c8-150">Kliknij przycisk Funkcje.</span><span class="sxs-lookup"><span data-stu-id="130c8-150">Click Functions.</span></span>
2. <span data-ttu-id="130c8-151">Kliknij opcję Zamknij niezgodność.</span><span class="sxs-lookup"><span data-stu-id="130c8-151">Click Close non conformance.</span></span>
3. <span data-ttu-id="130c8-152">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="130c8-152">Click Yes.</span></span>
4. <span data-ttu-id="130c8-153">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="130c8-153">Close the page.</span></span>
5. <span data-ttu-id="130c8-154">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="130c8-154">Close the page.</span></span>
