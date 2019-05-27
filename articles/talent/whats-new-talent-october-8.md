---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent Core HR (1 października 2018 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 10/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-10-07
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 92f06d29dfa8110106a2a0e71434b2c0c75110b5
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518860"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-october-8-2018"></a><span data-ttu-id="1d312-103">Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent Core HR (8 października 2018 r.)</span><span class="sxs-lookup"><span data-stu-id="1d312-103">What's new or changed in Dynamics 365 for Talent Core HR (October 8, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1d312-104">**Kompilacja 8.1.1050.0**</span><span class="sxs-lookup"><span data-stu-id="1d312-104">**Build 8.1.1050.0**</span></span>

<span data-ttu-id="1d312-105">W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Core HR.</span><span class="sxs-lookup"><span data-stu-id="1d312-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="allow-other-dates-to-be-used-on-leave-tier-basis-leave-management"></a><span data-ttu-id="1d312-106">Zezwalanie na używanie innych dat w podstawach warstw urlopów (Zarządzanie urlopami)</span><span class="sxs-lookup"><span data-stu-id="1d312-106">Allow other dates to be used on leave tier basis (Leave Management)</span></span>

<span data-ttu-id="1d312-107">Podczas udzielania pracownikom urlopów podstawa warstwy przyznania określa, ile czasu wolnego zostanie naliczone pracownikowi.</span><span class="sxs-lookup"><span data-stu-id="1d312-107">When awarding leave to employees, the award tier basis determines how much time off an employee accrues.</span></span> <span data-ttu-id="1d312-108">Obecnie te warstwy są oparte na dacie rozpoczęcia zatrudnienia i dacie stażu pracy.</span><span class="sxs-lookup"><span data-stu-id="1d312-108">Currently, these tiers are based on employee start date and seniority date.</span></span> <span data-ttu-id="1d312-109">W niektórych scenariuszach organizacje muszą oprzeć te warstwy na innych datach, takich jak data rocznicy lub pierwotna data zatrudnienia.</span><span class="sxs-lookup"><span data-stu-id="1d312-109">In some scenarios, organizations need these tiers to be based on other dates, like anniversary date or original hire date.</span></span> <span data-ttu-id="1d312-110">Te daty są już używane w planie urlopów do określania momentów naliczania. Teraz dodano możliwość używania tych samych dat podczas rejestrowania pracownika do planu w celu ustalania ilości do naliczenia.</span><span class="sxs-lookup"><span data-stu-id="1d312-110">These dates are already used on the leave plan to determine when accruals happen, the ability for these same dates to be used when an employee is enrolled in a plan have been added to determine the accrual amount.</span></span> 

## <a name="other-changes"></a><span data-ttu-id="1d312-111">Inne zmiany</span><span class="sxs-lookup"><span data-stu-id="1d312-111">Other changes</span></span>
<span data-ttu-id="1d312-112">W tej wersji wprowadzono wiele różnych poprawek.</span><span class="sxs-lookup"><span data-stu-id="1d312-112">Miscellanous fixes have been included in this release.</span></span>

## <a name="known-issue"></a><span data-ttu-id="1d312-113">Znany problem</span><span class="sxs-lookup"><span data-stu-id="1d312-113">Known issue</span></span>

<span data-ttu-id="1d312-114">**Problem:** podczas dodawania nowego załącznika do pracownika przyciski **Nowy** i **Edytuj** są wyszarzone. **Obejście:** przed otwarciem strony załącznika upewnij się, że pola informacji na stronie **Pracownik** są zamknięte.</span><span class="sxs-lookup"><span data-stu-id="1d312-114">**Issue:** When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out. **Workaround:** Before opening the attachment page, make sure that the FactBoxes on the **Worker** page are closed.</span></span> <span data-ttu-id="1d312-115">Jeśli pola informacji są zamknięte podczas wczytywania strony **Pracownik**, przyciski złączników będą włączone.</span><span class="sxs-lookup"><span data-stu-id="1d312-115">If the FactBoxes are closed when the **Worker** page is loaded, the attachments buttons will be enabled.</span></span> <span data-ttu-id="1d312-116">(Ten problem zostanie rozwiązany w następnej aktualizacji platformy).</span><span class="sxs-lookup"><span data-stu-id="1d312-116">(This issue will be fixed in the next platform update.)</span></span>
