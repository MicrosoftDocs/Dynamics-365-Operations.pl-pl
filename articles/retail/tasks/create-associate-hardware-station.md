--- 
title: "Tworzenie stacji sprzętowych"
description: "Ta procedura zawiera instruktaż tworzenia nowej stacji sprzętowej."
author: jashanno
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: 3551e37c6aae37c01b5cacff8b908faaf75fb3e2
ms.contentlocale: pl-pl
ms.lasthandoff: 08/09/2018

---
# <a name="create-hardware-stations"></a><span data-ttu-id="82b29-103">Tworzenie stacji sprzętowych</span><span class="sxs-lookup"><span data-stu-id="82b29-103">Create hardware stations</span></span>

[!include [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="82b29-104">Ta procedura zawiera instruktaż tworzenia nowej stacji sprzętowej.</span><span class="sxs-lookup"><span data-stu-id="82b29-104">This procedure walks through how to create a new hardware station.</span></span> <span data-ttu-id="82b29-105">Nowy profil sprzętu zostanie utworzony i użyty w celu dodania nowych stacji sprzętowych do wstępnie zdefiniowanego sklepu (kanału).</span><span class="sxs-lookup"><span data-stu-id="82b29-105">A new hardware profile will be created and used to add new hardware stations to a pre-defined store (channel).</span></span> <span data-ttu-id="82b29-106">Procedura wykorzystuje dane firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="82b29-106">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="82b29-107">Wybierz kolejno opcje Podstawowe funkcje handlowe > Kanały > ..</span><span class="sxs-lookup"><span data-stu-id="82b29-107">Go to Commerce essentials > Channels > ..</span></span> <span data-ttu-id="82b29-108">> ..</span><span class="sxs-lookup"><span data-stu-id="82b29-108">> ..</span></span> <span data-ttu-id="82b29-109">> ..</span><span class="sxs-lookup"><span data-stu-id="82b29-109">> ..</span></span> <span data-ttu-id="82b29-110">> Profile stacji sprzętowych.</span><span class="sxs-lookup"><span data-stu-id="82b29-110">> Hardware station profiles.</span></span>
2. <span data-ttu-id="82b29-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="82b29-111">Click New.</span></span>
3. <span data-ttu-id="82b29-112">W polu Identyfikator stacji sprzętowej wpisz „TestHWProfile”.</span><span class="sxs-lookup"><span data-stu-id="82b29-112">In the Hardware station ID field, type 'TestHWProfile'.</span></span>
4. <span data-ttu-id="82b29-113">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="82b29-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="82b29-114">W polu Numer portu wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="82b29-114">In the Port number field, enter a number.</span></span>
6. <span data-ttu-id="82b29-115">W polu Profil sprzętu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="82b29-115">In the Hardware profile field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="82b29-116">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="82b29-116">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="82b29-117">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="82b29-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="82b29-118">W polu Nazwa pakietu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="82b29-118">In the Package name field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="82b29-119">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="82b29-119">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="82b29-120">Jest to standardowy pakiet towarzyszący nowemu środowisku.</span><span class="sxs-lookup"><span data-stu-id="82b29-120">This is the standard package that comes with a new environment.</span></span> <span data-ttu-id="82b29-121">Numer wersji może się różnić.</span><span class="sxs-lookup"><span data-stu-id="82b29-121">The version number may vary.</span></span>  
11. <span data-ttu-id="82b29-122">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="82b29-122">Click Save.</span></span>
12. <span data-ttu-id="82b29-123">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="82b29-123">Close the page.</span></span>
13. <span data-ttu-id="82b29-124">Wybierz kolejno opcje Handel detaliczny i inny > Kanały > Wszystkie sklepy sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="82b29-124">Go to Retail and commerce > Channels > All retail stores.</span></span>
14. <span data-ttu-id="82b29-125">Na liście zaznacz wiersz 17.</span><span class="sxs-lookup"><span data-stu-id="82b29-125">In the list, select row 17.</span></span>
    * <span data-ttu-id="82b29-126">Jeśli używasz danych firmy demonstracyjnej USRT, jest to sklep w Houston.</span><span class="sxs-lookup"><span data-stu-id="82b29-126">If you are using the USRT demo data company, this is the Houston store.</span></span>  
15. <span data-ttu-id="82b29-127">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="82b29-127">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="82b29-128">Przełącz rozwinięcie sekcji Stacje sprzętowe.</span><span class="sxs-lookup"><span data-stu-id="82b29-128">Toggle the expansion of the Hardware stations section.</span></span>
17. <span data-ttu-id="82b29-129">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="82b29-129">Click Add.</span></span>
18. <span data-ttu-id="82b29-130">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="82b29-130">In the list, mark the selected row.</span></span>
19. <span data-ttu-id="82b29-131">W polu Identyfikator profilu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="82b29-131">In the Profile ID field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="82b29-132">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="82b29-132">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="82b29-133">Musi to być nowy profil stacji sprzętowej, który został utworzony w poprzednich krokach.</span><span class="sxs-lookup"><span data-stu-id="82b29-133">This must be the new hardware station profile that was created in the previous steps.</span></span>  
21. <span data-ttu-id="82b29-134">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="82b29-134">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="82b29-135">W polu Nazwa hosta wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="82b29-135">In the Host name field, type a value.</span></span>
23. <span data-ttu-id="82b29-136">W polu Identyfikator terminalu EFT wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="82b29-136">In the EFT terminal ID field, type a value.</span></span>
24. <span data-ttu-id="82b29-137">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="82b29-137">Click Save.</span></span>


