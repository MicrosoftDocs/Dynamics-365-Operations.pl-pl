---
title: Obliczanie amortyzacji środka trwałego we wszystkich firmach
description: Amortyzację środków trwałych można uruchomić w wielu firmach w jednym kroku.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetParameters, AssetProposalDepreciation, DefaultDashboard, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 500aa71e57f9c1ac8d1a2a080468381bc248741c
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1840104"
---
# <a name="calculate-fixed-asset-depreciation-across-legal-entities"></a><span data-ttu-id="dbb06-103">Obliczanie amortyzacji środka trwałego we wszystkich firmach</span><span class="sxs-lookup"><span data-stu-id="dbb06-103">Calculate fixed asset depreciation across legal entities</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="dbb06-104">Amortyzację środków trwałych można uruchomić w wielu firmach w jednym kroku.</span><span class="sxs-lookup"><span data-stu-id="dbb06-104">Fixed asset depreciation can be run across legal entities in a single step.</span></span> <span data-ttu-id="dbb06-105">Ta procedura przedstawia sposób ustawiania i uruchamiania procesu dla wielu firm.</span><span class="sxs-lookup"><span data-stu-id="dbb06-105">This procedure shows you to how set up and run the process for multiple legal entities.</span></span> <span data-ttu-id="dbb06-106">Procedura korzysta z roli księgowego i danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="dbb06-106">It uses the accountant role and demo data for the USMF legal entity.</span></span>


## <a name="set-up-cross-company-depreciation-run-journals"></a><span data-ttu-id="dbb06-107">Ustawianie arkuszy uruchomienia amortyzacji w całej firmie</span><span class="sxs-lookup"><span data-stu-id="dbb06-107">Set up cross company depreciation run journals</span></span>
1. <span data-ttu-id="dbb06-108">Wybierz kolejno opcje Środki trwałe > Ustawienia > Parametry środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="dbb06-108">Go to Fixed assets > Setup > Fixed assets parameters.</span></span>
2. <span data-ttu-id="dbb06-109">Rozwiń sekcję Propozycje środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="dbb06-109">Expand the Fixed asset proposals section.</span></span>
3. <span data-ttu-id="dbb06-110">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="dbb06-110">Click Add.</span></span>
4. <span data-ttu-id="dbb06-111">W polu Warstwa księgowania wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="dbb06-111">In the Posting layer field, enter or select a value.</span></span>
5. <span data-ttu-id="dbb06-112">Wprowadź lub wybierz wartość w polu Nazwa arkusza.</span><span class="sxs-lookup"><span data-stu-id="dbb06-112">In the Journal name field, enter or select a value.</span></span>
    * <span data-ttu-id="dbb06-113">Powtórz ustawianie arkusza na stronie Parametry środków trwałych w każdej firmie.</span><span class="sxs-lookup"><span data-stu-id="dbb06-113">Repeat the journal setup on the Fixed asset parameters page in each legal entity.</span></span>  

## <a name="depreciation-run"></a><span data-ttu-id="dbb06-114">Uruchomienie amortyzacji</span><span class="sxs-lookup"><span data-stu-id="dbb06-114">Depreciation run</span></span>
1. <span data-ttu-id="dbb06-115">Wybierz kolejno opcje Środki trwałe > Wpisy w arkuszu > Utwórz propozycję amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="dbb06-115">Go to Fixed assets > Journal entries > Create depreciation proposal.</span></span>
2. <span data-ttu-id="dbb06-116">W polu Warstwa księgowania wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="dbb06-116">In the Posting layer field, enter or select a value.</span></span>
    * <span data-ttu-id="dbb06-117">Nazwa arkusza przyjmie wartość domyślną z parametrów środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="dbb06-117">The journal name will default from the Fixed asset parameters.</span></span> <span data-ttu-id="dbb06-118">Można ją zmienić tutaj dla bieżącej firmy.</span><span class="sxs-lookup"><span data-stu-id="dbb06-118">It can be changed here for the current legal entity.</span></span>  
3. <span data-ttu-id="dbb06-119">Wprowadź datę w polu Do dnia.</span><span class="sxs-lookup"><span data-stu-id="dbb06-119">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="dbb06-120">Wybierz firmy, które mają zostać uwzględnione w uruchomieniu amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="dbb06-120">Select the legal entities to be included in the depreciation run.</span></span>  
    * <span data-ttu-id="dbb06-121">Na liście będą widoczne tylko firmy z arkuszami ustawionymi dla propozycji środków trwałych na stronie Parametry środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="dbb06-121">Only legal entities with journals set up for Fixed asset proposals on the Fixed asset parameters page will be shown in the list.</span></span>  
4. <span data-ttu-id="dbb06-122">Wybierz opcję Tak w polu Zaksięguj arkusze.</span><span class="sxs-lookup"><span data-stu-id="dbb06-122">Select Yes in the Post journals field.</span></span>
    * <span data-ttu-id="dbb06-123">Pola filtrowania obejmują wszystkie środki trwałe, grupy i księgi dla firm wybranych do tego uruchomienia amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="dbb06-123">Filtering fields include all fixed assets, groups, and books for the legal entities selected for this depreciation run.</span></span>  
    * <span data-ttu-id="dbb06-124">Opcja Przetwarzanie wsadowe jest domyślnie włączona.</span><span class="sxs-lookup"><span data-stu-id="dbb06-124">The Batch processing option is enabled by default.</span></span> <span data-ttu-id="dbb06-125">Gdy ta opcja jest włączona, tworzenie i księgowanie arkusza amortyzacji zostanie uruchomione w tle.</span><span class="sxs-lookup"><span data-stu-id="dbb06-125">When this option is enabled, the depreciation journal creation and posting will run in the background.</span></span>  
5. <span data-ttu-id="dbb06-126">Kliknij opcję Utwórz arkusz.</span><span class="sxs-lookup"><span data-stu-id="dbb06-126">Click Create journal.</span></span>
6. <span data-ttu-id="dbb06-127">Wybierz kolejno opcje Środki trwałe > Wpisy w arkuszu > Arkusz środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="dbb06-127">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>

