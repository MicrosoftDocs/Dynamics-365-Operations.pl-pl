---
title: Zarządzanie usterkami
description: W tym temacie wyjaśniono analizę zarządzania usterkami składników majątku w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetFaultArea, EntAssetFaultDesigner, EntAssetFaultCopyFromObjectType, EntAssetFaultRemedy, EntAssetObjectFaultRelationRequestInfoPart, EntAssetObjectFaultRelationWorkOrderInfoPart, EntAssetFaultCreateCombinations, EntAssetObjectFaultSymptom, EntAssetObjectFaultSymptomListPage, EntAssetFaultType, EntAssetFaultSymptom, EntAssetFaultCause
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 72d6c8d750a5a0903017b4c77b3ce5d9521cf99b
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/25/2020
ms.locfileid: "3889368"
---
# <a name="fault-management"></a><span data-ttu-id="21635-103">Zarządzanie usterkami</span><span class="sxs-lookup"><span data-stu-id="21635-103">Fault management</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="21635-104">W module Zarządzanie składnikami majątku można skorzystać z projektanta usterek, aby skonfigurować objawy usterek, obszary usterek i typy usterek w typach składników majątku.</span><span class="sxs-lookup"><span data-stu-id="21635-104">In Asset Management, you can use the fault designer to set up fault symptoms, fault areas, and fault types on asset types.</span></span> <span data-ttu-id="21635-105">W ten sposób można zarządzać usterkami wykrytymi w składnikach majątku.</span><span class="sxs-lookup"><span data-stu-id="21635-105">In this way, you can manage faults that are detected on assets.</span></span> <span data-ttu-id="21635-106">Ponadto w zleceniu pracy można rejestrować przyczyny usterek i sugestie dotyczące rozwiązania usterek.</span><span class="sxs-lookup"><span data-stu-id="21635-106">Additionally, fault causes and suggestions for fixing faults can be registered on a work order.</span></span>

<span data-ttu-id="21635-107">Proces rejestracji i zarządzania usterką składa się z tych kroków.</span><span class="sxs-lookup"><span data-stu-id="21635-107">The process for fault registration and management consists of these steps.</span></span>

1. <span data-ttu-id="21635-108">Utwórz listę objawów usterek, obszarów usterek i typów usterek, które mogą występować w typach składników majątku.</span><span class="sxs-lookup"><span data-stu-id="21635-108">Create a list of fault symptoms, fault areas, and fault types that might occur on your asset types.</span></span>
2. <span data-ttu-id="21635-109">W projektancie usterek ustaw objawy, obszary usterek i typy usterek.</span><span class="sxs-lookup"><span data-stu-id="21635-109">In the fault designer, set up symptoms, fault areas, and fault types.</span></span>

<span data-ttu-id="21635-110">Poniżej przedstawiono kilka przykładów ułatwiających zrozumienie różnicy między symptomami usterek, obszarami usterek i typami usterek.</span><span class="sxs-lookup"><span data-stu-id="21635-110">Here are some examples to help you understand the difference between fault symptoms, fault areas, and fault types.</span></span>

<span data-ttu-id="21635-111">**Objawy usterki:**</span><span class="sxs-lookup"><span data-stu-id="21635-111">**Fault symptoms:**</span></span>

- <span data-ttu-id="21635-112">Niezbilansowane napięcia</span><span class="sxs-lookup"><span data-stu-id="21635-112">Unbalanced voltages</span></span>
- <span data-ttu-id="21635-113">Krótki obwód</span><span class="sxs-lookup"><span data-stu-id="21635-113">Short circuit</span></span>
- <span data-ttu-id="21635-114">Hałas</span><span class="sxs-lookup"><span data-stu-id="21635-114">Noise</span></span>
- <span data-ttu-id="21635-115">Wyciek</span><span class="sxs-lookup"><span data-stu-id="21635-115">Leak</span></span>
- <span data-ttu-id="21635-116">Wibracje</span><span class="sxs-lookup"><span data-stu-id="21635-116">Vibrations</span></span>

<span data-ttu-id="21635-117">**Obszary usterki:**</span><span class="sxs-lookup"><span data-stu-id="21635-117">**Fault areas:**</span></span>

- <span data-ttu-id="21635-118">Elektryczny</span><span class="sxs-lookup"><span data-stu-id="21635-118">Electrical</span></span>
- <span data-ttu-id="21635-119">Maszynowy</span><span class="sxs-lookup"><span data-stu-id="21635-119">Mechanical</span></span>
- <span data-ttu-id="21635-120">Hydrauliczny</span><span class="sxs-lookup"><span data-stu-id="21635-120">Hydraulic</span></span>
- <span data-ttu-id="21635-121">Pneumatyczny</span><span class="sxs-lookup"><span data-stu-id="21635-121">Pneumatic</span></span>

<span data-ttu-id="21635-122">**Typy usterek:**</span><span class="sxs-lookup"><span data-stu-id="21635-122">**Fault types:**</span></span>

- <span data-ttu-id="21635-123">Błędne uzwojenie głównego wyciągu</span><span class="sxs-lookup"><span data-stu-id="21635-123">Faulty main stator winding</span></span>
- <span data-ttu-id="21635-124">Wadliwa dioda</span><span class="sxs-lookup"><span data-stu-id="21635-124">Faulty diode</span></span>
- <span data-ttu-id="21635-125">Brudne uzwojenia</span><span class="sxs-lookup"><span data-stu-id="21635-125">Dirty windings</span></span>
- <span data-ttu-id="21635-126">Wadliwy generator</span><span class="sxs-lookup"><span data-stu-id="21635-126">Defective generator</span></span>
- <span data-ttu-id="21635-127">Uszkodzony czujnik</span><span class="sxs-lookup"><span data-stu-id="21635-127">Defective sensor</span></span>

## <a name="create-fault-symptoms"></a><span data-ttu-id="21635-128">Utwórz objawy usterki</span><span class="sxs-lookup"><span data-stu-id="21635-128">Create fault symptoms</span></span>

<span data-ttu-id="21635-129">Aby utworzyć listę objawów, które mogą być używane w projektancie usterek, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="21635-129">Follow these steps to create a list of symptoms that can be used in the fault designer.</span></span>

1. <span data-ttu-id="21635-130">Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Usterka** \> **Objawy usterki**.</span><span class="sxs-lookup"><span data-stu-id="21635-130">Select **Asset management** \> **Setup** \> **Fault** \> **Fault symptoms**.</span></span>
2. <span data-ttu-id="21635-131">Wybierz **Nowy**, aby utworzyć rekord.</span><span class="sxs-lookup"><span data-stu-id="21635-131">Select **New** to create a record.</span></span>
3. <span data-ttu-id="21635-132">W polu **Objawy usterki** wprowadź nazwę objawu usterki.</span><span class="sxs-lookup"><span data-stu-id="21635-132">In the **Fault symptom** field, enter a name for the fault symptom.</span></span>
4. <span data-ttu-id="21635-133">W polu **Opis wprowadź** opis.</span><span class="sxs-lookup"><span data-stu-id="21635-133">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="21635-134">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="21635-134">Select **Save**.</span></span>

## <a name="create-fault-areas"></a><span data-ttu-id="21635-135">Tworzenie obszarów usterek</span><span class="sxs-lookup"><span data-stu-id="21635-135">Create fault areas</span></span>

<span data-ttu-id="21635-136">Aby utworzyć listę obszarów lub lokalizacji, które mogą być używane w projektancie usterek, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="21635-136">Follow these steps to create a list of areas or locations that can be used in the fault designer.</span></span>

1. <span data-ttu-id="21635-137">Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Usterka** \> **Obszary usterki**.</span><span class="sxs-lookup"><span data-stu-id="21635-137">Select **Asset management** \> **Setup** \> **Fault** \> **Fault areas**.</span></span>
2. <span data-ttu-id="21635-138">Wybierz **Nowy**, aby utworzyć rekord.</span><span class="sxs-lookup"><span data-stu-id="21635-138">Select **New** to create a record.</span></span>
3. <span data-ttu-id="21635-139">W polu **Obszar usterki** wprowadź nazwę obszaru usterki.</span><span class="sxs-lookup"><span data-stu-id="21635-139">In the **Fault area** field, enter a name for the fault area.</span></span>
4. <span data-ttu-id="21635-140">W polu **Opis wprowadź** opis.</span><span class="sxs-lookup"><span data-stu-id="21635-140">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="21635-141">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="21635-141">Select **Save**.</span></span>

## <a name="create-fault-types"></a><span data-ttu-id="21635-142">Utwórz typy usterek</span><span class="sxs-lookup"><span data-stu-id="21635-142">Create fault types</span></span>

<span data-ttu-id="21635-143">Aby utworzyć listę typów usterek, które mogą być używane w projektancie usterek, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="21635-143">Follow these steps to create a list of fault types that can be used in the fault designer.</span></span>

1. <span data-ttu-id="21635-144">Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Usterka** \> **Typy usterek**.</span><span class="sxs-lookup"><span data-stu-id="21635-144">Select **Asset management** \> **Setup** \> **Fault** \> **Fault types**.</span></span>
2. <span data-ttu-id="21635-145">Wybierz **Nowy**, aby utworzyć rekord.</span><span class="sxs-lookup"><span data-stu-id="21635-145">Select **New** to create a record.</span></span>
3. <span data-ttu-id="21635-146">W polu **Typ usterki** wprowadź nazwę typu usterki.</span><span class="sxs-lookup"><span data-stu-id="21635-146">In the **Fault type** field, enter a name for the fault type.</span></span>
4. <span data-ttu-id="21635-147">W polu **Opis wprowadź** opis.</span><span class="sxs-lookup"><span data-stu-id="21635-147">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="21635-148">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="21635-148">Select **Save**.</span></span>

## <a name="set-up-the-fault-designer"></a><span data-ttu-id="21635-149">Konfigurowanie projektanta usterek</span><span class="sxs-lookup"><span data-stu-id="21635-149">Set up the fault designer</span></span>

<span data-ttu-id="21635-150">W projektancie usterek można skonfigurować dane usterek dla typów składników majątku.</span><span class="sxs-lookup"><span data-stu-id="21635-150">In the fault designer, you set up fault data on asset types.</span></span>

1. <span data-ttu-id="21635-151">Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Usterka** \> **Projektant usterek**.</span><span class="sxs-lookup"><span data-stu-id="21635-151">Select **Asset management** \> **Setup** \> **Fault** \> **Fault designer**.</span></span>
2. <span data-ttu-id="21635-152">W lewym okienku wybierz typ składnika majątku, dla którego chcesz skonfigurować rekord usterki.</span><span class="sxs-lookup"><span data-stu-id="21635-152">In the left pane, select the type of asset to set up a fault record for.</span></span>
3. <span data-ttu-id="21635-153">Na skróconej karcie **Objawy usterki** wybierz opcję **Dodaj wiersz**, a następnie w polu **Objaw usterki** wybierz objaw usterki.</span><span class="sxs-lookup"><span data-stu-id="21635-153">On the **Fault symptom** FastTab, select **Add line**, and then, in the **Fault symptom** field, select a fault symptom.</span></span>
4. <span data-ttu-id="21635-154">Na skróconej karcie **Obszar usterki** wybierz opcję **Dodaj wiersz**, a następnie w polu **Obszar usterki** wybierz obszar usterki.</span><span class="sxs-lookup"><span data-stu-id="21635-154">On the **Fault area** FastTab, select **Add line**, and then, in the **Fault area** field select a fault area.</span></span>
5. <span data-ttu-id="21635-155">Na skróconej karcie **Typ usterki** wybierz opcję **Dodaj wiersz**, a następnie w polu **Typ usterki** wybierz typ usterki.</span><span class="sxs-lookup"><span data-stu-id="21635-155">On the **Fault type** FastTab, select **Add line**, and then, in the **Fault type** field, select a fault type.</span></span>
6. <span data-ttu-id="21635-156">Aby szybko utworzyć kombinacje wszystkich objawów usterek, obszarów i typów dla wybranego typu składnika, wybierz opcję **Utwórz kombinacje usterek**.</span><span class="sxs-lookup"><span data-stu-id="21635-156">To quickly create combinations of all existing fault symptoms, areas, and types for the selected asset type, select **Create fault combinations**.</span></span> <span data-ttu-id="21635-157">Ta funkcja jest przydatna w przypadku dodawania wielu objawów usterek, obszarów i typów.</span><span class="sxs-lookup"><span data-stu-id="21635-157">This function is useful if you've added many fault symptoms, areas, and types.</span></span> <span data-ttu-id="21635-158">Można łatwiej usunąć wiersze dla dowolnej kombinacji, która nie jest odpowiednia dla typu składnika majątku niż w celu ręcznego utworzenia nowych wierszy.</span><span class="sxs-lookup"><span data-stu-id="21635-158">It's easier to delete the lines for any combinations that aren't relevant to the asset type than to create new lines manually.</span></span>

    > [!NOTE]
    > <span data-ttu-id="21635-159">Aby skopiować ustawienia objawów usterek, obszarów i typów z jednego typu składnika majątku do wybranego typu składnika, należy wybrać opcję **Kopiuj z typu składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="21635-159">To copy the setup of fault symptoms, areas, and types from one asset type to the selected asset type, select **Copy from asset type**.</span></span>

7. <span data-ttu-id="21635-160">Wybierz **Zapisz**, żeby zapisać zmiany.</span><span class="sxs-lookup"><span data-stu-id="21635-160">Select **Save** to save your changes.</span></span>

![Strona Projektant usterek](media/21-setup-for-work-orders.png)

## <a name="create-fault-causes"></a><span data-ttu-id="21635-162">Utwórz przyczyny usterek</span><span class="sxs-lookup"><span data-stu-id="21635-162">Create fault causes</span></span>

<span data-ttu-id="21635-163">Wykonaj poniższe kroki, aby utworzyć listę znanych przyczyn usterek, które można dodać do zlecenia pracy lub do zgłoszenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="21635-163">Follow these steps to create a list of known fault causes that can be added to a work order or a maintenance request.</span></span>

1. <span data-ttu-id="21635-164">Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Usterka** \> **Przyczyny usterek**.</span><span class="sxs-lookup"><span data-stu-id="21635-164">Select **Asset management** \> **Setup** \> **Fault** \> **Fault causes**.</span></span>
2. <span data-ttu-id="21635-165">Wybierz **Nowy**, aby utworzyć rekord.</span><span class="sxs-lookup"><span data-stu-id="21635-165">Select **New** to create a record.</span></span>
3. <span data-ttu-id="21635-166">W polu **Przyczyny usterek** wprowadź nazwę przyczyny usterki.</span><span class="sxs-lookup"><span data-stu-id="21635-166">In the **Fault cause** field, enter a name for the fault cause.</span></span>
4. <span data-ttu-id="21635-167">W polu **Opis wprowadź** opis.</span><span class="sxs-lookup"><span data-stu-id="21635-167">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="21635-168">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="21635-168">Select **Save**.</span></span>

## <a name="create-fault-remedies"></a><span data-ttu-id="21635-169">Stwórz środki zaradcze dla usterki</span><span class="sxs-lookup"><span data-stu-id="21635-169">Create fault remedies</span></span>

<span data-ttu-id="21635-170">Wykonaj poniższe kroki, aby utworzyć listę znanych środków zaradczych dla usterek, które można dodać do zlecenia pracy lub do zgłoszenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="21635-170">Follow these steps to create a list of suggestions for remedy and repair that can be added to a work order or a maintenance request.</span></span>

1. <span data-ttu-id="21635-171">Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Usterka** \> **Środki zaradcze dla usterek**.</span><span class="sxs-lookup"><span data-stu-id="21635-171">Select **Asset management** \> **Setup** \> **Fault** \> **Fault remedies**.</span></span>
2. <span data-ttu-id="21635-172">Wybierz **Nowy**, aby utworzyć rekord.</span><span class="sxs-lookup"><span data-stu-id="21635-172">Select **New** to create a record.</span></span>
3. <span data-ttu-id="21635-173">W polu **Środki zaradcze dla usterek** wprowadź nazwę środka zaradczego usterki.</span><span class="sxs-lookup"><span data-stu-id="21635-173">In the **Fault remedy** field, enter a name for the fault remedy.</span></span>
4. <span data-ttu-id="21635-174">W polu **Opis wprowadź** opis.</span><span class="sxs-lookup"><span data-stu-id="21635-174">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="21635-175">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="21635-175">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="21635-176">Istnieje możliwość zmiany nazw objawów usterek, obszarów, typów, przyczyn i środków zaradczych stosownie do potrzeb.</span><span class="sxs-lookup"><span data-stu-id="21635-176">You can change the names of your fault symptoms, areas, types, causes, and remedies as you require.</span></span> <span data-ttu-id="21635-177">Zmiany nazwy są automatycznie odzwierciedlane w powiązanych z nią rejestracjach błędów.</span><span class="sxs-lookup"><span data-stu-id="21635-177">The name changes are automatically reflected in the related fault registrations.</span></span>
