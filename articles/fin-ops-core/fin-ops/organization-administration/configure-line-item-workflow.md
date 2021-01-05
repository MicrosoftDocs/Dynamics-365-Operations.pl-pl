---
title: Konfigurowanie przepływów pracy dla pozycji w wierszach
description: W tym temacie wyjaśniono sposób konfigurowania elementu przepływu pracy dla pozycji w wierszu.
author: ChrisGarty
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195833
ms.assetid: 3237347e-71d5-4569-bc9a-0d0fc9410b78
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a72719c9fd03f73b69b558fc0f08eed91ea94ee1
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/08/2020
ms.locfileid: "4694366"
---
# <a name="configure-line-item-workflows"></a><span data-ttu-id="55954-103">Konfigurowanie przepływów pracy dla pozycji w wierszach</span><span class="sxs-lookup"><span data-stu-id="55954-103">Configure line-item workflows</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="55954-104">W tym temacie wyjaśniono sposób konfigurowania elementu przepływu pracy dla pozycji w wierszu.</span><span class="sxs-lookup"><span data-stu-id="55954-104">This topic explains how to configure a line-item workflow element.</span></span>

<span data-ttu-id="55954-105">Aby skonfigurować element przepływu pracy dla pozycji w wierszu, w edytorze przepływu pracy kliknij element prawym przyciskiem myszy i wybierz polecenie **Właściwości**, a zostanie otwarta strona **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="55954-105">To configure a line-item workflow element, in the workflow editor, right-click the element, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="55954-106">Następnie użyj poniższych procedur, aby skonfigurować właściwości elementu przepływu pracy dla pozycji w wierszu.</span><span class="sxs-lookup"><span data-stu-id="55954-106">Then use the following procedures to configure the properties of the line-item workflow element.</span></span>

## <a name="name-the-line-item-workflow-element"></a><span data-ttu-id="55954-107">Nazywanie elementu przepływu pracy dla pozycji w wierszu</span><span class="sxs-lookup"><span data-stu-id="55954-107">Name the line-item workflow element</span></span>

<span data-ttu-id="55954-108">Należy wykonać następujące kroki, aby nadać nazwę elementowi przepływu pracy dla pozycji w wierszu.</span><span class="sxs-lookup"><span data-stu-id="55954-108">Follow these steps to enter a name for the line-item workflow element.</span></span>

1. <span data-ttu-id="55954-109">W lewym okienku kliknij przycisk **Ustawienia podstawowe**.</span><span class="sxs-lookup"><span data-stu-id="55954-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="55954-110">W polu **Nazwa** wprowadź unikatową nazwę elementu przepływu pracy dla pozycji w wierszu.</span><span class="sxs-lookup"><span data-stu-id="55954-110">In the **Name** field, enter a unique name for the line-item workflow element.</span></span>

## <a name="specify-whether-the-same-workflow-is-used-to-process-all-line-items"></a><span data-ttu-id="55954-111">Określanie, czy ten sam przepływ pracy ma być stosowany do przetwarzania wszystkich pozycji w wierszach</span><span class="sxs-lookup"><span data-stu-id="55954-111">Specify whether the same workflow is used to process all line items</span></span>

<span data-ttu-id="55954-112">Wykonaj następujące kroki, aby określić, czy ten sam przepływ pracy będzie używany do przetwarzania wszystkich pozycji w wierszach w dokumencie.</span><span class="sxs-lookup"><span data-stu-id="55954-112">Follow these steps to specify whether the same workflow is used to process all the line items on a document.</span></span>

1. <span data-ttu-id="55954-113">W lewym okienku kliknij przycisk **Ustawienia podstawowe**.</span><span class="sxs-lookup"><span data-stu-id="55954-113">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="55954-114">Jeśli ten sam przepływ pracy ma przetwarzać wszystkie pozycje w wierszach w dokumencie, kliknij opcje **Wywołaj pojedynczy przepływ pracy dla wszystkich elementów wiersza**.</span><span class="sxs-lookup"><span data-stu-id="55954-114">If the same workflow should process all the line items on a document, click **Invoke a single workflow for all line-items**.</span></span> <span data-ttu-id="55954-115">Następnie wybierz przepływ pracy, który ma być stosowany do pozycji w wierszach.</span><span class="sxs-lookup"><span data-stu-id="55954-115">Then select the workflow to use to process the line items.</span></span>
3. <span data-ttu-id="55954-116">Jeśli określony przepływ pracy ma przetwarzać pozycje w wierszach spełniające określony zbiór warunków, kliknij opcję **Wywołaj przepływ pracy dla wszystkich elementów wiersza**.</span><span class="sxs-lookup"><span data-stu-id="55954-116">If a specific workflow should process line items that meet a specific set of conditions, click **Invoke a workflow for each line-item**.</span></span> <span data-ttu-id="55954-117">Następnie wykonaj następujące czynności, aby zdefiniować zestaw warunków:</span><span class="sxs-lookup"><span data-stu-id="55954-117">Then follow these steps to define the set of conditions:</span></span>

    1. <span data-ttu-id="55954-118">Kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="55954-118">Click **Add**.</span></span>
    2. <span data-ttu-id="55954-119">Zaznacz warunek w tabeli.</span><span class="sxs-lookup"><span data-stu-id="55954-119">Select the condition in the table.</span></span>
    3. <span data-ttu-id="55954-120">Na karcie **Nazwa warunku** nadaj nazwę zestawowi warunków, który definiujesz.</span><span class="sxs-lookup"><span data-stu-id="55954-120">On the **Condition name** tab, enter a name for the set of conditions that you're defining.</span></span>
    4. <span data-ttu-id="55954-121">Kliknij przycisk **Dodaj warunek** i wprowadź warunek.</span><span class="sxs-lookup"><span data-stu-id="55954-121">Click **Add condition** to enter a condition.</span></span>
    5. <span data-ttu-id="55954-122">Wprowadź wszelkie wymagane dodatkowe warunki.</span><span class="sxs-lookup"><span data-stu-id="55954-122">Enter any additional conditions that are required.</span></span>
    6. <span data-ttu-id="55954-123">Aby sprawdzić, czy wprowadzony zbiór warunków jest poprawnie skonfigurowany, kliknij przycisk **Testuj**.</span><span class="sxs-lookup"><span data-stu-id="55954-123">To verify that the set of conditions that you entered is configured correctly, click **Test**.</span></span> <span data-ttu-id="55954-124">Na stronie **Warunek testowy przepływu pracy** w obszarze **Sprawdź poprawność warunku** wybierz rekord i kliknij przycisk **Testuj**.</span><span class="sxs-lookup"><span data-stu-id="55954-124">On the **Test workflow condition** page, in the **Validate condition** area, select a record, and then click **Test**.</span></span> <span data-ttu-id="55954-125">System oszacuje rekord i określi, czy rekord spełnia określone warunki.</span><span class="sxs-lookup"><span data-stu-id="55954-125">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span> <span data-ttu-id="55954-126">Kliknij przycisk **OK** lub **Anuluj**, aby powrócić do strony **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="55954-126">Click **OK** or **Cancel** to return to the **Properties** page.</span></span>

    <span data-ttu-id="55954-127">Na karcie **Przepływy pracy** wybierz przepływ pracy, który ma być używany do przetwarzania pozycji w wierszach spełniających utworzony zbiór warunków.</span><span class="sxs-lookup"><span data-stu-id="55954-127">On the **Workflow** tab, select the workflow select the workflow to use to process line items that meet the set of conditions that you defined.</span></span>
