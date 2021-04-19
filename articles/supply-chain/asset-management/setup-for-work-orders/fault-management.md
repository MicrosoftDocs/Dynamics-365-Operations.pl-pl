---
title: Zarządzanie usterkami
description: W tym temacie wyjaśniono analizę zarządzania usterkami składników majątku w module Zarządzanie składnikami majątku.
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetFaultArea, EntAssetFaultDesigner, EntAssetFaultCopyFromObjectType, EntAssetFaultRemedy, EntAssetObjectFaultRelationRequestInfoPart, EntAssetObjectFaultRelationWorkOrderInfoPart, EntAssetFaultCreateCombinations, EntAssetObjectFaultSymptom, EntAssetObjectFaultSymptomListPage, EntAssetFaultType, EntAssetFaultSymptom, EntAssetFaultCause
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: c87bfa057fd2808551674f2acb9d654ad47e9a42
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5825669"
---
# <a name="fault-management"></a><span data-ttu-id="ed35b-103">Zarządzanie usterkami</span><span class="sxs-lookup"><span data-stu-id="ed35b-103">Fault management</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="ed35b-104">W module Zarządzanie składnikami majątku można skorzystać z projektanta usterek, aby skonfigurować objawy usterek, obszary usterek i typy usterek w typach składników majątku.</span><span class="sxs-lookup"><span data-stu-id="ed35b-104">In Asset Management, you can use the fault designer to set up fault symptoms, fault areas, and fault types on asset types.</span></span> <span data-ttu-id="ed35b-105">W ten sposób można zarządzać usterkami wykrytymi w składnikach majątku.</span><span class="sxs-lookup"><span data-stu-id="ed35b-105">In this way, you can manage faults that are detected on assets.</span></span> <span data-ttu-id="ed35b-106">Ponadto w zleceniu pracy można rejestrować przyczyny usterek i sugestie dotyczące rozwiązania usterek.</span><span class="sxs-lookup"><span data-stu-id="ed35b-106">Additionally, fault causes and suggestions for fixing faults can be registered on a work order.</span></span>

<span data-ttu-id="ed35b-107">Proces rejestracji i zarządzania usterką składa się z tych kroków.</span><span class="sxs-lookup"><span data-stu-id="ed35b-107">The process for fault registration and management consists of these steps.</span></span>

1. <span data-ttu-id="ed35b-108">Utwórz listę objawów usterek, obszarów usterek i typów usterek, które mogą występować w typach składników majątku.</span><span class="sxs-lookup"><span data-stu-id="ed35b-108">Create a list of fault symptoms, fault areas, and fault types that might occur on your asset types.</span></span>
2. <span data-ttu-id="ed35b-109">W projektancie usterek ustaw objawy, obszary usterek i typy usterek.</span><span class="sxs-lookup"><span data-stu-id="ed35b-109">In the fault designer, set up symptoms, fault areas, and fault types.</span></span>

<span data-ttu-id="ed35b-110">Poniżej przedstawiono kilka przykładów ułatwiających zrozumienie różnicy między symptomami usterek, obszarami usterek i typami usterek.</span><span class="sxs-lookup"><span data-stu-id="ed35b-110">Here are some examples to help you understand the difference between fault symptoms, fault areas, and fault types.</span></span>

<span data-ttu-id="ed35b-111">**Objawy usterki:**</span><span class="sxs-lookup"><span data-stu-id="ed35b-111">**Fault symptoms:**</span></span>

- <span data-ttu-id="ed35b-112">Niezbilansowane napięcia</span><span class="sxs-lookup"><span data-stu-id="ed35b-112">Unbalanced voltages</span></span>
- <span data-ttu-id="ed35b-113">Krótki obwód</span><span class="sxs-lookup"><span data-stu-id="ed35b-113">Short circuit</span></span>
- <span data-ttu-id="ed35b-114">Hałas</span><span class="sxs-lookup"><span data-stu-id="ed35b-114">Noise</span></span>
- <span data-ttu-id="ed35b-115">Wyciek</span><span class="sxs-lookup"><span data-stu-id="ed35b-115">Leak</span></span>
- <span data-ttu-id="ed35b-116">Wibracje</span><span class="sxs-lookup"><span data-stu-id="ed35b-116">Vibrations</span></span>

<span data-ttu-id="ed35b-117">**Obszary usterki:**</span><span class="sxs-lookup"><span data-stu-id="ed35b-117">**Fault areas:**</span></span>

- <span data-ttu-id="ed35b-118">Elektryczny</span><span class="sxs-lookup"><span data-stu-id="ed35b-118">Electrical</span></span>
- <span data-ttu-id="ed35b-119">Maszynowy</span><span class="sxs-lookup"><span data-stu-id="ed35b-119">Mechanical</span></span>
- <span data-ttu-id="ed35b-120">Hydrauliczny</span><span class="sxs-lookup"><span data-stu-id="ed35b-120">Hydraulic</span></span>
- <span data-ttu-id="ed35b-121">Pneumatyczny</span><span class="sxs-lookup"><span data-stu-id="ed35b-121">Pneumatic</span></span>

<span data-ttu-id="ed35b-122">**Typy usterek:**</span><span class="sxs-lookup"><span data-stu-id="ed35b-122">**Fault types:**</span></span>

- <span data-ttu-id="ed35b-123">Błędne uzwojenie głównego wyciągu</span><span class="sxs-lookup"><span data-stu-id="ed35b-123">Faulty main stator winding</span></span>
- <span data-ttu-id="ed35b-124">Wadliwa dioda</span><span class="sxs-lookup"><span data-stu-id="ed35b-124">Faulty diode</span></span>
- <span data-ttu-id="ed35b-125">Brudne uzwojenia</span><span class="sxs-lookup"><span data-stu-id="ed35b-125">Dirty windings</span></span>
- <span data-ttu-id="ed35b-126">Wadliwy generator</span><span class="sxs-lookup"><span data-stu-id="ed35b-126">Defective generator</span></span>
- <span data-ttu-id="ed35b-127">Uszkodzony czujnik</span><span class="sxs-lookup"><span data-stu-id="ed35b-127">Defective sensor</span></span>

## <a name="create-fault-symptoms"></a><span data-ttu-id="ed35b-128">Utwórz objawy usterki</span><span class="sxs-lookup"><span data-stu-id="ed35b-128">Create fault symptoms</span></span>

<span data-ttu-id="ed35b-129">Aby utworzyć listę objawów, które mogą być używane w projektancie usterek, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="ed35b-129">Follow these steps to create a list of symptoms that can be used in the fault designer.</span></span>

1. <span data-ttu-id="ed35b-130">Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Usterka** \> **Objawy usterki**.</span><span class="sxs-lookup"><span data-stu-id="ed35b-130">Select **Asset management** \> **Setup** \> **Fault** \> **Fault symptoms**.</span></span>
2. <span data-ttu-id="ed35b-131">Wybierz **Nowy**, aby utworzyć rekord.</span><span class="sxs-lookup"><span data-stu-id="ed35b-131">Select **New** to create a record.</span></span>
3. <span data-ttu-id="ed35b-132">W polu **Objawy usterki** wprowadź nazwę objawu usterki.</span><span class="sxs-lookup"><span data-stu-id="ed35b-132">In the **Fault symptom** field, enter a name for the fault symptom.</span></span>
4. <span data-ttu-id="ed35b-133">W polu **Opis wprowadź** opis.</span><span class="sxs-lookup"><span data-stu-id="ed35b-133">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="ed35b-134">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="ed35b-134">Select **Save**.</span></span>

## <a name="create-fault-areas"></a><span data-ttu-id="ed35b-135">Tworzenie obszarów usterek</span><span class="sxs-lookup"><span data-stu-id="ed35b-135">Create fault areas</span></span>

<span data-ttu-id="ed35b-136">Aby utworzyć listę obszarów lub lokalizacji, które mogą być używane w projektancie usterek, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="ed35b-136">Follow these steps to create a list of areas or locations that can be used in the fault designer.</span></span>

1. <span data-ttu-id="ed35b-137">Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Usterka** \> **Obszary usterki**.</span><span class="sxs-lookup"><span data-stu-id="ed35b-137">Select **Asset management** \> **Setup** \> **Fault** \> **Fault areas**.</span></span>
2. <span data-ttu-id="ed35b-138">Wybierz **Nowy**, aby utworzyć rekord.</span><span class="sxs-lookup"><span data-stu-id="ed35b-138">Select **New** to create a record.</span></span>
3. <span data-ttu-id="ed35b-139">W polu **Obszar usterki** wprowadź nazwę obszaru usterki.</span><span class="sxs-lookup"><span data-stu-id="ed35b-139">In the **Fault area** field, enter a name for the fault area.</span></span>
4. <span data-ttu-id="ed35b-140">W polu **Opis wprowadź** opis.</span><span class="sxs-lookup"><span data-stu-id="ed35b-140">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="ed35b-141">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="ed35b-141">Select **Save**.</span></span>

## <a name="create-fault-types"></a><span data-ttu-id="ed35b-142">Utwórz typy usterek</span><span class="sxs-lookup"><span data-stu-id="ed35b-142">Create fault types</span></span>

<span data-ttu-id="ed35b-143">Aby utworzyć listę typów usterek, które mogą być używane w projektancie usterek, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="ed35b-143">Follow these steps to create a list of fault types that can be used in the fault designer.</span></span>

1. <span data-ttu-id="ed35b-144">Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Usterka** \> **Typy usterek**.</span><span class="sxs-lookup"><span data-stu-id="ed35b-144">Select **Asset management** \> **Setup** \> **Fault** \> **Fault types**.</span></span>
2. <span data-ttu-id="ed35b-145">Wybierz **Nowy**, aby utworzyć rekord.</span><span class="sxs-lookup"><span data-stu-id="ed35b-145">Select **New** to create a record.</span></span>
3. <span data-ttu-id="ed35b-146">W polu **Typ usterki** wprowadź nazwę typu usterki.</span><span class="sxs-lookup"><span data-stu-id="ed35b-146">In the **Fault type** field, enter a name for the fault type.</span></span>
4. <span data-ttu-id="ed35b-147">W polu **Opis wprowadź** opis.</span><span class="sxs-lookup"><span data-stu-id="ed35b-147">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="ed35b-148">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="ed35b-148">Select **Save**.</span></span>

## <a name="set-up-the-fault-designer"></a><span data-ttu-id="ed35b-149">Konfigurowanie projektanta usterek</span><span class="sxs-lookup"><span data-stu-id="ed35b-149">Set up the fault designer</span></span>

<span data-ttu-id="ed35b-150">W projektancie usterek można skonfigurować dane usterek dla typów składników majątku.</span><span class="sxs-lookup"><span data-stu-id="ed35b-150">In the fault designer, you set up fault data on asset types.</span></span>

1. <span data-ttu-id="ed35b-151">Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Usterka** \> **Projektant usterek**.</span><span class="sxs-lookup"><span data-stu-id="ed35b-151">Select **Asset management** \> **Setup** \> **Fault** \> **Fault designer**.</span></span>
2. <span data-ttu-id="ed35b-152">W lewym okienku wybierz typ składnika majątku, dla którego chcesz skonfigurować rekord usterki.</span><span class="sxs-lookup"><span data-stu-id="ed35b-152">In the left pane, select the type of asset to set up a fault record for.</span></span>
3. <span data-ttu-id="ed35b-153">Na skróconej karcie **Objawy usterki** wybierz opcję **Dodaj wiersz**, a następnie w polu **Objaw usterki** wybierz objaw usterki.</span><span class="sxs-lookup"><span data-stu-id="ed35b-153">On the **Fault symptom** FastTab, select **Add line**, and then, in the **Fault symptom** field, select a fault symptom.</span></span>
4. <span data-ttu-id="ed35b-154">Na skróconej karcie **Obszar usterki** wybierz opcję **Dodaj wiersz**, a następnie w polu **Obszar usterki** wybierz obszar usterki.</span><span class="sxs-lookup"><span data-stu-id="ed35b-154">On the **Fault area** FastTab, select **Add line**, and then, in the **Fault area** field select a fault area.</span></span>
5. <span data-ttu-id="ed35b-155">Na skróconej karcie **Typ usterki** wybierz opcję **Dodaj wiersz**, a następnie w polu **Typ usterki** wybierz typ usterki.</span><span class="sxs-lookup"><span data-stu-id="ed35b-155">On the **Fault type** FastTab, select **Add line**, and then, in the **Fault type** field, select a fault type.</span></span>
6. <span data-ttu-id="ed35b-156">Aby szybko utworzyć kombinacje wszystkich objawów usterek, obszarów i typów dla wybranego typu składnika, wybierz opcję **Utwórz kombinacje usterek**.</span><span class="sxs-lookup"><span data-stu-id="ed35b-156">To quickly create combinations of all existing fault symptoms, areas, and types for the selected asset type, select **Create fault combinations**.</span></span> <span data-ttu-id="ed35b-157">Ta funkcja jest przydatna w przypadku dodawania wielu objawów usterek, obszarów i typów.</span><span class="sxs-lookup"><span data-stu-id="ed35b-157">This function is useful if you've added many fault symptoms, areas, and types.</span></span> <span data-ttu-id="ed35b-158">Można łatwiej usunąć wiersze dla dowolnej kombinacji, która nie jest odpowiednia dla typu składnika majątku niż w celu ręcznego utworzenia nowych wierszy.</span><span class="sxs-lookup"><span data-stu-id="ed35b-158">It's easier to delete the lines for any combinations that aren't relevant to the asset type than to create new lines manually.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ed35b-159">Aby skopiować ustawienia objawów usterek, obszarów i typów z jednego typu składnika majątku do wybranego typu składnika, należy wybrać opcję **Kopiuj z typu składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="ed35b-159">To copy the setup of fault symptoms, areas, and types from one asset type to the selected asset type, select **Copy from asset type**.</span></span>

7. <span data-ttu-id="ed35b-160">Wybierz **Zapisz**, żeby zapisać zmiany.</span><span class="sxs-lookup"><span data-stu-id="ed35b-160">Select **Save** to save your changes.</span></span>

![Strona Projektant usterek](media/21-setup-for-work-orders.png)

## <a name="create-fault-causes"></a><span data-ttu-id="ed35b-162">Utwórz przyczyny usterek</span><span class="sxs-lookup"><span data-stu-id="ed35b-162">Create fault causes</span></span>

<span data-ttu-id="ed35b-163">Wykonaj poniższe kroki, aby utworzyć listę znanych przyczyn usterek, które można dodać do zlecenia pracy lub do zgłoszenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="ed35b-163">Follow these steps to create a list of known fault causes that can be added to a work order or a maintenance request.</span></span>

1. <span data-ttu-id="ed35b-164">Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Usterka** \> **Przyczyny usterek**.</span><span class="sxs-lookup"><span data-stu-id="ed35b-164">Select **Asset management** \> **Setup** \> **Fault** \> **Fault causes**.</span></span>
2. <span data-ttu-id="ed35b-165">Wybierz **Nowy**, aby utworzyć rekord.</span><span class="sxs-lookup"><span data-stu-id="ed35b-165">Select **New** to create a record.</span></span>
3. <span data-ttu-id="ed35b-166">W polu **Przyczyny usterek** wprowadź nazwę przyczyny usterki.</span><span class="sxs-lookup"><span data-stu-id="ed35b-166">In the **Fault cause** field, enter a name for the fault cause.</span></span>
4. <span data-ttu-id="ed35b-167">W polu **Opis wprowadź** opis.</span><span class="sxs-lookup"><span data-stu-id="ed35b-167">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="ed35b-168">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="ed35b-168">Select **Save**.</span></span>

## <a name="create-fault-remedies"></a><span data-ttu-id="ed35b-169">Stwórz środki zaradcze dla usterki</span><span class="sxs-lookup"><span data-stu-id="ed35b-169">Create fault remedies</span></span>

<span data-ttu-id="ed35b-170">Wykonaj poniższe kroki, aby utworzyć listę znanych środków zaradczych dla usterek, które można dodać do zlecenia pracy lub do zgłoszenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="ed35b-170">Follow these steps to create a list of suggestions for remedy and repair that can be added to a work order or a maintenance request.</span></span>

1. <span data-ttu-id="ed35b-171">Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Usterka** \> **Środki zaradcze dla usterek**.</span><span class="sxs-lookup"><span data-stu-id="ed35b-171">Select **Asset management** \> **Setup** \> **Fault** \> **Fault remedies**.</span></span>
2. <span data-ttu-id="ed35b-172">Wybierz **Nowy**, aby utworzyć rekord.</span><span class="sxs-lookup"><span data-stu-id="ed35b-172">Select **New** to create a record.</span></span>
3. <span data-ttu-id="ed35b-173">W polu **Środki zaradcze dla usterek** wprowadź nazwę środka zaradczego usterki.</span><span class="sxs-lookup"><span data-stu-id="ed35b-173">In the **Fault remedy** field, enter a name for the fault remedy.</span></span>
4. <span data-ttu-id="ed35b-174">W polu **Opis wprowadź** opis.</span><span class="sxs-lookup"><span data-stu-id="ed35b-174">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="ed35b-175">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="ed35b-175">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="ed35b-176">Istnieje możliwość zmiany nazw objawów usterek, obszarów, typów, przyczyn i środków zaradczych stosownie do potrzeb.</span><span class="sxs-lookup"><span data-stu-id="ed35b-176">You can change the names of your fault symptoms, areas, types, causes, and remedies as you require.</span></span> <span data-ttu-id="ed35b-177">Zmiany nazwy są automatycznie odzwierciedlane w powiązanych z nią rejestracjach błędów.</span><span class="sxs-lookup"><span data-stu-id="ed35b-177">The name changes are automatically reflected in the related fault registrations.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]