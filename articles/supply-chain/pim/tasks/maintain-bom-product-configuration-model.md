---
title: Obsługa BOM dla modelu konfiguracji produktu
description: Wykonanie tej procedury wymaga istnienia modelu konfiguracji produktu.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCBOMLineDetails, InventItemIdLookupSimple
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 49aa17aa376f8536e9d2290292f877d314c2c078
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818020"
---
# <a name="maintain-bom-for-a-product-configuration-model"></a><span data-ttu-id="a46b1-103">Obsługa BOM dla modelu konfiguracji produktu</span><span class="sxs-lookup"><span data-stu-id="a46b1-103">Maintain BOM for a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a46b1-104">Wykonanie tej procedury wymaga istnienia modelu konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="a46b1-104">Running this procedure requires an existing product configuration model.</span></span> <span data-ttu-id="a46b1-105">Do utworzenia tej procedury użyto modelu Głośnik o wysokiej jakości zawartego w firmie demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="a46b1-105">The High end speaker model in the demo company USMF is used to create this procedure.</span></span>


## <a name="add-a-bom-line"></a><span data-ttu-id="a46b1-106">Dodawanie wiersza BOM</span><span class="sxs-lookup"><span data-stu-id="a46b1-106">Add a BOM line</span></span>
1. <span data-ttu-id="a46b1-107">Kliknij opcję Definicja modelu wariantu produktu.</span><span class="sxs-lookup"><span data-stu-id="a46b1-107">Click Product variant model definition.</span></span>
2. <span data-ttu-id="a46b1-108">Kliknij opcję Modele konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="a46b1-108">Click Product configuration models.</span></span>
3. <span data-ttu-id="a46b1-109">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="a46b1-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="a46b1-110">Do wykonania tej procedury wybierz towar Głośnik o wysokiej jakości.</span><span class="sxs-lookup"><span data-stu-id="a46b1-110">Select the High end speaker for this procedure.</span></span>  
4. <span data-ttu-id="a46b1-111">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="a46b1-111">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="a46b1-112">Rozwiń sekcję Wiersze BOM.</span><span class="sxs-lookup"><span data-stu-id="a46b1-112">Expand the BOM lines section.</span></span>
6. <span data-ttu-id="a46b1-113">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="a46b1-113">Click Add.</span></span>
7. <span data-ttu-id="a46b1-114">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="a46b1-114">In the Name field, type a value.</span></span>
8. <span data-ttu-id="a46b1-115">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="a46b1-115">In the Description field, type a value.</span></span>
9. <span data-ttu-id="a46b1-116">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="a46b1-116">Click Save.</span></span>

## <a name="add-bom-line-details"></a><span data-ttu-id="a46b1-117">Dodawanie szczegółów wiersza BOM</span><span class="sxs-lookup"><span data-stu-id="a46b1-117">Add BOM line details</span></span>
1. <span data-ttu-id="a46b1-118">Kliknij opcję Szczegóły wiersza BOM.</span><span class="sxs-lookup"><span data-stu-id="a46b1-118">Click BOM line details.</span></span>
2. <span data-ttu-id="a46b1-119">W polu Numer towaru wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="a46b1-119">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="a46b1-120">Można na przykład wybrać towar M0055.</span><span class="sxs-lookup"><span data-stu-id="a46b1-120">For example, you can select the item M0055.</span></span>  
    * <span data-ttu-id="a46b1-121">Dla każdej właściwości wiersza BOM można wybrać, czy ma ona wartość stałą czy też jest mapowana do atrybutu.</span><span class="sxs-lookup"><span data-stu-id="a46b1-121">For each BOM line property, you can select if it takes a fixed value or is mapped to an attribute.</span></span>  
3. <span data-ttu-id="a46b1-122">Zaznacz pole wyboru Ustaw.</span><span class="sxs-lookup"><span data-stu-id="a46b1-122">Select the Set check box.</span></span>
4. <span data-ttu-id="a46b1-123">W polu Obliczanie wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="a46b1-123">Select Yes in the Calculation field.</span></span>
    * <span data-ttu-id="a46b1-124">Ustawienie we właściwości Obliczanie wartości Tak gwarantuje, że wiersz BOM zostanie uwzględniony w obliczeniach kosztów.</span><span class="sxs-lookup"><span data-stu-id="a46b1-124">Setting the Calculation property to Yes ensures that the BOM line is included in cost calculations.</span></span>  
5. <span data-ttu-id="a46b1-125">Kliknij kartę Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="a46b1-125">Click the Setup tab.</span></span>
6. <span data-ttu-id="a46b1-126">Zaznacz pole wyboru Ustaw.</span><span class="sxs-lookup"><span data-stu-id="a46b1-126">Select the Set check box.</span></span>
7. <span data-ttu-id="a46b1-127">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="a46b1-127">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="a46b1-128">Pole ilości określa, jaka część towaru zostanie uwzględniona na liście składowej.</span><span class="sxs-lookup"><span data-stu-id="a46b1-128">The quantity field determines how much of the item that will be included in the BOM.</span></span> <span data-ttu-id="a46b1-129">To pole jest idealnym kandydatem do mapowania atrybutów.</span><span class="sxs-lookup"><span data-stu-id="a46b1-129">This could be an obvious candidate for an attribute mapping.</span></span>  
8. <span data-ttu-id="a46b1-130">Kliknij kartę Wymiar.</span><span class="sxs-lookup"><span data-stu-id="a46b1-130">Click the Dimension tab.</span></span>
    * <span data-ttu-id="a46b1-131">Sprawdź, czy którykolwiek wymiar produktu jest aktywny i w związku z tym musi mieć przypisaną wartość lub atrybut.</span><span class="sxs-lookup"><span data-stu-id="a46b1-131">Verify if any of the product dimensions are active,  and therefore must have a value or attribute assigned.</span></span>  
9. <span data-ttu-id="a46b1-132">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="a46b1-132">Click OK.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]