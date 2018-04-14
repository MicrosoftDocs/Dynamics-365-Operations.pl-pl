--- 
title: "Ustawianie kodów podatków"
description: "Kody podatków tworzy się dla każdego podatku pośredniego lub cła, które firma musi naliczać, pobierać i wpłacać do urzędu skarbowego."
author: twheeloc
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
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 987e28f1e1af32a25015999c0b1b55757938bc56
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---
# <a name="set-up-sales-tax-codes"></a><span data-ttu-id="0cf38-103">Ustawianie kodów podatków</span><span class="sxs-lookup"><span data-stu-id="0cf38-103">Set up sales tax codes</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0cf38-104">Kody podatków tworzy się dla każdego podatku pośredniego lub cła, które firma musi naliczać, pobierać i wpłacać do urzędu skarbowego.</span><span class="sxs-lookup"><span data-stu-id="0cf38-104">Sales tax codes are created for every indirect tax or duty that the legal entity is obligated to calculate, collect, and pay to sales tax authorities.</span></span>

<span data-ttu-id="0cf38-105">W zadaniu wykorzystano firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="0cf38-105">This task uses the USMF demo company.</span></span>



1. <span data-ttu-id="0cf38-106">Wybierz kolejno opcje Podatek > Podatki pośrednie > Podatek > Kody podatków.</span><span class="sxs-lookup"><span data-stu-id="0cf38-106">Go to Tax > Indirect taxes > Sales tax > Sales tax codes.</span></span>
2. <span data-ttu-id="0cf38-107">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="0cf38-107">Click New.</span></span>
3. <span data-ttu-id="0cf38-108">W polu Kod podatku wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0cf38-108">In the Sales tax code field, type a value.</span></span>
4. <span data-ttu-id="0cf38-109">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0cf38-109">In the Name field, type a value.</span></span>
5. <span data-ttu-id="0cf38-110">Wybierz okres rozliczenia, aby określić, do którego urzędu skarbowego i w których interwałach ten podatek musi być zgłaszany i płacony.</span><span class="sxs-lookup"><span data-stu-id="0cf38-110">Select a Settlement period to specify which Sales tax authority and in which intervals this sales tax needs to be reported and paid.</span></span>
6. <span data-ttu-id="0cf38-111">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="0cf38-111">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="0cf38-112">Wybierz grupę księgowania, aby określić konta główne w Księdze głównej, na których będzie księgowany podatek.</span><span class="sxs-lookup"><span data-stu-id="0cf38-112">Select a Ledger posting group to specify the main accounts to post sales tax to the general ledger.</span></span>
8. <span data-ttu-id="0cf38-113">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="0cf38-113">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="0cf38-114">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="0cf38-114">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="0cf38-115">Rozwiń skróconą kartę Obliczanie.</span><span class="sxs-lookup"><span data-stu-id="0cf38-115">Expand the Calculation FastTab.</span></span>
    * <span data-ttu-id="0cf38-116">Skrócona karta Obliczanie zawiera wiele pól, które kontrolują sposób obliczania kwot podatków.</span><span class="sxs-lookup"><span data-stu-id="0cf38-116">The Calculation FastTab has multiple fields that control how sales tax amounts will be calculated.</span></span>  
11. <span data-ttu-id="0cf38-117">W okienku akcji kliknij opcję Kod podatku.</span><span class="sxs-lookup"><span data-stu-id="0cf38-117">On the Action Pane, click Sales tax code.</span></span>
12. <span data-ttu-id="0cf38-118">Kliknij opcję Wartości.</span><span class="sxs-lookup"><span data-stu-id="0cf38-118">Click Values.</span></span>
13. <span data-ttu-id="0cf38-119">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="0cf38-119">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="0cf38-120">Wprowadź wartość tego kodu podatku.</span><span class="sxs-lookup"><span data-stu-id="0cf38-120">Enter the value for this tax code.</span></span>
    * <span data-ttu-id="0cf38-121">Jeśli na skróconej karcie Obliczanie w polu Podstawa opodatkowania wybrano opcję Kwota na jednostkę, w celu obliczenia kwoty podatku wartość będzie mnożona przez ilość w transakcji.</span><span class="sxs-lookup"><span data-stu-id="0cf38-121">On the Calculation FastTab, in the Origin field, if Amount per unit is selected, the value will be multiplied by the quantity on the transaction to calculate the sales tax amount.</span></span>  <span data-ttu-id="0cf38-122">Jeśli kod podatku nie dotyczy podatku jednostkowego, w celu obliczenia kwoty podatku wartość jest procentem stosowanym do podstawy opodatkowania dla tego kodu podatku.</span><span class="sxs-lookup"><span data-stu-id="0cf38-122">If the tax code is not a unit based tax, the value is a percentage that is applied on the Origin for this tax code to calculate the sales tax amount.</span></span>     
15. <span data-ttu-id="0cf38-123">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="0cf38-123">Click Save.</span></span>
16. <span data-ttu-id="0cf38-124">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="0cf38-124">Close the page.</span></span>
17. <span data-ttu-id="0cf38-125">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="0cf38-125">Click Save.</span></span>


