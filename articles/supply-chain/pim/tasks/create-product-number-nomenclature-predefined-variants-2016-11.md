---
title: Tworzenie konwencji nazewnictwa identyfikatorów produktów dla wstępnie zdefiniowanych wariantów produktu
description: Ten temat pokazuje, jak skonfigurować konwencję nazewnictwa numerów produktu dla wstępnie zdefiniowanych wariantów produktu i jak ją przypisać do odpowiedniej grupy wymiarów produktu.
author: ShylaThompson
manager: tfehr
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6a4ad70a87cd8c6cab2e9853f4f6c52f574d318a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5257430"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a><span data-ttu-id="3bbbf-103">Tworzenie konwencji nazewnictwa identyfikatorów produktów dla wstępnie zdefiniowanych wariantów produktu</span><span class="sxs-lookup"><span data-stu-id="3bbbf-103">Create a product number nomenclature for predefined product variants</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3bbbf-104">Ten temat pokazuje, jak skonfigurować konwencję nazewnictwa numerów produktu dla wstępnie zdefiniowanych wariantów produktu i jak ją przypisać do odpowiedniej grupy wymiarów produktu.</span><span class="sxs-lookup"><span data-stu-id="3bbbf-104">This topic explains how to set up a product number nomenclature for predefined product variants, and how you assign it to the appropriate product dimension group.</span></span> <span data-ttu-id="3bbbf-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="3bbbf-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="3bbbf-106">Nowa konwencja nazewnictwa numerów produktu jest przypisana do grupy wymiarów koloru i rozmiaru.</span><span class="sxs-lookup"><span data-stu-id="3bbbf-106">The new product number nomenclature is assigned to the Color and Size product dimension group.</span></span> <span data-ttu-id="3bbbf-107">Zazwyczaj zadanie wykonuje projektant produktów.</span><span class="sxs-lookup"><span data-stu-id="3bbbf-107">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="3bbbf-108">Tworzenie konwencji nazewnictwa numerów produktu</span><span class="sxs-lookup"><span data-stu-id="3bbbf-108">Create a product number nomenclature</span></span>
1. <span data-ttu-id="3bbbf-109">Wybierz **Definicja modelu wariantu produktu**.</span><span class="sxs-lookup"><span data-stu-id="3bbbf-109">Select **Product variant model definition**.</span></span>
2. <span data-ttu-id="3bbbf-110">Wybierz **Nazewnictwo produktów**.</span><span class="sxs-lookup"><span data-stu-id="3bbbf-110">Select **Product nomenclature**.</span></span>
3. <span data-ttu-id="3bbbf-111">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="3bbbf-111">Select **New**.</span></span>
4. <span data-ttu-id="3bbbf-112">W polu **Nazwa** wprowadź nazwę konwencji nazewnictwa, która pomoże w identyfikacji docelowej grupy wymiarów produktu, na przykład `ColorSize`.</span><span class="sxs-lookup"><span data-stu-id="3bbbf-112">In the **Name** field, enter a nomenclature name that helps to identify the target product dimension group, for example, `ColorSize`.</span></span>
5. <span data-ttu-id="3bbbf-113">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3bbbf-113">In the **Description** field, type a value.</span></span>
6. <span data-ttu-id="3bbbf-114">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="3bbbf-114">Select **Add**.</span></span>
7. <span data-ttu-id="3bbbf-115">Wybierz numer **produktu głównego**.</span><span class="sxs-lookup"><span data-stu-id="3bbbf-115">Select **Product master** number.</span></span>
8. <span data-ttu-id="3bbbf-116">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="3bbbf-116">Select **Add**.</span></span>
9. <span data-ttu-id="3bbbf-117">Wybierz **Stała tekstowa**.</span><span class="sxs-lookup"><span data-stu-id="3bbbf-117">Select **Text constant**.</span></span>
10. <span data-ttu-id="3bbbf-118">W polu **Tekst** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3bbbf-118">In the **Text** field, type a value.</span></span>
11. <span data-ttu-id="3bbbf-119">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="3bbbf-119">Select **Add**.</span></span>
12. <span data-ttu-id="3bbbf-120">Wybierz **Kolor**.</span><span class="sxs-lookup"><span data-stu-id="3bbbf-120">Select **Color**.</span></span>
13. <span data-ttu-id="3bbbf-121">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="3bbbf-121">Select **Add**.</span></span>
14. <span data-ttu-id="3bbbf-122">Wybierz **Stała tekstowa**.</span><span class="sxs-lookup"><span data-stu-id="3bbbf-122">Select **Text constant**.</span></span>
15. <span data-ttu-id="3bbbf-123">W polu **Tekst** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3bbbf-123">In the **Text** field, type a value.</span></span>
16. <span data-ttu-id="3bbbf-124">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="3bbbf-124">Select **Add**.</span></span>
17. <span data-ttu-id="3bbbf-125">Wybierz **Rozmiar**.</span><span class="sxs-lookup"><span data-stu-id="3bbbf-125">Select **Size**.</span></span>
18. <span data-ttu-id="3bbbf-126">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3bbbf-126">Close the page.</span></span>

## <a name="assign-the-nomenclature-to-a-product-master"></a><span data-ttu-id="3bbbf-127">Przypisywanie konwencji nazewnictwa do produktu głównego</span><span class="sxs-lookup"><span data-stu-id="3bbbf-127">Assign the nomenclature to a product master</span></span>
1. <span data-ttu-id="3bbbf-128">Wybierz **Grupy wymiarów produktu**.</span><span class="sxs-lookup"><span data-stu-id="3bbbf-128">Select **Product dimension groups**.</span></span>
2. <span data-ttu-id="3bbbf-129">Zaznacz grupę **wymiarów produktu SizeCol**.</span><span class="sxs-lookup"><span data-stu-id="3bbbf-129">Select the **SizeCol product dimension** group.</span></span>
3. <span data-ttu-id="3bbbf-130">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="3bbbf-130">Select **Edit**.</span></span>
4. <span data-ttu-id="3bbbf-131">W polu **Użyj nazewnictwa** zaznacz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="3bbbf-131">Select **Yes** in the **Use nomenclature** field.</span></span>
5. <span data-ttu-id="3bbbf-132">W polu **Nazewnictwo numerów wariantów produktu** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="3bbbf-132">In the **Product variant number nomenclature** field, enter or select a value.</span></span>
6. <span data-ttu-id="3bbbf-133">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3bbbf-133">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]