---
title: Tworzenie listy składowej (BOM) dla produktu głównego opartego na wymiarach
description: Przed wykonaniem tej procedury należy wykonać 4 poprzednie przewodniki z tej sekwencji ośmiu nagrań.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, EcoResProductDetailsExtended, BOMConsistOf, BOMTable, InventItemIdLookupSimple, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 13053dd87242963586678b46c64493feb3383c4c
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920712"
---
# <a name="create-a-bill-of-materials-for-a-dimension-based-product-master"></a><span data-ttu-id="bf6d0-103">Tworzenie listy składowej (BOM) dla produktu głównego opartego na wymiarach</span><span class="sxs-lookup"><span data-stu-id="bf6d0-103">Create a bill of materials for a dimension-based product master</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bf6d0-104">Przed wykonaniem tej procedury należy wykonać 4 poprzednie przewodniki z tej sekwencji ośmiu nagrań.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-104">For this procedure you should have completed the previous 4 guides in this sequence of eight recordings.</span></span> <span data-ttu-id="bf6d0-105">Pierwsze 4 nagrania obejmują skonfigurowanie danych wymaganych do wykonania tej procedury.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-105">The first 4 recordings set up data that is required to complete this procedure.</span></span> <span data-ttu-id="bf6d0-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="bf6d0-107">To zadanie jest zazwyczaj wykonywane przez projektanta produktów.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-107">This task is typically handled by the product designer.</span></span>

## <a name="select-the-product"></a><span data-ttu-id="bf6d0-108">Wybieranie produktu</span><span class="sxs-lookup"><span data-stu-id="bf6d0-108">Select the product</span></span>

1. <span data-ttu-id="bf6d0-109">Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-109">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="bf6d0-110">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-110">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="bf6d0-111">Znajdź zwolniony produkt główny z technologią konfiguracji opartej na wymiarach, który utworzono w pierwszym przewodniku po zadaniach w tej sekwencji.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-111">Find the released product master with dimension-based configuration technology that you created in the first task guide in this sequence.</span></span>  
1. <span data-ttu-id="bf6d0-112">W okienku akcji wybierz opcję **Konstruuj**.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-112">On the Action Pane, select **Engineer**.</span></span>
1. <span data-ttu-id="bf6d0-113">Wybierz opcję **Wersje BOM**.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-113">Select **BOM versions**.</span></span>

## <a name="create-new-bom-and-bom-version"></a><span data-ttu-id="bf6d0-114">Tworzenie nowej BOM i wersji BOM</span><span class="sxs-lookup"><span data-stu-id="bf6d0-114">Create new BOM and BOM version</span></span>

1. <span data-ttu-id="bf6d0-115">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-115">Select **New**.</span></span>
1. <span data-ttu-id="bf6d0-116">Wybierz opcję **BOM i wersja BOM**.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-116">Select **BOM and BOM version**.</span></span>
1. <span data-ttu-id="bf6d0-117">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-117">In the **Name** field, type a value.</span></span>
    * <span data-ttu-id="bf6d0-118">Ustawianie oddziału</span><span class="sxs-lookup"><span data-stu-id="bf6d0-118">Setting a site</span></span>  
    * <span data-ttu-id="bf6d0-119">W tej procedurze nie ustawimy konkretnego oddziału dla BOM.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-119">In this procedure we don't set a specific site for the BOM.</span></span>  
1. <span data-ttu-id="bf6d0-120">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-120">Select **OK**.</span></span>
1. <span data-ttu-id="bf6d0-121">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-121">Select **New**.</span></span>
    * <span data-ttu-id="bf6d0-122">W tej procedurze dodamy cztery wiersze do BOM.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-122">In this procedure we will add four lines to the BOM.</span></span> <span data-ttu-id="bf6d0-123">Dwa wiersze reprezentują opcje kabla, a dwa opcje szafy.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-123">Two lines represent cable options and two lines represent cabinet options.</span></span>  
1. <span data-ttu-id="bf6d0-124">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-124">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="bf6d0-125">W polu **Kod towaru** wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-125">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="bf6d0-126">Wybierz towar o numerze A0001 HDMI 6' Cables (kable HDMI o długości 1,8 m).</span><span class="sxs-lookup"><span data-stu-id="bf6d0-126">Select item number A0001, HDMI 6' Cables.</span></span>  
1. <span data-ttu-id="bf6d0-127">W polu **Grupa konfiguracji** wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-127">In the **Configuration group** field, enter or select a value.</span></span>
    * <span data-ttu-id="bf6d0-128">Wybierz grupę konfiguracji kabla utworzoną w przewodniku 4 w tej sekwencji.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-128">Select the cable configuration group created in guide 4 in this sequence.</span></span>  
1. <span data-ttu-id="bf6d0-129">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-129">Select **New**.</span></span>
    * <span data-ttu-id="bf6d0-130">Wybierz towar o numerze A0002 HDMI 6' Cables (kable HDMI o długości 3,6 m).</span><span class="sxs-lookup"><span data-stu-id="bf6d0-130">Select item number A0002, HDMI 12' Cables.</span></span>  
1. <span data-ttu-id="bf6d0-131">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-131">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="bf6d0-132">W polu **Kod towaru** wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-132">In the **Item number** field, enter or select a value.</span></span>
1. <span data-ttu-id="bf6d0-133">W polu **Grupa konfiguracji** wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-133">In the **Configuration group** field, enter or select a value.</span></span>
    * <span data-ttu-id="bf6d0-134">Ponownie zaznacz grupę konfiguracji kabla.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-134">Select the cable configuration group again.</span></span>  
1. <span data-ttu-id="bf6d0-135">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-135">Select **New**.</span></span>
1. <span data-ttu-id="bf6d0-136">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-136">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="bf6d0-137">W polu **Kod towaru** wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-137">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="bf6d0-138">Wybierz towar o numerze D0002 Cabinet (Szafa).</span><span class="sxs-lookup"><span data-stu-id="bf6d0-138">Select item number D0002 Cabinet.</span></span>  
1. <span data-ttu-id="bf6d0-139">W polu **Grupa konfiguracji** wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-139">In the **Configuration group** field, enter or select a value.</span></span>
    * <span data-ttu-id="bf6d0-140">Dla tego wiersza BOM wybierz grupę konfiguracji szafy.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-140">Select the cabinet configuration group for this BOM line.</span></span>  
1. <span data-ttu-id="bf6d0-141">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-141">Select **New**.</span></span>
1. <span data-ttu-id="bf6d0-142">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-142">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="bf6d0-143">W polu **Kod towaru** wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-143">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="bf6d0-144">Jako ostatni wiersz BOM wybierz towar o numerze 0007 StandardCabinet (Standardowa szafa).</span><span class="sxs-lookup"><span data-stu-id="bf6d0-144">Select Item number M0007 StandardCabinet as the last BOM line.</span></span>  
1. <span data-ttu-id="bf6d0-145">W polu **Grupa konfiguracji** wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-145">In the **Configuration group** field, enter or select a value.</span></span>
    * <span data-ttu-id="bf6d0-146">W ostatnim wierszu BOM wybierz grupę konfiguracji Szafa.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-146">Select the Cabinet configuration group for the last BOM line.</span></span>  

## <a name="approve-and-activate"></a><span data-ttu-id="bf6d0-147">Zatwierdź i aktywuj</span><span class="sxs-lookup"><span data-stu-id="bf6d0-147">Approve and activate</span></span>

1. <span data-ttu-id="bf6d0-148">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-148">Close the page.</span></span>
1. <span data-ttu-id="bf6d0-149">Wybierz opcję **Zatwierdź**.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-149">Select **Approve**.</span></span>
1. <span data-ttu-id="bf6d0-150">W polu **Zatwierdzone przez** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-150">In the **Approved by** field, enter or select a value.</span></span>
1. <span data-ttu-id="bf6d0-151">W polu **Czy chcesz także zatwierdzić listę składową (BOM)?** zaznacz wartość *Tak*.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-151">Select *Yes* in the **Do you also want to approve the bill of materials?** field.</span></span>
1. <span data-ttu-id="bf6d0-152">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-152">Select **OK**.</span></span>
1. <span data-ttu-id="bf6d0-153">Wybierz **Aktywuj**.</span><span class="sxs-lookup"><span data-stu-id="bf6d0-153">Select **Activate**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]