---
title: Tworzenie wymiarów finansowych dla kanałów sprzedaży detalicznej i konfigurowanie wartości wymiarów w sklepach
description: Ta procedura prowadzi przez proces tworzenia wymiaru finansowego kanału handlu z wartościami wymiarów i krokami konfigurowania wartości wymiaru finansowego w sklepach.
author: jashanno
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 86fc9c9a400bee1280b32f10b1e8f55e581e1984
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4964752"
---
# <a name="create-financial-dimensions-for-retail-channels-and-configure-dimension-values-on-stores"></a><span data-ttu-id="66409-103">Tworzenie wymiarów finansowych dla kanałów sprzedaży detalicznej i konfigurowanie wartości wymiarów w sklepach</span><span class="sxs-lookup"><span data-stu-id="66409-103">Create financial dimensions for retail channels and configure dimension values on stores</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="66409-104">Ta procedura prowadzi przez proces tworzenia wymiaru finansowego kanału handlu z wartościami wymiarów i krokami konfigurowania wartości wymiaru finansowego w sklepach.</span><span class="sxs-lookup"><span data-stu-id="66409-104">This procedure walks through creating a commerce channel financial dimension with dimension values and steps to configure financial dimension values on stores.</span></span> <span data-ttu-id="66409-105">Temat nie ma innych czynności pokrewnych, takich jak tworzenie zestawów wymiarów i struktur kont.</span><span class="sxs-lookup"><span data-stu-id="66409-105">The topic does not include other related steps, such as creating dimension sets and account structures.</span></span> <span data-ttu-id="66409-106">Procedura wykorzystuje dane firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="66409-106">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="66409-107">Wybierz kolejno opcje Księga główna > Plan kont > Wymiary > Wymiary finansowe.</span><span class="sxs-lookup"><span data-stu-id="66409-107">Go to General ledger > Chart of accounts > Dimensions > Financial dimensions.</span></span>
2. <span data-ttu-id="66409-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="66409-108">Click New.</span></span>
3. <span data-ttu-id="66409-109">W polu Użyj wartości z wybierz opcję „Kanały Commerce”.</span><span class="sxs-lookup"><span data-stu-id="66409-109">In the Use values from field, select 'Commerce channels'.</span></span>
4. <span data-ttu-id="66409-110">W polu Wymiar menu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="66409-110">In the Dimension name field, type a value.</span></span>
5. <span data-ttu-id="66409-111">Kliknij Aktywacja.</span><span class="sxs-lookup"><span data-stu-id="66409-111">Click Activate.</span></span>
6. <span data-ttu-id="66409-112">Kliknij przycisk Zamknij.</span><span class="sxs-lookup"><span data-stu-id="66409-112">Click Close.</span></span>
7. <span data-ttu-id="66409-113">Kliknij Aktywacja.</span><span class="sxs-lookup"><span data-stu-id="66409-113">Click Activate.</span></span>
8. <span data-ttu-id="66409-114">Kliknij opcję Wartości wymiarów.</span><span class="sxs-lookup"><span data-stu-id="66409-114">Click Dimension values.</span></span>
9. <span data-ttu-id="66409-115">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="66409-115">Close the page.</span></span>
10. <span data-ttu-id="66409-116">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="66409-116">Click Save.</span></span>
11. <span data-ttu-id="66409-117">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="66409-117">Close the page.</span></span>
12. <span data-ttu-id="66409-118">Wybierz kolejno opcje Handel detaliczny i inny > Kanały > > Sklepy > Wszystkie sklepy.</span><span class="sxs-lookup"><span data-stu-id="66409-118">Go to Retail and Commerce > Channels > Stores > All stores.</span></span>
13. <span data-ttu-id="66409-119">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="66409-119">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="66409-120">Przełącz rozwinięcie sekcji Wymiary finansowe.</span><span class="sxs-lookup"><span data-stu-id="66409-120">Toggle the expansion of the Financial dimensions section.</span></span>
15. <span data-ttu-id="66409-121">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="66409-121">Click Edit.</span></span>
16. <span data-ttu-id="66409-122">W polu kanał Commerce kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="66409-122">In the Commerce channel field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="66409-123">Na liście znajdź i wybierz wartość wymiaru dla aktualizowanego sklepu.</span><span class="sxs-lookup"><span data-stu-id="66409-123">In the list, find and select the dimension value for the store being updated.</span></span>
18. <span data-ttu-id="66409-124">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="66409-124">In the list, click the link in the selected row.</span></span>
19. <span data-ttu-id="66409-125">W polu CostCenter kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="66409-125">In the CostCenter field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="66409-126">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="66409-126">In the list, find and select the desired record.</span></span>
21. <span data-ttu-id="66409-127">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="66409-127">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="66409-128">W polu Dział kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="66409-128">In the Department field, click the drop-down button to open the lookup.</span></span>
23. <span data-ttu-id="66409-129">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="66409-129">In the list, find and select the desired record.</span></span>
24. <span data-ttu-id="66409-130">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="66409-130">In the list, click the link in the selected row.</span></span>
25. <span data-ttu-id="66409-131">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="66409-131">Click Save.</span></span>

