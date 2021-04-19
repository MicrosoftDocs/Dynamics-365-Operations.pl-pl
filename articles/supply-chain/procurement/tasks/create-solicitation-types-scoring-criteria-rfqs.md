---
title: Tworzenie typów zdobywania zamówień i kryteriów punktowania dla ZO
description: W tym przewodniku pokazano, jak utworzyć typ zdobywania zamówień i skojarzyć go z metodą punktowania.
author: kamaybac
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchRFQSolicitationType, PurchRFQCaseTableListPage, PurchCreateRFQCase, PurchRFQCaseTable, PurchRFQScoringRFQCaseCriteria, PurchRFQScoringCriteriaCopy
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2d28cb4bf20ba50aae6b85e835339e2df711c99d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5812069"
---
# <a name="create-solicitation-types-and-scoring-criteria-for-rfqs"></a><span data-ttu-id="d5074-103">Tworzenie typów zdobywania zamówień i kryteriów punktowania dla ZO</span><span class="sxs-lookup"><span data-stu-id="d5074-103">Create solicitation types and scoring criteria for RFQs</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d5074-104">W tym przewodniku pokazano, jak utworzyć typ zdobywania zamówień i skojarzyć go z metodą punktowania.</span><span class="sxs-lookup"><span data-stu-id="d5074-104">This guide shows you how to create a solicitation type and associate this with a scoring method.</span></span> <span data-ttu-id="d5074-105">Pokazano także sposób użycia typu zdobywania zamówień w zapytaniu ofertowym (ZO), w następstwie czego jest ustawiana domyślna metoda punktowania.</span><span class="sxs-lookup"><span data-stu-id="d5074-105">It also shows how to use the solicitation type on a request for quotation (RFQ) which then sets the default scoring method.</span></span> <span data-ttu-id="d5074-106">Te zadania zazwyczaj wykonuje menedżer ds. zakupów.</span><span class="sxs-lookup"><span data-stu-id="d5074-106">These tasks would typically be carried out by a purchasing manager.</span></span> <span data-ttu-id="d5074-107">Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="d5074-107">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="d5074-108">Przed rozpoczęciem trzeba zapewnić dostępność metody punktowania.</span><span class="sxs-lookup"><span data-stu-id="d5074-108">You need to have a scoring method available before you start.</span></span>


## <a name="create-a-solicitation-type"></a><span data-ttu-id="d5074-109">Tworzenie typu zdobywania zamówień</span><span class="sxs-lookup"><span data-stu-id="d5074-109">Create a solicitation type</span></span>
1. <span data-ttu-id="d5074-110">Wybierz kolejno opcje Zaopatrzenie i sourcing > Ustawienia > Zapytanie ofertowe > Typ zdobywania zamówień.</span><span class="sxs-lookup"><span data-stu-id="d5074-110">Go to Procurement and sourcing > Setup > Request for quotation > Solicitation type.</span></span>
2. <span data-ttu-id="d5074-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="d5074-111">Click New.</span></span>
3. <span data-ttu-id="d5074-112">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="d5074-112">In the Name field, type a value.</span></span>
4. <span data-ttu-id="d5074-113">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="d5074-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="d5074-114">W polu Metoda punktowa wybierz metodę punktowania, której chcesz używać dla tego typu zdobywania zamówień.</span><span class="sxs-lookup"><span data-stu-id="d5074-114">In the Scoring method field, select the scoring method that you want to use for this solicitation type.</span></span>
6. <span data-ttu-id="d5074-115">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="d5074-115">Click Save.</span></span>
7. <span data-ttu-id="d5074-116">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d5074-116">Close the page.</span></span>

## <a name="use-the-solicitation-type"></a><span data-ttu-id="d5074-117">Używanie typu zdobywania zamówień</span><span class="sxs-lookup"><span data-stu-id="d5074-117">Use the solicitation type</span></span>
1. <span data-ttu-id="d5074-118">Wybierz kolejno opcje Zaopatrzenie i sourcing > Zapytania ofertowe > Wszystkie zapytania ofertowe.</span><span class="sxs-lookup"><span data-stu-id="d5074-118">Go to Procurement and sourcing > Requests for quotations > All requests for quotations.</span></span>
2. <span data-ttu-id="d5074-119">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="d5074-119">Click New.</span></span>
3. <span data-ttu-id="d5074-120">W polu Typ zdobywania zamówień wybierz nowo utworzony typ zdobywania zamówień.</span><span class="sxs-lookup"><span data-stu-id="d5074-120">In the Solicitation type field, select the solicitation type that you have just created.</span></span> 
    *   
4. <span data-ttu-id="d5074-121">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="d5074-121">Click OK.</span></span>
5. <span data-ttu-id="d5074-122">Kliknij opcję Kryteria punktowania.</span><span class="sxs-lookup"><span data-stu-id="d5074-122">Click Scoring criteria.</span></span>
    * <span data-ttu-id="d5074-123">Wyświetlane kryteria punktowania pochodzą z metody punktowania skojarzonej z typem zdobywania zamówień.</span><span class="sxs-lookup"><span data-stu-id="d5074-123">The scoring criteria that are shown are the ones from the scoring method that you associated with the solicitation type.</span></span> <span data-ttu-id="d5074-124">Na tej stronie można dodawać i usuwać kryteria.</span><span class="sxs-lookup"><span data-stu-id="d5074-124">You can choose to add or delete criteria on this page.</span></span> <span data-ttu-id="d5074-125">Istnieje również możliwość dodawania nowych kryteriów przez ich kopiowanie z innych metod punktowania.</span><span class="sxs-lookup"><span data-stu-id="d5074-125">It's also possible to add new criteria by copying them from other scoring methods.</span></span>  
6. <span data-ttu-id="d5074-126">Kliknij opcję Kopiowanie kryteriów.</span><span class="sxs-lookup"><span data-stu-id="d5074-126">Click Copy criteria.</span></span>
7. <span data-ttu-id="d5074-127">W polu Metoda punktowa wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="d5074-127">In the Scoring method field, enter or select a value.</span></span>
8. <span data-ttu-id="d5074-128">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="d5074-128">Click OK.</span></span>
9. <span data-ttu-id="d5074-129">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d5074-129">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]