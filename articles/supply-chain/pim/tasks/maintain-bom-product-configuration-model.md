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
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1aa2a22056ff4435d4c66f13c170aeadc02fbe03
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3203579"
---
# <a name="maintain-bom-for-a-product-configuration-model"></a><span data-ttu-id="b5f72-103">Obsługa BOM dla modelu konfiguracji produktu</span><span class="sxs-lookup"><span data-stu-id="b5f72-103">Maintain BOM for a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b5f72-104">Wykonanie tej procedury wymaga istnienia modelu konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="b5f72-104">Running this procedure requires an existing product configuration model.</span></span> <span data-ttu-id="b5f72-105">Do utworzenia tej procedury użyto modelu Głośnik o wysokiej jakości zawartego w firmie demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="b5f72-105">The High end speaker model in the demo company USMF is used to create this procedure.</span></span>


## <a name="add-a-bom-line"></a><span data-ttu-id="b5f72-106">Dodawanie wiersza BOM</span><span class="sxs-lookup"><span data-stu-id="b5f72-106">Add a BOM line</span></span>
1. <span data-ttu-id="b5f72-107">Kliknij opcję Definicja modelu wariantu produktu.</span><span class="sxs-lookup"><span data-stu-id="b5f72-107">Click Product variant model definition.</span></span>
2. <span data-ttu-id="b5f72-108">Kliknij opcję Modele konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="b5f72-108">Click Product configuration models.</span></span>
3. <span data-ttu-id="b5f72-109">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="b5f72-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="b5f72-110">Do wykonania tej procedury wybierz towar Głośnik o wysokiej jakości.</span><span class="sxs-lookup"><span data-stu-id="b5f72-110">Select the High end speaker for this procedure.</span></span>  
4. <span data-ttu-id="b5f72-111">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="b5f72-111">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="b5f72-112">Rozwiń sekcję Wiersze BOM.</span><span class="sxs-lookup"><span data-stu-id="b5f72-112">Expand the BOM lines section.</span></span>
6. <span data-ttu-id="b5f72-113">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="b5f72-113">Click Add.</span></span>
7. <span data-ttu-id="b5f72-114">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="b5f72-114">In the Name field, type a value.</span></span>
8. <span data-ttu-id="b5f72-115">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="b5f72-115">In the Description field, type a value.</span></span>
9. <span data-ttu-id="b5f72-116">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="b5f72-116">Click Save.</span></span>

## <a name="add-bom-line-details"></a><span data-ttu-id="b5f72-117">Dodawanie szczegółów wiersza BOM</span><span class="sxs-lookup"><span data-stu-id="b5f72-117">Add BOM line details</span></span>
1. <span data-ttu-id="b5f72-118">Kliknij opcję Szczegóły wiersza BOM.</span><span class="sxs-lookup"><span data-stu-id="b5f72-118">Click BOM line details.</span></span>
2. <span data-ttu-id="b5f72-119">W polu Numer towaru wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="b5f72-119">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="b5f72-120">Można na przykład wybrać towar M0055.</span><span class="sxs-lookup"><span data-stu-id="b5f72-120">For example, you can select the item M0055.</span></span>  
    * <span data-ttu-id="b5f72-121">Dla każdej właściwości wiersza BOM można wybrać, czy ma ona wartość stałą czy też jest mapowana do atrybutu.</span><span class="sxs-lookup"><span data-stu-id="b5f72-121">For each BOM line property, you can select if it takes a fixed value or is mapped to an attribute.</span></span>  
3. <span data-ttu-id="b5f72-122">Zaznacz pole wyboru Ustaw.</span><span class="sxs-lookup"><span data-stu-id="b5f72-122">Select the Set check box.</span></span>
4. <span data-ttu-id="b5f72-123">W polu Obliczanie wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="b5f72-123">Select Yes in the Calculation field.</span></span>
    * <span data-ttu-id="b5f72-124">Ustawienie we właściwości Obliczanie wartości Tak gwarantuje, że wiersz BOM zostanie uwzględniony w obliczeniach kosztów.</span><span class="sxs-lookup"><span data-stu-id="b5f72-124">Setting the Calculation property to Yes ensures that the BOM line is included in cost calculations.</span></span>  
5. <span data-ttu-id="b5f72-125">Kliknij kartę Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="b5f72-125">Click the Setup tab.</span></span>
6. <span data-ttu-id="b5f72-126">Zaznacz pole wyboru Ustaw.</span><span class="sxs-lookup"><span data-stu-id="b5f72-126">Select the Set check box.</span></span>
7. <span data-ttu-id="b5f72-127">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="b5f72-127">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="b5f72-128">Pole ilości określa, jaka część towaru zostanie uwzględniona na liście składowej.</span><span class="sxs-lookup"><span data-stu-id="b5f72-128">The quantity field determines how much of the item that will be included in the BOM.</span></span> <span data-ttu-id="b5f72-129">To pole jest idealnym kandydatem do mapowania atrybutów.</span><span class="sxs-lookup"><span data-stu-id="b5f72-129">This could be an obvious candidate for an attribute mapping.</span></span>  
8. <span data-ttu-id="b5f72-130">Kliknij kartę Wymiar.</span><span class="sxs-lookup"><span data-stu-id="b5f72-130">Click the Dimension tab.</span></span>
    * <span data-ttu-id="b5f72-131">Sprawdź, czy którykolwiek wymiar produktu jest aktywny i w związku z tym musi mieć przypisaną wartość lub atrybut.</span><span class="sxs-lookup"><span data-stu-id="b5f72-131">Verify if any of the product dimensions are active,  and therefore must have a value or attribute assigned.</span></span>  
9. <span data-ttu-id="b5f72-132">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="b5f72-132">Click OK.</span></span>

