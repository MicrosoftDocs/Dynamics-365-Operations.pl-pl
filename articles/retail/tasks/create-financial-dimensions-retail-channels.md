---
title: Tworzenie wymiarów finansowych dla kanałów sprzedaży detalicznej i konfigurowanie wartości wymiarów w sklepach
description: Ta procedura prowadzi przez proces tworzenia wymiaru finansowego kanału sprzedaży detalicznej z wartościami wymiarów i krokami konfigurowania wartości wymiaru finansowego w sklepach sieci sprzedaży.
author: jashanno
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cf32d17a36fd699141ce697d23e20b2eb5cbfa54
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "354536"
---
# <a name="create-financial-dimensions-for-retail-channels-and-configure-dimension-values-on-stores"></a><span data-ttu-id="f980c-103">Tworzenie wymiarów finansowych dla kanałów sprzedaży detalicznej i konfigurowanie wartości wymiarów w sklepach</span><span class="sxs-lookup"><span data-stu-id="f980c-103">Create financial dimensions for retail channels and configure dimension values on stores</span></span>

[!include [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="f980c-104">Ta procedura prowadzi przez proces tworzenia wymiaru finansowego kanału sprzedaży detalicznej z wartościami wymiarów i krokami konfigurowania wartości wymiaru finansowego w sklepach sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f980c-104">This procedure walks through creating a retail channel financial dimension with dimension values and steps to configure financial dimension values on retail stores.</span></span> <span data-ttu-id="f980c-105">Temat nie ma innych czynności pokrewnych, takich jak tworzenie zestawów wymiarów i struktur kont.</span><span class="sxs-lookup"><span data-stu-id="f980c-105">The topic does not include other related steps, such as creating dimension sets and account structures.</span></span> <span data-ttu-id="f980c-106">Procedura wykorzystuje dane firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="f980c-106">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="f980c-107">Wybierz kolejno opcje Księga główna > Plan kont > Wymiary > Wymiary finansowe.</span><span class="sxs-lookup"><span data-stu-id="f980c-107">Go to General ledger > Chart of accounts > Dimensions > Financial dimensions.</span></span>
2. <span data-ttu-id="f980c-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="f980c-108">Click New.</span></span>
3. <span data-ttu-id="f980c-109">W polu Użyj wartości z wybierz opcję „Kanały sprzedaży detalicznej”.</span><span class="sxs-lookup"><span data-stu-id="f980c-109">In the Use values from field, select 'Retail channels'.</span></span>
4. <span data-ttu-id="f980c-110">W polu Wymiar menu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="f980c-110">In the Dimension name field, type a value.</span></span>
5. <span data-ttu-id="f980c-111">Kliknij Aktywacja.</span><span class="sxs-lookup"><span data-stu-id="f980c-111">Click Activate.</span></span>
6. <span data-ttu-id="f980c-112">Kliknij przycisk Zamknij.</span><span class="sxs-lookup"><span data-stu-id="f980c-112">Click Close.</span></span>
7. <span data-ttu-id="f980c-113">Kliknij Aktywacja.</span><span class="sxs-lookup"><span data-stu-id="f980c-113">Click Activate.</span></span>
8. <span data-ttu-id="f980c-114">Kliknij opcję Wartości wymiarów.</span><span class="sxs-lookup"><span data-stu-id="f980c-114">Click Dimension values.</span></span>
9. <span data-ttu-id="f980c-115">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f980c-115">Close the page.</span></span>
10. <span data-ttu-id="f980c-116">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="f980c-116">Click Save.</span></span>
11. <span data-ttu-id="f980c-117">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f980c-117">Close the page.</span></span>
12. <span data-ttu-id="f980c-118">Wybierz kolejno opcje Handel detaliczny i inny > Kanały > Sklepy sieci sprzedaży > Wszystkie sklepy sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f980c-118">Go to Retail and commerce > Channels > Retail stores > All retail stores.</span></span>
13. <span data-ttu-id="f980c-119">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="f980c-119">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="f980c-120">Przełącz rozwinięcie sekcji Wymiary finansowe.</span><span class="sxs-lookup"><span data-stu-id="f980c-120">Toggle the expansion of the Financial dimensions section.</span></span>
15. <span data-ttu-id="f980c-121">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="f980c-121">Click Edit.</span></span>
16. <span data-ttu-id="f980c-122">W polu Kanał sprzedaży detalicznej kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="f980c-122">In the Retailchannel field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="f980c-123">Na liście znajdź i wybierz wartość wymiaru dla aktualizowanego sklepu.</span><span class="sxs-lookup"><span data-stu-id="f980c-123">In the list, find and select the dimension value for the store being updated.</span></span>
18. <span data-ttu-id="f980c-124">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="f980c-124">In the list, click the link in the selected row.</span></span>
19. <span data-ttu-id="f980c-125">W polu CostCenter kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="f980c-125">In the CostCenter field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="f980c-126">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="f980c-126">In the list, find and select the desired record.</span></span>
21. <span data-ttu-id="f980c-127">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="f980c-127">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="f980c-128">W polu Dział kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="f980c-128">In the Department field, click the drop-down button to open the lookup.</span></span>
23. <span data-ttu-id="f980c-129">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="f980c-129">In the list, find and select the desired record.</span></span>
24. <span data-ttu-id="f980c-130">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="f980c-130">In the list, click the link in the selected row.</span></span>
25. <span data-ttu-id="f980c-131">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="f980c-131">Click Save.</span></span>

