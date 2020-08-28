---
title: Wyświetlanie zmian adresu i zarządzanie nimi
description: W tym temacie wyjaśniono, w jaki sposób można przeglądać i zarządzać zmianami adresu w Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 08/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-08-07
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: a69d723b45e834b022491c8eaf2a7fb580e54f1d
ms.sourcegitcommit: 288df4fe766536e51ca9b5306c5bb948b7772ac5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2020
ms.locfileid: "3688328"
---
# <a name="view-and-manage-address-changes"></a><span data-ttu-id="626d2-103">Wyświetlanie zmian adresu i zarządzanie nimi</span><span class="sxs-lookup"><span data-stu-id="626d2-103">View and manage address changes</span></span>

<span data-ttu-id="626d2-104">W tym temacie wyjaśniono, w jaki sposób można wyświetlać zmiany adresu i zarządzać nimi na stronie **Edytuj dane osobowe pracownika sklepu internetowego** lub strony szczegółów **pracownika** w programie Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="626d2-104">This topic explains how you can view and manage address changes in the Employee self-service **Edit personal details** page or the **Worker** details page in Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="626d2-105">Wiele organizacji chce, aby pracownicy mogli zarządzać własnymi szczegółami, korzystając z funkcji samoobsługi.</span><span class="sxs-lookup"><span data-stu-id="626d2-105">Many organizations want employees to manage their own personal details through a self-service experience.</span></span> <span data-ttu-id="626d2-106">Można zezwolić użytkownikom na aktualizowanie ich adresów w obszarze roboczym **samoobsługi pracownika etatowego**.</span><span class="sxs-lookup"><span data-stu-id="626d2-106">You can allow users to update their address in the **Employee self service** workspace.</span></span> <span data-ttu-id="626d2-107">Następnie można monitorować te zmiany w obszarze roboczym **zarządzanie kadrami**.</span><span class="sxs-lookup"><span data-stu-id="626d2-107">You can then monitor these changes in the **Personnel management** workspace.</span></span> <span data-ttu-id="626d2-108">Aby użyć tej funkcji, należy określić liczbę dni, które mają zostać wyświetlone, aby wyświetlić zmiany na stronie **Parametry modułu Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="626d2-108">To use this feature, you must specify the number of days that you want to view changes in the **Human resources parameters** page.</span></span>

## <a name="configure-address-change-parameters"></a><span data-ttu-id="626d2-109">Konfigurowanie parametrów zmiany adresu</span><span class="sxs-lookup"><span data-stu-id="626d2-109">Configure address change parameters</span></span>

<span data-ttu-id="626d2-110">Aby skonfigurować liczbę dni, o jaką zmiany adresu mają się pojawiać w obszarze roboczym **zarządzanie personelem**, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="626d2-110">To configure the number of days that you want address changes to appear in the **Personnel management** workspace, follow these steps:</span></span>

1. <span data-ttu-id="626d2-111">W okienku nawigacji wybierz opcję **Zarządzanie personelem**.</span><span class="sxs-lookup"><span data-stu-id="626d2-111">On the navigation pane, select **Personnel management**.</span></span>

2. <span data-ttu-id="626d2-112">Wybierz **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="626d2-112">Select **Links**.</span></span>

3. <span data-ttu-id="626d2-113">Wybierz **Parametry modułu Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="626d2-113">Select **Human resources parameters**.</span></span>

4. <span data-ttu-id="626d2-114">W polu **Liczba dni** w obszarze **Zmiana adresu** wprowadź liczbę dni, w ciągu których zmiany adresu mają się pojawiać w obszarze roboczym **Zarządzanie kadrami**.</span><span class="sxs-lookup"><span data-stu-id="626d2-114">In the **Number of days** field under **Address change**, enter the number of days that you want address changes to appear in the **Personnel management** workspace.</span></span>

5. <span data-ttu-id="626d2-115">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="626d2-115">Close the page.</span></span>

## <a name="create-or-change-an-employee-address"></a><span data-ttu-id="626d2-116">Utwórz lub zmień adres pracownika etatowego</span><span class="sxs-lookup"><span data-stu-id="626d2-116">Create or change an employee address</span></span>

<span data-ttu-id="626d2-117">Pracownicy mogą aktualizować własne adresy w obszarze roboczym **samoobsługi pracownika etatowego**.</span><span class="sxs-lookup"><span data-stu-id="626d2-117">Employees can update their own address in the **Employee self service** workspace.</span></span> <span data-ttu-id="626d2-118">Wykonaj następujące kroki, aby utworzyć lub zmienić adres:</span><span class="sxs-lookup"><span data-stu-id="626d2-118">Follow these steps to create or change an address:</span></span>

1. <span data-ttu-id="626d2-119">Wybierz kafelek **Samoobsługa pracownika etatowego** na swojej stronie głównej.</span><span class="sxs-lookup"><span data-stu-id="626d2-119">Select the **Employee self-service** tile on your home page.</span></span>

2. <span data-ttu-id="626d2-120">Wybierz opcję **Edytuj dane osobowe**.</span><span class="sxs-lookup"><span data-stu-id="626d2-120">Select **Edit personal details**.</span></span>

3. <span data-ttu-id="626d2-121">Wybierz pozycję **Dodaj**, aby dodać adres.</span><span class="sxs-lookup"><span data-stu-id="626d2-121">To add an address, select **Add**.</span></span> <span data-ttu-id="626d2-122">Aby aktualizować istniejący adres, wybierz adres z listy i wybierz opcję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="626d2-122">To update an existing address, select the address from the list and then select **Edit**.</span></span>

4. <span data-ttu-id="626d2-123">Wprowadź **Nazwę lub opis**.</span><span class="sxs-lookup"><span data-stu-id="626d2-123">Enter the **Name or description**.</span></span>

5. <span data-ttu-id="626d2-124">Zaznacz pole rozwijane **Cel**, a następnie wybierz typ adresu.</span><span class="sxs-lookup"><span data-stu-id="626d2-124">Select the **Purpose** drop-down box and then select the type of address.</span></span>

6. <span data-ttu-id="626d2-125">Wprowadź **Kraj/region**.</span><span class="sxs-lookup"><span data-stu-id="626d2-125">Enter the **Country/region**.</span></span>

7. <span data-ttu-id="626d2-126">Wprowadź **ZIP/Kod pocztowy**.</span><span class="sxs-lookup"><span data-stu-id="626d2-126">Enter the **ZIP/postal code**.</span></span>

8. <span data-ttu-id="626d2-127">Wprowadź **Ulica**.</span><span class="sxs-lookup"><span data-stu-id="626d2-127">Enter the **Street**.</span></span>

9. <span data-ttu-id="626d2-128">Wprowadź **Miasto**, **Stan** i **Kraj**.</span><span class="sxs-lookup"><span data-stu-id="626d2-128">Enter the **City**, **State**, and **County**.</span></span> <span data-ttu-id="626d2-129">Zazwyczaj pola te są automatycznie ustawiane na podstawie pola **ZIP/kod pocztowy**.</span><span class="sxs-lookup"><span data-stu-id="626d2-129">Typically, these fields are automatically set based on the **ZIP/postal code** field.</span></span>

10. <span data-ttu-id="626d2-130">Opcjonalnie wybierz pole **Podstawowe**, które ma wskazywać adres podstawowy.</span><span class="sxs-lookup"><span data-stu-id="626d2-130">Optionally, select the **Primary** field to indicate a primary address.</span></span> <span data-ttu-id="626d2-131">Jako główny może być zaznaczony tylko jeden adres.</span><span class="sxs-lookup"><span data-stu-id="626d2-131">Only one address can be marked as the primary.</span></span> <span data-ttu-id="626d2-132">Jeśli inny adres jest już oznaczony jako adres podstawowy, musisz potwierdzić, że chcesz używać tego adresu jako adresu podstawowego.</span><span class="sxs-lookup"><span data-stu-id="626d2-132">If another address is already marked as the primary address, you'll need to confirm that you want to use this address as the primary.</span></span>

11. <span data-ttu-id="626d2-133">Opcjonalnie wybierz pole **Prywatne**, które ma wskazywać adres prywatny.</span><span class="sxs-lookup"><span data-stu-id="626d2-133">Optionally, select the **Private** field to indicate that the address is private.</span></span> <span data-ttu-id="626d2-134">Tylko użytkownicy z wyraźnymi uprawnieniami do przeglądania prywatnych informacji adresowych mogą wyświetlać ten adres.</span><span class="sxs-lookup"><span data-stu-id="626d2-134">Only users with explicit permission to view private address information can view this address.</span></span>

12. <span data-ttu-id="626d2-135">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="626d2-135">Select **OK**.</span></span>

## <a name="create-or-change-a-worker-address"></a><span data-ttu-id="626d2-136">Utwórz lub zmień adres pracownika</span><span class="sxs-lookup"><span data-stu-id="626d2-136">Create or change a worker address</span></span>

<span data-ttu-id="626d2-137">Adres można zaktualizować w obszarze roboczym **Zarządzanie personelem**.</span><span class="sxs-lookup"><span data-stu-id="626d2-137">You can update an address in the **Personnel management** workspace.</span></span> <span data-ttu-id="626d2-138">Wykonaj następujące kroki, aby utworzyć lub zmienić adres:</span><span class="sxs-lookup"><span data-stu-id="626d2-138">Follow these steps to create or change an address:</span></span>

1. <span data-ttu-id="626d2-139">W obszarze roboczym **Zarządzanie personelem** wybierz opcję **Łącza**, a następnie wybierz **Pracownicy**.</span><span class="sxs-lookup"><span data-stu-id="626d2-139">In the **Personnel management** workspace, select **Links**, and then select **Workers**.</span></span>

3. <span data-ttu-id="626d2-140">Wybierz pracownika, a następnie wybierz **Adresy**.</span><span class="sxs-lookup"><span data-stu-id="626d2-140">Select the worker, and then select **Addresses**.</span></span>

3. <span data-ttu-id="626d2-141">Wybierz pozycję **Dodaj**, aby dodać adres.</span><span class="sxs-lookup"><span data-stu-id="626d2-141">To add an address, select **Add**.</span></span> <span data-ttu-id="626d2-142">Aby aktualizować istniejący adres, wybierz adres z listy i wybierz opcję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="626d2-142">To update an existing address, select the address from the list and then select **Edit**.</span></span>

4. <span data-ttu-id="626d2-143">Wprowadź **Nazwę lub opis**.</span><span class="sxs-lookup"><span data-stu-id="626d2-143">Enter the **Name or description**.</span></span>

5. <span data-ttu-id="626d2-144">Zaznacz pole rozwijane **Cel**, a następnie wybierz typ adresu.</span><span class="sxs-lookup"><span data-stu-id="626d2-144">Select the **Purpose** drop-down box and then select the type of address.</span></span>

6. <span data-ttu-id="626d2-145">Wprowadź **Kraj/region**.</span><span class="sxs-lookup"><span data-stu-id="626d2-145">Enter the **Country/region**.</span></span>

7. <span data-ttu-id="626d2-146">Wprowadź **ZIP/Kod pocztowy**.</span><span class="sxs-lookup"><span data-stu-id="626d2-146">Enter the **ZIP/postal code**.</span></span>

8. <span data-ttu-id="626d2-147">Wprowadź **Ulica**.</span><span class="sxs-lookup"><span data-stu-id="626d2-147">Enter the **Street**.</span></span>

9. <span data-ttu-id="626d2-148">Wprowadź **Miasto**, **Stan** i **Kraj**.</span><span class="sxs-lookup"><span data-stu-id="626d2-148">Enter the **City**, **State**, and **County**.</span></span> <span data-ttu-id="626d2-149">Zazwyczaj pola te są automatycznie ustawiane na podstawie pola **ZIP/kod pocztowy**.</span><span class="sxs-lookup"><span data-stu-id="626d2-149">Typically, these fields are automatically set based on the **ZIP/postal code** field.</span></span>

10. <span data-ttu-id="626d2-150">Opcjonalnie wybierz pole **Podstawowe**, które ma wskazywać adres podstawowy.</span><span class="sxs-lookup"><span data-stu-id="626d2-150">Optionally, select the **Primary** field to indicate a primary address.</span></span> <span data-ttu-id="626d2-151">Jako główny może być zaznaczony tylko jeden adres.</span><span class="sxs-lookup"><span data-stu-id="626d2-151">Only one address can be marked as the primary.</span></span> <span data-ttu-id="626d2-152">Jeśli inny adres jest już oznaczony jako adres podstawowy, musisz potwierdzić, że chcesz używać tego adresu jako adresu podstawowego.</span><span class="sxs-lookup"><span data-stu-id="626d2-152">If another address is already marked as the primary address, you'll need to confirm that you want to use this address as the primary.</span></span>

11. <span data-ttu-id="626d2-153">Opcjonalnie wybierz pole **Prywatne**, które ma wskazywać adres prywatny.</span><span class="sxs-lookup"><span data-stu-id="626d2-153">Optionally, select the **Private** field to indicate that the address is private.</span></span> <span data-ttu-id="626d2-154">Tylko użytkownicy z wyraźnymi uprawnieniami do przeglądania prywatnych informacji adresowych mogą wyświetlać ten adres.</span><span class="sxs-lookup"><span data-stu-id="626d2-154">Only users with explicit permission to view private address information can view this address.</span></span>

12. <span data-ttu-id="626d2-155">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="626d2-155">Select **OK**.</span></span>
 
## <a name="create-a-future-change-for-an-address"></a><span data-ttu-id="626d2-156">Tworzenie przyszłej zmiany adresu</span><span class="sxs-lookup"><span data-stu-id="626d2-156">Create a future change for an address</span></span>

<span data-ttu-id="626d2-157">W niektórych przypadkach może być konieczne zaktualizowanie adresu w celu zmiany w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="626d2-157">In some cases, you might want to update an address to change in the future.</span></span> <span data-ttu-id="626d2-158">Na przykład byłoby to przydatne, jeśli pracownik wyprowadza się 15 dnia następnego miesiąca.</span><span class="sxs-lookup"><span data-stu-id="626d2-158">For example, this would be useful if an employee is moving on the 15th of the following month.</span></span>

1. <span data-ttu-id="626d2-159">Otwórz stronę **Zarządzanie adresami**, wybierając **Więcej opcji > Zaawansowane** z dowolnej siatki adresów.</span><span class="sxs-lookup"><span data-stu-id="626d2-159">Open the **Manage addresses** page by selecting **More options > Advanced** from any address grid.</span></span>

2. <span data-ttu-id="626d2-160">Wybierz pozycję **Nowy**, aby utworzyć nowy adres.</span><span class="sxs-lookup"><span data-stu-id="626d2-160">Select **New** to create a new address.</span></span>

3. <span data-ttu-id="626d2-161">Umożliwia wprowadzenie szczegółów adresu.</span><span class="sxs-lookup"><span data-stu-id="626d2-161">Enter the details of the address.</span></span>

4. <span data-ttu-id="626d2-162">Wybierz skróconą kartę **Ogólne**.</span><span class="sxs-lookup"><span data-stu-id="626d2-162">Select the **General** FastTab.</span></span>

5. <span data-ttu-id="626d2-163">W polu **Data wejścia w życie** wybierz datę, od której będzie obowiązywać nowy adres.</span><span class="sxs-lookup"><span data-stu-id="626d2-163">In the **Effective date** field, select the date the new address will be effective.</span></span>

6. <span data-ttu-id="626d2-164">Opcjonalnie wybierz pole **Data wygaśnięcia** i określ, kiedy adres nie będzie już obowiązywać.</span><span class="sxs-lookup"><span data-stu-id="626d2-164">In the **Expiration date** field, optionally select when the address will no longer be effective.</span></span>

7. <span data-ttu-id="626d2-165">Zamknij strony.</span><span class="sxs-lookup"><span data-stu-id="626d2-165">Close the pages.</span></span>

## <a name="view-and-monitor-address-changes"></a><span data-ttu-id="626d2-166">Wyświetlanie i monitorowanie zmian adresu</span><span class="sxs-lookup"><span data-stu-id="626d2-166">View and monitor address changes</span></span>

<span data-ttu-id="626d2-167">Pracownicy działu kadr mogą wyświetlać i monitorować zmiany adresów z obszaru roboczego **Zarządzanie personelem**.</span><span class="sxs-lookup"><span data-stu-id="626d2-167">HR personnel can view and monitor address changes from the **Personnel management** workspace.</span></span> <span data-ttu-id="626d2-168">Aby wyświetlić zmiany adresu, otwórz kafelek **Zarządzanie personelem** ze strony **Głównej**.</span><span class="sxs-lookup"><span data-stu-id="626d2-168">To view the address changes, open the **Personnel management** tile from the **Home** page.</span></span> <span data-ttu-id="626d2-169">Adres zmienia się na kafelku w prawym górnym rogu.</span><span class="sxs-lookup"><span data-stu-id="626d2-169">The address changes display on a tile in the upper-right corner.</span></span> <span data-ttu-id="626d2-170">Liczba powyżej **Zmiany adresu** pokazuje, ile zmian adresu wystąpiło w ciągu liczby dni określonej na stronie **Parametry Human resources**.</span><span class="sxs-lookup"><span data-stu-id="626d2-170">The number above **Address changes** shows how many address changes occurred in the number of days specified in the **Human resources parameters** page.</span></span> 

<span data-ttu-id="626d2-171">Po wybraniu kafelka **Zmiany adresu** na nowej stronie są wyświetlane szczegółowe informacje o wszelkich zmianach adresu.</span><span class="sxs-lookup"><span data-stu-id="626d2-171">When you select the **Address changes** tile, a new page displays the details of any address changes.</span></span> <span data-ttu-id="626d2-172">Opcjonalnie można wybrać opcję **Dołącz przyszłe zmiany adresu** w prawym górnym rogu, aby wyświetlić zmiany w adresie z przyszłą datą.</span><span class="sxs-lookup"><span data-stu-id="626d2-172">You can optionally select **Include future address changes** in the upper-right corner to display address changes with a future date.</span></span>

> [!NOTE]
> <span data-ttu-id="626d2-173">Jeśli chcesz otrzymywać alert lub pocztę e-mail o tych zmianach adresu, możesz utworzyć nową regułę alertu na karcie **Opcje** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="626d2-173">If you want to receive an alert or email about these address changes, you can create a new alert rule on the **Options** tab in the Action Pane.</span></span> <span data-ttu-id="626d2-174">Aby uzyskać więcej informacji dotyczących sposobu tworzenia reguł, zobacz [Tworzenie reguł alertów](/fin-ops-core/fin-ops/get-started/create-alert-rules.md).</span><span class="sxs-lookup"><span data-stu-id="626d2-174">For more information about alert rules, see [Create alert rules](/fin-ops-core/fin-ops/get-started/create-alert-rules.md).</span></span><br><br>

> <span data-ttu-id="626d2-175">Jeśli chcesz skonfigurować przepływ pracy dla zmiany adresu, możesz wybrać opcję **Wyślij zewnętrznie** w regule alertu, a następnie użyć Power Automate do wyzwolenia zdarzenia biznesowego i skonfigurowania przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="626d2-175">If you want to configure a workflow for the address changes, you can select the **Send externally** option on your alert rule, and then use Power Automate to trigger the business event and configure a workflow.</span></span> <span data-ttu-id="626d2-176">Aby uzyskać więcej informacji, zajrzyj do [Alerty jako zdarzenia biznesowe](/fin-ops-core/dev-itpro/business-events/alerts-business-events.md).</span><span class="sxs-lookup"><span data-stu-id="626d2-176">For more information, see [Alerts as business events](/fin-ops-core/dev-itpro/business-events/alerts-business-events.md).</span></span>
