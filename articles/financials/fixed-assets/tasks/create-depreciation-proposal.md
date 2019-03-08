---
title: Utwórz propozycję amortyzacji
description: W tej procedurze opisano sposób działania propozycji amortyzacji partii i wyjaśniono, jak proponować amortyzację dla środków trwałych.
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d11554ee5f26ef5a85e799194d2f75757a31c254
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "361298"
---
# <a name="create-depreciation-proposal"></a><span data-ttu-id="bd05d-103">Utwórz propozycję amortyzacji</span><span class="sxs-lookup"><span data-stu-id="bd05d-103">Create depreciation proposal</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bd05d-104">W tej procedurze opisano sposób działania propozycji amortyzacji partii i wyjaśniono, jak proponować amortyzację dla środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="bd05d-104">This procedure describes how depreciation batch proposals work and explains how to propose depreciation for fixed assets.</span></span> <span data-ttu-id="bd05d-105">Zadanie używa firmy demonstracyjnej USMF i roli Księgowy.</span><span class="sxs-lookup"><span data-stu-id="bd05d-105">This task uses the USMF demo company and the accountant role.</span></span>


## <a name="create-depreciation-proposal"></a><span data-ttu-id="bd05d-106">Utwórz propozycję amortyzacji</span><span class="sxs-lookup"><span data-stu-id="bd05d-106">Create depreciation proposal</span></span>
1. <span data-ttu-id="bd05d-107">Wybierz kolejno opcje Środki trwałe > Wpisy w arkuszu > Utwórz propozycję amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="bd05d-107">Go to Fixed assets > Journal entries > Create depreciation proposal.</span></span>
2. <span data-ttu-id="bd05d-108">W polu Nazwa arkusza kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="bd05d-108">In the Name of journal field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="bd05d-109">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="bd05d-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="bd05d-110">Wprowadź datę w polu Do dnia.</span><span class="sxs-lookup"><span data-stu-id="bd05d-110">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="bd05d-111">Wybierz opcję Podsumowanie amortyzacji, aby zsumować miesięczne amortyzacje w jednym wierszu arkusza.</span><span class="sxs-lookup"><span data-stu-id="bd05d-111">Select the Summarize depreciation option to summarize monthly depreciations into one journal line.</span></span>  
    * <span data-ttu-id="bd05d-112">Na przykład jeśli wartość pola Do dnia wynosi 31 marca 2015, zostanie wygenerowany następujący opis: „Amortyzacja od 31 stycznia 2015”.</span><span class="sxs-lookup"><span data-stu-id="bd05d-112">For example, if the To date value is March 31, 2015, the following description is generated: “Depreciation since January 31, 2015.”</span></span> <span data-ttu-id="bd05d-113">Pole Data w proponowanych wierszach arkusza zostanie następnie ustawione na wartość 31 marca 2015.</span><span class="sxs-lookup"><span data-stu-id="bd05d-113">The Date field on the proposed journal lines is then set to March 31, 2015.</span></span>  
    * <span data-ttu-id="bd05d-114">Propozycję amortyzacji można filtrować według składników aktywów, grup składników aktywów lub innych kryteriów przy użyciu opcji Filtr.</span><span class="sxs-lookup"><span data-stu-id="bd05d-114">The depreciation proposal can be filtered by asset, asset group, or other criteria using the Filter option.</span></span>  
    * <span data-ttu-id="bd05d-115">W przypadku używania formularza Tworzenie propozycji nabycia lub amortyzacji środków trwałych można zaproponować amortyzację partiami.</span><span class="sxs-lookup"><span data-stu-id="bd05d-115">When you use the Create acquisition or depreciation proposals for fixed assets form, you can propose depreciation in batches.</span></span> <span data-ttu-id="bd05d-116">Jest to zalecane dla większych propozycji, które zużywają więcej zasobów systemowych.</span><span class="sxs-lookup"><span data-stu-id="bd05d-116">This is recommended for larger proposals that will use more system resources.</span></span> <span data-ttu-id="bd05d-117">Jeśli zostanie wybrana opcja przetwarzania wsadowego, możliwe jest wykonywanie innych zadań w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="bd05d-117">If you select the batch option, you can still complete other tasks during that time.</span></span> <span data-ttu-id="bd05d-118">Gdy proponujesz amortyzację w ten sposób, amortyzacja jest obliczana dla modeli ewidencji środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="bd05d-118">When you propose depreciation in this way, depreciation is calculated for value models for fixed assets.</span></span>  
5. <span data-ttu-id="bd05d-119">Kliknij opcję Utwórz arkusz.</span><span class="sxs-lookup"><span data-stu-id="bd05d-119">Click Create journal.</span></span>

## <a name="review-depreciation-entries"></a><span data-ttu-id="bd05d-120">Przeglądanie zapisów amortyzacji</span><span class="sxs-lookup"><span data-stu-id="bd05d-120">Review depreciation entries</span></span>
1. <span data-ttu-id="bd05d-121">Wybierz kolejno opcje Środki trwałe > Wpisy w arkuszu > Arkusz środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="bd05d-121">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>
2. <span data-ttu-id="bd05d-122">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="bd05d-122">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="bd05d-123">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="bd05d-123">Click Lines.</span></span>
4. <span data-ttu-id="bd05d-124">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="bd05d-124">Click Post.</span></span>

