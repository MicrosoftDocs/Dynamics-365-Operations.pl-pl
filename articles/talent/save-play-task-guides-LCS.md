---
title: Zapisywanie przewodników zadań w usłudze LCS i odtwarzanie ich ponownie
description: W tym temacie opisano, jak zapisać przewodniki po zadaniach do programu Microsoft Dynamics Lifecycle Services (LCS), a następnie odtworzyć je ponownie.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 6ee3556e033cf298bbd5102746d2b57884f5e6d0
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898071"
---
# <a name="save-task-guides-to-lcs-and-replay-them"></a><span data-ttu-id="6dd65-103">Zapisywanie przewodników zadań w usłudze LCS i odtwarzanie ich ponownie</span><span class="sxs-lookup"><span data-stu-id="6dd65-103">Save task guides to LCS and replay them</span></span>

<span data-ttu-id="6dd65-104">**Szczegóły środowiska**</span><span class="sxs-lookup"><span data-stu-id="6dd65-104">**Environment details**</span></span> 

<span data-ttu-id="6dd65-105">Microsoft Dynamics 365 Talent, który został wdrożony za pośrednictwem Microsoft Dynamics Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="6dd65-105">Microsoft Dynamics 365 Talent, which was deployed via Microsoft Dynamics Lifecycle Services (LCS)</span></span>

<span data-ttu-id="6dd65-106">**Wystawienie**</span><span class="sxs-lookup"><span data-stu-id="6dd65-106">**Issue**</span></span>

<span data-ttu-id="6dd65-107">Odbiorca chce zapisać nowe nagrania zadań w projekcie LCS, a następnie odtworzyć wskazówki zapisanego zadania.</span><span class="sxs-lookup"><span data-stu-id="6dd65-107">The customer wants to save new task recordings to his or her LCS project, and then replay the saved task guides.</span></span>

<span data-ttu-id="6dd65-108">**Rozdzielczość**</span><span class="sxs-lookup"><span data-stu-id="6dd65-108">**Resolution**</span></span>

<span data-ttu-id="6dd65-109">Wykonaj te kroki, aby zapisać nagranie zadania w LCS.</span><span class="sxs-lookup"><span data-stu-id="6dd65-109">Follow these steps to save a task recording to LCS.</span></span>

1. <span data-ttu-id="6dd65-110">Zaloguj się do LCS, a następnie wybierz projekt.</span><span class="sxs-lookup"><span data-stu-id="6dd65-110">Sign in to LCS, and select the project.</span></span>
2. <span data-ttu-id="6dd65-111">Wybierz kafelek **Narzędzie do modelowania procesów biznesowych**.</span><span class="sxs-lookup"><span data-stu-id="6dd65-111">Select the **Business process modeler** tile.</span></span>
3. <span data-ttu-id="6dd65-112">Wyświetl tę stronę w zaktualizowanym interfejsie narzędzia BPM.</span><span class="sxs-lookup"><span data-stu-id="6dd65-112">View the page in the "Updated BPM experience."</span></span>
4. <span data-ttu-id="6dd65-113">Wybierz bibliotekę, a następnie wybierz przycisk **Kopiuj**.</span><span class="sxs-lookup"><span data-stu-id="6dd65-113">Select a library, and then select **Copy**.</span></span>
5. <span data-ttu-id="6dd65-114">Wprowadź nazwę dla modelu Narzędzie do modelowania procesów biznesowych (BPM).</span><span class="sxs-lookup"><span data-stu-id="6dd65-114">Enter a name for the Business process modeler (BPM) model.</span></span>
6. <span data-ttu-id="6dd65-115">Zaloguj się w aplikacji Talent z LCS.</span><span class="sxs-lookup"><span data-stu-id="6dd65-115">Sign in to Talent from LCS.</span></span>
7. <span data-ttu-id="6dd65-116">W polu **Wyszukaj** wpisz **pomoc**.</span><span class="sxs-lookup"><span data-stu-id="6dd65-116">In the **Search** field, enter **help**.</span></span> <span data-ttu-id="6dd65-117">Zostanie otwarta pomoc usługi Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="6dd65-117">Lifecycle Services Help is opened.</span></span>
8. <span data-ttu-id="6dd65-118">Wybierz przycisk **odśwież** dla konfiguracji pomocy usługi Lifecycle Services.</span><span class="sxs-lookup"><span data-stu-id="6dd65-118">Select the **Refresh** button for Lifecycle Services Help configuration.</span></span>

    <span data-ttu-id="6dd65-119">Nowe biblioteki BPM powinny być wyświetlane i aktywne.</span><span class="sxs-lookup"><span data-stu-id="6dd65-119">Your new BPM library should appear, and it should be active.</span></span>

9. <span data-ttu-id="6dd65-120">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="6dd65-120">Close the page.</span></span>
10. <span data-ttu-id="6dd65-121">Utwórz nagranie zadania.</span><span class="sxs-lookup"><span data-stu-id="6dd65-121">Create a task recording.</span></span>
11. <span data-ttu-id="6dd65-122">Po zakończeniu zaznacz **zapisz w Lifecycle Services**.</span><span class="sxs-lookup"><span data-stu-id="6dd65-122">When you've finished, select **Save to Lifecycle Services**.</span></span>

    ![Zapisz w usłudze Lifecycle Services](media/task-guides.png)

12. <span data-ttu-id="6dd65-124">Wybierz bibliotekę BPM i węzeł, aby zapisać nagranie zadania.</span><span class="sxs-lookup"><span data-stu-id="6dd65-124">Select the BPM library and node to save the task recording to.</span></span>

<span data-ttu-id="6dd65-125">Wykonaj następujące kroki, aby powtórzyć odtworzyć przewodnik zadania z LCS.</span><span class="sxs-lookup"><span data-stu-id="6dd65-125">Follow these steps to replay a task guide from LCS.</span></span>

1. <span data-ttu-id="6dd65-126">Otwórz rejestratora zadań.</span><span class="sxs-lookup"><span data-stu-id="6dd65-126">Start Task recorder.</span></span>
2. <span data-ttu-id="6dd65-127">Wybierz **Otwórz z LCS**.</span><span class="sxs-lookup"><span data-stu-id="6dd65-127">Select **Open from LCS**.</span></span>
3. <span data-ttu-id="6dd65-128">Wybierz bibliotekę i węzeł BPM, który ma zapisany przewodnik zadania.</span><span class="sxs-lookup"><span data-stu-id="6dd65-128">Select the library and the BPM node that have the saved task guide.</span></span>
4. <span data-ttu-id="6dd65-129">Otwórz przewodnik zadania.</span><span class="sxs-lookup"><span data-stu-id="6dd65-129">Open the task guide.</span></span>
