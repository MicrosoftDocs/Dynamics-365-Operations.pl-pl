---
title: Importowanie danych historycznych dla prognoz popytu
description: Aby uzyskać dokładne prognozy popytu, potrzebne są historyczne dane dotyczące popytu na towar lub klucz alokacji produktów. W tym temacie opisano, jak za pomocą jednostek danych importować historyczne dane popytu z dowolnego systemu, w celu uzyskania dłuższej historii danych dotyczących prognoz popytu.
author: roxanadiaconu
ms.date: 05/10/2017
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 0b04ee246d4c28e934407ccb92d792692cc4347d
ms.sourcegitcommit: cbbb35c71ab4ff1ae08fa4f7cc97019b207246be
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301657"
---
# <a name="import-historical-data-for-demand-forecasts"></a><span data-ttu-id="a8928-104">Importowanie danych historycznych dla prognoz popytu</span><span class="sxs-lookup"><span data-stu-id="a8928-104">Import historical data for demand forecasts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a8928-105">W celu zagwarantowania dokładności prognoz popytu, musisz mieć tyle historycznych danych popytu, ile możesz uzyskać dla pozycji lub klucza alokacji produktów.</span><span class="sxs-lookup"><span data-stu-id="a8928-105">To help guarantee the accuracy of demand forecasts, you must have as much historical demand data as you can get per item or item allocation key.</span></span> <span data-ttu-id="a8928-106">Jeśli historyczne dane popytu nie zostały jeszcze zaimportowane, użyj jednostki danych **Historyczny popyt zewnętrzny** (ReqDemPlanHistoricalExternalDemandEntity) w Dynamics 365 Supply Chain Management do ich zaimportowania.</span><span class="sxs-lookup"><span data-stu-id="a8928-106">If the historical demand data isn't already imported, use the **Historical external demand** (ReqDemPlanHistoricalExternalDemandEntity) data entity in Dynamics 365 Supply Chain Management to import it.</span></span>

<span data-ttu-id="a8928-107">W obszarze roboczym **Zarządzanie danymi** można wyświetlić przegląd wszystkich pól w jednostce.</span><span class="sxs-lookup"><span data-stu-id="a8928-107">In the **Data management** workspace, you can see an overview of all the fields in the entity.</span></span>

1. <span data-ttu-id="a8928-108">Otwórz obszar roboczy **Zarządzanie danymi**.</span><span class="sxs-lookup"><span data-stu-id="a8928-108">Open the **Data management** workspace.</span></span>
2. <span data-ttu-id="a8928-109">Wybierz kafelek **Jednostki danych**.</span><span class="sxs-lookup"><span data-stu-id="a8928-109">Select the **Data entities** tile.</span></span>
3. <span data-ttu-id="a8928-110">Wyszukaj na liście jednostek pozycję **Historyczny popyt zewnętrzny**.</span><span class="sxs-lookup"><span data-stu-id="a8928-110">Search the entity list for **Historical external demand**.</span></span>
4. <span data-ttu-id="a8928-111">Wybierz **Pola docelowe**.</span><span class="sxs-lookup"><span data-stu-id="a8928-111">Select **Target fields**.</span></span> <span data-ttu-id="a8928-112">Następujące pola jednostki są wymagane: oddziału (**DeliveringSiteId**), daty (**DemandDate**), ilości (**DemandQuantity**) i numeru pozycji (**ItemNumber**) lub klucza alokacji produktów (**ProductAllocationKeyId**).</span><span class="sxs-lookup"><span data-stu-id="a8928-112">The following entity fields are mandatory: site (**DeliveringSiteId**), date (**DemandDate**), quantity (**DemandQuantity**), and either item number (**ItemNumber**) or item allocation key (**ProductAllocationKeyId**).</span></span>

<span data-ttu-id="a8928-113">Aby użyć jednostki danych, musisz mieć plik programu Microsoft Excel lub plik wartości rozdzielanych przecinkami (CSV) zawierający dane historyczne popytu.</span><span class="sxs-lookup"><span data-stu-id="a8928-113">To use the data entity, you must have a Microsoft Excel file or comma-separated values (CSV) file that contains the historical demand data.</span></span> <span data-ttu-id="a8928-114">Poniższy przykład pokazuje, jak przeprowadzić import danych z pliku CSV.</span><span class="sxs-lookup"><span data-stu-id="a8928-114">The following example shows how to import the data from a CSV file.</span></span>

<span data-ttu-id="a8928-115">Aby uzyskać więcej informacji dotyczących sposobu importowania danych, w tym sposobu oczyszczania danych po imporcie, zobacz temat [Omówienie zadań importowania i eksportowania danych](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md) oraz tematy pokrewne.</span><span class="sxs-lookup"><span data-stu-id="a8928-115">For more information about how to import data, including how to clean up data after an import, see [Data import and export jobs overview](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md) and its related topics.</span></span>

<span data-ttu-id="a8928-116">Zobacz także [Generowanie bazowej prognozy statystycznej](generate-statistical-baseline-forecast.md).</span><span class="sxs-lookup"><span data-stu-id="a8928-116">See also [Generate a statistical baseline forecast](generate-statistical-baseline-forecast.md).</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]