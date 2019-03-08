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
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b0d72c88d6ba851e96ca07b896630549690e9396
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "321761"
---
# <a name="create-a-sales-tax-payment"></a><span data-ttu-id="199c7-103">Tworzenie płatności podatku</span><span class="sxs-lookup"><span data-stu-id="199c7-103">Create a sales tax payment</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="199c7-104">Zadanie rozliczenia i księgowania podatku rozlicza salda podatku na kontach podatków i kompensuje je na koncie rozliczeniowym podatku za dany okres.</span><span class="sxs-lookup"><span data-stu-id="199c7-104">The settle and post sales tax job settles sales tax balances on the sales tax accounts and offsets them to the sales tax settlement account for a given period.</span></span>

1. <span data-ttu-id="199c7-105">Wybierz kolejno opcje Podatek > Deklaracje > Podatek > Rozlicz i zaksięguj podatek.</span><span class="sxs-lookup"><span data-stu-id="199c7-105">Go to Tax > Declarations > Sales tax > Settle and post sales tax.</span></span>
2. <span data-ttu-id="199c7-106">W polu Okres rozliczeniowy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="199c7-106">In the Settlement period field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="199c7-107">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="199c7-107">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="199c7-108">W polu Od dnia wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="199c7-108">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="199c7-109">Jeśli na stronie Parametry księgi głównej nie zaznaczono opcji Uwzględnij korekty, rozliczenie może być przetwarzane dla różnych wersji.</span><span class="sxs-lookup"><span data-stu-id="199c7-109">If the Include corrections option is not selected on the General ledger parameters page, the settlement can be processed for different versions.</span></span> <span data-ttu-id="199c7-110">Oryginał jest pierwszym rozliczeniem w interwale okresu i może być przetwarzany tylko raz w interwale.</span><span class="sxs-lookup"><span data-stu-id="199c7-110">Original is the first settlement for a period interval and can only processed once for a period interval.</span></span> <span data-ttu-id="199c7-111">Najnowsze korekty rozliczają transakcje podatkowe, które zostały zaksięgowane po utworzeniu oryginalnej wersji.</span><span class="sxs-lookup"><span data-stu-id="199c7-111">Latest corrections will settle sales tax transactions which have been posted after the original version has been created.</span></span>   
5. <span data-ttu-id="199c7-112">W polu Data transakcji wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="199c7-112">In the Transaction date field, enter a date.</span></span>
6. <span data-ttu-id="199c7-113">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="199c7-113">Click OK.</span></span>

