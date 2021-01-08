---
title: Tworzenie zamówienia sprzedaży dla konfigurowalnego produktu
description: Ta procedura pokazuje sposób zastosowania szablonu konfiguracji do produktu w zamówieniu sprzedaży.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, PCRuntimeConfigurator, PCTemplateConfigurationSelection
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 988d87757019d20dcaf675af925166ed376685f5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435215"
---
# <a name="create-a-sales-order-for-a-configurable-product"></a><span data-ttu-id="560da-103">Tworzenie zamówienia sprzedaży dla konfigurowalnego produktu</span><span class="sxs-lookup"><span data-stu-id="560da-103">Create a sales order for a configurable product</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="560da-104">Ta procedura pokazuje sposób zastosowania szablonu konfiguracji do produktu w zamówieniu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="560da-104">This procedure shows how to apply a configuration template to a product on a sales order.</span></span> <span data-ttu-id="560da-105">W przykładzie użyto modelu głośnika D0006 zawartego w danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="560da-105">This example uses the D0006 speaker model in the USMF demo data company.</span></span> <span data-ttu-id="560da-106">Zazwyczaj z tej procedury korzysta osoba przetwarzająca zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="560da-106">Typically, a sales order processor uses this procedure.</span></span>


## <a name="create-a-sales-order"></a><span data-ttu-id="560da-107">Utwórz zamówienie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="560da-107">Create a sales order</span></span>
1. <span data-ttu-id="560da-108">Kliknij opcję Przetwarzanie zamówienia sprzedaży i dotyczące go zapytania.</span><span class="sxs-lookup"><span data-stu-id="560da-108">Click Sales order processing and inquiry.</span></span>
2. <span data-ttu-id="560da-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="560da-109">Click New.</span></span>
3. <span data-ttu-id="560da-110">Kliknij opcję zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="560da-110">Click Sales order.</span></span>
4. <span data-ttu-id="560da-111">W polu Konto odbiorcy zaznacz wartość US-001.</span><span class="sxs-lookup"><span data-stu-id="560da-111">In the Customer account field, select US-001.</span></span> 
5. <span data-ttu-id="560da-112">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="560da-112">Click OK.</span></span>
6. <span data-ttu-id="560da-113">W polu Numer pozycji wybierz wartość D0006.</span><span class="sxs-lookup"><span data-stu-id="560da-113">In the Item number field, select D0006.</span></span>
    * <span data-ttu-id="560da-114">Dla tego zadania należy wybrać konfigurowalny produkt.</span><span class="sxs-lookup"><span data-stu-id="560da-114">For this task, you must select a configurable product.</span></span>  
7. <span data-ttu-id="560da-115">Kliknij opcję Produkt i dostawa.</span><span class="sxs-lookup"><span data-stu-id="560da-115">Click Product and supply.</span></span>
8. <span data-ttu-id="560da-116">Kliknij opcję Konfiguruj wiersz.</span><span class="sxs-lookup"><span data-stu-id="560da-116">Click Configure line.</span></span>
    * <span data-ttu-id="560da-117">Należy zauważyć, że cena zmieniła się na podstawie wybranej konfiguracji, a pole Uwzględnij kabel jest teraz ustawiony na wartość Prawda.</span><span class="sxs-lookup"><span data-stu-id="560da-117">Note that the price has changed, based on the configuration that was selected, and that the Include cable field is now set to True.</span></span>  
    * <span data-ttu-id="560da-118">Zwróć uwagę na domyślną cenę i ustawienia wybrane dla kabla.</span><span class="sxs-lookup"><span data-stu-id="560da-118">Note the default price and the settings that are selected for the cable.</span></span>  
9. <span data-ttu-id="560da-119">Kliknij przycisk Szablon ładunku.</span><span class="sxs-lookup"><span data-stu-id="560da-119">Click Load template.</span></span>
    * <span data-ttu-id="560da-120">W tym przykładzie pokazano, jak można zastosować szablon w celu wybrania wstępnie zdefiniowanej konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="560da-120">This example shows how you can apply a template to select a predefined configuration.</span></span> <span data-ttu-id="560da-121">Jeśli używasz tej procedury jako przewodnika po zadaniu i chcesz widzieć inne dostępne wartości atrybutów, kliknij przycisk Odblokuj.</span><span class="sxs-lookup"><span data-stu-id="560da-121">If you're using this procedure as a task guide and want to see the other attribute values that are available, you must click the Unlock button.</span></span>  
10. <span data-ttu-id="560da-122">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="560da-122">Click OK.</span></span>
11. <span data-ttu-id="560da-123">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="560da-123">Click OK.</span></span>
12. <span data-ttu-id="560da-124">Rozwiń sekcję Szczegóły wiersza.</span><span class="sxs-lookup"><span data-stu-id="560da-124">Expand the Line details section.</span></span>
13. <span data-ttu-id="560da-125">Kliknij kartę Produkt.</span><span class="sxs-lookup"><span data-stu-id="560da-125">Click the Product tab.</span></span>
    * <span data-ttu-id="560da-126">Konfiguracja towaru jest teraz wyświetlana w obszarze wymiarów produktu.</span><span class="sxs-lookup"><span data-stu-id="560da-126">The configuration of the item is now listed under the product dimensions.</span></span>  
14. <span data-ttu-id="560da-127">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="560da-127">Close the page.</span></span>

## <a name="select-the-product-configuration"></a><span data-ttu-id="560da-128">Wybór konfiguracji produktu</span><span class="sxs-lookup"><span data-stu-id="560da-128">Select the product configuration</span></span>

