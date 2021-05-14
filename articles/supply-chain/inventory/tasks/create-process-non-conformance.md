---
title: Tworzenie i przetwarzanie niezgodności
description: Ten temat opisuje jak przeprowadzić zarządzanie niezgodnościami na podstawie istniejącego zlecenia kontroli jakości.
author: perlynne
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 06a56a694f7a80d65cb46d08744e78d8361cee3b
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956213"
---
# <a name="create-and-process-nonconformances"></a><span data-ttu-id="05511-103">Tworzenie i przetwarzanie niezgodności</span><span class="sxs-lookup"><span data-stu-id="05511-103">Create and process nonconformances</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="05511-104">Ten temat opisuje jak przeprowadzić zarządzanie niezgodnościami na podstawie istniejącego zlecenia kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="05511-104">This topic describes how to perform nonconformance management based on an existing quality order.</span></span> <span data-ttu-id="05511-105">Zazwyczaj zarządzanie niezgodnościami jest wykonywane przez pracownika ds. kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="05511-105">Typically, nonconformance management is done by a quality clerk.</span></span> <span data-ttu-id="05511-106">Warunkiem wstępnym jest dostęp do zlecenia kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="05511-106">As a prerequisite, you must have a quality order available.</span></span> <span data-ttu-id="05511-107">(Aby uzyskać informacje o tworzeniu zlecenia kontroli jakości, zobacz temat [Sprawdzanie jakości towarów](inspect-quality-goods.md)).</span><span class="sxs-lookup"><span data-stu-id="05511-107">(For information about how to create a quality order, see [Inspect the quality of goods](inspect-quality-goods.md).)</span></span>

<span data-ttu-id="05511-108">Aby użytkownik był w stanie przetworzyć zatwierdzenie niezgodności, musi być do niego przypisany pracownik w polu **Osoba** na stronie **Użytkownicy**.</span><span class="sxs-lookup"><span data-stu-id="05511-108">Before a user can process the approval of a nonconformance, a worker must be assigned to them in the **Person** field on the **Users** page.</span></span> <span data-ttu-id="05511-109">Ponadto, aby użytkownik mógł używać notatek do dokumentu, w polu **Włącz obsługę dokumentów** w jego opcjach użytkownika musi być ustawiona wartość *Tak*.</span><span class="sxs-lookup"><span data-stu-id="05511-109">Additionally, before the user can use the document notes, the **Enable document handling** option must be set to *Yes* in their user options.</span></span>

## <a name="create-a-nonconformance"></a><span data-ttu-id="05511-110">Tworzenie rekordu niezgodności</span><span class="sxs-lookup"><span data-stu-id="05511-110">Create a nonconformance</span></span>

<span data-ttu-id="05511-111">Aby utworzyć niezgodność, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="05511-111">To create a nonconformance, follow these steps.</span></span>

1. <span data-ttu-id="05511-112">Wybierz kolejno opcje **Zarządzanie zapasami \> Zadania okresowe \> Zarządzanie jakością \> Niezgodności**.</span><span class="sxs-lookup"><span data-stu-id="05511-112">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="05511-113">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="05511-113">On the Action pane, select **New**.</span></span>
1. <span data-ttu-id="05511-114">W oknie dialogowym **Tworzenie niezgodności** w polu **Typ problemu** wybierz typ problemu, który został znaleziony w trakcie procesu inspekcji.</span><span class="sxs-lookup"><span data-stu-id="05511-114">In the **Create non conformance** dialog box, in **Problem type** field, select the type of problem that was found during the inspection process.</span></span>
1. <span data-ttu-id="05511-115">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="05511-115">Select **OK**.</span></span>

## <a name="approve-or-reject-a-nonconformance"></a><span data-ttu-id="05511-116">Zatwierdzanie lub odrzucanie niezgodności</span><span class="sxs-lookup"><span data-stu-id="05511-116">Approve or reject a nonconformance</span></span>

<span data-ttu-id="05511-117">Aby zatwierdzić lub odrzucić niezgodność, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="05511-117">To approve or reject a nonconformance, follow these steps.</span></span>

1. <span data-ttu-id="05511-118">Wybierz kolejno opcje **Zarządzanie zapasami \> Zadania okresowe \> Zarządzanie jakością \> Niezgodności**.</span><span class="sxs-lookup"><span data-stu-id="05511-118">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="05511-119">Na liście zaznacz niezgodność, którą chcesz zaktualizować.</span><span class="sxs-lookup"><span data-stu-id="05511-119">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="05511-120">Korektę można dodać tylko do zatwierdzonych niezgodności.</span><span class="sxs-lookup"><span data-stu-id="05511-120">You can add a correction only to nonconformances that are approved.</span></span>

1. <span data-ttu-id="05511-121">W okienku akcji wybierz opcje **Funkcje \> Zatwierdź niezgodność**, aby zatwierdzić tę niezgodność, lub **Funkcje \> Odrzuć niezgodność**, aby ją odrzucić.</span><span class="sxs-lookup"><span data-stu-id="05511-121">On the Action Pane, select **Functions \> Approve non conformance** to approve the nonconformance or **Functions \> Refuse non conformance** to reject it.</span></span> <span data-ttu-id="05511-122">Zatwierdzone niezgodności można skojarzyć z [powiązanymi operacjami](../quality-operations.md).</span><span class="sxs-lookup"><span data-stu-id="05511-122">You can associate approved nonconformances with [related operations](../quality-operations.md).</span></span> <span data-ttu-id="05511-123">W ten sposób można rejestrować pracę wykonaną w ramach obsługi niezgodności i przetwarzania obsługi korekt.</span><span class="sxs-lookup"><span data-stu-id="05511-123">In this way, you can record work that is done as part of the nonconformance handling and the processing of correction handling.</span></span>
1. <span data-ttu-id="05511-124">Zostanie wyświetlony monit o potwierdzenie wyboru.</span><span class="sxs-lookup"><span data-stu-id="05511-124">You're prompted to confirm your selection.</span></span> <span data-ttu-id="05511-125">Wybierz przycisk **Tak**, aby kontynuować.</span><span class="sxs-lookup"><span data-stu-id="05511-125">Select **Yes** to continue.</span></span>

## <a name="add-operations-and-other-details-to-nonconformances"></a><span data-ttu-id="05511-126">Dodawanie operacji i innych szczegółów do niezgodności</span><span class="sxs-lookup"><span data-stu-id="05511-126">Add operations and other details to nonconformances</span></span>

<span data-ttu-id="05511-127">Po utworzeniu niezgodności można rozpocząć dodawanie powiązanych operacji i określenie dodatkowych informacji o tych operacjach.</span><span class="sxs-lookup"><span data-stu-id="05511-127">After you've created a nonconformance, you can start to add related operations and specify additional information about those operations.</span></span> <span data-ttu-id="05511-128">Powiązane operacje można dodać tylko do zatwierdzonych niezgodności.</span><span class="sxs-lookup"><span data-stu-id="05511-128">You can add related operations only to nonconformances that are approved.</span></span>

<span data-ttu-id="05511-129">Oprócz podstawowych informacji do operacji można dodawać następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="05511-129">Besides the basic information, you can add the following details to an operation:</span></span>

- <span data-ttu-id="05511-130">**Towary** — można utworzyć listę towarów zużywanych w celu wykonania korekty.</span><span class="sxs-lookup"><span data-stu-id="05511-130">**Items** – You can create a list of items that are consumed to perform the correction.</span></span> <span data-ttu-id="05511-131">Na przykład towary mogą być produktami wymaganymi do naprawy sprzętu lub substancjami wymaganymi do przeróbki gotowego produktu.</span><span class="sxs-lookup"><span data-stu-id="05511-131">For example, the items might be products that are required to repair equipment or ingredients that are required to rework a finished product.</span></span>
- <span data-ttu-id="05511-132">**Opłaty związane z kontrolą jakości** — można utworzyć listę opłat, które zostały poniesione lub które są rozliczane w zewnętrznych źródłach.</span><span class="sxs-lookup"><span data-stu-id="05511-132">**Quality charges** – You can create a list of charges that are incurred or billed out to external sources.</span></span>
- <span data-ttu-id="05511-133">**Karta czasu pracy** — można utworzyć dziennik czasu, jaki każdy pracownik poświęca na operację.</span><span class="sxs-lookup"><span data-stu-id="05511-133">**Timesheet** – You can create a log of the time that each worker spends on the operation.</span></span>

<span data-ttu-id="05511-134">Pozostałe ustawienia są opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="05511-134">The remaining settings are optional.</span></span> <span data-ttu-id="05511-135">Koszt każdego towaru, opłaty związane z jakością i karta czasu pracy są sumowane i wyświetlane w operacji.</span><span class="sxs-lookup"><span data-stu-id="05511-135">The cost for each item, quality charges, and the timesheet are summed and shown on the operation.</span></span> <span data-ttu-id="05511-136">Nie można bezpośrednio edytować pola **Koszt** w operacji.</span><span class="sxs-lookup"><span data-stu-id="05511-136">You can't directly edit the **Cost** field on the operation.</span></span>

### <a name="create-an-operation-for-a-nonconformance"></a><span data-ttu-id="05511-137">Tworzenie operacji dla niezgodności</span><span class="sxs-lookup"><span data-stu-id="05511-137">Create an operation for a nonconformance</span></span>

<span data-ttu-id="05511-138">Aby utworzyć operację dla niezgodności, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="05511-138">To create an operation for a nonconformance, follow these steps.</span></span>

1. <span data-ttu-id="05511-139">Wybierz kolejno opcje **Zarządzanie zapasami \> Zadania okresowe \> Zarządzanie jakością \> Niezgodności**.</span><span class="sxs-lookup"><span data-stu-id="05511-139">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="05511-140">Na liście zaznacz niezgodność, którą chcesz zaktualizować.</span><span class="sxs-lookup"><span data-stu-id="05511-140">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="05511-141">Operacje można dodać lub aktualizować tylko dla zatwierdzonych niezgodności.</span><span class="sxs-lookup"><span data-stu-id="05511-141">You can add or update operations only for nonconformances that are approved.</span></span>

1. <span data-ttu-id="05511-142">W okienku akcji wybierz pozycję **Powiązane operacje**.</span><span class="sxs-lookup"><span data-stu-id="05511-142">On the Action Pane, select **Related operations**.</span></span>
1. <span data-ttu-id="05511-143">Na stronie **Powiązane operacje** w okienku akcja wybierz pozycję **Nowa**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="05511-143">On the **Related operations** page, on the Action pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="05511-144">Następnie ustaw następujące pola dla nowego wiersza:</span><span class="sxs-lookup"><span data-stu-id="05511-144">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="05511-145">**Operacja** — umożliwia wybranie kodu operacji, która zostanie wykonana dla niezgodności.</span><span class="sxs-lookup"><span data-stu-id="05511-145">**Operation** – Select the code of the operation that will be performed for the nonconformance.</span></span>
    - <span data-ttu-id="05511-146">**Przyczyna** — służy do wprowadzania szczegółowego opisu objaśnienia powodu, dla którego operacja jest wymagana.</span><span class="sxs-lookup"><span data-stu-id="05511-146">**Reason** – Enter a detailed description that explains why the operation is required.</span></span>
    - <span data-ttu-id="05511-147">**Zamówienie sprzedaży** — jeśli wybrany kod operacji jest powiązany z typem zamówienia sprzedaży, należy wybrać zamówienie sprzedaży, z którym ma być powiązana operacja.</span><span class="sxs-lookup"><span data-stu-id="05511-147">**Sales order** – If the selected operation code is related to the sales order type, select the sales order that you're linking the operation to.</span></span>
    - <span data-ttu-id="05511-148">**Zamówienie zakupu** — jeśli wybrany kod operacji jest powiązany z typem zamówienia zakupu, należy wybrać zamówienie zakupu, z którym ma być powiązana operacja.</span><span class="sxs-lookup"><span data-stu-id="05511-148">**Purchase order** – If the selected operation code is related to the purchase order type, select the purchase order that you're linking the operation to.</span></span>

1. <span data-ttu-id="05511-149">Zamknij strony.</span><span class="sxs-lookup"><span data-stu-id="05511-149">Close the pages.</span></span>

### <a name="add-items-to-an-operation"></a><span data-ttu-id="05511-150">Dodawanie towarów do operacji</span><span class="sxs-lookup"><span data-stu-id="05511-150">Add items to an operation</span></span>

<span data-ttu-id="05511-151">Aby dodać towary do operacji, wykonaj następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="05511-151">To add items to an operation, follow these steps.</span></span>

1. <span data-ttu-id="05511-152">Wybierz kolejno opcje **Zarządzanie zapasami \> Zadania okresowe \> Zarządzanie jakością \> Niezgodności**.</span><span class="sxs-lookup"><span data-stu-id="05511-152">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="05511-153">Na liście zaznacz niezgodność, którą chcesz zaktualizować.</span><span class="sxs-lookup"><span data-stu-id="05511-153">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="05511-154">Operacje można dodać lub aktualizować tylko dla zatwierdzonych niezgodności.</span><span class="sxs-lookup"><span data-stu-id="05511-154">You can add or update operations only for nonconformances that are approved.</span></span>

1. <span data-ttu-id="05511-155">W okienku akcji wybierz pozycję **Powiązane operacje**.</span><span class="sxs-lookup"><span data-stu-id="05511-155">On the Action Pane, select **Related operations**.</span></span>
1. <span data-ttu-id="05511-156">Na stronie **Powiązane operacje** wybierz operację, do której chcesz dodać towary.</span><span class="sxs-lookup"><span data-stu-id="05511-156">On the **Related operations** page, select the operation that you want to add items to.</span></span>
1. <span data-ttu-id="05511-157">W okienku akcji kliknij pozycję **Towary**.</span><span class="sxs-lookup"><span data-stu-id="05511-157">On the Action Pane, select **Items**.</span></span>
1. <span data-ttu-id="05511-158">Na stronie **Powiązane operacje** w okienku akcja wybierz pozycję **Nowa**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="05511-158">On the **Related operations** page, on the Action pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="05511-159">Następnie ustaw następujące pola dla nowego wiersza:</span><span class="sxs-lookup"><span data-stu-id="05511-159">Then set the following fields for new row:</span></span>

    - <span data-ttu-id="05511-160">**Kod towaru** — umożliwia wybór produktu, który zostanie zużyty w ramach wybranej operacji.</span><span class="sxs-lookup"><span data-stu-id="05511-160">**Item number** – Select the product that will be consumed as part of the selected operation.</span></span>
    - <span data-ttu-id="05511-161">**Ilość** — umożliwia wprowadzenie liczby towarów, które zostaną zużyte.</span><span class="sxs-lookup"><span data-stu-id="05511-161">**Quantity** – Enter the number of items that will be consumed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="05511-162">Koszt towaru można wyświetlić w polu **Koszt** na karcie **Ogólne**. Wyświetlany koszt pochodzi z kosztu ustawionego na stronie **Zwolniony produkt**.</span><span class="sxs-lookup"><span data-stu-id="05511-162">You can view the cost for the item in the **Cost** field on the **General** tab. The cost that is shown there comes from the cost that is set up on the **Released product** page.</span></span> <span data-ttu-id="05511-163">Nie można zaktualizować kosztu bezpośrednio na stronie **Towar operacji powiązanej**.</span><span class="sxs-lookup"><span data-stu-id="05511-163">The cost can't be updated directly on the **Related operation item** page.</span></span> <span data-ttu-id="05511-164">Koszt wszystkich towarów dodawanych na stronie **Towary powiązanej operacji** jest automatycznie dodawany do pola **Koszt** na stronie **Operacje powiązane**.</span><span class="sxs-lookup"><span data-stu-id="05511-164">The cost of all items that are added on the **Related operation items** page is automatically added to the **Cost** field on the **Related operations** page.</span></span>

1. <span data-ttu-id="05511-165">Powtórz poprzedni krok dla każdego dodatkowego towaru, który musisz dodać.</span><span class="sxs-lookup"><span data-stu-id="05511-165">Repeat the previous step for each additional item that you must add.</span></span>
1. <span data-ttu-id="05511-166">Zamknij strony.</span><span class="sxs-lookup"><span data-stu-id="05511-166">Close the pages.</span></span>

### <a name="add-quality-charges-to-an-operation"></a><span data-ttu-id="05511-167">Dodawanie opłat związanych z kontrolą jakości do operacji</span><span class="sxs-lookup"><span data-stu-id="05511-167">Add quality charges to an operation</span></span>

<span data-ttu-id="05511-168">Aby dodać opłaty związane z kontrolą jakości do operacji, wykonaj następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="05511-168">To add quality charges to an operation, follow these steps.</span></span>

1. <span data-ttu-id="05511-169">Wybierz kolejno opcje **Zarządzanie zapasami \> Zadania okresowe \> Zarządzanie jakością \> Niezgodności**.</span><span class="sxs-lookup"><span data-stu-id="05511-169">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="05511-170">Na liście zaznacz niezgodność, którą chcesz zaktualizować.</span><span class="sxs-lookup"><span data-stu-id="05511-170">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="05511-171">Operacje można dodać lub aktualizować tylko dla zatwierdzonych niezgodności.</span><span class="sxs-lookup"><span data-stu-id="05511-171">You can add or update operations only for nonconformances that are approved.</span></span>

1. <span data-ttu-id="05511-172">W okienku akcji wybierz pozycję **Powiązane operacje**.</span><span class="sxs-lookup"><span data-stu-id="05511-172">On the Action Pane, select **Related operations**.</span></span>
1. <span data-ttu-id="05511-173">Na stronie **Powiązane operacje** wybierz operację, do której chcesz dodać opłaty związane z kontrolą jakości.</span><span class="sxs-lookup"><span data-stu-id="05511-173">On the **Related operations** page, select the operation that you want to add quality charges to.</span></span>
1. <span data-ttu-id="05511-174">W okienku akcji kliknij opcję **Opłaty związane z kontroli jakości**.</span><span class="sxs-lookup"><span data-stu-id="05511-174">On the Action Pane, select **Quality charges**.</span></span>
1. <span data-ttu-id="05511-175">Na stronie **Opłaty za powiązane operacje** w okienku akcja wybierz pozycję **Nowa**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="05511-175">On the **Related operation charges** page, on the Action pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="05511-176">Następnie ustaw następujące pola dla nowego wiersza:</span><span class="sxs-lookup"><span data-stu-id="05511-176">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="05511-177">**Kod opłat** — umożliwia wybór opłaty związanej z kontrolą jakości, która ma zostać dodana.</span><span class="sxs-lookup"><span data-stu-id="05511-177">**Charges code** – Select the quality charge that you want to add.</span></span>
    - <span data-ttu-id="05511-178">**Opis** – wprowadź szczegółowy opis opłaty.</span><span class="sxs-lookup"><span data-stu-id="05511-178">**Description** – Enter a detailed description of the charge.</span></span>
    - <span data-ttu-id="05511-179">**Wartość opłat** — umożliwia wprowadzanie kwoty do naliczenia.</span><span class="sxs-lookup"><span data-stu-id="05511-179">**Charges value** – Enter the amount of the charge.</span></span>

1. <span data-ttu-id="05511-180">Powtórz poprzedni krok dla każdej dodatkowej opłaty, którą musisz dodać.</span><span class="sxs-lookup"><span data-stu-id="05511-180">Repeat the previous step for each additional charge that you must add.</span></span>
1. <span data-ttu-id="05511-181">Zamknij strony.</span><span class="sxs-lookup"><span data-stu-id="05511-181">Close the pages.</span></span>

> [!NOTE]
> <span data-ttu-id="05511-182">Kwota w polu **Wartość opłat** jest automatycznie sumowana dla wszystkich opłat związanych z kontrolą jakości i dodawana do innych kwot w polu **Koszt** na stronie **Operacje powiązane**.</span><span class="sxs-lookup"><span data-stu-id="05511-182">The amount in the **Charges value** field is automatically summed for all quality charges and added to any other amounts in the **Cost** field on the **Related operations** page.</span></span>

### <a name="create-a-timesheet-on-an-operation"></a><span data-ttu-id="05511-183">Tworzenie karty czasu pracy dla operacji</span><span class="sxs-lookup"><span data-stu-id="05511-183">Create a timesheet on an operation</span></span>

<span data-ttu-id="05511-184">Aby dodać kartę czasu pracy do operacji, wykonaj następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="05511-184">To add a timesheet to an operation, follow these steps.</span></span>

1. <span data-ttu-id="05511-185">Wybierz kolejno opcje **Zarządzanie zapasami \> Zadania okresowe \> Zarządzanie jakością \> Niezgodności**.</span><span class="sxs-lookup"><span data-stu-id="05511-185">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="05511-186">Na liście zaznacz niezgodność, którą chcesz zaktualizować.</span><span class="sxs-lookup"><span data-stu-id="05511-186">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="05511-187">Operacje można dodać lub aktualizować tylko dla zatwierdzonych niezgodności.</span><span class="sxs-lookup"><span data-stu-id="05511-187">You can add or update operations only for nonconformances that are approved.</span></span>

1. <span data-ttu-id="05511-188">W okienku akcji wybierz pozycję **Powiązane operacje**.</span><span class="sxs-lookup"><span data-stu-id="05511-188">On the Action Pane, select **Related operations**.</span></span>
1. <span data-ttu-id="05511-189">Na stronie **Powiązane operacje** wybierz operację, do której chcesz dodać kartę czasu pracy.</span><span class="sxs-lookup"><span data-stu-id="05511-189">On the **Related operations** page, select the operation that you want to add a timesheet to.</span></span>
1. <span data-ttu-id="05511-190">W okienku akcji wybierz opcję **Karta czasu pracy**.</span><span class="sxs-lookup"><span data-stu-id="05511-190">On the Action Pane, select **Timesheet**.</span></span>
1. <span data-ttu-id="05511-191">Na stronie **Karty czasu pracy powiązanej operacji** w okienku akcja wybierz pozycję **Nowa**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="05511-191">On the **Related operation time sheets** page, on the Action pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="05511-192">Następnie ustaw następujące pola dla nowego wiersza:</span><span class="sxs-lookup"><span data-stu-id="05511-192">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="05511-193">**Data** — umożliwia określenie daty zakończenia pracy.</span><span class="sxs-lookup"><span data-stu-id="05511-193">**Date** – Specify the date when work was done.</span></span> <span data-ttu-id="05511-194">Domyślnie w tym polu jest wstawiona bieżąca data.</span><span class="sxs-lookup"><span data-stu-id="05511-194">By default, this field is set to the current date.</span></span>
    - <span data-ttu-id="05511-195">**Pracownik** — Pozwala wybrać pracownika, który wykonał pracę.</span><span class="sxs-lookup"><span data-stu-id="05511-195">**Worker** – Select the worker who did the work.</span></span> <span data-ttu-id="05511-196">Domyślnie w tym polu jest wstawiony pracownik przypisany do bieżącego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="05511-196">By default, this field is set to the worker that is assigned to the current user.</span></span>
    - <span data-ttu-id="05511-197">**Godziny operacji** — służy do wprowadzania liczby godzin przepracowanych przy wybranej operacji.</span><span class="sxs-lookup"><span data-stu-id="05511-197">**Operation hours** – Enter the number of hours that were worked on the selected operation.</span></span>
    - <span data-ttu-id="05511-198">**Zafakturowane** — to pole wyboru należy zaznaczyć, jeśli faktura obciąża dostawcę lub odbiorcę.</span><span class="sxs-lookup"><span data-stu-id="05511-198">**Invoiced** – Select this check box if the time has been charged to a customer or vendor on an invoice.</span></span>

    > [!NOTE]
    > <span data-ttu-id="05511-199">Koszt można wyświetlić w polu **Koszt** na karcie **Ogólne**. Koszt jest obliczany przy użyciu stawki która jest zdefiniowana na stronie **Parametry zarządzania zapasami**.</span><span class="sxs-lookup"><span data-stu-id="05511-199">You can view the cost in the **Cost** field on the **General** tab. The cost is calculated by using the rate that you define on the **Inventory management parameters** page.</span></span>

1. <span data-ttu-id="05511-200">Powtórz poprzedni krok dla każdego dodatkowego wiersza karty czasu pracy, który musisz dodać.</span><span class="sxs-lookup"><span data-stu-id="05511-200">Repeat the previous step for each additional timesheet line that you must add.</span></span>
1. <span data-ttu-id="05511-201">Zamknij strony.</span><span class="sxs-lookup"><span data-stu-id="05511-201">Close the pages.</span></span>

> [!NOTE]
> <span data-ttu-id="05511-202">Kwota w polu **Koszt** jest automatycznie sumowana dla wszystkich wierszy karty czasu pracy i dodawana do innych kwot w polu **Koszt** na stronie **Operacje powiązane**.</span><span class="sxs-lookup"><span data-stu-id="05511-202">The amount in the **Cost** field is summed for all timesheet lines and added to any other amounts in the **Cost** field on the **Related operations** page.</span></span>

## <a name="add-a-correction-to-a-nonconformance"></a><span data-ttu-id="05511-203">Dodawanie korekty do niezgodności</span><span class="sxs-lookup"><span data-stu-id="05511-203">Add a correction to a nonconformance</span></span>

<span data-ttu-id="05511-204">Aby dodać korektę do niezgodności, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="05511-204">To add a correction to a nonconformance, follow these steps.</span></span>

1. <span data-ttu-id="05511-205">Wybierz kolejno opcje **Zarządzanie zapasami \> Zadania okresowe \> Zarządzanie jakością \> Niezgodności**.</span><span class="sxs-lookup"><span data-stu-id="05511-205">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="05511-206">Na liście zaznacz niezgodność, którą chcesz zaktualizować.</span><span class="sxs-lookup"><span data-stu-id="05511-206">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="05511-207">Korektę można dodać tylko do zatwierdzonych niezgodności.</span><span class="sxs-lookup"><span data-stu-id="05511-207">You can add a correction only to nonconformances that are approved.</span></span>

1. <span data-ttu-id="05511-208">W okienku akcji wybierz opcję **Korekty**.</span><span class="sxs-lookup"><span data-stu-id="05511-208">On the Action Pane, select **Corrections**.</span></span>
1. <span data-ttu-id="05511-209">Na stronie **Korekty**, w okienku akcji wybierz opcję **Nowy**, aby dodać nowy wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="05511-209">On the **Corrections** page, on the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="05511-210">Następnie ustaw następujące pola dla nowego wiersza:</span><span class="sxs-lookup"><span data-stu-id="05511-210">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="05511-211">**Diagnostyka** — umożliwia wybranie typu diagnostyki identyfikującego typ korekty, która jest tworzona.</span><span class="sxs-lookup"><span data-stu-id="05511-211">**Diagnostic** – Select the diagnostic type that identifies the type of correction that you're creating.</span></span>
    - <span data-ttu-id="05511-212">**Pracownik** — Umożliwia wybór osoby, która odpowiada za korektę.</span><span class="sxs-lookup"><span data-stu-id="05511-212">**Worker** – Select the person who is responsible for the correction.</span></span>
    - <span data-ttu-id="05511-213">**Priorytet korekty** — umożliwia wybór opcji wskazującej sposób ustalania priorytetów korekty (*Niski*, *Normalny* lub *Wysoki*).</span><span class="sxs-lookup"><span data-stu-id="05511-213">**Correction priority** – Select an option to indicate how the correction should be prioritized (*Low*, *Normal*, or *High*).</span></span>
    - <span data-ttu-id="05511-214">**Data wnioskowania** — wprowadź datę wnioskowania o akcję korygującą.</span><span class="sxs-lookup"><span data-stu-id="05511-214">**Requested date** – Enter the date when the corrective action was requested.</span></span>
    - <span data-ttu-id="05511-215">**Data planowana** — umożliwia wprowadzenie oczekiwanej daty wykonania korekty.</span><span class="sxs-lookup"><span data-stu-id="05511-215">**Planned date** – Enter the date when the correction is expected to be completed.</span></span>
    - <span data-ttu-id="05511-216">**Rozwiązanie krótkoterminowe** — należy zaznaczyć to pole wyboru, jeśli akcja korekcyjna koryguje niezgodność tylko przez krótki czas.</span><span class="sxs-lookup"><span data-stu-id="05511-216">**Short term solution** – Select this check box if the corrective action corrects the nonconformance only for a short time.</span></span>

1. <span data-ttu-id="05511-217">Zamknij strony.</span><span class="sxs-lookup"><span data-stu-id="05511-217">Close the pages.</span></span>

## <a name="mark-a-correction-as-completed"></a><span data-ttu-id="05511-218">Oznaczanie korekty jako zakończonej</span><span class="sxs-lookup"><span data-stu-id="05511-218">Mark a correction as completed</span></span>

<span data-ttu-id="05511-219">Aby oznaczyć korektę niezgodności jako zakończoną, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="05511-219">To mark a nonconformance correction as completed, follow these steps.</span></span>

1. <span data-ttu-id="05511-220">Wybierz kolejno opcje **Zarządzanie zapasami \> Zadania okresowe \> Zarządzanie jakością \> Niezgodności**.</span><span class="sxs-lookup"><span data-stu-id="05511-220">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="05511-221">Na liście zaznacz niezgodność, którą chcesz zaktualizować.</span><span class="sxs-lookup"><span data-stu-id="05511-221">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="05511-222">Korektę można dodać tylko do zatwierdzonych niezgodności.</span><span class="sxs-lookup"><span data-stu-id="05511-222">You can add a correction only to nonconformances that are approved.</span></span>

1. <span data-ttu-id="05511-223">W okienku akcji wybierz opcję **Korekty**.</span><span class="sxs-lookup"><span data-stu-id="05511-223">On the Action Pane, select **Corrections**.</span></span>
1. <span data-ttu-id="05511-224">Na stronie **Korekty** w siatce zaznacz korektę, którą chcesz oznaczyć jako zakończoną.</span><span class="sxs-lookup"><span data-stu-id="05511-224">On the **Corrections** page, in the grid, select the correction that you want to mark as completed.</span></span>
1. <span data-ttu-id="05511-225">W okienku akcji wybierz opcję **Oznacz jako ukończone**.</span><span class="sxs-lookup"><span data-stu-id="05511-225">On the Action Pane, select **Mark complete**.</span></span>
1. <span data-ttu-id="05511-226">Zostanie wyświetlony monit o potwierdzenie wyboru.</span><span class="sxs-lookup"><span data-stu-id="05511-226">You're prompted to confirm your selection.</span></span> <span data-ttu-id="05511-227">Wybierz przycisk **OK**, aby kontynuować.</span><span class="sxs-lookup"><span data-stu-id="05511-227">Select **OK** to continue.</span></span> <span data-ttu-id="05511-228">W polu **Data i godzina zakończenia** jest ustawiona bieżąca data i godzina, a pole wyboru **Zakończono** jest zaznaczone.</span><span class="sxs-lookup"><span data-stu-id="05511-228">The **Completion date and time** field is set to the current date and time, and the **Completed** check box is selected.</span></span>
1. <span data-ttu-id="05511-229">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="05511-229">Close the page.</span></span>

## <a name="reopen-a-completed-correction"></a><span data-ttu-id="05511-230">Ponowne otwieranie zakończonej korekty</span><span class="sxs-lookup"><span data-stu-id="05511-230">Reopen a completed correction</span></span>

<span data-ttu-id="05511-231">Aby ponownie otworzyć zakończoną korektę, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="05511-231">To reopen a completed correction, follow these steps.</span></span>

1. <span data-ttu-id="05511-232">Wybierz kolejno opcje **Zarządzanie zapasami \> Zadania okresowe \> Zarządzanie jakością \> Niezgodności**.</span><span class="sxs-lookup"><span data-stu-id="05511-232">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="05511-233">Na liście zaznacz niezgodność, którą chcesz zaktualizować.</span><span class="sxs-lookup"><span data-stu-id="05511-233">In the list, select the nonconformance that you want to update.</span></span>
1. <span data-ttu-id="05511-234">W okienku akcji wybierz opcję **Korekty**.</span><span class="sxs-lookup"><span data-stu-id="05511-234">On the Action pane, select **Corrections**.</span></span>
1. <span data-ttu-id="05511-235">Na stronie **Korekty** w siatce zaznacz korektę, którą chcesz ponownie otworzyć.</span><span class="sxs-lookup"><span data-stu-id="05511-235">On the **Corrections** page, in the grid, select the correction that you want to reopen.</span></span>
1. <span data-ttu-id="05511-236">W okienku akcji kliknij przycisk **Otwórz ponownie**.</span><span class="sxs-lookup"><span data-stu-id="05511-236">On the Action Pane, select **Reopen**.</span></span>
1. <span data-ttu-id="05511-237">Zostanie wyświetlony monit o potwierdzenie wyboru.</span><span class="sxs-lookup"><span data-stu-id="05511-237">You're prompted to confirm your selection.</span></span> <span data-ttu-id="05511-238">Wybierz przycisk **OK**, aby kontynuować.</span><span class="sxs-lookup"><span data-stu-id="05511-238">Select **OK** to continue.</span></span> <span data-ttu-id="05511-239">Zawartość pola **Data i godzina ukończenia** zostanie wyczyszczona, a zaznaczenie pola wyboru **Zakończone** zostanie usunięte.</span><span class="sxs-lookup"><span data-stu-id="05511-239">The value is cleared from the **Completion date and time** field, and the **Completed** check box is cleared.</span></span>
1. <span data-ttu-id="05511-240">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="05511-240">Close the page.</span></span>

<span data-ttu-id="05511-241">Teraz możesz dokonać dodatkowych edycji lub aktualizacji korekty.</span><span class="sxs-lookup"><span data-stu-id="05511-241">You can now make additional edits or updates to the correction.</span></span> <span data-ttu-id="05511-242">Po zakończeniu można ponownie oznaczyć korektę jako zakończoną.</span><span class="sxs-lookup"><span data-stu-id="05511-242">When you've finished, you can mark the correction as completed again.</span></span>

## <a name="close-a-nonconformance"></a><span data-ttu-id="05511-243">Zamykanie rekordu niezgodności</span><span class="sxs-lookup"><span data-stu-id="05511-243">Close a nonconformance</span></span>

<span data-ttu-id="05511-244">Aby zamknąć niezgodność, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="05511-244">To close a nonconformance, follow these steps.</span></span>

1. <span data-ttu-id="05511-245">Wybierz kolejno opcje **Zarządzanie zapasami \> Zadania okresowe \> Zarządzanie jakością \> Zlecenia kontroli jakości**.</span><span class="sxs-lookup"><span data-stu-id="05511-245">Go to **Inventory management \> Periodic tasks \> Quality management \> Quality orders**.</span></span>
1. <span data-ttu-id="05511-246">Wybierz zlecenie kontroli jakości w siatce.</span><span class="sxs-lookup"><span data-stu-id="05511-246">Select a quality order in the grid.</span></span>
1. <span data-ttu-id="05511-247">W okienku akcji wybierz **Zapytania \> Niezgodności**.</span><span class="sxs-lookup"><span data-stu-id="05511-247">On the Action Pane, select **Inquiries \> Non conformances**.</span></span>
1. <span data-ttu-id="05511-248">Na stronie **Niezgodności** zaznacz w siatce docelową niezgodność.</span><span class="sxs-lookup"><span data-stu-id="05511-248">On the **Non conformances** page, select the target nonconformance in the grid.</span></span>
1. <span data-ttu-id="05511-249">W okienku akcji wybierz **Funkcje \> Zamknij niezgodność**.</span><span class="sxs-lookup"><span data-stu-id="05511-249">On the Action Pane, select **Functions \> Close non conformance**.</span></span>
1. <span data-ttu-id="05511-250">Zostanie wyświetlony monit o potwierdzenie wyboru.</span><span class="sxs-lookup"><span data-stu-id="05511-250">You're prompted to confirm your selection.</span></span> <span data-ttu-id="05511-251">Wybierz przycisk **Tak**, aby kontynuować.</span><span class="sxs-lookup"><span data-stu-id="05511-251">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="05511-252">Zamknij strony.</span><span class="sxs-lookup"><span data-stu-id="05511-252">Close the pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="05511-253">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="05511-253">Additional resources</span></span>

- [<span data-ttu-id="05511-254">Omówienie zarządzanie jakością</span><span class="sxs-lookup"><span data-stu-id="05511-254">Quality management overview</span></span>](../quality-management-processes.md)
- [<span data-ttu-id="05511-255">Włączanie zarządzania kontrolą jakości i niezgodnością</span><span class="sxs-lookup"><span data-stu-id="05511-255">Enable quality and nonconformance management</span></span>](../enable-quality-management.md)
- [<span data-ttu-id="05511-256">Pracownicy odpowiedzialni za zatwierdzanie niezgodności</span><span class="sxs-lookup"><span data-stu-id="05511-256">Workers responsible for approving nonconformances</span></span>](../quality-responsible-workers.md)
- [<span data-ttu-id="05511-257">Strefy kwarantanny niezgodności</span><span class="sxs-lookup"><span data-stu-id="05511-257">Quarantine zones for nonconformances</span></span>](../quality-quarantine-zones.md)
- [<span data-ttu-id="05511-258">Typy diagnostyki niezgodności</span><span class="sxs-lookup"><span data-stu-id="05511-258">Diagnostic types for nonconformances</span></span>](../quality-diagnostic-types.md)
- [<span data-ttu-id="05511-259">Opłaty związane z kontrolą jakości dla niezgodności</span><span class="sxs-lookup"><span data-stu-id="05511-259">Quality charges for nonconformances</span></span>](../quality-charges.md)
- [<span data-ttu-id="05511-260">Operacje dotyczące niezgodności</span><span class="sxs-lookup"><span data-stu-id="05511-260">Operations for nonconformances</span></span>](../quality-operations.md)
- [<span data-ttu-id="05511-261">Zarządzanie jakością dla procesów magazynowych</span><span class="sxs-lookup"><span data-stu-id="05511-261">Quality management for warehouse processes</span></span>](../quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
