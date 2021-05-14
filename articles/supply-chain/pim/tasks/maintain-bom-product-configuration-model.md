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
ms.openlocfilehash: b4ad73265e321b6339c061a7866b55cb2769954b
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921324"
---
# <a name="maintain-bom-for-a-product-configuration-model"></a><span data-ttu-id="cebcd-103">Obsługa BOM dla modelu konfiguracji produktu</span><span class="sxs-lookup"><span data-stu-id="cebcd-103">Maintain BOM for a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="cebcd-104">Wykonanie tej procedury wymaga istnienia modelu konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="cebcd-104">Running this procedure requires an existing product configuration model.</span></span> <span data-ttu-id="cebcd-105">Do utworzenia tej procedury użyto modelu Głośnik o wysokiej jakości zawartego w firmie demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="cebcd-105">The High end speaker model in the demo company USMF is used to create this procedure.</span></span>

## <a name="add-a-bom-line"></a><span data-ttu-id="cebcd-106">Dodawanie wiersza BOM</span><span class="sxs-lookup"><span data-stu-id="cebcd-106">Add a BOM line</span></span>

1. <span data-ttu-id="cebcd-107">Przejdź do **Zarządzanie informacjami o produktach \> Produkty \> Modele konfiguracji produktów**.</span><span class="sxs-lookup"><span data-stu-id="cebcd-107">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="cebcd-108">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="cebcd-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="cebcd-109">Do wykonania tej procedury wybierz towar Głośnik o wysokiej jakości.</span><span class="sxs-lookup"><span data-stu-id="cebcd-109">Select the High end speaker for this procedure.</span></span>  
1. <span data-ttu-id="cebcd-110">Na liście wybierz łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="cebcd-110">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="cebcd-111">Rozwiń sekcję **Wiersze BOM**.</span><span class="sxs-lookup"><span data-stu-id="cebcd-111">Expand the **BOM lines** section.</span></span>
1. <span data-ttu-id="cebcd-112">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="cebcd-112">Select **Add**.</span></span>
1. <span data-ttu-id="cebcd-113">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="cebcd-113">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="cebcd-114">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="cebcd-114">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="cebcd-115">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="cebcd-115">Select **Save**.</span></span>

## <a name="add-bom-line-details"></a><span data-ttu-id="cebcd-116">Dodawanie szczegółów wiersza BOM</span><span class="sxs-lookup"><span data-stu-id="cebcd-116">Add BOM line details</span></span>

1. <span data-ttu-id="cebcd-117">Wybierz opcję **Szczegóły wiersza BOM**.</span><span class="sxs-lookup"><span data-stu-id="cebcd-117">Select **BOM line details**.</span></span>
2. <span data-ttu-id="cebcd-118">W polu **Kod towaru** wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="cebcd-118">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="cebcd-119">Można na przykład wybrać towar M0055.</span><span class="sxs-lookup"><span data-stu-id="cebcd-119">For example, you can select the item M0055.</span></span>  
    * <span data-ttu-id="cebcd-120">Dla każdej właściwości wiersza BOM można wybrać, czy ma ona wartość stałą czy też jest mapowana do atrybutu.</span><span class="sxs-lookup"><span data-stu-id="cebcd-120">For each BOM line property, you can select if it takes a fixed value or is mapped to an attribute.</span></span>  
3. <span data-ttu-id="cebcd-121">Zaznacz pole wyboru **Ustaw**.</span><span class="sxs-lookup"><span data-stu-id="cebcd-121">Select the **Set** check box.</span></span>
4. <span data-ttu-id="cebcd-122">W polu **Obliczanie** wybierz opcję *Tak*.</span><span class="sxs-lookup"><span data-stu-id="cebcd-122">Select *Yes* in the **Calculation** field.</span></span>
    * <span data-ttu-id="cebcd-123">Ustawienie we właściwości **Obliczanie** wartości *Tak* gwarantuje, że wiersz BOM zostanie uwzględniony w obliczeniach kosztów.</span><span class="sxs-lookup"><span data-stu-id="cebcd-123">Setting the **Calculation** property to *Yes* ensures that the BOM line is included in cost calculations.</span></span>  
5. <span data-ttu-id="cebcd-124">Kliknij kartę **Konfiguracja**.</span><span class="sxs-lookup"><span data-stu-id="cebcd-124">Select the **Setup** tab.</span></span>
6. <span data-ttu-id="cebcd-125">Zaznacz pole wyboru **Ustaw**.</span><span class="sxs-lookup"><span data-stu-id="cebcd-125">Select the **Set** check box.</span></span>
7. <span data-ttu-id="cebcd-126">W polu **Ilość** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="cebcd-126">In the **Quantity** field, enter a number.</span></span>
    * <span data-ttu-id="cebcd-127">Pole ilości określa, jaka część towaru zostanie uwzględniona na liście składowej.</span><span class="sxs-lookup"><span data-stu-id="cebcd-127">The quantity field determines how much of the item that will be included in the BOM.</span></span> <span data-ttu-id="cebcd-128">To pole jest idealnym kandydatem do mapowania atrybutów.</span><span class="sxs-lookup"><span data-stu-id="cebcd-128">This could be an obvious candidate for an attribute mapping.</span></span>  
8. <span data-ttu-id="cebcd-129">Wybierz kartę **Wymiary**.</span><span class="sxs-lookup"><span data-stu-id="cebcd-129">Select the **Dimension** tab.</span></span>
    * <span data-ttu-id="cebcd-130">Sprawdź, czy którykolwiek wymiar produktu jest aktywny i w związku z tym musi mieć przypisaną wartość lub atrybut.</span><span class="sxs-lookup"><span data-stu-id="cebcd-130">Verify if any of the product dimensions are active,  and therefore must have a value or attribute assigned.</span></span>  
9. <span data-ttu-id="cebcd-131">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="cebcd-131">Select **OK**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]