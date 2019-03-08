---
title: Tworzenie typów zdobywania zamówień i kryteriów punktowania dla ZO
description: W tym przewodniku pokazano, jak utworzyć typ zdobywania zamówień i skojarzyć go z metodą punktowania.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchRFQSolicitationType, PurchRFQCaseTableListPage, PurchCreateRFQCase, PurchRFQCaseTable, PurchRFQScoringRFQCaseCriteria, PurchRFQScoringCriteriaCopy
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 14fd7d0bfa17427883f97c5e0a72044016d4965e
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "344623"
---
# <a name="create-solicitation-types-and-scoring-criteria-for-rfqs"></a><span data-ttu-id="66788-103">Tworzenie typów zdobywania zamówień i kryteriów punktowania dla ZO</span><span class="sxs-lookup"><span data-stu-id="66788-103">Create solicitation types and scoring criteria for RFQs</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="66788-104">W tym przewodniku pokazano, jak utworzyć typ zdobywania zamówień i skojarzyć go z metodą punktowania.</span><span class="sxs-lookup"><span data-stu-id="66788-104">This guide shows you how to create a solicitation type and associate this with a scoring method.</span></span> <span data-ttu-id="66788-105">Pokazano także sposób użycia typu zdobywania zamówień w zapytaniu ofertowym (ZO), w następstwie czego jest ustawiana domyślna metoda punktowania.</span><span class="sxs-lookup"><span data-stu-id="66788-105">It also shows how to use the solicitation type on a request for quotation (RFQ) which then sets the default scoring method.</span></span> <span data-ttu-id="66788-106">Te zadania zazwyczaj wykonuje menedżer ds. zakupów.</span><span class="sxs-lookup"><span data-stu-id="66788-106">These tasks would typically be carried out by a purchasing manager.</span></span> <span data-ttu-id="66788-107">Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="66788-107">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="66788-108">Przed rozpoczęciem trzeba zapewnić dostępność metody punktowania.</span><span class="sxs-lookup"><span data-stu-id="66788-108">You need to have a scoring method available before you start.</span></span>


## <a name="create-a-solicitation-type"></a><span data-ttu-id="66788-109">Tworzenie typu zdobywania zamówień</span><span class="sxs-lookup"><span data-stu-id="66788-109">Create a solicitation type</span></span>
1. <span data-ttu-id="66788-110">Wybierz kolejno opcje Zaopatrzenie i sourcing > Ustawienia > Zapytanie ofertowe > Typ zdobywania zamówień.</span><span class="sxs-lookup"><span data-stu-id="66788-110">Go to Procurement and sourcing > Setup > Request for quotation > Solicitation type.</span></span>
2. <span data-ttu-id="66788-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="66788-111">Click New.</span></span>
3. <span data-ttu-id="66788-112">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="66788-112">In the Name field, type a value.</span></span>
4. <span data-ttu-id="66788-113">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="66788-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="66788-114">W polu Metoda punktowa wybierz metodę punktowania, której chcesz używać dla tego typu zdobywania zamówień.</span><span class="sxs-lookup"><span data-stu-id="66788-114">In the Scoring method field, select the scoring method that you want to use for this solicitation type.</span></span>
6. <span data-ttu-id="66788-115">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="66788-115">Click Save.</span></span>
7. <span data-ttu-id="66788-116">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="66788-116">Close the page.</span></span>

## <a name="use-the-solicitation-type"></a><span data-ttu-id="66788-117">Używanie typu zdobywania zamówień</span><span class="sxs-lookup"><span data-stu-id="66788-117">Use the solicitation type</span></span>
1. <span data-ttu-id="66788-118">Wybierz kolejno opcje Zaopatrzenie i sourcing > Zapytania ofertowe > Wszystkie zapytania ofertowe.</span><span class="sxs-lookup"><span data-stu-id="66788-118">Go to Procurement and sourcing > Requests for quotations > All requests for quotations.</span></span>
2. <span data-ttu-id="66788-119">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="66788-119">Click New.</span></span>
3. <span data-ttu-id="66788-120">W polu Typ zdobywania zamówień wybierz nowo utworzony typ zdobywania zamówień.</span><span class="sxs-lookup"><span data-stu-id="66788-120">In the Solicitation type field, select the solicitation type that you have just created.</span></span> 
    *   
4. <span data-ttu-id="66788-121">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="66788-121">Click OK.</span></span>
5. <span data-ttu-id="66788-122">Kliknij opcję Kryteria punktowania.</span><span class="sxs-lookup"><span data-stu-id="66788-122">Click Scoring criteria.</span></span>
    * <span data-ttu-id="66788-123">Wyświetlane kryteria punktowania pochodzą z metody punktowania skojarzonej z typem zdobywania zamówień.</span><span class="sxs-lookup"><span data-stu-id="66788-123">The scoring criteria that are shown are the ones from the scoring method that you associated with the solicitation type.</span></span> <span data-ttu-id="66788-124">Na tej stronie można dodawać i usuwać kryteria.</span><span class="sxs-lookup"><span data-stu-id="66788-124">You can choose to add or delete criteria on this page.</span></span> <span data-ttu-id="66788-125">Istnieje również możliwość dodawania nowych kryteriów przez ich kopiowanie z innych metod punktowania.</span><span class="sxs-lookup"><span data-stu-id="66788-125">It's also possible to add new criteria by copying them from other scoring methods.</span></span>  
6. <span data-ttu-id="66788-126">Kliknij opcję Kopiowanie kryteriów.</span><span class="sxs-lookup"><span data-stu-id="66788-126">Click Copy criteria.</span></span>
7. <span data-ttu-id="66788-127">W polu Metoda punktowa wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="66788-127">In the Scoring method field, enter or select a value.</span></span>
8. <span data-ttu-id="66788-128">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="66788-128">Click OK.</span></span>
9. <span data-ttu-id="66788-129">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="66788-129">Close the page.</span></span>

