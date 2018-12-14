---
title: Osadzanie aplikacji PowerApps w Core HR
description: "W tym temacie opisano, jak rozwiązać problem, gdzie element menu usługi PowerApps znika w module Administracja systemu."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: 197b553f0b202ee29ad42274e2c0e03446ec782c
ms.contentlocale: pl-pl
ms.lasthandoff: 12/04/2018

---

# <a name="embed-powerapps-apps-in-core-hr"></a><span data-ttu-id="09b5b-103">Osadzanie aplikacji PowerApps w Core HR</span><span class="sxs-lookup"><span data-stu-id="09b5b-103">Embed PowerApps apps in Core HR</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="09b5b-104">**Wydaj**</span><span class="sxs-lookup"><span data-stu-id="09b5b-104">**Issue**</span></span>

<span data-ttu-id="09b5b-105">Element menu **PowerApps** zniknął z modułu **administrowanie systemem**.</span><span class="sxs-lookup"><span data-stu-id="09b5b-105">The **PowerApps** menu item has disappeared from the **System administration** module.</span></span>

<span data-ttu-id="09b5b-106">**Przyczyna**</span><span class="sxs-lookup"><span data-stu-id="09b5b-106">**Cause**</span></span>

<span data-ttu-id="09b5b-107">Projekt interfejsu użytkownika został zmieniony, a Microsoft PowerApps zostanie dołączony do modelu standardowego personalizacji.</span><span class="sxs-lookup"><span data-stu-id="09b5b-107">The user interface (UI) design has been changed, and Microsoft PowerApps is now included in the standard personalization model.</span></span>

<span data-ttu-id="09b5b-108">**Rozdzielczość**</span><span class="sxs-lookup"><span data-stu-id="09b5b-108">**Resolution**</span></span>

<span data-ttu-id="09b5b-109">Zmienił się sposób osadzenia usługi PowerApps.</span><span class="sxs-lookup"><span data-stu-id="09b5b-109">The way that PowerApps apps are embedded has been changed.</span></span> <span data-ttu-id="09b5b-110">Aplikacje PowerApps teraz są dodawane za pomocą modelu personalizacji.</span><span class="sxs-lookup"><span data-stu-id="09b5b-110">PowerApps apps are now added through the personalization model.</span></span> <span data-ttu-id="09b5b-111">Aplikacje PowerApps można dodać do prawie wszystkich stron w Microsoft Dynamics 365 for Talent.</span><span class="sxs-lookup"><span data-stu-id="09b5b-111">You can add PowerApps apps to almost all pages in Microsoft Dynamics 365 for Talent.</span></span>

<span data-ttu-id="09b5b-112">Aby uzyskać szczegółowe informacje o osadzaniu aplikacji usługi PowerApps w Talents, zobacz [Osadzanie aplikacji PowerApp](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span><span class="sxs-lookup"><span data-stu-id="09b5b-112">For information about how to embed PowerApps apps in Talent, see [Embed PowerApps apps](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span></span>

<span data-ttu-id="09b5b-113">Odbiorcy PowerApps, którzy osadzili aplikacje przed zmianą powinni mieć uaktualniony system do nowego modelu.</span><span class="sxs-lookup"><span data-stu-id="09b5b-113">Any PowerApps customer who embedded apps before the change should have been upgraded to the new model.</span></span>

<span data-ttu-id="09b5b-114">Przycisk **PowerApps** znajduje się w prawym górnym rogu prawie każdej strony w Talent.</span><span class="sxs-lookup"><span data-stu-id="09b5b-114">The **PowerApps** button is in the upper-right corner of almost every page in Talent.</span></span> <span data-ttu-id="09b5b-115">Ten przycisk służy do wstawiania aplikacji PowerApps.</span><span class="sxs-lookup"><span data-stu-id="09b5b-115">You can use this button to insert a PowerApps app.</span></span>

<span data-ttu-id="09b5b-116">Oto przykład.</span><span class="sxs-lookup"><span data-stu-id="09b5b-116">Here is an example.</span></span>

1. <span data-ttu-id="09b5b-117">Przejdź do **zarządzania personelem \>łącza \>pracownicy \>pracownicy**.</span><span class="sxs-lookup"><span data-stu-id="09b5b-117">Go to **Personnel management \> Links \> Workers \> Employees**.</span></span>
2. <span data-ttu-id="09b5b-118">Wybierz przycisk **PowerApps**, a następnie wybierz opcję **Wstaw PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="09b5b-118">Select the **PowerApps** button, and then select **Insert a PowerApp**.</span></span>

    ![Przycisk PowerApps](media/png.png)

3. <span data-ttu-id="09b5b-120">Wypełnij pola w oknie dialogowym **Wstaw PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="09b5b-120">Complete the fields in the **Insert a PowerApp** dialog box.</span></span>

    ![Okno dialogowe Wstaw PowerApp](media/insert-powerapp.png)

<span data-ttu-id="09b5b-122">Można też wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="09b5b-122">Alternatively, follow these steps.</span></span>

1. <span data-ttu-id="09b5b-123">W okienku akcji strony na karcie **Opcje** w grupie **Personalizacja** wybierz **Personalizuj ten formularz**.</span><span class="sxs-lookup"><span data-stu-id="09b5b-123">On the page's Action Pane, on the **Options** tab, in the **Personalize** group, select **Personalize this form**.</span></span>

    ![Personalizowanie grupy na karcie Opcje](media/options.png)

    <span data-ttu-id="09b5b-125">Pojawi się pasek narzędzi personalizacji.</span><span class="sxs-lookup"><span data-stu-id="09b5b-125">The personalization toolbar appears.</span></span>

2. <span data-ttu-id="09b5b-126">Na pasku narzędzi, wybierz **Wstaw \>PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="09b5b-126">On the toolbar, select **Insert \> PowerApp**.</span></span>

    ![Wstawianie aplikacji PowerApps za pomocą paska narzędzi personalizacji](media/powerapp-bar.png)

