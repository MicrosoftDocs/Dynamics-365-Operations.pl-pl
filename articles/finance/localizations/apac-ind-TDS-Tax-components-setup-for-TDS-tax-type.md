---
title: Skonfiguruj składniki podatku dla typu podatku TDS
description: W tym temacie wyjaśniono, jak skonfigurować składniki podatku u źródła dla typu podatku odliczanego u źródła (TDS). Opisano w nim także sposób definiowania limitu progowego używanego do obliczania identyfikatorów TDS dla każdego składnika TDS.
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
ms.openlocfilehash: 6e0a6a05fcb4afb8c8965e25c3089bc1b3d98431
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023503"
---
# <a name="set-up-tax-components-for-the-tds-tax-type"></a><span data-ttu-id="7bb8f-104">Skonfiguruj składniki podatku dla typu podatku TDS</span><span class="sxs-lookup"><span data-stu-id="7bb8f-104">Set up tax components for the TDS tax type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7bb8f-105">W tym temacie wyjaśniono, jak skonfigurować składniki podatku u źródła dla typu podatku odliczanego u źródła (TDS).</span><span class="sxs-lookup"><span data-stu-id="7bb8f-105">This topic explains how to set up withholding tax components for the Tax Deducted at Source (TDS) tax type.</span></span> <span data-ttu-id="7bb8f-106">Składniki TDS to TDS, dopłaty, PE-Cess i SHE Cess.</span><span class="sxs-lookup"><span data-stu-id="7bb8f-106">The TDS components are TDS, surcharge, PE-Cess, and SHE Cess.</span></span> <span data-ttu-id="7bb8f-107">Opisano w temacie także sposób definiowania limitu progowego używanego do obliczania identyfikatorów TDS dla każdego składnika TDS.</span><span class="sxs-lookup"><span data-stu-id="7bb8f-107">This topic also explains how to define the threshold that is used to calculate TDS for each TDS component.</span></span> <span data-ttu-id="7bb8f-108">Ponadto można zdefiniować próg wyjątku, który służy do obliczania identyfikatorów TDS dla każdego składnika TDS.</span><span class="sxs-lookup"><span data-stu-id="7bb8f-108">Additionally, you can define an exception threshold that is used to calculate TDS for each TDS component.</span></span>

<span data-ttu-id="7bb8f-109">Wykonaj poniższe czynności, aby skonfigurować składniki TDS.</span><span class="sxs-lookup"><span data-stu-id="7bb8f-109">Follow these steps to set up TDS components.</span></span>

1. <span data-ttu-id="7bb8f-110">Wybierz kolejno opcje **Podatek \> Konfiguracja \> Potrącona zaliczka na podatek \> Składniki potrąconej zaliczki**.</span><span class="sxs-lookup"><span data-stu-id="7bb8f-110">Go to **Tax \> Setup \> Withholding tax \> Withholding tax components**.</span></span>

    <span data-ttu-id="7bb8f-111">[![Strona składników podatku u źródła](./media/apac-ind-TDS-9.png)](./media/apac-ind-TDS-9.png)</span><span class="sxs-lookup"><span data-stu-id="7bb8f-111">[![Withholding tax components page](./media/apac-ind-TDS-9.png)](./media/apac-ind-TDS-9.png)</span></span>

2. <span data-ttu-id="7bb8f-112">W polu **Typ podatku** wybierz **TDS**, aby skonfigurować składniki potrąconej zaliczki na podatek dla tego typu podatku TDS.</span><span class="sxs-lookup"><span data-stu-id="7bb8f-112">In the **Tax type** field, select **TDS** to set up withholding tax components for the TDS tax type.</span></span>
3. <span data-ttu-id="7bb8f-113">W okienku akcji wybierz opcję **Nowy**, aby utworzyć wiersz.</span><span class="sxs-lookup"><span data-stu-id="7bb8f-113">On the Action Pane, select **New** to create a line.</span></span>
4. <span data-ttu-id="7bb8f-114">W polu **Składniki potrąconej zaliczki na podatek** wprowadź nazwę składników TDS.</span><span class="sxs-lookup"><span data-stu-id="7bb8f-114">In the **Withholding tax component** field, enter a name for the TDS component.</span></span>
5. <span data-ttu-id="7bb8f-115">W polu **Grupa składników potrąconej zaliczki na podatek** wybierz grupę składników potrąconej zaliczki na podatek TDS, do której ma być dołączany składnik TDS.</span><span class="sxs-lookup"><span data-stu-id="7bb8f-115">In the **Withholding tax component group** field, select the TDS withholding tax component group to attach the TDS component to.</span></span>
6. <span data-ttu-id="7bb8f-116">Na skróconej karcie **Ogólne** w polu **Opis** wpisz opis składnika TDS.</span><span class="sxs-lookup"><span data-stu-id="7bb8f-116">On the **General** FastTab, in the **Description** field, enter a description of  the TDS component.</span></span>
7. <span data-ttu-id="7bb8f-117">W okienku akcji wybierz pozycję **Próg**, aby otworzyć stronę **Progu**, aby można było zdefiniować próg używany do obliczania TDS dla składnika TDS.</span><span class="sxs-lookup"><span data-stu-id="7bb8f-117">On the Action Pane, select **Threshold** to open **Threshold** page, so that you can define the threshold that is used to calculate TDS for the TDS component.</span></span>
8. <span data-ttu-id="7bb8f-118">Za pomocą pól **Od dnia** i **Do dnia** zdefiniuj okres, do których ma zastosowanie próg.</span><span class="sxs-lookup"><span data-stu-id="7bb8f-118">Use the **From date** and **To date** fields to define the period that the threshold is applicable to.</span></span>
9. <span data-ttu-id="7bb8f-119">Na skróconej karcie **Ogólne** w polu **Próg** wprowadź kwotę progu używaną do obliczania TDS dla składnika TDS.</span><span class="sxs-lookup"><span data-stu-id="7bb8f-119">On the **General** FastTab, in the **Threshold** field, enter the threshold amount that is used to calculate TDS for the TDS component.</span></span> <span data-ttu-id="7bb8f-120">Podatek zostanie potrącony w źródle tylko wtedy, gdy skumulowana kwota faktury przekroczy próg.</span><span class="sxs-lookup"><span data-stu-id="7bb8f-120">The tax will be deducted at the source only when the cumulative invoice amount crosses the threshold.</span></span>

    <span data-ttu-id="7bb8f-121">Na przykład, jeśli kwota progowa wynosi 10 000, identyfikator TDS jest obliczany po tym, jak kwota skumulowanej faktury przekroczy 10 000 (czyli jeśli wynosi 10 001 lub więcej).</span><span class="sxs-lookup"><span data-stu-id="7bb8f-121">For example, if the threshold amount is 10,000, TDS is calculated after the cumulative invoice amount exceeds 10,000 (in other words, when it's 10,001 or more).</span></span>

10. <span data-ttu-id="7bb8f-122">W polu **Próg wyjątku** wprowadź kwotę progu wyjątku, która jest używana do obliczenia TDS dla składnika TDS.</span><span class="sxs-lookup"><span data-stu-id="7bb8f-122">In the **Exception threshold** field, enter the exception threshold amount that is used to calculate TDS for the TDS component.</span></span> <span data-ttu-id="7bb8f-123">Podatek w wierszu faktury zostanie potrącony u źródła tylko wtedy, gdy kwota przekroczy próg wyjątku.</span><span class="sxs-lookup"><span data-stu-id="7bb8f-123">The tax on an invoice line will be deducted at the source only when the amount crosses the exception threshold.</span></span>

    <span data-ttu-id="7bb8f-124">Na przykład, jeśli kwota progu wyjątku wynosi 5000, identyfikator TDS jest obliczany dla określonego wiersza faktury, jeśli kwota wiersza faktury przekracza 5000 (innymi słowy, jeśli wynosi 5001 lub więcej).</span><span class="sxs-lookup"><span data-stu-id="7bb8f-124">For example, if the exception threshold amount is 5,000, TDS is calculated on a specific invoice line if the invoice line amount exceeds 5,000 (in other words, if it's 5,001 or more).</span></span>

    <span data-ttu-id="7bb8f-125">[![Strona progu](./media/apac-ind-TDS-10.png)](./media/apac-ind-TDS-10.png)</span><span class="sxs-lookup"><span data-stu-id="7bb8f-125">[![Threshold page](./media/apac-ind-TDS-10.png)](./media/apac-ind-TDS-10.png)</span></span>

    > [!NOTE]
    > <span data-ttu-id="7bb8f-126">Kwota progu wyjątku musi być mniejsza od kwoty progu lub jej równa.</span><span class="sxs-lookup"><span data-stu-id="7bb8f-126">The exception threshold amount must be less than or equal to the threshold amount.</span></span>
    >
    > <span data-ttu-id="7bb8f-127">Podatek jest potrącana dla transakcji, jeśli kwota transakcji przekracza próg wyjątku, nawet jeśli skumulowana kwota faktury nie przekracza progu określonego w polu **Próg**.</span><span class="sxs-lookup"><span data-stu-id="7bb8f-127">The tax is deducted for a transaction if the transaction amount crosses the exception threshold, even if the cumulative invoice amount doesn't cross the threshold that is specified in the **Threshold** field.</span></span>

11. <span data-ttu-id="7bb8f-128">Zamknij stronę **Próg**, aby powrócić do strony **Składniki potrąconej zaliczki na podatek**.</span><span class="sxs-lookup"><span data-stu-id="7bb8f-128">Close the **Threshold** page to return to the **Withholding tax components** page.</span></span>
12. <span data-ttu-id="7bb8f-129">W okienku akcji wybierz opcję **Kopiuj**, aby otworzyć okno dialogowe **Kopiowanie składników potrąconych zaliczek na podatek**, aby można było skopiować składniki TDS, które zostały ustawione dla jednej grupy składników TDS do innej grupy składników TDS.</span><span class="sxs-lookup"><span data-stu-id="7bb8f-129">On the Action Pane, select **Copy** to open the **Copy withholding tax components** dialog box, so that you can copy the TDS components that were set up for one TDS component group to another TDS component group.</span></span>
13. <span data-ttu-id="7bb8f-130">W polu **Od** wybierz grupę składników TDS, z których mają być skopiowane składniki TDS.</span><span class="sxs-lookup"><span data-stu-id="7bb8f-130">In the **From** field, select the TDS component group to copy the TDS components from.</span></span> <span data-ttu-id="7bb8f-131">W polu **Do** wybierz grupę składników zaliczki, do których mają być skopiowane składniki TDS.</span><span class="sxs-lookup"><span data-stu-id="7bb8f-131">In the **To** field, select the withholding tax component group to copy the TDS components to.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7bb8f-132">Typowe składniki TDS dołączone do obu grup składników TDS nie są kopiowane.</span><span class="sxs-lookup"><span data-stu-id="7bb8f-132">Common TDS components that are attached to both TDS component groups aren't copied.</span></span>

14. <span data-ttu-id="7bb8f-133">Wybierz **przycisk OK**, aby skopiować i utworzyć składniki TDS dla innej grupy składników TDS na stronie **Składniki potrąconej zaliczki na podatek**.</span><span class="sxs-lookup"><span data-stu-id="7bb8f-133">Select **OK** to copy and create TDS components for the other TDS component group on the **Withholding tax components** page.</span></span>

    <span data-ttu-id="7bb8f-134">[![Okno dialogowe kopiowania składników potrąconych zaliczek na podatek](./media/apac-ind-TDS-11.png)](./media/apac-ind-TDS-11.png)</span><span class="sxs-lookup"><span data-stu-id="7bb8f-134">[![Copy withholding tax components dialog box](./media/apac-ind-TDS-11.png)](./media/apac-ind-TDS-11.png)</span></span>

15. <span data-ttu-id="7bb8f-135">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7bb8f-135">Close the page.</span></span>
