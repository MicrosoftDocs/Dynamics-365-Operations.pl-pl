---
title: Usprawnij model przewidywania (wersja zapoznawcza)
description: W tym temacie opisano funkcje, których można używać w celu poprawy działania modeli przewidywania.
author: ShivamPandey-msft
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 184a1cb5d3851e26b41340b711c51ef38e06eb53
ms.sourcegitcommit: ebcd9019cbb88a7f2afd9e701812e222566fd43d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2021
ms.locfileid: "6186649"
---
# <a name="improve-the-prediction-model-preview"></a><span data-ttu-id="326ed-103">Usprawnij model przewidywania (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="326ed-103">Improve the prediction model (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="326ed-104">W tym temacie opisano funkcje, których można używać w celu poprawy działania modeli przewidywania.</span><span class="sxs-lookup"><span data-stu-id="326ed-104">This topic describes features that you can use to improve the performance of prediction models.</span></span> <span data-ttu-id="326ed-105">Rozpoczynanie ulepszania modelu zaczyna się w obszarze roboczym **Prognozy płatności odbiorcy** w rozwiązaniu Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="326ed-105">You start to improve your model in the **Customer payment predictions** workspace in Microsoft Dynamics 365 Finance.</span></span> <span data-ttu-id="326ed-106">Następnie czynności ulepszające wykonuje się w aplikacji AI Builder.</span><span class="sxs-lookup"><span data-stu-id="326ed-106">The improvement steps are then completed in AI Builder.</span></span>

## <a name="select-historical-outcomes"></a><span data-ttu-id="326ed-107">Wybór wyników historycznych</span><span class="sxs-lookup"><span data-stu-id="326ed-107">Select historical outcomes</span></span>

<span data-ttu-id="326ed-108">Najpierw wybierz co najmniej jeden z trzech możliwych wyników dla faktur: **Na czas**, **Opóźnione** i **Bardzo opóźnione**.</span><span class="sxs-lookup"><span data-stu-id="326ed-108">You first select one or more of the three possible outcomes for invoices: **On time**, **Late**, and **Very late**.</span></span> <span data-ttu-id="326ed-109">Należy wybrać wszystkie trzy wyniki.</span><span class="sxs-lookup"><span data-stu-id="326ed-109">All three outcomes should be selected.</span></span> <span data-ttu-id="326ed-110">Jeśli wyczyścisz wybór któregokolwiek z tych wyników, faktury zostaną odfiltrowane z procesu trenowania, a dokładność przewidywania spadnie.</span><span class="sxs-lookup"><span data-stu-id="326ed-110">If you clear the selection of any of the outcomes, invoices will be filtered out of the training process and the accuracy of the prediction will be reduced.</span></span>

<span data-ttu-id="326ed-111">[![Potwierdzanie wyników](./media/confirm-3-outcomes.png)](./media/confirm-3-outcomes.png)</span><span class="sxs-lookup"><span data-stu-id="326ed-111">[![Confirming outcomes](./media/confirm-3-outcomes.png)](./media/confirm-3-outcomes.png)</span></span>

<span data-ttu-id="326ed-112">Jeśli organizacja wymaga tylko dwóch wyników, zmień wartości progowe wyników **Opóźnione** i **Bardzo opóźnione** na 0 (zero) dni.</span><span class="sxs-lookup"><span data-stu-id="326ed-112">If your organization requires only two outcomes, change the **Late** and **Very late** thresholds to 0 (zero) days.</span></span> <span data-ttu-id="326ed-113">W ten sposób w praktyce zwijasz prognozę do stanu binarnego **Na czas** lub **Opóźnione**.</span><span class="sxs-lookup"><span data-stu-id="326ed-113">In this way, you effectively collapse the prediction to a binary state of **On time** or **Late**.</span></span>

## <a name="select-fields"></a><span data-ttu-id="326ed-114">Wybierz pola</span><span class="sxs-lookup"><span data-stu-id="326ed-114">Select fields</span></span>

<span data-ttu-id="326ed-115">Wybierając pola, które mają być uwzględnione w modelu, należy pamiętać, że lista zawiera wszystkie pola dostępne w tabeli usługi Microsoft Dataverse, które są mapowane na dane w Azure data lake.</span><span class="sxs-lookup"><span data-stu-id="326ed-115">When you're selecting fields to include in the model, be aware that the list includes all available fields in the Microsoft Dataverse table that is mapped to the data in the Azure data lake.</span></span> <span data-ttu-id="326ed-116">Niektóre z tych pól **nie powinny** być zaznaczane.</span><span class="sxs-lookup"><span data-stu-id="326ed-116">Some of these fields should **not** be selected.</span></span> <span data-ttu-id="326ed-117">Pola, których nie należy zaznaczać, należą do jednej z trzech kategorii:</span><span class="sxs-lookup"><span data-stu-id="326ed-117">The fields that should not be selected fall into one of three categories:</span></span>

- <span data-ttu-id="326ed-118">Pole jest wymagane przez tabelę usługi Dataverse, ale w data lake nie ma dla niej żadnych danych.</span><span class="sxs-lookup"><span data-stu-id="326ed-118">The field is required for the Dataverse table, but there is no backing data for it in the data lake.</span></span>
- <span data-ttu-id="326ed-119">Pole jest identyfikatorem i w związku z tym jest nieprzydatne dla funkcji uczenia maszynowego.</span><span class="sxs-lookup"><span data-stu-id="326ed-119">The field is an ID and therefore doesn't make sense for a machine learning feature.</span></span>
- <span data-ttu-id="326ed-120">Pole reprezentuje informacje, które nie będą dostępne podczas przewidywania.</span><span class="sxs-lookup"><span data-stu-id="326ed-120">The field represents information that won't be available during prediction.</span></span>

<span data-ttu-id="326ed-121">W poniższych sekcjach przedstawiono pola dostępne dla jednostek faktury i odbiorcy oraz listę pól, które **nie powinny** być wybierane do trenowania.</span><span class="sxs-lookup"><span data-stu-id="326ed-121">The following sections show the fields that are available for the invoice and customer entities, and list the fields that should **not** be selected for training.</span></span> <span data-ttu-id="326ed-122">Kategoria określona dla każdego z tych pól nawiązuje do kategorii z poprzedzającej listy.</span><span class="sxs-lookup"><span data-stu-id="326ed-122">The category that is specified for each of those fields refers to the categories in the preceding list.</span></span>
 
### <a name="invoice-dataverse-table"></a><span data-ttu-id="326ed-123">Tabela Faktura Dataverse</span><span class="sxs-lookup"><span data-stu-id="326ed-123">Invoice Dataverse table</span></span>

<span data-ttu-id="326ed-124">Na poniższej ilustracji pokazano pola dostępne dla tabali Faktura.</span><span class="sxs-lookup"><span data-stu-id="326ed-124">The following illustration shows the fields that are available for the invoice table.</span></span>

<span data-ttu-id="326ed-125">[![Pola dostępne dla tabeli Faktura](./media/available-fields.png)](./media/available-fields.png)</span><span class="sxs-lookup"><span data-stu-id="326ed-125">[![Available fields for the invoice table](./media/available-fields.png)](./media/available-fields.png)</span></span>

<span data-ttu-id="326ed-126">Następujących pól nie należy wybierać do trenowania:</span><span class="sxs-lookup"><span data-stu-id="326ed-126">The following fields should not be selected for training:</span></span>

- <span data-ttu-id="326ed-127">**Konto faktury** (kategoria 2)</span><span class="sxs-lookup"><span data-stu-id="326ed-127">**Invoice Account** (category 2)</span></span>
- <span data-ttu-id="326ed-128">**Zamknięte** (kategoria 3) — to pole służy do filtrowania faktur dla trenowania (zamknięte) i przewidywania (niezamknięte).</span><span class="sxs-lookup"><span data-stu-id="326ed-128">**Is closed** (category 3) – This field is used to filter invoices for training (closed) and prediction (not closed).</span></span>
- <span data-ttu-id="326ed-129">**Nazwa** (kategoria 1)</span><span class="sxs-lookup"><span data-stu-id="326ed-129">**Name** (category 1)</span></span>
- <span data-ttu-id="326ed-130">**Identyfikator źródła** (kategoria 2)</span><span class="sxs-lookup"><span data-stu-id="326ed-130">**Source Id** (category 2)</span></span>
- <span data-ttu-id="326ed-131">**Rekord źródłowy** (kategoria 2)</span><span class="sxs-lookup"><span data-stu-id="326ed-131">**Source record** (category 2)</span></span>
- <span data-ttu-id="326ed-132">**Tabela źródłowa** (kategoria 2)</span><span class="sxs-lookup"><span data-stu-id="326ed-132">**Source table** (category 2)</span></span>

### <a name="customer-dataverse-table"></a><span data-ttu-id="326ed-133">Tabela odbiorców Dataverse</span><span class="sxs-lookup"><span data-stu-id="326ed-133">Customer Dataverse table</span></span>

<span data-ttu-id="326ed-134">Na poniższej ilustracji pokazano pola dostępne dla tabeli Odbiorca.</span><span class="sxs-lookup"><span data-stu-id="326ed-134">The following illustration shows the fields that are available for the customer table.</span></span>

<span data-ttu-id="326ed-135">[![Pola dostępne dla tabeli Odbiorca](./media/related-entities.png)](./media/related-entities.png)</span><span class="sxs-lookup"><span data-stu-id="326ed-135">[![Available fields for the customer table](./media/related-entities.png)](./media/related-entities.png)</span></span>

<span data-ttu-id="326ed-136">Następującego pola nie należy wybierać do trenowania:</span><span class="sxs-lookup"><span data-stu-id="326ed-136">The following field should not be selected for training:</span></span>

- <span data-ttu-id="326ed-137">**Unikatowy klucz wiersza** (kategoria 2)</span><span class="sxs-lookup"><span data-stu-id="326ed-137">**Row Unique Key** (category 2)</span></span>

## <a name="filters"></a><span data-ttu-id="326ed-138">Filtry</span><span class="sxs-lookup"><span data-stu-id="326ed-138">Filters</span></span>

<span data-ttu-id="326ed-139">Filtry obecnie nie obsługują scenariusza prognozowania płatności od odbiorców.</span><span class="sxs-lookup"><span data-stu-id="326ed-139">The filters don't currently support the Customer payment predictor scenario.</span></span> <span data-ttu-id="326ed-140">W związku z tym wybierz opcję **Pomiń ten krok** i przejdź do strony podsumowania.</span><span class="sxs-lookup"><span data-stu-id="326ed-140">Therefore, select **Skip this step**, and continue to the summary page.</span></span>

<span data-ttu-id="326ed-141">[![Koncentrowanie modelu za pomocą filtrów](./media/focus-model-with-filters.png)](./media/focus-model-with-filters.png)</span><span class="sxs-lookup"><span data-stu-id="326ed-141">[![Focus model with filters](./media/focus-model-with-filters.png)](./media/focus-model-with-filters.png)</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
