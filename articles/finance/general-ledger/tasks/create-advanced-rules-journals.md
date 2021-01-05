---
title: Tworzenie reguł zaawansowanych dla arkuszy
description: Ta procedura prowadzi przez proces tworzenia zaawansowanych reguł dla arkuszy.
author: aprilolson
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalControl, CompanyLookup, LedgerJournalPostControl
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ea6ca24d27bb5b00bbe31060ce2f7e40bf2fb335
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446875"
---
# <a name="create-advanced-rules-for-journals"></a><span data-ttu-id="50769-103">Tworzenie reguł zaawansowanych dla arkuszy</span><span class="sxs-lookup"><span data-stu-id="50769-103">Create advanced rules for journals</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="50769-104">Ta procedura prowadzi przez proces tworzenia zaawansowanych reguł dla arkuszy.</span><span class="sxs-lookup"><span data-stu-id="50769-104">This procedure steps through creating advanced rules for journals.</span></span> <span data-ttu-id="50769-105">Obejmuje skonfigurowanie kontroli arkusza i ograniczeń księgowania dla użytkowników.</span><span class="sxs-lookup"><span data-stu-id="50769-105">This includes setting up journal control and user posting restrictions.</span></span> <span data-ttu-id="50769-106">Procedura wykorzystuje dane firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="50769-106">This procedure uses the USMF demo data company.</span></span>


## <a name="set-up-journal-control"></a><span data-ttu-id="50769-107">Konfigurowanie kontroli arkusza</span><span class="sxs-lookup"><span data-stu-id="50769-107">Set up journal control</span></span>
1. <span data-ttu-id="50769-108">W **Okienku nawigacji** otwórz **Moduły > Księga główna > Konfiguracja arkusza > Nazwy arkuszy**.</span><span class="sxs-lookup"><span data-stu-id="50769-108">In the **Navigation pane**, go to **Modules > General ledger > Journal setup > Journal names**.</span></span>
2. <span data-ttu-id="50769-109">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="50769-109">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="50769-110">W **Okienku akcji** kliknij **Kontrola arkusza**.</span><span class="sxs-lookup"><span data-stu-id="50769-110">On the **Action pane**, click **Journal control**.</span></span>
4. <span data-ttu-id="50769-111">W formularzu można zaksięgować skróconej karcie **Na jakiego typu kontach można księgować** kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="50769-111">In the **Which account types can be posted** fastTab, click **Add**.</span></span>
5. <span data-ttu-id="50769-112">W polu **Firmy** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="50769-112">In the **Company accounts** field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="50769-113">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="50769-113">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="50769-114">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="50769-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="50769-115">Na skróconej karcie **Które wartości segmentów są dozwolone dla tego arkusza** kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="50769-115">In the **Which segment values are valid for this journal** fastTab, click **Add**.</span></span>
9. <span data-ttu-id="50769-116">W polu **Struktura konta** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="50769-116">In the **Account structure** field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="50769-117">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="50769-117">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="50769-118">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="50769-118">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="50769-119">W polu **Segment** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="50769-119">In the **Segment** field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="50769-120">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="50769-120">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="50769-121">W polu **Od wartości** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="50769-121">In the **From value** field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="50769-122">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="50769-122">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="50769-123">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="50769-123">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="50769-124">W polu **Do wartości** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="50769-124">In the **To value** field, click the drop-down button to open the lookup.</span></span>
18. <span data-ttu-id="50769-125">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="50769-125">In the list, find and select the desired record.</span></span>
19. <span data-ttu-id="50769-126">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="50769-126">In the list, click the link in the selected row.</span></span>

## <a name="set-up-posting-restrictions"></a><span data-ttu-id="50769-127">Konfigurowanie ograniczeń księgowania</span><span class="sxs-lookup"><span data-stu-id="50769-127">Set up posting restrictions</span></span>
1. <span data-ttu-id="50769-128">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="50769-128">Close the page.</span></span>
2. <span data-ttu-id="50769-129">Kliknij opcję **Ograniczenia księgowania**.</span><span class="sxs-lookup"><span data-stu-id="50769-129">Click **Posting restrictions**.</span></span>
3. <span data-ttu-id="50769-130">W polu **Jak chcesz skonfigurować ograniczenia księgowania** wybierz opcję „Według grupy użytkowników”.</span><span class="sxs-lookup"><span data-stu-id="50769-130">In the **How do you want to set up posting restrictions** field, select 'By user group'.</span></span>
4. <span data-ttu-id="50769-131">W drzewie zaznacz grupę, której chcesz pozwolić na księgowanie w tym arkuszu.</span><span class="sxs-lookup"><span data-stu-id="50769-131">In the tree, check 'the group that you want to allow posting for this journal name.'.</span></span>
5. <span data-ttu-id="50769-132">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="50769-132">Click **OK**.</span></span>

