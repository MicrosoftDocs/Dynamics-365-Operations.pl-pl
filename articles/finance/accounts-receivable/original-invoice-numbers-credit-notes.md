---
title: Odwołania do oryginalnych faktur w fakturach korygujących
description: W tym temacie wyjaśniono, jak skonfigurować i wydrukować numery oryginalnych faktur w powiązanych fakturach korygujących.
author: ilkond
manager: AnnBe
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 04a4fc96cb7de60052b17e36c33ad5d5be322be4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5207358"
---
# <a name="references-to-original-invoices-in-credit-notes"></a><span data-ttu-id="cd5f6-103">Odwołania do oryginalnych faktur w fakturach korygujących</span><span class="sxs-lookup"><span data-stu-id="cd5f6-103">References to original invoices in credit notes</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="cd5f6-104">W niektórych krajach i regionach istnieje wymóg prawny, aby wydrukowane noty kredytowe zawierały odniesienia do oryginalnych faktur.</span><span class="sxs-lookup"><span data-stu-id="cd5f6-104">In some countries and regions, there is a legal requirement that printed credit notes include references to the original invoices.</span></span> <span data-ttu-id="cd5f6-105">W tym temacie wyjaśniono, jak skonfigurować i wydrukować numery oryginalnych faktur w powiązanych fakturach korygujących.</span><span class="sxs-lookup"><span data-stu-id="cd5f6-105">This topic explains how to set up and print the original invoice numbers in related credit notes.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cd5f6-106">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="cd5f6-106">Prerequisites</span></span>

- <span data-ttu-id="cd5f6-107">W obszarze roboczym **Zarządzanie funkcjami** włącz funkcję **Układ faktur kredytowych dla raportów faktur sprzedaży i projektów**.</span><span class="sxs-lookup"><span data-stu-id="cd5f6-107">In the **Feature management** workspace, turn on the **Credit invoicing layout for sales and project invoice reports** feature.</span></span> <span data-ttu-id="cd5f6-108">Aby uzyskać więcej informacji, zapoznaj się z tematem [Zarządzanie funkcjami — omówienie](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cd5f6-108">For more information, see [Feature management overview](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span></span>
- <span data-ttu-id="cd5f6-109">Formaty do drukowania wymaganych dokumentów muszą być skonfigurowane w zarządzaniu drukowaniem.</span><span class="sxs-lookup"><span data-stu-id="cd5f6-109">The printable formats of the required documents must be configured in Print management.</span></span>

<span data-ttu-id="cd5f6-110">Funkcje opisane w tym temacie dotyczą następujących dokumentów:</span><span class="sxs-lookup"><span data-stu-id="cd5f6-110">The functionality that is described in this topic applies to the following documents:</span></span>

<span data-ttu-id="cd5f6-111">**Rozrachunki z odbiorcami**</span><span class="sxs-lookup"><span data-stu-id="cd5f6-111">**Accounts receivable**</span></span>

- <span data-ttu-id="cd5f6-112">Niezależna faktura korygująca</span><span class="sxs-lookup"><span data-stu-id="cd5f6-112">Free text credit note</span></span>
- <span data-ttu-id="cd5f6-113">Odbiorca faktury korygującej</span><span class="sxs-lookup"><span data-stu-id="cd5f6-113">Customer credit note</span></span>

<span data-ttu-id="cd5f6-114">**Zarządzanie projektami i ich księgowanie**</span><span class="sxs-lookup"><span data-stu-id="cd5f6-114">**Project management and accounting**</span></span>

- <span data-ttu-id="cd5f6-115">Projektowanie faktury korygującej</span><span class="sxs-lookup"><span data-stu-id="cd5f6-115">Project credit note</span></span>

## <a name="configure-accounts-receivable-parameters"></a><span data-ttu-id="cd5f6-116">Konfiguruj Parametry modułu rozrachunków z odbiorcami</span><span class="sxs-lookup"><span data-stu-id="cd5f6-116">Configure Accounts receivable parameters</span></span>

<span data-ttu-id="cd5f6-117">Aby ustawić parametr sterujący tym, czy odwołania do oryginalnych faktur mają być drukowane w powiązanych fakturach korygują, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="cd5f6-117">Follow these steps to set the parameter that controls whether references to the original invoices are printed in related credit notes.</span></span>

1. <span data-ttu-id="cd5f6-118">Wybierz kolejno pozycje **Rozrachunki z odbiorcami** \> **Ustawienia** \> **Parametry modułu rozrachunków z odbiorcami**.</span><span class="sxs-lookup"><span data-stu-id="cd5f6-118">Go to **Accounts receivable** \> **Setup** \> **Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="cd5f6-119">Na karcie **Aktualizacje** na skróconej karcie **Faktura** ustaw opcję **Zastosuj układ faktur kredytowych w raportach faktur sprzedaży i projektów** na wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="cd5f6-119">On the **Updates** tab, on the **Invoice** FastTab, set the **Apply the credit invoicing layout into sales and project invoice reports** option to **Yes**.</span></span>

![Konfiguruj Parametry modułu rozrachunków z odbiorcami](media/original-invoice-number-in-credit-note.jpg)

## <a name="define-references-to-original-invoices"></a><span data-ttu-id="cd5f6-121">Zdefiniuj odniesienia do oryginalnych faktur</span><span class="sxs-lookup"><span data-stu-id="cd5f6-121">Define references to original invoices</span></span>

<span data-ttu-id="cd5f6-122">Poniższe procedury służą do definiowania odniesień do oryginalnych faktur na podstawie typu dokumentu.</span><span class="sxs-lookup"><span data-stu-id="cd5f6-122">Use the following procedures to define references to original invoices, based on the document type.</span></span>

### <a name="free-text-credit-note"></a><span data-ttu-id="cd5f6-123">Niezależna faktura korygująca</span><span class="sxs-lookup"><span data-stu-id="cd5f6-123">Free text credit note</span></span>

1. <span data-ttu-id="cd5f6-124">Wybierz kolejno opcje **Rozrachunki z odbiorcami** \> **Faktury** \> **Wszystkie faktury niezależne**.</span><span class="sxs-lookup"><span data-stu-id="cd5f6-124">Go to **Accounts receivable** \> **Invoices** \> **All free text invoices**.</span></span>
2. <span data-ttu-id="cd5f6-125">Utwórz nową notę kredytową lub wybierz istniejącą notę kredytową.</span><span class="sxs-lookup"><span data-stu-id="cd5f6-125">Create a new credit note, or select an existing credit note.</span></span>
3. <span data-ttu-id="cd5f6-126">Otwórz fakturę.</span><span class="sxs-lookup"><span data-stu-id="cd5f6-126">Open the invoice.</span></span>
4. <span data-ttu-id="cd5f6-127">W okienku akcji na karcie **Faktura** w grupie **Funkcje** wybierz **Księgowanie fakturowania po stronie kredytowej**.</span><span class="sxs-lookup"><span data-stu-id="cd5f6-127">On the Action Pane, on the **Invoice** tab, in the **Functions** group, select **Credit invoicing**.</span></span>
5. <span data-ttu-id="cd5f6-128">Wprowadź odwołanie do oryginalnej faktury i wybierz przyczynę korekty.</span><span class="sxs-lookup"><span data-stu-id="cd5f6-128">Enter the reference to the original invoice, and select the reason for the correction.</span></span>

![Definiowanie odwołania dla faktury elektronicznej](media/reference-original-invoice-FTI.jpg)

### <a name="customer-credit-note"></a><span data-ttu-id="cd5f6-130">Odbiorca faktury korygującej</span><span class="sxs-lookup"><span data-stu-id="cd5f6-130">Customer credit note</span></span>

1. <span data-ttu-id="cd5f6-131">Przejdź do pozycji **Rozrachunki z odbiorcami** \> **Zamówienia** \> **Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="cd5f6-131">Go to **Accounts receivable** \> **Orders** \> **All sales orders**.</span></span>
2. <span data-ttu-id="cd5f6-132">Wybierz i otwórz zafakturowane zamówienie sprzedaży, które musi zostać skorygowane.</span><span class="sxs-lookup"><span data-stu-id="cd5f6-132">Select and open the invoiced sales order that must be corrected.</span></span>
3. <span data-ttu-id="cd5f6-133">W okienku akcji na karcie **Sprzedaj** w grupie **Nota kredytowa** wybierz **Nota kredytowa**.</span><span class="sxs-lookup"><span data-stu-id="cd5f6-133">On the Action Pane, on the **Sell** tab, in the **Credit note** group, select **Credit note**.</span></span>
4. <span data-ttu-id="cd5f6-134">Wpisz powód korekty.</span><span class="sxs-lookup"><span data-stu-id="cd5f6-134">Enter the reason for the correction.</span></span> <span data-ttu-id="cd5f6-135">Automatycznie zostanie utworzone odwołanie do oryginalnej faktury.</span><span class="sxs-lookup"><span data-stu-id="cd5f6-135">The reference to the original invoice is automatically established.</span></span>

![Definiowanie odwołania do zamówienia sprzedaży](media/reference-original-invoice-SO.jpg)

### <a name="project-credit-note"></a><span data-ttu-id="cd5f6-137">Projektowanie faktury korygującej</span><span class="sxs-lookup"><span data-stu-id="cd5f6-137">Project credit note</span></span>

1. <span data-ttu-id="cd5f6-138">Wybierz kolejno opcje **Zarządzanie projektami i ich księgowanie** \> **Faktury projektu** \> **Faktury projektu**.</span><span class="sxs-lookup"><span data-stu-id="cd5f6-138">Go to **Project management and accounting** \> **Project invoices** \> **Project invoices**.</span></span>
2. <span data-ttu-id="cd5f6-139">Wybierz i otwórz fakturę za projekt, która musi zostać poprawiona.</span><span class="sxs-lookup"><span data-stu-id="cd5f6-139">Select and open the project invoice that must be corrected.</span></span>
3. <span data-ttu-id="cd5f6-140">W okienku akcji na karcie **Faktura projektu** w grupie **Funkcje** wybierz **Wybierz do faktury korygującej**.</span><span class="sxs-lookup"><span data-stu-id="cd5f6-140">On the Action Pane, on the **Project invoice** tab, in the **Functions** group, select **Select for credit note**.</span></span>
4. <span data-ttu-id="cd5f6-141">Wybierz **Księgowanie fakturowania po stronie kredytowej**.</span><span class="sxs-lookup"><span data-stu-id="cd5f6-141">Select **Credit invoicing**.</span></span>
5. <span data-ttu-id="cd5f6-142">Wpisz powód korekty.</span><span class="sxs-lookup"><span data-stu-id="cd5f6-142">Enter the reason for the correction.</span></span> <span data-ttu-id="cd5f6-143">Automatycznie zostanie utworzone odwołanie do oryginalnej faktury.</span><span class="sxs-lookup"><span data-stu-id="cd5f6-143">The reference to the original invoice is automatically established.</span></span>

![Definiowanie odwołania dla faktury do projektu](media/reference-original-invoice-project.jpg)

## <a name="printing-credit-notes"></a><span data-ttu-id="cd5f6-145">Drukowanie faktur korygujących</span><span class="sxs-lookup"><span data-stu-id="cd5f6-145">Printing credit notes</span></span>

<span data-ttu-id="cd5f6-146">Gdy drukujesz dowolny tekst, noty kredytowe klienta i projektu, będą one zawierać odniesienie do oryginalnej faktury i powód korekty.</span><span class="sxs-lookup"><span data-stu-id="cd5f6-146">When you print free text, customer, and project credit notes, they will include the reference to the original invoice and the correction reason.</span></span>

![Drukowanie faktury korygującej](media/credit-note-FTI.jpg)

> [!NOTE]
> <span data-ttu-id="cd5f6-148">Upewnij się, że formaty dokumentów do druku są poprawnie skonfigurowane, przy założeniu, że zostaną wydrukowane odniesienia do oryginalnych faktur.</span><span class="sxs-lookup"><span data-stu-id="cd5f6-148">Make sure that the printable formats of the documents are correctly configured, on the assumption that references to original invoices will be printed.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]