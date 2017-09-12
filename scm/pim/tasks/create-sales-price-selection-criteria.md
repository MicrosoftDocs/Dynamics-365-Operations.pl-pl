--- 
title: "Tworzenie kryteriów wyboru ceny sprzedaży"
description: "Ta procedura pokazuje, jak utworzyć kryterium wyboru ceny sprzedaży dla modeli ceny sprzedaży opartych na atrybutach."
author: BibiSp
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: ce805b0bf43c931ebca13720d43754c18094fc85
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="create-sales-price-selection-criteria"></a><span data-ttu-id="7a372-103">Tworzenie kryteriów wyboru ceny sprzedaży</span><span class="sxs-lookup"><span data-stu-id="7a372-103">Create sales price selection criteria</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7a372-104">Ta procedura pokazuje, jak utworzyć kryterium wyboru ceny sprzedaży dla modeli ceny sprzedaży opartych na atrybutach.</span><span class="sxs-lookup"><span data-stu-id="7a372-104">This procedure shows how to create a sales price selection criterion for attribute-based sales price models.</span></span> <span data-ttu-id="7a372-105">Procedura wymaga dostępności co najmniej jednego modelu ceny sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="7a372-105">This procedure requires that at least one sales price model be available.</span></span> <span data-ttu-id="7a372-106">W tym przykładzie jest używany model ceny będący modelem cen sprzedaży rozwiązania Głośnik w firmie demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="7a372-106">This example uses the price model for the Speaker solution sales price model in the USMF demo data company.</span></span> <span data-ttu-id="7a372-107">Zazwyczaj procedurę wykonuje menedżer produktu.</span><span class="sxs-lookup"><span data-stu-id="7a372-107">Typically, a product manager uses this procedure.</span></span>


## <a name="add-a-new-criterion-for-an-existing-sales-price-model"></a><span data-ttu-id="7a372-108">Dodawanie nowego kryterium dla istniejącego modelu ceny sprzedaży</span><span class="sxs-lookup"><span data-stu-id="7a372-108">Add a new criterion for an existing sales price model</span></span>
1. <span data-ttu-id="7a372-109">Kliknij opcję Definicja modelu wariantu produktu.</span><span class="sxs-lookup"><span data-stu-id="7a372-109">Click Product variant model definition.</span></span>
2. <span data-ttu-id="7a372-110">Kliknij opcję Modele konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="7a372-110">Click Product configuration models.</span></span>
3. <span data-ttu-id="7a372-111">Na liście zaznacz wiersz modelu produktu rozwiązania Głośnika, ale nie klikaj łącza z nazwą modelu.</span><span class="sxs-lookup"><span data-stu-id="7a372-111">In the list, select the row for the Speaker solution product model, but don’t click the link for the model name.</span></span>
4. <span data-ttu-id="7a372-112">W okienku akcji kliknij pozycję Model.</span><span class="sxs-lookup"><span data-stu-id="7a372-112">On the Action Pane, click Model.</span></span>
5. <span data-ttu-id="7a372-113">Kliknij opcję Kryteria modelu ceny.</span><span class="sxs-lookup"><span data-stu-id="7a372-113">Click Price model criteria.</span></span>
6. <span data-ttu-id="7a372-114">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7a372-114">Click New.</span></span>
7. <span data-ttu-id="7a372-115">W polu Nazwa wpisz „Grupa odbiorców 10”.</span><span class="sxs-lookup"><span data-stu-id="7a372-115">In the Name field, type ‘Customer group 10’.</span></span>
    * <span data-ttu-id="7a372-116">Nazwa kryterium modelu ceny służy do identyfikowania bazowych kryteriów wyboru.</span><span class="sxs-lookup"><span data-stu-id="7a372-116">The name of the price model criterion is used to help identify the underlying selection criteria.</span></span>  
8. <span data-ttu-id="7a372-117">Wprowadź lub wybierz wartość w polu Model ceny.</span><span class="sxs-lookup"><span data-stu-id="7a372-117">In the Price model field, enter or select a value.</span></span>
9. <span data-ttu-id="7a372-118">W polu Typ zamówienia zaznacz opcję Zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="7a372-118">In the Order type field, select Sales order.</span></span>
    * <span data-ttu-id="7a372-119">Typ zamówienia określa pola bazy danych, które będą dostępne dla kwerendy wyboru.</span><span class="sxs-lookup"><span data-stu-id="7a372-119">The order type determines the database fields that will be available for the selection query.</span></span>  
10. <span data-ttu-id="7a372-120">W polu Obowiązuje od wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="7a372-120">In the Valid from field, enter a date.</span></span>
11. <span data-ttu-id="7a372-121">W polu Data ważności wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="7a372-121">In the Expire by field, enter a date.</span></span>
12. <span data-ttu-id="7a372-122">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="7a372-122">Click Save.</span></span>

## <a name="create-the-query-for-the-selection-criteria"></a><span data-ttu-id="7a372-123">Tworzenie zapytania dla kryteriów wyboru</span><span class="sxs-lookup"><span data-stu-id="7a372-123">Create the query for the selection criteria</span></span>
1. <span data-ttu-id="7a372-124">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="7a372-124">Click Edit.</span></span>
2. <span data-ttu-id="7a372-125">W polu Tabela wybierz opcję Odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="7a372-125">In the Table field, select Customers.</span></span> 
3. <span data-ttu-id="7a372-126">W polu Pole wybierz opcję Grupa odbiorców.</span><span class="sxs-lookup"><span data-stu-id="7a372-126">In the Field field, select Customer group.</span></span>
    * <span data-ttu-id="7a372-127">W tym przykładzie jako kryteriów wyboru użyjemy określonej grupy odbiorców.</span><span class="sxs-lookup"><span data-stu-id="7a372-127">In this example, we will use a specific customer group for the selection criteria.</span></span>  
4. <span data-ttu-id="7a372-128">W polu Kryteria wybierz opcję Grupa odbiorców 10.</span><span class="sxs-lookup"><span data-stu-id="7a372-128">In the Criteria field, select Customer group 10.</span></span> 
5. <span data-ttu-id="7a372-129">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="7a372-129">Click OK.</span></span>


