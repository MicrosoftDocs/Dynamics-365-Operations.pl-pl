---
title: Konfigurowanie przyszłych zmian sytuacji życiowej
description: W module Dynamics 365 Human Resources można zaplanować przyszłe zmiany sytuacji życiowej.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitFutureLifeEvents
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 655070e52e3d1f43ca6904ce3218582868f193fe
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010217"
---
# <a name="configure-future-life-events"></a><span data-ttu-id="9ba86-103">Konfigurowanie przyszłych zmian sytuacji życiowej</span><span class="sxs-lookup"><span data-stu-id="9ba86-103">Configure future life events</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="9ba86-104">W module Dynamics 365 Human Resources można zaplanować przyszłe zmiany sytuacji życiowej.</span><span class="sxs-lookup"><span data-stu-id="9ba86-104">You can schedule future life events in Dynamics 365 Human Resources.</span></span>

1. <span data-ttu-id="9ba86-105">W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Przyszłe zdarzenia zmiany sytuacji życiowej**.</span><span class="sxs-lookup"><span data-stu-id="9ba86-105">In the **Benefits management** workspace, under **Setup**, select **Future life events**.</span></span>

2. <span data-ttu-id="9ba86-106">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="9ba86-106">Select **New**.</span></span>

3. <span data-ttu-id="9ba86-107">Określ wartości dla następujących pól:</span><span class="sxs-lookup"><span data-stu-id="9ba86-107">Specify values for the following fields:</span></span>

   | <span data-ttu-id="9ba86-108">Pole</span><span class="sxs-lookup"><span data-stu-id="9ba86-108">Field</span></span> | <span data-ttu-id="9ba86-109">Opis</span><span class="sxs-lookup"><span data-stu-id="9ba86-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="9ba86-110">Data zdarzenia zmiany sytuacji życiowej</span><span class="sxs-lookup"><span data-stu-id="9ba86-110">Life event date</span></span> | <span data-ttu-id="9ba86-111">System przetwarza wszystkie zdarzenia w okresie rejestracji, który nastąpiły do tej daty.</span><span class="sxs-lookup"><span data-stu-id="9ba86-111">The system processes all events during the enrollment period that occur up until this date.</span></span> |
   | <span data-ttu-id="9ba86-112">Zarejestrowane zdarzenie zmiany sytuacji życiowej</span><span class="sxs-lookup"><span data-stu-id="9ba86-112">Life event logged</span></span> | <span data-ttu-id="9ba86-113">Data i godzina zarejestrowania zmiany sytuacji życiowej.</span><span class="sxs-lookup"><span data-stu-id="9ba86-113">Date and time when the life event is logged.</span></span> |
   | <span data-ttu-id="9ba86-114">Typ dziennika</span><span class="sxs-lookup"><span data-stu-id="9ba86-114">Log type</span></span> | <span data-ttu-id="9ba86-115">Pokazuje, czy akcja ma jeden z następujących typów:</span><span class="sxs-lookup"><span data-stu-id="9ba86-115">Shows whether the action is one of the following:</span></span></br></br><span data-ttu-id="9ba86-116">- **Aktualizacja** — zmiana istniejącego rekordu, który śledzi zmiany sytuacji życiowej</span><span class="sxs-lookup"><span data-stu-id="9ba86-116">- **Update** – a change to an existing record that is tracking life events</span></span></br></br><span data-ttu-id="9ba86-117">- **Wstawienie** — utworzenie nowego rekordu zmiany sytuacji życiowej</span><span class="sxs-lookup"><span data-stu-id="9ba86-117">- **Insert** – the creation of a new life event record</span></span> |
   | <span data-ttu-id="9ba86-118">Identyfikator typu zdarzenia zmiany sytuacji życiowej</span><span class="sxs-lookup"><span data-stu-id="9ba86-118">Life event type ID</span></span> | <span data-ttu-id="9ba86-119">Unikatowy identyfikator typu zmiany sytuacji życiowej.</span><span class="sxs-lookup"><span data-stu-id="9ba86-119">The life event type unique identifier.</span></span> |
   | <span data-ttu-id="9ba86-120">Typ zdarzenia zmiany sytuacji życiowej</span><span class="sxs-lookup"><span data-stu-id="9ba86-120">Life event type</span></span> | <span data-ttu-id="9ba86-121">Katalizator aktualizujący rejestrację pracownika na świadczenia.</span><span class="sxs-lookup"><span data-stu-id="9ba86-121">A catalyst to updating an employee’s benefits enrollment.</span></span> <span data-ttu-id="9ba86-122">Aby uzyskać więcej informacji, zajrzyj do sekcji Wyzwalacze zmian sytuacji życiowej.</span><span class="sxs-lookup"><span data-stu-id="9ba86-122">For more details, see the Life event triggers section.</span></span> |
   | <span data-ttu-id="9ba86-123">Stan</span><span class="sxs-lookup"><span data-stu-id="9ba86-123">Status</span></span> | <span data-ttu-id="9ba86-124">Określa, czy zmiana sytuacji życiowej została przetworzona, czy nie.</span><span class="sxs-lookup"><span data-stu-id="9ba86-124">Whether the life event has been processed or not.</span></span> |
   | <span data-ttu-id="9ba86-125">Wiersz</span><span class="sxs-lookup"><span data-stu-id="9ba86-125">Line</span></span> | <span data-ttu-id="9ba86-126">Numer wiersza przyszłej zmiany sytuacji życiowej.</span><span class="sxs-lookup"><span data-stu-id="9ba86-126">The line number of the future life event.</span></span> |

4. <span data-ttu-id="9ba86-127">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="9ba86-127">Select **Save**.</span></span> 
