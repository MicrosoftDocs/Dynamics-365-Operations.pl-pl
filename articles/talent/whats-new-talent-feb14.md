---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (14 lutego 2019 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 02/14/2019
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
ms.search.validFrom: 2019-02-14
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 32f3bab38233833498ed566fa1558a023b3bc0dd
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/06/2019
ms.locfileid: "2899227"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-february-14-2019"></a><span data-ttu-id="d284b-103">Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (14 lutego 2019 r.)</span><span class="sxs-lookup"><span data-stu-id="d284b-103">What's new or changed in Dynamics 365 Talent (February 14, 2019)</span></span>

<span data-ttu-id="d284b-104">W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Talent.</span><span class="sxs-lookup"><span data-stu-id="d284b-104">This topic describes features that are either new or changed in Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="d284b-105">Zmiany w Attract</span><span class="sxs-lookup"><span data-stu-id="d284b-105">Changes in Attract</span></span>
<span data-ttu-id="d284b-106">Inne niewielkie poprawki są dołączone do tej wersji.</span><span class="sxs-lookup"><span data-stu-id="d284b-106">There are minor bug fixes included with this release.</span></span>

## <a name="changes-in-onboarding"></a><span data-ttu-id="d284b-107">Zmiany we wdrażaniu do pracy</span><span class="sxs-lookup"><span data-stu-id="d284b-107">Changes in Onboarding</span></span>
<span data-ttu-id="d284b-108">Inne niewielkie poprawki są dołączone do tej wersji.</span><span class="sxs-lookup"><span data-stu-id="d284b-108">There are minor bug fixes included with this release.</span></span>
 
## <a name="changes-in-core-hr"></a><span data-ttu-id="d284b-109">Zmiany w Core HR</span><span class="sxs-lookup"><span data-stu-id="d284b-109">Changes in Core HR</span></span> 
<span data-ttu-id="d284b-110">**Kompilacja 8.1.2146**</span><span class="sxs-lookup"><span data-stu-id="d284b-110">**Build 8.1.2146**</span></span>

### <a name="employee-fixed-compensation-entity-doesnt-export-all-records"></a><span data-ttu-id="d284b-111">Jednostki stałego wynagrodzenia pracownika nie eksportują wszystkich rekordów</span><span class="sxs-lookup"><span data-stu-id="d284b-111">Employee fixed compensation entity doesn't export all records</span></span>
<span data-ttu-id="d284b-112">Z tą zmianą jednostka **stałe wynagrodzenie pracownika** będzie teraz eksportować wszystkie rekordy.</span><span class="sxs-lookup"><span data-stu-id="d284b-112">With this change, the **Employee fixed compensation** entity will now export all records.</span></span> <span data-ttu-id="d284b-113">Jednostka może służyć do tworzenia i aktualizowania istniejących rekordów stałego wynagrodzenia dla pracowników.</span><span class="sxs-lookup"><span data-stu-id="d284b-113">The entity can be used to create and update existing fixed compensation records for employees.</span></span> 

### <a name="employment-end-date-doesnt-honor-employee-preferred-time-zone-settings"></a><span data-ttu-id="d284b-114">Data zakończenia zatrudnienia nie uwzględnia ustawienia preferowanej strefy czasowej pracownika</span><span class="sxs-lookup"><span data-stu-id="d284b-114">Employment end date doesn't honor employee preferred time zone settings</span></span>
<span data-ttu-id="d284b-115">Daty zakończenia zatrudnienia uwzględniają teraz strefę czasową preferowaną przez użytkownika podczas tworzenia lub zakończenia zatrudnienia w firmie.</span><span class="sxs-lookup"><span data-stu-id="d284b-115">Employment end dates are now honoring the user-preferred time zone when creating or ending employment with a company.</span></span>
 
### <a name="uk-addresses-display-in-analytics-as-eastern-switzerland-addresses"></a><span data-ttu-id="d284b-116">Brytyjskie adresy są wyświetlane w Analytics jako adresy we wschodniej Szwajcarii</span><span class="sxs-lookup"><span data-stu-id="d284b-116">UK addresses display in Analytics as Eastern Switzerland addresses</span></span>
<span data-ttu-id="d284b-117">W tej wersji została wprowadzona zmiana, aby naprawić niespójność w adresach w raporcie "stan osobowy według lokalizacji" **zarządzania personelem**.</span><span class="sxs-lookup"><span data-stu-id="d284b-117">In this release, a change has been made to correct misalignment in addresses in the **Personnel Management** "Headcount by location" report.</span></span>
 
### <a name="termination-code-is-not-populated-on-the-worker-position-assignment-record-when-ending-the-position"></a><span data-ttu-id="d284b-118">Kod zwolnienia nie jest wypełniony dla rekordu przypisania stanowiska pracownika przy wygaśnięciu zatrudnienia na stanowisku</span><span class="sxs-lookup"><span data-stu-id="d284b-118">Termination code is not populated on the worker position assignment record when ending the position</span></span>
<span data-ttu-id="d284b-119">Wprowadzono zmianę w domyślnym kodzie "Powód rozwiązania umowy" przy dodawaniu przypisania stanowiska do pracownika.</span><span class="sxs-lookup"><span data-stu-id="d284b-119">A change has been made to default the "Termination reason" code when ending the employees position assignment.</span></span>

### <a name="new-entity-created-for-job-compensation-levels"></a><span data-ttu-id="d284b-120">Utworzono nową jednostkę dla poziomów wynagrodzenia</span><span class="sxs-lookup"><span data-stu-id="d284b-120">New entity created for job compensation levels</span></span>
<span data-ttu-id="d284b-121">Utworzono nową jednostkę DMF.</span><span class="sxs-lookup"><span data-stu-id="d284b-121">A new data management framework (DMF) entity was created.</span></span> <span data-ttu-id="d284b-122">Jednostka zapewnia tworzenie i aktualizacje poziomów wynagrodzeń, wartości rynkowej i informacji dotyczących badania dla każdego stanowiska zdefiniowanego w systemie.</span><span class="sxs-lookup"><span data-stu-id="d284b-122">The entity provides for creation and updates to compensation levels, market values, and survey information for each job defined in the system.</span></span>
