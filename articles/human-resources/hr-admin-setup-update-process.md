---
title: Aktualizowanie procesu
description: Microsoft Dynamics 365 Human Resources to rozwiązanie typu oprogramowanie jako usługa (SaaS), które zapewnia ciągłe aktualizacje dla zmian w aplikacji i platformie.
author: andreabichsel
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-27
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2466c53885340991aeeb0a07af83517473b332b6
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053642"
---
# <a name="update-process"></a><span data-ttu-id="38904-103">Aktualizowanie procesu</span><span class="sxs-lookup"><span data-stu-id="38904-103">Update process</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="38904-104">Microsoft Dynamics 365 Human Resources to rozwiązanie typu oprogramowanie jako usługa (SaaS), które zapewnia ciągłe aktualizacje usług bez interwencji użytkownika.</span><span class="sxs-lookup"><span data-stu-id="38904-104">Microsoft Dynamics 365 Human Resources is a true software as a service (SaaS) that provides continuous, touchless service updates.</span></span> <span data-ttu-id="38904-105">Te aktualizacje zawierają modyfikacje aplikacji i platformy, które często wprowadzają krytyczne udoskonalenia usługi, w tym aktualizacje wymagane przepisami prawa.</span><span class="sxs-lookup"><span data-stu-id="38904-105">These updates contain both application and platform changes that often provide critical improvements to the service, including regulatory updates.</span></span>

## <a name="update-policy"></a><span data-ttu-id="38904-106">Zasady aktualizacji</span><span class="sxs-lookup"><span data-stu-id="38904-106">Update policy</span></span>

<span data-ttu-id="38904-107">Aktualizacje są publikowane regularnie dla wszystkich środowisk.</span><span class="sxs-lookup"><span data-stu-id="38904-107">Updates are released on a regular cadence to all environments.</span></span> <span data-ttu-id="38904-108">Program Human Resources jest wspierany zgodnie z [zasadami cyklu życia pomocy technicznej Microsoft](https://support.microsoft.com/hub/4095338/microsoft-lifecycle-policy), które określają spójny i przewidywalny harmonogram dostępności wsparcia technicznego.</span><span class="sxs-lookup"><span data-stu-id="38904-108">Human Resources is supported according to the [Microsoft Lifecycle policy](https://support.microsoft.com/hub/4095338/microsoft-lifecycle-policy), which provides consistent and predictable guidelines for the availability of support.</span></span>

## <a name="release-cadence"></a><span data-ttu-id="38904-109">Częstotliwość wydań</span><span class="sxs-lookup"><span data-stu-id="38904-109">Release cadence</span></span> 

<span data-ttu-id="38904-110">Aktualizacje modułu Human Resources są stosowane do wszystkich środowisk automatycznie.</span><span class="sxs-lookup"><span data-stu-id="38904-110">Human Resources updates are applied to all environments automatically.</span></span> <span data-ttu-id="38904-111">Dla modułu Human Resources są publikowane dwa typy wydań:</span><span class="sxs-lookup"><span data-stu-id="38904-111">Human Resources provides two types of releases:</span></span>

- <span data-ttu-id="38904-112">**Aktualizacje usług**: Aktualizacje pojawiają się co dwa tygodnie, zawierają poprawki błędów i nowe funkcje.</span><span class="sxs-lookup"><span data-stu-id="38904-112">**Service updates**: Updates occur every two weeks that include bug fixes and new features.</span></span> <span data-ttu-id="38904-113">Aktualizacje usług obejmują także odpowiednie aktualizacje platformy, kiedy są one publikowane.</span><span class="sxs-lookup"><span data-stu-id="38904-113">Service updates also include applicable Platform updates when they release.</span></span> <span data-ttu-id="38904-114">Aby zapoznać się z orientacyjnym harmonogramem publikowania aktualizacji platformy, zobacz [Tabela 3: Wydania platformy](../fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy.md#table-3-platform-releases).</span><span class="sxs-lookup"><span data-stu-id="38904-114">To get an idea of when Platform updates are released, see [Table 3: Platform releases](../fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy.md#table-3-platform-releases).</span></span> <span data-ttu-id="38904-115">Aktualizacje co dwa tygodnie zawierają wdrożenia globalne w różnych regionach.</span><span class="sxs-lookup"><span data-stu-id="38904-115">Biweekly updates have a staged global rollout across regions.</span></span> <span data-ttu-id="38904-116">Aby uzyskać więcej informacji o aktualizacjach co dwa tygodnie, zobacz [Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources](hr-admin-whats-new.md).</span><span class="sxs-lookup"><span data-stu-id="38904-116">For more information about biweekly updates, see [What's new or changed in Dynamics 365 Human Resources](hr-admin-whats-new.md).</span></span>

    <span data-ttu-id="38904-117">Wszystkie obsługiwane centra danych są aktualizowane co dwa tygodnie, o ile nie zaznaczono inaczej.</span><span class="sxs-lookup"><span data-stu-id="38904-117">All supported data centers update every two weeks, unless otherwise noted.</span></span> <span data-ttu-id="38904-118">Stany Zjednoczone, Australia, Europa, Wielka Brytania, Azja i Kanada są objęte aktualizacjami co dwa tygodnie.</span><span class="sxs-lookup"><span data-stu-id="38904-118">US, Australia, Europe, UK, Asia, and Canada regions are included in biweekly updates.</span></span> 

- <span data-ttu-id="38904-119">**Aktualizacje rozwiązania Dataverse**: te aktualizacje odbywają się w przybliżeniu co sześć tygodni, jeśli jest to konieczne.</span><span class="sxs-lookup"><span data-stu-id="38904-119">**Dataverse solution updates**: These updates occur approximately every six weeks, as needed.</span></span> <span data-ttu-id="38904-120">Obejmują nowe jednostki i zmiany istniejących jednostek w usłudze Dataverse.</span><span class="sxs-lookup"><span data-stu-id="38904-120">They include new entities and changes to existing entities in Dataverse.</span></span> <span data-ttu-id="38904-121">Te aktualizacje są publikowane w tych samych regionach, jak aktualizacje co dwa tygodnie, a ich zreplikowanie do wszystkich centrów danych może potrwać do sześciu tygodni.</span><span class="sxs-lookup"><span data-stu-id="38904-121">These updates release to the same regions as the biweekly updates, and they take about six weeks to replicate through all data centers.</span></span> <span data-ttu-id="38904-122">Aktualizacje rozwiązania mogą być zbieżne z aktualizacjami usług co dwa tygodnie, ale nie muszą.</span><span class="sxs-lookup"><span data-stu-id="38904-122">Solution updates may or may not align with biweekly service updates.</span></span>

> [!NOTE]
> <span data-ttu-id="38904-123">Aktualizacje rozwiązania są dostępne we wszystkich centrach danych po opublikowaniu.</span><span class="sxs-lookup"><span data-stu-id="38904-123">Solution updates are available on all data centers once they're released.</span></span> <span data-ttu-id="38904-124">Jeśli nie chcesz czekać na automatyczne zreplikowanie aktualizacji, możesz ręcznie zastosować te aktualizacje w dowolnym środowisku w dowolnym centrum danych.</span><span class="sxs-lookup"><span data-stu-id="38904-124">If you don't want to wait for the updates to replicate automatically, you can manually apply these updates on any environment in any data center.</span></span>

<span data-ttu-id="38904-125">W razie potrzeby dla modułu Human Resources są również dostarczane następujące typy rozwiązań błędów:</span><span class="sxs-lookup"><span data-stu-id="38904-125">When needed, Human Resources also provides the following types of fixes:</span></span>

- <span data-ttu-id="38904-126">**Poprawka**: poprawki błędów, które mogą towarzyszyć wydaniom aktualizacji usług co dwa tygodnie albo być publikowane niezależnie</span><span class="sxs-lookup"><span data-stu-id="38904-126">**Revision (hotfix)**: Bug fixes that can occur either with or apart from a biweekly service update release</span></span>

- <span data-ttu-id="38904-127">**Poprawka awaryjna**: Proaktywne i reaktywne poprawki, które co do zasady są autonomiczne, mogą zawierać modyfikacje konfiguracji lub kodu źródłowego w celu rozwiązania istniejących problemów w ośrodku oraz mogą występować poza aktualizacjami wersji usług co dwa tygodnie</span><span class="sxs-lookup"><span data-stu-id="38904-127">**Emergency fix**: Proactive and reactive hotfixes that are standalone in nature, can include configuration-only or code changes to resolve live site issues, and can occur apart from a biweekly service update release</span></span>

<span data-ttu-id="38904-128">Wersje są przeglądane, testowane i weryfikowane w środowisku wewnętrznym.</span><span class="sxs-lookup"><span data-stu-id="38904-128">Releases are reviewed, tested, and validated on an internal environment.</span></span> <span data-ttu-id="38904-129">Zaakceptowane kompilacje są wdrażane w środowisku produkcyjnym.</span><span class="sxs-lookup"><span data-stu-id="38904-129">After builds are signed off, they're then deployed to production.</span></span>

## <a name="release-cadence-exceptions-in-2021"></a><span data-ttu-id="38904-130">Częstotliwośc wydawania wyjątków w wersji 2021</span><span class="sxs-lookup"><span data-stu-id="38904-130">Release cadence exceptions in 2021</span></span>

<span data-ttu-id="38904-131">Aby uwzględnić dni wolne, harmonogram wydawanych aktualizacji dla listopada i grudnia 2021 roku jest następujący:</span><span class="sxs-lookup"><span data-stu-id="38904-131">To account for holidays, the release schedule for November and December 2021 is as follows:</span></span>

- <span data-ttu-id="38904-132">Wersja listopadowa: 1 listopada – 14 listopada</span><span class="sxs-lookup"><span data-stu-id="38904-132">November release: November 1 - November 14</span></span>
- <span data-ttu-id="38904-133">Wersja grudniowa: 29 listopada – 12 grudnia</span><span class="sxs-lookup"><span data-stu-id="38904-133">December release: November 29 - December 12</span></span>
 
<span data-ttu-id="38904-134">Dwutygodniowe odstępy pomiędzy wersjami zaczną zwnou obowiązywać od 10 stycznia 2022 roku.</span><span class="sxs-lookup"><span data-stu-id="38904-134">The two-week release cadence will resume as usual on January 10, 2022.</span></span>

## <a name="communications"></a><span data-ttu-id="38904-135">Komunikacja</span><span class="sxs-lookup"><span data-stu-id="38904-135">Communications</span></span>

<span data-ttu-id="38904-136">W lokalizacjach wymienionych poniżej można dowiedzieć się, co szykujemy w module Human Resources i jakie aktualizacje dotychczas opublikowano:</span><span class="sxs-lookup"><span data-stu-id="38904-136">You can find out what's in the works for Human Resources and what we've released in the following locations:</span></span>

- [<span data-ttu-id="38904-137">Plan rozwoju rozwiązania Dynamics 365 Human Resources</span><span class="sxs-lookup"><span data-stu-id="38904-137">Dynamics 365 Human Resources roadmap</span></span>](https://dynamics.microsoft.com/roadmap/human-resources/)

- [<span data-ttu-id="38904-138">Plany wydań Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="38904-138">Dynamics 365 Release Plans</span></span>](/dynamics365/release-plans/)

- [<span data-ttu-id="38904-139">Nowości i zmiany w Dynamics 365 Human Resources</span><span class="sxs-lookup"><span data-stu-id="38904-139">What's new or changed in Dynamics 365 Human Resources</span></span>](hr-admin-whats-new.md)

- <span data-ttu-id="38904-140">[Wyszukiwanie problemów w usługach Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/issue-search-lcs.md) (tylko błędy platformy)</span><span class="sxs-lookup"><span data-stu-id="38904-140">[Issue search in Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/issue-search-lcs.md) (for Platform-related bugs only)</span></span>

- [<span data-ttu-id="38904-141">Blog o rozwiązaniu Human Resources</span><span class="sxs-lookup"><span data-stu-id="38904-141">Human Resources blog</span></span>](https://community.dynamics.com/365/talent/b/dynamics365fortalent)

- [<span data-ttu-id="38904-142">Społeczność użytkowników rozwiązania Human Resources w serwisie Yammer</span><span class="sxs-lookup"><span data-stu-id="38904-142">Human Resources Yammer community</span></span>](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=10542230)

## <a name="preview-features-in-a-sandbox-environment"></a><span data-ttu-id="38904-143">Funkcje w wersji zapoznawczej w środowisku piaskownicy</span><span class="sxs-lookup"><span data-stu-id="38904-143">Preview features in a sandbox environment</span></span>

<span data-ttu-id="38904-144">Funkcje w wersji zapoznawczej można weryfikować w środowisku piaskownicy przed ich włączeniem w środowisku produkcyjnym.</span><span class="sxs-lookup"><span data-stu-id="38904-144">You can validate preview features in a sandbox environment before enabling them in your production environment.</span></span> <span data-ttu-id="38904-145">Aby uzyskać więcej informacji o włączaniu funkcji, zobacz [Zarządzanie funkcjami — omówienie](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="38904-145">For more information about enabling features, see [Feature management overview](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>

<span data-ttu-id="38904-146">Wszystkie nowe funkcje pozostają w podglądzie przez co najmniej 30 dni, a zazwyczaj 30-60 dni.</span><span class="sxs-lookup"><span data-stu-id="38904-146">All new features remain in preview for at least 30 days, and typically 30-60 days.</span></span> <span data-ttu-id="38904-147">Najważniejsze funkcje są zazwyczaj dostępne w październiku i kwietniu każdego roku po okresie podglądu.</span><span class="sxs-lookup"><span data-stu-id="38904-147">Major features are generally available in October and April of each year following the preview period.</span></span> <span data-ttu-id="38904-148">Po wyświetleniu nowych możliwości w obszarze roboczym zarządzanie funkcjami można je włączyć.</span><span class="sxs-lookup"><span data-stu-id="38904-148">As soon as you see new capabilities in the Feature management workspace, you can turn them on.</span></span> <span data-ttu-id="38904-149">Niektóre funkcje mogą być domyślnie włączone.</span><span class="sxs-lookup"><span data-stu-id="38904-149">Some features may be on by default.</span></span>

<span data-ttu-id="38904-150">Czasami funkcja jest domyślnie włączona i nie można jej wyłączyć (na przykład w obszarze roboczym zarządzanie funkcjami).</span><span class="sxs-lookup"><span data-stu-id="38904-150">At times, an integral feature will be on by default and can't be turned off (for example, the Feature management workspace).</span></span>

<span data-ttu-id="38904-151">Gdy funkcja jest ogólnie dostępna, może być włączana lub wyłączana w środowiskach produkcyjnych.</span><span class="sxs-lookup"><span data-stu-id="38904-151">Once a feature is generally available, it may be turned on or off in production environments.</span></span> <span data-ttu-id="38904-152">Przestrzeń robocza Zarządzanie funkcjami wskazuje, kiedy funkcja podglądu stanie się obowiązkowa.</span><span class="sxs-lookup"><span data-stu-id="38904-152">The Feature management workspace indicates when a preview feature will become mandatory.</span></span> <span data-ttu-id="38904-153">Ta data zazwyczaj jest równa 1 października lub 1 kwietnia w celu dostosowania ich do półrocznych planów zwolnień.</span><span class="sxs-lookup"><span data-stu-id="38904-153">This date is usually on October 1 or April 1 to align with the semiannual release plans.</span></span> <span data-ttu-id="38904-154">Nie można wyłączać obowiązkowych funkcji.</span><span class="sxs-lookup"><span data-stu-id="38904-154">You can't turn off mandatory features.</span></span> <span data-ttu-id="38904-155">Dopóki ta funkcja nie stanie się obowiązkowa, można ją włączać i wyłączać we wszystkich środowiskach.</span><span class="sxs-lookup"><span data-stu-id="38904-155">Until it becomes mandatory, you can turn a feature on and off in all environments.</span></span>

<span data-ttu-id="38904-156">Zdecydowanie zalecamy sprawdzenie działania funkcji w wersji zapoznawczej w środowisku piaskownicy lub w próbnym.</span><span class="sxs-lookup"><span data-stu-id="38904-156">We highly recommend previewing features in a sandbox or trial environment.</span></span> <span data-ttu-id="38904-157">Najlepiej utworzyć kopię bieżącego środowiska produkcyjnego lub bazy danych w środowisku piaskownicy, co pozwoli kompleksowo sprawdzić działanie nowych funkcji z danymi firmy.</span><span class="sxs-lookup"><span data-stu-id="38904-157">It's best to create a copy of your current production environment or database into a sandbox environment so you can get the complete experience of the new features with your data.</span></span>

<span data-ttu-id="38904-158">Aby uzyskać więcej informacji na temat inicjowania obsługi środowiska piaskownicy, zobacz [Inicjowanie obsługi administracyjnej projektu programu Human Resources](hr-admin-setup-provision.md).</span><span class="sxs-lookup"><span data-stu-id="38904-158">For more information about provisioning a sandbox environment, see [Provision a Human Resources project](hr-admin-setup-provision.md).</span></span> <span data-ttu-id="38904-159">Aby usunąć środowisko testowe, zobacz [Usuwanie wystąpienia](hr-admin-setup-remove-instance.md#remove-a-test-drive-environment).</span><span class="sxs-lookup"><span data-stu-id="38904-159">To remove a test environment, see [Remove an instance](hr-admin-setup-remove-instance.md#remove-a-test-drive-environment).</span></span> 

## <a name="report-bugs"></a><span data-ttu-id="38904-160">Zgłaszanie usterek</span><span class="sxs-lookup"><span data-stu-id="38904-160">Report bugs</span></span>

<span data-ttu-id="38904-161">Podczas testowania funkcji w wersji zapoznawczej lub sprawdzania nowych możliwości oprogramowania można znaleźć elementy, które nie działają zgodnie z oczekiwaniami.</span><span class="sxs-lookup"><span data-stu-id="38904-161">While testing preview features or trying new capabilities, you might find items that don't work as expected.</span></span> <span data-ttu-id="38904-162">Wszelkie usterki prosimy zgłaszać do [działu pomocy technicznej systemu Microsoft Dynamics 365](https://dynamics.microsoft.com/support/).</span><span class="sxs-lookup"><span data-stu-id="38904-162">Please report any bugs through [Microsoft Dynamics 365 support](https://dynamics.microsoft.com/support/).</span></span>

## <a name="see-also"></a><span data-ttu-id="38904-163">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="38904-163">See also</span></span>

[<span data-ttu-id="38904-164">Plany wydań rozwiązań Dynamics 365 i Power Platform</span><span class="sxs-lookup"><span data-stu-id="38904-164">Dynamics 365 and Power Platform Release Plans</span></span>](/dynamics365/release-plans)</br>
[<span data-ttu-id="38904-165">Nowości i zmiany w module Dynamics 365 Human Resources</span><span class="sxs-lookup"><span data-stu-id="38904-165">What's new or changed in Dynamics 365 Human Resource</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="38904-166">Zasady dotyczące cyklu życia oprogramowania</span><span class="sxs-lookup"><span data-stu-id="38904-166">Software lifecycle policy</span></span>](../fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]