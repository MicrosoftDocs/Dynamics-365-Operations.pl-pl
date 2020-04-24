---
title: Tworzenie profilu lokalizacji
description: W tym temacie opisano sposób tworzenia profilu lokalizacji w Dynamics 365 Supply Chain Management.
author: ShylaThompson
manager: tfehr
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 320059184dc69c4fd34c4b50265ceb142d47a467
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3217156"
---
# <a name="create-a-location-profile"></a><span data-ttu-id="74e27-103">Tworzenie profilu lokalizacji</span><span class="sxs-lookup"><span data-stu-id="74e27-103">Create a location profile</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="74e27-104">W tym temacie opisano sposób tworzenia profilu lokalizacji w Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="74e27-104">This topic explains how to create a location profile in Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="74e27-105">Z każdą lokalizacją w magazynie musi być skojarzony profil lokalizacji opisujący jej właściwości, na przykład czy lokalizacji pozwala na mieszane towary.</span><span class="sxs-lookup"><span data-stu-id="74e27-105">Every location in the warehouse needs to have a location profile associated with it that describes the properties of the location, for example, whether the location allows mixed items.</span></span> <span data-ttu-id="74e27-106">W tej procedurze utworzymy profil dla lokalizacji, która nie wymaga kontroli na podstawie numerów identyfikacyjnych.</span><span class="sxs-lookup"><span data-stu-id="74e27-106">In this procedure we'll create a profile for a location that doesn't require license plate control.</span></span> <span data-ttu-id="74e27-107">Włączymy obsługę mieszanych towarów i mieszanych stanów zapasów oraz pozwolimy na inwentaryzację ciągłą.</span><span class="sxs-lookup"><span data-stu-id="74e27-107">We'll enable mixed items, and mixed inventory statuses, and allow cycle counting.</span></span> <span data-ttu-id="74e27-108">Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="74e27-108">You can use this procedure in the USMF demo data company.</span></span>


1. <span data-ttu-id="74e27-109">W okienku nawigacji przejdź do **Moduły > Zarządzanie magazynem > Ustawienia > Magazyn > Profile lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="74e27-109">In the navigation pane, go to **Modules > Warehouse management > Setup > Warehouse > Location profiles**.</span></span>
2. <span data-ttu-id="74e27-110">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="74e27-110">Select **New**.</span></span>
3. <span data-ttu-id="74e27-111">W polu **Identyfikator profilu lokalizacji** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="74e27-111">In the **Location profile ID** field, type a value.</span></span>
4. <span data-ttu-id="74e27-112">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="74e27-112">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="74e27-113">W polu **Format lokalizacji** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="74e27-113">In the **Location format** field, enter or select a value.</span></span>
6. <span data-ttu-id="74e27-114">W polu **Typ lokalizacji** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="74e27-114">In the **Location type** field, enter or select a value.</span></span>
7. <span data-ttu-id="74e27-115">W polu **Identyfikator profilu zarządzania na rampie** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="74e27-115">In the **Dock management profile ID** field, enter or select a value.</span></span>
8. <span data-ttu-id="74e27-116">W polu **Pozwól na mieszane pozycje** wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="74e27-116">Select **Yes** in the **Allow mixed items** field.</span></span>
9. <span data-ttu-id="74e27-117">w polu **Pozwól na mieszane stany zapasów** wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="74e27-117">Select **Yes** in the **Allow mixed inventory statuses** field.</span></span>
10. <span data-ttu-id="74e27-118">W polu **Pozwól na inwentaryzację ciągłą** wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="74e27-118">Select **Yes** in the **Allow cycle counting** field.</span></span>
11. <span data-ttu-id="74e27-119">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="74e27-119">Select **Save**.</span></span>

