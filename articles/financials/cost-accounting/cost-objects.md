---
title: Wymiary obiektów kosztów
description: Podczas analizowania kosztów wymiary składników kosztów służą do ustalania, gdzie płyną koszty. Wymiary obiektów kosztów są używane do określenia, gdzie należy przypisać koszty. Ten temat zawiera informacje o wymiarach obiektów kosztów.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimensionMember
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 223174
ms.assetid: 2a1cdd35-30cb-41e7-9506-67fd04a537c5
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 60a6575387a6ebe3b349a61368a7561d78dc69f3
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1565422"
---
# <a name="cost-object-dimensions"></a><span data-ttu-id="12c7b-105">Wymiary obiektów kosztów</span><span class="sxs-lookup"><span data-stu-id="12c7b-105">Cost object dimensions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="12c7b-106">Podczas analizowania kosztów wymiary składników kosztów służą do ustalania, gdzie płyną koszty.</span><span class="sxs-lookup"><span data-stu-id="12c7b-106">When you analyze costs, you use cost element dimensions to determine where costs flow to.</span></span> <span data-ttu-id="12c7b-107">Wymiary obiektów kosztów są używane do określenia, gdzie należy przypisać koszty.</span><span class="sxs-lookup"><span data-stu-id="12c7b-107">You use cost object dimensions to determine where you should assign costs.</span></span> <span data-ttu-id="12c7b-108">Ten temat zawiera informacje o wymiarach obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="12c7b-108">This topic provides information about cost object dimensions.</span></span>

<span data-ttu-id="12c7b-109">Obiektem kosztów może być dowolny typu obiektu, który chcesz oszacować, przydzielić mu koszty lub bezpośrednio zmierzyć.</span><span class="sxs-lookup"><span data-stu-id="12c7b-109">A cost object can be any type of object that you want to estimate, allocate costs to, or measure directly.</span></span> <span data-ttu-id="12c7b-110">Typowymi obiektami kosztów są produkty, projekty, zasoby, działy, centra kosztów i regiony geograficzne.</span><span class="sxs-lookup"><span data-stu-id="12c7b-110">Typical cost objects include products, projects, resources, departments, cost centers, and geographical regions.</span></span> <span data-ttu-id="12c7b-111">Kierownictwo używa obiektów kosztów do mierzenia kosztów, ale także do analizy rentowności.</span><span class="sxs-lookup"><span data-stu-id="12c7b-111">Management uses cost objects to quantify costs and also to drive profitability analysis.</span></span>

## <a name="cost-object-dimensions-and-cost-object-dimension-members"></a><span data-ttu-id="12c7b-112">Wymiary obiektów kosztów i elementy członkowskie wymiarów obiektów kosztów</span><span class="sxs-lookup"><span data-stu-id="12c7b-112">Cost object dimensions and cost object dimension members</span></span>
<span data-ttu-id="12c7b-113">Obiekty kosztów są nazywane *wymiarami obiektów kosztów*.</span><span class="sxs-lookup"><span data-stu-id="12c7b-113">Cost objects are known as *cost object dimensions*.</span></span> <span data-ttu-id="12c7b-114">Po ustaleniu, do której jednostki powinien się odnosić wymiar obiektów kosztów, należy określić wartości poszczególnych wymiarów lub zaimportować je do modułu Rachunek kosztów z innych systemów źródłowych.</span><span class="sxs-lookup"><span data-stu-id="12c7b-114">After you’ve decided which entity the cost object dimension should refer to, you must specify the individual dimension values or import them into Cost accounting from other source systems.</span></span> <span data-ttu-id="12c7b-115">Te wartości poszczególnych wymiarów są nazywane *elementami członkowskimi wymiarów obiektów kosztów*.</span><span class="sxs-lookup"><span data-stu-id="12c7b-115">These individual dimension values are known as *cost object dimension members*.</span></span> <span data-ttu-id="12c7b-116">Na przykład jako wymiaru obiektów kosztów chcesz użyć wymiaru finansowego o nazwie Centrum kosztu.</span><span class="sxs-lookup"><span data-stu-id="12c7b-116">For example, you want to use the financial dimension that is named Cost center as the cost object dimension.</span></span> <span data-ttu-id="12c7b-117">Aby zobaczyć, jak koszty przepływają do poszczególnych centrów kosztów, należy zaimportować elementy członkowskie wymiaru obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="12c7b-117">To see how costs flow to the individual cost centers, you must import the cost object dimension members.</span></span> <span data-ttu-id="12c7b-118">W tym przypadku elementy członkowskie wymiaru obiektów kosztów są rzeczywistymi centrami kosztów, takimi jak Sprzedaż, Produkcja, Administracja i Lokalizacje geograficzne.</span><span class="sxs-lookup"><span data-stu-id="12c7b-118">In this case, the cost object dimension members are the actual cost centers, such as Sales, Production, Administration, and Geographic locations.</span></span> <span data-ttu-id="12c7b-119">Poniższy zrzut ekranu przedstawia przykład centrów kosztów jako wymiaru obiektów kosztów, gdzie faktyczne centra kosztów są elementami członkowskimi wymiaru obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="12c7b-119">The following screenshot shows an example of Cost Centers as the cost object dimension with its actual cost centers as cost object dimension members.</span></span> 

<span data-ttu-id="12c7b-120">[![cost-object-dimensions](./media/cost-object-dimensions.png)](./media/cost-object-dimensions.png)</span><span class="sxs-lookup"><span data-stu-id="12c7b-120">[![cost-object-dimensions](./media/cost-object-dimensions.png)](./media/cost-object-dimensions.png)</span></span>

## <a name="import-cost-object-dimension-members-through-data-connectors"></a><span data-ttu-id="12c7b-121">Importowanie elementów członkowskich wymiarów obiektów kosztów za pośrednictwem łączników danych</span><span class="sxs-lookup"><span data-stu-id="12c7b-121">Import cost object dimension members through data connectors</span></span>
<span data-ttu-id="12c7b-122">Aby ułatwić sobie importowania elementów członkowskich wymiarów obiektów kosztów, można za pomocą łączników danych pobierać wartości z jednostek, które mają zostać użyte jako wymiary obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="12c7b-122">To make the import of cost object dimension members easier, you use data connectors to retrieve the values from the entities that you want to use as cost object dimensions.</span></span> <span data-ttu-id="12c7b-123">Można używać łączników danych wbudowanych w systemie lub łączników niestandardowych, utworzonych przez siebie.</span><span class="sxs-lookup"><span data-stu-id="12c7b-123">You can use either the pre-built data connectors or custom data connectors that you build.</span></span>



