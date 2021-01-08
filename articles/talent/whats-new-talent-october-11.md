---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent - Core HR (15 października 2018 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 10/15/2018
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
ms.search.validFrom: 2018-10-11
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 96f877ae284a0f914bae2d0f5e5f7caf49109511
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462211"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-october-15-2018"></a><span data-ttu-id="a118c-103">Nowości i zmiany w rozwiązaniu Dynamics 365 Talent - Core HR (15 października 2018 r.)</span><span class="sxs-lookup"><span data-stu-id="a118c-103">What's new or changed in Dynamics 365 Talent - Core HR (October 15, 2018)</span></span>

<span data-ttu-id="a118c-104">**Kompilacja 8.1.1056**</span><span class="sxs-lookup"><span data-stu-id="a118c-104">**Build 8.1.1056**</span></span>

<span data-ttu-id="a118c-105">W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Core HR.</span><span class="sxs-lookup"><span data-stu-id="a118c-105">This topic describes features that are either new or changed in Core HR.</span></span>


## <a name="changes"></a><span data-ttu-id="a118c-106">Zmiany</span><span class="sxs-lookup"><span data-stu-id="a118c-106">Changes</span></span>
<span data-ttu-id="a118c-107">Poza wieloma różnymi poprawkami w tym wydaniu wprowadzono następujące aktualizacje:</span><span class="sxs-lookup"><span data-stu-id="a118c-107">In addition to miscellanous fixes, the following updates have been made in this release:</span></span>
- <span data-ttu-id="a118c-108">Ostatni dzień pracy jest teraz ustawiany podczas zatrudniania lub ustawiana daty zakończenia zatrudnienia.</span><span class="sxs-lookup"><span data-stu-id="a118c-108">Last Day worked now set when hiring or setting an employment end date.</span></span>
- <span data-ttu-id="a118c-109">Usunięto odwołania do zgodności z ustawodawstwem amerykańskim (ACA, ADA i I9) w firmach z innych krajów.</span><span class="sxs-lookup"><span data-stu-id="a118c-109">US compliance references removed when in non US companies (ACA, ADA, and I9).</span></span>
- <span data-ttu-id="a118c-110">Nieprawidłowe daty (1.1.1900) są teraz ukryte na stronach analiz.</span><span class="sxs-lookup"><span data-stu-id="a118c-110">Invalid dates (1/1/1900) are now hidden on analytics pages.</span></span>

## <a name="known-issue"></a><span data-ttu-id="a118c-111">Znany problem</span><span class="sxs-lookup"><span data-stu-id="a118c-111">Known issue</span></span>

<span data-ttu-id="a118c-112">**Problem:** podczas dodawania nowego załącznika do pracownika przyciski **Nowy** i **Edytuj** są wyszarzone. **Obejście:** przed otwarciem strony załącznika upewnij się, że pola informacji na stronie **Pracownik** są zamknięte.</span><span class="sxs-lookup"><span data-stu-id="a118c-112">**Issue:** When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out. **Workaround:** Before opening the attachment page, make sure that the FactBoxes on the **Worker** page are closed.</span></span> <span data-ttu-id="a118c-113">Jeśli pola informacji są zamknięte podczas wczytywania strony **Pracownik**, przyciski złączników będą włączone.</span><span class="sxs-lookup"><span data-stu-id="a118c-113">If the FactBoxes are closed when the **Worker** page is loaded, the attachments buttons will be enabled.</span></span> <span data-ttu-id="a118c-114">(Ten problem zostanie rozwiązany w następnej aktualizacji platformy).</span><span class="sxs-lookup"><span data-stu-id="a118c-114">(This issue will be fixed in the next platform update.)</span></span>
