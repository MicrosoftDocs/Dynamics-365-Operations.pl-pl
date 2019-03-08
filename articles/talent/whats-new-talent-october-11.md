---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent Core HR (15 października 2018 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 10/15/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-10-11
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 1d48bc4bad795611ce322b5f09b78886a50c415c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "305737"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-october-15-2018"></a><span data-ttu-id="e9430-103">Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent Core HR (15 października 2018 r.)</span><span class="sxs-lookup"><span data-stu-id="e9430-103">What's new or changed in Dynamics 365 for Talent Core HR (October 15, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e9430-104">**Kompilacja 8.1.1056**</span><span class="sxs-lookup"><span data-stu-id="e9430-104">**Build 8.1.1056**</span></span>

<span data-ttu-id="e9430-105">W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Core HR.</span><span class="sxs-lookup"><span data-stu-id="e9430-105">This topic describes features that are either new or changed in Core HR.</span></span>


## <a name="changes"></a><span data-ttu-id="e9430-106">Zmiany</span><span class="sxs-lookup"><span data-stu-id="e9430-106">Changes</span></span>
<span data-ttu-id="e9430-107">Poza wieloma różnymi poprawkami w tym wydaniu wprowadzono następujące aktualizacje:</span><span class="sxs-lookup"><span data-stu-id="e9430-107">In addition to miscellanous fixes, the following updates have been made in this release:</span></span>
- <span data-ttu-id="e9430-108">Ostatni dzień pracy jest teraz ustawiany podczas zatrudniania lub ustawiana daty zakończenia zatrudnienia.</span><span class="sxs-lookup"><span data-stu-id="e9430-108">Last Day worked now set when hiring or setting an employment end date.</span></span>
- <span data-ttu-id="e9430-109">Usunięto odwołania do zgodności z ustawodawstwem amerykańskim (ACA, ADA i I9) w firmach z innych krajów.</span><span class="sxs-lookup"><span data-stu-id="e9430-109">US compliance references removed when in non US companies (ACA, ADA, and I9).</span></span>
- <span data-ttu-id="e9430-110">Nieprawidłowe daty (1.1.1900) są teraz ukryte na stronach analiz.</span><span class="sxs-lookup"><span data-stu-id="e9430-110">Invalid dates (1/1/1900) are now hidden on analytics pages.</span></span>

## <a name="known-issue"></a><span data-ttu-id="e9430-111">Znany problem</span><span class="sxs-lookup"><span data-stu-id="e9430-111">Known issue</span></span>

<span data-ttu-id="e9430-112">**Problem:** podczas dodawania nowego załącznika do pracownika przyciski **Nowy** i **Edytuj** są wyszarzone. **Obejście:** przed otwarciem strony załącznika upewnij się, że pola informacji na stronie **Pracownik** są zamknięte.</span><span class="sxs-lookup"><span data-stu-id="e9430-112">**Issue:** When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out. **Workaround:** Before opening the attachment page, make sure that the FactBoxes on the **Worker** page are closed.</span></span> <span data-ttu-id="e9430-113">Jeśli pola informacji są zamknięte podczas wczytywania strony **Pracownik**, przyciski złączników będą włączone.</span><span class="sxs-lookup"><span data-stu-id="e9430-113">If the FactBoxes are closed when the **Worker** page is loaded, the attachments buttons will be enabled.</span></span> <span data-ttu-id="e9430-114">(Ten problem zostanie rozwiązany w następnej aktualizacji platformy).</span><span class="sxs-lookup"><span data-stu-id="e9430-114">(This issue will be fixed in the next platform update.)</span></span>
