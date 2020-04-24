---
title: Typy atrybutów konserwacji
description: W tym temacie wyjaśniono, jak tworzyć typy atrybutów w Zarządzaniu składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2ed333a3064654691966eac3c20626955ada0030
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3205904"
---
# <a name="maintenance-attribute-types"></a><span data-ttu-id="a212d-103">Typy atrybutów konserwacji</span><span class="sxs-lookup"><span data-stu-id="a212d-103">Maintenance attribute types</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="a212d-104">W tym temacie wyjaśniono, jak tworzyć typy atrybutów w Zarządzaniu składnikami majątku.</span><span class="sxs-lookup"><span data-stu-id="a212d-104">This topic explains how to create attribute types in Asset Management.</span></span> <span data-ttu-id="a212d-105">Atrybuty są używane do opisywania właściwości różnych elementów.</span><span class="sxs-lookup"><span data-stu-id="a212d-105">Attributes are used to describe the properties of various elements.</span></span> <span data-ttu-id="a212d-106">Można konfigurować atrybuty następujących elementów:</span><span class="sxs-lookup"><span data-stu-id="a212d-106">You can set up attributes on the following elements:</span></span>

- [<span data-ttu-id="a212d-107">Typy lokalizacji czynności konserwacyjnych</span><span class="sxs-lookup"><span data-stu-id="a212d-107">Functional location types</span></span>](../setup-for-functional-locations/functional-location-types.md)
- [<span data-ttu-id="a212d-108">Tworzenie lokalizacji czynności konserwacyjnych</span><span class="sxs-lookup"><span data-stu-id="a212d-108">Create functional locations</span></span>](../functional-locations/create-functional-locations.md)
- [<span data-ttu-id="a212d-109">Typy składników majątku</span><span class="sxs-lookup"><span data-stu-id="a212d-109">Asset types</span></span>](../setup-for-objects/object-types.md)
- <span data-ttu-id="a212d-110">Składniki majątku</span><span class="sxs-lookup"><span data-stu-id="a212d-110">Assets</span></span>

<span data-ttu-id="a212d-111">Atrybuty, które można skonfigurować różnią się w zależności od elementu.</span><span class="sxs-lookup"><span data-stu-id="a212d-111">The attributes that you can set up vary, depending on the element.</span></span> <span data-ttu-id="a212d-112">Na przykład dla lokalizacji czynności konserwacyjnych można skonfigurować atrybuty dla konfiguracji i fizycznego rozmiaru lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="a212d-112">For example, for a functional location, you can set up attributes for the configuration and physical size of the location.</span></span> <span data-ttu-id="a212d-113">Dla typu składnika majątku lub składnika majątku można skonfigurować atrybuty dla objętości silnika, zużycia energii i maksymalnej pojemności w różnych warunkach.</span><span class="sxs-lookup"><span data-stu-id="a212d-113">For an asset type or an asset, you can set up attributes for engine volume, power consumption, and maximum load capacity under different conditions.</span></span>

## <a name="create-attribute-types"></a><span data-ttu-id="a212d-114">Tworzenie typu atrybutu</span><span class="sxs-lookup"><span data-stu-id="a212d-114">Create attribute types</span></span>

<span data-ttu-id="a212d-115">Tworzenie własnych typów atrybutów.</span><span class="sxs-lookup"><span data-stu-id="a212d-115">You can create your own attribute types.</span></span> <span data-ttu-id="a212d-116">Ponadto można przenosić wymiary produkty do strony **Typy atrybutów**.</span><span class="sxs-lookup"><span data-stu-id="a212d-116">Additionally, you can transfer product dimensions to the **Attribute types** page.</span></span>

1. <span data-ttu-id="a212d-117">Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Typy atrybutów**.</span><span class="sxs-lookup"><span data-stu-id="a212d-117">Select **Asset management** \> **Setup** \> **Attribute types**.</span></span>
2. <span data-ttu-id="a212d-118">Przy pierwszym ustawianiu typów atrybutów wybierz opcję **Utwórz wymiary produktu**, aby automatycznie przenieść standardowe wymiary produktu.</span><span class="sxs-lookup"><span data-stu-id="a212d-118">The first time that you set up attribute types, select **Create product dimensions** to automatically transfer standard product dimensions.</span></span>
3. <span data-ttu-id="a212d-119">Wybierz pozycję **Nowy**, aby utworzyć nowy typ atrybutu.</span><span class="sxs-lookup"><span data-stu-id="a212d-119">Select **New** to create a new attribute type.</span></span>
4. <span data-ttu-id="a212d-120">W polu **Typ atrybutu** wprowadź nazwę typu atrybutu.</span><span class="sxs-lookup"><span data-stu-id="a212d-120">In the **Attribute type** field, enter a name for the attribute type.</span></span>
5. <span data-ttu-id="a212d-121">W polu **Opis wprowadź** opis.</span><span class="sxs-lookup"><span data-stu-id="a212d-121">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="a212d-122">W polu **Jednostka** wybierz odpowiednią jednostkę atrybutu, zgodnie z wymaganiami.</span><span class="sxs-lookup"><span data-stu-id="a212d-122">In the **Unit** field, select the relevant attribute unit, as required.</span></span>
7. <span data-ttu-id="a212d-123">W polu **Typ daty** wybierz typ daty dla jednostki.</span><span class="sxs-lookup"><span data-stu-id="a212d-123">In the **Data type** field, select a data type for the unit.</span></span>
8. <span data-ttu-id="a212d-124">Jeśli wybrano **Ciąg** jako typ danych, wykonaj następujące kroki, aby utworzyć wartości dla typu atrybutu:</span><span class="sxs-lookup"><span data-stu-id="a212d-124">If you selected **String** as the data type, follow these steps to create values for the attribute type:</span></span>

    1. <span data-ttu-id="a212d-125">Wybierz typ atrybutu, a następnie wybierz **Wartości**.</span><span class="sxs-lookup"><span data-stu-id="a212d-125">Select the attribute type, and then select **Values**.</span></span>
    2. <span data-ttu-id="a212d-126">W polu **Wartości atrybutu** wybierz wartość **Nowa**.</span><span class="sxs-lookup"><span data-stu-id="a212d-126">In the **Attribute values** field, select **New**.</span></span>
    3. <span data-ttu-id="a212d-127">W polu **Typ atrybutu** wybierz typ atrybutu (wymiar).</span><span class="sxs-lookup"><span data-stu-id="a212d-127">In the **Attribute type** field, select an attribute type (dimension).</span></span>
    4. <span data-ttu-id="a212d-128">W polu **Wartość** wpisz wartość powiązaną.</span><span class="sxs-lookup"><span data-stu-id="a212d-128">In the **Value** field, enter a related value.</span></span>
    5. <span data-ttu-id="a212d-129">W polu **Opis wprowadź** opis.</span><span class="sxs-lookup"><span data-stu-id="a212d-129">In the **Description** field, enter a description.</span></span>
    6. <span data-ttu-id="a212d-130">Zapisz rekord.</span><span class="sxs-lookup"><span data-stu-id="a212d-130">Save the record.</span></span>
    7. <span data-ttu-id="a212d-131">Wróć do strony **Typy atrybutów**.</span><span class="sxs-lookup"><span data-stu-id="a212d-131">Return to the **Attribute types** page.</span></span>

9. <span data-ttu-id="a212d-132">Zapisz rekord.</span><span class="sxs-lookup"><span data-stu-id="a212d-132">Save the record.</span></span>

    <span data-ttu-id="a212d-133">Pole **Typy lokalizacji czynności konserwacyjnych** pokazuje liczbę lokalizacji funkcjonalnych, które używają typu atrybutu.</span><span class="sxs-lookup"><span data-stu-id="a212d-133">The **Functional location types** field shows the number of functional locations that are using the attribute type.</span></span> <span data-ttu-id="a212d-134">Pole **Typy składników majątku** zawiera liczbę typów składników majątku, które są używane.</span><span class="sxs-lookup"><span data-stu-id="a212d-134">The **Asset types** field shows the number of asset types that are using it.</span></span>
