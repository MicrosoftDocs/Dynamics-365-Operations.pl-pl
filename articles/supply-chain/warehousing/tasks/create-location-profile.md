---
title: Tworzenie profilu lokalizacji
description: Z każdą lokalizacją w magazynie musi być skojarzony profil lokalizacji opisujący jej właściwości, na przykład czy lokalizacji pozwala na mieszane towary.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationProfile
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8bc7705b7db46af8fbe8bf9e78a878a53249b452
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "361390"
---
# <a name="create-a-location-profile"></a><span data-ttu-id="b9beb-103">Tworzenie profilu lokalizacji</span><span class="sxs-lookup"><span data-stu-id="b9beb-103">Create a location profile</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b9beb-104">Z każdą lokalizacją w magazynie musi być skojarzony profil lokalizacji opisujący jej właściwości, na przykład czy lokalizacji pozwala na mieszane towary.</span><span class="sxs-lookup"><span data-stu-id="b9beb-104">Every location in the warehouse needs to have a location profile associated with it that describes the properties of the location, for example, whether the location allows mixed items.</span></span> <span data-ttu-id="b9beb-105">W tej procedurze utworzymy profil dla lokalizacji, która nie wymaga kontroli na podstawie numerów identyfikacyjnych.</span><span class="sxs-lookup"><span data-stu-id="b9beb-105">In this procedure we’ll create a profile for a location that doesn’t require license plate control.</span></span> <span data-ttu-id="b9beb-106">Włączymy obsługę mieszanych towarów i mieszanych stanów zapasów oraz pozwolimy na inwentaryzację ciągłą.</span><span class="sxs-lookup"><span data-stu-id="b9beb-106">We’ll enable mixed items, and mixed inventory statuses, and allow cycle counting.</span></span> <span data-ttu-id="b9beb-107">Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="b9beb-107">You can use this procedure in the USMF demo data company.</span></span>

1. <span data-ttu-id="b9beb-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="b9beb-108">Click New.</span></span>
2. <span data-ttu-id="b9beb-109">W polu Identyfikator profilu lokalizacji wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="b9beb-109">In the Location profile ID field, type a value.</span></span>
3. <span data-ttu-id="b9beb-110">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="b9beb-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="b9beb-111">W polu Format lokalizacji wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="b9beb-111">In the Location format field, enter or select a value.</span></span>
5. <span data-ttu-id="b9beb-112">W polu Typ lokalizacji wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="b9beb-112">In the Location type field, enter or select a value.</span></span>
6. <span data-ttu-id="b9beb-113">W polu Identyfikator profilu zarządzania na rampie wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="b9beb-113">In the Dock management profile ID field, enter or select a value.</span></span>
7. <span data-ttu-id="b9beb-114">W polu Pozwól na mieszane pozycje wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="b9beb-114">Select Yes in the Allow mixed items field.</span></span>
8. <span data-ttu-id="b9beb-115">W polu Pozwól na mieszane stany zapasów wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="b9beb-115">Select Yes in the Allow mixed  inventory statuses field.</span></span>
9. <span data-ttu-id="b9beb-116">W polu Pozwól na inwentaryzację ciągłą wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="b9beb-116">Select Yes in the Allow cycle counting field.</span></span>
10. <span data-ttu-id="b9beb-117">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="b9beb-117">Click Save.</span></span>
11. <span data-ttu-id="b9beb-118">Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Magazyn > Profile lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="b9beb-118">Go to Warehouse management > Setup > Warehouse > Location profiles.</span></span>

