---
title: Tworzenie kryteriów wyboru ceny sprzedaży
description: Ta procedura pokazuje, jak utworzyć kryterium wyboru ceny sprzedaży dla modeli ceny sprzedaży opartych na atrybutach.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelSelectionCriteria, SysQueryForm, SysQueryTableLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 69d22c3321beaa2667ee20bff00acd746714b993
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920538"
---
# <a name="create-sales-price-selection-criteria"></a><span data-ttu-id="82b9a-103">Tworzenie kryteriów wyboru ceny sprzedaży</span><span class="sxs-lookup"><span data-stu-id="82b9a-103">Create sales price selection criteria</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="82b9a-104">Ta procedura pokazuje, jak utworzyć kryterium wyboru ceny sprzedaży dla modeli ceny sprzedaży opartych na atrybutach.</span><span class="sxs-lookup"><span data-stu-id="82b9a-104">This procedure shows how to create a sales price selection criterion for attribute-based sales price models.</span></span> <span data-ttu-id="82b9a-105">Procedura wymaga dostępności co najmniej jednego modelu ceny sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="82b9a-105">This procedure requires that at least one sales price model be available.</span></span> <span data-ttu-id="82b9a-106">W tym przykładzie jest używany model ceny będący modelem cen sprzedaży rozwiązania Głośnik w firmie demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="82b9a-106">This example uses the price model for the Speaker solution sales price model in the USMF demo data company.</span></span> <span data-ttu-id="82b9a-107">Zazwyczaj procedurę wykonuje menedżer produktu.</span><span class="sxs-lookup"><span data-stu-id="82b9a-107">Typically, a product manager uses this procedure.</span></span>

## <a name="add-a-new-criterion-for-an-existing-sales-price-model"></a><span data-ttu-id="82b9a-108">Dodawanie nowego kryterium dla istniejącego modelu ceny sprzedaży</span><span class="sxs-lookup"><span data-stu-id="82b9a-108">Add a new criterion for an existing sales price model</span></span>

1. <span data-ttu-id="82b9a-109">Przejdź do **Zarządzanie informacjami o produktach \> Produkty \> Modele konfiguracji produktów**.</span><span class="sxs-lookup"><span data-stu-id="82b9a-109">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="82b9a-110">Na liście zaznacz wiersz modelu produktu rozwiązania Głośnika, ale nie wybieraj łącza z nazwą modelu.</span><span class="sxs-lookup"><span data-stu-id="82b9a-110">In the list, select the row for the Speaker solution product model, but don't select the link for the model name.</span></span>
1. <span data-ttu-id="82b9a-111">W okienku akcji kliknij pozycję **Model**.</span><span class="sxs-lookup"><span data-stu-id="82b9a-111">On the Action Pane, select **Model**.</span></span>
1. <span data-ttu-id="82b9a-112">Wybierz opcję **Kryteria modelu ceny**.</span><span class="sxs-lookup"><span data-stu-id="82b9a-112">Select **Price model criteria**.</span></span>
1. <span data-ttu-id="82b9a-113">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="82b9a-113">Select **New**.</span></span>
1. <span data-ttu-id="82b9a-114">W polu **Nazwa** wpisz „Grupa odbiorców 10”.</span><span class="sxs-lookup"><span data-stu-id="82b9a-114">In the **Name** field, type 'Customer group 10'.</span></span>
    * <span data-ttu-id="82b9a-115">Nazwa kryterium modelu ceny służy do identyfikowania bazowych kryteriów wyboru.</span><span class="sxs-lookup"><span data-stu-id="82b9a-115">The name of the price model criterion is used to help identify the underlying selection criteria.</span></span>  
1. <span data-ttu-id="82b9a-116">Wprowadź lub wybierz wartość w polu **Model ceny**.</span><span class="sxs-lookup"><span data-stu-id="82b9a-116">In the **Price model** field, enter or select a value.</span></span>
1. <span data-ttu-id="82b9a-117">W polu **Typ zamówienia** zaznacz opcję *Zamówienie sprzedaży*.</span><span class="sxs-lookup"><span data-stu-id="82b9a-117">In the **Order type** field, select *Sales order*.</span></span>
    * <span data-ttu-id="82b9a-118">Typ zamówienia określa pola bazy danych, które będą dostępne dla kwerendy wyboru.</span><span class="sxs-lookup"><span data-stu-id="82b9a-118">The order type determines the database fields that will be available for the selection query.</span></span>  
1. <span data-ttu-id="82b9a-119">W polu **Obowiązuje od** wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="82b9a-119">In the **Valid from** field, enter a date.</span></span>
1. <span data-ttu-id="82b9a-120">W polu **Data ważności** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="82b9a-120">In the **Expire by** field, enter a date.</span></span>
1. <span data-ttu-id="82b9a-121">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="82b9a-121">Select **Save**.</span></span>

## <a name="create-the-query-for-the-selection-criteria"></a><span data-ttu-id="82b9a-122">Tworzenie zapytania dla kryteriów wyboru</span><span class="sxs-lookup"><span data-stu-id="82b9a-122">Create the query for the selection criteria</span></span>

1. <span data-ttu-id="82b9a-123">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="82b9a-123">Select **Edit**.</span></span>
2. <span data-ttu-id="82b9a-124">W polu **Tabela** wybierz opcję *Odbiorcy*.</span><span class="sxs-lookup"><span data-stu-id="82b9a-124">In the **Table** field, select *Customers*.</span></span>
3. <span data-ttu-id="82b9a-125">W polu **Pole** wybierz opcję *Grupa odbiorców*.</span><span class="sxs-lookup"><span data-stu-id="82b9a-125">In the **Field** field, select *Customer group*.</span></span>
    * <span data-ttu-id="82b9a-126">W tym przykładzie jako kryteriów wyboru użyjemy określonej grupy odbiorców.</span><span class="sxs-lookup"><span data-stu-id="82b9a-126">In this example, we will use a specific customer group for the selection criteria.</span></span>  
4. <span data-ttu-id="82b9a-127">W polu **Kryteria** wybierz opcję *Grupa odbiorców 10*.</span><span class="sxs-lookup"><span data-stu-id="82b9a-127">In the **Criteria** field, select *Customer group 10*.</span></span>
5. <span data-ttu-id="82b9a-128">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="82b9a-128">Select **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]