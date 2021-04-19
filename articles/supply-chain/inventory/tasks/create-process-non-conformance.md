---
title: Tworzenie i przetwarzanie zgodności
description: Ten temat pokazuje jak przeprowadzić zarządzanie niezgodnościami na podstawie istniejącego zlecenia kontroli jakości.
author: perlynne
ms.date: 08/07/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c4f7e61adf37e74bdb082270b689cf0375ccc7f7
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833960"
---
# <a name="create-and-process-a-conformance"></a><span data-ttu-id="0aa48-103">Tworzenie i przetwarzanie zgodności</span><span class="sxs-lookup"><span data-stu-id="0aa48-103">Create and process a conformance</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0aa48-104">Ten temat pokazuje jak przeprowadzić zarządzanie niezgodnościami na podstawie istniejącego zlecenia kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="0aa48-104">This topic explains how to perform nonconformance management, based on an existing quality order.</span></span> <span data-ttu-id="0aa48-105">To nagranie można uruchomić w kontekście firmy demonstracyjnej USMF i użyć sugerowanych wartości.</span><span class="sxs-lookup"><span data-stu-id="0aa48-105">You can run this recording in the USMF demo company and can use the suggested values.</span></span> <span data-ttu-id="0aa48-106">Zazwyczaj ta procedura jest wykonywana przez pracownika ds. kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="0aa48-106">Typically, this procedure is performed by a quality clerk.</span></span>  <span data-ttu-id="0aa48-107">Warunkiem wstępnym jest ukończenie instrukcji w [Sprawdzanie jakości towarów](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md).</span><span class="sxs-lookup"><span data-stu-id="0aa48-107">As a prerequisite, complete the instructions in [Inspect the quality of goods](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md).</span></span> <span data-ttu-id="0aa48-108">Aby wykonać zatwierdzenie niezgodności, użytkownik, który uruchomił nagranie zadania, musi mieć przypisaną wartość „Nazwa” na stronie Użytkownicy.</span><span class="sxs-lookup"><span data-stu-id="0aa48-108">To process the approval of a nonconformance, the user who runs the task recording must have a "Name" value assigned on the Users page.</span></span> <span data-ttu-id="0aa48-109">Aby korzystać z notatek do dokumentu, użytkownik musi mieć również włączoną funkcję Obsługa dokumentu w opcjach użytkownika.</span><span class="sxs-lookup"><span data-stu-id="0aa48-109">To use the document notes, the user must also have Document handling activated in the user options.</span></span>


## <a name="select-a-quality-order"></a><span data-ttu-id="0aa48-110">Wybieranie zlecenia kontroli jakości</span><span class="sxs-lookup"><span data-stu-id="0aa48-110">Select a quality order</span></span>
1. <span data-ttu-id="0aa48-111">W okienku nawigacji otwórz **Moduły > Zarządzanie zapasami > Zadania okresowe > Zarządzanie jakością > Zlecenia kontroli jakości**.</span><span class="sxs-lookup"><span data-stu-id="0aa48-111">In the navigation pane, go to **Modules > Inventory management > Periodic tasks > Quality management > Quality orders**.</span></span>
2. <span data-ttu-id="0aa48-112">Na liście wybierz zlecenie kontroli jakości, które zostało stworzone w [Sprawdzanie jakości towarów](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md).</span><span class="sxs-lookup"><span data-stu-id="0aa48-112">In the list, select the quality order that was created in [Inspect the quality of goods](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md).</span></span>  

## <a name="create-a-nonconformance"></a><span data-ttu-id="0aa48-113">Tworzenie rekordu niezgodności</span><span class="sxs-lookup"><span data-stu-id="0aa48-113">Create a nonconformance</span></span>
1. <span data-ttu-id="0aa48-114">W okienku akcji wybierz pozycję **Zapytania**.</span><span class="sxs-lookup"><span data-stu-id="0aa48-114">On the Action Pane, select **Inquiries**.</span></span>
2. <span data-ttu-id="0aa48-115">Wybierz **Niezgodności**.</span><span class="sxs-lookup"><span data-stu-id="0aa48-115">Select **Non conformances**.</span></span>
3. <span data-ttu-id="0aa48-116">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="0aa48-116">Select **New**.</span></span>
4. <span data-ttu-id="0aa48-117">W menu rozwijanym pola **Typ problemu** wybierz problem, który został znaleziony podczas procesu inspekcji.</span><span class="sxs-lookup"><span data-stu-id="0aa48-117">In the drop-down menu of the **Problem type** field, select the problem that was found during the inspection process.</span></span>  
5. <span data-ttu-id="0aa48-118">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="0aa48-118">Select **OK**.</span></span>

## <a name="approvereject-a-nonconformance"></a><span data-ttu-id="0aa48-119">Zatwierdzanie/odrzucanie rekordu niezgodności</span><span class="sxs-lookup"><span data-stu-id="0aa48-119">Approve/reject a nonconformance</span></span>
1. <span data-ttu-id="0aa48-120">Wybierz **Funkcje**.</span><span class="sxs-lookup"><span data-stu-id="0aa48-120">Select **Functions**.</span></span>
2. <span data-ttu-id="0aa48-121">Wybierz **Zatwierdź niezgodność**.</span><span class="sxs-lookup"><span data-stu-id="0aa48-121">Select **Approve non conformance**.</span></span> <span data-ttu-id="0aa48-122">W tym przykładzie zatwierdź niezgodność.</span><span class="sxs-lookup"><span data-stu-id="0aa48-122">For this example, approve the nonconformance.</span></span> <span data-ttu-id="0aa48-123">Zatwierdzone niezgodności można skojarzyć z powiązanymi operacjami w celu zarejestrowania pracy wykonywanej w ramach postępowania z niezgodnością oraz, tak jak w tym temacie, przetwarzanie korekty.</span><span class="sxs-lookup"><span data-stu-id="0aa48-123">Approved nonconformances can be associated with related operations to record work that is done as part of the nonconformance handling and, as in this topic, the processing of correction handling.</span></span>  
3. <span data-ttu-id="0aa48-124">Wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="0aa48-124">Select **Yes**.</span></span>

## <a name="create-a-correction-action"></a><span data-ttu-id="0aa48-125">Tworzenie działania naprawczego</span><span class="sxs-lookup"><span data-stu-id="0aa48-125">Create a correction action</span></span>
1. <span data-ttu-id="0aa48-126">Wybierz **Korekty**.</span><span class="sxs-lookup"><span data-stu-id="0aa48-126">Select **Corrections**.</span></span>
2. <span data-ttu-id="0aa48-127">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="0aa48-127">Select **New**.</span></span>
3. <span data-ttu-id="0aa48-128">W polu **Numer pracownika** nowego wiersza wybierz żądany rekord z menu rozwijanego.</span><span class="sxs-lookup"><span data-stu-id="0aa48-128">In the **Personnel number** field of the new row, select the desired record from the drop down menu.</span></span>
4. <span data-ttu-id="0aa48-129">Kliknij opcję **Wybierz**.</span><span class="sxs-lookup"><span data-stu-id="0aa48-129">Click **Select**.</span></span>
5. <span data-ttu-id="0aa48-130">Wybierz **Dołącz**.</span><span class="sxs-lookup"><span data-stu-id="0aa48-130">Select **Attach**.</span></span> <span data-ttu-id="0aa48-131">Utwórz notatkę dotyczącą korekty.</span><span class="sxs-lookup"><span data-stu-id="0aa48-131">Create a note about the correction.</span></span> <span data-ttu-id="0aa48-132">W tym przykładzie działanie polega na skontaktowaniu się z dostawcą w celu omówienia przypadku niezgodności.</span><span class="sxs-lookup"><span data-stu-id="0aa48-132">For this example, the action is to contact the vendor to discuss the nonconformance case.</span></span>  
6. <span data-ttu-id="0aa48-133">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="0aa48-133">Select **New**.</span></span>
7. <span data-ttu-id="0aa48-134">Wybierz **Uwaga**.</span><span class="sxs-lookup"><span data-stu-id="0aa48-134">Select **Note**.</span></span> <span data-ttu-id="0aa48-135">Należy zauważyć, że w zależności od konfiguracji raportu mogą być drukowane różne typy dokumentów na raportach, które są związane z zarządzaniem niezgodnościami.</span><span class="sxs-lookup"><span data-stu-id="0aa48-135">Depending on the report setup, different document types can be printed on the reports that are related to nonconformance management.</span></span>  
8. <span data-ttu-id="0aa48-136">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0aa48-136">In the **Description** field, type a value.</span></span>
9. <span data-ttu-id="0aa48-137">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="0aa48-137">Close the page.</span></span>

## <a name="maintain-a-correction"></a><span data-ttu-id="0aa48-138">Obsługa korekty</span><span class="sxs-lookup"><span data-stu-id="0aa48-138">Maintain a correction</span></span>
1. <span data-ttu-id="0aa48-139">Wybierz opcję **Oznacz jako ukończone**.</span><span class="sxs-lookup"><span data-stu-id="0aa48-139">Select **Mark complete**.</span></span>
2. <span data-ttu-id="0aa48-140">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="0aa48-140">Select **OK**.</span></span>
3. <span data-ttu-id="0aa48-141">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="0aa48-141">Close the page.</span></span>

## <a name="close-a-nonconformance"></a><span data-ttu-id="0aa48-142">Zamykanie rekordu niezgodności</span><span class="sxs-lookup"><span data-stu-id="0aa48-142">Close a nonconformance</span></span>
1. <span data-ttu-id="0aa48-143">Wybierz **Funkcje**.</span><span class="sxs-lookup"><span data-stu-id="0aa48-143">Select **Functions**.</span></span>
2. <span data-ttu-id="0aa48-144">Wybierz **Zamknij tę niezgodność**.</span><span class="sxs-lookup"><span data-stu-id="0aa48-144">Select **Close non conformance**.</span></span>
3. <span data-ttu-id="0aa48-145">Wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="0aa48-145">Select **Yes**.</span></span>
4. <span data-ttu-id="0aa48-146">Zamknij strony.</span><span class="sxs-lookup"><span data-stu-id="0aa48-146">Close the pages.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]