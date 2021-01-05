---
title: Tworzenie wymiarów i importowanie członków wymiaru
description: Rachunek kosztów to niezależny moduł, który wymaga danych głównych z innych modułów.
author: ShylaThompson
manager: AnnBe
ms.date: 09/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 256254
ms.assetid: e1b0a6e3-0c72-4a7d-90e1-20f870c6dbad
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: d61358be79adc943572bb4a5d624cb7c80b52e6e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446826"
---
# <a name="create-dimensions-and-import-dimension-members"></a><span data-ttu-id="2f66b-103">Tworzenie wymiarów i importowanie członków wymiaru</span><span class="sxs-lookup"><span data-stu-id="2f66b-103">Create dimensions and import dimension members</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2f66b-104">Rachunek kosztów to niezależny moduł, który wymaga danych z innych modułów.</span><span class="sxs-lookup"><span data-stu-id="2f66b-104">Cost accounting is an independent module that requires data from other modules.</span></span> <span data-ttu-id="2f66b-105">Te dane są podzielone na następujące kategorie:</span><span class="sxs-lookup"><span data-stu-id="2f66b-105">This data is categorized into the following:</span></span>

-  <span data-ttu-id="2f66b-106">Składniki kosztów</span><span class="sxs-lookup"><span data-stu-id="2f66b-106">Cost elements</span></span>
-  <span data-ttu-id="2f66b-107">Obiekty kosztów</span><span class="sxs-lookup"><span data-stu-id="2f66b-107">Cost objects</span></span>
-  <span data-ttu-id="2f66b-108">Wymiary statystyczne</span><span class="sxs-lookup"><span data-stu-id="2f66b-108">Statistical dimensions</span></span>

<span data-ttu-id="2f66b-109">**Składnik kosztu** odnosi się do elementu istotnego dla kosztów w planie kont.</span><span class="sxs-lookup"><span data-stu-id="2f66b-109">A **Cost element** corresponds to a cost-relevant item in the chart of accounts.</span></span> <span data-ttu-id="2f66b-110">**Obiekt kosztów** odpowiada dowolnemu typowi wymiaru finansowego, takiego jak produkty, centra kosztów i projekty, które chcesz oszacować, przydzielić do nich koszty lub zmierzyć bezpośrednio.</span><span class="sxs-lookup"><span data-stu-id="2f66b-110">A **Cost object** corresponds to any type of financial dimension, such as products, cost centers, and projects that you want to estimate, allocate costs to, or measure directly.</span></span> <span data-ttu-id="2f66b-111">**Wymiar statystyczny** i jego elementy są używane do rejestrowania wpisów niepieniężnych.</span><span class="sxs-lookup"><span data-stu-id="2f66b-111">A **Statistical dimension** and its members are used to register non-monetary entries.</span></span> <span data-ttu-id="2f66b-112">Elementy członkowskie wymiaru statystycznego mogą służyć jako podstawa alokacji w dystrybucji i alokacji kosztów</span><span class="sxs-lookup"><span data-stu-id="2f66b-112">Statistical dimension members can be used as an allocation base in cost distribution and allocation</span></span> 

<span data-ttu-id="2f66b-113">Poniższy schemat przedstawia wymiary, które są używane w module Rachunek kosztów.</span><span class="sxs-lookup"><span data-stu-id="2f66b-113">The following diagram illustrates the dimensions that are used in Cost accounting.</span></span>

<span data-ttu-id="2f66b-114">[![Wymiary rachunku kosztów](./media/cost-eos-dimensions.png)](./media/cost-eos-dimensions.png)</span><span class="sxs-lookup"><span data-stu-id="2f66b-114">[![Cost accounting dimensions](./media/cost-eos-dimensions.png)](./media/cost-eos-dimensions.png)</span></span>

<span data-ttu-id="2f66b-115">Po zaimportowaniu danych do modułu Rachunek kosztów można ich użyć do tworzenia różnych perspektyw zapewniających informacje menedżerom na wszystkich poziomach organizacji.</span><span class="sxs-lookup"><span data-stu-id="2f66b-115">After the data is imported into Cost accounting, you can use it to build various perspectives that provide insights to managers at all levels of the organization.</span></span> <span data-ttu-id="2f66b-116">Poniższe tematy zawierają informacje dotyczące tworzenia wymiarów i importowania elementów wymiarów.</span><span class="sxs-lookup"><span data-stu-id="2f66b-116">The following topics provide information about creating dimensions and importing dimension members.</span></span> 

-  [<span data-ttu-id="2f66b-117">Wymiary składników kosztów</span><span class="sxs-lookup"><span data-stu-id="2f66b-117">Cost element dimensions</span></span>](cost-elements.md)
-  [<span data-ttu-id="2f66b-118">Tworzenie składników kosztu</span><span class="sxs-lookup"><span data-stu-id="2f66b-118">Create cost elements</span></span>](./tasks/create-cost-elements.md)
-  [<span data-ttu-id="2f66b-119">Wymiary obiektów kosztów</span><span class="sxs-lookup"><span data-stu-id="2f66b-119">Cost object dimensions</span></span>](cost-objects.md)
-  [<span data-ttu-id="2f66b-120">Mapowanie elementów członkowskich wymiaru elementu kosztów na wspólny zestaw elementów członkowskich wymiaru</span><span class="sxs-lookup"><span data-stu-id="2f66b-120">Map cost element dimension members to a common set of dimension members</span></span>](map-cost-elements-dimension-members.md)
-  [<span data-ttu-id="2f66b-121">Mapowanie wymiaru składnika kosztu</span><span class="sxs-lookup"><span data-stu-id="2f66b-121">Map a cost element dimension</span></span>](./tasks/map-cost-element-dimension.md)
-  [<span data-ttu-id="2f66b-122">Elementy członkowskie wymiaru statystycznego i szablony dostawców miar statystycznych</span><span class="sxs-lookup"><span data-stu-id="2f66b-122">Statistical dimension members and statistical measure provider templates</span></span>](statistical-measure-provider-template.md)






