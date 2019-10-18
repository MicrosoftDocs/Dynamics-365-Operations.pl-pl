---
title: Dodawanie do swojego arkusza wydajności i wysyłanie pochwały innej osobie
description: Arkusz wydajności przechowuje informacje, które odnoszą się do sposobu osiągania celów lub efektywności działania w okresie.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EssWorkspace, HcmPerfJournal, HcmPerfJournalAddLink, HcmPerfPraise, HcmWorkerLookUpByPerson, HcmPerfJournalAdd
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0f2f8e0e858a27bec09eee6f7f02dc952fe8e408
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2190725"
---
# <a name="add-to-your-performance-journal-and-send-praise-to-someone"></a><span data-ttu-id="0107e-103">Dodawanie do swojego arkusza wydajności i wysyłanie pochwały innej osobie</span><span class="sxs-lookup"><span data-stu-id="0107e-103">Add to your performance journal and send praise to someone</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0107e-104">Arkusz wydajności przechowuje informacje, które odnoszą się do sposobu osiągania celów lub efektywności działania w okresie.</span><span class="sxs-lookup"><span data-stu-id="0107e-104">The performance journal holds information that relates to how you met your goals or how you performed during a period.</span></span> <span data-ttu-id="0107e-105">Z arkusza można także pochwalić działania współpracownika.</span><span class="sxs-lookup"><span data-stu-id="0107e-105">You can also praise the actions of a co-worker from the journal.</span></span> <span data-ttu-id="0107e-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="0107e-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="0107e-107">Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="0107e-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="0107e-108">Wybierz kolejno opcje Wszystkie obszary robocze > Samoobsługa pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="0107e-108">Go to All workspaces > Employee self service.</span></span>
2. <span data-ttu-id="0107e-109">Kliknij opcję Arkusz wydajności.</span><span class="sxs-lookup"><span data-stu-id="0107e-109">Click Performance journal.</span></span>
3. <span data-ttu-id="0107e-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="0107e-110">Click New.</span></span>
4. <span data-ttu-id="0107e-111">W polu Tytuł wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0107e-111">In the Title field, type a value.</span></span>
5. <span data-ttu-id="0107e-112">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="0107e-112">In the Description field, type a value.</span></span>
    * <span data-ttu-id="0107e-113">Datą arkusza wydajności jest dzień, w którym został utworzony arkusz.</span><span class="sxs-lookup"><span data-stu-id="0107e-113">The performance journal date is the date that the journal was created.</span></span>  
    * <span data-ttu-id="0107e-114">Źródło pokazuje, skąd pochodzi dziennik wydajności.</span><span class="sxs-lookup"><span data-stu-id="0107e-114">The source represents where the performance journal came from.</span></span> <span data-ttu-id="0107e-115">Jeśli Ty go tworzysz, pochodzi z okna Mój arkusz.</span><span class="sxs-lookup"><span data-stu-id="0107e-115">When you create one, it comes from My journal.</span></span> <span data-ttu-id="0107e-116">Jeśli tworzy go Twój kierownik, pochodzi z okna Arkusz menedżera.</span><span class="sxs-lookup"><span data-stu-id="0107e-116">If your manager creates one, it comes from the Manager journal.</span></span>  
    * <span data-ttu-id="0107e-117">Możesz udostępnić ten arkusz swojemu kierownikowi lub sprawić, że będzie widoczny tylko dla Ciebie.</span><span class="sxs-lookup"><span data-stu-id="0107e-117">You can share this journal with your manager or make it only visible to you.</span></span>  
6. <span data-ttu-id="0107e-118">W polu Data początkowa wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="0107e-118">In the Start date field, enter a date.</span></span>
7. <span data-ttu-id="0107e-119">W polu Data ukończenia wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="0107e-119">In the Date completed field, enter a date.</span></span>
8. <span data-ttu-id="0107e-120">W polu Plan rozwoju wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="0107e-120">Select Yes in the Development plan field.</span></span>
9. <span data-ttu-id="0107e-121">W polu Słowa kluczowe wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0107e-121">In the Keywords field, type a value.</span></span>
10. <span data-ttu-id="0107e-122">Kliknij opcję Dodaj łącze zewnętrzne.</span><span class="sxs-lookup"><span data-stu-id="0107e-122">Click Add external link.</span></span>
11. <span data-ttu-id="0107e-123">W polu Opis wpisz „Envision”.</span><span class="sxs-lookup"><span data-stu-id="0107e-123">In the Description field, type 'Envision'.</span></span>
12. <span data-ttu-id="0107e-124">W polu Adres internetowy wpisz wartość „https://www.microsoft.com/en/envision/default”.</span><span class="sxs-lookup"><span data-stu-id="0107e-124">In the Internet address field, type 'https://www.microsoft.com/en/envision/default'.</span></span>
13. <span data-ttu-id="0107e-125">Kliknij napis poniżej przycisku Zapisz zatytułowany „Arkusz wydajności”, aby powrócić do siatki.</span><span class="sxs-lookup"><span data-stu-id="0107e-125">Click on the caption below the Save button called "Performance journal" to return to the grid.</span></span>
    * <span data-ttu-id="0107e-126">Wybrany arkusz lub arkusze można dodać do celu, tak aby były wyświetlane po otwarciu celu.</span><span class="sxs-lookup"><span data-stu-id="0107e-126">You can add the selected journal or journals to a goal so that it appears when you open the goal.</span></span> <span data-ttu-id="0107e-127">Na skróconej karcie Łącza zostanie dodane łącze. Jeśli dodasz arkusz do celu, a następnie dodasz cel do przeglądu, arkusz pojawi się w przeglądzie automatycznie.</span><span class="sxs-lookup"><span data-stu-id="0107e-127">A link will be added in the Links fast tab.    If you add a journal to a goal and then add the goal to a review, the journal will appear on the review automatically.</span></span>  
    * <span data-ttu-id="0107e-128">Wybrany arkusz lub arkusze można dodać do przeglądu, tak aby były wyświetlane po otwarciu przeglądu.</span><span class="sxs-lookup"><span data-stu-id="0107e-128">You can add the selected journal or journals to a review so that it appears when you open the review.</span></span>    <span data-ttu-id="0107e-129">Na skróconej karcie Łącza zostanie dodane łącze.</span><span class="sxs-lookup"><span data-stu-id="0107e-129">A link will be added in the Links fast tab.</span></span>  
14. <span data-ttu-id="0107e-130">Kliknij opcję Dodaj szybko.</span><span class="sxs-lookup"><span data-stu-id="0107e-130">Click Quick add.</span></span>
15. <span data-ttu-id="0107e-131">W polu Tytuł wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0107e-131">In the Title field, type a value.</span></span>
16. <span data-ttu-id="0107e-132">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="0107e-132">In the Description field, type a value.</span></span>
17. <span data-ttu-id="0107e-133">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="0107e-133">Click Save.</span></span>
18. <span data-ttu-id="0107e-134">Kliknij opcję Wyślij pochwałę.</span><span class="sxs-lookup"><span data-stu-id="0107e-134">Click Send praise.</span></span>
19. <span data-ttu-id="0107e-135">Zaznacz osobę na liście pracowników firmy.</span><span class="sxs-lookup"><span data-stu-id="0107e-135">Select a person from the list of employees in the company.</span></span>
20. <span data-ttu-id="0107e-136">W polu Opis wpisz „Dziękuję za całą pomoc podczas konferencji!”.</span><span class="sxs-lookup"><span data-stu-id="0107e-136">In the Description field, enter 'Thanks for all the help at the conference!'.</span></span>
21. <span data-ttu-id="0107e-137">Kliknij przycisk Wyślij.</span><span class="sxs-lookup"><span data-stu-id="0107e-137">Click Send.</span></span>

