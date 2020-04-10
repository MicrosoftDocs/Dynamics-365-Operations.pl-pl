---
title: Tworzenie płatności podatku
description: Zadanie rozliczenia i księgowania podatku rozlicza salda podatku na kontach podatków i kompensuje je na koncie rozliczeniowym podatku za dany okres.
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
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 99059a8e5d6f4bf125266ad2a98cb73751529e6b
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3139934"
---
# <a name="create-a-sales-tax-payment"></a><span data-ttu-id="3cf7e-103">Tworzenie płatności podatku</span><span class="sxs-lookup"><span data-stu-id="3cf7e-103">Create a sales tax payment</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3cf7e-104">Zadanie rozliczenia i księgowania podatku rozlicza salda podatku na kontach podatków i kompensuje je na koncie rozliczeniowym podatku za dany okres.</span><span class="sxs-lookup"><span data-stu-id="3cf7e-104">The settle and post sales tax job settles sales tax balances on the sales tax accounts and offsets them to the sales tax settlement account for a given period.</span></span>

1. <span data-ttu-id="3cf7e-105">Wybierz kolejno opcje Podatek > Deklaracje > Podatek > Rozlicz i zaksięguj podatek.</span><span class="sxs-lookup"><span data-stu-id="3cf7e-105">Go to Tax > Declarations > Sales tax > Settle and post sales tax.</span></span>
2. <span data-ttu-id="3cf7e-106">W polu Okres rozliczeniowy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="3cf7e-106">In the Settlement period field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="3cf7e-107">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="3cf7e-107">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="3cf7e-108">W polu Od dnia wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="3cf7e-108">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="3cf7e-109">Jeśli na stronie Parametry księgi głównej nie zaznaczono opcji Uwzględnij korekty, rozliczenie może być przetwarzane dla różnych wersji.</span><span class="sxs-lookup"><span data-stu-id="3cf7e-109">If the Include corrections option is not selected on the General ledger parameters page, the settlement can be processed for different versions.</span></span> <span data-ttu-id="3cf7e-110">Oryginał jest pierwszym rozliczeniem w interwale okresu i może być przetwarzany tylko raz w interwale.</span><span class="sxs-lookup"><span data-stu-id="3cf7e-110">Original is the first settlement for a period interval and can only processed once for a period interval.</span></span> <span data-ttu-id="3cf7e-111">Najnowsze korekty rozliczają transakcje podatkowe, które zostały zaksięgowane po utworzeniu oryginalnej wersji.</span><span class="sxs-lookup"><span data-stu-id="3cf7e-111">Latest corrections will settle sales tax transactions which have been posted after the original version has been created.</span></span>   
5. <span data-ttu-id="3cf7e-112">W polu Data transakcji wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="3cf7e-112">In the Transaction date field, enter a date.</span></span>
6. <span data-ttu-id="3cf7e-113">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3cf7e-113">Click OK.</span></span>

