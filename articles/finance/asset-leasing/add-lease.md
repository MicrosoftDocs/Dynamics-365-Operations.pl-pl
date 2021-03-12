---
title: Dodaj lub kopiuj wynajmy (podgląd)
description: W tym temacie opisano sposób tworzenia nowego wynajmu przez wprowadzenie informacji jego dotyczących w Wynajem składnika majątku lub przez skopiowanie informacji z istniejącego wynajmu.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: abbf04d009a4b347792cd8b317e334da2a4cbbee
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969610"
---
# <a name="add-or-copy-leases-preview"></a><span data-ttu-id="0529c-103">Dodaj lub kopiuj wynajmy (podgląd)</span><span class="sxs-lookup"><span data-stu-id="0529c-103">Add or copy leases (Preview)</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0529c-104">W tym temacie wyjaśniono, jak utworzyć wynajem od podstaw w Wynajem składnika majątku, a także jak utworzyć wynajem, kopiując istniejący wynajem.</span><span class="sxs-lookup"><span data-stu-id="0529c-104">This topic explains how to create a lease from scratch in Asset leasing, and also how to create a lease by copying an existing lease.</span></span> <span data-ttu-id="0529c-105">Proces tworzenia wynajmu od podstaw obejmuje wprowadzenie informacji dotyczących nowego wynajmu, a następnie utworzenie harmonogramu wynajmu.</span><span class="sxs-lookup"><span data-stu-id="0529c-105">The process for creating a lease from scratch involves entering information for the new lease and then creating a lease schedule.</span></span> <span data-ttu-id="0529c-106">Po skonfigurowaniu co najmniej jednego wynajmu może okazać się łatwiejsze skopiowanie informacji z istniejącego wynajmu, a następnie edytowanie tych informacji w razie konieczności utworzenia nowego wynajmu.</span><span class="sxs-lookup"><span data-stu-id="0529c-106">After at least one lease has been set up, you might find it easier to copy the information from an existing lease and then edit that information as you require to create a new lease.</span></span>

## <a name="create-a-lease"></a><span data-ttu-id="0529c-107">Tworzenie wynajmu</span><span class="sxs-lookup"><span data-stu-id="0529c-107">Create a lease</span></span>

<span data-ttu-id="0529c-108">Aby utworzyć wynajem w Wynajem składnika majątku, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="0529c-108">Follow these steps to create a lease in Asset leasing.</span></span>

1. <span data-ttu-id="0529c-109">Na stronie **Podsumowanie wynajmu**, w okienku akcji, wybierz **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="0529c-109">On the **Lease summary** page, on the Action Pane, select **New**.</span></span>
2. <span data-ttu-id="0529c-110">Wpisz informacje o wynajmie.</span><span class="sxs-lookup"><span data-stu-id="0529c-110">Enter the lease information.</span></span> <span data-ttu-id="0529c-111">Wymagane pola mają czerwone obramowanie.</span><span class="sxs-lookup"><span data-stu-id="0529c-111">Fields that are required have red borders.</span></span>

## <a name="create-a-lease-schedule"></a><span data-ttu-id="0529c-112">Tworzenie harmonogramu wynajmu</span><span class="sxs-lookup"><span data-stu-id="0529c-112">Create a lease schedule</span></span>

<span data-ttu-id="0529c-113">Po zakończeniu wprowadzania informacji dotyczących wynajmu należy wykonać poniższe kroki w celu utworzenia harmonogramu wynajmu.</span><span class="sxs-lookup"><span data-stu-id="0529c-113">After you've finished entering information for the lease, follow these steps to create a lease schedule.</span></span>

> [!NOTE]
> <span data-ttu-id="0529c-114">Wymiary finansowe mogą się zmieniać w zależności od niestandardowych wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="0529c-114">The financial dimensions might change based on any custom financial dimensions.</span></span>

1. <span data-ttu-id="0529c-115">Wybierz opcję **Utwórz harmonogramy**, aby wygenerować księgi wynajmu.</span><span class="sxs-lookup"><span data-stu-id="0529c-115">Select **Create schedules** to generate the lease books.</span></span> <span data-ttu-id="0529c-116">Księgi wynajmu obejmują harmonogramy wydatków, amortyzacji i płatności.</span><span class="sxs-lookup"><span data-stu-id="0529c-116">The lease books include the payment, amortization, depreciation, and expense schedules.</span></span>
2. <span data-ttu-id="0529c-117">Aby uzyskać dostęp do ksiąg wynajmu i wyświetlić nowo utworzone harmonogramy, wybierz kartę **Księgi**.</span><span class="sxs-lookup"><span data-stu-id="0529c-117">To access the lease books and view the newly created schedules, select the **Books** tab.</span></span>

    <span data-ttu-id="0529c-118">Strona **Szczegóły księgi** pokazuje, w jaki sposób wynajem jest księgowany w przypisanych do niego księgach.</span><span class="sxs-lookup"><span data-stu-id="0529c-118">The **Book details** page shows how the lease is accounted for by the books that have been allocated to it.</span></span> <span data-ttu-id="0529c-119">W tym miejscu można przejrzeć harmonogramy wynajmu.</span><span class="sxs-lookup"><span data-stu-id="0529c-119">From here, you can view the lease schedules.</span></span>

    <span data-ttu-id="0529c-120">Harmonogram płatności zawiera dane wejściowe z karty **Wiersze harmonogramu płatności** na stronie **Dodaj wynajem**.</span><span class="sxs-lookup"><span data-stu-id="0529c-120">The payment schedule contains the inputs from the **Payment schedule lines** tab on the **Add lease** page.</span></span> <span data-ttu-id="0529c-121">Nadal można zmienić każdą kwotę płatności i opłaty zmienne.</span><span class="sxs-lookup"><span data-stu-id="0529c-121">You can still change each payment amount and variable payment.</span></span> <span data-ttu-id="0529c-122">Zobowiązanie z tytułu wynajmu jest obliczane na podstawie zmodyfikowanego harmonogramu płatności.</span><span class="sxs-lookup"><span data-stu-id="0529c-122">The lease liability is calculated based on the modified payment schedule.</span></span>

4. <span data-ttu-id="0529c-123">Po przejrzeniu harmonogramu płatności wybierz pozycję **Potwierdź harmonogram**.</span><span class="sxs-lookup"><span data-stu-id="0529c-123">After you've finished reviewing the payment schedule, select **Confirm schedule**.</span></span> <span data-ttu-id="0529c-124">Po potwierdzeniu harmonogramu wynajem nie będzie już dostępny do edycji.</span><span class="sxs-lookup"><span data-stu-id="0529c-124">After the schedule is confirmed, the lease is no longer available for editing.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0529c-125">System automatycznie obliczy okres wynajmu na podstawie wierszy harmonogramu płatności na stronie **Dodaj wynajem**.</span><span class="sxs-lookup"><span data-stu-id="0529c-125">The system automatically calculates the lease term from the payment schedule lines on the **Add lease** page.</span></span>
    >
    > <span data-ttu-id="0529c-126">Aby obliczyć okres wynajmu w miesiącach, system wyszukuje różnicę między datą początkową a datą końcową określonego wiersza harmonogramu płatności.</span><span class="sxs-lookup"><span data-stu-id="0529c-126">To calculate the lease term in months, the system finds the difference between the start date and the end date for a specific payment schedule line.</span></span> <span data-ttu-id="0529c-127">Następnie następuje przejście do następnego wiersza harmonogramu płatności i ponowne obliczenie różnicy.</span><span class="sxs-lookup"><span data-stu-id="0529c-127">It then moves to the next payment schedule line and finds the difference again.</span></span> <span data-ttu-id="0529c-128">Na koniec system sumuje wszystkie kwoty, aby określić okres wynajmu w miesiącach.</span><span class="sxs-lookup"><span data-stu-id="0529c-128">Finally, the system sums all the amounts to determine the lease term in months.</span></span>

5. <span data-ttu-id="0529c-129">Aby wyświetlić obliczone okresowe koszty odsetek, otwórz stronę **Harmonogram amortyzacji zobowiązań**.</span><span class="sxs-lookup"><span data-stu-id="0529c-129">To view the calculated period interest expenses, open the **Liability amortization schedule** page.</span></span> <span data-ttu-id="0529c-130">Aby wyświetlić obliczoną amortyzację liniową, otwórz stronę **Harmonogram amortyzacji składników majątku**.</span><span class="sxs-lookup"><span data-stu-id="0529c-130">To view calculated straight-line depreciation, open the **Asset depreciation schedule** page.</span></span>
6. <span data-ttu-id="0529c-131">Po przejrzeniu obliczonej kwoty można utworzyć wpis w arkuszu początkowego rozpoznania na stronie **Początkowe rozpoznawanie**.</span><span class="sxs-lookup"><span data-stu-id="0529c-131">After you've finished reviewing the calculated amount, you can create the initial recognition journal entry on the **Initial recognition** page.</span></span> <span data-ttu-id="0529c-132">Zostanie wyświetlony komunikat informujący o utworzeniu arkusza.</span><span class="sxs-lookup"><span data-stu-id="0529c-132">You receive a message that states that the journal has been created.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0529c-133">Wpis w arkuszu nie jest publikowany w księdze głównej, dopóki nie zostanie zaksięgowany ręcznie.</span><span class="sxs-lookup"><span data-stu-id="0529c-133">The journal entry isn't posted to General ledger until you manually post the entry.</span></span>

7. <span data-ttu-id="0529c-134">Aby przejrzeć proponowany wpis początkowego rozpoznania przed zaksięgowaniem go, wybierz **Arkusze wynajmu składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="0529c-134">To review the proposed initial recognition entry before you post it, select **Asset leasing journal**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0529c-135">Nie można ręcznie utworzyć Arkusza wynajmu składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="0529c-135">The Asset leasing journal can't be created manually.</span></span> <span data-ttu-id="0529c-136">Jest on tworzony automatycznie podczas tworzenia harmonogramów wynajmu.</span><span class="sxs-lookup"><span data-stu-id="0529c-136">It's automatically created when lease schedules are created.</span></span>

8. <span data-ttu-id="0529c-137">Aby zaksięgować wpis w arkuszu początkowego rozpoznania po jego przejrzeniu, należy wybrać opcję **Zaksięguj** w celu opublikowania składnika majątku z PDU i zobowiązania z tytułu wynajmu w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="0529c-137">When you've finished reviewing the initial recognition journal entry and are ready to post it, select **Post** to recognize the right-of-use (ROU) asset and lease liability in General ledger.</span></span>

## <a name="copy-a-lease"></a><span data-ttu-id="0529c-138">Kopiowanie wynajmu</span><span class="sxs-lookup"><span data-stu-id="0529c-138">Copy a lease</span></span>

<span data-ttu-id="0529c-139">Wynajem składników majątku umożliwia kopiowanie szczegółów wynajmu w celu utworzenia nowego wynajmu mającego takie same informacje.</span><span class="sxs-lookup"><span data-stu-id="0529c-139">Asset leasing lets you copy the details of a lease to create a new lease that has the same information.</span></span> <span data-ttu-id="0529c-140">Następnie można zmienić pola wynajmu przed utworzeniem harmonogramów dla kopiowanego wynajmu.</span><span class="sxs-lookup"><span data-stu-id="0529c-140">You can then change the lease fields before you create the schedules for the copied lease.</span></span>

1. <span data-ttu-id="0529c-141">Na stronie **Podsumowanie wynajmu** wybierz wynajem do skopiowania, a następnie w okienku akcji wybierz opcję **Kopiuj wynajem**.</span><span class="sxs-lookup"><span data-stu-id="0529c-141">On the **Lease summary** page, select the lease to copy, and then, on the Action Pane, select **Copy lease**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0529c-142">Jeśli parametr **Ręczny** jest wyłączony dla sekwencji numerów dla identyfikatorów wynajmów, kolejny numer w sekwencji jest automatycznie generowany jako identyfikator wynajmu dla kopiowanego wynajmu.</span><span class="sxs-lookup"><span data-stu-id="0529c-142">If the **Manual** parameter is turned off for the number sequence for lease IDs, the next number in the sequence is automatically generated as the lease ID of the copied lease.</span></span> <span data-ttu-id="0529c-143">Jeśli parametr **Ręczny** jest włączony, zostanie wyświetlony komunikat z monitem o wprowadzenie identyfikatora wynajmu, zanim będzie można kontynuować kopiowanie wynajmu.</span><span class="sxs-lookup"><span data-stu-id="0529c-143">If the **Manual** parameter is turned on, you receive a message that prompts you to enter the lease ID before you proceed to copy the lease.</span></span>

2. <span data-ttu-id="0529c-144">Wybierz opcję **Kopiuj**.</span><span class="sxs-lookup"><span data-stu-id="0529c-144">Select **Copy**.</span></span> <span data-ttu-id="0529c-145">Szczegóły wynajmu z wybranego wynajmu są kopiowane do nowego wynajmu.</span><span class="sxs-lookup"><span data-stu-id="0529c-145">The lease details from the selected lease are copied to a new lease.</span></span> <span data-ttu-id="0529c-146">Szczegóły nowego wynajmu można zmodyfikować przed jego zapisaniem i utworzeniem harmonogramów wynajmu.</span><span class="sxs-lookup"><span data-stu-id="0529c-146">You can then edit the details of the new lease before you save it and create the lease schedules.</span></span>

## <a name="asset-leasing-journal"></a><span data-ttu-id="0529c-147">Arkusz wynajmu składnika majątku</span><span class="sxs-lookup"><span data-stu-id="0529c-147">Asset leasing journal</span></span>

<span data-ttu-id="0529c-148">Wszystkie wpisy w arkuszu, które są tworzone w module Wynajem składnika majątku, są zawarte w arkuszu wynajmu składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="0529c-148">All journal entries that are created in Asset leasing are contained in the Asset leasing journal.</span></span> <span data-ttu-id="0529c-149">Na stronie **Arkusz wynajmu składnika majątku** (**Wynajem składnika majątku \> Wpisy w arkuszu \> Arkusz wynajmu składnika majątku**) można filtrować według stanu zaksięgowania, wyświetlać określone wpisy w arkuszu i załączniki oraz księgować niezaksięgowane wpisy w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="0529c-149">On the **Asset leasing journal** page (**Asset leasing \> Journal entries \> Asset leasing journal**), you can filter by posting status, view specific journal entries and the vouchers, and post unposted journal entries.</span></span>

> [!NOTE]
> <span data-ttu-id="0529c-150">Nie można ręcznie utworzyć Arkusza wynajmu składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="0529c-150">The Asset leasing journal can't be created manually.</span></span> <span data-ttu-id="0529c-151">Jest on tworzony automatycznie podczas tworzenia harmonogramów wynajmu.</span><span class="sxs-lookup"><span data-stu-id="0529c-151">It's automatically created when lease schedules are created.</span></span>
