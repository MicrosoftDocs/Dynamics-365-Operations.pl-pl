---
title: Tworzenie zaawansowanych umów dla rozliczeń na podstawie stanu realizacji
description: W tym temacie opisano sposób tworzenia umów dotyczących projektów, dzięki czemu można generować faktury dla odbiorców na podstawie procentu ukończonej pracy.
author: RadhikaRS
manager: AnnBe
ms.date: 03/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 90cae104d0abad909606ef6a0e0c45ed95e74de2
ms.sourcegitcommit: dfef2faf881b2db1bd0f016df36e2b838105312b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/22/2020
ms.locfileid: "3282843"
---
# <a name="create-advanced-contracts-for-billing-based-on-progress"></a><span data-ttu-id="00d41-103">Tworzenie zaawansowanych umów dla rozliczeń na podstawie stanu realizacji</span><span class="sxs-lookup"><span data-stu-id="00d41-103">Create advanced contracts for billing based on progress</span></span>
[!include [banner](../includes/banner.md)]

<span data-ttu-id="00d41-104">W tym temacie opisano sposób tworzenia umów dotyczących projektów, dzięki czemu można tworzyć faktury dla odbiorców na podstawie procentu ukończonej pracy.</span><span class="sxs-lookup"><span data-stu-id="00d41-104">This topic explains how to create project contracts so that you can create invoices for customers, based on a percentage of completed work.</span></span> <span data-ttu-id="00d41-105">Kwoty faktur są obliczane automatycznie dla kategorii budżetu pracy, który skonfigurowano dla projektu.</span><span class="sxs-lookup"><span data-stu-id="00d41-105">Invoice amounts are automatically calculated for the budget categories of work that you set up for a project.</span></span> <span data-ttu-id="00d41-106">Informacje o czasach faktur są skonfigurowane podczas negocjowania umowy dotyczącej projektu z odbiorcą.</span><span class="sxs-lookup"><span data-stu-id="00d41-106">The invoice timing is set when you negotiate the project contract with the customer.</span></span>

<span data-ttu-id="00d41-107">Użyj tych procedur w tym temacie, aby skonfigurować umowę, skojarzony projektu i reguły fakturowania używane do obliczania kwot faktury dla kategorii budżetu, które należy utworzyć dla projektu.</span><span class="sxs-lookup"><span data-stu-id="00d41-107">Use the procedures in this topic to set up a contract, an associated project, and the billing rules that calculate invoice amounts for the budget categories of work that you set up for the project.</span></span>

<span data-ttu-id="00d41-108">Po utworzeniu umowy i projektu można utworzyć szczegóły projektu.</span><span class="sxs-lookup"><span data-stu-id="00d41-108">After you've created the contract and the project, you can set up the details of the project.</span></span> <span data-ttu-id="00d41-109">Na przykład można określić działania i przydzielić pracowników do projektu.</span><span class="sxs-lookup"><span data-stu-id="00d41-109">For example, you can define activities and assign workers to the project.</span></span>

## <a name="example"></a><span data-ttu-id="00d41-110">Przykład</span><span class="sxs-lookup"><span data-stu-id="00d41-110">Example</span></span>

<span data-ttu-id="00d41-111">Organizacja jest firmą zajmującą się tworzeniem oprogramowania.</span><span class="sxs-lookup"><span data-stu-id="00d41-111">Your organization is a software development firm.</span></span> <span data-ttu-id="00d41-112">Użytkownik godzi się na opracowanie pakietu do księgowania listy płac dla odbiorcy za 20 000 dolarów amerykańskich USD.</span><span class="sxs-lookup"><span data-stu-id="00d41-112">You agree to develop a payroll accounting package for a customer for a total fee of 20,000 US dollars (USD).</span></span> <span data-ttu-id="00d41-113">Organizacja zgadza się wysłać fakturę odbiorcy po ukończeniu określonych procentowo części pracy nad tym projektem.</span><span class="sxs-lookup"><span data-stu-id="00d41-113">Your organization agrees to invoice the customer as you complete specific percentages of the project.</span></span> <span data-ttu-id="00d41-114">Istnieje możliwość skonfigurowania następujących kategorii projektu dla pracy, dzięki czemu można ich używać w procesie rozliczania:</span><span class="sxs-lookup"><span data-stu-id="00d41-114">You set up the following project categories for the work, so that you can use them in the billing process:</span></span>

- <span data-ttu-id="00d41-115">Konsultacje</span><span class="sxs-lookup"><span data-stu-id="00d41-115">Consulting</span></span>
- <span data-ttu-id="00d41-116">Projekt</span><span class="sxs-lookup"><span data-stu-id="00d41-116">Design</span></span>
- <span data-ttu-id="00d41-117">Instalacja</span><span class="sxs-lookup"><span data-stu-id="00d41-117">Installation</span></span>

<span data-ttu-id="00d41-118">Należy zdefiniować reguły fakturowania, które obliczą automatycznie kwoty faktury dla procentu pracy projektu dla poszczególnych kategorii.</span><span class="sxs-lookup"><span data-stu-id="00d41-118">You also set up billing rules that automatically calculate the invoice amounts for the percentage of project work that is completed in each category.</span></span>

<span data-ttu-id="00d41-119">Menedżer budżetu tworzy budżetu dla kategorii projektu.</span><span class="sxs-lookup"><span data-stu-id="00d41-119">The budget manager creates a budget for the project categories.</span></span> <span data-ttu-id="00d41-120">Wielkość ukończonej już pracy jest obliczana automatycznie jako procent rzeczywistej pracy w porównaniu w wielkością budżetu.</span><span class="sxs-lookup"><span data-stu-id="00d41-120">The amount of completed work is automatically calculated as a percentage of actual work in comparison to the budgeted amounts.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="00d41-121">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="00d41-121">Prerequisites</span></span>

<span data-ttu-id="00d41-122">Przed utworzeniem projektu, w którym są używane reguły fakturowania, należy skonfigurować sekwencje numerów dla reguł fakturowania oraz arkusz opłat używany do księgowania rozliczeń w toku.</span><span class="sxs-lookup"><span data-stu-id="00d41-122">Before you create a project that uses billing rules, you must set up the number sequences for billing rules and a fee journal that is used to post progress billings.</span></span>

1. <span data-ttu-id="00d41-123">Wybierz kolejno opcje **Zarządzanie projektami i ich księgowanie** \> **Ustawienia** \> **Parametry modułu Zarządzanie projektami i ich księgowanie**.</span><span class="sxs-lookup"><span data-stu-id="00d41-123">Go to **Project management and accounting** \> **Setup** \> **Project management and accounting parameters**.</span></span>
2. <span data-ttu-id="00d41-124">Na stronie **Parametry modułu Zarządzanie projektami i ich księgowanie** na karcie **Numery kolejne** skonfiguruj sekwencję numerów, która ma być używana podczas tworzenia reguł fakturowania.</span><span class="sxs-lookup"><span data-stu-id="00d41-124">On the **Project management and accounting parameters** page, on the **Number sequences** tab, set up the number sequence that you want to use when billing rules are created.</span></span>
3. <span data-ttu-id="00d41-125">Przejdź do **Zarządzanie projektami i ich księgowanie** \> **Arkusze** \> **Opłata**.</span><span class="sxs-lookup"><span data-stu-id="00d41-125">Go to **Project management and accounting** \> **Journals** \> **Fee**.</span></span>
4. <span data-ttu-id="00d41-126">Na stronie **Arkusz opłat** wybierz opcję **Nowy** i wprowadź nazwę arkusza.</span><span class="sxs-lookup"><span data-stu-id="00d41-126">On the **Fee journal** page, select **New**, and enter the journal name.</span></span>

## <a name="create-a-contract-for-progress-billings"></a><span data-ttu-id="00d41-127">Konfigurowanie umowy dla fakturowania uwarunkowanego stanem realizacji umowy</span><span class="sxs-lookup"><span data-stu-id="00d41-127">Create a contract for progress billings</span></span>

<span data-ttu-id="00d41-128">Ta procedura umożliwia tworzenie umowy dotyczącej projektu dla projektu o stałej cenie.</span><span class="sxs-lookup"><span data-stu-id="00d41-128">Use this procedure to create a project contract for a fixed-price project.</span></span> <span data-ttu-id="00d41-129">Tworzysz fakturę za projekt, gdy w projekcie wykonano określoną procentowo część pracy.</span><span class="sxs-lookup"><span data-stu-id="00d41-129">You create a project invoice when the work that is completed on the project reaches a specified percentage.</span></span>

1. <span data-ttu-id="00d41-130">Wybierz kolejno opcje **Zarządzanie projektami i ich księgowanie** \> **Projekty** \> **Umowy dotyczące projektu**.</span><span class="sxs-lookup"><span data-stu-id="00d41-130">Go to **Project management and accounting** \> **Projects** \> **Project contracts**.</span></span>
2. <span data-ttu-id="00d41-131">Na stronie **Umowy dotyczące projektu** wybierz opcję **Nowa**.</span><span class="sxs-lookup"><span data-stu-id="00d41-131">On the **Project contracts** page, select **New**.</span></span>
3. <span data-ttu-id="00d41-132">W wyświetlonym oknie dialogowym **Nowa umowa dotycząca projektu** można ustawić następujące pola:</span><span class="sxs-lookup"><span data-stu-id="00d41-132">In the **New project contract** dialog box, set the following fields:</span></span>

    - <span data-ttu-id="00d41-133">**Imię i nazwisko**</span><span class="sxs-lookup"><span data-stu-id="00d41-133">**Name**</span></span>
    - <span data-ttu-id="00d41-134">**Typ finansowania**</span><span class="sxs-lookup"><span data-stu-id="00d41-134">**Funding type**</span></span>
    - <span data-ttu-id="00d41-135">**Źródło finansowania**</span><span class="sxs-lookup"><span data-stu-id="00d41-135">**Funding source**</span></span>
    - <span data-ttu-id="00d41-136">**Waluta sprzedaży** — domyślnie jest to waluta używana w fakturach dla odbiorcy, skojarzona z umową dotyczącą projektu.</span><span class="sxs-lookup"><span data-stu-id="00d41-136">**Sales currency** – By default, this currency is used for customer invoices that are associated with the project contract.</span></span> <span data-ttu-id="00d41-137">Możesz jednak zmienić walutę sprzedaży dla wybranej faktury dla odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="00d41-137">However, you can change the sales currency on a specific customer invoice.</span></span>

4. <span data-ttu-id="00d41-138">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="00d41-138">Select **OK**.</span></span> <span data-ttu-id="00d41-139">Informacje zostaną skopiowane do nagłówka strony **Umowy dotyczące projektu**.</span><span class="sxs-lookup"><span data-stu-id="00d41-139">The information is copied to the header of the **Project contracts** page.</span></span>
5. <span data-ttu-id="00d41-140">Na stronie **Umowy dotyczące projektu** wprowadź pozostałe wymagane informacje dotyczące projektu.</span><span class="sxs-lookup"><span data-stu-id="00d41-140">On the **Project contracts** page, fill in the rest of the required information for the project.</span></span>

## <a name="create-a-project-for-progress-billings"></a><span data-ttu-id="00d41-141">Konfigurowanie umowy dla fakturowania uwarunkowanego stanem realizacji umowy</span><span class="sxs-lookup"><span data-stu-id="00d41-141">Create a project for progress billings</span></span>

<span data-ttu-id="00d41-142">Wykonaj te kroki, aby stworzyć projekt oraz podprojekty skojarzone z umową dotyczącą projektu.</span><span class="sxs-lookup"><span data-stu-id="00d41-142">Follow these steps to create a project and any subprojects that are associated with a project contract.</span></span>

1. <span data-ttu-id="00d41-143">Wybierz kolejno opcje **Zarządzanie projektami i ich księgowanie** \> **Projekty** \> **Wszystkie projekty**.</span><span class="sxs-lookup"><span data-stu-id="00d41-143">Go to **Project management and accounting** \> **Projects** \> **All projects**.</span></span>
2. <span data-ttu-id="00d41-144">Na stronie **Wszystkie projekty** wybierz opcję **Nowe**.</span><span class="sxs-lookup"><span data-stu-id="00d41-144">On the **All projects** page, select **New**.</span></span>
3. <span data-ttu-id="00d41-145">W oknie dialogowym **Nowy projekt**, w polu **Typ projektu** wybierz opcję **Czas i materiały**.</span><span class="sxs-lookup"><span data-stu-id="00d41-145">In the **New project** dialog box, in the **Project type** field, select **Time and material**.</span></span>
4. <span data-ttu-id="00d41-146">Służy do wybierania grupy projektów.</span><span class="sxs-lookup"><span data-stu-id="00d41-146">Select a project group.</span></span> <span data-ttu-id="00d41-147">Grupa projektów definiuje informacje o księgowaniu dla projektów przypisanych do grupy.</span><span class="sxs-lookup"><span data-stu-id="00d41-147">A project group defines the posting information for the projects that are assigned to the group.</span></span>
5. <span data-ttu-id="00d41-148">Wybierz opcję **Utwórz projekt**.</span><span class="sxs-lookup"><span data-stu-id="00d41-148">Select **Create project**.</span></span>
6. <span data-ttu-id="00d41-149">Po utworzeniu projektu ustaw etap projektu **W toku**.</span><span class="sxs-lookup"><span data-stu-id="00d41-149">After the project is created, set the project stage to **In process**.</span></span>

## <a name="create-a-budget-for-a-project"></a><span data-ttu-id="00d41-150">Tworzenie budżetu dla projektu</span><span class="sxs-lookup"><span data-stu-id="00d41-150">Create a budget for a project</span></span>

<span data-ttu-id="00d41-151">Kategorie budżetu są używane celu automatycznego obliczania kwot faktur za wykonaną, procentowo określoną część pracy dla każdej kategorii.</span><span class="sxs-lookup"><span data-stu-id="00d41-151">Budget categories are used to automatically calculate the invoice amounts for the percentage of work that is completed for each category.</span></span> <span data-ttu-id="00d41-152">Aby utworzyć kategorie budżetu dla kosztów szacowanych, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="00d41-152">Follow these steps to create budget categories for the estimated costs.</span></span>

1. <span data-ttu-id="00d41-153">Wybierz kolejno opcje **Zarządzanie projektami i ich księgowanie** \> **Projekty** \> **Wszystkie projekty**.</span><span class="sxs-lookup"><span data-stu-id="00d41-153">Go to **Project management and accounting** \> **Projects** \> **All projects**.</span></span>
2. <span data-ttu-id="00d41-154">Na stronie **Wszystkie projekty** wybierz odpowiedni projekt i otwórz go.</span><span class="sxs-lookup"><span data-stu-id="00d41-154">On the **All projects** page, select and open the project that you want.</span></span>
3. <span data-ttu-id="00d41-155">Na stronie **Projekty** w okienku akcji, na karcie **Plan**, w grupie **Budżet** wybierz opcję **Budżet projektu**.</span><span class="sxs-lookup"><span data-stu-id="00d41-155">On the **Projects** page, on the Action Pane, on the **Plan** tab, in the **Budget** group, select **Project budget**.</span></span>
4. <span data-ttu-id="00d41-156">Na stronie **Budżet projektu** wprowadź szacowany koszt dla każdej kategorii w projekcie.</span><span class="sxs-lookup"><span data-stu-id="00d41-156">On the **Project budget** page, enter an estimated cost for each category in the project.</span></span>

## <a name="create-billing-rules-for-progress-billings"></a><span data-ttu-id="00d41-157">Umożliwia tworzenie reguł fakturowania uwarunkowanego stanem realizacji umowy</span><span class="sxs-lookup"><span data-stu-id="00d41-157">Create billing rules for progress billings</span></span>

1. <span data-ttu-id="00d41-158">Wybierz kolejno opcje **Zarządzanie projektami i ich księgowanie** \> **Projekty** \> **Umowy dotyczące projektu**.</span><span class="sxs-lookup"><span data-stu-id="00d41-158">Go to **Project management and accounting** \> **Projects** \> **Project contracts**.</span></span>
2. <span data-ttu-id="00d41-159">Na stronie **Umowy dotyczące projektu** wybierz opcję i otwórz umowę dotyczącą projektu.</span><span class="sxs-lookup"><span data-stu-id="00d41-159">On the **Project contracts** page, select and open a project contract.</span></span>
3. <span data-ttu-id="00d41-160">Na stronie umowa dotycząca projektu w skróconej karcie **Reguły fakturowania** wybierz pozycję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="00d41-160">On the project contract page, on the **Billing rules** FastTab, select **Add**.</span></span>
4. <span data-ttu-id="00d41-161">Na stronie **Reguła fakturowania** w polu **Typ wiersza** wybierz opcję **Postęp**.</span><span class="sxs-lookup"><span data-stu-id="00d41-161">On the **Billing rule** page, in the **Line type** field, select **Progress**.</span></span>
5. <span data-ttu-id="00d41-162">Na skróconej karcie **Szczegóły wiersza reguły fakturowania** wprowadź łączną wartość umowy w polu **Wartość umowy**.</span><span class="sxs-lookup"><span data-stu-id="00d41-162">On the **Billing rule line details** FastTab, in the **Contract value** field, enter the total value of the contract.</span></span>
6. <span data-ttu-id="00d41-163">W polu **Kategoria** wybierz kategorię, aby zaksięgować transakcję opłaty.</span><span class="sxs-lookup"><span data-stu-id="00d41-163">In the **Category** field, select the category to post the fee transaction to.</span></span>
7. <span data-ttu-id="00d41-164">W polu **Projekt** wybierz projekt lub zadanie, które korzysta z tej reguły rozliczeń.</span><span class="sxs-lookup"><span data-stu-id="00d41-164">In the **Project** field, select the project that uses this billing rule.</span></span>
8. <span data-ttu-id="00d41-165">Opcjonalne: Przypisz regułę fakturowania do dodatkowych projektów.</span><span class="sxs-lookup"><span data-stu-id="00d41-165">Optional: Assign the billing rule to additional projects.</span></span> <span data-ttu-id="00d41-166">Na skróconej karcie **Projekt**, w sekcji **Dostępne projekty** wybierz projekt, a następnie wybierz przycisk strzałka w prawo, aby dodać projekt do sekcji **Wybrane projekty**.</span><span class="sxs-lookup"><span data-stu-id="00d41-166">On the **Project** FastTab, in the **Available projects** section, select a project, and then select the right arrow button to add the project to the **Selected projects** section.</span></span>
9. <span data-ttu-id="00d41-167">Opcjonalne: Oblicz procent kwoty, jaka zostanie potrącona na zaliczki na podatek od płatności z faktury odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="00d41-167">Optional: Calculate the percentage amount that the customer withholds from payments on an invoice.</span></span> <span data-ttu-id="00d41-168">Na skróconej karcie **Warunki zatrzymywania płatności** wybierz źródło finansowania, a następnie w polu **Procent zatrzymania** wprowadź zatrzymywany procent.</span><span class="sxs-lookup"><span data-stu-id="00d41-168">On the **Payment retention terms** FastTab, select the funding source, and then, in the **Retention percentage** field, enter the retention percentage.</span></span>
10. <span data-ttu-id="00d41-169">Powtórz te kroki w celu utworzenia dodatkowych reguł fakturowania dla umowy dotyczącej projektu.</span><span class="sxs-lookup"><span data-stu-id="00d41-169">Repeat these steps to create additional billing rules for the project contract.</span></span>
