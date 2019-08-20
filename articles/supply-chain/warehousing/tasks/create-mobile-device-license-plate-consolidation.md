---
title: Tworzenie elementu menu urządzenia przenośnego dla konsolidacji na podstawie numerów identyfikacyjnych
description: Ta procedura pokazuje, jak utworzyć element menu urządzenia przenośnego dla pracy konsolidacji na podstawie numerów identyfikacyjnych.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cc610a16f4b0e574b5d5e7f8fc9ecf1e12534645
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1847310"
---
# <a name="create-a-mobile-device-menu-item-for-license-plate-consolidation"></a><span data-ttu-id="5d42c-103">Tworzenie elementu menu urządzenia przenośnego dla konsolidacji na podstawie numerów identyfikacyjnych</span><span class="sxs-lookup"><span data-stu-id="5d42c-103">Create a mobile device menu item for license plate consolidation</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5d42c-104">Ta procedura pokazuje, jak utworzyć element menu urządzenia przenośnego dla pracy konsolidacji na podstawie numerów identyfikacyjnych.</span><span class="sxs-lookup"><span data-stu-id="5d42c-104">This procedure shows you how to create a mobile device menu item for license plate consolidation work.</span></span> <span data-ttu-id="5d42c-105">Dzięki temu pracownicy magazynu będą mogli konsolidować towary o jednym numerze identyfikacyjnym z towarami o innym numerze identyfikacyjnym w tej samej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="5d42c-105">This enables warehouse workers to consolidate items on one license plate with items on another license place within the same location.</span></span> <span data-ttu-id="5d42c-106">Na przykład mogą używać tej funkcji, jeżeli kolejne kroki przygotowania były takie same w obu zleceniach i pracę można wykonać tylko raz dla scalonych towarów.</span><span class="sxs-lookup"><span data-stu-id="5d42c-106">For example, they might use this if subsequent staging steps were the same on both work orders, so that the work only needs to be performed once for the merged items.</span></span> <span data-ttu-id="5d42c-107">Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="5d42c-107">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="5d42c-108">To zadanie zazwyczaj wykonuje kierownik magazynu.</span><span class="sxs-lookup"><span data-stu-id="5d42c-108">The task would typically be carried out by a warehouse manager.</span></span> <span data-ttu-id="5d42c-109">Ta procedura dotyczy funkcji, która została dodana w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="5d42c-109">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>

1. <span data-ttu-id="5d42c-110">Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Urządzenie przenośne > Elementy menu urządzenia przenośnego.</span><span class="sxs-lookup"><span data-stu-id="5d42c-110">Go to Warehouse management > Setup > Mobile device > Mobile device menu items.</span></span>
2. <span data-ttu-id="5d42c-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="5d42c-111">Click New.</span></span>
3. <span data-ttu-id="5d42c-112">W polu Nazwa elementu menu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="5d42c-112">In the Menu item name field, type a value.</span></span>
4. <span data-ttu-id="5d42c-113">W polu Tytuł wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="5d42c-113">In the Title field, type a value.</span></span>
5. <span data-ttu-id="5d42c-114">W polu Tryb wybierz opcję „Pośrednie”.</span><span class="sxs-lookup"><span data-stu-id="5d42c-114">In the Mode field, select 'Indirect'.</span></span>
6. <span data-ttu-id="5d42c-115">W polu Kod działania wybierz opcję „Konsoliduj numery identyfikacyjne”.</span><span class="sxs-lookup"><span data-stu-id="5d42c-115">In the Activity code field, select 'Consolidate license plates'.</span></span>

