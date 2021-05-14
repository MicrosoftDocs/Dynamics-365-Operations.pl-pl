---
title: Tworzenie konwencji nazewnictwa identyfikatorów produktów dla wstępnie zdefiniowanych wariantów produktu
description: Ten temat pokazuje, jak skonfigurować konwencję nazewnictwa numerów produktu dla wstępnie zdefiniowanych wariantów produktu i jak ją przypisać do odpowiedniej grupy wymiarów produktu.
author: ShylaThompson
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4bb73854f52525c0722683086d1b4f1dd7173306
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920664"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a><span data-ttu-id="26d44-103">Tworzenie konwencji nazewnictwa identyfikatorów produktów dla wstępnie zdefiniowanych wariantów produktu</span><span class="sxs-lookup"><span data-stu-id="26d44-103">Create a product number nomenclature for predefined product variants</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="26d44-104">Ten temat pokazuje, jak skonfigurować konwencję nazewnictwa numerów produktu dla wstępnie zdefiniowanych wariantów produktu i jak ją przypisać do odpowiedniej grupy wymiarów produktu.</span><span class="sxs-lookup"><span data-stu-id="26d44-104">This topic explains how to set up a product number nomenclature for predefined product variants, and how you assign it to the appropriate product dimension group.</span></span> <span data-ttu-id="26d44-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="26d44-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="26d44-106">Nowa konwencja nazewnictwa numerów produktu jest przypisana do grupy wymiarów koloru i rozmiaru.</span><span class="sxs-lookup"><span data-stu-id="26d44-106">The new product number nomenclature is assigned to the Color and Size product dimension group.</span></span> <span data-ttu-id="26d44-107">Zazwyczaj zadanie wykonuje projektant produktów.</span><span class="sxs-lookup"><span data-stu-id="26d44-107">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="26d44-108">Tworzenie konwencji nazewnictwa numerów produktu</span><span class="sxs-lookup"><span data-stu-id="26d44-108">Create a product number nomenclature</span></span>

1. <span data-ttu-id="26d44-109">Wybierz kolejno pozycje **Zarządzanie informacjami o produktach \> Ustawienia \> Nazewnictwo produktów**.</span><span class="sxs-lookup"><span data-stu-id="26d44-109">Go to **Product information management \> Setup \> Product nomenclature**.</span></span>
1. <span data-ttu-id="26d44-110">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="26d44-110">Select **New**.</span></span>
1. <span data-ttu-id="26d44-111">W polu **Nazwa** wprowadź nazwę konwencji nazewnictwa, która pomoże w identyfikacji docelowej grupy wymiarów produktu, na przykład `ColorSize`.</span><span class="sxs-lookup"><span data-stu-id="26d44-111">In the **Name** field, enter a nomenclature name that helps to identify the target product dimension group, for example, `ColorSize`.</span></span>
1. <span data-ttu-id="26d44-112">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="26d44-112">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="26d44-113">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="26d44-113">Select **Add**.</span></span>
1. <span data-ttu-id="26d44-114">Wybierz numer **produktu głównego**.</span><span class="sxs-lookup"><span data-stu-id="26d44-114">Select **Product master** number.</span></span>
1. <span data-ttu-id="26d44-115">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="26d44-115">Select **Add**.</span></span>
1. <span data-ttu-id="26d44-116">Wybierz **Stała tekstowa**.</span><span class="sxs-lookup"><span data-stu-id="26d44-116">Select **Text constant**.</span></span>
1. <span data-ttu-id="26d44-117">W polu **Tekst** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="26d44-117">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="26d44-118">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="26d44-118">Select **Add**.</span></span>
1. <span data-ttu-id="26d44-119">Wybierz **Kolor**.</span><span class="sxs-lookup"><span data-stu-id="26d44-119">Select **Color**.</span></span>
1. <span data-ttu-id="26d44-120">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="26d44-120">Select **Add**.</span></span>
1. <span data-ttu-id="26d44-121">Wybierz **Stała tekstowa**.</span><span class="sxs-lookup"><span data-stu-id="26d44-121">Select **Text constant**.</span></span>
1. <span data-ttu-id="26d44-122">W polu **Tekst** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="26d44-122">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="26d44-123">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="26d44-123">Select **Add**.</span></span>
1. <span data-ttu-id="26d44-124">Wybierz **Rozmiar**.</span><span class="sxs-lookup"><span data-stu-id="26d44-124">Select **Size**.</span></span>
1. <span data-ttu-id="26d44-125">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="26d44-125">Close the page.</span></span>

## <a name="assign-the-nomenclature-to-a-product-master"></a><span data-ttu-id="26d44-126">Przypisywanie konwencji nazewnictwa do produktu głównego</span><span class="sxs-lookup"><span data-stu-id="26d44-126">Assign the nomenclature to a product master</span></span>

1. <span data-ttu-id="26d44-127">Wybierz **Grupy wymiarów produktu**.</span><span class="sxs-lookup"><span data-stu-id="26d44-127">Select **Product dimension groups**.</span></span>
2. <span data-ttu-id="26d44-128">Zaznacz grupę **wymiarów produktu SizeCol**.</span><span class="sxs-lookup"><span data-stu-id="26d44-128">Select the **SizeCol product dimension** group.</span></span>
3. <span data-ttu-id="26d44-129">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="26d44-129">Select **Edit**.</span></span>
4. <span data-ttu-id="26d44-130">W polu **Użyj nazewnictwa** zaznacz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="26d44-130">Select **Yes** in the **Use nomenclature** field.</span></span>
5. <span data-ttu-id="26d44-131">W polu **Nazewnictwo numerów wariantów produktu** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="26d44-131">In the **Product variant number nomenclature** field, enter or select a value.</span></span>
6. <span data-ttu-id="26d44-132">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="26d44-132">Close the page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]