---
title: Osadzona aplikacja Power Apps w Dynamics 365 - Core HR
description: W tym temacie opisano, jak rozwiązać problem, gdzie element menu usługi Microsoft Power Apps znika w module Administracja systemu.
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
ms.openlocfilehash: 6d1b7f1dd71e6bcbf10c4d91fe33e9494b041a2c
ms.sourcegitcommit: ae0efac749ab34d423fac44d00a597801c143fbb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/22/2019
ms.locfileid: "2830216"
---
# <a name="embed-power-apps-apps-in-dynamics-365---core-hr"></a><span data-ttu-id="a5f91-103">Osadzona aplikacja Power Apps w Dynamics 365 - Core HR</span><span class="sxs-lookup"><span data-stu-id="a5f91-103">Embed Power Apps apps in Dynamics 365 - Core HR</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a5f91-104">**Wystawienie**</span><span class="sxs-lookup"><span data-stu-id="a5f91-104">**Issue**</span></span>

<span data-ttu-id="a5f91-105">Element menu **Power Apps** zniknął z modułu **Administrowanie systemem**.</span><span class="sxs-lookup"><span data-stu-id="a5f91-105">The **Power Apps** menu item has disappeared from the **System administration** module.</span></span>

<span data-ttu-id="a5f91-106">**Przyczyna**</span><span class="sxs-lookup"><span data-stu-id="a5f91-106">**Cause**</span></span>

<span data-ttu-id="a5f91-107">Projekt interfejsu użytkownika został zmieniony, a Microsoft Power Apps zostanie dołączony do modelu standardowego personalizacji.</span><span class="sxs-lookup"><span data-stu-id="a5f91-107">The user interface (UI) design has been changed, and Microsoft Power Apps is now included in the standard personalization model.</span></span>

<span data-ttu-id="a5f91-108">**Rozdzielczość**</span><span class="sxs-lookup"><span data-stu-id="a5f91-108">**Resolution**</span></span>

<span data-ttu-id="a5f91-109">Zmienił się sposób osadzenia usługi Power Apps.</span><span class="sxs-lookup"><span data-stu-id="a5f91-109">The way that Power Apps are embedded has been changed.</span></span> <span data-ttu-id="a5f91-110">Power Apps teraz są dodawane za pomocą modelu personalizacji.</span><span class="sxs-lookup"><span data-stu-id="a5f91-110">Power Apps are now added through the personalization model.</span></span> <span data-ttu-id="a5f91-111">Power Apps można dodać do prawie wszystkich stron w Microsoft Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="a5f91-111">You can add Power Apps to almost all pages in Microsoft Dynamics 365 Talent.</span></span>

<span data-ttu-id="a5f91-112">Aby uzyskać szczegółowe informacje o osadzaniu aplikacji Power Apps w Talents, zobacz [Osadzone Microsoft Power Apps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span><span class="sxs-lookup"><span data-stu-id="a5f91-112">For information about how to embed Power Apps in Talent, see [Embed Microsoft Power Apps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span></span>

<span data-ttu-id="a5f91-113">Odbiorcy Power Apps, którzy osadzili aplikacje przed zmianą powinni mieć uaktualniony system do nowego modelu.</span><span class="sxs-lookup"><span data-stu-id="a5f91-113">Any Power Apps customer who embedded apps before the change should have been upgraded to the new model.</span></span>

<span data-ttu-id="a5f91-114">Przycisk **Power Apps** znajduje się w prawym górnym rogu prawie każdej strony w Talent.</span><span class="sxs-lookup"><span data-stu-id="a5f91-114">The **Power Apps** button is in the upper-right corner of almost every page in Talent.</span></span> <span data-ttu-id="a5f91-115">Ten przycisk służy do wstawiania Power Apps.</span><span class="sxs-lookup"><span data-stu-id="a5f91-115">You can use this button to insert Power Apps.</span></span>

<span data-ttu-id="a5f91-116">Oto przykład.</span><span class="sxs-lookup"><span data-stu-id="a5f91-116">Here is an example.</span></span>

1. <span data-ttu-id="a5f91-117">Przejdź do **zarządzania personelem \>łącza \>pracownicy \>pracownicy**.</span><span class="sxs-lookup"><span data-stu-id="a5f91-117">Go to **Personnel management \> Links \> Workers \> Employees**.</span></span>
2. <span data-ttu-id="a5f91-118">Wybierz przycisk **Power Apps**, a następnie wybierz opcję **Wstaw PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="a5f91-118">Select the **Power Apps** button, and then select **Insert a PowerApp**.</span></span>

    ![Przycisk Power Apps](media/png.png)

3. <span data-ttu-id="a5f91-120">Wypełnij pola w oknie dialogowym **Wstaw PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="a5f91-120">Complete the fields in the **Insert a PowerApp** dialog box.</span></span>

    ![Okno dialogowe Wstaw PowerApp](media/insert-powerapp.png)

<span data-ttu-id="a5f91-122">Można też wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a5f91-122">Alternatively, follow these steps.</span></span>

1. <span data-ttu-id="a5f91-123">W okienku akcji strony na karcie **Opcje** w grupie **Personalizacja** wybierz **Personalizuj ten formularz**.</span><span class="sxs-lookup"><span data-stu-id="a5f91-123">On the page's Action Pane, on the **Options** tab, in the **Personalize** group, select **Personalize this form**.</span></span>

    ![Personalizowanie grupy na karcie Opcje](media/options.png)

    <span data-ttu-id="a5f91-125">Pojawi się pasek narzędzi personalizacji.</span><span class="sxs-lookup"><span data-stu-id="a5f91-125">The personalization toolbar appears.</span></span>

2. <span data-ttu-id="a5f91-126">Na pasku narzędzi, wybierz **Wstaw \>PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="a5f91-126">On the toolbar, select **Insert \> PowerApp**.</span></span>

    ![Wstawianie aplikacji Power Apps za pomocą paska narzędzi personalizacji](media/powerapp-bar.png)
