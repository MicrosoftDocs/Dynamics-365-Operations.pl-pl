---
title: Ustaw parametry TDS
description: W tym temacie wyjaśniono, jak skonfigurować parametry uaktywnienia funkcji potrącenia podatku w źródle (TDS) w określonych transakcjach. Jest to krok niezbędny, aby użyć funkcji Podatek potrącony w źródłowym TDS.
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
ms.openlocfilehash: dda276b7d634317aae26728f7d9f51af9ccfb896
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023506"
---
# <a name="set-the-tds-parameters"></a><span data-ttu-id="f28de-104">Ustaw parametry TDS</span><span class="sxs-lookup"><span data-stu-id="f28de-104">Set the TDS parameters</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f28de-105">W tym temacie wyjaśniono, jak skonfigurować parametry uaktywnienia funkcji potrącenia podatku w źródle (TDS) w określonych transakcjach.</span><span class="sxs-lookup"><span data-stu-id="f28de-105">This topic explains how to set parameters to activate Tax Deducted at Source (TDS) functionality in specified transactions.</span></span> <span data-ttu-id="f28de-106">Jest to krok niezbędny, aby użyć funkcji Podatek potrącony w źródłowym TDS.</span><span class="sxs-lookup"><span data-stu-id="f28de-106">This is a necessary step to use the Tax Deducted at Source TDS feature.</span></span>

1. <span data-ttu-id="f28de-107">Przejdź do pozycji **Księga główna \> Ustawienia księgi \> Parametry księgi głównej**.</span><span class="sxs-lookup"><span data-stu-id="f28de-107">Go to **General ledger \> Ledger setup \> General ledger parameters**.</span></span>
2. <span data-ttu-id="f28de-108">Na karcie **Podatki bezpośrednie**, w sekcji **Podatek potrącony w źródle** ustaw opcję **Aktywuj TDS** na wartość **Tak**, aby uaktywnić funkcję TDS, oraz strony i pola, które są dla nich używane.</span><span class="sxs-lookup"><span data-stu-id="f28de-108">On the **Direct taxes** tab, in the **Tax Deducted at Source** section, set the **Activate TDS** option to **Yes** to activate the TDS functionality, and the pages and fields that are used for it.</span></span>
3. <span data-ttu-id="f28de-109">Ustaw dla opcji **Faktura** wartość **Tak**, aby uaktywnić pola używane do obliczania i odejmowania identyfikatorów TDS na poziomie faktury.</span><span class="sxs-lookup"><span data-stu-id="f28de-109">Set the **Invoice** option to **Yes** to activate the fields that are used to calculate and deduct TDS at the invoice level.</span></span>
4. <span data-ttu-id="f28de-110">Ustaw dla opcji **Płatność** wartość **Tak**, aby uaktywnić pola używane do obliczania i odejmowania identyfikatorów TDS na poziomie płatności.</span><span class="sxs-lookup"><span data-stu-id="f28de-110">Set the **Payment** option to **Yes** to activate the fields that are used to calculate and deduct TDS at the payment level.</span></span>

    <span data-ttu-id="f28de-111">[![Karta Podatki bezpośrednie](./media/apac-ind-TDS-1.png)](./media/apac-ind-TDS-1.png)</span><span class="sxs-lookup"><span data-stu-id="f28de-111">[![Direct taxes tab](./media/apac-ind-TDS-1.png)](./media/apac-ind-TDS-1.png)</span></span>

5. <span data-ttu-id="f28de-112">Na karcie **Sekwencje numerów** znajdź wiersz, w którym w polu **Odwołanie** ustawiono **płatność potrąconej zaliczki na podatek**.</span><span class="sxs-lookup"><span data-stu-id="f28de-112">On the **Number sequences** tab, find the row where the **Reference** field is set to **Withholding tax payment**.</span></span> <span data-ttu-id="f28de-113">W wierszu **kod sekwencji numerów** wybierz kod każdej sekwencji numerów kodu.</span><span class="sxs-lookup"><span data-stu-id="f28de-113">In the **Number sequence code** field for the row, select the number sequence code.</span></span> <span data-ttu-id="f28de-114">Kod sekwencji numerów służy do generowania numerów załączników dla okresowego procesu rozliczania TDS.</span><span class="sxs-lookup"><span data-stu-id="f28de-114">The number sequence code is used to generate voucher numbers for the periodic TDS settlement process.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f28de-115">Aby uruchomić okresowy proces rozliczania TDS, przejdź do **Podatek \> Deklaracje \> Potrącona zaliczka na podatek \> Płatność zaliczki na podatek**.</span><span class="sxs-lookup"><span data-stu-id="f28de-115">To run the periodic TDS settlement process, go to **Tax \> Declarations \> Withholding tax \> Withholding tax payment**.</span></span>

    <span data-ttu-id="f28de-116">[![Karta Sekwencje numerów](./media/apac-ind-TDS-2.png)](./media/apac-ind-TDS-2.png)</span><span class="sxs-lookup"><span data-stu-id="f28de-116">[![Number sequences tab](./media/apac-ind-TDS-2.png)](./media/apac-ind-TDS-2.png)</span></span>

6. <span data-ttu-id="f28de-117">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f28de-117">Close the page.</span></span>
