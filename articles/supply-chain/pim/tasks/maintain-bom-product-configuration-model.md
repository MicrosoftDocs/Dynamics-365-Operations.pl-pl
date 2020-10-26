---
title: Obsługa BOM dla modelu konfiguracji produktu
description: Wykonanie tej procedury wymaga istnienia modelu konfiguracji produktu.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCBOMLineDetails, InventItemIdLookupSimple
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fcdf4b735587b76b7f761f59c56da1ca358a2e37
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2020
ms.locfileid: "3985324"
---
# <a name="maintain-bom-for-a-product-configuration-model"></a><span data-ttu-id="4a017-103">Obsługa BOM dla modelu konfiguracji produktu</span><span class="sxs-lookup"><span data-stu-id="4a017-103">Maintain BOM for a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4a017-104">Wykonanie tej procedury wymaga istnienia modelu konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="4a017-104">Running this procedure requires an existing product configuration model.</span></span> <span data-ttu-id="4a017-105">Do utworzenia tej procedury użyto modelu Głośnik o wysokiej jakości zawartego w firmie demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="4a017-105">The High end speaker model in the demo company USMF is used to create this procedure.</span></span>


## <a name="add-a-bom-line"></a><span data-ttu-id="4a017-106">Dodawanie wiersza BOM</span><span class="sxs-lookup"><span data-stu-id="4a017-106">Add a BOM line</span></span>
1. <span data-ttu-id="4a017-107">Kliknij opcję Definicja modelu wariantu produktu.</span><span class="sxs-lookup"><span data-stu-id="4a017-107">Click Product variant model definition.</span></span>
2. <span data-ttu-id="4a017-108">Kliknij opcję Modele konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="4a017-108">Click Product configuration models.</span></span>
3. <span data-ttu-id="4a017-109">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="4a017-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="4a017-110">Do wykonania tej procedury wybierz towar Głośnik o wysokiej jakości.</span><span class="sxs-lookup"><span data-stu-id="4a017-110">Select the High end speaker for this procedure.</span></span>  
4. <span data-ttu-id="4a017-111">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="4a017-111">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="4a017-112">Rozwiń sekcję Wiersze BOM.</span><span class="sxs-lookup"><span data-stu-id="4a017-112">Expand the BOM lines section.</span></span>
6. <span data-ttu-id="4a017-113">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="4a017-113">Click Add.</span></span>
7. <span data-ttu-id="4a017-114">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="4a017-114">In the Name field, type a value.</span></span>
8. <span data-ttu-id="4a017-115">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="4a017-115">In the Description field, type a value.</span></span>
9. <span data-ttu-id="4a017-116">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="4a017-116">Click Save.</span></span>

## <a name="add-bom-line-details"></a><span data-ttu-id="4a017-117">Dodawanie szczegółów wiersza BOM</span><span class="sxs-lookup"><span data-stu-id="4a017-117">Add BOM line details</span></span>
1. <span data-ttu-id="4a017-118">Kliknij opcję Szczegóły wiersza BOM.</span><span class="sxs-lookup"><span data-stu-id="4a017-118">Click BOM line details.</span></span>
2. <span data-ttu-id="4a017-119">W polu Numer towaru wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="4a017-119">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="4a017-120">Można na przykład wybrać towar M0055.</span><span class="sxs-lookup"><span data-stu-id="4a017-120">For example, you can select the item M0055.</span></span>  
    * <span data-ttu-id="4a017-121">Dla każdej właściwości wiersza BOM można wybrać, czy ma ona wartość stałą czy też jest mapowana do atrybutu.</span><span class="sxs-lookup"><span data-stu-id="4a017-121">For each BOM line property, you can select if it takes a fixed value or is mapped to an attribute.</span></span>  
3. <span data-ttu-id="4a017-122">Zaznacz pole wyboru Ustaw.</span><span class="sxs-lookup"><span data-stu-id="4a017-122">Select the Set check box.</span></span>
4. <span data-ttu-id="4a017-123">W polu Obliczanie wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="4a017-123">Select Yes in the Calculation field.</span></span>
    * <span data-ttu-id="4a017-124">Ustawienie we właściwości Obliczanie wartości Tak gwarantuje, że wiersz BOM zostanie uwzględniony w obliczeniach kosztów.</span><span class="sxs-lookup"><span data-stu-id="4a017-124">Setting the Calculation property to Yes ensures that the BOM line is included in cost calculations.</span></span>  
5. <span data-ttu-id="4a017-125">Kliknij kartę Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="4a017-125">Click the Setup tab.</span></span>
6. <span data-ttu-id="4a017-126">Zaznacz pole wyboru Ustaw.</span><span class="sxs-lookup"><span data-stu-id="4a017-126">Select the Set check box.</span></span>
7. <span data-ttu-id="4a017-127">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="4a017-127">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="4a017-128">Pole ilości określa, jaka część towaru zostanie uwzględniona na liście składowej.</span><span class="sxs-lookup"><span data-stu-id="4a017-128">The quantity field determines how much of the item that will be included in the BOM.</span></span> <span data-ttu-id="4a017-129">To pole jest idealnym kandydatem do mapowania atrybutów.</span><span class="sxs-lookup"><span data-stu-id="4a017-129">This could be an obvious candidate for an attribute mapping.</span></span>  
8. <span data-ttu-id="4a017-130">Kliknij kartę Wymiar.</span><span class="sxs-lookup"><span data-stu-id="4a017-130">Click the Dimension tab.</span></span>
    * <span data-ttu-id="4a017-131">Sprawdź, czy którykolwiek wymiar produktu jest aktywny i w związku z tym musi mieć przypisaną wartość lub atrybut.</span><span class="sxs-lookup"><span data-stu-id="4a017-131">Verify if any of the product dimensions are active,  and therefore must have a value or attribute assigned.</span></span>  
9. <span data-ttu-id="4a017-132">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="4a017-132">Click OK.</span></span>

