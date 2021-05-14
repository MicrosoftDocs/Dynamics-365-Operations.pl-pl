---
title: Zatwierdzanie modelu konfiguracji produktu
description: Wykonanie tej procedury wymaga dostępności co najmniej jednego modelu konfiguracji produktu.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductModelVersion, PCApproveProductModelVersion, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2c945756997b0580ac7ffb19261f9184e53a1c10
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920514"
---
# <a name="approve-a-product-configuration-model"></a><span data-ttu-id="aecec-103">Zatwierdzanie modelu konfiguracji produktu</span><span class="sxs-lookup"><span data-stu-id="aecec-103">Approve a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="aecec-104">Wykonanie tej procedury wymaga dostępności co najmniej jednego modelu konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="aecec-104">Running this procedure requires that at least one product configuration model is available.</span></span> <span data-ttu-id="aecec-105">Do utworzenia tej procedury użyto modelu Głośnik o wysokiej jakości zawartego w danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="aecec-105">This procedure uses the High end speaker model in the demo data company USMF.</span></span> <span data-ttu-id="aecec-106">Należy zauważyć, że ten model został już zatwierdzony, ale procedura prowadzi przez cały proces.</span><span class="sxs-lookup"><span data-stu-id="aecec-106">Note that this model has already been approved, but the procedure walks you through the entire process.</span></span>

1. <span data-ttu-id="aecec-107">Przejdź do **Zarządzanie informacjami o produktach \> Produkty \> Modele konfiguracji produktów**.</span><span class="sxs-lookup"><span data-stu-id="aecec-107">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="aecec-108">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="aecec-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="aecec-109">Do tej procedury wybierz model Głośnik o wysokiej jakości.</span><span class="sxs-lookup"><span data-stu-id="aecec-109">Select the High end speaker model for this procedure.</span></span>  
1. <span data-ttu-id="aecec-110">Wybierz opcję **Wersje**.</span><span class="sxs-lookup"><span data-stu-id="aecec-110">Select **Versions**.</span></span>
1. <span data-ttu-id="aecec-111">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="aecec-111">Select **New**.</span></span>
1. <span data-ttu-id="aecec-112">W polu **Numer produktu** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="aecec-112">In the **Product number** field, enter or select a value.</span></span>
    * <span data-ttu-id="aecec-113">Odwołanie do produktu reprezentuje wersję modelu konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="aecec-113">The reference to a product represents a version of a product configuration model.</span></span> <span data-ttu-id="aecec-114">Na liście będą widoczne tylko produkty główne, które mają technologię konfiguracji opartej na ograniczeniach.</span><span class="sxs-lookup"><span data-stu-id="aecec-114">Only product masters which have the constraint-based configuration technology will appear in this list.</span></span>  
1. <span data-ttu-id="aecec-115">W polu **Od dnia** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="aecec-115">In the **From date** field, enter a date.</span></span>
    * <span data-ttu-id="aecec-116">Wybierz, kiedy wersja modelu produktu będzie dostępna.</span><span class="sxs-lookup"><span data-stu-id="aecec-116">Select when the product model version will be available.</span></span>  
1. <span data-ttu-id="aecec-117">Wprowadź datę w polu **Do dnia**.</span><span class="sxs-lookup"><span data-stu-id="aecec-117">In the **To date** field, enter a date.</span></span>
    * <span data-ttu-id="aecec-118">Wybierz datę końcową, do kiedy ta wersja modelu produktu działa, lub zaznacz opcję Nigdy.</span><span class="sxs-lookup"><span data-stu-id="aecec-118">Select an end date when this product model version will expire, or select Never.</span></span>  
1. <span data-ttu-id="aecec-119">Wybierz przycisk **Zatwierdź**, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="aecec-119">Select **Approve** to open the drop dialog.</span></span>
1. <span data-ttu-id="aecec-120">W polu **Zatwierdzone przez** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="aecec-120">In the **Approved by** field, enter or select a value.</span></span>
    * <span data-ttu-id="aecec-121">Wybierz osobę odpowiedzialną za zatwierdzanie modeli produktów do użytku w operacjach.</span><span class="sxs-lookup"><span data-stu-id="aecec-121">Select the person who is responsible for approving product models for use in operations.</span></span>  
1. <span data-ttu-id="aecec-122">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="aecec-122">Select **OK**.</span></span>
1. <span data-ttu-id="aecec-123">W polu **Metoda wyceny** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="aecec-123">In the **Pricing method** field, select an option.</span></span>
    * <span data-ttu-id="aecec-124">Aktywuj wersję modelu produktu.</span><span class="sxs-lookup"><span data-stu-id="aecec-124">Activate the product model version.</span></span> <span data-ttu-id="aecec-125">W danym momencie może istnieć tylko jeden aktywny produkt o danym modelu.</span><span class="sxs-lookup"><span data-stu-id="aecec-125">It is only possible to have one product active for one product model at a time.</span></span>  
1. <span data-ttu-id="aecec-126">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="aecec-126">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]