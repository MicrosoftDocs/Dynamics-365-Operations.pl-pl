--- 
title: "Tworzenie typów zdobywania zamówień i kryteriów punktowania dla ZO"
description: "W tym przewodniku pokazano, jak utworzyć typ zdobywania zamówień i skojarzyć go z metodą punktowania."
author: mkirknel
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 095855d552d228375635bdbaa9fca37c47a3b952
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="create-solicitation-types-and-scoring-criteria-for-rfqs"></a><span data-ttu-id="ea37a-103">Tworzenie typów zdobywania zamówień i kryteriów punktowania dla ZO</span><span class="sxs-lookup"><span data-stu-id="ea37a-103">Create solicitation types and scoring criteria for RFQs</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ea37a-104">W tym przewodniku pokazano, jak utworzyć typ zdobywania zamówień i skojarzyć go z metodą punktowania.</span><span class="sxs-lookup"><span data-stu-id="ea37a-104">This guide shows you how to create a solicitation type and associate this with a scoring method.</span></span> <span data-ttu-id="ea37a-105">Pokazano także sposób użycia typu zdobywania zamówień w zapytaniu ofertowym (ZO), w następstwie czego jest ustawiana domyślna metoda punktowania.</span><span class="sxs-lookup"><span data-stu-id="ea37a-105">It also shows how to use the solicitation type on a request for quotation (RFQ) which then sets the default scoring method.</span></span> <span data-ttu-id="ea37a-106">Te zadania zazwyczaj wykonuje menedżer ds. zakupów.</span><span class="sxs-lookup"><span data-stu-id="ea37a-106">These tasks would typically be carried out by a purchasing manager.</span></span> <span data-ttu-id="ea37a-107">Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="ea37a-107">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="ea37a-108">Przed rozpoczęciem trzeba zapewnić dostępność metody punktowania.</span><span class="sxs-lookup"><span data-stu-id="ea37a-108">You need to have a scoring method available before you start.</span></span>


## <a name="create-a-solicitation-type"></a><span data-ttu-id="ea37a-109">Tworzenie typu zdobywania zamówień</span><span class="sxs-lookup"><span data-stu-id="ea37a-109">Create a solicitation type</span></span>
1. <span data-ttu-id="ea37a-110">Wybierz kolejno opcje Zaopatrzenie i sourcing > Ustawienia > Zapytanie ofertowe > Typ zdobywania zamówień.</span><span class="sxs-lookup"><span data-stu-id="ea37a-110">Go to Procurement and sourcing > Setup > Request for quotation > Solicitation type.</span></span>
2. <span data-ttu-id="ea37a-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ea37a-111">Click New.</span></span>
3. <span data-ttu-id="ea37a-112">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ea37a-112">In the Name field, type a value.</span></span>
4. <span data-ttu-id="ea37a-113">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="ea37a-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="ea37a-114">W polu Metoda punktowa wybierz metodę punktowania, której chcesz używać dla tego typu zdobywania zamówień.</span><span class="sxs-lookup"><span data-stu-id="ea37a-114">In the Scoring method field, select the scoring method that you want to use for this solicitation type.</span></span>
6. <span data-ttu-id="ea37a-115">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="ea37a-115">Click Save.</span></span>
7. <span data-ttu-id="ea37a-116">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ea37a-116">Close the page.</span></span>

## <a name="use-the-solicitation-type"></a><span data-ttu-id="ea37a-117">Używanie typu zdobywania zamówień</span><span class="sxs-lookup"><span data-stu-id="ea37a-117">Use the solicitation type</span></span>
1. <span data-ttu-id="ea37a-118">Wybierz kolejno opcje Zaopatrzenie i sourcing > Zapytania ofertowe > Wszystkie zapytania ofertowe.</span><span class="sxs-lookup"><span data-stu-id="ea37a-118">Go to Procurement and sourcing > Requests for quotations > All requests for quotations.</span></span>
2. <span data-ttu-id="ea37a-119">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ea37a-119">Click New.</span></span>
3. <span data-ttu-id="ea37a-120">W polu Typ zdobywania zamówień wybierz nowo utworzony typ zdobywania zamówień.</span><span class="sxs-lookup"><span data-stu-id="ea37a-120">In the Solicitation type field, select the solicitation type that you have just created.</span></span> 
4. <span data-ttu-id="ea37a-121">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ea37a-121">Click OK.</span></span>
5. <span data-ttu-id="ea37a-122">Kliknij opcję Kryteria punktowania.</span><span class="sxs-lookup"><span data-stu-id="ea37a-122">Click Scoring criteria.</span></span>
    * <span data-ttu-id="ea37a-123">Wyświetlane kryteria punktowania pochodzą z metody punktowania skojarzonej z typem zdobywania zamówień.</span><span class="sxs-lookup"><span data-stu-id="ea37a-123">The scoring criteria that are shown are the ones from the scoring method that you associated with the solicitation type.</span></span> <span data-ttu-id="ea37a-124">Na tej stronie można dodawać i usuwać kryteria.</span><span class="sxs-lookup"><span data-stu-id="ea37a-124">You can choose to add or delete criteria on this page.</span></span> <span data-ttu-id="ea37a-125">Istnieje również możliwość dodawania nowych kryteriów przez ich kopiowanie z innych metod punktowania.</span><span class="sxs-lookup"><span data-stu-id="ea37a-125">It's also possible to add new criteria by copying them from other scoring methods.</span></span>  
6. <span data-ttu-id="ea37a-126">Kliknij opcję Kopiowanie kryteriów.</span><span class="sxs-lookup"><span data-stu-id="ea37a-126">Click Copy criteria.</span></span>
7. <span data-ttu-id="ea37a-127">W polu Metoda punktowa wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ea37a-127">In the Scoring method field, enter or select a value.</span></span>
8. <span data-ttu-id="ea37a-128">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ea37a-128">Click OK.</span></span>
9. <span data-ttu-id="ea37a-129">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ea37a-129">Close the page.</span></span>


