---
title: Typy atrybutów konserwacji
description: W tym temacie wyjaśniono, jak tworzyć typy atrybutów w Zarządzaniu składnikami majątku.
author: johanhoffmann
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetFunctionalLocationTypeCopy, EntAssetAttributeType, EntAssetAttributeTypeValue, EntAssetFunctionalLocationType
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 283cff931ce665ae09152c8f3d3c976b7c8b66ff
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808527"
---
# <a name="maintenance-attribute-types"></a><span data-ttu-id="c92c1-103">Typy atrybutów konserwacji</span><span class="sxs-lookup"><span data-stu-id="c92c1-103">Maintenance attribute types</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="c92c1-104">W tym temacie wyjaśniono, jak tworzyć typy atrybutów w Zarządzaniu składnikami majątku.</span><span class="sxs-lookup"><span data-stu-id="c92c1-104">This topic explains how to create attribute types in Asset Management.</span></span> <span data-ttu-id="c92c1-105">Atrybuty są używane do opisywania właściwości różnych elementów.</span><span class="sxs-lookup"><span data-stu-id="c92c1-105">Attributes are used to describe the properties of various elements.</span></span> <span data-ttu-id="c92c1-106">Można konfigurować atrybuty następujących elementów:</span><span class="sxs-lookup"><span data-stu-id="c92c1-106">You can set up attributes on the following elements:</span></span>

- [<span data-ttu-id="c92c1-107">Typy lokalizacji czynności konserwacyjnych</span><span class="sxs-lookup"><span data-stu-id="c92c1-107">Functional location types</span></span>](../setup-for-functional-locations/functional-location-types.md)
- [<span data-ttu-id="c92c1-108">Tworzenie lokalizacji czynności konserwacyjnych</span><span class="sxs-lookup"><span data-stu-id="c92c1-108">Create functional locations</span></span>](../functional-locations/create-functional-locations.md)
- [<span data-ttu-id="c92c1-109">Typy składników majątku</span><span class="sxs-lookup"><span data-stu-id="c92c1-109">Asset types</span></span>](../setup-for-objects/object-types.md)
- <span data-ttu-id="c92c1-110">Składniki majątku</span><span class="sxs-lookup"><span data-stu-id="c92c1-110">Assets</span></span>

<span data-ttu-id="c92c1-111">Atrybuty, które można skonfigurować różnią się w zależności od elementu.</span><span class="sxs-lookup"><span data-stu-id="c92c1-111">The attributes that you can set up vary, depending on the element.</span></span> <span data-ttu-id="c92c1-112">Na przykład dla lokalizacji czynności konserwacyjnych można skonfigurować atrybuty dla konfiguracji i fizycznego rozmiaru lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="c92c1-112">For example, for a functional location, you can set up attributes for the configuration and physical size of the location.</span></span> <span data-ttu-id="c92c1-113">Dla typu składnika majątku lub składnika majątku można skonfigurować atrybuty dla objętości silnika, zużycia energii i maksymalnej pojemności w różnych warunkach.</span><span class="sxs-lookup"><span data-stu-id="c92c1-113">For an asset type or an asset, you can set up attributes for engine volume, power consumption, and maximum load capacity under different conditions.</span></span>

## <a name="create-attribute-types"></a><span data-ttu-id="c92c1-114">Tworzenie typu atrybutu</span><span class="sxs-lookup"><span data-stu-id="c92c1-114">Create attribute types</span></span>

<span data-ttu-id="c92c1-115">Tworzenie własnych typów atrybutów.</span><span class="sxs-lookup"><span data-stu-id="c92c1-115">You can create your own attribute types.</span></span> <span data-ttu-id="c92c1-116">Ponadto można przenosić wymiary produkty do strony **Typy atrybutów**.</span><span class="sxs-lookup"><span data-stu-id="c92c1-116">Additionally, you can transfer product dimensions to the **Attribute types** page.</span></span>

1. <span data-ttu-id="c92c1-117">Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Typy atrybutów**.</span><span class="sxs-lookup"><span data-stu-id="c92c1-117">Select **Asset management** \> **Setup** \> **Attribute types**.</span></span>
2. <span data-ttu-id="c92c1-118">Przy pierwszym ustawianiu typów atrybutów wybierz opcję **Utwórz wymiary produktu**, aby automatycznie przenieść standardowe wymiary produktu.</span><span class="sxs-lookup"><span data-stu-id="c92c1-118">The first time that you set up attribute types, select **Create product dimensions** to automatically transfer standard product dimensions.</span></span>
3. <span data-ttu-id="c92c1-119">Wybierz pozycję **Nowy**, aby utworzyć nowy typ atrybutu.</span><span class="sxs-lookup"><span data-stu-id="c92c1-119">Select **New** to create a new attribute type.</span></span>
4. <span data-ttu-id="c92c1-120">W polu **Typ atrybutu** wprowadź nazwę typu atrybutu.</span><span class="sxs-lookup"><span data-stu-id="c92c1-120">In the **Attribute type** field, enter a name for the attribute type.</span></span>
5. <span data-ttu-id="c92c1-121">W polu **Opis wprowadź** opis.</span><span class="sxs-lookup"><span data-stu-id="c92c1-121">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="c92c1-122">W polu **Jednostka** wybierz odpowiednią jednostkę atrybutu, zgodnie z wymaganiami.</span><span class="sxs-lookup"><span data-stu-id="c92c1-122">In the **Unit** field, select the relevant attribute unit, as required.</span></span>
7. <span data-ttu-id="c92c1-123">W polu **Typ daty** wybierz typ daty dla jednostki.</span><span class="sxs-lookup"><span data-stu-id="c92c1-123">In the **Data type** field, select a data type for the unit.</span></span>
8. <span data-ttu-id="c92c1-124">Jeśli wybrano **Ciąg** jako typ danych, wykonaj następujące kroki, aby utworzyć wartości dla typu atrybutu:</span><span class="sxs-lookup"><span data-stu-id="c92c1-124">If you selected **String** as the data type, follow these steps to create values for the attribute type:</span></span>

    1. <span data-ttu-id="c92c1-125">Wybierz typ atrybutu, a następnie wybierz **Wartości**.</span><span class="sxs-lookup"><span data-stu-id="c92c1-125">Select the attribute type, and then select **Values**.</span></span>
    2. <span data-ttu-id="c92c1-126">W polu **Wartości atrybutu** wybierz wartość **Nowa**.</span><span class="sxs-lookup"><span data-stu-id="c92c1-126">In the **Attribute values** field, select **New**.</span></span>
    3. <span data-ttu-id="c92c1-127">W polu **Typ atrybutu** wybierz typ atrybutu (wymiar).</span><span class="sxs-lookup"><span data-stu-id="c92c1-127">In the **Attribute type** field, select an attribute type (dimension).</span></span>
    4. <span data-ttu-id="c92c1-128">W polu **Wartość** wpisz wartość powiązaną.</span><span class="sxs-lookup"><span data-stu-id="c92c1-128">In the **Value** field, enter a related value.</span></span>
    5. <span data-ttu-id="c92c1-129">W polu **Opis wprowadź** opis.</span><span class="sxs-lookup"><span data-stu-id="c92c1-129">In the **Description** field, enter a description.</span></span>
    6. <span data-ttu-id="c92c1-130">Zapisz rekord.</span><span class="sxs-lookup"><span data-stu-id="c92c1-130">Save the record.</span></span>
    7. <span data-ttu-id="c92c1-131">Wróć do strony **Typy atrybutów**.</span><span class="sxs-lookup"><span data-stu-id="c92c1-131">Return to the **Attribute types** page.</span></span>

9. <span data-ttu-id="c92c1-132">Zapisz rekord.</span><span class="sxs-lookup"><span data-stu-id="c92c1-132">Save the record.</span></span>

    <span data-ttu-id="c92c1-133">Pole **Typy lokalizacji czynności konserwacyjnych** pokazuje liczbę lokalizacji funkcjonalnych, które używają typu atrybutu.</span><span class="sxs-lookup"><span data-stu-id="c92c1-133">The **Functional location types** field shows the number of functional locations that are using the attribute type.</span></span> <span data-ttu-id="c92c1-134">Pole **Typy składników majątku** zawiera liczbę typów składników majątku, które są używane.</span><span class="sxs-lookup"><span data-stu-id="c92c1-134">The **Asset types** field shows the number of asset types that are using it.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]