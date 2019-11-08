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
ms.openlocfilehash: a19aa20cef7d8671876a5fd5e8552ff72d6d29ac
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/03/2019
ms.locfileid: "2551354"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-october-15-2018"></a><span data-ttu-id="b7a08-103">Nowości i zmiany w rozwiązaniu Dynamics 365 Talent - Core HR (15 października 2018 r.)</span><span class="sxs-lookup"><span data-stu-id="b7a08-103">What's new or changed in Dynamics 365 Talent - Core HR (October 15, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b7a08-104">**Kompilacja 8.1.1056**</span><span class="sxs-lookup"><span data-stu-id="b7a08-104">**Build 8.1.1056**</span></span>

<span data-ttu-id="b7a08-105">W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Core HR.</span><span class="sxs-lookup"><span data-stu-id="b7a08-105">This topic describes features that are either new or changed in Core HR.</span></span>


## <a name="changes"></a><span data-ttu-id="b7a08-106">Zmiany</span><span class="sxs-lookup"><span data-stu-id="b7a08-106">Changes</span></span>
<span data-ttu-id="b7a08-107">Poza wieloma różnymi poprawkami w tym wydaniu wprowadzono następujące aktualizacje:</span><span class="sxs-lookup"><span data-stu-id="b7a08-107">In addition to miscellanous fixes, the following updates have been made in this release:</span></span>
- <span data-ttu-id="b7a08-108">Ostatni dzień pracy jest teraz ustawiany podczas zatrudniania lub ustawiana daty zakończenia zatrudnienia.</span><span class="sxs-lookup"><span data-stu-id="b7a08-108">Last Day worked now set when hiring or setting an employment end date.</span></span>
- <span data-ttu-id="b7a08-109">Usunięto odwołania do zgodności z ustawodawstwem amerykańskim (ACA, ADA i I9) w firmach z innych krajów.</span><span class="sxs-lookup"><span data-stu-id="b7a08-109">US compliance references removed when in non US companies (ACA, ADA, and I9).</span></span>
- <span data-ttu-id="b7a08-110">Nieprawidłowe daty (1.1.1900) są teraz ukryte na stronach analiz.</span><span class="sxs-lookup"><span data-stu-id="b7a08-110">Invalid dates (1/1/1900) are now hidden on analytics pages.</span></span>

## <a name="known-issue"></a><span data-ttu-id="b7a08-111">Znany problem</span><span class="sxs-lookup"><span data-stu-id="b7a08-111">Known issue</span></span>

<span data-ttu-id="b7a08-112">**Problem:** podczas dodawania nowego załącznika do pracownika przyciski **Nowy** i **Edytuj** są wyszarzone. **Obejście:** przed otwarciem strony załącznika upewnij się, że pola informacji na stronie **Pracownik** są zamknięte.</span><span class="sxs-lookup"><span data-stu-id="b7a08-112">**Issue:** When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out. **Workaround:** Before opening the attachment page, make sure that the FactBoxes on the **Worker** page are closed.</span></span> <span data-ttu-id="b7a08-113">Jeśli pola informacji są zamknięte podczas wczytywania strony **Pracownik**, przyciski złączników będą włączone.</span><span class="sxs-lookup"><span data-stu-id="b7a08-113">If the FactBoxes are closed when the **Worker** page is loaded, the attachments buttons will be enabled.</span></span> <span data-ttu-id="b7a08-114">(Ten problem zostanie rozwiązany w następnej aktualizacji platformy).</span><span class="sxs-lookup"><span data-stu-id="b7a08-114">(This issue will be fixed in the next platform update.)</span></span>
