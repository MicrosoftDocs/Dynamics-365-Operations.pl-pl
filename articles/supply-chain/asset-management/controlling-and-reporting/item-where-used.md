---
title: Używająca pozycja
description: W tym temacie opisano sposób uzyskiwania przeglądu miejsca użycia towaru w Zarządzaniu składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetItemWhereUsed, EntAssetItemWhereUsedCalculate
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: db0932c5a52030c1a7f0411163aee120e2173ca0
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021146"
---
# <a name="item-where-used"></a><span data-ttu-id="804d0-103">Używająca pozycja</span><span class="sxs-lookup"><span data-stu-id="804d0-103">Item where used</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="804d0-104">Można dokonać obliczeń dla konkretnego towaru, aby uzyskać przegląd informacji o miejscu użycia towaru w module Zarządzanie składnikami majątku.</span><span class="sxs-lookup"><span data-stu-id="804d0-104">You can make a calculation for a specific item to get an overview of where in Asset Management the item has been used.</span></span> <span data-ttu-id="804d0-105">Wyniki zawierają kontekst, w którym towar został użyty w czasie jego istnienia.</span><span class="sxs-lookup"><span data-stu-id="804d0-105">The results show the context in which the item has been used during its lifetime.</span></span> <span data-ttu-id="804d0-106">Stronę **Używająca pozycja** można otworzyć z głównego menu modułu Zarządzanie składnikami majątku, a także uzyskać do niej dostęp z następujących stron:</span><span class="sxs-lookup"><span data-stu-id="804d0-106">The **Item where used** page can be opened from the main Asset Management menu, and it can also be accessed from the following pages:</span></span>

- [<span data-ttu-id="804d0-107">Obiekty BOM składnika majątku</span><span class="sxs-lookup"><span data-stu-id="804d0-107">Asset BOMs</span></span>](../objects/object-BOM.md)

- [<span data-ttu-id="804d0-108">Części zamienne w domyślnym typie składnika majątku</span><span class="sxs-lookup"><span data-stu-id="804d0-108">Spare parts on asset type defaults</span></span>](../setup-for-objects/object-types.md#spare-parts-on-the-asset-type-setup)

- [<span data-ttu-id="804d0-109">Kategorie typów zadań obsługi i typy zadań serwisowych, warianty typu zadań obsługi, handel zadaniami konserwacyjnymi oraz listy kontrolne konserwacji</span><span class="sxs-lookup"><span data-stu-id="804d0-109">Maintenance job type categories and maintenance job types, maintenance job type variants, maintenance job trades, and maintenance checklists</span></span>](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md)

- [<span data-ttu-id="804d0-110">Prognoza konserwacji</span><span class="sxs-lookup"><span data-stu-id="804d0-110">Maintenance forecast</span></span>](../work-orders/maintenance-forecasts.md)

- [<span data-ttu-id="804d0-111">Zaopatrzenie</span><span class="sxs-lookup"><span data-stu-id="804d0-111">Procurement</span></span>](../work-orders/procurement.md)

- [<span data-ttu-id="804d0-112">Zakup zlecenia pracy</span><span class="sxs-lookup"><span data-stu-id="804d0-112">Work order purchase</span></span>](../work-orders/procurement.md)

## <a name="make-an-item-where-used-calculation"></a><span data-ttu-id="804d0-113">Umożliwia obliczanie użycia pozycji w miejscu</span><span class="sxs-lookup"><span data-stu-id="804d0-113">Make an item-where-used calculation</span></span>

1. <span data-ttu-id="804d0-114">Kliknij **Zarządzanie składnikami majątku** > **Zapytania** > **Używająca pozycja** lub wybierz **Używająca pozycja** na jednej ze stron wymienionych powyżej.</span><span class="sxs-lookup"><span data-stu-id="804d0-114">Click **Asset management** > **Inquiries** > **Item where used**, or select the **Item where used** button on one of the pages mentioned above.</span></span>

2. <span data-ttu-id="804d0-115">W oknie **Używająca pozycja** wybierz towar, dla którego chcesz dokonać obliczeń w polu **Kod towaru** .</span><span class="sxs-lookup"><span data-stu-id="804d0-115">In the **Item where used** dialog, select the item for which you want to make the calculation in the **Item number** field.</span></span>

3. <span data-ttu-id="804d0-116">Pola **Poziom** można użyć, aby wskazać, jak szczegółowe mają być wiersze dla pozycji dotyczące lokalizacji czynności konserwacyjnych.</span><span class="sxs-lookup"><span data-stu-id="804d0-116">You can use the **Level** field to indicate how detailed you want the item lines to be regarding functional locations.</span></span> 

    <span data-ttu-id="804d0-117">Jeśli na przykład w polu zostanie wstawiony numer „1”, a istnieje struktura lokalizacji funkcjonalnej z wieloma poziomami, wszystkie wiersze pozycji dla lokalizacji funkcjonalnej będą wyświetlane na najwyższym poziomie.</span><span class="sxs-lookup"><span data-stu-id="804d0-117">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all item lines for a functional location will be shown on the top level.</span></span> <span data-ttu-id="804d0-118">Relacja/ilość w wierszu można więc dodać z lokalizacji funkcjonalnych znajdujących się na niższym poziomie.</span><span class="sxs-lookup"><span data-stu-id="804d0-118">Therefore, relation/quantity on a line may be added up from functional locations located at a lower level.</span></span> 
    
    <span data-ttu-id="804d0-119">W przypadku wstawienia liczby „0” w polu **Poziom** zostanie wyświetlony szczegółowy wynik zawierający wszystkie wiersze pozycji na każdym poziomie lokalizacji czynności konserwacyjnych, z którymi są powiązane.</span><span class="sxs-lookup"><span data-stu-id="804d0-119">If you insert the number "0" in the **Level** field, you will see a detailed result showing all item lines on all the functional location levels to which they are related.</span></span>

4. <span data-ttu-id="804d0-120">Należy wybrać wartość „tak” na przełączniku, który ma być uwzględniony w obliczeniach w sekcji **Uwzględnij**.</span><span class="sxs-lookup"><span data-stu-id="804d0-120">In the **Include** section, select "Yes" on the toggle buttons that you want to include in the calculation.</span></span>

5. <span data-ttu-id="804d0-121">Kliknij przycisk **OK**, aby rozpocząć obliczanie.</span><span class="sxs-lookup"><span data-stu-id="804d0-121">Click **OK** to start the calculation.</span></span>

6. <span data-ttu-id="804d0-122">Na karcie **Używająca pozycja** wybierz przyciski **Grupuj wg**, aby wyświetlić wymagany poziom szczegółowości obliczania.</span><span class="sxs-lookup"><span data-stu-id="804d0-122">On the **Item where used** tab, select the **Group by** buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="804d0-123">Wybrane przyciski grupy **Grupuj wg...** są wyróżnione.</span><span class="sxs-lookup"><span data-stu-id="804d0-123">The selected **Group by** buttons are highlighted.</span></span> <span data-ttu-id="804d0-124">Aby uaktywnić lub dezaktywować przycisk, należy go kliknąć.</span><span class="sxs-lookup"><span data-stu-id="804d0-124">Click on a button to activate or deactivate it.</span></span>

7. <span data-ttu-id="804d0-125">Aby wyświetlić wymiary powiązane z danym towarem, kliknij przycisk **Wyświetl wymiary** i wybierz wymiary, które mają zostać wyświetlone.</span><span class="sxs-lookup"><span data-stu-id="804d0-125">If you want to show dimensions related to the item, click **Display dimensions**, and select the dimensions to be shown.</span></span>

## <a name="example"></a><span data-ttu-id="804d0-126">Przykład</span><span class="sxs-lookup"><span data-stu-id="804d0-126">Example</span></span>

<span data-ttu-id="804d0-127">Na poniższym zrzucie ekranu widać przykład obliczeń dla pozycji używającej towaru o kodzie „1000”.</span><span class="sxs-lookup"><span data-stu-id="804d0-127">In the screenshot below, you see an example of an item-where-used calculation for item number "1000".</span></span>

![Przykład obliczenia dla używającej pozycji](media/12-controlling-and-reporting.png)

