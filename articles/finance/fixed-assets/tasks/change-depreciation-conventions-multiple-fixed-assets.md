---
title: Zmiana konwencji amortyzacji dla wielu środków trwałych
description: To zadanie aktualizuje konwencję amortyzacji dla wybranej grupy środków trwałych.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysQueryForm, SrsReportViewerForm
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 39930134782b40de05a92a6ad51c4f628f304a78
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446655"
---
# <a name="change-depreciation-conventions-for-multiple-fixed-assets"></a><span data-ttu-id="250e0-103">Zmiana konwencji amortyzacji dla wielu środków trwałych</span><span class="sxs-lookup"><span data-stu-id="250e0-103">Change depreciation conventions for multiple fixed assets</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="250e0-104">To zadanie aktualizuje konwencję amortyzacji dla wybranej grupy środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="250e0-104">This task updates the depreciation convention for a specified fixed asset group.</span></span> <span data-ttu-id="250e0-105">W tym przewodniku po zadaniach jest wykorzystywana firma demonstracyjna USMF.</span><span class="sxs-lookup"><span data-stu-id="250e0-105">This task guide uses the USMF demo company.</span></span>

1. <span data-ttu-id="250e0-106">Wybierz kolejno opcje Środki trwałe > Zadania okresowe > Aktualizacja grupowa.</span><span class="sxs-lookup"><span data-stu-id="250e0-106">Go to Fixed assets > Periodic tasks > Mass update</span></span>
2. <span data-ttu-id="250e0-107">W polu Księga amortyzacji kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="250e0-107">In the Depreciation book field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="250e0-108">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="250e0-108">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="250e0-109">W polu Rozpoczęcie eksploatacji wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="250e0-109">In the Placed in service start field, enter a date.</span></span>
5. <span data-ttu-id="250e0-110">W polu Zakończenie eksploatacji wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="250e0-110">In the Placed in service end field, enter a date.</span></span>
    * <span data-ttu-id="250e0-111">Aktualizacji podlegają tylko składniki aktywów, które są częścią wybranej księgi amortyzacji i zostały włączone do eksploatacji w okresie wyznaczonym tymi datami.</span><span class="sxs-lookup"><span data-stu-id="250e0-111">Only assets that are a part of the select depreciation book and that have been placed in service between these dates will be updated.</span></span>  
6. <span data-ttu-id="250e0-112">W polu Bieżąca konwencja amortyzacji wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="250e0-112">In the Current depreciation convention field, select an option.</span></span>
    * <span data-ttu-id="250e0-113">Aktualizacja obejmie tylko składniki aktywów, które mają bieżącą konwencję amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="250e0-113">Only assets that have the current depreciation convention will be updated.</span></span>  
7. <span data-ttu-id="250e0-114">W polu Nowa konwencja amortyzacji wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="250e0-114">In the New depreciation convention field, select an option.</span></span>
    * <span data-ttu-id="250e0-115">Sprawdź, czy raport będzie drukowany w żądanym miejscu docelowym.</span><span class="sxs-lookup"><span data-stu-id="250e0-115">Verify the report will print to the desired destination.</span></span>  
8. <span data-ttu-id="250e0-116">Rozwiń sekcję Rekordy do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="250e0-116">Expand the Records to include section.</span></span>
9. <span data-ttu-id="250e0-117">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="250e0-117">Click Filter.</span></span>
10. <span data-ttu-id="250e0-118">Na liście zaznacz grupę środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="250e0-118">In the list, select the Fixed asset group.</span></span>
11. <span data-ttu-id="250e0-119">W polu Kryteria kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="250e0-119">In the Criteria field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="250e0-120">Zaznacz żądaną grupę środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="250e0-120">Select the desired Fixed asset group.</span></span>
13. <span data-ttu-id="250e0-121">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="250e0-121">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="250e0-122">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="250e0-122">Click OK.</span></span>
15. <span data-ttu-id="250e0-123">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="250e0-123">Click OK.</span></span>
    *  <span data-ttu-id="250e0-124">Wyniki procesu są wyświetlane w raporcie Aktualizacja grupowa.</span><span class="sxs-lookup"><span data-stu-id="250e0-124">Results of the process are shown on the Mass update report.</span></span>     

