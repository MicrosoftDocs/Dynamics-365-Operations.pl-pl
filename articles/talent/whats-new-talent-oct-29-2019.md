---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (29 października 2019 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 10/29/2019
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
ms.search.validFrom: 2019-10-29
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 83b4734190163ebd2dc29096632642bd45c61e8f
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773884"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-october-29-2019"></a><span data-ttu-id="d4829-103">Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (29 października 2019 r.)</span><span class="sxs-lookup"><span data-stu-id="d4829-103">What's new or changed in Dynamics 365 Talent (October 29, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d4829-104">W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="d4829-104">This topic describes features that are either new or changed in Dynamics 365 Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="d4829-105">Zmiany w Attract</span><span class="sxs-lookup"><span data-stu-id="d4829-105">Changes in Attract</span></span>

<span data-ttu-id="d4829-106">Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="d4829-106">This release includes minor bug fixes for Dynamics 365 Talent: Attract.</span></span>

## <a name="changes-in-onboard"></a><span data-ttu-id="d4829-107">Zmiany w Onboard</span><span class="sxs-lookup"><span data-stu-id="d4829-107">Changes in Onboard</span></span>

<span data-ttu-id="d4829-108">Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="d4829-108">This release includes minor bug fixes for Dynamics 365 Talent: Onboard.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="d4829-109">Zmiany w Core HR</span><span class="sxs-lookup"><span data-stu-id="d4829-109">Changes in Core HR</span></span>

<span data-ttu-id="d4829-110">Zmiany opisane w tej części dotyczą kompilacji 8.1.2586.</span><span class="sxs-lookup"><span data-stu-id="d4829-110">Changes described in this section apply to build number 8.1.2586.</span></span> <span data-ttu-id="d4829-111">Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w usługach Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="d4829-111">The numbers in parentheses in some headings refer to support numbers in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

### <a name="delete-parties-with-no-roles-should-be-on-by-default-371233"></a><span data-ttu-id="d4829-112">Usuwanie jednostek bez ról powinno być włączone domyślnie (371233)</span><span class="sxs-lookup"><span data-stu-id="d4829-112">Delete parties with no roles should be on by default (371233)</span></span>

<span data-ttu-id="d4829-113">Jeśli w talentów jest inicjowane nowe środowisko, należy **usunąć jednostki, jeśli nie istnieją** żadne role domyślnie włączone.</span><span class="sxs-lookup"><span data-stu-id="d4829-113">When you provision a new environment in Talent, **Delete parties if no roles exist** is turned on by default.</span></span> <span data-ttu-id="d4829-114">Po usunięciu pracownika jednostka skojarzona z pracownikiem nie jest usuwana, o ile to ustawienie nie jest włączone.</span><span class="sxs-lookup"><span data-stu-id="d4829-114">When you delete a worker, the party associated with the worker is not removed unless this setting is on.</span></span> <span data-ttu-id="d4829-115">Ta zmiana powoduje ograniczenie duplikatów rekordów w globalna książka adresowa, gdy zachodzi potrzeba importu, zmiany lub od importowania pracowników.</span><span class="sxs-lookup"><span data-stu-id="d4829-115">This change limits duplicate records in the global address book when you need to import, change, or reimport workers.</span></span>

### <a name="draft-and-cancelled-leave-requests-should-be-allowed-to-be-deleted-in-common-data-service-376999"></a><span data-ttu-id="d4829-116">Należy zezwolić na usuwanie roboczych i anulowanych żądań urlopów w Common Data Service (376999)</span><span class="sxs-lookup"><span data-stu-id="d4829-116">Draft and cancelled leave requests should be allowed to be deleted in Common Data Service (376999)</span></span>

<span data-ttu-id="d4829-117">Dzięki tej zmianie można teraz usuwać żądania urlopu ze stanem **wersja robocza** lub **anulowane** w systemie Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="d4829-117">With this change, you can now delete leave requests with a status of **Draft** or **Cancelled** in Common Data Service.</span></span>

### <a name="additional-list-values-in-custom-fields-arent-reflected-in-common-data-service-after-clicking-apply-on-the-custom-fields-form-379599"></a><span data-ttu-id="d4829-118">Dodatkowe wartości listy w polach niestandardowych nie są odzwierciedlane Common Data Service po kliknięciu przycisku Zastosuj w formularzu pola niestandardowe (379599)</span><span class="sxs-lookup"><span data-stu-id="d4829-118">Additional list values in custom fields aren't reflected in Common Data Service after clicking Apply on the Custom fields form (379599)</span></span>

<span data-ttu-id="d4829-119">Po dodaniu nowych wartości do istniejącego pola niestandardowego Common Data Service, które jest już zsynchronizowane, są one dostępne w popularnych serivce danych po zastosowaniu zmian w formularzu **pola niestandardowe**.</span><span class="sxs-lookup"><span data-stu-id="d4829-119">When you add new list values to an existing custom field that has already synchronized with Common Data Service, they're now available in Common Data Serivce after you apply your changes in the **Custom fields** form.</span></span>

### <a name="apply-onboarding-checklists-across-legal-entities-when-more-than-one-employment-exists-371270"></a><span data-ttu-id="d4829-120">Stosowanie list kontrolnych na wejściu do firmy w przypadku istnienia więcej niż jednego zatrudnienia (371270)</span><span class="sxs-lookup"><span data-stu-id="d4829-120">Apply onboarding checklists across legal entities when more than one employment exists (371270)</span></span>

<span data-ttu-id="d4829-121">W wersji tego tygodnia można zastosować listy kontrolne do pracowników, którzy mają więcej niż jedno zatrudnienie w **Formularz pracownika >listy kontrolne**.</span><span class="sxs-lookup"><span data-stu-id="d4829-121">In this week's release, you can apply checklists to employees with more than one employment in **Worker form > Checklists**.</span></span>

### <a name="benefits-open-enrollment-preview-feature-has-been-removed"></a><span data-ttu-id="d4829-122">Funkcja zapoznawcza Otwarte zapisy na świadczenia została usunięta.</span><span class="sxs-lookup"><span data-stu-id="d4829-122">Benefits open enrollment preview feature has been removed</span></span>

<span data-ttu-id="d4829-123">W powiązaniu z naszymi oświadczeniami w wpisie na blogu pt. [Strategiczne inwestycje w Core HR zwiększają doskonałość operacyjną](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/10/02/strategic-investments-in-core-hr-drive-operational-excellence), firma Microsoft usunęła funkcję otwartej rejestracji świadczeń z podglądu publicznego.</span><span class="sxs-lookup"><span data-stu-id="d4829-123">In conjunction with our announcement in the [Strategic investments in core HR drive operational excellence](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/10/02/strategic-investments-in-core-hr-drive-operational-excellence) blog post, Microsoft has removed the benefits open enrollment feature from public preview.</span></span> <span data-ttu-id="d4829-124">Nowa funkcjonalność zostanie opublikowana w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="d4829-124">New functionality will be released in the future.</span></span> <span data-ttu-id="d4829-125">Nie jest obsługiwane korzystanie z funkcji rejestrowania świadczeń otwartych w produkcji.</span><span class="sxs-lookup"><span data-stu-id="d4829-125">Production use of the benefits open enrollment feature isn't be supported.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="d4829-126">Wkrótce</span><span class="sxs-lookup"><span data-stu-id="d4829-126">Coming soon</span></span>

### <a name="print-performance-reviews"></a><span data-ttu-id="d4829-127">Drukowanie przeglądów wydajności</span><span class="sxs-lookup"><span data-stu-id="d4829-127">Print performance reviews</span></span>

<span data-ttu-id="d4829-128">Zapoznaj się z [Drukowanie przeglądów wydajności](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) w Dynamics 365: plan 2. fali publikacji 2019.</span><span class="sxs-lookup"><span data-stu-id="d4829-128">See [Print performance reviews](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) in the Dynamics 365: 2019 release wave 2 plan.</span></span>

### <a name="feature-management-workspace"></a><span data-ttu-id="d4829-129">Obszar roboczy zarządzanie funkcjami</span><span class="sxs-lookup"><span data-stu-id="d4829-129">Feature management workspace</span></span>

<span data-ttu-id="d4829-130">Funkcje są dodawane i aktualizowane w każdym wydaniu.</span><span class="sxs-lookup"><span data-stu-id="d4829-130">Features are added and updated in every release.</span></span> <span data-ttu-id="d4829-131">Środowisko zarządzania funkcjami udostępnia obszar roboczy, w którym można wyświetlić listę funkcji, które zostały dostarczone w każdej wersji.</span><span class="sxs-lookup"><span data-stu-id="d4829-131">The feature management experience provides a workspace where you can view a list of features that have been delivered in each release.</span></span> <span data-ttu-id="d4829-132">Domyślnie nowe funkcje są wyłączone.</span><span class="sxs-lookup"><span data-stu-id="d4829-132">By default, new features are turned off.</span></span> <span data-ttu-id="d4829-133">Można użyć obszaru roboczego, aby włączyć je i wyświetlić dokumentację dla nich.</span><span class="sxs-lookup"><span data-stu-id="d4829-133">You can use the workspace to turn them on and view the documentation for them.</span></span>

<span data-ttu-id="d4829-134">Aby dowiedzieć się więcej o zmianach pochodzących z zarządzania funkcjam, zobacz [Omówienie zarządzania funkcjami](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).</span><span class="sxs-lookup"><span data-stu-id="d4829-134">To learn more about the changes coming with feature management, see [Feature management overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).</span></span>
