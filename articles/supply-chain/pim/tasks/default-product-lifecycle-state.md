---
title: Tworzenie domyślnego stanu cyklu życia produktu
description: W tej procedurze pokazano, jak utworzyć domyślny stan cyklu życia produktu, a także jak skojarzyć stan domyślny ze zwolnionymi produktami.
author: cvocph
manager: tfehr
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b65f34c1d7a0fd22201df5b48f8d42d452d6b8ef
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5216088"
---
# <a name="create-a-default-product-lifecycle-state"></a><span data-ttu-id="20f8c-103">Tworzenie domyślnego stanu cyklu życia produktu</span><span class="sxs-lookup"><span data-stu-id="20f8c-103">Create a default product lifecycle state</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="20f8c-104">W tej procedurze pokazano, jak utworzyć domyślny stan cyklu życia produktu, a także jak skojarzyć stan domyślny ze zwolnionymi produktami.</span><span class="sxs-lookup"><span data-stu-id="20f8c-104">This procedure shows how to create a default product lifecycle state as well as how to associate the default state with released products.</span></span>


## <a name="create-a-default-lifecycle-state"></a><span data-ttu-id="20f8c-105">Tworzenie domyślnego stanu cyklu życia</span><span class="sxs-lookup"><span data-stu-id="20f8c-105">Create a default lifecycle state</span></span>
1. <span data-ttu-id="20f8c-106">Wybierz kolejno opcje Zarządzanie informacjami o produktach > Ustawienia > Stan cyklu życia produktu.</span><span class="sxs-lookup"><span data-stu-id="20f8c-106">Go to Product information management > Setup > Product lifecycle state.</span></span>
2. <span data-ttu-id="20f8c-107">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="20f8c-107">Click New.</span></span>
3. <span data-ttu-id="20f8c-108">W polu Stan wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="20f8c-108">In the State field, type a value.</span></span>
4. <span data-ttu-id="20f8c-109">Wybierz opcję Tak w ustawieniu Domyślny po zwolnieniu do pola firmy.</span><span class="sxs-lookup"><span data-stu-id="20f8c-109">Select Yes in the Default when released to legal entity field.</span></span>
5. <span data-ttu-id="20f8c-110">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="20f8c-110">In the Description field, type a value.</span></span>
6. <span data-ttu-id="20f8c-111">W polu Jest aktywna dla planowania zaznacz opcję Nie.</span><span class="sxs-lookup"><span data-stu-id="20f8c-111">Select No in the Is active for planning field.</span></span>

> [!NOTE]
> <span data-ttu-id="20f8c-112">Jeśli nowy zwolniony produkt nie powinien być uwzględniony w planowaniu głównym, wybierz opcję Nie.</span><span class="sxs-lookup"><span data-stu-id="20f8c-112">If a new released product should not be included in Master planning, select No.</span></span> <span data-ttu-id="20f8c-113">Jeśli planowanie główne powinno być uwzględnione, należy pozostawić dla formantu wartość domyślną Tak.</span><span class="sxs-lookup"><span data-stu-id="20f8c-113">If it should be included in Master planning, leave the control at its default value Yes.</span></span>  

## <a name="create-a-new-released-product"></a><span data-ttu-id="20f8c-114">Tworzenie nowego zwolnionego produktu</span><span class="sxs-lookup"><span data-stu-id="20f8c-114">Create a new released product</span></span>
1. <span data-ttu-id="20f8c-115">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="20f8c-115">Close the page.</span></span>
2. <span data-ttu-id="20f8c-116">Przejdź do Zarządzanie informacjami o produktach > Produkty > Zwolnione produkty.</span><span class="sxs-lookup"><span data-stu-id="20f8c-116">Go to Product information management > Products > Released products.</span></span>
3. <span data-ttu-id="20f8c-117">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="20f8c-117">Click New.</span></span>
4. <span data-ttu-id="20f8c-118">W polu Numer produktu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="20f8c-118">In the Product number field, type a value.</span></span>
5. <span data-ttu-id="20f8c-119">W polu Nazwa produktu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="20f8c-119">In the Product name field, type a value.</span></span>
6. <span data-ttu-id="20f8c-120">W polu Alias wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="20f8c-120">In the Search name field, type a value.</span></span>
7. <span data-ttu-id="20f8c-121">W polu grupa modelu produktu wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="20f8c-121">In the Item model group field, enter or select a value.</span></span>
8. <span data-ttu-id="20f8c-122">W polu Grupa towarów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="20f8c-122">In the Item group field, enter or select a value.</span></span>
9. <span data-ttu-id="20f8c-123">W polu grupa wymiaru magazynowania wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="20f8c-123">In the Storage dimension group field, enter or select a value.</span></span>
10. <span data-ttu-id="20f8c-124">W polu grupa wymiaru śledzenia wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="20f8c-124">In the Tracking dimension group field, enter or select a value.</span></span>
11. <span data-ttu-id="20f8c-125">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="20f8c-125">Click OK.</span></span>

> [!NOTE]
> <span data-ttu-id="20f8c-126">Domyślny stan cyklu życia produktu to definicja globalna.</span><span class="sxs-lookup"><span data-stu-id="20f8c-126">The default product lifecycle state is a global definition.</span></span>  

## <a name="change-the-product-to-an-active-state"></a><span data-ttu-id="20f8c-127">Zmiana stanu produktu na aktywny</span><span class="sxs-lookup"><span data-stu-id="20f8c-127">Change the product to an active state</span></span>
1. <span data-ttu-id="20f8c-128">W polu Stan cyklu życia produktu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="20f8c-128">In the Product lifecycle state field, enter or select a value.</span></span>

> [!NOTE]
> <span data-ttu-id="20f8c-129">Załóżmy, że skonfigurowano stan aktywny. W takim przypadku można wybrać aktywny, aby zezwolić na użycie produktu w planowaniu głównym o obliczaniu na poziomie BOM.</span><span class="sxs-lookup"><span data-stu-id="20f8c-129">Assume that you have set up an active state, you can now select the active state to allow the product to be used in Master planning and BOM-level calculation.</span></span> <span data-ttu-id="20f8c-130">Oczywiście ma to sens tylko wówczas, gdy określono wszystkie dane szczegółowe produkty wymagane do spójnego planowania.</span><span class="sxs-lookup"><span data-stu-id="20f8c-130">Obviously, this only makes sense if all the product details that are required for consistent planning are specified.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]