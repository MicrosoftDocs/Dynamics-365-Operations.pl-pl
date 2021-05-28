---
title: Ustaw okresy rozliczenia podatku u źródła dla typu podatku TDS
description: W tym temacie wyjaśniono, jak skonfigurować okresy rozliczeniowe dla okresów rozliczenia podatku odliczonego u źródła (TDS).
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
ms.openlocfilehash: 9430bc1386f127d02b598d6cad1b53f66e0cf2ba
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023495"
---
# <a name="set-up-withholding-tax-settlement-periods-for-the-tds-tax-type"></a><span data-ttu-id="8fd45-103">Ustaw okresy rozliczenia podatku u źródła dla typu podatku TDS</span><span class="sxs-lookup"><span data-stu-id="8fd45-103">Set up withholding tax settlement periods for the TDS tax type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8fd45-104">W tym temacie wyjaśniono, jak skonfigurować okresy rozliczeniowe dla okresów rozliczenia podatku odliczonego u źródła (TDS).</span><span class="sxs-lookup"><span data-stu-id="8fd45-104">This topic explains how to set up settlement periods for Tax Deducted at Source (TDS) settlement periods.</span></span>

1. <span data-ttu-id="8fd45-105">Wybierz kolejno opcje **Podatek \> Podatki pośrednie \> Potrącona zaliczka na podatek \> Okresy rozliczenia podatku u źródła**.</span><span class="sxs-lookup"><span data-stu-id="8fd45-105">Go to **Tax \> Indirect taxes \> Withholding tax \> Withholding tax settlement periods**.</span></span>

    <span data-ttu-id="8fd45-106">[![Strona Okresy rozliczenia podatku u źródła](./media/apac-ind-TDS-13.png)](./media/apac-ind-TDS-13.png)</span><span class="sxs-lookup"><span data-stu-id="8fd45-106">[![Withholding tax settlement periods page](./media/apac-ind-TDS-13.png)](./media/apac-ind-TDS-13.png)</span></span>

2. <span data-ttu-id="8fd45-107">W polu **Typ podatku** wybierz **TDS**, aby ustawić okresy rozliczenia podatku u źródła dla typu podatku potrącanego u źródła.</span><span class="sxs-lookup"><span data-stu-id="8fd45-107">In the **Tax type** field, select **TDS** to set up withholding tax settlement periods for the TDS tax type.</span></span>
3. <span data-ttu-id="8fd45-108">Wybierz **Nowy**, aby utworzyć wiersz.</span><span class="sxs-lookup"><span data-stu-id="8fd45-108">Select **New** to create a line.</span></span>
4. <span data-ttu-id="8fd45-109">W polu **Okres rozliczeniowy** wprowadź nazwę okresu rozliczeniowego TDS.</span><span class="sxs-lookup"><span data-stu-id="8fd45-109">In the **Settlement period** field, enter a name for the TDS settlement period.</span></span>
5. <span data-ttu-id="8fd45-110">W polu **Opis wprowadź** opis.</span><span class="sxs-lookup"><span data-stu-id="8fd45-110">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="8fd45-111">W polu **Potrącona zaliczka na podatek** wybierz urząd TDS, dla którym jest definiowany okres rozliczeniowy TDS.</span><span class="sxs-lookup"><span data-stu-id="8fd45-111">In the **Withholding tax authority** field, select the TDS authority that you're defining the TDS settlement period for.</span></span>
7. <span data-ttu-id="8fd45-112">Na skróconej karcie **Ogólne** w polu **Interwał okresu** wybierz typ interwału okresu dla okresu rozliczeniowego TDS.</span><span class="sxs-lookup"><span data-stu-id="8fd45-112">On the **General** FastTab, in the **Period interval** field, select the type of period interval for the TDS settlement period.</span></span>
8. <span data-ttu-id="8fd45-113">W polu **Liczba jednostek** określ liczbę jednostek dla typu interwału okresu.</span><span class="sxs-lookup"><span data-stu-id="8fd45-113">In the **Number of units** field, specify the number of units for the period interval type.</span></span>
9. <span data-ttu-id="8fd45-114">Na skróconej karcie **Okresy** w polu **Od dnia** wybierz datę rozpoczęcia okresu rozliczeniowego TDS.</span><span class="sxs-lookup"><span data-stu-id="8fd45-114">On the **Periods** FastTab, in the **From date** field, select the start date for the TDS settlement period.</span></span> <span data-ttu-id="8fd45-115">W polu **Do dnia** wybierz datę zakończenia.</span><span class="sxs-lookup"><span data-stu-id="8fd45-115">In the **To date** field, select the end date.</span></span>
10. <span data-ttu-id="8fd45-116">Aby utworzyć kolejny okres rozliczeniowy TDS dla istniejącego okresu na podstawie interwału okresu i jednostek okresu, wybierz opcję **Nowy okres**.</span><span class="sxs-lookup"><span data-stu-id="8fd45-116">To create a subsequent TDS settlement period for an existing period, based on the period interval and period units, select **New period**.</span></span>
11. <span data-ttu-id="8fd45-117">Aby wyświetlić szczegóły okresowego rozliczania TDS uruchomionego dla określonego okresu rozliczeniowego, wybierz opcję **Płatności potrąconej zaliczki na podatek**, aby otworzyć stronę **Płatność potrąconej zaliczki na podatek**.</span><span class="sxs-lookup"><span data-stu-id="8fd45-117">To view the details of the periodic TDS settlement that is run for a specific settlement period, select **Withholding tax payments** to open the **Withholding tax payment** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8fd45-118">Aby uruchomić okresowy proces rozliczania TDS, przejdź do **Księga główna \> Okresowe \> Potrącona zaliczka na podatek \> Płatność zaliczki na podatek**.</span><span class="sxs-lookup"><span data-stu-id="8fd45-118">To run the periodic TDS settlement process, go to **General ledger \> Periodic \> Withholding tax \> Withholding tax payment**.</span></span>

    <span data-ttu-id="8fd45-119">[![Strona płatności potrąconej zaliczki na podatek](./media/apac-ind-TDS-15.png)](./media/apac-ind-TDS-15.png)</span><span class="sxs-lookup"><span data-stu-id="8fd45-119">[![Withholding tax payment page](./media/apac-ind-TDS-15.png)](./media/apac-ind-TDS-15.png)</span></span>

12. <span data-ttu-id="8fd45-120">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="8fd45-120">Close the page.</span></span>
