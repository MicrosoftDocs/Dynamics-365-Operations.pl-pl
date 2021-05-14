---
title: Tworzenie konfiguracji opartych na wymiarach
description: W tej procedurze pokazano sposób definiowania konfiguracji produktu opartego na wymiarach.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, EcoResProductDetailsExtended, EcoResDimensionBasedConfiguration, ConfigChooseFromRoute, ConfigChooseFromGroup, ConfigChoiceApprove
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 584bb558ee0afeaffaeb003e9f1d1b0bca42d19d
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920688"
---
# <a name="create-dimension-based-configurations"></a><span data-ttu-id="813bd-103">Tworzenie konfiguracji opartych na wymiarach</span><span class="sxs-lookup"><span data-stu-id="813bd-103">Create dimension-based configurations</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="813bd-104">W tej procedurze pokazano sposób definiowania konfiguracji produktu opartego na wymiarach.</span><span class="sxs-lookup"><span data-stu-id="813bd-104">This procedure shows how to define a configuration for a dimension-based product.</span></span> <span data-ttu-id="813bd-105">Jest to ostatnia z serii procedur opisujących sposób tworzenia kombinacji dla konfiguracji opartej na wymiarach.</span><span class="sxs-lookup"><span data-stu-id="813bd-105">This is the last procedure in the series that explains how to build combinations for dimension-based configuration.</span></span> <span data-ttu-id="813bd-106">Wykonanie tej procedury zależy od danych utworzonych w poprzednich siedmiu nagraniach.</span><span class="sxs-lookup"><span data-stu-id="813bd-106">The execution of this procedure is dependent on the data created in the previous seven recordings.</span></span> <span data-ttu-id="813bd-107">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="813bd-107">The demo data company used to create this procedure is USMF.</span></span>

## <a name="find-the-dimension-based-product-master"></a><span data-ttu-id="813bd-108">Znajdowanie produktu głównego opartego na wymiarach</span><span class="sxs-lookup"><span data-stu-id="813bd-108">Find the dimension-based product master</span></span>

1. <span data-ttu-id="813bd-109">Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="813bd-109">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="813bd-110">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="813bd-110">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="813bd-111">Zaznacz produkt główny oparty na wymiarach, który utworzono w pierwszym nagraniu w tej sekwencji 8 nagrań.</span><span class="sxs-lookup"><span data-stu-id="813bd-111">Select the dimension-based product master that you created in the first recording in this sequence of 8 recordings.</span></span>  

## <a name="create-configurations"></a><span data-ttu-id="813bd-112">Tworzenie konfiguracji</span><span class="sxs-lookup"><span data-stu-id="813bd-112">Create configurations</span></span>

1. <span data-ttu-id="813bd-113">W okienku akcji **Inżynieria** kliknij opcję **Obsługa konfiguracji**.</span><span class="sxs-lookup"><span data-stu-id="813bd-113">On the **Engineering** Action Pane, select **Maintain configurations**.</span></span>
1. <span data-ttu-id="813bd-114">Wybierz pozycję **Konfiguruj**.</span><span class="sxs-lookup"><span data-stu-id="813bd-114">Select **Configure**.</span></span>
1. <span data-ttu-id="813bd-115">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="813bd-115">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="813bd-116">W polu **Kod towaru** wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="813bd-116">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="813bd-117">Wybierz dowolną pozycję z pierwszej grupy konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="813bd-117">Select any of the items in the first configuration group.</span></span>  
1. <span data-ttu-id="813bd-118">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="813bd-118">In the list, find and select the desired record.</span></span>
1. <span data-ttu-id="813bd-119">W polu **Kod towaru** wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="813bd-119">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="813bd-120">Wybierz dowolną pozycję z drugiej grupy konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="813bd-120">Select any item from the second configuration group.</span></span>  
1. <span data-ttu-id="813bd-121">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="813bd-121">Select **OK**.</span></span>
1. <span data-ttu-id="813bd-122">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="813bd-122">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="813bd-123">W polu **Konfiguracja** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="813bd-123">In the **Configuration** field, type a value.</span></span>
    * <span data-ttu-id="813bd-124">Wprowadź nazwę konfiguracji, która ułatwi identyfikowanie konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="813bd-124">Enter a configuration name that will make it easy to identify the configuration.</span></span>  
1. <span data-ttu-id="813bd-125">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="813bd-125">In the **Description** field, type a value.</span></span>
    * <span data-ttu-id="813bd-126">Wprowadzić opis konfiguracji wyjaśniający, co ona zawiera.</span><span class="sxs-lookup"><span data-stu-id="813bd-126">Enter a description of the configuration to explain what it contains.</span></span>  
1. <span data-ttu-id="813bd-127">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="813bd-127">Select **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]