---
title: Konfigurowanie przyszłych zmian sytuacji życiowej
description: W module Dynamics 365 Human Resources można zaplanować przyszłe zmiany sytuacji życiowej.
author: andreabichsel
manager: tfehr
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitFutureLifeEvents, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f10d7b6c9b45f6cedc16972fb157e43b7e0c40b3
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2021
ms.locfileid: "5113893"
---
# <a name="configure-future-life-events"></a><span data-ttu-id="bf32b-103">Konfigurowanie przyszłych zmian sytuacji życiowej</span><span class="sxs-lookup"><span data-stu-id="bf32b-103">Configure future life events</span></span>

<span data-ttu-id="bf32b-104">W module Dynamics 365 Human Resources można zaplanować przyszłe zmiany sytuacji życiowej.</span><span class="sxs-lookup"><span data-stu-id="bf32b-104">You can schedule future life events in Dynamics 365 Human Resources.</span></span>

1. <span data-ttu-id="bf32b-105">W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Przyszłe zdarzenia zmiany sytuacji życiowej**.</span><span class="sxs-lookup"><span data-stu-id="bf32b-105">In the **Benefits management** workspace, under **Setup**, select **Future life events**.</span></span>

2. <span data-ttu-id="bf32b-106">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="bf32b-106">Select **New**.</span></span>

3. <span data-ttu-id="bf32b-107">Określ wartości dla następujących pól:</span><span class="sxs-lookup"><span data-stu-id="bf32b-107">Specify values for the following fields:</span></span>

   | <span data-ttu-id="bf32b-108">Pole</span><span class="sxs-lookup"><span data-stu-id="bf32b-108">Field</span></span> | <span data-ttu-id="bf32b-109">Opis</span><span class="sxs-lookup"><span data-stu-id="bf32b-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="bf32b-110">Data zdarzenia zmiany sytuacji życiowej</span><span class="sxs-lookup"><span data-stu-id="bf32b-110">Life event date</span></span> | <span data-ttu-id="bf32b-111">System przetwarza wszystkie zdarzenia w okresie rejestracji, który nastąpiły do tej daty.</span><span class="sxs-lookup"><span data-stu-id="bf32b-111">The system processes all events during the enrollment period that occur up until this date.</span></span> |
   | <span data-ttu-id="bf32b-112">Zarejestrowane zdarzenie zmiany sytuacji życiowej</span><span class="sxs-lookup"><span data-stu-id="bf32b-112">Life event logged</span></span> | <span data-ttu-id="bf32b-113">Data i godzina zarejestrowania zmiany sytuacji życiowej.</span><span class="sxs-lookup"><span data-stu-id="bf32b-113">Date and time when the life event is logged.</span></span> |
   | <span data-ttu-id="bf32b-114">Typ dziennika</span><span class="sxs-lookup"><span data-stu-id="bf32b-114">Log type</span></span> | <span data-ttu-id="bf32b-115">Pokazuje, czy akcja ma jeden z następujących typów:</span><span class="sxs-lookup"><span data-stu-id="bf32b-115">Shows whether the action is one of the following:</span></span></br></br><span data-ttu-id="bf32b-116">- **Aktualizacja** — zmiana istniejącego rekordu, który śledzi zmiany sytuacji życiowej</span><span class="sxs-lookup"><span data-stu-id="bf32b-116">- **Update** – a change to an existing record that is tracking life events</span></span></br></br><span data-ttu-id="bf32b-117">- **Wstawienie** — utworzenie nowego rekordu zmiany sytuacji życiowej</span><span class="sxs-lookup"><span data-stu-id="bf32b-117">- **Insert** – the creation of a new life event record</span></span> |
   | <span data-ttu-id="bf32b-118">Identyfikator typu zdarzenia zmiany sytuacji życiowej</span><span class="sxs-lookup"><span data-stu-id="bf32b-118">Life event type ID</span></span> | <span data-ttu-id="bf32b-119">Unikatowy identyfikator typu zmiany sytuacji życiowej.</span><span class="sxs-lookup"><span data-stu-id="bf32b-119">The life event type unique identifier.</span></span> |
   | <span data-ttu-id="bf32b-120">Typ zdarzenia zmiany sytuacji życiowej</span><span class="sxs-lookup"><span data-stu-id="bf32b-120">Life event type</span></span> | <span data-ttu-id="bf32b-121">Katalizator aktualizujący rejestrację pracownika na świadczenia.</span><span class="sxs-lookup"><span data-stu-id="bf32b-121">A catalyst to updating an employee’s benefits enrollment.</span></span> <span data-ttu-id="bf32b-122">Aby uzyskać więcej informacji, zajrzyj do sekcji Wyzwalacze zmian sytuacji życiowej.</span><span class="sxs-lookup"><span data-stu-id="bf32b-122">For more details, see the Life event triggers section.</span></span> |
   | <span data-ttu-id="bf32b-123">Stan</span><span class="sxs-lookup"><span data-stu-id="bf32b-123">Status</span></span> | <span data-ttu-id="bf32b-124">Określa, czy zmiana sytuacji życiowej została przetworzona, czy nie.</span><span class="sxs-lookup"><span data-stu-id="bf32b-124">Whether the life event has been processed or not.</span></span> |
   | <span data-ttu-id="bf32b-125">Wiersz</span><span class="sxs-lookup"><span data-stu-id="bf32b-125">Line</span></span> | <span data-ttu-id="bf32b-126">Numer wiersza przyszłej zmiany sytuacji życiowej.</span><span class="sxs-lookup"><span data-stu-id="bf32b-126">The line number of the future life event.</span></span> |

4. <span data-ttu-id="bf32b-127">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="bf32b-127">Select **Save**.</span></span> 
