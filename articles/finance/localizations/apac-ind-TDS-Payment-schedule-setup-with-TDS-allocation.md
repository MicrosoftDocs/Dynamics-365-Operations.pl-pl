---
title: Konfigurowanie harmonogramów płatności z alokacją podatku TDS
description: W tym temacie wyjaśniono, jak skonfigurować harmonogramy płatności z alokacją podatku odliczonego u źródła (TDS).
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
ms.openlocfilehash: 47551f52f35fec5ae49d696e3f4027b7d2eb2e19
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023516"
---
# <a name="set-up-payment-schedules-with-tds-allocation"></a><span data-ttu-id="d7bf8-103">Konfigurowanie harmonogramów płatności z alokacją podatku TDS</span><span class="sxs-lookup"><span data-stu-id="d7bf8-103">Set up payment schedules with TDS allocation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d7bf8-104">W tym temacie wyjaśniono, jak skonfigurować harmonogramy płatności z alokacją podatku odliczonego u źródła (TDS).</span><span class="sxs-lookup"><span data-stu-id="d7bf8-104">This topic explains how to set up payment schedules with Tax Deducted at Source (TDS) allocation.</span></span>

1. <span data-ttu-id="d7bf8-105">Wybierz kolejno opcje **Rozrachunki z dostawcami \> Ustawienia płatności \> Harmonogramy płatności**.</span><span class="sxs-lookup"><span data-stu-id="d7bf8-105">Go to **Accounts payable \> Payment setup \> Payment schedules**.</span></span>

    <span data-ttu-id="d7bf8-106">[![Strona Harmonogramy płatności](./media/apac-ind-TDS-27.png)](./media/apac-ind-TDS-27.png)</span><span class="sxs-lookup"><span data-stu-id="d7bf8-106">[![Payment schedules page](./media/apac-ind-TDS-27.png)](./media/apac-ind-TDS-27.png)</span></span>

2. <span data-ttu-id="d7bf8-107">Wybierz **Nowy** na okienku akcji, aby utworzyć harmonogram opłat za płatność i wprowadź wymagane szczegóły.</span><span class="sxs-lookup"><span data-stu-id="d7bf8-107">On the Action Pane, select **New** to create a payment schedule, and enter the required details.</span></span>
3. <span data-ttu-id="d7bf8-108">W polu **Alokacja** wybierz metodę alokacji płatności dla harmonogramu płatności:</span><span class="sxs-lookup"><span data-stu-id="d7bf8-108">In the **Allocation** field, select the method to use to allocate the payment for the payment schedule:</span></span>

    - <span data-ttu-id="d7bf8-109">Razem</span><span class="sxs-lookup"><span data-stu-id="d7bf8-109">Total</span></span>
    - <span data-ttu-id="d7bf8-110">Stała kwota</span><span class="sxs-lookup"><span data-stu-id="d7bf8-110">Fixed amount</span></span>
    - <span data-ttu-id="d7bf8-111">Stała ilość</span><span class="sxs-lookup"><span data-stu-id="d7bf8-111">Fixed quantity</span></span>
    - <span data-ttu-id="d7bf8-112">Określone</span><span class="sxs-lookup"><span data-stu-id="d7bf8-112">Specified</span></span>

    <span data-ttu-id="d7bf8-113">Pole **Alokacja potrąconej zaliczki** na podatek zawiera metodę alokacji TDS dla harmonogramu płatności.</span><span class="sxs-lookup"><span data-stu-id="d7bf8-113">The **Withholding tax allocation** field shows the TDS allocation method for the payment schedule.</span></span> <span data-ttu-id="d7bf8-114">Jeśli zostanie zaznaczyna wartość **Suma** w polu **Alokacja** zw polu **Alokacja potrąconej zaliczki na podatek** zostanie automatycznie ustawiona wartość **Suma**.</span><span class="sxs-lookup"><span data-stu-id="d7bf8-114">If you select **Total** in the **Allocation** field, the **Withholding tax allocation** field is automatically set to **Total**.</span></span> <span data-ttu-id="d7bf8-115">W przypadku wybrania opcji **Stała kwota**, **Stała ilość** lub **Określona** w polu **Alokacja** pole **Alokacja potrąconej zaliczki na podatek** jest automatycznie ustawiane na wartość **Proporcjonalnie**.</span><span class="sxs-lookup"><span data-stu-id="d7bf8-115">If you select **Fixed amount**, **Fixed quantity**, or **Specified** in the **Allocation** field, the **Withholding tax allocation** field is automatically set to **Proportionally**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d7bf8-116">Jeśli w polu **Alokacja potrąconej zaliczki na podatek** jest ustawiona wartość **Suma**, raty płatności są obliczane na podstawie kwoty brutto, która zawiera kwotę TDS.</span><span class="sxs-lookup"><span data-stu-id="d7bf8-116">If the **Withholding tax allocation** field is set to **Total**, the payment installments are calculated based on the gross amount, which includes the TDS amount.</span></span> <span data-ttu-id="d7bf8-117">Jeśli w polu **Alokacja potrąconej zaliczki na podatek** jest ustawiona wartość **Proporcjonalnie**, raty płatności są naliczane na podstawie kwoty faktury netto po potrąceniu kwoty TDS.</span><span class="sxs-lookup"><span data-stu-id="d7bf8-117">If the **Withholding tax allocation** field is set to **Proportionally**, the payment installments are calculated based on the net invoice amount after the TDS amount is deducted.</span></span>

4. <span data-ttu-id="d7bf8-118">Wprowadź inne wymagane szczegóły, a następnie zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d7bf8-118">Enter the other required details, and then close the page.</span></span>
