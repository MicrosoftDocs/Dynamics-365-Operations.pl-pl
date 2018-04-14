--- 
title: "Kojarzenie indeksu paliwa z przewoźnikiem jako opłaty za usługi dodatkowe"
description: "W tym podręczniku pokazano sposób tworzenia przypisania usług dodatkowych, opłaty za usługi dodatkowe przewoźnika i danych głównych usług dodatkowych dla dopłaty za paliwo, a także kojarzenia indeksu paliwowego przewoźnika z przewoźnikiem."
author: BibiSp
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 101ebe4a2e177a5702a162297e1820598e56a6e5
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---
# <a name="associate-a-fuel-index-with-a-carrier-as-an-accessorial-charge"></a><span data-ttu-id="068fc-103">Kojarzenie indeksu paliwa z przewoźnikiem jako opłaty za usługi dodatkowe</span><span class="sxs-lookup"><span data-stu-id="068fc-103">Associate a fuel index with a carrier as an accessorial charge</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="068fc-104">W tym podręczniku pokazano sposób tworzenia przypisania usług dodatkowych, opłaty za usługi dodatkowe przewoźnika i danych głównych usług dodatkowych dla dopłaty za paliwo, a także kojarzenia indeksu paliwowego przewoźnika z przewoźnikiem.</span><span class="sxs-lookup"><span data-stu-id="068fc-104">This guide shows how to create an accessorial assignment, carrier accessorial charge, accessorial master for fuel surcharge, and associate a carrier fuel index with a carrier.</span></span> <span data-ttu-id="068fc-105">Przed wykonaniem zadań z tego przewodnika należy utworzyć indeks paliwowy przewoźnika.</span><span class="sxs-lookup"><span data-stu-id="068fc-105">You need to have set up a carrier fuel index before you run this guide.</span></span> <span data-ttu-id="068fc-106">Do tego celu służy przewodnik „Konfigurowanie indeksu paliwowego przewoźnika”.</span><span class="sxs-lookup"><span data-stu-id="068fc-106">You can use the “Set up a carrier fuel index” guide to do this.</span></span> <span data-ttu-id="068fc-107">Te zadania konfiguracyjne z reguły są wykonywane przez menedżera logistyki.</span><span class="sxs-lookup"><span data-stu-id="068fc-107">These setup tasks are typically done by a Logistics manager.</span></span> <span data-ttu-id="068fc-108">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="068fc-108">The demo data used to create this procedure is USMF.</span></span>


## <a name="create-an-accessorial-master"></a><span data-ttu-id="068fc-109">Tworzenie danych głównych usług dodatkowych</span><span class="sxs-lookup"><span data-stu-id="068fc-109">Create an accessorial master</span></span>
1. <span data-ttu-id="068fc-110">Wybierz kolejno opcje Zarządzanie transportem > Ustawienia > Ocena > Główne usługi dodatkowe.</span><span class="sxs-lookup"><span data-stu-id="068fc-110">Go to Transportation management > Setup > Rating > Accessorial masters.</span></span>
2. <span data-ttu-id="068fc-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="068fc-111">Click New.</span></span>
3. <span data-ttu-id="068fc-112">W polu Główne dodatkowe usługi wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="068fc-112">In the Accessorial master field, type a value.</span></span>
4. <span data-ttu-id="068fc-113">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="068fc-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="068fc-114">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="068fc-114">Click Save.</span></span>

## <a name="create-a-carrier-accessorial-charge"></a><span data-ttu-id="068fc-115">Tworzenie opłaty za usługi dodatkowe przewoźnika</span><span class="sxs-lookup"><span data-stu-id="068fc-115">Create a carrier accessorial charge</span></span>
1. <span data-ttu-id="068fc-116">Wybierz kolejno opcje Zarządzanie transportem > Ustawienia > Ocena > Opłaty za usługi dodatkowe przewoźnika.</span><span class="sxs-lookup"><span data-stu-id="068fc-116">Go to Transportation management > Setup > Rating > Carrier accessorial charges.</span></span>
2. <span data-ttu-id="068fc-117">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="068fc-117">Click New.</span></span>
3. <span data-ttu-id="068fc-118">W polu Identyfikator współpracownika przewoźnika wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="068fc-118">In the Carrier accessorial ID field, type a value.</span></span>
4. <span data-ttu-id="068fc-119">W polu Firma przewozowa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="068fc-119">In the Shipping carrier field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="068fc-120">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="068fc-120">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="068fc-121">W tym przykładzie wybierz opcję Przewoźnik ciężarowy.</span><span class="sxs-lookup"><span data-stu-id="068fc-121">In this example, choose Truck Carrier.</span></span>  
6. <span data-ttu-id="068fc-122">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="068fc-122">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="068fc-123">W polu Usługa przewozowa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="068fc-123">In the Carrier service field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="068fc-124">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="068fc-124">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="068fc-125">W polu Główne dodatkowe usługi kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="068fc-125">In the Accessorial master field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="068fc-126">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="068fc-126">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="068fc-127">W tym przykładzie wybierz nowo utworzone dane główne usług dodatkowych.</span><span class="sxs-lookup"><span data-stu-id="068fc-127">In this example, choose the newly created Accessorial master.</span></span>  
11. <span data-ttu-id="068fc-128">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="068fc-128">Click Save.</span></span>

## <a name="create-an-accessorial-assignment"></a><span data-ttu-id="068fc-129">Tworzenie przypisania usług dodatkowych</span><span class="sxs-lookup"><span data-stu-id="068fc-129">Create an accessorial assignment</span></span>
1. <span data-ttu-id="068fc-130">Kliknij opcję Przypisania usług dodatkowych.</span><span class="sxs-lookup"><span data-stu-id="068fc-130">Click Accessorial assignments.</span></span>
2. <span data-ttu-id="068fc-131">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="068fc-131">Click New.</span></span>
3. <span data-ttu-id="068fc-132">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="068fc-132">In the Name field, type a value.</span></span>
4. <span data-ttu-id="068fc-133">Przełącz rozwinięcie sekcji Kryteria.</span><span class="sxs-lookup"><span data-stu-id="068fc-133">Toggle the expansion of the Criteria section.</span></span>
    * <span data-ttu-id="068fc-134">W kryteriach można określić, aby dopłata za paliwo była stosowana zawsze, lub — jak w tym przykładzie — że ma dotyczyć tylko określonego regionu.</span><span class="sxs-lookup"><span data-stu-id="068fc-134">In the criteria, you can choose to always apply the fuel surcharge or for this example choose that it only applies within a certain region.</span></span>  
5. <span data-ttu-id="068fc-135">W polu Początkowy kod pocztowy wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="068fc-135">In the ZIP/postal code from field, type a value.</span></span>
6. <span data-ttu-id="068fc-136">W polu Końcowy kod pocztowy wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="068fc-136">In the ZIP/postal code to field, type a value.</span></span>
7. <span data-ttu-id="068fc-137">Przełącz rozwinięcie sekcji Obliczanie.</span><span class="sxs-lookup"><span data-stu-id="068fc-137">Toggle the expansion of the Calculation section.</span></span>
    * <span data-ttu-id="068fc-138">W sekcji obliczeń można określić sposób obliczania dopłaty za paliwo.</span><span class="sxs-lookup"><span data-stu-id="068fc-138">In the calculation section you can specify how to calculate the fuel surcharge.</span></span> <span data-ttu-id="068fc-139">To obliczenie zależy od jednostki usług dodatkowych wybranej jako podstawa do obliczeń.</span><span class="sxs-lookup"><span data-stu-id="068fc-139">This calculation depends on the Accessorial unit that you chose as the base for your calculation.</span></span>  
8. <span data-ttu-id="068fc-140">W polu Typ opłaty za usługi dodatkowe wybierz opcję „Dopłata za paliwo”.</span><span class="sxs-lookup"><span data-stu-id="068fc-140">In the Accessorial fee type field, select 'Fuel surcharge'.</span></span>
9. <span data-ttu-id="068fc-141">W polu Jednostka usług dodatkowych wybierz opcję „Przebieg”.</span><span class="sxs-lookup"><span data-stu-id="068fc-141">In the Accessorial unit field, select 'Mileage'.</span></span>
10. <span data-ttu-id="068fc-142">W polu Region kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="068fc-142">In the Region field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="068fc-143">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="068fc-143">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="068fc-144">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="068fc-144">Click Save.</span></span>

## <a name="update-the-carrier-rating-profile"></a><span data-ttu-id="068fc-145">Aktualizowanie profilu wyznaczania stawek przewoźnika</span><span class="sxs-lookup"><span data-stu-id="068fc-145">Update the carrier rating profile</span></span>
1. <span data-ttu-id="068fc-146">Wybierz kolejno opcje Zarządzanie transportem > Ustawienia > Przewoźnicy > Firmy przewozowe.</span><span class="sxs-lookup"><span data-stu-id="068fc-146">Go to Transportation management > Setup > Carriers > Shipping carriers.</span></span>
2. <span data-ttu-id="068fc-147">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="068fc-147">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="068fc-148">Przełącz rozwinięcie sekcji Profile oceny.</span><span class="sxs-lookup"><span data-stu-id="068fc-148">Toggle the expansion of the Rating profiles section.</span></span>
4. <span data-ttu-id="068fc-149">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="068fc-149">Click Edit.</span></span>
5. <span data-ttu-id="068fc-150">W polu Indeks paliwa przewoźnika kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="068fc-150">In the Carrier fuel index field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="068fc-151">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="068fc-151">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="068fc-152">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="068fc-152">Click Save.</span></span>


