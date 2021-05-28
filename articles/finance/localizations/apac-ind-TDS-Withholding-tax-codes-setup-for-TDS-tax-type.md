---
title: Skonfiguruj kody podatku u źródła dla typu podatku TDS
description: W tym temacie wyjaśniono, jak skonfigurować kody podatków dla podatku odliczanego u źródła (TDS).
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
ms.openlocfilehash: d56a23f7af7633e1761a8a7c48f71381d6f14df2
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023520"
---
# <a name="set-up-withholding-tax-codes-for-the-tds-tax-type"></a><span data-ttu-id="77295-103">Skonfiguruj kody podatku u źródła dla typu podatku TDS</span><span class="sxs-lookup"><span data-stu-id="77295-103">Set up withholding tax codes for the TDS tax type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="77295-104">W tym temacie wyjaśniono, jak skonfigurować kody podatków dla podatku odliczanego u źródła (TDS).</span><span class="sxs-lookup"><span data-stu-id="77295-104">This topic explains how to set up tax codes for Tax Deducted at Source (TDS).</span></span>

1. <span data-ttu-id="77295-105">Wybierz kolejno opcje **Podatek \> I Podatki pośrednie \> Potrącona zaliczka na podatek \> Kody potrąconych zaliczek na podatek**.</span><span class="sxs-lookup"><span data-stu-id="77295-105">Go to **Tax \> Indirect taxes \> Withholding tax \> Withholding tax codes**.</span></span>

    <span data-ttu-id="77295-106">[![Strona Kody potrąconych zaliczek na podatek](./media/apac-ind-TDS-17.png)](./media/apac-ind-TDS-17.png)</span><span class="sxs-lookup"><span data-stu-id="77295-106">[![Withholding tax codes page](./media/apac-ind-TDS-17.png)](./media/apac-ind-TDS-17.png)</span></span>

2. <span data-ttu-id="77295-107">Wybierz **Nowy** na okienku akcji, aby utworzyć kod podatku u źródła dla podatku u źródła i wprowadź wymagane szczegóły.</span><span class="sxs-lookup"><span data-stu-id="77295-107">On the Action Pane, select **New** to create a withholding tax code for TDS, and enter the required details.</span></span>
3. <span data-ttu-id="77295-108">Na skróconej karcie **Ogólne** w polu **Typ podatku** wybierz kod **TDS**, aby sklasyfikować kod podatku jako kod podatku TDS.</span><span class="sxs-lookup"><span data-stu-id="77295-108">On the **General** FastTab, in the **Tax type** field, select **TDS** to categorize the tax code as a TDS tax code.</span></span>
4. <span data-ttu-id="77295-109">W polu **Okres rozliczeniowy** wybierz okres rozliczeniowy podatku potrącanego u źródła dla kodu podatku potrącanego u źródła.</span><span class="sxs-lookup"><span data-stu-id="77295-109">In the **Settlement period** field, select the TDS settlement period for the TDS tax code.</span></span>
5. <span data-ttu-id="77295-110">W polu **Konto główne** wybierz konto księgowe, na które ma zostać zaksięgowana kwota TDS.</span><span class="sxs-lookup"><span data-stu-id="77295-110">In the **Main account** field, select the ledger account that the TDS amount should be posted to.</span></span>
6. <span data-ttu-id="77295-111">W polu **Konto należności** wybierz konto należności, na które ma być księgowana kwota TDS potrącona z transakcji sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="77295-111">In the **Receivable account** field, select the receivable account that the TDS amount that is deducted in sales transactions should be posted to.</span></span>

    <span data-ttu-id="77295-112">W polu **Źródło** jest automatycznie ustawiana wartość **Procent od kwoty brutto** i nie można zmienić tej wartości.</span><span class="sxs-lookup"><span data-stu-id="77295-112">The **Origin** field is automatically set to **Percentage of gross amount**, and the value can't be changed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="77295-113">Nie można ustawić **wartości procentowej kwoty netto** dla kodów podatków typu TDS.</span><span class="sxs-lookup"><span data-stu-id="77295-113">You can't set the origin to **Percentage of net amount** for tax codes of the TDS tax type.</span></span>

7. <span data-ttu-id="77295-114">W polu **Składnik zaliczki na podatek** wybierz składnik podatku potrącanego u źródła dla kodu podatku potrącanego u źródła.</span><span class="sxs-lookup"><span data-stu-id="77295-114">In the **Withholding tax component** field, select the TDS tax component for the TDS tax code.</span></span>
8. <span data-ttu-id="77295-115">W okienku akcji wybierz opcję **Wartości**, aby otworzyć stronę **Wartości podatku u źródła**.</span><span class="sxs-lookup"><span data-stu-id="77295-115">On the Action Pane, select **Values** to open the **Withholding tax values** page.</span></span>
9. <span data-ttu-id="77295-116">Wybierz datę początkową wartości TDS w polu **Od dnia**.</span><span class="sxs-lookup"><span data-stu-id="77295-116">In the **From date** field, enter the start date for the TDS value.</span></span> <span data-ttu-id="77295-117">W polu **Do dnia** wprowadź datę zakończenia.</span><span class="sxs-lookup"><span data-stu-id="77295-117">In the **To date** field, enter the end date.</span></span>

    > [!NOTE]
    > <span data-ttu-id="77295-118">Pola **Minimalny limit**, **Górny limit** i **Wyklucz procent** nie są dostępne dla kodów podatków typu TDS.</span><span class="sxs-lookup"><span data-stu-id="77295-118">The **Minimum limit**, **Upper limit**, and **Exclude %** fields aren't available for tax codes of the TDS tax type.</span></span>

10. <span data-ttu-id="77295-119">W polu **Wartość** wprowadź wartość procentową podatku potrącanego u źródła dla kodu podatku potrącanego u źródła.</span><span class="sxs-lookup"><span data-stu-id="77295-119">In the **Value** field, enter the percentage of TDS for the TDS tax code.</span></span>
11. <span data-ttu-id="77295-120">Zamknij stronę **Wartości podatku u źródła**, aby powrócić do strony **Kody potrąconej zaliczki na podatek**.</span><span class="sxs-lookup"><span data-stu-id="77295-120">Close the **Withholding tax values** page to return to the **Withholding tax codes** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="77295-121">Przycisk **Limity** na stronie **Kody potrąconych zaliczek** na podatek jest niedostępny dla kodów podatków typu TDS.</span><span class="sxs-lookup"><span data-stu-id="77295-121">The **Limits** button on the **Withholding tax codes** page isn't available for tax codes of the TDS tax type.</span></span>

12. <span data-ttu-id="77295-122">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="77295-122">Close the page.</span></span>
