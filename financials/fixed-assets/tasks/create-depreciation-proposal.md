--- 
title: Tworzenie propozycji amortyzacji
description: "W tej procedurze opisano sposób działania propozycji amortyzacji partii i wyjaśniono, jak proponować amortyzację dla środków trwałych."
author: saraschi2
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
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 07d8cf2f1c46b99dfcd1d7c3419fe835f37c5a02
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-depreciation-proposal"></a><span data-ttu-id="5a91b-103">Tworzenie propozycji amortyzacji</span><span class="sxs-lookup"><span data-stu-id="5a91b-103">Create a depreciation proposal</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5a91b-104">W tej procedurze opisano sposób działania propozycji amortyzacji partii i wyjaśniono, jak proponować amortyzację dla środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="5a91b-104">This procedure describes how depreciation batch proposals work and explains how to propose depreciation for fixed assets.</span></span> <span data-ttu-id="5a91b-105">Zadanie używa firmy demonstracyjnej USMF i roli Księgowy.</span><span class="sxs-lookup"><span data-stu-id="5a91b-105">This task uses the USMF demo company and the accountant role.</span></span>


## <a name="create-depreciation-proposal"></a><span data-ttu-id="5a91b-106">Utwórz propozycję amortyzacji</span><span class="sxs-lookup"><span data-stu-id="5a91b-106">Create depreciation proposal</span></span>
1. <span data-ttu-id="5a91b-107">Wybierz kolejno opcje Środki trwałe > Wpisy w arkuszu > Utwórz propozycję amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="5a91b-107">Go to Fixed assets > Journal entries > Create depreciation proposal.</span></span>
2. <span data-ttu-id="5a91b-108">W polu Nazwa arkusza kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="5a91b-108">In the Name of journal field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="5a91b-109">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="5a91b-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="5a91b-110">Wprowadź datę w polu Do dnia.</span><span class="sxs-lookup"><span data-stu-id="5a91b-110">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="5a91b-111">Wybierz opcję Podsumowanie amortyzacji, aby zsumować miesięczne amortyzacje w jednym wierszu arkusza.</span><span class="sxs-lookup"><span data-stu-id="5a91b-111">Select the Summarize depreciation option to summarize monthly depreciations into one journal line.</span></span>  
    * <span data-ttu-id="5a91b-112">Na przykład jeśli wartość pola Do dnia wynosi 31 marca 2015, zostanie wygenerowany następujący opis: „Amortyzacja od 31 stycznia 2015”.</span><span class="sxs-lookup"><span data-stu-id="5a91b-112">For example, if the To date value is March 31, 2015, the following description is generated: “Depreciation since January 31, 2015.”</span></span> <span data-ttu-id="5a91b-113">Pole Data w proponowanych wierszach arkusza zostanie następnie ustawione na wartość 31 marca 2015.</span><span class="sxs-lookup"><span data-stu-id="5a91b-113">The Date field on the proposed journal lines is then set to March 31, 2015.</span></span>  
    * <span data-ttu-id="5a91b-114">Propozycję amortyzacji można filtrować według składników aktywów, grup składników aktywów lub innych kryteriów przy użyciu opcji Filtr.</span><span class="sxs-lookup"><span data-stu-id="5a91b-114">The depreciation proposal can be filtered by asset, asset group, or other criteria using the Filter option.</span></span>  
    * <span data-ttu-id="5a91b-115">W przypadku używania formularza Tworzenie propozycji nabycia lub amortyzacji środków trwałych można zaproponować amortyzację partiami.</span><span class="sxs-lookup"><span data-stu-id="5a91b-115">When you use the Create acquisition or depreciation proposals for fixed assets form, you can propose depreciation in batches.</span></span> <span data-ttu-id="5a91b-116">Jest to zalecane dla większych propozycji, które zużywają więcej zasobów systemowych.</span><span class="sxs-lookup"><span data-stu-id="5a91b-116">This is recommended for larger proposals that will use more system resources.</span></span> <span data-ttu-id="5a91b-117">Jeśli zostanie wybrana opcja przetwarzania wsadowego, możliwe jest wykonywanie innych zadań w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="5a91b-117">If you select the batch option, you can still complete other tasks during that time.</span></span> <span data-ttu-id="5a91b-118">Gdy proponujesz amortyzację w ten sposób, amortyzacja jest obliczana dla modeli ewidencji środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="5a91b-118">When you propose depreciation in this way, depreciation is calculated for value models for fixed assets.</span></span>  
5. <span data-ttu-id="5a91b-119">Kliknij opcję Utwórz arkusz.</span><span class="sxs-lookup"><span data-stu-id="5a91b-119">Click Create journal.</span></span>

## <a name="review-depreciation-entries"></a><span data-ttu-id="5a91b-120">Przeglądanie zapisów amortyzacji</span><span class="sxs-lookup"><span data-stu-id="5a91b-120">Review depreciation entries</span></span>
1. <span data-ttu-id="5a91b-121">Wybierz kolejno opcje Środki trwałe > Wpisy w arkuszu > Arkusz środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="5a91b-121">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>
2. <span data-ttu-id="5a91b-122">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="5a91b-122">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="5a91b-123">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="5a91b-123">Click Lines.</span></span>
4. <span data-ttu-id="5a91b-124">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="5a91b-124">Click Post.</span></span>


