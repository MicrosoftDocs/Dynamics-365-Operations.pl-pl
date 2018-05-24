---
title: Importowanie danych historycznych dla prognoz popytu
description: "Aby uzyskać dokładne prognozy popytu, potrzebne są historyczne dane dotyczące popytu na towar lub klucz alokacji produktów. W tym temacie opisano, jak za pomocą jednostek danych importować historyczne dane popytu z dowolnego systemu, w celu uzyskania dłuższej historii danych dotyczących prognoz popytu."
author: roxanadiaconu
manager: AnnBe
ms.date: 05/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.assetid: 59c0d269-9db0-48e7-b8c7-9a388781a9ca
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: e7975003620d951717c66144c8d0521de0f69158
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---

# <a name="import-historical-data-for-demand-forecasts"></a><span data-ttu-id="6e8b6-104">Importowanie danych historycznych dla prognoz popytu</span><span class="sxs-lookup"><span data-stu-id="6e8b6-104">Import historical data for demand forecasts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6e8b6-105">W celu zagwarantowania dokładności prognoz popytu, musisz mieć tyle historycznych danych popytu, ile możesz uzyskać dla pozycji lub klucza alokacji produktów.</span><span class="sxs-lookup"><span data-stu-id="6e8b6-105">To help guarantee the accuracy of demand forecasts, you must have as much historical demand data as you can get per item or item allocation key.</span></span> <span data-ttu-id="6e8b6-106">Jeśli historyczne dane popytu nie zostały jeszcze zaimportowane, użyj jednostki danych **Historyczny popyt zewnętrzny** (ReqDemPlanHistoricalExternalDemandEntity) w Microsoft Dynamics 365 for Finance and Operations do ich zaimportowania.</span><span class="sxs-lookup"><span data-stu-id="6e8b6-106">If the historical demand data isn't already imported, use the **Historical external demand** (ReqDemPlanHistoricalExternalDemandEntity) data entity in Microsoft Dynamics 365 for Finance and Operations to import it.</span></span>

<span data-ttu-id="6e8b6-107">W obszarze roboczym **Zarządzanie danymi** można wyświetlić przegląd wszystkich pól w jednostce.</span><span class="sxs-lookup"><span data-stu-id="6e8b6-107">In the **Data management** workspace, you can see an overview of all the fields in the entity.</span></span>

1. <span data-ttu-id="6e8b6-108">Otwórz obszar roboczy **Zarządzanie danymi**.</span><span class="sxs-lookup"><span data-stu-id="6e8b6-108">Open the **Data management** workspace.</span></span>
2. <span data-ttu-id="6e8b6-109">Kliknij kafelek **Jednostki danych**.</span><span class="sxs-lookup"><span data-stu-id="6e8b6-109">Click the **Data entities** tile.</span></span>
3. <span data-ttu-id="6e8b6-110">Wyszukaj na liście jednostek pozycję **Historyczny popyt zewnętrzny**.</span><span class="sxs-lookup"><span data-stu-id="6e8b6-110">Search the entity list for **Historical external demand**.</span></span>
4. <span data-ttu-id="6e8b6-111">Kliknij **Pola docelowe**.</span><span class="sxs-lookup"><span data-stu-id="6e8b6-111">Click **Target fields**.</span></span> <span data-ttu-id="6e8b6-112">Następujące pola jednostki są wymagane: oddziału (**DeliveringSiteId**), daty (**DemandDate**), ilości (**DemandQuantity**) i numeru pozycji (**ItemNumber**) lub klucza alokacji produktów (**ProductAllocationKeyId**).</span><span class="sxs-lookup"><span data-stu-id="6e8b6-112">The following entity fields are mandatory: site (**DeliveringSiteId**), date (**DemandDate**), quantity (**DemandQuantity**), and either item number (**ItemNumber**) or item allocation key (**ProductAllocationKeyId**).</span></span>

<span data-ttu-id="6e8b6-113">Aby użyć jednostki danych, musisz mieć plik programu Microsoft Excel lub plik wartości rozdzielanych przecinkami (CSV) zawierający dane historyczne popytu.</span><span class="sxs-lookup"><span data-stu-id="6e8b6-113">To use the data entity, you must have a Microsoft Excel file or comma-separated values (CSV) file that contains the historical demand data.</span></span> <span data-ttu-id="6e8b6-114">Poniższy przykład pokazuje, jak przeprowadzić import danych z pliku CSV.</span><span class="sxs-lookup"><span data-stu-id="6e8b6-114">The following example shows how to import the data from a CSV file.</span></span>

## <a name="example"></a><span data-ttu-id="6e8b6-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="6e8b6-115">Example</span></span>

<span data-ttu-id="6e8b6-116">Można użyć następującego pliku jako przykładowego.</span><span class="sxs-lookup"><span data-stu-id="6e8b6-116">You can use the following file as an example.</span></span> <span data-ttu-id="6e8b6-117">Pobierz [HistoricalDemandData](https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/365OperationsDemandForecast).</span><span class="sxs-lookup"><span data-stu-id="6e8b6-117">Download the [HistoricalDemandData](https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/365OperationsDemandForecast).</span></span> <span data-ttu-id="6e8b6-118">Ten plik zawiera historyczne dane dotyczące popytu dla pozycji D0001.</span><span class="sxs-lookup"><span data-stu-id="6e8b6-118">This file contains the historical demand data for item D0001.</span></span> <span data-ttu-id="6e8b6-119">Zawiera on tylko następujące wymagane pola: oddział, ilość i data zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="6e8b6-119">It contains only the following mandatory fields: site, quantity, and the demand date.</span></span>

1. <span data-ttu-id="6e8b6-120">Wybierz firmę do której zostaną zaimportowane historyczne dane popytu.</span><span class="sxs-lookup"><span data-stu-id="6e8b6-120">Select the company to import the historical demand data into.</span></span>
2. <span data-ttu-id="6e8b6-121">Otwórz obszar roboczy **Zarządzanie danymi**.</span><span class="sxs-lookup"><span data-stu-id="6e8b6-121">Open the **Data management** workspace.</span></span>
3. <span data-ttu-id="6e8b6-122">Kliknij kafelek **Importuj**.</span><span class="sxs-lookup"><span data-stu-id="6e8b6-122">Click the **Import** tile.</span></span>
4. <span data-ttu-id="6e8b6-123">Wprowadź nazwę dla importowania projektu, taką jak **Importowanie historycznego popytu dla pozycji D0001**.</span><span class="sxs-lookup"><span data-stu-id="6e8b6-123">Enter a name for the import project, such as **Import historical demand for item D0001**.</span></span>
5. <span data-ttu-id="6e8b6-124">W polu **Format danych źródłowych** wybierz format pliku, który jest importowany.</span><span class="sxs-lookup"><span data-stu-id="6e8b6-124">In the **Source data format** field, select the file format of the file that you're importing.</span></span> <span data-ttu-id="6e8b6-125">Aby zaimportować plik HistoricalDemandData w tym przykładzie, zaznacz **CSV**.</span><span class="sxs-lookup"><span data-stu-id="6e8b6-125">To import the HistoricalDemandData file for this example, select **CSV**.</span></span>
6. <span data-ttu-id="6e8b6-126">W polu **Nazwa jednostki** wybierz **Historyczny popyt zewnętrzny**.</span><span class="sxs-lookup"><span data-stu-id="6e8b6-126">In the **Entity name** field, select **Historical external demand**.</span></span>
7. <span data-ttu-id="6e8b6-127">Zapisz plik na komputerze, a następnie przekaż go.</span><span class="sxs-lookup"><span data-stu-id="6e8b6-127">Save the file to your computer, and then upload it.</span></span>
8. <span data-ttu-id="6e8b6-128">Kliknij **Importuj**.</span><span class="sxs-lookup"><span data-stu-id="6e8b6-128">Click **Import**.</span></span>
9. <span data-ttu-id="6e8b6-129">Strona **Podsumowanie wykonania** zostanie automatycznie otwarta.</span><span class="sxs-lookup"><span data-stu-id="6e8b6-129">The **Execution summary** page is opened automatically.</span></span> <span data-ttu-id="6e8b6-130">Sprawdź importowane dane na stronie.</span><span class="sxs-lookup"><span data-stu-id="6e8b6-130">Verify the imported data on the page.</span></span>

<span data-ttu-id="6e8b6-131">Po zaimportowaniu historycznych danych popytu można generować prognozy popytu.</span><span class="sxs-lookup"><span data-stu-id="6e8b6-131">After you've imported the historical demand data, you can generate a demand forecast.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6e8b6-132">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="6e8b6-132">Additional resources</span></span>

[<span data-ttu-id="6e8b6-133">Generowanie bazowej prognozy statystycznej</span><span class="sxs-lookup"><span data-stu-id="6e8b6-133">Generate a statistical baseline forecast</span></span>](generate-statistical-baseline-forecast.md)

