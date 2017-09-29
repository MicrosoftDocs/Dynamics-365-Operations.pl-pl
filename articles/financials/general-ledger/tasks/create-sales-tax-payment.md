--- 
title: "Tworzenie płatności podatku"
description: "Zadanie rozliczenia i księgowania podatku rozlicza salda podatku na kontach podatków i kompensuje je na koncie rozliczeniowym podatku za dany okres."
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 6ee84da7fd055c8b0b50c43f134c0fc048ecfaeb
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-sales-tax-payment"></a><span data-ttu-id="c19ca-103">Tworzenie płatności podatku</span><span class="sxs-lookup"><span data-stu-id="c19ca-103">Create a sales tax payment</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c19ca-104">Zadanie rozliczenia i księgowania podatku rozlicza salda podatku na kontach podatków i kompensuje je na koncie rozliczeniowym podatku za dany okres.</span><span class="sxs-lookup"><span data-stu-id="c19ca-104">The settle and post sales tax job settles sales tax balances on the sales tax accounts and offsets them to the sales tax settlement account for a given period.</span></span>

1. <span data-ttu-id="c19ca-105">Wybierz kolejno opcje Podatek > Deklaracje > Podatek > Rozlicz i zaksięguj podatek.</span><span class="sxs-lookup"><span data-stu-id="c19ca-105">Go to Tax > Declarations > Sales tax > Settle and post sales tax.</span></span>
2. <span data-ttu-id="c19ca-106">W polu Okres rozliczeniowy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="c19ca-106">In the Settlement period field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="c19ca-107">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="c19ca-107">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="c19ca-108">W polu Od dnia wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="c19ca-108">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="c19ca-109">Jeśli na stronie Parametry księgi głównej nie zaznaczono opcji Uwzględnij korekty, rozliczenie może być przetwarzane dla różnych wersji.</span><span class="sxs-lookup"><span data-stu-id="c19ca-109">If the Include corrections option is not selected on the General ledger parameters page, the settlement can be processed for different versions.</span></span> <span data-ttu-id="c19ca-110">Oryginał jest pierwszym rozliczeniem w interwale okresu i może być przetwarzany tylko raz w interwale.</span><span class="sxs-lookup"><span data-stu-id="c19ca-110">Original is the first settlement for a period interval and can only processed once for a period interval.</span></span> <span data-ttu-id="c19ca-111">Najnowsze korekty rozliczają transakcje podatkowe, które zostały zaksięgowane po utworzeniu oryginalnej wersji.</span><span class="sxs-lookup"><span data-stu-id="c19ca-111">Latest corrections will settle sales tax transactions which have been posted after the original version has been created.</span></span>   
5. <span data-ttu-id="c19ca-112">W polu Data transakcji wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="c19ca-112">In the Transaction date field, enter a date.</span></span>
6. <span data-ttu-id="c19ca-113">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="c19ca-113">Click OK.</span></span>


