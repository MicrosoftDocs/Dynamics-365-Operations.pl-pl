---
title: Osadzenie aplikacji Power Apps w Dynamics 365 Human Resources
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
ms.openlocfilehash: 8275a8a7c68fa13d6b9880c4c411deaa2dcbb998
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/04/2020
ms.locfileid: "3017880"
---
# <a name="embed-power-apps-apps-in-dynamics-365-human-resources"></a><span data-ttu-id="bc770-103">Osadzenie aplikacji Power Apps w Dynamics 365 Human Resources</span><span class="sxs-lookup"><span data-stu-id="bc770-103">Embed Power Apps apps in Dynamics 365 Human Resources</span></span>

<span data-ttu-id="bc770-104">**Wystawienie**</span><span class="sxs-lookup"><span data-stu-id="bc770-104">**Issue**</span></span>

<span data-ttu-id="bc770-105">Element menu **Power Apps** zniknął z modułu **Administrowanie systemem**.</span><span class="sxs-lookup"><span data-stu-id="bc770-105">The **Power Apps** menu item has disappeared from the **System administration** module.</span></span>

<span data-ttu-id="bc770-106">**Przyczyna**</span><span class="sxs-lookup"><span data-stu-id="bc770-106">**Cause**</span></span>

<span data-ttu-id="bc770-107">Projekt interfejsu użytkownika został zmieniony, a Microsoft Power Apps zostanie dołączony do modelu standardowego personalizacji.</span><span class="sxs-lookup"><span data-stu-id="bc770-107">The user interface (UI) design has been changed, and Microsoft Power Apps is now included in the standard personalization model.</span></span>

<span data-ttu-id="bc770-108">**Rozdzielczość**</span><span class="sxs-lookup"><span data-stu-id="bc770-108">**Resolution**</span></span>

<span data-ttu-id="bc770-109">Zmienił się sposób osadzenia usługi Power Apps.</span><span class="sxs-lookup"><span data-stu-id="bc770-109">The way that Power Apps are embedded has been changed.</span></span> <span data-ttu-id="bc770-110">Power Apps teraz są dodawane za pomocą modelu personalizacji.</span><span class="sxs-lookup"><span data-stu-id="bc770-110">Power Apps are now added through the personalization model.</span></span> <span data-ttu-id="bc770-111">Power Apps można dodać do prawie wszystkich stron w Microsoft Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="bc770-111">You can add Power Apps to almost all pages in Microsoft Dynamics 365 Talent.</span></span>

<span data-ttu-id="bc770-112">Aby uzyskać szczegółowe informacje o osadzaniu aplikacji Power Apps w Talents, zobacz [Osadzone Power Apps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span><span class="sxs-lookup"><span data-stu-id="bc770-112">For information about how to embed Power Apps in Talent, see [Embed Power Apps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span></span>

<span data-ttu-id="bc770-113">Odbiorcy Power Apps, którzy osadzili aplikacje przed zmianą powinni mieć uaktualniony system do nowego modelu.</span><span class="sxs-lookup"><span data-stu-id="bc770-113">Any Power Apps customer who embedded apps before the change should have been upgraded to the new model.</span></span>

<span data-ttu-id="bc770-114">Przycisk **Power Apps** znajduje się w prawym górnym rogu prawie każdej strony w Talent.</span><span class="sxs-lookup"><span data-stu-id="bc770-114">The **Power Apps** button is in the upper-right corner of almost every page in Talent.</span></span> <span data-ttu-id="bc770-115">Ten przycisk służy do wstawiania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="bc770-115">You can use this button to insert apps.</span></span>

<span data-ttu-id="bc770-116">Oto przykład.</span><span class="sxs-lookup"><span data-stu-id="bc770-116">Here is an example.</span></span>

1. <span data-ttu-id="bc770-117">Przejdź do **zarządzania personelem \>łącza \>pracownicy \>pracownicy**.</span><span class="sxs-lookup"><span data-stu-id="bc770-117">Go to **Personnel management \> Links \> Workers \> Employees**.</span></span>
2. <span data-ttu-id="bc770-118">Wybierz przycisk **Power Apps**, a następnie wybierz opcję **Dodaj aplikację z Power Apps**.</span><span class="sxs-lookup"><span data-stu-id="bc770-118">Select the **Power Apps** button, and then select **Add an app from Power Apps**.</span></span>

    ![Przycisk Power Apps](media/png.png)

3. <span data-ttu-id="bc770-120">Wypełnij pola w oknie dialogowym **Dodaj aplikację z Power Apps**.</span><span class="sxs-lookup"><span data-stu-id="bc770-120">Complete the fields in the **Add an app from Power Apps** dialog box.</span></span>

    ![Dodawanie aplikacji z  okna dialogowego Power Apps](media/insert-powerapp.png)

<span data-ttu-id="bc770-122">Można też wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="bc770-122">Alternatively, follow these steps.</span></span>

1. <span data-ttu-id="bc770-123">W okienku akcji strony na karcie **Opcje** w grupie **Personalizacja** wybierz **Personalizuj tę stronę**.</span><span class="sxs-lookup"><span data-stu-id="bc770-123">On the page's Action Pane, on the **Options** tab, in the **Personalize** group, select **Personalize this page**.</span></span>

    ![Personalizowanie grupy na karcie Opcje](media/options.png)

    <span data-ttu-id="bc770-125">Pojawi się pasek narzędzi personalizacji.</span><span class="sxs-lookup"><span data-stu-id="bc770-125">The personalization toolbar appears.</span></span>

2. <span data-ttu-id="bc770-126">Na pasku narzędzi wybierz opcję **Dodaj aplikację z Power Apps**.</span><span class="sxs-lookup"><span data-stu-id="bc770-126">On the toolbar, select **Add an app from Power Apps**.</span></span>

    ![Wstawianie aplikacji Power Apps za pomocą paska narzędzi personalizacji](media/powerapp-bar.png)
