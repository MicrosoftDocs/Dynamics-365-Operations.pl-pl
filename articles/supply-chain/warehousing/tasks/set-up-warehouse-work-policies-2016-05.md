---
title: Konfigurowanie zasad pracy magazynowej (zgłoszenie, maj 2016)
description: Procesy magazynowe nie zawsze obejmują pracę magazynową.
author: johanhoffmann
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkPolicy, WMSLocationIdLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 34b4255c85bb53f7e238b60559890571070953a6
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "335331"
---
# <a name="set-up-warehouse-work-policies-application-may-2016"></a><span data-ttu-id="8ec2d-103">Konfigurowanie zasad pracy magazynowej (zgłoszenie, maj 2016)</span><span class="sxs-lookup"><span data-stu-id="8ec2d-103">Set up warehouse work policies (Application, May 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8ec2d-104">Procesy magazynowe nie zawsze obejmują pracę magazynową.</span><span class="sxs-lookup"><span data-stu-id="8ec2d-104">Warehouse processes don’t always include warehouse work.</span></span> <span data-ttu-id="8ec2d-105">Poprzez zdefiniowanie pracy magazynowej można zablokować tworzenie pracy pobierania surowców i odkładania wyrobów gotowych dla zbioru produktów w określonych lokalizacjach.</span><span class="sxs-lookup"><span data-stu-id="8ec2d-105">By defining a work policy, you can prevent the creation of work for raw material picking and put-away of finished goods for a set of products at specific locations.</span></span> <span data-ttu-id="8ec2d-106">Dane wykorzystane do stworzenia tego nagrania pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="8ec2d-106">The USMF demo data company was used to create this recording.</span></span> <span data-ttu-id="8ec2d-107">Ten przewodnik po zadaniach wymaga aplikacji Dynamics AX w wersji 7.0.1 lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="8ec2d-107">This task guide requires Dynamics AX application 7.0.1 or later.</span></span>

1. <span data-ttu-id="8ec2d-108">Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Praca > Zasady pracy.</span><span class="sxs-lookup"><span data-stu-id="8ec2d-108">Go to Warehouse management > Setup > Work > Work policies.</span></span>
2. <span data-ttu-id="8ec2d-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="8ec2d-109">Click New.</span></span>
3. <span data-ttu-id="8ec2d-110">W polu Nazwa zasady pracy wpisz „Bez pracy odłożenia”.</span><span class="sxs-lookup"><span data-stu-id="8ec2d-110">In the Work policy name field, type 'No put-away work'.</span></span>
4. <span data-ttu-id="8ec2d-111">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="8ec2d-111">Click Save.</span></span>
5. <span data-ttu-id="8ec2d-112">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="8ec2d-112">Click Add.</span></span>
6. <span data-ttu-id="8ec2d-113">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="8ec2d-113">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="8ec2d-114">W polu Typ zlecenia wybierz wartość „Ukończono odkładanie wyrobów”.</span><span class="sxs-lookup"><span data-stu-id="8ec2d-114">In the Work order type field, select 'Finished goods put away'.</span></span>
8. <span data-ttu-id="8ec2d-115">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="8ec2d-115">Click Add.</span></span>
9. <span data-ttu-id="8ec2d-116">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="8ec2d-116">In the list, mark the selected row.</span></span>
10. <span data-ttu-id="8ec2d-117">W polu Typ zlecenia wybierz opcję „Odłożenie produktu ubocznego i produktu towarzyszącego”.</span><span class="sxs-lookup"><span data-stu-id="8ec2d-117">In the Work order type field, select 'Co-product and by-product put away'.</span></span>
11. <span data-ttu-id="8ec2d-118">Rozwiń sekcję Magazyny.</span><span class="sxs-lookup"><span data-stu-id="8ec2d-118">Expand the Inventory locations section.</span></span>
12. <span data-ttu-id="8ec2d-119">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="8ec2d-119">Click Add.</span></span>
13. <span data-ttu-id="8ec2d-120">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="8ec2d-120">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="8ec2d-121">Na liście magazynów wpisz „51”.</span><span class="sxs-lookup"><span data-stu-id="8ec2d-121">In the Warehouse list, enter '51'.</span></span>
15. <span data-ttu-id="8ec2d-122">W polu Lokalizacja wprowadź lub wybierz wartość „001”.</span><span class="sxs-lookup"><span data-stu-id="8ec2d-122">In the Location field, enter or select '001'.</span></span>
16. <span data-ttu-id="8ec2d-123">Rozwiń sekcję Produkty.</span><span class="sxs-lookup"><span data-stu-id="8ec2d-123">Expand the Products section.</span></span>
17. <span data-ttu-id="8ec2d-124">W polu Wybór produktu wybierz opcję „Wybrane”.</span><span class="sxs-lookup"><span data-stu-id="8ec2d-124">In the Product selection field, select 'Selected'.</span></span>
18. <span data-ttu-id="8ec2d-125">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="8ec2d-125">Click Add.</span></span>
19. <span data-ttu-id="8ec2d-126">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="8ec2d-126">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="8ec2d-127">W polu Numer pozycji wprowadź lub wybierz wartość „L0101”.</span><span class="sxs-lookup"><span data-stu-id="8ec2d-127">In the Item number field, enter or select 'L0101'.</span></span>
21. <span data-ttu-id="8ec2d-128">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="8ec2d-128">Click Save.</span></span>

