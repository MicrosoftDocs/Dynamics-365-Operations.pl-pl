---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent - Core HR (24 września 2018 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 09/21/2018
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
ms.search.validFrom: 2018-09-30
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 6001b3c777be005dfc0b22ca0b64d5c56a56cb1e
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2019
ms.locfileid: "2010068"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-core-hr-september-24-2018"></a><span data-ttu-id="2f557-103">Nowości i zmiany w rozwiązaniu Dynamics 365 Talent: Core HR (24 września 2018 r.)</span><span class="sxs-lookup"><span data-stu-id="2f557-103">What's new or changed in Dynamics 365 Talent: Core HR (September 24, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2f557-104">**Kompilacja 8.1.1015.0**</span><span class="sxs-lookup"><span data-stu-id="2f557-104">**Build 8.1.1015.0**</span></span>

<span data-ttu-id="2f557-105">W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Core HR.</span><span class="sxs-lookup"><span data-stu-id="2f557-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="currency-added-to-benefits"></a><span data-ttu-id="2f557-106">Dodano funkcję walut do świadczeń</span><span class="sxs-lookup"><span data-stu-id="2f557-106">Currency added to Benefits</span></span>

<span data-ttu-id="2f557-107">Funkcjonalność planów świadczeń została zaktualizowana o pole waluty świadczenia.</span><span class="sxs-lookup"><span data-stu-id="2f557-107">Benefit plans have been updated to include the currency of the benefit.</span></span> <span data-ttu-id="2f557-108">To nowe pole jest również dostępne na świadczeń, w których rejestrują się pracownicy.</span><span class="sxs-lookup"><span data-stu-id="2f557-108">This new field is also available on worker enrolled benefits.</span></span> <span data-ttu-id="2f557-109">To nowe pole jest częścią uprawnień Obsługa świadczeń i Wyświetl listę świadczeń.</span><span class="sxs-lookup"><span data-stu-id="2f557-109">This new field is part of the Maintain benefits and View a list of benefits security privilege.</span></span>

## <a name="update-proration-process--leave-and-absence"></a><span data-ttu-id="2f557-110">Zaktualizowano proces obliczania proporcjonalnego — Urlopy i nieobecności</span><span class="sxs-lookup"><span data-stu-id="2f557-110">Update proration process – Leave and Absence</span></span>

<span data-ttu-id="2f557-111">Organizacje przyznają pulę czasu wolnego/urlopów zależnie od tego, kiedy pracownik rozpoczął i zakończył zatrudnienie.</span><span class="sxs-lookup"><span data-stu-id="2f557-111">Organizations award time off differently based on when employees join and leave the company.</span></span> <span data-ttu-id="2f557-112">W przypadku pracowników opuszczających organizację niektórym trzeba zakończyć naliczanie puli przysługujących wolnych dni z dniem ustania stosunku pracy, a innym w ostatnim przepracowanym dniu.</span><span class="sxs-lookup"><span data-stu-id="2f557-112">For employees leaving the organization, some may need to end the award on the termination date, while others rely on the last day worked to stop the accrual process.</span></span> <span data-ttu-id="2f557-113">Te zmiany umożliwiają organizacjom wybieranie, kiedy zakończyć rejestrację na świadczenia w procesie rozwiązywania stosunku pracy.</span><span class="sxs-lookup"><span data-stu-id="2f557-113">These changes provide organizations the ability to choose when to end enrollment during the termination process.</span></span> <span data-ttu-id="2f557-114">Te nowe opcje są częścią uprawnień Zwolnij pracownika i Zwalnianie pracownika z poziomu samoobsługi menedżera.</span><span class="sxs-lookup"><span data-stu-id="2f557-114">These new options are part of the privileges for Terminate a worker and Terminate a worker from manager self service.</span></span> 

## <a name="other-changes"></a><span data-ttu-id="2f557-115">Inne zmiany</span><span class="sxs-lookup"><span data-stu-id="2f557-115">Other changes</span></span>

<span data-ttu-id="2f557-116">Ta wersja zawiera kilka dodatkowych poprawek błędów.</span><span class="sxs-lookup"><span data-stu-id="2f557-116">This release includes several additional bug fixes.</span></span>

## <a name="known-issue"></a><span data-ttu-id="2f557-117">Znany problem</span><span class="sxs-lookup"><span data-stu-id="2f557-117">Known Issue</span></span>

-   <span data-ttu-id="2f557-118">**Problem:** podczas dodawania nowego załącznika do pracownika przyciski **Nowy** i **Edytuj** są wyszarzone. **Obejście:** przed otwarciem strony załącznika upewnij się, że pola informacji na stronie **Pracownik** są zamknięte.</span><span class="sxs-lookup"><span data-stu-id="2f557-118">**Issue:** When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out. **Workaround:** Before opening the attachment page, make sure that the fact boxes on the **Worker** page are closed.</span></span> <span data-ttu-id="2f557-119">Jeśli pola informacji są zamknięte podczas wczytywania strony **Pracownik**, przyciski w sekcji załączników będą włączone.</span><span class="sxs-lookup"><span data-stu-id="2f557-119">If the fact boxes are closed when the **Worker** page is loaded, the attachments buttons will be enabled.</span></span> <span data-ttu-id="2f557-120">(Ten problem zostanie rozwiązany w następnej aktualizacji platformy).</span><span class="sxs-lookup"><span data-stu-id="2f557-120">(This issue will be fixed in the next platform update.)</span></span>
