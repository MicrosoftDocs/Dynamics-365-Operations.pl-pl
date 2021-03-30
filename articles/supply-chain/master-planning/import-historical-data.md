---
title: Importowanie danych historycznych dla prognoz popytu
description: Aby uzyskać dokładne prognozy popytu, potrzebne są historyczne dane dotyczące popytu na towar lub klucz alokacji produktów. W tym temacie opisano, jak za pomocą jednostek danych importować historyczne dane popytu z dowolnego systemu, w celu uzyskania dłuższej historii danych dotyczących prognoz popytu.
author: roxanadiaconu
manager: tfehr
ms.date: 05/10/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.assetid: 59c0d269-9db0-48e7-b8c7-9a388781a9ca
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d415895bd05b9ab1a2311ab69cc3757047df91db
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5204623"
---
# <a name="import-historical-data-for-demand-forecasts"></a><span data-ttu-id="aa8b2-104">Importowanie danych historycznych dla prognoz popytu</span><span class="sxs-lookup"><span data-stu-id="aa8b2-104">Import historical data for demand forecasts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="aa8b2-105">W celu zagwarantowania dokładności prognoz popytu, musisz mieć tyle historycznych danych popytu, ile możesz uzyskać dla pozycji lub klucza alokacji produktów.</span><span class="sxs-lookup"><span data-stu-id="aa8b2-105">To help guarantee the accuracy of demand forecasts, you must have as much historical demand data as you can get per item or item allocation key.</span></span> <span data-ttu-id="aa8b2-106">Jeśli historyczne dane popytu nie zostały jeszcze zaimportowane, użyj jednostki danych **Historyczny popyt zewnętrzny** (ReqDemPlanHistoricalExternalDemandEntity) w Dynamics 365 Supply Chain Management do ich zaimportowania.</span><span class="sxs-lookup"><span data-stu-id="aa8b2-106">If the historical demand data isn't already imported, use the **Historical external demand** (ReqDemPlanHistoricalExternalDemandEntity) data entity in Dynamics 365 Supply Chain Management to import it.</span></span>

<span data-ttu-id="aa8b2-107">W obszarze roboczym **Zarządzanie danymi** można wyświetlić przegląd wszystkich pól w jednostce.</span><span class="sxs-lookup"><span data-stu-id="aa8b2-107">In the **Data management** workspace, you can see an overview of all the fields in the entity.</span></span>

1. <span data-ttu-id="aa8b2-108">Otwórz obszar roboczy **Zarządzanie danymi**.</span><span class="sxs-lookup"><span data-stu-id="aa8b2-108">Open the **Data management** workspace.</span></span>
2. <span data-ttu-id="aa8b2-109">Wybierz kafelek **Jednostki danych**.</span><span class="sxs-lookup"><span data-stu-id="aa8b2-109">Select the **Data entities** tile.</span></span>
3. <span data-ttu-id="aa8b2-110">Wyszukaj na liście jednostek pozycję **Historyczny popyt zewnętrzny**.</span><span class="sxs-lookup"><span data-stu-id="aa8b2-110">Search the entity list for **Historical external demand**.</span></span>
4. <span data-ttu-id="aa8b2-111">Wybierz **Pola docelowe**.</span><span class="sxs-lookup"><span data-stu-id="aa8b2-111">Select **Target fields**.</span></span> <span data-ttu-id="aa8b2-112">Następujące pola jednostki są wymagane: oddziału (**DeliveringSiteId**), daty (**DemandDate**), ilości (**DemandQuantity**) i numeru pozycji (**ItemNumber**) lub klucza alokacji produktów (**ProductAllocationKeyId**).</span><span class="sxs-lookup"><span data-stu-id="aa8b2-112">The following entity fields are mandatory: site (**DeliveringSiteId**), date (**DemandDate**), quantity (**DemandQuantity**), and either item number (**ItemNumber**) or item allocation key (**ProductAllocationKeyId**).</span></span>

<span data-ttu-id="aa8b2-113">Aby użyć jednostki danych, musisz mieć plik programu Microsoft Excel lub plik wartości rozdzielanych przecinkami (CSV) zawierający dane historyczne popytu.</span><span class="sxs-lookup"><span data-stu-id="aa8b2-113">To use the data entity, you must have a Microsoft Excel file or comma-separated values (CSV) file that contains the historical demand data.</span></span> <span data-ttu-id="aa8b2-114">Poniższy przykład pokazuje, jak przeprowadzić import danych z pliku CSV.</span><span class="sxs-lookup"><span data-stu-id="aa8b2-114">The following example shows how to import the data from a CSV file.</span></span>

<span data-ttu-id="aa8b2-115">Aby uzyskać więcej informacji dotyczących sposobu importowania danych, w tym sposobu oczyszczania danych po imporcie, zobacz temat [Omówienie zadań importowania i eksportowania danych](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md) oraz tematy pokrewne.</span><span class="sxs-lookup"><span data-stu-id="aa8b2-115">For more information about how to import data, including how to clean up data after an import, see [Data import and export jobs overview](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md) and its related topics.</span></span>

## <a name="example"></a><span data-ttu-id="aa8b2-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="aa8b2-116">Example</span></span>

<span data-ttu-id="aa8b2-117">Można użyć następującego pliku jako przykładowego.</span><span class="sxs-lookup"><span data-stu-id="aa8b2-117">You can use the following file as an example.</span></span> <span data-ttu-id="aa8b2-118">Pobierz [HistoricalDemandData](https://docs.microsoft.com/dynamics/s-e/).</span><span class="sxs-lookup"><span data-stu-id="aa8b2-118">Download the [HistoricalDemandData](https://docs.microsoft.com/dynamics/s-e/).</span></span> <span data-ttu-id="aa8b2-119">Ten plik zawiera historyczne dane dotyczące popytu dla pozycji D0001.</span><span class="sxs-lookup"><span data-stu-id="aa8b2-119">This file contains the historical demand data for item D0001.</span></span> <span data-ttu-id="aa8b2-120">Zawiera on tylko następujące wymagane pola: oddział, ilość i data zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="aa8b2-120">It contains only the following mandatory fields: site, quantity, and the demand date.</span></span>

1. <span data-ttu-id="aa8b2-121">Wybierz firmę do której zostaną zaimportowane historyczne dane popytu.</span><span class="sxs-lookup"><span data-stu-id="aa8b2-121">Select the company to import the historical demand data into.</span></span>
2. <span data-ttu-id="aa8b2-122">Otwórz obszar roboczy **Zarządzanie danymi**.</span><span class="sxs-lookup"><span data-stu-id="aa8b2-122">Open the **Data management** workspace.</span></span>
3. <span data-ttu-id="aa8b2-123">Wybierz kafelek **Import**.</span><span class="sxs-lookup"><span data-stu-id="aa8b2-123">Select the **Import** tile.</span></span>
4. <span data-ttu-id="aa8b2-124">Wprowadź nazwę dla importowania projektu, taką jak **Importowanie historycznego popytu dla pozycji D0001**.</span><span class="sxs-lookup"><span data-stu-id="aa8b2-124">Enter a name for the import project, such as **Import historical demand for item D0001**.</span></span>
5. <span data-ttu-id="aa8b2-125">W polu **Format danych źródłowych** wybierz format pliku, który jest importowany.</span><span class="sxs-lookup"><span data-stu-id="aa8b2-125">In the **Source data format** field, select the file format of the file that you're importing.</span></span> <span data-ttu-id="aa8b2-126">Aby zaimportować plik HistoricalDemandData w tym przykładzie, zaznacz **CSV**.</span><span class="sxs-lookup"><span data-stu-id="aa8b2-126">To import the HistoricalDemandData file for this example, select **CSV**.</span></span>
6. <span data-ttu-id="aa8b2-127">W polu **Nazwa jednostki** wybierz **Historyczny popyt zewnętrzny**.</span><span class="sxs-lookup"><span data-stu-id="aa8b2-127">In the **Entity name** field, select **Historical external demand**.</span></span>
7. <span data-ttu-id="aa8b2-128">Zapisz plik na komputerze, a następnie przekaż go.</span><span class="sxs-lookup"><span data-stu-id="aa8b2-128">Save the file to your computer, and then upload it.</span></span>
8. <span data-ttu-id="aa8b2-129">Wybierz opcję **Importuj**.</span><span class="sxs-lookup"><span data-stu-id="aa8b2-129">Select **Import**.</span></span>
9. <span data-ttu-id="aa8b2-130">Strona **Podsumowanie wykonania** zostanie automatycznie otwarta.</span><span class="sxs-lookup"><span data-stu-id="aa8b2-130">The **Execution summary** page is opened automatically.</span></span> <span data-ttu-id="aa8b2-131">Sprawdź importowane dane na stronie.</span><span class="sxs-lookup"><span data-stu-id="aa8b2-131">Verify the imported data on the page.</span></span>

<span data-ttu-id="aa8b2-132">Po zaimportowaniu historycznych danych popytu można generować prognozy popytu.</span><span class="sxs-lookup"><span data-stu-id="aa8b2-132">After you've imported the historical demand data, you can generate a demand forecast.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="aa8b2-133">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="aa8b2-133">Additional resources</span></span>

[<span data-ttu-id="aa8b2-134">Generowanie bazowej prognozy statystycznej</span><span class="sxs-lookup"><span data-stu-id="aa8b2-134">Generate a statistical baseline forecast</span></span>](generate-statistical-baseline-forecast.md)  
[<span data-ttu-id="aa8b2-135">Omówienie zadań importowania i eksportowania danych</span><span class="sxs-lookup"><span data-stu-id="aa8b2-135">Data import and export jobs overview</span></span>](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]