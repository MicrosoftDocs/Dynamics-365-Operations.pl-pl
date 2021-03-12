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
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9744f8a9abe16955b397f85ba731c4723c20b4ee
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985169"
---
# <a name="change-depreciation-conventions-for-multiple-fixed-assets"></a><span data-ttu-id="d49a2-103">Zmiana konwencji amortyzacji dla wielu środków trwałych</span><span class="sxs-lookup"><span data-stu-id="d49a2-103">Change depreciation conventions for multiple fixed assets</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d49a2-104">To zadanie aktualizuje konwencję amortyzacji dla wybranej grupy środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="d49a2-104">This task updates the depreciation convention for a specified fixed asset group.</span></span> <span data-ttu-id="d49a2-105">W tym przewodniku po zadaniach jest wykorzystywana firma demonstracyjna USMF.</span><span class="sxs-lookup"><span data-stu-id="d49a2-105">This task guide uses the USMF demo company.</span></span>

1. <span data-ttu-id="d49a2-106">Wybierz kolejno opcje Środki trwałe > Zadania okresowe > Aktualizacja grupowa.</span><span class="sxs-lookup"><span data-stu-id="d49a2-106">Go to Fixed assets > Periodic tasks > Mass update</span></span>
2. <span data-ttu-id="d49a2-107">W polu Księga amortyzacji kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="d49a2-107">In the Depreciation book field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="d49a2-108">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="d49a2-108">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="d49a2-109">W polu Rozpoczęcie eksploatacji wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="d49a2-109">In the Placed in service start field, enter a date.</span></span>
5. <span data-ttu-id="d49a2-110">W polu Zakończenie eksploatacji wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="d49a2-110">In the Placed in service end field, enter a date.</span></span>
    * <span data-ttu-id="d49a2-111">Aktualizacji podlegają tylko składniki aktywów, które są częścią wybranej księgi amortyzacji i zostały włączone do eksploatacji w okresie wyznaczonym tymi datami.</span><span class="sxs-lookup"><span data-stu-id="d49a2-111">Only assets that are a part of the select depreciation book and that have been placed in service between these dates will be updated.</span></span>  
6. <span data-ttu-id="d49a2-112">W polu Bieżąca konwencja amortyzacji wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="d49a2-112">In the Current depreciation convention field, select an option.</span></span>
    * <span data-ttu-id="d49a2-113">Aktualizacja obejmie tylko składniki aktywów, które mają bieżącą konwencję amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="d49a2-113">Only assets that have the current depreciation convention will be updated.</span></span>  
7. <span data-ttu-id="d49a2-114">W polu Nowa konwencja amortyzacji wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="d49a2-114">In the New depreciation convention field, select an option.</span></span>
    * <span data-ttu-id="d49a2-115">Sprawdź, czy raport będzie drukowany w żądanym miejscu docelowym.</span><span class="sxs-lookup"><span data-stu-id="d49a2-115">Verify the report will print to the desired destination.</span></span>  
8. <span data-ttu-id="d49a2-116">Rozwiń sekcję Rekordy do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="d49a2-116">Expand the Records to include section.</span></span>
9. <span data-ttu-id="d49a2-117">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="d49a2-117">Click Filter.</span></span>
10. <span data-ttu-id="d49a2-118">Na liście zaznacz grupę środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="d49a2-118">In the list, select the Fixed asset group.</span></span>
11. <span data-ttu-id="d49a2-119">W polu Kryteria kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="d49a2-119">In the Criteria field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="d49a2-120">Zaznacz żądaną grupę środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="d49a2-120">Select the desired Fixed asset group.</span></span>
13. <span data-ttu-id="d49a2-121">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="d49a2-121">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="d49a2-122">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="d49a2-122">Click OK.</span></span>
15. <span data-ttu-id="d49a2-123">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="d49a2-123">Click OK.</span></span>
    *  <span data-ttu-id="d49a2-124">Wyniki procesu są wyświetlane w raporcie Aktualizacja grupowa.</span><span class="sxs-lookup"><span data-stu-id="d49a2-124">Results of the process are shown on the Mass update report.</span></span>     

