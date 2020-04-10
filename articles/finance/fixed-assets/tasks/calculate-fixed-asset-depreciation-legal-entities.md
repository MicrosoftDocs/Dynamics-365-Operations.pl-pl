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
ms.openlocfilehash: 074a1b80584050302920a95c20fb547523a4866c
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142922"
---
# <a name="calculate-fixed-asset-depreciation-across-legal-entities"></a><span data-ttu-id="001cb-103">Obliczanie amortyzacji środka trwałego we wszystkich firmach</span><span class="sxs-lookup"><span data-stu-id="001cb-103">Calculate fixed asset depreciation across legal entities</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="001cb-104">Amortyzację środków trwałych można uruchomić w wielu firmach w jednym kroku.</span><span class="sxs-lookup"><span data-stu-id="001cb-104">Fixed asset depreciation can be run across legal entities in a single step.</span></span> <span data-ttu-id="001cb-105">Ta procedura przedstawia sposób ustawiania i uruchamiania procesu dla wielu firm.</span><span class="sxs-lookup"><span data-stu-id="001cb-105">This procedure shows you to how set up and run the process for multiple legal entities.</span></span> <span data-ttu-id="001cb-106">Procedura korzysta z roli księgowego i danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="001cb-106">It uses the accountant role and demo data for the USMF legal entity.</span></span>


## <a name="set-up-cross-company-depreciation-run-journals"></a><span data-ttu-id="001cb-107">Ustawianie arkuszy uruchomienia amortyzacji w całej firmie</span><span class="sxs-lookup"><span data-stu-id="001cb-107">Set up cross company depreciation run journals</span></span>
1. <span data-ttu-id="001cb-108">Wybierz kolejno opcje Środki trwałe > Ustawienia > Parametry środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="001cb-108">Go to Fixed assets > Setup > Fixed assets parameters.</span></span>
2. <span data-ttu-id="001cb-109">Rozwiń sekcję Propozycje środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="001cb-109">Expand the Fixed asset proposals section.</span></span>
3. <span data-ttu-id="001cb-110">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="001cb-110">Click Add.</span></span>
4. <span data-ttu-id="001cb-111">W polu Warstwa księgowania wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="001cb-111">In the Posting layer field, enter or select a value.</span></span>
5. <span data-ttu-id="001cb-112">Wprowadź lub wybierz wartość w polu Nazwa arkusza.</span><span class="sxs-lookup"><span data-stu-id="001cb-112">In the Journal name field, enter or select a value.</span></span>
    * <span data-ttu-id="001cb-113">Powtórz ustawianie arkusza na stronie Parametry środków trwałych w każdej firmie.</span><span class="sxs-lookup"><span data-stu-id="001cb-113">Repeat the journal setup on the Fixed asset parameters page in each legal entity.</span></span>  

## <a name="depreciation-run"></a><span data-ttu-id="001cb-114">Uruchomienie amortyzacji</span><span class="sxs-lookup"><span data-stu-id="001cb-114">Depreciation run</span></span>
1. <span data-ttu-id="001cb-115">Wybierz kolejno opcje Środki trwałe > Wpisy w arkuszu > Utwórz propozycję amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="001cb-115">Go to Fixed assets > Journal entries > Create depreciation proposal.</span></span>
2. <span data-ttu-id="001cb-116">W polu Warstwa księgowania wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="001cb-116">In the Posting layer field, enter or select a value.</span></span>
    * <span data-ttu-id="001cb-117">Nazwa arkusza przyjmie wartość domyślną z parametrów środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="001cb-117">The journal name will default from the Fixed asset parameters.</span></span> <span data-ttu-id="001cb-118">Można ją zmienić tutaj dla bieżącej firmy.</span><span class="sxs-lookup"><span data-stu-id="001cb-118">It can be changed here for the current legal entity.</span></span>  
3. <span data-ttu-id="001cb-119">Wprowadź datę w polu Do dnia.</span><span class="sxs-lookup"><span data-stu-id="001cb-119">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="001cb-120">Wybierz firmy, które mają zostać uwzględnione w uruchomieniu amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="001cb-120">Select the legal entities to be included in the depreciation run.</span></span>  
    * <span data-ttu-id="001cb-121">Na liście będą widoczne tylko firmy z arkuszami ustawionymi dla propozycji środków trwałych na stronie Parametry środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="001cb-121">Only legal entities with journals set up for Fixed asset proposals on the Fixed asset parameters page will be shown in the list.</span></span>  
4. <span data-ttu-id="001cb-122">Wybierz opcję Tak w polu Zaksięguj arkusze.</span><span class="sxs-lookup"><span data-stu-id="001cb-122">Select Yes in the Post journals field.</span></span>
    * <span data-ttu-id="001cb-123">Pola filtrowania obejmują wszystkie środki trwałe, grupy i księgi dla firm wybranych do tego uruchomienia amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="001cb-123">Filtering fields include all fixed assets, groups, and books for the legal entities selected for this depreciation run.</span></span>  
    * <span data-ttu-id="001cb-124">Opcja Przetwarzanie wsadowe jest domyślnie włączona.</span><span class="sxs-lookup"><span data-stu-id="001cb-124">The Batch processing option is enabled by default.</span></span> <span data-ttu-id="001cb-125">Gdy ta opcja jest włączona, tworzenie i księgowanie arkusza amortyzacji zostanie uruchomione w tle.</span><span class="sxs-lookup"><span data-stu-id="001cb-125">When this option is enabled, the depreciation journal creation and posting will run in the background.</span></span>  
5. <span data-ttu-id="001cb-126">Kliknij opcję Utwórz arkusz.</span><span class="sxs-lookup"><span data-stu-id="001cb-126">Click Create journal.</span></span>
6. <span data-ttu-id="001cb-127">Wybierz kolejno opcje Środki trwałe > Wpisy w arkuszu > Arkusz środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="001cb-127">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>

