---
title: Tworzenie zamówienia sprzedaży dla konfigurowalnego produktu
description: Ta procedura pokazuje sposób zastosowania szablonu konfiguracji do produktu w zamówieniu sprzedaży.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, PCRuntimeConfigurator, PCTemplateConfigurationSelection
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8607de5705354aa58c985fb536f3e1d52acd1f37
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921296"
---
# <a name="create-a-sales-order-for-a-configurable-product"></a><span data-ttu-id="357ef-103">Tworzenie zamówienia sprzedaży dla konfigurowalnego produktu</span><span class="sxs-lookup"><span data-stu-id="357ef-103">Create a sales order for a configurable product</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="357ef-104">Ta procedura pokazuje sposób zastosowania szablonu konfiguracji do produktu w zamówieniu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="357ef-104">This procedure shows how to apply a configuration template to a product on a sales order.</span></span> <span data-ttu-id="357ef-105">W przykładzie użyto modelu głośnika D0006 zawartego w danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="357ef-105">This example uses the D0006 speaker model in the USMF demo data company.</span></span> <span data-ttu-id="357ef-106">Zazwyczaj z tej procedury korzysta osoba przetwarzająca zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="357ef-106">Typically, a sales order processor uses this procedure.</span></span>

## <a name="create-a-sales-order"></a><span data-ttu-id="357ef-107">Utwórz zamówienie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="357ef-107">Create a sales order</span></span>

1. <span data-ttu-id="357ef-108">Przejdź do lokalizacji **Sprzedaż i marketing \> Obszary robocze \> Przetwarzanie zamówienia sprzedaży i zapytania o nie**.</span><span class="sxs-lookup"><span data-stu-id="357ef-108">Go to **Sales and marketing \> Workspaces \> Sales order processing and inquiry**.</span></span>
1. <span data-ttu-id="357ef-109">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="357ef-109">Select **New**.</span></span>
1. <span data-ttu-id="357ef-110">Wybierz opcję **Zamówienie sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="357ef-110">Select **Sales order**.</span></span>
1. <span data-ttu-id="357ef-111">W polu **Konto odbiorcy** zaznacz wartość *US-001*.</span><span class="sxs-lookup"><span data-stu-id="357ef-111">In the **Customer account** field, select *US-001*.</span></span> 
1. <span data-ttu-id="357ef-112">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="357ef-112">Select **OK**.</span></span>
1. <span data-ttu-id="357ef-113">W polu **Numer pozycji** wybierz wartość *D0006*.</span><span class="sxs-lookup"><span data-stu-id="357ef-113">In the **Item number** field, select *D0006*.</span></span>
    * <span data-ttu-id="357ef-114">Dla tego zadania należy wybrać konfigurowalny produkt.</span><span class="sxs-lookup"><span data-stu-id="357ef-114">For this task, you must select a configurable product.</span></span>  
1. <span data-ttu-id="357ef-115">Wybierz opcję **Produkt i dostawa**.</span><span class="sxs-lookup"><span data-stu-id="357ef-115">Select **Product and supply**.</span></span>
1. <span data-ttu-id="357ef-116">Wybierz pozycję **Konfiguruj wiersz**.</span><span class="sxs-lookup"><span data-stu-id="357ef-116">Select **Configure line**.</span></span>
    * <span data-ttu-id="357ef-117">Należy zauważyć, że cena zmieniła się na podstawie wybranej konfiguracji, a pole **Uwzględnij kabel** jest teraz ustawiony na wartość *Prawda*.</span><span class="sxs-lookup"><span data-stu-id="357ef-117">Note that the price has changed, based on the configuration that was selected, and that the **Include cable** field is now set to *True*.</span></span>  
    * <span data-ttu-id="357ef-118">Zwróć uwagę na domyślną cenę i ustawienia wybrane dla kabla.</span><span class="sxs-lookup"><span data-stu-id="357ef-118">Note the default price and the settings that are selected for the cable.</span></span>  
1. <span data-ttu-id="357ef-119">Wybierz opcję **Szablon ładunku**.</span><span class="sxs-lookup"><span data-stu-id="357ef-119">Select **Load template**.</span></span>
    * <span data-ttu-id="357ef-120">W tym przykładzie pokazano, jak można zastosować szablon w celu wybrania wstępnie zdefiniowanej konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="357ef-120">This example shows how you can apply a template to select a predefined configuration.</span></span> <span data-ttu-id="357ef-121">Jeśli używasz tej procedury jako przewodnika po zadaniu i chcesz widzieć inne dostępne wartości atrybutów, musisz nacisnąć przycisk **Odblokuj**.</span><span class="sxs-lookup"><span data-stu-id="357ef-121">If you're using this procedure as a task guide and want to see the other attribute values that are available, you must select the **Unlock** button.</span></span>  
1. <span data-ttu-id="357ef-122">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="357ef-122">Select **OK**.</span></span>
1. <span data-ttu-id="357ef-123">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="357ef-123">Select **OK**.</span></span>
1. <span data-ttu-id="357ef-124">Rozwiń sekcję **Szczegóły wiersza**.</span><span class="sxs-lookup"><span data-stu-id="357ef-124">Expand the **Line details** section.</span></span>
1. <span data-ttu-id="357ef-125">Wybierz kartę **Produkt**.</span><span class="sxs-lookup"><span data-stu-id="357ef-125">Select the **Product** tab.</span></span>
    * <span data-ttu-id="357ef-126">Konfiguracja towaru jest teraz wyświetlana w obszarze wymiarów produktu.</span><span class="sxs-lookup"><span data-stu-id="357ef-126">The configuration of the item is now listed under the product dimensions.</span></span>  
1. <span data-ttu-id="357ef-127">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="357ef-127">Close the page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]