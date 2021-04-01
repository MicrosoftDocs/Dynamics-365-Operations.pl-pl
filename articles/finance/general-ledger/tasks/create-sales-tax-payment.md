---
title: Tworzenie płatności podatku
description: Procedura zadania rozliczenia i księgowania podatku rozlicza salda podatku na kontach podatków i kompensuje je na koncie rozliczeniowym podatku za dany okres.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f9523ef75953bdca36f509f596c51c08b12b3fdb
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254470"
---
# <a name="create-a-sales-tax-payment"></a><span data-ttu-id="aaccb-103">Tworzenie płatności podatku</span><span class="sxs-lookup"><span data-stu-id="aaccb-103">Create a sales tax payment</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="aaccb-104">Procedura zadania rozliczenia i księgowania podatku rozlicza salda podatku na kontach podatków i kompensuje je na koncie rozliczeniowym podatku za dany okres.</span><span class="sxs-lookup"><span data-stu-id="aaccb-104">The settle and post sales tax job procedure settles sales tax balances on the sales tax accounts, and offsets them to the sales tax settlement account for a given period.</span></span>

1. <span data-ttu-id="aaccb-105">Wybierz kolejno opcje **Podatek > Deklaracje > Podatek > Rozlicz i zaksięguj podatek**.</span><span class="sxs-lookup"><span data-stu-id="aaccb-105">Go to **Tax > Declarations > Sales tax > Settle and post sales tax**.</span></span>
2. <span data-ttu-id="aaccb-106">W polu **Okres rozliczeniowy** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="aaccb-106">In the **Settlement period** field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="aaccb-107">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="aaccb-107">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="aaccb-108">W polu **Od dnia** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="aaccb-108">In the **From date** field, enter a date.</span></span>
    * <span data-ttu-id="aaccb-109">Jeśli na stronie **Parametry księgi głównej** nie zaznaczono opcji **Uwzględnij korekty**, rozliczenie może być przetwarzane dla różnych wersji.</span><span class="sxs-lookup"><span data-stu-id="aaccb-109">If you don't select the **Include corrections** option on the **General ledger parameters** page, the settlement can be processed for different versions.</span></span> <span data-ttu-id="aaccb-110">Oryginał jest pierwszym rozliczeniem w interwale okresu i może być przetwarzany tylko raz w interwale.</span><span class="sxs-lookup"><span data-stu-id="aaccb-110">Original is the first settlement for a period interval and can be processed only once for a period interval.</span></span> <span data-ttu-id="aaccb-111">Najnowsze korekty rozliczają transakcje podatkowe, które zostały zaksięgowane po utworzeniu oryginalnej wersji.</span><span class="sxs-lookup"><span data-stu-id="aaccb-111">The latest corrections will settle sales tax transactions which have been posted after the original version has been created.</span></span>   
5. <span data-ttu-id="aaccb-112">W polu **Data transakcji** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="aaccb-112">In the **Transaction date** field, enter a date.</span></span>
6. <span data-ttu-id="aaccb-113">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="aaccb-113">Click **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]