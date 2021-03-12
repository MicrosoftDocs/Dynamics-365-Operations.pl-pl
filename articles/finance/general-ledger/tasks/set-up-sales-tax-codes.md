---
title: Konfigurowanie kodów podatków
description: W tym temacie wyjaśniono sposób konfigurowania kodów podatków w Dynamics 365 Finance.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3f6df5ed3fc49b537845e7d418d4953c0faee5f3
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994547"
---
# <a name="set-up-sales-tax-codes"></a><span data-ttu-id="ece42-103">Konfigurowanie kodów podatków</span><span class="sxs-lookup"><span data-stu-id="ece42-103">Set up sales tax codes</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ece42-104">W tym temacie wyjaśniono sposób konfigurowania kodów podatków.</span><span class="sxs-lookup"><span data-stu-id="ece42-104">This topic explains how to set up sales tax codes.</span></span> <span data-ttu-id="ece42-105">Kody podatków tworzy się dla każdego podatku pośredniego lub cła, które firma musi naliczać, pobierać i wpłacać do urzędu skarbowego.</span><span class="sxs-lookup"><span data-stu-id="ece42-105">Sales tax codes are created for every indirect tax or duty that the legal entity is obligated to calculate, collect, and pay to sales tax authorities.</span></span>

<span data-ttu-id="ece42-106">W zadaniu wykorzystano firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="ece42-106">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="ece42-107">Otwórz **Okienko nawigacji > Podatek > Podatki pośrednie > Podatek > Kody podatków**.</span><span class="sxs-lookup"><span data-stu-id="ece42-107">Go to **Navigation pane > Tax > Indirect taxes > Sales tax > Sales tax codes**.</span></span>
2. <span data-ttu-id="ece42-108">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="ece42-108">Select **New**.</span></span>
3. <span data-ttu-id="ece42-109">W polu **Kod podatku** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ece42-109">In the **Sales tax code** field, type a value.</span></span>
4. <span data-ttu-id="ece42-110">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ece42-110">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="ece42-111">Wybierz **okres rozliczenia**, otwierając listę rozwijaną, aby określić, do którego urzędu skarbowego i w których interwałach ten podatek musi być zgłaszany i płacony.</span><span class="sxs-lookup"><span data-stu-id="ece42-111">Select a **Settlement period** by opening the pull-down list to specify which Sales tax authority and in which intervals this sales tax needs to be reported and paid.</span></span>
6. <span data-ttu-id="ece42-112">Wybierz **grupę księgowania**, aby określić konta główne w Księdze głównej, na których będzie księgowany podatek.</span><span class="sxs-lookup"><span data-stu-id="ece42-112">Select a **Ledger posting group** to specify the main accounts to post sales tax to the general ledger.</span></span>
7. <span data-ttu-id="ece42-113">Rozwiń skróconą kartę **Obliczanie**.</span><span class="sxs-lookup"><span data-stu-id="ece42-113">Expand the **Calculation** FastTab.</span></span> <span data-ttu-id="ece42-114">Zawiera ona wiele pól, które kontrolują sposób obliczania kwot podatków.</span><span class="sxs-lookup"><span data-stu-id="ece42-114">This includes multiple fields that control how sales tax amounts will be calculated.</span></span> <span data-ttu-id="ece42-115">Odpowiednio wypełnij te pola.</span><span class="sxs-lookup"><span data-stu-id="ece42-115">Fill these fields out as needed.</span></span>  
8. <span data-ttu-id="ece42-116">W **okienku akcji** u góry interfejsu wybierz **Kod podatku**.</span><span class="sxs-lookup"><span data-stu-id="ece42-116">On the **Action Pane** at the top of the interface, select **Sales tax code**.</span></span>
9. <span data-ttu-id="ece42-117">Wybierz **Wartości**.</span><span class="sxs-lookup"><span data-stu-id="ece42-117">Select **Values**.</span></span>
10. <span data-ttu-id="ece42-118">Wprowadź wartość dla tego kodu podatków w kolumnie **Wartość**.</span><span class="sxs-lookup"><span data-stu-id="ece42-118">Enter the value for this tax code in the **value** column.</span></span>
    - <span data-ttu-id="ece42-119">Jeśli na skróconej karcie **Obliczanie** w polu Podstawa opodatkowania wybrano opcję Kwota na jednostkę, w celu obliczenia kwoty podatku wartość będzie mnożona przez ilość w transakcji.</span><span class="sxs-lookup"><span data-stu-id="ece42-119">On the **Calculation** FastTab, in the Origin field, if Amount per unit is selected, the value will be multiplied by the quantity on the transaction to calculate the sales tax amount.</span></span>  <span data-ttu-id="ece42-120">Jeśli kod podatku nie dotyczy podatku jednostkowego, w celu obliczenia kwoty podatku wartość jest procentem stosowanym do podstawy opodatkowania dla tego kodu podatku.</span><span class="sxs-lookup"><span data-stu-id="ece42-120">If the tax code is not a unit based tax, the value is a percentage that is applied on the Origin for this tax code to calculate the sales tax amount.</span></span>     
11. <span data-ttu-id="ece42-121">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="ece42-121">Select **Save**.</span></span>
12. <span data-ttu-id="ece42-122">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ece42-122">Close the page.</span></span>
13. <span data-ttu-id="ece42-123">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="ece42-123">Select **Save**.</span></span>

