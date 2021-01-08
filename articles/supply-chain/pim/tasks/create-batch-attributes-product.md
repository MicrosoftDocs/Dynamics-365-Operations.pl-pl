---
title: Tworzenie atrybutów partii dla produktu
description: W tej procedurze pokazano sposób tworzenia atrybutu partii, przypisywania domyślnych zakresów wartości oraz umieszczania atrybutu w grupie.
author: ShylaThompson
manager: tfehr
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PdsBatchAttrib
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8924eedfbb635ca04aa167d7f6c44872fef496fd
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435230"
---
# <a name="create-batch-attributes-for-a-product"></a><span data-ttu-id="e3580-103">Tworzenie atrybutów partii dla produktu</span><span class="sxs-lookup"><span data-stu-id="e3580-103">Create batch attributes for a product</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e3580-104">W tej procedurze pokazano sposób tworzenia atrybutu partii, przypisywania domyślnych zakresów wartości oraz umieszczania atrybutu w grupie.</span><span class="sxs-lookup"><span data-stu-id="e3580-104">This procedure shows how to create a batch attribute, assign default value ranges, and include the attribute in a group.</span></span> <span data-ttu-id="e3580-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USP2.</span><span class="sxs-lookup"><span data-stu-id="e3580-105">The demo data company used to create this procedure is the USP2 Company.</span></span>

1. <span data-ttu-id="e3580-106">Kliknij kolejno opcje Zarządzanie zapasami > Ustawienia > Partia > Atrybuty partii.</span><span class="sxs-lookup"><span data-stu-id="e3580-106">Go to Inventory management > Setup > Batch > Batch attributes.</span></span>
2. <span data-ttu-id="e3580-107">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e3580-107">Click New.</span></span>
3. <span data-ttu-id="e3580-108">W polu Atrybut wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e3580-108">In the Attribute field, type a value.</span></span>
4. <span data-ttu-id="e3580-109">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="e3580-109">In the Description field, type a value.</span></span>
5. <span data-ttu-id="e3580-110">W polu Typ atrybutu zaznacz opcję „Ułamek”.</span><span class="sxs-lookup"><span data-stu-id="e3580-110">In the Attribute type field, select 'Fraction'.</span></span>
    * <span data-ttu-id="e3580-111">Ta procedura wykorzystuje typ Ułamek, aby włączyć obsługę wartości dziesiętnych.</span><span class="sxs-lookup"><span data-stu-id="e3580-111">This procedure uses the Fraction type to enable decimal values.</span></span> <span data-ttu-id="e3580-112">Można wybrać inne typy atrybutów.</span><span class="sxs-lookup"><span data-stu-id="e3580-112">You can select other attribute types.</span></span> <span data-ttu-id="e3580-113">Jeśli zostanie wybrany typ Wyliczenie, należy wprowadzić wartości na liście wyliczeń, zanim będzie można wprowadzić wartość w polu Obiekt docelowy.</span><span class="sxs-lookup"><span data-stu-id="e3580-113">If you select the Enumeration type, you must enter values in the enumeration list before you can enter a value in the Target field.</span></span>  
6. <span data-ttu-id="e3580-114">W polu Minimum wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="e3580-114">In the Minimum field, enter a number.</span></span>
7. <span data-ttu-id="e3580-115">W polu Maksimum wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="e3580-115">In the Maximum field, enter a number.</span></span>
8. <span data-ttu-id="e3580-116">W polu Przyrost wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="e3580-116">In the Increment field, enter a number.</span></span>
9. <span data-ttu-id="e3580-117">W polu Obiekt docelowy wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e3580-117">In the Target field, type a value.</span></span>
10. <span data-ttu-id="e3580-118">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="e3580-118">Click Save.</span></span>
11. <span data-ttu-id="e3580-119">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e3580-119">Close the page.</span></span>
12. <span data-ttu-id="e3580-120">Kliknij kolejno opcje Zarządzanie zapasami > Ustawienia > Partia > Grupy atrybutów partii.</span><span class="sxs-lookup"><span data-stu-id="e3580-120">Go to Inventory management > Setup > Batch > Batch attribute groups.</span></span>
13. <span data-ttu-id="e3580-121">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e3580-121">Click New.</span></span>
14. <span data-ttu-id="e3580-122">W polu Grupa atrybutów wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e3580-122">In the Attribute group field, type a value.</span></span>
15. <span data-ttu-id="e3580-123">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="e3580-123">In the Description field, type a value.</span></span>
16. <span data-ttu-id="e3580-124">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="e3580-124">Click Save.</span></span>
17. <span data-ttu-id="e3580-125">Kliknij Atrybuty grupy.</span><span class="sxs-lookup"><span data-stu-id="e3580-125">Click Group attributes.</span></span>
18. <span data-ttu-id="e3580-126">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e3580-126">Click New.</span></span>
19. <span data-ttu-id="e3580-127">W polu Atrybut kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="e3580-127">In the Attribute field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="e3580-128">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="e3580-128">In the list, find and select the desired record.</span></span>
21. <span data-ttu-id="e3580-129">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="e3580-129">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="e3580-130">Atrybut można umieścić w dowolnej z tych grup.</span><span class="sxs-lookup"><span data-stu-id="e3580-130">An attribute can be included in any of the groups.</span></span>  
22. <span data-ttu-id="e3580-131">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="e3580-131">Click Save.</span></span>
23. <span data-ttu-id="e3580-132">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e3580-132">Close the page.</span></span>

