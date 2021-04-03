---
title: Rozliczanie konserwacji składników majątku należących do klienta
description: W tym temacie wyjaśniono, jak tworzyć, przetwarzać i rozliczać prace konserwacyjne wykonane dla składników majątku należących do klienta.
author: johanhoffmann
manager: tfehr
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectContractsListPage, ProjInvoiceTable, ProjProjectsListPage, ProjTable, EntAssetWorkOrderType, EntAssetWorkOrderProjectSetup, EntAssetObjectTable, EntAssetWorkOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: a93436d101e6201c9d86279ea5b1a37fcc644fd1
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500461"
---
# <a name="bill-for-maintenance-on-customer-owned-assets"></a><span data-ttu-id="58221-103">Rozliczanie konserwacji składników majątku należących do klienta</span><span class="sxs-lookup"><span data-stu-id="58221-103">Bill for maintenance on customer-owned assets</span></span>

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../../includes/preview-banner.md)]

<span data-ttu-id="58221-104">Funkcja *rozliczania zleceń pracy* umożliwia tworzenie, przetwarzanie i rozliczanie prac konserwacyjnych dotyczących składników majątku należących do klientów.</span><span class="sxs-lookup"><span data-stu-id="58221-104">The *Work order billing* feature lets you create, process, and bill maintenance work that is done on assets that your customers own.</span></span> <span data-ttu-id="58221-105">Ta funkcja pozwala wykonać następujące zadania:</span><span class="sxs-lookup"><span data-stu-id="58221-105">This feature lets you perform the following tasks:</span></span>

- <span data-ttu-id="58221-106">Połącz odbiorców z posiadanymi przez nich składnikami majątku.</span><span class="sxs-lookup"><span data-stu-id="58221-106">Connect customers to the assets that they own.</span></span>
- <span data-ttu-id="58221-107">Wybierz klienta i wyświetl składniki majątku, których właścicielem jest klient, podczas tworzenia zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="58221-107">Select a customer and view the assets that customer owns when you create a work order.</span></span>
- <span data-ttu-id="58221-108">Skonfiguruj projekt nadrzędny dla każdego klienta.</span><span class="sxs-lookup"><span data-stu-id="58221-108">Set up a parent project for each customer.</span></span>
- <span data-ttu-id="58221-109">Zarejestruj godziny, pozycje, wydatki i opłaty względem zlecenia pracy, a następnie utwórz propozycję faktury dla odbiorcy później.</span><span class="sxs-lookup"><span data-stu-id="58221-109">Register hours, items, expenses, and fees against the work order, and then create an invoice proposal for the customer later.</span></span>

<span data-ttu-id="58221-110">Ponadto ta funkcja udostępnia następujące funkcje:</span><span class="sxs-lookup"><span data-stu-id="58221-110">In addition, the feature provides the following functionality:</span></span>

- <span data-ttu-id="58221-111">Umowa projektu z nadrzędnego projektu odbiorcy jest automatycznie kopiowana do odpowiedniego projektu zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="58221-111">The project contract from a customer's parent project is automatically copied to the relevant work order project.</span></span>
- <span data-ttu-id="58221-112">Zarządzanie składnikami majątku może teraz używać typu transakcji projektu *opłaty* zarówno w prognozach, jak i w arkuszach zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="58221-112">Asset management can now use the *fee* project transaction type on both work order forecasts and work order journals.</span></span>

## <a name="turn-on-the-customer-billing-feature"></a><span data-ttu-id="58221-113">Włącz funkcję rozliczania klientów</span><span class="sxs-lookup"><span data-stu-id="58221-113">Turn on the customer billing feature</span></span>

<span data-ttu-id="58221-114">Aby móc używać tej funkcji, należy ją włączyć w systemie.</span><span class="sxs-lookup"><span data-stu-id="58221-114">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="58221-115">Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją.</span><span class="sxs-lookup"><span data-stu-id="58221-115">Admins can use the [feature management](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="58221-116">W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:</span><span class="sxs-lookup"><span data-stu-id="58221-116">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="58221-117">**Moduł:** *Zarządzanie projektami i ich księgowanie*</span><span class="sxs-lookup"><span data-stu-id="58221-117">**Module:** *Project management and accounting*</span></span>
- <span data-ttu-id="58221-118">**Nazwa funkcji:** *Rozliczanie zlecenia pracy*</span><span class="sxs-lookup"><span data-stu-id="58221-118">**Feature name:** *Work order billing*</span></span>

## <a name="example-scenario"></a><span data-ttu-id="58221-119">Przykładowy scenariusz</span><span class="sxs-lookup"><span data-stu-id="58221-119">Example scenario</span></span>

<span data-ttu-id="58221-120">Aby się dowiedzieć, jak działa ta funkcja, należy przejść do poniższego przykładowego scenariusza.</span><span class="sxs-lookup"><span data-stu-id="58221-120">To learn how this feature works, work through the following example scenario.</span></span>

<span data-ttu-id="58221-121">Aby pracować z tym scenariuszem przy użyciu określonych przykładowych rekordów i wartości tutaj określonych, należy użyć systemu, w którym są zainstalowane standardowe [dane demonstracyjne](../../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md).</span><span class="sxs-lookup"><span data-stu-id="58221-121">To work through this scenario by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="58221-122">Należy wybrać firmę **USMF** przed rozpoczęciem.</span><span class="sxs-lookup"><span data-stu-id="58221-122">You must select the **USMF** legal entity before you begin.</span></span>

<span data-ttu-id="58221-123">Tego scenariusza można również używać jako wskazówek dotyczących danej funkcji podczas pracy w produkcji.</span><span class="sxs-lookup"><span data-stu-id="58221-123">You can also use this scenario as guidance for using the feature when you work on a production system.</span></span> <span data-ttu-id="58221-124">Jednak w takim przypadku trzeba podstawiać własne wartości i w niektórych przypadkach może brakować pewnych typów wymaganych rekordów, które są dostępne w standardowych danych demonstracyjnych.</span><span class="sxs-lookup"><span data-stu-id="58221-124">However, in that case, you must substitute your own values, and you might be missing some types of required records that the standard demo data provides.</span></span>

### <a name="step-1-create-a-new-project-contract-for-the-customer"></a><span data-ttu-id="58221-125">Krok 1: Tworzenie nowej umowy dotyczącej projektu dla klienta</span><span class="sxs-lookup"><span data-stu-id="58221-125">Step 1: Create a new project contract for the customer</span></span>

1. <span data-ttu-id="58221-126">Wybierz kolejno opcje **Zarządzanie projektami i ich księgowanie \> Projekty \> Umowy dotyczące projektu**.</span><span class="sxs-lookup"><span data-stu-id="58221-126">Go to **Project management and accounting \> Projects \> Project contracts**.</span></span>
1. <span data-ttu-id="58221-127">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="58221-127">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="58221-128">W wyświetlonym oknie dialogowym **Nowa umowa dotycząca projektu** można ustawić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="58221-128">In the **New project contract** dialog box, set the following values:</span></span>

    - <span data-ttu-id="58221-129">**Nazwa:** *Pelican Wholesales*</span><span class="sxs-lookup"><span data-stu-id="58221-129">**Name:** *Pelican Wholesales*</span></span>
    - <span data-ttu-id="58221-130">**Typ finansowania:** *Klient*</span><span class="sxs-lookup"><span data-stu-id="58221-130">**Funding type:** *Customer*</span></span>
    - <span data-ttu-id="58221-131">**Źródło finansowania:** *US-013* (*Pelican Wholesales*)</span><span class="sxs-lookup"><span data-stu-id="58221-131">**Funding source:** *US-013* (*Pelican Wholesales*)</span></span>

1. <span data-ttu-id="58221-132">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="58221-132">Select **OK**.</span></span>

### <a name="step-2-create-a-new-parent-project-for-the-customer"></a><span data-ttu-id="58221-133">Krok 2: Tworzenie nowego projektu nadrzędnego dla klienta</span><span class="sxs-lookup"><span data-stu-id="58221-133">Step 2: Create a new parent project for the customer</span></span>

<span data-ttu-id="58221-134">Utworzony tutaj projekt nadrzędny będzie używany podczas tworzenia zleceń pracy dla odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="58221-134">The parent project that you create here will be used when work orders for the customer are created.</span></span>

1. <span data-ttu-id="58221-135">Wybierz kolejno opcje **Zarządzanie projektami i ich księgowanie \> Projekty \> Wszystkie projekty**.</span><span class="sxs-lookup"><span data-stu-id="58221-135">Go to **Project management and accounting \> Projects \> All projects**.</span></span>
1. <span data-ttu-id="58221-136">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="58221-136">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="58221-137">W wyświetlonym oknie dialogowym **Nowy projekt** można ustawić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="58221-137">In the **New project** dialog box, set the following values:</span></span>

    - <span data-ttu-id="58221-138">**Typ projektu:** *Czas i materiały*</span><span class="sxs-lookup"><span data-stu-id="58221-138">**Project type:** *Time and material*</span></span>
    - <span data-ttu-id="58221-139">**Nazwa projektu:** *Zlecenia pracy Pelican Wholesales*</span><span class="sxs-lookup"><span data-stu-id="58221-139">**Project name:** *Pelican Wholesales work orders*</span></span>
    - <span data-ttu-id="58221-140">**Grupa projektów:** *TM*</span><span class="sxs-lookup"><span data-stu-id="58221-140">**Project group:** *TM*</span></span>
    - <span data-ttu-id="58221-141">**Identyfikator umowy projektu:** *Pelican Wholesales* (wcześniej utworzona umowa)</span><span class="sxs-lookup"><span data-stu-id="58221-141">**Project contract ID:** *Pelican Wholesales* (the contract that you created earlier)</span></span>
    - <span data-ttu-id="58221-142">**Data początkowa**: wybierz dzisiejszą datę.</span><span class="sxs-lookup"><span data-stu-id="58221-142">**Start date:** Select today's date.</span></span>

1. <span data-ttu-id="58221-143">Wybierz opcję **Utwórz projekt**.</span><span class="sxs-lookup"><span data-stu-id="58221-143">Select **Create project**.</span></span>
1. <span data-ttu-id="58221-144">Nowy projekt jest otwarty.</span><span class="sxs-lookup"><span data-stu-id="58221-144">The new project is opened.</span></span> <span data-ttu-id="58221-145">Zanotuj wartość **identyfikatora projektu**.</span><span class="sxs-lookup"><span data-stu-id="58221-145">Make a note of the **Project ID** value.</span></span> <span data-ttu-id="58221-146">Trzeba będzie go wprowadzić później.</span><span class="sxs-lookup"><span data-stu-id="58221-146">You will have to enter it later.</span></span>

### <a name="step-3-create-a-new-work-order-type-in-asset-management"></a><span data-ttu-id="58221-147">Krok 3: Tworzenie nowego typu zlecenia pracy w zarządzaniu składnikami majątku</span><span class="sxs-lookup"><span data-stu-id="58221-147">Step 3: Create a new work order type in Asset management</span></span>

1. <span data-ttu-id="58221-148">Przejdź do pozycji **Zarządzanie składnikami majątku \> Konfiguracja \> Zlecenie pracy \> Typy zleceń pracy**.</span><span class="sxs-lookup"><span data-stu-id="58221-148">Go to **Asset management \> Setup \> Work order \> Work order types**.</span></span>
1. <span data-ttu-id="58221-149">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="58221-149">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="58221-150">Nowy rekord zostanie dodany do listy.</span><span class="sxs-lookup"><span data-stu-id="58221-150">A new record is added to the list.</span></span> <span data-ttu-id="58221-151">Należy dla niego określić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="58221-151">Set the following values for it:</span></span>

    - <span data-ttu-id="58221-152">**Typ zlecenia pracy:** *Usługa*</span><span class="sxs-lookup"><span data-stu-id="58221-152">**Work order type:** *Service*</span></span>
    - <span data-ttu-id="58221-153">**Nazwa:** *Zlecenia pracy usług*</span><span class="sxs-lookup"><span data-stu-id="58221-153">**Name:** *Service work orders*</span></span>
    - <span data-ttu-id="58221-154">**Stan cyklu życia zlecenia pracy:** *Standardowy*</span><span class="sxs-lookup"><span data-stu-id="58221-154">**Work order lifecycle state:** *Standard*</span></span>

### <a name="step-4-link-the-customer-account-to-the-parent-project"></a><span data-ttu-id="58221-155">Krok 4: Łączenie konta klientem z projektem nadrzędnym</span><span class="sxs-lookup"><span data-stu-id="58221-155">Step 4: Link the customer account to the parent project</span></span>

<span data-ttu-id="58221-156">Teraz musisz połączyć konto klienta z projektem nadrzędnym w ustawieniach projektu w zarządzaniu składnikami aktywów.</span><span class="sxs-lookup"><span data-stu-id="58221-156">You must now link the customer account to the parent project in the project setup in Asset management.</span></span>

1. <span data-ttu-id="58221-157">Przejdź do **Zarządzanie składnikami majątku \> Konfiguracja \> Zlecenia pracy \> Ustawienia projektu**.</span><span class="sxs-lookup"><span data-stu-id="58221-157">Go to **Asset management \> Setup \> Work orders \> Project setup**.</span></span>
1. <span data-ttu-id="58221-158">Na karcie **Projekt nadrzędny** wybierz opcję **Dodaj**, aby dodać wiersz.</span><span class="sxs-lookup"><span data-stu-id="58221-158">On the **Parent project** tab, select **Add** to add a line.</span></span>
1. <span data-ttu-id="58221-159">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="58221-159">On the new line, set the following values:</span></span>

    - <span data-ttu-id="58221-160">**Konto klienta:** *US-013* (*Pelican Wholesales*)</span><span class="sxs-lookup"><span data-stu-id="58221-160">**Customer account:** *US-013* (*Pelican Wholesales*)</span></span>
    - <span data-ttu-id="58221-161">**Identyfikator projektu**: wprowadź identyfikator projektu zanotowany wcześniej.</span><span class="sxs-lookup"><span data-stu-id="58221-161">**Project ID:** Enter the project ID that you made a note of earlier.</span></span>

### <a name="step-5-link-the-project-group-and-type-to-the-work-order-project"></a><span data-ttu-id="58221-162">Krok 5: Łączenie grupy projektów i ustawianie typu projektu zlecenia pracy</span><span class="sxs-lookup"><span data-stu-id="58221-162">Step 5: Link the project group and type to the work order project</span></span>

<span data-ttu-id="58221-163">Użytkownik nadal powinien być na stronie **Ustawienia projektu** (**Zarządzanie składnikami majątku \> Ustawienia \> Zlecenia pracy \> Ustawienia projektu**).</span><span class="sxs-lookup"><span data-stu-id="58221-163">You should still be on the **Project setup** page (**Asset management \> Setup \> Work orders \> Project setup**).</span></span>

1. <span data-ttu-id="58221-164">Na karcie **Grupa projektów** wybierz opcję **Dodaj**, aby dodać wiersz.</span><span class="sxs-lookup"><span data-stu-id="58221-164">On the **Project group** tab, select **Add** to add a line.</span></span>
1. <span data-ttu-id="58221-165">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="58221-165">On the new line, set the following values:</span></span>

    - <span data-ttu-id="58221-166">**Typ zlecenia pracy:** *Usługa* (typ zlecenia pracy utworzony wcześniej)</span><span class="sxs-lookup"><span data-stu-id="58221-166">**Work order type:** *Service* (the work order type that you created earlier)</span></span>
    - <span data-ttu-id="58221-167">**Grupa projektów:** *TM*</span><span class="sxs-lookup"><span data-stu-id="58221-167">**Project group:** *TM*</span></span>

> [!NOTE]
> <span data-ttu-id="58221-168">Umowa projektu w projekcie zlecenia pracy jest zawsze dziedziczona po projekcie nadrzędnym.</span><span class="sxs-lookup"><span data-stu-id="58221-168">The project contract on the work order project is always inherited from the parent project.</span></span>

### <a name="step-6-link-an-asset-to-the-customer-id"></a><span data-ttu-id="58221-169">Krok 6: Łączenie składnika majątku z identyfikatorem klienta</span><span class="sxs-lookup"><span data-stu-id="58221-169">Step 6: Link an asset to the customer ID</span></span>

1. <span data-ttu-id="58221-170">Wybierz **Zarządzanie składnikami majątku \> Składniki majątku \> Aktywne składniki majątku**.</span><span class="sxs-lookup"><span data-stu-id="58221-170">Go to **Asset management \> Assets \> Active assets**.</span></span>
1. <span data-ttu-id="58221-171">W polu **Filtruj** wprowadź *VE-102* i wybierz opcję filtrowania według **składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="58221-171">In the **Filter** field, enter *VE-102*, and select to filter by **Asset**.</span></span>
1. <span data-ttu-id="58221-172">Wybierz składnik majątku, aby otworzyć ustawienia.</span><span class="sxs-lookup"><span data-stu-id="58221-172">Select the asset to open its settings.</span></span>
1. <span data-ttu-id="58221-173">Na skróconej karcie **Odbiorca**, w polu **Konto odbiorcy**, należy ustawić wartość *US-013* (*Pelican Wholesales*).</span><span class="sxs-lookup"><span data-stu-id="58221-173">On the **Customer** FastTab, set the **Customer account** field to *US-013* (*Pelican Wholesales*).</span></span>

    <span data-ttu-id="58221-174">Pole **Nazwa** jest automatycznie aktualizowana do wartości *Pelican Wholesales*.</span><span class="sxs-lookup"><span data-stu-id="58221-174">The **Name** field is automatically updated to *Pelican Wholesales*.</span></span>

### <a name="step-7-create-a-new-work-order-on-the-asset"></a><span data-ttu-id="58221-175">Krok 7: Tworzenie nowego typu zlecenia pracy w składniku majątku</span><span class="sxs-lookup"><span data-stu-id="58221-175">Step 7: Create a new work order on the asset</span></span>

1. <span data-ttu-id="58221-176">Przejdź do pozycji **Zarządzanie składnikami majątku \> Zlecenia pracy \> Aktywne zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="58221-176">Go to **Asset management \> Work orders \> Active work orders**.</span></span>
1. <span data-ttu-id="58221-177">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="58221-177">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="58221-178">W wyświetlonym oknie dialogowym **Utwórz zlecenie pracy** można ustawić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="58221-178">In the **Create work order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="58221-179">**Typ zlecenia pracy:** *Usługa*</span><span class="sxs-lookup"><span data-stu-id="58221-179">**Work order type:** *Service*</span></span>
    - <span data-ttu-id="58221-180">**Opis:** *Naprawa ciężarówki*</span><span class="sxs-lookup"><span data-stu-id="58221-180">**Description:** *Repair Truck*</span></span>
    - <span data-ttu-id="58221-181">**Konto klienta:** *US-013* (*Pelican Wholesales*)</span><span class="sxs-lookup"><span data-stu-id="58221-181">**Customer account:** *US-013* (*Pelican Wholesales*)</span></span>
    - <span data-ttu-id="58221-182">**Składnik majątku:** *VE-102*</span><span class="sxs-lookup"><span data-stu-id="58221-182">**Asset:** *VE-102*</span></span>

        > [!NOTE]
        > <span data-ttu-id="58221-183">W wynikach wyszukiwania są dostępne tylko te składnik majątku, które są połączone z wybranym kontem odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="58221-183">The lookup shows only assets that are linked to the selected customer account.</span></span>

    - <span data-ttu-id="58221-184">**Typ zadania konserwacji:** *Naprawa*</span><span class="sxs-lookup"><span data-stu-id="58221-184">**Maintenance job type:** *Repair*</span></span>
    - <span data-ttu-id="58221-185">**Zawód:** *Mechanik*</span><span class="sxs-lookup"><span data-stu-id="58221-185">**Trade:** *Mechanic*</span></span>
    - <span data-ttu-id="58221-186">**Poziom usług:** *4*</span><span class="sxs-lookup"><span data-stu-id="58221-186">**Service level:** *4*</span></span>

1. <span data-ttu-id="58221-187">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="58221-187">Select **OK**.</span></span>

### <a name="step-8-review-the-work-order-and-start-to-work-on-it"></a><span data-ttu-id="58221-188">Krok 8: Przeglądanie zlecenia pracy i rozpoczynanie pracy</span><span class="sxs-lookup"><span data-stu-id="58221-188">Step 8: Review the work order and start to work on it</span></span>

<span data-ttu-id="58221-189">W tej sekcji będziesz pracować nad zleceniem pracy utworzonym w poprzedniej sekcji.</span><span class="sxs-lookup"><span data-stu-id="58221-189">In this section, you will work on the work order that you created in the previous section.</span></span>

1. <span data-ttu-id="58221-190">Aby sprawdzić, czy projekt nadrzędny to projekt *Zlecenie pracy Pelican Wholesales*, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="58221-190">Follow these steps to verify that the parent project is the *Pelican wholesales Work order* project:</span></span>

    1. <span data-ttu-id="58221-191">W sekcji **Zadania konserwacji zlecenia pracy** wybierz wiersz.</span><span class="sxs-lookup"><span data-stu-id="58221-191">In the **Work order maintenance jobs** section, select a line.</span></span>
    1. <span data-ttu-id="58221-192">Na skróconej karcie **Szczegóły wiersza** sprawdź wartość **identyfikatora projektu**.</span><span class="sxs-lookup"><span data-stu-id="58221-192">On the **Line details** FastTab, inspect the **Project ID** value.</span></span> <span data-ttu-id="58221-193">Powinien to być numer z łącznikiem w następującej postaci: *\<Parent-Project-ID\>-\<Project-ID\>*.</span><span class="sxs-lookup"><span data-stu-id="58221-193">It should be a hyphenated number in the form *\<Parent-Project-ID\>-\<Project-ID\>*.</span></span> <span data-ttu-id="58221-194">Ta wartość jest linkiem.</span><span class="sxs-lookup"><span data-stu-id="58221-194">This value is a link.</span></span>
    1. <span data-ttu-id="58221-195">Wybierz link identyfikatora projektu, aby otworzyć stronę, na której możesz przejrzeć projekt nadrzędny i nazwy projektów.</span><span class="sxs-lookup"><span data-stu-id="58221-195">Select the project ID link to open a page where you can view the parent project and project names.</span></span>

1. <span data-ttu-id="58221-196">W okienku akcji, na karcie **Zlecenie pracy**, w grupie **Stan cyklu życia** wybierz **Aktualizuj stan zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="58221-196">On the Action Pane, on the **Work order** tab, in the **Lifecycle state** group, select **Update work order state**.</span></span>
1. <span data-ttu-id="58221-197">W oknie dialogowym **Aktualizuj stan zlecenia pracy** w kolumnie **Wybierz** zaznacz pole wyboru dla wiersza, w którym w polu **Stan cyklu życia** ustawiono wartość *W toku*.</span><span class="sxs-lookup"><span data-stu-id="58221-197">In the **Update work order state** dialog box, in the **Select** column, select the check box for the row where the **Lifecycle state** field is set to *In progress*.</span></span>
1. <span data-ttu-id="58221-198">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="58221-198">Select **OK**.</span></span>
1. <span data-ttu-id="58221-199">W oknie dialogowym **Stan cyklu życia: W toku** wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="58221-199">In the **Lifecycle state: InProgress** dialog box, select **OK**.</span></span>

### <a name="step-9-post-the-hours-that-were-spent-on-the-work-order-and-create-a-new-invoice-proposal"></a><span data-ttu-id="58221-200">Krok 9: Księgowanie godzin spędzonych na pracy ze zleceniem i tworzenie nowej propozycji faktury</span><span class="sxs-lookup"><span data-stu-id="58221-200">Step 9: Post the hours that were spent on the work order and create a new invoice proposal</span></span>

<span data-ttu-id="58221-201">W tej sekcji będziesz nadal pracować nad zleceniem pracy, nad którym rozpoczęto pracę w poprzedniej sekcji.</span><span class="sxs-lookup"><span data-stu-id="58221-201">In this section, you will continue to work on the work order that you worked on in the previous section.</span></span>

1. <span data-ttu-id="58221-202">W okienku akcji na karcie **Zlecenie pracy**, w grupie **Projekt** kliknij **Arkusze**.</span><span class="sxs-lookup"><span data-stu-id="58221-202">On the Action Pane, on the **Work order** tab, in the **Project** group, select **Journals**.</span></span>

    <span data-ttu-id="58221-203">Zostanie wyświetlona strona **Arkusze zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="58221-203">The **Work order journals** page appears.</span></span> <span data-ttu-id="58221-204">W tym miejscu można rejestrować czas, który użytkownik poświęcił na zlecenie pracy.</span><span class="sxs-lookup"><span data-stu-id="58221-204">Here, you can register the time that you spent on the work order.</span></span>

1. <span data-ttu-id="58221-205">Na skróconej karcie **Godziny** wybierz pozycję **Dodaj wiersz**.</span><span class="sxs-lookup"><span data-stu-id="58221-205">On the **Hours** FastTab, select **Add line**.</span></span>
1. <span data-ttu-id="58221-206">W nowym wierszu ustaw w polu **Godziny** wartość *4*.</span><span class="sxs-lookup"><span data-stu-id="58221-206">On the new, line, set the **Hours** field to *4*.</span></span>
1. <span data-ttu-id="58221-207">W okienku akcji wybierz pozycję **Księguj arkusze**.</span><span class="sxs-lookup"><span data-stu-id="58221-207">On the Action Pane, select **Post journals**.</span></span>
1. <span data-ttu-id="58221-208">Zamknij stronę **Arkusze zlecenia pracy**, aby powrócić do zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="58221-208">Close the **Work order journals** page to return to the work order.</span></span>
1. <span data-ttu-id="58221-209">W okienku akcji na karcie **Fakturowanie** wybierz opcję **Nowa propozycja faktury**.</span><span class="sxs-lookup"><span data-stu-id="58221-209">On the Action Pane, on the **Invoicing** tab, select **New invoice proposal**.</span></span>
1. <span data-ttu-id="58221-210">W oknie dialogowym **Tworzenie propozycji faktury** w sekcji **Transakcje projektu** zaznacz pole wyboru **Wybierz** dla każdego wiersza, który chcesz zafakturować.</span><span class="sxs-lookup"><span data-stu-id="58221-210">In the **Create invoice proposal** dialog box, in the **Project transactions** section, select the **Select** check box for every line  that you want to invoice.</span></span>
1. <span data-ttu-id="58221-211">Naciśnij przycisk **OK**, aby zamknąć okno dialogowe i wyświetlić nową propozycję faktury.</span><span class="sxs-lookup"><span data-stu-id="58221-211">Select **OK** to close the dialog box and view the new invoice proposal.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]