---
title: Tworzenie płatności podatku
description: Procedura zadania rozliczenia i księgowania podatku rozlicza salda podatku na kontach podatków i kompensuje je na koncie rozliczeniowym podatku za dany okres.
author: twheeloc
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5066689fb85dd176da1ca1561614e443cb87d816
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5832761"
---
# <a name="create-a-sales-tax-payment"></a><span data-ttu-id="a75db-103">Tworzenie płatności podatku</span><span class="sxs-lookup"><span data-stu-id="a75db-103">Create a sales tax payment</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a75db-104">Procedura zadania rozliczenia i księgowania podatku rozlicza salda podatku na kontach podatków i kompensuje je na koncie rozliczeniowym podatku za dany okres.</span><span class="sxs-lookup"><span data-stu-id="a75db-104">The settle and post sales tax job procedure settles sales tax balances on the sales tax accounts, and offsets them to the sales tax settlement account for a given period.</span></span>

1. <span data-ttu-id="a75db-105">Wybierz kolejno opcje **Podatek > Deklaracje > Podatek > Rozlicz i zaksięguj podatek**.</span><span class="sxs-lookup"><span data-stu-id="a75db-105">Go to **Tax > Declarations > Sales tax > Settle and post sales tax**.</span></span>
2. <span data-ttu-id="a75db-106">W polu **Okres rozliczeniowy** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="a75db-106">In the **Settlement period** field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="a75db-107">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="a75db-107">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="a75db-108">W polu **Od dnia** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="a75db-108">In the **From date** field, enter a date.</span></span>
    * <span data-ttu-id="a75db-109">Jeśli na stronie **Parametry księgi głównej** nie zaznaczono opcji **Uwzględnij korekty**, rozliczenie może być przetwarzane dla różnych wersji.</span><span class="sxs-lookup"><span data-stu-id="a75db-109">If you don't select the **Include corrections** option on the **General ledger parameters** page, the settlement can be processed for different versions.</span></span> <span data-ttu-id="a75db-110">Oryginał jest pierwszym rozliczeniem w interwale okresu i może być przetwarzany tylko raz w interwale.</span><span class="sxs-lookup"><span data-stu-id="a75db-110">Original is the first settlement for a period interval and can be processed only once for a period interval.</span></span> <span data-ttu-id="a75db-111">Najnowsze korekty rozliczają transakcje podatkowe, które zostały zaksięgowane po utworzeniu oryginalnej wersji.</span><span class="sxs-lookup"><span data-stu-id="a75db-111">The latest corrections will settle sales tax transactions which have been posted after the original version has been created.</span></span>   
5. <span data-ttu-id="a75db-112">W polu **Data transakcji** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="a75db-112">In the **Transaction date** field, enter a date.</span></span>
6. <span data-ttu-id="a75db-113">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a75db-113">Click **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]