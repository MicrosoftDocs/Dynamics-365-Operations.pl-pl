---
title: Producenci i modele składników majątku
description: W tym temacie wyjaśniono, jak konfigurować producentów składników majątku i pokrewne modele w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetProductLookup, EntAssetModelLookup, EntAssetProduct
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ae2dfcebcbab77cba1795a8b559a3a4244abd00e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435128"
---
# <a name="asset-manufacturers-and-models"></a><span data-ttu-id="5cc19-103">Producenci i modele składników majątku</span><span class="sxs-lookup"><span data-stu-id="5cc19-103">Asset manufacturers and models</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="5cc19-104">W tym temacie wyjaśniono, jak konfigurować producentów składników majątku i pokrewne modele w module Zarządzanie składnikami majątku.</span><span class="sxs-lookup"><span data-stu-id="5cc19-104">This topic explains how to set up asset manufacturers and related models in Asset Management.</span></span> <span data-ttu-id="5cc19-105">Modele mogą być powiązane z typami składników majątku.</span><span class="sxs-lookup"><span data-stu-id="5cc19-105">Models can be related to asset types.</span></span>

## <a name="set-up-product-model-relations"></a><span data-ttu-id="5cc19-106">Konfigurowanie relacji produkt-model</span><span class="sxs-lookup"><span data-stu-id="5cc19-106">Set up product-model relations</span></span>

1. <span data-ttu-id="5cc19-107">Wybierz kolejno **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Składniki majątku** \> **Producent i model**.</span><span class="sxs-lookup"><span data-stu-id="5cc19-107">Select **Asset management** \> **Setup** \> **Assets** \> **Manufacturer and model**.</span></span>
2. <span data-ttu-id="5cc19-108">Wybierz opcję **Nowy**, aby utworzyć nowy produkt.</span><span class="sxs-lookup"><span data-stu-id="5cc19-108">Select **New** to create a new product.</span></span>
3. <span data-ttu-id="5cc19-109">W polu **Producent** wprowadź nazwę producenta składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="5cc19-109">In the **Manufacturer** field, enter a name for the asset manufacturer.</span></span>
4. <span data-ttu-id="5cc19-110">W polu **Opis wprowadź** opis.</span><span class="sxs-lookup"><span data-stu-id="5cc19-110">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="5cc19-111">Na skróconej karcie **Modele** wybierz opcję **Dodaj**, aby utworzyć model składnika majątku, który powinien być powiązany z producentem składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="5cc19-111">On the **Models** FastTab, select **Add** to create an asset model that should be related to the asset manufacturer.</span></span>
6. <span data-ttu-id="5cc19-112">W polu **Model** wprowadź nazwę modelu składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="5cc19-112">In the **Model** field, enter a name for the asset model.</span></span>
7. <span data-ttu-id="5cc19-113">W polu **Opis wprowadź** opis.</span><span class="sxs-lookup"><span data-stu-id="5cc19-113">In the **Description** field, enter a description.</span></span>
8. <span data-ttu-id="5cc19-114">W polu **Typ składnika majątku** wybierz typ składnika majątku, z którym ma być powiązany model producenta.</span><span class="sxs-lookup"><span data-stu-id="5cc19-114">In the **Asset type** field, select the asset type that the manufacturer model should be related to.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5cc19-115">Można również skonfigurować relacje dla typów składników majątku, producentów oraz modeli w wyszukiwaniu **Typy składników majątku**.</span><span class="sxs-lookup"><span data-stu-id="5cc19-115">You can also set up relations for asset types, manufacturers, and models in the **Asset types** lookup.</span></span> <span data-ttu-id="5cc19-116">Aby uzyskać więcej informacji, zobacz [Typy składników majątku](../setup-for-objects/object-types.md).</span><span class="sxs-lookup"><span data-stu-id="5cc19-116">For more information, see [Asset types](../setup-for-objects/object-types.md).</span></span>

    <span data-ttu-id="5cc19-117">Na skróconej karcie **Szczegóły** w polu **Modele** wyświetlana jest liczba modeli składników majątku, które są skonfigurowane na wybranym producencie składników majątku.</span><span class="sxs-lookup"><span data-stu-id="5cc19-117">In the **Details** FastTab, the **Models** field shows the number of asset models that are set up on the selected asset manufacturer.</span></span> <span data-ttu-id="5cc19-118">W polu **Składniki majątku** wyświetlana jest liczba składników majątku korzystających z wybranego producenta.</span><span class="sxs-lookup"><span data-stu-id="5cc19-118">The **Assets** field shows the number of assets that are using the selected manufacturer.</span></span>
    
    <span data-ttu-id="5cc19-119">W polu **Składniki majątku** wyświetlana jest liczba obiektów korzystających z modelu producenta.</span><span class="sxs-lookup"><span data-stu-id="5cc19-119">The **Assets** field shows the number of objects that are using the manufacturer model.</span></span>

> [!NOTE]
> <span data-ttu-id="5cc19-120">Typ składnika majątku może nie mieć relacji modelu producenta składnika majątku, może być powiązany z jednym modelem producenta składnika majątku lub może być powiązany z wieloma modelami producentów składników majątku.</span><span class="sxs-lookup"><span data-stu-id="5cc19-120">An asset type can have no asset manufacturer model relations, it can be related to one asset manufacturer model, or it can be related multiple asset manufacturer models.</span></span> <span data-ttu-id="5cc19-121">Jeśli typ składnika majątku jest powiązany z co najmniej jednym modelem producenta, tylko kombinacje skonfigurowane w wyszukiwaniu **Model producenta** mogą być wybrane na tych stronach Zarządzanie składnikami majątku, na których połączenie typu składnika majątku, producenta i modelu może być skonfigurowane.</span><span class="sxs-lookup"><span data-stu-id="5cc19-121">If an asset type is related to at least one manufacturer model, only the combinations that are set up in the **Manufacturer model** lookup can be selected on those Asset Management pages where a combination of an asset type, manufacturer, and model can be set up.</span></span> <span data-ttu-id="5cc19-122">Te strony obejmują **Wszystkie składniki majątku**, **Poziomy usługi składnika majątku**, **Domyślne typy zadań** oraz **Wiersze budżetu konserwacji**.</span><span class="sxs-lookup"><span data-stu-id="5cc19-122">These pages include **All assets**, **Asset service levels**, **Job type defaults**, and **Maintenance budget lines**.</span></span> <span data-ttu-id="5cc19-123">Jeśli niektóre typy składników majątku nie są powiązane z żadnym modelem producenta, na stronach są wyświetlane tylko te typy składników majątku i modele producenta, które również nie mają związku z typami składników majątku.</span><span class="sxs-lookup"><span data-stu-id="5cc19-123">If some asset types aren't related to any manufacturer model, only those asset types, and manufacturer models that also have no relation to asset types, are shown on the pages.</span></span>

## <a name="select-a-manufacturer-and-model-on-an-object"></a><span data-ttu-id="5cc19-124">Wybieranie producenta i modelu na obiekcie</span><span class="sxs-lookup"><span data-stu-id="5cc19-124">Select a manufacturer and model on an object</span></span>

1. <span data-ttu-id="5cc19-125">Wybierz kolejno **Zarządzanie składnikami majątku** \> **Wspólne** \> **Składniki majątku** \> **Wszystkie składniki majątku**.</span><span class="sxs-lookup"><span data-stu-id="5cc19-125">Select **Asset management** \> **Common** \> **Assets** \> **All assets**.</span></span>
2. <span data-ttu-id="5cc19-126">W kolumnie **Składnik majątku** wybierz łącze dla składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="5cc19-126">In the **Asset** column, select the link for the asset.</span></span> <span data-ttu-id="5cc19-127">Zostanie wyświetlona strona **Szczegóły**.</span><span class="sxs-lookup"><span data-stu-id="5cc19-127">The **Details** page appears.</span></span>
3. <span data-ttu-id="5cc19-128">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="5cc19-128">Select **Edit**.</span></span>
4. <span data-ttu-id="5cc19-129">Na skróconej karcie **Ogólne** wybierz wartości w polach **Producent** i **Model**.</span><span class="sxs-lookup"><span data-stu-id="5cc19-129">On the **General** FastTab, select values in the **Manufacturer** and **Model** fields.</span></span>
