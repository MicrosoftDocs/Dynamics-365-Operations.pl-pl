---
title: Śledzenie źródeł profilów i zgłoszeń kandydatów
description: Ten temat zawiera informacje dotyczące śledzenia źródła dla profili kandydata i zgłoszeń.
author: hachandr
manager: AnnBe
ms.date: 03/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: ebc82ada31d2803800358cd9aecfe389ada8f0dc
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518868"
---
# <a name="track-sources-for-candidate-profiles-and-applications"></a><span data-ttu-id="d845a-103">Śledzenie źródeł profilów i zgłoszeń kandydatów</span><span class="sxs-lookup"><span data-stu-id="d845a-103">Track sources for candidate profiles and applications</span></span> 

[!include[banner](../includes/banner.md)]

> [!NOTE] 
> <span data-ttu-id="d845a-104">Funkcje wymienione w tym temacie są dostępne w ramach wydania wersji zapoznawczej.</span><span class="sxs-lookup"><span data-stu-id="d845a-104">Functionality noted in this topic is available as part of a preview review release.</span></span> <span data-ttu-id="d845a-105">Zawartość i funkcje mogą ulec zmianie.</span><span class="sxs-lookup"><span data-stu-id="d845a-105">The content and the functionality are subject to change.</span></span> <span data-ttu-id="d845a-106">Aby użyć tej funkcji, poproś administratora o włączenie jej za pomocą **ustawień administratora** w Attract.</span><span class="sxs-lookup"><span data-stu-id="d845a-106">To use this feature, ask an administrator to enable it using the **Admin settings** in Attract.</span></span> <span data-ttu-id="d845a-107">W przyszłej wersji będą dostępne raporty ze śledzenia źródła.</span><span class="sxs-lookup"><span data-stu-id="d845a-107">A future release will provide source tracking reports.</span></span> <span data-ttu-id="d845a-108">Aby uzyskać więcej informacji, zobacz [Dostęp do funkcji w wersji zapoznawczej w aplikacji Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/access-preview-feature).</span><span class="sxs-lookup"><span data-stu-id="d845a-108">For more information, see [Access preview features in Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/access-preview-feature).</span></span>

<span data-ttu-id="d845a-109">Gdy kandydaci zgłaszają się do pracy na stanowisku, Attract automatycznie śledzi źródła ich aplikacji, zapewniając cenne informacje, które pomagają w procesie rekrutacji.</span><span class="sxs-lookup"><span data-stu-id="d845a-109">When candidates apply for a job, Attract automatically tracks the source of their applications, providing you with valuable information to help you target your recruiting efforts.</span></span> <span data-ttu-id="d845a-110">Osoby prowadzące rekrutację i menedżerowie zatrudniający mogą także wybrać źródła aplikacji, dodając ręcznie kandydata do stanowiska lub puli umiejętności i kandydatów.</span><span class="sxs-lookup"><span data-stu-id="d845a-110">Recruiters and hiring managers can also select an application source while manually adding a candidate to a job or talent pool.</span></span>

<span data-ttu-id="d845a-111">Można wyświetlić źródło aplikacji w szczegółach działań aplikacji na karcie **działania**, a także w historii aplikacji w obszarze **profilu** w pulach umiejętności i kandydatów.</span><span class="sxs-lookup"><span data-stu-id="d845a-111">You can view the application source in the application activity details under the **Activity** tab, as well as in the application history available under **Profile** in talent pools.</span></span> <span data-ttu-id="d845a-112">Można znaleźć źródło profilu kandydata w szczegółach kandydata na karcie **profil** zarówno w aplikacjach, jak i pulach umiejętności i kandydatów.</span><span class="sxs-lookup"><span data-stu-id="d845a-112">You can find a candidate's profile source in the candidate details under the **Profile** tab in both applications and talent pools.</span></span>

> [!NOTE] 
> <span data-ttu-id="d845a-113">Szablony procesów są dostępne po zainstalowaniu [dodatku kompleksowej obsługi rekrutacji](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span><span class="sxs-lookup"><span data-stu-id="d845a-113">You can find process templates in the [Comprehensive hiring add-on](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span></span>

## <a name="pre-configured-sources"></a><span data-ttu-id="d845a-114">Wstępnie skonfigurowane źródła</span><span class="sxs-lookup"><span data-stu-id="d845a-114">Pre-configured sources</span></span>

<span data-ttu-id="d845a-115">Domyślna lista źródeł zawiera wspólne źródła aplikacji.</span><span class="sxs-lookup"><span data-stu-id="d845a-115">The default source list contains common application sources.</span></span> <span data-ttu-id="d845a-116">Niektóre typy źródeł, takie jak **Tablica funkcji** i **Sieć społecznościowa** mają dodatkowe szczegóły źródeł.</span><span class="sxs-lookup"><span data-stu-id="d845a-116">Some source types, like **Job board** and **Social Network**, have additional source details.</span></span> <span data-ttu-id="d845a-117">Na przykład **sieć społecznościowa** obejmuje witryny, takie jak Facebook i Twitter.</span><span class="sxs-lookup"><span data-stu-id="d845a-117">For example, **Social Network** includes Facebook and Twitter.</span></span> <span data-ttu-id="d845a-118">Typ źródła **Polecenie** umożliwia określenie pracownika wewnętrznego jako osoby polecającej.</span><span class="sxs-lookup"><span data-stu-id="d845a-118">The **Referral** source type allows you to specify an internal employee as the referrer.</span></span> <span data-ttu-id="d845a-119">Domyślna lista źródeł zawiera następujące wstępnie skonfigurowane źródła:</span><span class="sxs-lookup"><span data-stu-id="d845a-119">The default source list includes the following pre-configured sources:</span></span>

-   <span data-ttu-id="d845a-120">Witryna kariery Attract</span><span class="sxs-lookup"><span data-stu-id="d845a-120">Attract career site</span></span>

-   <span data-ttu-id="d845a-121">Agencja</span><span class="sxs-lookup"><span data-stu-id="d845a-121">Agency</span></span>

-   <span data-ttu-id="d845a-122">Targi kariery</span><span class="sxs-lookup"><span data-stu-id="d845a-122">Career Fair</span></span>

-   <span data-ttu-id="d845a-123">Dział marketingu firmy</span><span class="sxs-lookup"><span data-stu-id="d845a-123">Company Marketing</span></span>

-   <span data-ttu-id="d845a-124">Wystawy i konferencje handlowe</span><span class="sxs-lookup"><span data-stu-id="d845a-124">Conferences & Trade shows</span></span>

-   <span data-ttu-id="d845a-125">Stowarzyszenia branżowe</span><span class="sxs-lookup"><span data-stu-id="d845a-125">Professional Association</span></span>

-   <span data-ttu-id="d845a-126">Tablica funkcji</span><span class="sxs-lookup"><span data-stu-id="d845a-126">Job board</span></span>

    -   <span data-ttu-id="d845a-127">Indeed</span><span class="sxs-lookup"><span data-stu-id="d845a-127">Indeed</span></span>

    -   <span data-ttu-id="d845a-128">Seek</span><span class="sxs-lookup"><span data-stu-id="d845a-128">Seek</span></span>

    -   <span data-ttu-id="d845a-129">CareerBuilder</span><span class="sxs-lookup"><span data-stu-id="d845a-129">CareerBuilder</span></span>

    -   <span data-ttu-id="d845a-130">Google Jobs</span><span class="sxs-lookup"><span data-stu-id="d845a-130">Google Jobs</span></span>

    -   <span data-ttu-id="d845a-131">Xing</span><span class="sxs-lookup"><span data-stu-id="d845a-131">Xing</span></span>

    -   <span data-ttu-id="d845a-132">Glassdoor</span><span class="sxs-lookup"><span data-stu-id="d845a-132">Glassdoor</span></span>

    -   <span data-ttu-id="d845a-133">Monster Jobs</span><span class="sxs-lookup"><span data-stu-id="d845a-133">Monster Jobs</span></span>

-   <span data-ttu-id="d845a-134">Magazyny i publikacje</span><span class="sxs-lookup"><span data-stu-id="d845a-134">Magazines & Publications</span></span>

-   <span data-ttu-id="d845a-135">Sieci społecznościowe</span><span class="sxs-lookup"><span data-stu-id="d845a-135">Social Network</span></span>

    -   <span data-ttu-id="d845a-136">Facebook</span><span class="sxs-lookup"><span data-stu-id="d845a-136">Facebook</span></span>

    -   <span data-ttu-id="d845a-137">Twitter</span><span class="sxs-lookup"><span data-stu-id="d845a-137">Twitter</span></span>

-   <span data-ttu-id="d845a-138">Rekrutacja na uniwersytetach</span><span class="sxs-lookup"><span data-stu-id="d845a-138">University Recruiting</span></span>

-   <span data-ttu-id="d845a-139">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="d845a-139">LinkedIn</span></span>

-   <span data-ttu-id="d845a-140">Zastrzeżone</span><span class="sxs-lookup"><span data-stu-id="d845a-140">Classifieds</span></span>

-   <span data-ttu-id="d845a-141">Polecenie</span><span class="sxs-lookup"><span data-stu-id="d845a-141">Referral</span></span>

-   <span data-ttu-id="d845a-142">Dodany przez osobę rekrutującą</span><span class="sxs-lookup"><span data-stu-id="d845a-142">Added by Recruiter</span></span>

-   <span data-ttu-id="d845a-143">Inna</span><span class="sxs-lookup"><span data-stu-id="d845a-143">Other</span></span>

## <a name="customize-the-source-list"></a><span data-ttu-id="d845a-144">Dostosowywanie listy źródłowej</span><span class="sxs-lookup"><span data-stu-id="d845a-144">Customize the source list</span></span> 

<span data-ttu-id="d845a-145">Można rozszerzyć listy źródłowe, aby uwzględnić dodatkowe źródła aplikacji.</span><span class="sxs-lookup"><span data-stu-id="d845a-145">You can extend the source list to include additional application sources.</span></span> <span data-ttu-id="d845a-146">Aby dostosować tę listę, postępuj zgodnie z instrukcjami w [Rozszerzanie zestawów opcji w Attract](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/extensibility-attract#extending-option-sets-in-attract).</span><span class="sxs-lookup"><span data-stu-id="d845a-146">To customize this list, follow the instructions in [Extending Option Sets in Attract](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/extensibility-attract#extending-option-sets-in-attract).</span></span> <span data-ttu-id="d845a-147">Edytuj jednostkę **źródła talentu**, aby uwzględnić dodatkowe źródła.</span><span class="sxs-lookup"><span data-stu-id="d845a-147">Edit the **TalentSource** entity to include additional sources.</span></span> 

<span data-ttu-id="d845a-148">Aby uniknąć negatywnych skutków w interfejsie użytkownika, nie edytuj i nie usuwaj wartości wyliczanych atrybutu **kategoria talentu** (nie nazw) dla następujących pozycji:</span><span class="sxs-lookup"><span data-stu-id="d845a-148">To avoid negatively impacting the user interface (UI), don't edit or delete the **TalentCategory** enum values (not names) for the following:</span></span>

- <span data-ttu-id="d845a-149">**Polecenie**</span><span class="sxs-lookup"><span data-stu-id="d845a-149">**Referral**</span></span>
- <span data-ttu-id="d845a-150">**LinkedIn**</span><span class="sxs-lookup"><span data-stu-id="d845a-150">**LinkedIn**</span></span>
- <span data-ttu-id="d845a-151">**Inna**</span><span class="sxs-lookup"><span data-stu-id="d845a-151">**Other**</span></span>

<span data-ttu-id="d845a-152">Zamiast tego można rozszerzyć wyliczenia **źródła talentu**, aby dodać inne typy źródeł.</span><span class="sxs-lookup"><span data-stu-id="d845a-152">Instead, you can extend the **TalentSource** enum to add other types of sources.</span></span>
