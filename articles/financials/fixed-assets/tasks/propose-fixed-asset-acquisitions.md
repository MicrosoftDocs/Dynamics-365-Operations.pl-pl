--- 
title: "Proponowanie nabycia środka trwałego"
description: "W tej procedurze pokazano sposób nabywania środka trwałego przy użyciu propozycji nabycia zdefiniowanej w arkuszu środków trwałych."
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetTable, AssetBook, LedgerJournalTable, LedgerJournalTransAsset, SysQueryForm
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 1891206bb266b126eccfa789b8c8062c9bfa688b
ms.contentlocale: pl-pl
ms.lasthandoff: 09/14/2018

---
# <a name="propose-fixed-asset-acquisitions"></a><span data-ttu-id="e4f68-103">Proponowanie nabycia środka trwałego</span><span class="sxs-lookup"><span data-stu-id="e4f68-103">Propose fixed asset acquisitions</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e4f68-104">W tej procedurze pokazano sposób nabywania środka trwałego przy użyciu propozycji nabycia zdefiniowanej w arkuszu środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="e4f68-104">This procedure shows how to acquire a fixed asset using the acquisition proposal in the Fixed assets journal.</span></span> <span data-ttu-id="e4f68-105">Procedura korzysta z roli księgowego i danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="e4f68-105">It uses the accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="e4f68-106">Wybierz kolejno opcje Środki trwałe > Wpisy w arkuszu > Arkusz środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="e4f68-106">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>
2. <span data-ttu-id="e4f68-107">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e4f68-107">Click New.</span></span>
3. <span data-ttu-id="e4f68-108">W polu Nazwa wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e4f68-108">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="e4f68-109">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="e4f68-109">Click Lines.</span></span>
5. <span data-ttu-id="e4f68-110">Kliknij opcję Propozycje.</span><span class="sxs-lookup"><span data-stu-id="e4f68-110">Click Proposals.</span></span>
6. <span data-ttu-id="e4f68-111">Kliknij opcję Propozycja nabycia.</span><span class="sxs-lookup"><span data-stu-id="e4f68-111">Click Acquisition proposal.</span></span>
7. <span data-ttu-id="e4f68-112">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="e4f68-112">Click Filter.</span></span>
8. <span data-ttu-id="e4f68-113">Kliknij przycisk Resetuj, aby wyczyścić poprzednie wartości.</span><span class="sxs-lookup"><span data-stu-id="e4f68-113">Click Reset to clear out previous values.</span></span>
9. <span data-ttu-id="e4f68-114">Zaznacz wiersz Numer środka trwałego.</span><span class="sxs-lookup"><span data-stu-id="e4f68-114">Select the Fixed asset number row.</span></span>
10. <span data-ttu-id="e4f68-115">W polu Kryteria wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e4f68-115">In the Criteria field, enter or select a value.</span></span>
    * <span data-ttu-id="e4f68-116">Skonfiguruj pozostałe kryteria środków trwałych, które chcesz nabyć za pomocą tej propozycji.</span><span class="sxs-lookup"><span data-stu-id="e4f68-116">Set the remaining criteria for the fixed assets that you want to acquire with this proposal.</span></span>  
11. <span data-ttu-id="e4f68-117">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="e4f68-117">Click OK.</span></span>
12. <span data-ttu-id="e4f68-118">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="e4f68-118">Click OK.</span></span>
    * <span data-ttu-id="e4f68-119">Sprawdź utworzone wiersze transakcji.</span><span class="sxs-lookup"><span data-stu-id="e4f68-119">Verify the transaction lines created.</span></span>  
    * <span data-ttu-id="e4f68-120">W propozycji nabycia zostaną uwzględnione tylko środki trwałe, które w księdze mają ustawioną datę nabycia i cenę nabycia.</span><span class="sxs-lookup"><span data-stu-id="e4f68-120">Only fixed assets with the acquisition date and acquisition price set on the book will be included in the acquisition proposal.</span></span>  
13. <span data-ttu-id="e4f68-121">Kliknij kartę Księgi.</span><span class="sxs-lookup"><span data-stu-id="e4f68-121">Click the Books tab.</span></span>
14. <span data-ttu-id="e4f68-122">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="e4f68-122">Click Post.</span></span>


