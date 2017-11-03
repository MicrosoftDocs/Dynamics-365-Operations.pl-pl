---
title: "Rozwiązywanie problemów z budżetowaniem stanowisk"
description: "Ten artykuł zawiera odpowiedzi na pytania, które mogą się pojawić podczas konfigurowania budżetowania stanowisk. Odpowiada na często zadawane pytania na temat tworzenia składników kosztu budżetowego, grup wynagrodzeń i siatek wynagrodzeń."
author: ryansandness
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: HcmBudgetPurposeType, HcmPositionForecast
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 88253
ms.assetid: c44df01b-8700-4022-b4c6-c4b1cb84d31d
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: f2ef04008a5e6339a2193f9fcc77f2e0e6643557
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="position-budgeting-troubleshooting"></a><span data-ttu-id="ad07b-104">Rozwiązywanie problemów z budżetowaniem stanowisk</span><span class="sxs-lookup"><span data-stu-id="ad07b-104">Position budgeting troubleshooting</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="ad07b-105">Ten artykuł zawiera odpowiedzi na pytania, które mogą się pojawić podczas konfigurowania budżetowania stanowisk.</span><span class="sxs-lookup"><span data-stu-id="ad07b-105">This article provides answers to questions that you might have when you configure position budgeting.</span></span> <span data-ttu-id="ad07b-106">Odpowiada na często zadawane pytania na temat tworzenia składników kosztu budżetowego, grup wynagrodzeń i siatek wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="ad07b-106">It addresses frequently asked questions about how to create budget cost elements, compensation groups, and compensation grids.</span></span> 

<a name="why-cant-i-find-the-forecast-position-page-in-human-resources"></a><span data-ttu-id="ad07b-107">Dlaczego nie można odnaleźć strony stanowiska podlegającego prognozie w module Zasoby ludzkie?</span><span class="sxs-lookup"><span data-stu-id="ad07b-107">Why can’t I find the forecast position page in Human resources?</span></span>
---------------------------------------------------------------

<span data-ttu-id="ad07b-108">Stanowiska podlegające prognozie zostały przeniesione do moduł Budżetowanie.</span><span class="sxs-lookup"><span data-stu-id="ad07b-108">Forecast positions have been moved to Budgeting.</span></span>

## <a name="why-cant-i-delete-a-budget-cost-element"></a><span data-ttu-id="ad07b-109">Dlaczego nie można usunąć składnika kosztu budżetowego?</span><span class="sxs-lookup"><span data-stu-id="ad07b-109">Why can’t I delete a budget cost element?</span></span>
<span data-ttu-id="ad07b-110">Nie można usunąć składnika kosztu budżetowego, który jest przypisany do stanowiska podlegającego prognozie.</span><span class="sxs-lookup"><span data-stu-id="ad07b-110">You can’t delete a budget cost element that is assigned to a forecast position.</span></span> <span data-ttu-id="ad07b-111">Aby można było usunąć składnik kosztu budżetowego, należy go wykasować ze wszystkich stanowisk podlegających prognozie.</span><span class="sxs-lookup"><span data-stu-id="ad07b-111">Before you can delete a budget cost element, you must remove it from all forecast positions.</span></span> <span data-ttu-id="ad07b-112">**Porada:** Aby znaleźć wszystkie stanowiska, do których przypisano składnik kosztu budżetowego, zaznacz składnik kosztu na stronie **Składniki kosztu budżetowego** , a następnie kliknij przycisk **Aktualizuj stanowiska**.</span><span class="sxs-lookup"><span data-stu-id="ad07b-112">**Tip:** To find all the positions that a budget cost element is assigned to, select the cost element on the **Budget cost elements** page, and then click **Update positions**.</span></span> <span data-ttu-id="ad07b-113">Stanowiska, które używają składnika kosztu, znajdują się w górnej siatce.</span><span class="sxs-lookup"><span data-stu-id="ad07b-113">The positions that use the cost element are listed in the upper grid.</span></span>

## <a name="how-can-i-remove-a-cost-element-from-multiple-forecast-positions-without-opening-each-one"></a><span data-ttu-id="ad07b-114">Jak można usunąć składnik kosztu z wielu stanowisk podlegających prognozie bez konieczności otwierania każdego z nich?</span><span class="sxs-lookup"><span data-stu-id="ad07b-114">How can I remove a cost element from multiple forecast positions without opening each one?</span></span>
<span data-ttu-id="ad07b-115">Nie można usunąć składnika kosztu.</span><span class="sxs-lookup"><span data-stu-id="ad07b-115">You can’t remove a cost element.</span></span> <span data-ttu-id="ad07b-116">Jednak jeśli zmienisz daty rozpoczęcia i zakończenia, tak aby przypadały poza datami cyklu planowania budżetu, składnik kosztu nie będzie już przypisany do stanowisk podlegających prognozie w tym cyklu planowania budżetu.</span><span class="sxs-lookup"><span data-stu-id="ad07b-116">However, if you change the start and end dates so that they are outside the budget planning cycle dates, the cost element will no longer be assigned to the forecast positions in that budget planning cycle.</span></span> <span data-ttu-id="ad07b-117">Aby wprowadzić tę zmianę, otwórz składnik kosztu budżetowego, a następnie na skróconej karcie **Obliczanie kosztów** kliknij przycisk **Zmień daty** i zmień datę wejścia w życie lub datę ważności.</span><span class="sxs-lookup"><span data-stu-id="ad07b-117">To make this change, open the budget cost element, and then, on the **Cost calculation** FastTab, click **Change dates**, and change the effective date or expiration date.</span></span> <span data-ttu-id="ad07b-118">Następnie kliknij przycisk **OK**, co spowoduje automatyczną aktualizację wszystkich stanowisk podlegających prognozie, do których jest przypisany ten składnik kosztu.</span><span class="sxs-lookup"><span data-stu-id="ad07b-118">Then click **OK** to automatically update all forecast positions that the cost element is assigned to.</span></span> <span data-ttu-id="ad07b-119">**Porada:** Korzystając z tej metody, należy pamiętać, że usunie ona składnik kosztu budżetowego ze **wszystkich** stanowisk podlegających prognozie, w których daty rozpoczęcia i zakończenia nie przypadają już w odpowiednim przedziale.</span><span class="sxs-lookup"><span data-stu-id="ad07b-119">**Tip:** If you use this method, be aware that it removes the budget cost element from **all** forecast positions where the start and end dates are no longer within the appropriate range.</span></span> <span data-ttu-id="ad07b-120">Jeśli ten efekt jest niepożądany, trzeba otworzyć każde stanowisko podlegające prognozie, z którego chcesz usunąć składnik kosztu budżetowego, i ręcznie wprowadzić zmianę.</span><span class="sxs-lookup"><span data-stu-id="ad07b-120">If this effect isn't what you intend, you must open each forecast position that you want to remove the budget cost element from and manually make the change.</span></span>

## <a name="why-cant-i-enter-an-annual-amount-on-the-cost-calculation-fasttab-for-the-budget-cost-element"></a><span data-ttu-id="ad07b-121">Dlaczego nie można wprowadzić kwoty rocznej na skróconej karcie Obliczanie kosztów dla składnika kosztu budżetowego?</span><span class="sxs-lookup"><span data-stu-id="ad07b-121">Why can’t I enter an annual amount on the Cost calculation FastTab for the budget cost element?</span></span>
<span data-ttu-id="ad07b-122">Nie można wprowadzić kwoty rocznej, jeśli na skróconej karcie **Podstawa obliczania** istnieją składniki kosztu budżetowego, ponieważ system wymaga wartości procentowej do obliczenia wartości kwotowej.</span><span class="sxs-lookup"><span data-stu-id="ad07b-122">You can’t enter an annual amount if there are budget cost elements on the **Calculation basis** FastTab, because the system requires a percentage in order to calculate the value.</span></span> <span data-ttu-id="ad07b-123">Aby zmienić tę wartość, usuń wszystkie składniki kosztu budżetowego ze skróconej karty **Podstawa obliczania**.</span><span class="sxs-lookup"><span data-stu-id="ad07b-123">To change the value, remove all budget cost elements from the **Calculation basis** FastTab.</span></span>

## <a name="why-cant-i-change-the-budget-cost-type-from-earning-to-another-budget-cost-type"></a><span data-ttu-id="ad07b-124">Dlaczego nie można zmienić typu kosztu budżetowego z „zarobki” na inny typ kosztu budżetowego?</span><span class="sxs-lookup"><span data-stu-id="ad07b-124">Why can’t I change the budget cost type from earning to another budget cost type?</span></span>
<span data-ttu-id="ad07b-125">Niektóre składniki kosztu budżetowego używają składnika kosztu „zarobki” jako podstawy obliczeń.</span><span class="sxs-lookup"><span data-stu-id="ad07b-125">Some budget cost elements use the earning cost element as a calculation basis.</span></span> <span data-ttu-id="ad07b-126">Aby zmienić wartość w polu **Typ kosztu budżetowego**, usuń składnik kosztu „zarobki” ze skróconej karty **Podstawa obliczania** we wszystkich składnikach kosztów budżetowych.</span><span class="sxs-lookup"><span data-stu-id="ad07b-126">To change the **Budget cost type** field, remove the earning cost element from the **Calculation basis** FastTab of all budget cost elements.</span></span>

## <a name="why-cant-i-change-the-date-on-budget-cost-element-lines-for-a-budget-cost-element"></a><span data-ttu-id="ad07b-127">Dlaczego nie można zmienić daty w wierszach składnika kosztu budżegowego dla składnika kosztu budżetowego?</span><span class="sxs-lookup"><span data-stu-id="ad07b-127">Why can’t I change the date on budget cost element lines for a budget cost element?</span></span>
<span data-ttu-id="ad07b-128">Nie można zmienić daty w wierszu składnika kosztu budżetowego, gdy składnik kosztu budżetowego jest używany przez stanowisko podlegające prognozie.</span><span class="sxs-lookup"><span data-stu-id="ad07b-128">You can’t change the date on the budget cost element line when a budget cost element is used by a forecast position.</span></span> <span data-ttu-id="ad07b-129">To ograniczenie pomaga zagwarantować, że stanowiska podlegające prognozie są zawsze zgodne z wytycznymi dla składnika kosztu budżetowego.</span><span class="sxs-lookup"><span data-stu-id="ad07b-129">This limitation helps guarantee that the forecast positions are always within the guidelines of the budget cost element.</span></span> <span data-ttu-id="ad07b-130">Aby zmienić tę datę, na skróconej karcie **Obliczanie kosztów** kliknij przycisk **Zmień daty** i wprowadź nowe daty.</span><span class="sxs-lookup"><span data-stu-id="ad07b-130">To change the date, on the **Cost calculation** FastTab, click **Change dates**, and enter the new dates.</span></span> <span data-ttu-id="ad07b-131">Następnie kliknij przycisk **OK**, co spowoduje aktualizację stanowisk, do których jest przypisany ten składnik kosztu.</span><span class="sxs-lookup"><span data-stu-id="ad07b-131">Then click **OK** to update the positions that the cost element is assigned to.</span></span>

## <a name="why-cant-i-change-the-costs-for-a-budget-cost-element-on-the-compensation-group-page"></a><span data-ttu-id="ad07b-132">Dlaczego nie można zmienić kosztów dla składnika kosztu budżetowego na stronie Grupa wynagrodzeń?</span><span class="sxs-lookup"><span data-stu-id="ad07b-132">Why can’t I change the costs for a budget cost element on the Compensation group page?</span></span>
<span data-ttu-id="ad07b-133">Składniki kosztu budżetowego można tworzyć i modyfikować tylko na stronie **Składniki kosztu budżetowego**.</span><span class="sxs-lookup"><span data-stu-id="ad07b-133">You can create and change budget cost elements only on the **Budget cost elements** page.</span></span>

## <a name="why-do-i-receive-an-error-message-when-i-change-the-dates-for-a-cost-element-on-a-forecast-position"></a><span data-ttu-id="ad07b-134">Dlaczego widzę komunikat o błędzie po zmianie dat w składniku kosztu dla stanowiska podlegającego prognozie?</span><span class="sxs-lookup"><span data-stu-id="ad07b-134">Why do I receive an error message when I change the dates for a cost element on a forecast position?</span></span>
<span data-ttu-id="ad07b-135">Daty w wierszu składnika kosztu stanowiska podlegającego prognozie muszą się zawierać w następujących zakresach:</span><span class="sxs-lookup"><span data-stu-id="ad07b-135">The dates on the forecast position cost element line must be within the following ranges:</span></span>

-   <span data-ttu-id="ad07b-136">Daty aktywacji i przejścia na emeryturę stanowiska.</span><span class="sxs-lookup"><span data-stu-id="ad07b-136">The activation and retirement dates of the position.</span></span>
-   <span data-ttu-id="ad07b-137">Daty aktywacji i ważności składnika kosztu budżetowego.</span><span class="sxs-lookup"><span data-stu-id="ad07b-137">The activation and expiration dates of the budget cost element.</span></span>
-   <span data-ttu-id="ad07b-138">Daty początkowa i końcowa cyklu budżetu skojarzonego z procesem planowania budżetu dla stanowiska podlegającego prognozie.</span><span class="sxs-lookup"><span data-stu-id="ad07b-138">The start and end dates of the budget cycle that is associated with the budget planning process of the forecast position.</span></span>





