---
title: Tworzenie propozycji amortyzacji
description: W tym temacie opisano sposób działania propozycji amortyzacji partii i wyjaśniono, jak proponować amortyzację dla środków trwałych.
author: abruer
manager: AnnBe
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 07337063c01f146c72ca6d9e0f9096907cdc9638
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142830"
---
# <a name="create-a-depreciation-proposal"></a><span data-ttu-id="c282f-103">Tworzenie propozycji amortyzacji</span><span class="sxs-lookup"><span data-stu-id="c282f-103">Create a depreciation proposal</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c282f-104">W tym temacie opisano sposób działania propozycji amortyzacji partii i wyjaśniono, jak proponować amortyzację dla środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="c282f-104">This topic describes how depreciation batch proposals work and explains how to propose depreciation for fixed assets.</span></span> <span data-ttu-id="c282f-105">Zadanie używa firmy demonstracyjnej USMF i roli Księgowy.</span><span class="sxs-lookup"><span data-stu-id="c282f-105">This task uses the USMF demo company and the accountant role.</span></span>


## <a name="create-a-depreciation-proposal"></a><span data-ttu-id="c282f-106">Tworzenie propozycji amortyzacji</span><span class="sxs-lookup"><span data-stu-id="c282f-106">Create a depreciation proposal</span></span>
1. <span data-ttu-id="c282f-107">W okienku nawigacji przejdź do **Moduły > Środki trwałe > Wpisy w arkuszu > Utwórz propozycję amortyzacji**.</span><span class="sxs-lookup"><span data-stu-id="c282f-107">In the navigation pane, go to **Modules > Fixed assets > Journal entries > Create depreciation proposal**.</span></span>
2. <span data-ttu-id="c282f-108">W polu **Nazwa arkusza** wybierz opcję z menu rozwijanego.</span><span class="sxs-lookup"><span data-stu-id="c282f-108">In the **Name of journal** field, select an option from the drop-down menu.</span></span>
3. <span data-ttu-id="c282f-109">Wprowadź datę w polu **Do dnia**.</span><span class="sxs-lookup"><span data-stu-id="c282f-109">In the **To date** field, enter a date.</span></span>

    - <span data-ttu-id="c282f-110">Wybierz opcję **Podsumowanie amortyzacji**, aby zsumować miesięczne amortyzacje w jednym wierszu arkusza.</span><span class="sxs-lookup"><span data-stu-id="c282f-110">Select the **Summarize depreciation** option to summarize monthly depreciations into one journal line.</span></span>  
    - <span data-ttu-id="c282f-111">Na przykład jeśli wartość pola Do dnia wynosi 31 marca 2015, zostanie wygenerowany następujący opis: „Amortyzacja od 31 stycznia 2015”.</span><span class="sxs-lookup"><span data-stu-id="c282f-111">For example, if the To date value is March 31, 2015, the following description is generated: "Depreciation since January 31, 2015."</span></span> <span data-ttu-id="c282f-112">Pole **Data** w proponowanych wierszach arkusza zostanie następnie ustawione na wartość 31 marca 2015 r.</span><span class="sxs-lookup"><span data-stu-id="c282f-112">The **Date** field on the proposed journal lines is then set to March 31, 2015.</span></span>  
    - <span data-ttu-id="c282f-113">Propozycję amortyzacji można filtrować według składników majątku, grup składników majątku lub innych kryteriów przy użyciu opcji **Filtruj**.</span><span class="sxs-lookup"><span data-stu-id="c282f-113">The depreciation proposal can be filtered by asset, asset group, or other criteria using the **Filter** option.</span></span>  
    - <span data-ttu-id="c282f-114">W przypadku używania formularza **Tworzenie propozycji nabycia lub amortyzacji środków trwałych** można zaproponować amortyzację partiami.</span><span class="sxs-lookup"><span data-stu-id="c282f-114">When you use the **Create acquisition or depreciation proposals for fixed assets** form, you can propose depreciation in batches.</span></span> <span data-ttu-id="c282f-115">Jest to zalecane dla większych propozycji, które zużywają więcej zasobów systemowych.</span><span class="sxs-lookup"><span data-stu-id="c282f-115">This is recommended for larger proposals that will use more system resources.</span></span> <span data-ttu-id="c282f-116">Jeśli zostanie wybrana opcja przetwarzania wsadowego, możliwe jest wykonywanie innych zadań w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="c282f-116">If you select the batch option, you can still complete other tasks during that time.</span></span> <span data-ttu-id="c282f-117">Gdy proponujesz amortyzację w ten sposób, amortyzacja jest obliczana dla modeli ewidencji środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="c282f-117">When you propose depreciation in this way, depreciation is calculated for value models for fixed assets.</span></span>  

4. <span data-ttu-id="c282f-118">Wybierz **Utwórz arkusz**.</span><span class="sxs-lookup"><span data-stu-id="c282f-118">Select **Create journal**.</span></span>

## <a name="review-depreciation-entries"></a><span data-ttu-id="c282f-119">Przeglądanie zapisów amortyzacji</span><span class="sxs-lookup"><span data-stu-id="c282f-119">Review depreciation entries</span></span>
1. <span data-ttu-id="c282f-120">W okienku nawigacji przejdź do **Moduły > Środki trwałe > Wpisy w arkuszu > Arkusz środków trwałych**.</span><span class="sxs-lookup"><span data-stu-id="c282f-120">In the navigation pane, go to **Modules > Fixed assets > Journal entries > Fixed assets journal**.</span></span>
2. <span data-ttu-id="c282f-121">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="c282f-121">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="c282f-122">Wybierz **Linie**.</span><span class="sxs-lookup"><span data-stu-id="c282f-122">Select **Lines**.</span></span>
4. <span data-ttu-id="c282f-123">Wybierz opcję **Zaksięguj**.</span><span class="sxs-lookup"><span data-stu-id="c282f-123">Select **Post**.</span></span>

