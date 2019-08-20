---
title: Określanie sposobu likwidacji zwróconych towarów
description: Można określić sposób likwidacji zwróconych towarów.
author: ShylaThompson
manager: AnnBe
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6991fc04f5015fc3d604306e9327a5e551e728db
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2019
ms.locfileid: "1743079"
---
# <a name="specify-how-to-dispose-of-returned-items"></a><span data-ttu-id="28427-103">Określanie sposobu likwidacji zwróconych towarów</span><span class="sxs-lookup"><span data-stu-id="28427-103">Specify how to dispose of returned items</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="28427-104">Podczas obsługi zamówienia zwrotu należy określić kod przyczyny zwrotu wskazujący powód zwracania produktu.</span><span class="sxs-lookup"><span data-stu-id="28427-104">When you handle a return order, you must specify a reason return code to identify why the product is being returned.</span></span> <span data-ttu-id="28427-105">Należy także określić kod dyspozycji i akcję dyspozycji, aby określić, co należy zrobić ze zwracanym produktem.</span><span class="sxs-lookup"><span data-stu-id="28427-105">You must also specify a disposition code and a disposition action to determine what should be done with the returned product itself.</span></span>

<span data-ttu-id="28427-106">Kod dyspozycji można zastosować po utworzeniu zamówienia zwrotu, zarejestrowaniu przyjęcia towaru lub zaktualizowaniu dokumentu dostawy dla przyjęcia towaru oraz zakończeniu zlecenia kwarantanny.</span><span class="sxs-lookup"><span data-stu-id="28427-106">A disposition code can be applied when you create the return order, register item arrival or packing-slip update an item arrival, and end a quarantine order.</span></span>

<span data-ttu-id="28427-107">Można definiować dowolne kody dyspozycji potrzebne w celu obsługi procesów biznesowych.</span><span class="sxs-lookup"><span data-stu-id="28427-107">You can define any disposition codes that you need in order to support the business processes.</span></span> <span data-ttu-id="28427-108">W poniższej tabeli przedstawiono zestaw często używanych kodów służących do przypisywania dyspozycji zwrotu towaru.</span><span class="sxs-lookup"><span data-stu-id="28427-108">The following table provides a set of typically used codes to assign return-item disposition.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="28427-109">Typ dyspozycji</span><span class="sxs-lookup"><span data-stu-id="28427-109">Disposition type</span></span></p></th>
<th><p><span data-ttu-id="28427-110">Typowy kod</span><span class="sxs-lookup"><span data-stu-id="28427-110">Common code</span></span></p></th>
<th><p><span data-ttu-id="28427-111">opis</span><span class="sxs-lookup"><span data-stu-id="28427-111">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="28427-112">Likwidacja</span><span class="sxs-lookup"><span data-stu-id="28427-112">Disposal</span></span></p></td>
<td><p><span data-ttu-id="28427-113">LZ</span><span class="sxs-lookup"><span data-stu-id="28427-113">SC</span></span></p></td>
<td><p><span data-ttu-id="28427-114">Likwidacja/zniszczenie</span><span class="sxs-lookup"><span data-stu-id="28427-114">Scrap/Destroy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28427-115">Likwidacja</span><span class="sxs-lookup"><span data-stu-id="28427-115">Disposal</span></span></p></td>
<td><p><span data-ttu-id="28427-116">PCD</span><span class="sxs-lookup"><span data-stu-id="28427-116">DC</span></span></p></td>
<td><p><span data-ttu-id="28427-117">Przekazanie na cele dobroczynne</span><span class="sxs-lookup"><span data-stu-id="28427-117">Donate to Charity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28427-118">Likwidacja</span><span class="sxs-lookup"><span data-stu-id="28427-118">Disposal</span></span></p></td>
<td><p><span data-ttu-id="28427-119">LFZ</span><span class="sxs-lookup"><span data-stu-id="28427-119">TD</span></span></p></td>
<td><p><span data-ttu-id="28427-120">Likwidacja przez firmę zewnętrzną</span><span class="sxs-lookup"><span data-stu-id="28427-120">Third-Party Disposal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28427-121">Likwidacja</span><span class="sxs-lookup"><span data-stu-id="28427-121">Disposal</span></span></p></td>
<td><p><span data-ttu-id="28427-122">OD</span><span class="sxs-lookup"><span data-stu-id="28427-122">SL</span></span></p></td>
<td><p><span data-ttu-id="28427-123">Odzysk</span><span class="sxs-lookup"><span data-stu-id="28427-123">Salvage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28427-124">Likwidacja</span><span class="sxs-lookup"><span data-stu-id="28427-124">Disposal</span></span></p></td>
<td><p><span data-ttu-id="28427-125">SFZ</span><span class="sxs-lookup"><span data-stu-id="28427-125">TS</span></span></p></td>
<td><p><span data-ttu-id="28427-126">Sprzedaż przez firmę zewnętrzną (rynki wtórne)</span><span class="sxs-lookup"><span data-stu-id="28427-126">Third-Party Sale (Secondary Markets)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28427-127">Naprawa/modyfikacja</span><span class="sxs-lookup"><span data-stu-id="28427-127">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="28427-128">PR</span><span class="sxs-lookup"><span data-stu-id="28427-128">RW</span></span></p></td>
<td><p><span data-ttu-id="28427-129">Przeróbka</span><span class="sxs-lookup"><span data-stu-id="28427-129">Rework</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28427-130">Naprawa/modyfikacja</span><span class="sxs-lookup"><span data-stu-id="28427-130">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="28427-131">PPO</span><span class="sxs-lookup"><span data-stu-id="28427-131">RF</span></span></p></td>
<td><p><span data-ttu-id="28427-132">Ponowna produkcja/odnowienie</span><span class="sxs-lookup"><span data-stu-id="28427-132">Remanufacture/Refurbish</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28427-133">Naprawa/modyfikacja</span><span class="sxs-lookup"><span data-stu-id="28427-133">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="28427-134">MD</span><span class="sxs-lookup"><span data-stu-id="28427-134">MD</span></span></p></td>
<td><p><span data-ttu-id="28427-135">Modyfikacja</span><span class="sxs-lookup"><span data-stu-id="28427-135">Modify</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28427-136">Naprawa/modyfikacja</span><span class="sxs-lookup"><span data-stu-id="28427-136">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="28427-137">NP</span><span class="sxs-lookup"><span data-stu-id="28427-137">RP</span></span></p></td>
<td><p><span data-ttu-id="28427-138">Naprawa</span><span class="sxs-lookup"><span data-stu-id="28427-138">Repair</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28427-139">Naprawa/modyfikacja</span><span class="sxs-lookup"><span data-stu-id="28427-139">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="28427-140">ZD</span><span class="sxs-lookup"><span data-stu-id="28427-140">RV</span></span></p></td>
<td><p><span data-ttu-id="28427-141">Zwrot do dostawcy</span><span class="sxs-lookup"><span data-stu-id="28427-141">Return to Vendor</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28427-142">Inne</span><span class="sxs-lookup"><span data-stu-id="28427-142">Other</span></span></p></td>
<td><p><span data-ttu-id="28427-143">UOP</span><span class="sxs-lookup"><span data-stu-id="28427-143">AI</span></span></p></td>
<td><p><span data-ttu-id="28427-144">Zastosowanie w obecnej postaci</span><span class="sxs-lookup"><span data-stu-id="28427-144">Use as is</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28427-145">Inne</span><span class="sxs-lookup"><span data-stu-id="28427-145">Other</span></span></p></td>
<td><p><span data-ttu-id="28427-146">OS</span><span class="sxs-lookup"><span data-stu-id="28427-146">RS</span></span></p></td>
<td><p><span data-ttu-id="28427-147">Odsprzedaż</span><span class="sxs-lookup"><span data-stu-id="28427-147">Resale</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28427-148">Inne</span><span class="sxs-lookup"><span data-stu-id="28427-148">Other</span></span></p></td>
<td><p><span data-ttu-id="28427-149">WM</span><span class="sxs-lookup"><span data-stu-id="28427-149">EX</span></span></p></td>
<td><p><span data-ttu-id="28427-150">Import/eksport</span><span class="sxs-lookup"><span data-stu-id="28427-150">Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28427-151">Inne</span><span class="sxs-lookup"><span data-stu-id="28427-151">Other</span></span></p></td>
<td><p><span data-ttu-id="28427-152">RN</span><span class="sxs-lookup"><span data-stu-id="28427-152">MS</span></span></p></td>
<td><p><span data-ttu-id="28427-153">Różne</span><span class="sxs-lookup"><span data-stu-id="28427-153">Miscellaneous</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="28427-154">Dla każdego zdefiniowanego kodu dyspozycji musisz wybrać akcję dyspozycji.</span><span class="sxs-lookup"><span data-stu-id="28427-154">For each disposition code that you define, you must select a disposition action.</span></span> <span data-ttu-id="28427-155">Akcja dyspozycji określa fizyczne i finansowe następstwa kodów dyspozycji.</span><span class="sxs-lookup"><span data-stu-id="28427-155">The disposition action determines the physical and financial implications of the disposition codes.</span></span> <span data-ttu-id="28427-156">Na przykład akcja dyspozycji określa fizyczną obsługę zwróconego towaru, skutek finansowy zwrotu towarów i czy towar zastępczy musi zostać wysłany do odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="28427-156">For example, the disposition action determines the physical handling of the returned item, the financial effect of the returned item, and if a replacement item must be sent to the customer.</span></span> <span data-ttu-id="28427-157">Można zdefiniować nieograniczoną liczbę kodów dyspozycji zależnie od potrzeb biznesowych, ale są tylko sześć wstępnie zdefiniowanych akcji dyspozycji, z których można wybierać.</span><span class="sxs-lookup"><span data-stu-id="28427-157">You can define an unlimited number of disposition codes according to your business needs, but there are only six predefined disposition actions that you can select from.</span></span> <span data-ttu-id="28427-158">Poniższa tabela zawiera akcje dyspozycji i ich definicje.</span><span class="sxs-lookup"><span data-stu-id="28427-158">The following table provides the disposition actions and their definitions.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="28427-159">Akcja dyspozycji</span><span class="sxs-lookup"><span data-stu-id="28427-159">Disposition action</span></span></p></th>
<th><p><span data-ttu-id="28427-160">opis</span><span class="sxs-lookup"><span data-stu-id="28427-160">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="28427-161"><strong>Strona kredytowa</strong></span><span class="sxs-lookup"><span data-stu-id="28427-161"><strong>Credit</strong></span></span></p></td>
<td><p><span data-ttu-id="28427-162">Zwracanie towaru do magazynu i kredyt dla odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="28427-162">Return the item to inventory and credit the customer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28427-163"><strong>Tylko kredytowe</strong></span><span class="sxs-lookup"><span data-stu-id="28427-163"><strong>Credit only</strong></span></span></p></td>
<td><p><span data-ttu-id="28427-164">Kredyt dla odbiorcy bez wymagań lub oczekiwań zwrotu towaru.</span><span class="sxs-lookup"><span data-stu-id="28427-164">Credit the customer without requiring or expecting the item to be returned.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28427-165"><strong>Odpadki</strong></span><span class="sxs-lookup"><span data-stu-id="28427-165"><strong>Scrap</strong></span></span></p></td>
<td><p><span data-ttu-id="28427-166">Uznanie towaru za odpad i kredyt dla odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="28427-166">Scrap the item and credit the customer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28427-167"><strong>Zastąp i zaksięguj po stronie kredytowej</strong></span><span class="sxs-lookup"><span data-stu-id="28427-167"><strong>Replace and credit</strong></span></span></p></td>
<td><p><span data-ttu-id="28427-168">Zwraca towar do magazynu, tworzenie zamówienie wymiany i kredyt dla odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="28427-168">Return the item to inventory, create a replacement order, and credit the customer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28427-169"><strong>Zastąp i zlikwiduj</strong></span><span class="sxs-lookup"><span data-stu-id="28427-169"><strong>Replace and scrap</strong></span></span></p></td>
<td><p><span data-ttu-id="28427-170">Przeznaczenie towaru na odpadki, tworzenie zamówienia wymiany i kredyt dla odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="28427-170">Scrap the item, create a replacement order, and credit the customer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28427-171"><strong>Zwrot do odbiorcy</strong></span><span class="sxs-lookup"><span data-stu-id="28427-171"><strong>Return to customer</strong></span></span></p></td>
<td><p><span data-ttu-id="28427-172">Odrzucenie zwróconego towaru i zwrócenie go do odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="28427-172">Reject the returned item and return it to the customer.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="select-a-disposition-code-for-a-quarantine-order"></a><span data-ttu-id="28427-173">Wybieranie kodu dyspozycji dla zlecenia kwarantanny</span><span class="sxs-lookup"><span data-stu-id="28427-173">Select a disposition code for a quarantine order</span></span>

1.  <span data-ttu-id="28427-174">Kliknij kolejno opcje **Zarządzanie zapasami** \> **Okresowe** \> **Zarządzanie jakością** \> **Zlecenia kwarantanny**.</span><span class="sxs-lookup"><span data-stu-id="28427-174">Click **Inventory management** \> **Periodic** \> **Quality management** \> **Quarantine orders**.</span></span>

2.  <span data-ttu-id="28427-175">Dla istniejącego zlecenia kwarantanny wybierz akcję w polu **Kod dyspozycji** na karcie **Przegląd**.</span><span class="sxs-lookup"><span data-stu-id="28427-175">For an existing quarantine order, select an action from the **Disposition code** field on the **Overview** tab.</span></span>



## <a name="see-also"></a><span data-ttu-id="28427-176">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="28427-176">See also</span></span>

<span data-ttu-id="28427-177">[Zlecenie kwarantanny (formularz)](https://technet.microsoft.com/library/aa554073(v=ax.60))</span><span class="sxs-lookup"><span data-stu-id="28427-177">[Quarantine order (form)](https://technet.microsoft.com/library/aa554073(v=ax.60))</span></span>

<span data-ttu-id="28427-178">[Kody dyspozycji (formularz)](https://technet.microsoft.com/library/hh597113\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="28427-178">[Disposition codes (form)](https://technet.microsoft.com/library/hh597113\(v=ax.60\))</span></span>

  


