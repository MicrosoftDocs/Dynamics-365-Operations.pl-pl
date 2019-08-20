---
title: Konfigurowanie podwyższenia amortyzacji
description: W tej procedurze pokazano, jak utworzyć specjalny odpis amortyzacyjny i skojarzyć go z księgą środków trwałych.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBonus, AssetGroup, AssetGroupBookSetup, AssetGroupSetupBonus
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 788cddf4d822fe3d3d6a33e83d7b30f32f4b6b9c
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1839888"
---
# <a name="set-up-bonus-depreciation"></a><span data-ttu-id="e6687-103">Konfigurowanie podwyższenia amortyzacji</span><span class="sxs-lookup"><span data-stu-id="e6687-103">Set up bonus depreciation</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e6687-104">W tej procedurze pokazano, jak utworzyć specjalny odpis amortyzacyjny i skojarzyć go z księgą środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="e6687-104">This procedure shows how to create a special depreciation allowance and associate it with a fixed asset book.</span></span> <span data-ttu-id="e6687-105">Procedura korzysta z roli księgowego i danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="e6687-105">It uses the accountant role and demo data for the USMF legal entity.</span></span>


## <a name="create-a-special-depreciation-allowance"></a><span data-ttu-id="e6687-106">Tworzenie specjalnego odpisu amortyzacyjnego</span><span class="sxs-lookup"><span data-stu-id="e6687-106">Create a special depreciation allowance</span></span>
1. <span data-ttu-id="e6687-107">Wybierz kolejno opcje Środki trwałe > Ustawienia > Specjalny odpis amortyzacyjny.</span><span class="sxs-lookup"><span data-stu-id="e6687-107">Go to Fixed assets > Setup > Special depreciation allowance.</span></span>
2. <span data-ttu-id="e6687-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e6687-108">Click New.</span></span>
3. <span data-ttu-id="e6687-109">W polu Specjalny odpis amortyzacyjny wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e6687-109">In the Special depreciation allowance field, type a value.</span></span>
4. <span data-ttu-id="e6687-110">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="e6687-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="e6687-111">W polu Wartość procentowa wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="e6687-111">In the Percentage field, enter a number.</span></span>
    * <span data-ttu-id="e6687-112">Jeśli nie wskazano wartości procentowej, ustaw kwotę.</span><span class="sxs-lookup"><span data-stu-id="e6687-112">If a percentage was not indicated, set an amount.</span></span>  

## <a name="associate-a-special-depreciation-allowance-with-a-fixed-asset-group-book"></a><span data-ttu-id="e6687-113">Kojarzenie specjalnego odpisu amortyzacyjnego z księgą grupy środków trwałych</span><span class="sxs-lookup"><span data-stu-id="e6687-113">Associate a special depreciation allowance with a fixed asset group book</span></span>
1. <span data-ttu-id="e6687-114">Wybierz kolejno opcje Środki trwałe > Ustawienia > Grupy środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="e6687-114">Go to Fixed assets > Setup > Fixed asset groups.</span></span>
2. <span data-ttu-id="e6687-115">Na liście zaznacz grupę środków trwałych skojarzoną ze specjalnym odpisem amortyzacyjnym.</span><span class="sxs-lookup"><span data-stu-id="e6687-115">In the list, select the fixed asset group associated with the special depreciation allowance.</span></span>
3. <span data-ttu-id="e6687-116">Kliknij opcję Księgi.</span><span class="sxs-lookup"><span data-stu-id="e6687-116">Click Books.</span></span>
4. <span data-ttu-id="e6687-117">Na liście zaznacz księgę skojarzoną ze specjalnym odpisem amortyzacyjnym.</span><span class="sxs-lookup"><span data-stu-id="e6687-117">In the list, select the book that is associated with the special depreciation allowance.</span></span>
5. <span data-ttu-id="e6687-118">Kliknij opcję Specjalny odpis amortyzacyjny.</span><span class="sxs-lookup"><span data-stu-id="e6687-118">Click Special depreciation allowance.</span></span>
6. <span data-ttu-id="e6687-119">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e6687-119">Click New.</span></span>
7. <span data-ttu-id="e6687-120">W polu Specjalny odpis amortyzacyjny wpisz lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e6687-120">In the Special depreciation allowance field, enter or select a value.</span></span>
    * <span data-ttu-id="e6687-121">Domyślna wartość ustawienia Wartość procentowa lub Kwota pochodzi z konfiguracji specjalnego odpisu amortyzacyjnego.</span><span class="sxs-lookup"><span data-stu-id="e6687-121">The default for Percentage or Amount comes from the special depreciation allowance setup.</span></span>  
8. <span data-ttu-id="e6687-122">W polu Priorytet wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="e6687-122">In the Priority field, enter a number.</span></span>

