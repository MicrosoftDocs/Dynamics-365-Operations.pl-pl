---
title: Umożliwia dołączanie kodów podatków TDS do grup podatków TDS i definiowanie formuły obliczania TDS
description: W tym temacie wyjaśniono, jak skonfigurować grupy podatków Potrącone w źródle (TDS) i dołączyć kody podatków TDS do grup podatków TDS. Aby obliczyć TDS dla grupy podatków TDS, należy zdefiniować formułę dla dołączonych do niej kodów podatków TDS.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: ec0d683153bd5ab731035159d32881fbdb352d70
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023517"
---
# <a name="attach-tds-tax-codes-to-tds-tax-groups-and-define-the-formula-for-calculating-tds"></a><span data-ttu-id="d3747-104">Umożliwia dołączanie kodów podatków TDS do grup podatków TDS i definiowanie formuły obliczania TDS</span><span class="sxs-lookup"><span data-stu-id="d3747-104">Attach TDS tax codes to TDS tax groups and define the formula for calculating TDS</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d3747-105">W tym temacie wyjaśniono, jak skonfigurować grupy podatków Potrącone w źródle (TDS) i dołączyć kody podatków TDS do grup podatków TDS.</span><span class="sxs-lookup"><span data-stu-id="d3747-105">This topic explains how to set up Tax Deducted at Source (TDS) tax groups and attach TDS tax codes to TDS tax groups.</span></span> <span data-ttu-id="d3747-106">Aby obliczyć TDS dla grupy podatków TDS, należy zdefiniować formułę dla dołączonych do niej kodów podatków TDS.</span><span class="sxs-lookup"><span data-stu-id="d3747-106">To calculate TDS for a TDS tax group, you must define the formula for TDS tax codes that are attached to it.</span></span>

<span data-ttu-id="d3747-107">Aby skonfigurować grupę podatków TDS, dołączyć kody podatków TDS i zdefiniować formułę obliczania tych identyfikatorów.</span><span class="sxs-lookup"><span data-stu-id="d3747-107">Follow these steps to set up a TDS tax group, attach TDS tax codes to it, and define the formula for calculating TDS.</span></span>

1. <span data-ttu-id="d3747-108">Wybierz kolejno opcje **Podatek \> Podatki pośrednie \> Potrącona zaliczka na podatek \> Grupy potrąconych zaliczek na podatek**.</span><span class="sxs-lookup"><span data-stu-id="d3747-108">Go to **Tax \> Indirect taxes \> Withholding tax \> Withholding tax groups**.</span></span>

    <span data-ttu-id="d3747-109">[![Strona Grupy potrąconych zaliczek na podatek](./media/apac-ind-TDS-29.png)](./media/apac-ind-TDS-29.png)</span><span class="sxs-lookup"><span data-stu-id="d3747-109">[![Withholding tax groups page](./media/apac-ind-TDS-29.png)](./media/apac-ind-TDS-29.png)</span></span>

2. <span data-ttu-id="d3747-110">Wybierz **Nowy** na okienku akcji, aby utworzyć grupę podatku u źródła dla podatku u źródła i wprowadź wymagane szczegóły.</span><span class="sxs-lookup"><span data-stu-id="d3747-110">On the Action Pane, select **New** to create a withholding tax group for TDS, and enter the required details.</span></span>
3. <span data-ttu-id="d3747-111">W polu **Typ podatku** zaznacz opcję **TDS**.</span><span class="sxs-lookup"><span data-stu-id="d3747-111">In the **Tax type** field, select **TDS**.</span></span>
4. <span data-ttu-id="d3747-112">Na skróconej karcie **Ustawienia** wybierz **Dodaj**, aby utworzyć nowy wiersz.</span><span class="sxs-lookup"><span data-stu-id="d3747-112">On the **Setup** FastTab, select **Add** to create a line.</span></span>
5. <span data-ttu-id="d3747-113">W polu **Kod potrąconej zaliczki na podatek** wybierz kod podatku TDS dla grupy podatkowej TDS.</span><span class="sxs-lookup"><span data-stu-id="d3747-113">In the **Withholding tax code** field, select the TDS tax code for the TDS tax group.</span></span> <span data-ttu-id="d3747-114">Pole **Nazwa potrąconej zaliczki na podatek** zawiera nazwę kodu podatku TDS, a pole **Wartość** zawiera wartość.</span><span class="sxs-lookup"><span data-stu-id="d3747-114">The **Withholding tax name** field shows the name of the TDS tax code, and the **Value** field shows the value.</span></span>
6. <span data-ttu-id="d3747-115">Aby zignorować limit progowy i limit progu wyjątku, który jest zdefiniowany dla składnika podatku TDS dołączonego do kodu podatku TDS w transakcjach TDS, zaznacz pole wyboru **Przeoczenie progu**.</span><span class="sxs-lookup"><span data-stu-id="d3747-115">To ignore the threshold limit and exception threshold limit that are defined for the TDS tax component that is attached to the TDS tax code in TDS transactions, select the **Overlook threshold** check box.</span></span>
7. <span data-ttu-id="d3747-116">Aby zapobiec obliczaniu grupy podatkowej w transakcjach, zaznacz pole wyboru **Zwolnienie**.</span><span class="sxs-lookup"><span data-stu-id="d3747-116">To prevent the tax group from being calculated in transactions, select the **Exempt** check box.</span></span>
8. <span data-ttu-id="d3747-117">W okienku akcji wybierz opcję **Projektant**, aby otworzyć projektanta formuł, aby można było zdefiniować formułę obliczania TDS dla grupy podatków TDS.</span><span class="sxs-lookup"><span data-stu-id="d3747-117">On the Action Pane, select **Designer** to open the formula designer, so that you can define the formula for calculating TDS for the TDS tax group.</span></span> <span data-ttu-id="d3747-118">Na stronie **Konstruktor** na karcie **Podatki** są widać kody podatków TDS wybrane dla grupy podatków TDS.</span><span class="sxs-lookup"><span data-stu-id="d3747-118">On the **Designer** page, the **Taxes** tab shows the TDS tax codes that have been selected for the TDS tax group.</span></span>

    <span data-ttu-id="d3747-119">[![Strona Projektant](./media/apac-ind-TDS-30.png)](./media/apac-ind-TDS-30.png)</span><span class="sxs-lookup"><span data-stu-id="d3747-119">[![Designer page](./media/apac-ind-TDS-30.png)](./media/apac-ind-TDS-30.png)</span></span>

9. <span data-ttu-id="d3747-120">Na karcie **Obliczanie** wybierz klawisze **Alt+N**, aby utworzyć wiersz.</span><span class="sxs-lookup"><span data-stu-id="d3747-120">On the **Calculation** tab, select **Alt+N** to create a line.</span></span> <span data-ttu-id="d3747-121">Pole **identyfikator** zawiera automatycznie wygenerowany identyfikator priorytetu dla obliczania TDS.</span><span class="sxs-lookup"><span data-stu-id="d3747-121">The **ID** field shows the automatically generated priority ID for TDS calculation.</span></span>
10. <span data-ttu-id="d3747-122">W polu **Kod podatku** wybierz kod podatku TDS, dla którego ma zostać zdefiniowana formuła.</span><span class="sxs-lookup"><span data-stu-id="d3747-122">In the **Tax code** field, select the TDS tax code to define the formula for.</span></span> <span data-ttu-id="d3747-123">W tym polu są dostępne wszystkie kody podatków TDS wybrane dla grupy podatków TDS.</span><span class="sxs-lookup"><span data-stu-id="d3747-123">All the TDS tax codes that have been selected for the TDS tax group are available for selection in this field.</span></span>
11. <span data-ttu-id="d3747-124">W polu **Podstawa opodatkowania** wybierz podstawę do obliczania TDS:</span><span class="sxs-lookup"><span data-stu-id="d3747-124">In the **Taxable basis** field, select the basis for calculating TDS:</span></span>

    - <span data-ttu-id="d3747-125">**Kwota brutto** — obliczanie TDS na podstawie kwoty transakcji brutto (to jest kwoty faktury) przy użyciu wyrażenia obliczeń zdefiniowanego dla kodu podatku.</span><span class="sxs-lookup"><span data-stu-id="d3747-125">**Gross amount** – Calculate TDS based on the gross transaction amount (that is, the invoice amount) by using the calculation expression that is defined for the tax code.</span></span>
    - <span data-ttu-id="d3747-126">**Bez kwoty brutto** — obliczanie TDS na podstawie wyrażenia obliczeń zdefiniowanego dla kodu podatku.</span><span class="sxs-lookup"><span data-stu-id="d3747-126">**Excl Gross amount** – Calculate TDS based on the calculation expression that is defined for the tax code.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d3747-127">W polu **Podstawa opodatkowania** nie można ustawić wartości **Bez kwoty brutto** dla kodu podatku TDS o identyfikatorze priorytetu **1**.</span><span class="sxs-lookup"><span data-stu-id="d3747-127">The **Taxable basis** field can't be set to **Excl Gross amount** for the TDS tax code that has a priority ID of **1**.</span></span>

12. <span data-ttu-id="d3747-128">Obliczenie TDS jest oparte na formule zdefiniowanej w polu **Obliczanie wyrażenia** dla każdego kodu podatku dołączonego do grupy podatków TDS.</span><span class="sxs-lookup"><span data-stu-id="d3747-128">The TDS calculation is based on the formula that is defined in the **Calculation expression** field for each tax code that is attached to the TDS tax group.</span></span> <span data-ttu-id="d3747-129">Umożliwia wybranie znaku plus (**+**), znaku minus (**-**), znaku mnożenia (**\**_) lub znaku dzielenia (_*/**) w celu wprowadzenia wyrażenia obliczeń dla wybranego kodu podatku TDS w polu **Obliczanie wyrażenia**.</span><span class="sxs-lookup"><span data-stu-id="d3747-129">Select the plus sign (**+**), minus sign (**-**), multiplication sign (**\**_), or division sign (_*/**) button to enter the calculation expression for the selected TDS tax code in the **Calculation expression** field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d3747-130">Nie można zdefiniować wyrażenia obliczeń dla kodu podatku TDS o identyfikatorze priorytetu **1**.</span><span class="sxs-lookup"><span data-stu-id="d3747-130">No calculation expression can be defined for the TDS tax code that has a priority ID of **1**.</span></span>

13. <span data-ttu-id="d3747-131">Aby zdefiniować wyrażenie obliczeń dla kodu podatku TDS w polu **Obliczanie wyrażenia**, dodaj kody podatków TDS, które są dostępne na karcie **Podatki**. Aby dodać kody podatków TDS w polu **Obliczanie wyrażenia**, można użyć dowolnej z następujących metod:</span><span class="sxs-lookup"><span data-stu-id="d3747-131">To define the calculation expression for the TDS tax code in the **Calculation expression** field, add TDS tax codes that are available on the **Taxes** tab. To add TDS tax codes in the **Calculation expression** field, you can use any of the following methods:</span></span>

    - <span data-ttu-id="d3747-132">Przeciągnij wymagany kod podatku z karty **Podatki** do pola **Obliczanie wyrażenia**.</span><span class="sxs-lookup"><span data-stu-id="d3747-132">Drag the required tax code from the **Taxes** tab to the **Calculation expression** field.</span></span>
    - <span data-ttu-id="d3747-133">Kliknij dwukrotnie (lub kliknij dwukrotnie) wymagany kod podatku na karcie **Podatki**.</span><span class="sxs-lookup"><span data-stu-id="d3747-133">Double-tap (or double-click) the required tax code on the **Taxes** tab.</span></span>
    - <span data-ttu-id="d3747-134">Wybierz i przytrzymaj (lub kliknij prawym przyciskiem myszy) wymagany kod podatku na karcie **Podatki**, a następnie wybierz polecenie **Dodaj kod podatku**.</span><span class="sxs-lookup"><span data-stu-id="d3747-134">Select and hold (or right-click) the required tax code on the **Taxes** tab, and then select **Add tax code**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d3747-135">Wstaw wyrażenie obliczeń przed każdym kodem podatku TDS.</span><span class="sxs-lookup"><span data-stu-id="d3747-135">Insert a calculation expression before each TDS tax code.</span></span> <span data-ttu-id="d3747-136">Kody podatków TDS dodane do obliczenia wyrażenia są wyświetlane w nawiasach (\[...\]).</span><span class="sxs-lookup"><span data-stu-id="d3747-136">The TDS tax codes that have been added to the calculation expression appear in brackets (\[...\]).</span></span>

14. <span data-ttu-id="d3747-137">Aby wyczyścić wyrażenie obliczeń, które jest zdefiniowane dla kodu podatku w polu **Obliczanie wyrażenia**, wybierz przycisk **C**.</span><span class="sxs-lookup"><span data-stu-id="d3747-137">To clear the calculation expression that is defined for a tax code in the **Calculation expression** field, select the **C** button.</span></span>
15. <span data-ttu-id="d3747-138">Aby usunąć rekord na karcie **Obliczanie**, wybierz polecenie **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="d3747-138">To delete a record on the **Calculation** tab, select **Delete**.</span></span>
16. <span data-ttu-id="d3747-139">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d3747-139">Close the page.</span></span>
