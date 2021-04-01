---
title: Tworzenie i kojarzenie stacji sprzętowej
description: Ta procedura zawiera instruktaż tworzenia nowej stacji sprzętowej.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailHardwareStation, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d0c02246a20ef28c0f4f28b73dfe5ff56f38a68b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5247051"
---
# <a name="create-and-associate-a-hardware-station"></a><span data-ttu-id="ea0dc-103">Tworzenie i kojarzenie stacji sprzętowej</span><span class="sxs-lookup"><span data-stu-id="ea0dc-103">Create and associate a hardware station</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ea0dc-104">Ta procedura zawiera instruktaż tworzenia nowej stacji sprzętowej.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-104">This procedure walks through how to create a new hardware station.</span></span> <span data-ttu-id="ea0dc-105">Nowy profil sprzętu zostanie utworzony i użyty w celu dodania nowych stacji sprzętowych do wstępnie zdefiniowanego sklepu (kanału).</span><span class="sxs-lookup"><span data-stu-id="ea0dc-105">A new hardware profile will be created and used to add new hardware stations to a pre-defined store (channel).</span></span> <span data-ttu-id="ea0dc-106">Procedura wykorzystuje dane firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-106">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="ea0dc-107">Wybierz kolejno opcje Podstawowe funkcje handlowe > Kanały > ..</span><span class="sxs-lookup"><span data-stu-id="ea0dc-107">Go to Commerce essentials > Channels > ..</span></span> <span data-ttu-id="ea0dc-108">> ..</span><span class="sxs-lookup"><span data-stu-id="ea0dc-108">> ..</span></span> <span data-ttu-id="ea0dc-109">> ..</span><span class="sxs-lookup"><span data-stu-id="ea0dc-109">> ..</span></span> <span data-ttu-id="ea0dc-110">> Profile stacji sprzętowych.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-110">> Hardware station profiles.</span></span>
2. <span data-ttu-id="ea0dc-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-111">Click New.</span></span>
3. <span data-ttu-id="ea0dc-112">W polu Identyfikator stacji sprzętowej wpisz „TestHWProfile”.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-112">In the Hardware station ID field, type 'TestHWProfile'.</span></span>
4. <span data-ttu-id="ea0dc-113">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="ea0dc-114">W polu Numer portu wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-114">In the Port number field, enter a number.</span></span>
6. <span data-ttu-id="ea0dc-115">W polu Profil sprzętu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-115">In the Hardware profile field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="ea0dc-116">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-116">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="ea0dc-117">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="ea0dc-118">W polu Nazwa pakietu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-118">In the Package name field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="ea0dc-119">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-119">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ea0dc-120">Jest to standardowy pakiet towarzyszący nowemu środowisku.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-120">This is the standard package that comes with a new environment.</span></span> <span data-ttu-id="ea0dc-121">Numer wersji może się różnić.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-121">The version number may vary.</span></span>  
11. <span data-ttu-id="ea0dc-122">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-122">Click Save.</span></span>
12. <span data-ttu-id="ea0dc-123">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-123">Close the page.</span></span>
13. <span data-ttu-id="ea0dc-124">Wybierz kolejno opcje Handel detaliczny i inny > Kanały > Wszystkie sklepy.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-124">Go to Retail and Commerce > Channels > All stores.</span></span>
14. <span data-ttu-id="ea0dc-125">Na liście zaznacz wiersz 17.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-125">In the list, select row 17.</span></span>
    * <span data-ttu-id="ea0dc-126">Jeśli używasz danych firmy demonstracyjnej USRT, jest to sklep w Houston.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-126">If you are using the USRT demo data company, this is the Houston store.</span></span>  
15. <span data-ttu-id="ea0dc-127">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-127">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="ea0dc-128">Przełącz rozwinięcie sekcji Stacje sprzętowe.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-128">Toggle the expansion of the Hardware stations section.</span></span>
17. <span data-ttu-id="ea0dc-129">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-129">Click Add.</span></span>
18. <span data-ttu-id="ea0dc-130">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-130">In the list, mark the selected row.</span></span>
19. <span data-ttu-id="ea0dc-131">W polu Identyfikator profilu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-131">In the Profile ID field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="ea0dc-132">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-132">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="ea0dc-133">Musi to być nowy profil stacji sprzętowej, który został utworzony w poprzednich krokach.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-133">This must be the new hardware station profile that was created in the previous steps.</span></span>  
21. <span data-ttu-id="ea0dc-134">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-134">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="ea0dc-135">W polu Nazwa hosta wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-135">In the Host name field, type a value.</span></span>
23. <span data-ttu-id="ea0dc-136">W polu Identyfikator terminalu EFT wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-136">In the EFT terminal ID field, type a value.</span></span>
24. <span data-ttu-id="ea0dc-137">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-137">Click Save.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]