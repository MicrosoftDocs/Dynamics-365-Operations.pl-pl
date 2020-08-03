---
title: Omówienie zarządzania świadczeniami
description: Omówienie funkcji Zarządzanie świadczeniami w Dynamics 365 Human Resources. Zaoferuj pracownikom rozszerzone opcje zarządzania świadczeniami w przyjaznym internetowym środowisku.
author: andreabichsel
manager: AnnBe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1043fb18c33e5ec0cde13008b168fd317c7c7be6
ms.sourcegitcommit: 9dc5c7dd5877cc6e7cd0059d173bcd8052ba13bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/16/2020
ms.locfileid: "3599387"
---
# <a name="benefits-management-overview"></a><span data-ttu-id="5d232-104">Omówienie obszaru roboczego Zarządzanie świadczeniami</span><span class="sxs-lookup"><span data-stu-id="5d232-104">Benefits management overview</span></span>

<span data-ttu-id="5d232-105">Aby zachować konkurencyjność, należy oferować bogaty zestaw świadczeń, który pomoże przyciągnąć i utrzymać najlepszych pracowników.</span><span class="sxs-lookup"><span data-stu-id="5d232-105">To remain competitive, you must offer a rich set of benefits to attract and retain your best employees.</span></span> <span data-ttu-id="5d232-106">Oprócz standardowych świadczeń, takich jak opieka medyczna i dentystyczna, można również zaoferować rozszerzone usługi, takie jak pomoc we wdrożeniu do pracy, programy rekreacyjne i dodatki na odzież roboczą.</span><span class="sxs-lookup"><span data-stu-id="5d232-106">In addition to standard benefits like medical and dental coverage, you might also want to offer expanded services like adoption assistance, recreation programs, and clothing allowances.</span></span> <span data-ttu-id="5d232-107">Funkcja Zarządzanie świadczeniami dostępna w Microsoft Dynamics 365 Human Resources stanowi elastyczne rozwiązanie, które obsługuje wiele różnych opcji świadczeń.</span><span class="sxs-lookup"><span data-stu-id="5d232-107">Benefits management in Microsoft Dynamics 365 Human Resources provides you with a flexible solution that supports a wide variety of benefit options.</span></span> <span data-ttu-id="5d232-108">Moduł Human Resources zawiera również przyjazne środowisko obsługi pracownika, które eksponuje oferty pracodawcy.</span><span class="sxs-lookup"><span data-stu-id="5d232-108">Human Resources also includes an easy-to-use employee experience that showcases your offerings.</span></span>

- <span data-ttu-id="5d232-109">Rozszerzona funkcjonalność planów świadczeń umożliwia tworzenie unikatowych planów świadczeń i zarządzanie nimi oraz obsługę skomplikowanych tabel stawek i zagnieżdżonych warstw.</span><span class="sxs-lookup"><span data-stu-id="5d232-109">Enhanced benefits plans let you create and manage unique benefit plans and support complex benefit rate tables and nested tiers.</span></span> <span data-ttu-id="5d232-110">Istnieje możliwość łatwego tworzenia programów świadczeń, pakietów i reguł automatycznego rejestrowania, aby ułatwić pracownikom obsługę.</span><span class="sxs-lookup"><span data-stu-id="5d232-110">You can easily create benefit programs, bundles, and auto-enrollment rules for an easier employee experience.</span></span>

- <span data-ttu-id="5d232-111">Programy kredytu elastycznego umożliwiają obliczanie proporcjonalne w celu uwzględnienia przejścia na emeryturę i innych zmian sytuacji życiowej.</span><span class="sxs-lookup"><span data-stu-id="5d232-111">Flex credit programs let you prorate to support retirement and other life events.</span></span>

- <span data-ttu-id="5d232-112">Rozbudowane reguły uprawnień pomagają udostępniać odpowiednie świadczenia odpowiednim pracownikom.</span><span class="sxs-lookup"><span data-stu-id="5d232-112">Extensive eligibility rules ensure you make the right benefits available to the right employees.</span></span>

- <span data-ttu-id="5d232-113">Internetowa rejestracja na świadczenia ułatwia pracownikom korzystanie z systemu.</span><span class="sxs-lookup"><span data-stu-id="5d232-113">Online benefits enrollment provides an easy experience for your employees.</span></span>

- <span data-ttu-id="5d232-114">Przetwarzanie kwalifikowanych zdarzeń życiowych obsługuje przyszłe zdarzenia życiowe.</span><span class="sxs-lookup"><span data-stu-id="5d232-114">Qualified life event processing supports future life events.</span></span>

<span data-ttu-id="5d232-115">Jeśli chcesz przejść do danych demonstracyjnych, musisz ponownie wdrożyć środowisko piaskownicy.</span><span class="sxs-lookup"><span data-stu-id="5d232-115">If you would like to access the demo data, you'll need to redeploy your sandbox environment.</span></span>

## <a name="benefits-management-known-issues"></a><span data-ttu-id="5d232-116">Znane problemy związane z zarządzaniem korzyściami</span><span class="sxs-lookup"><span data-stu-id="5d232-116">Benefits management known issues</span></span>

### <a name="flex-credit-programs"></a><span data-ttu-id="5d232-117">Programy kredytów elastycznych</span><span class="sxs-lookup"><span data-stu-id="5d232-117">Flex credit programs</span></span>

<span data-ttu-id="5d232-118">Łączna wartość kredytu zdefiniowana dla programu kredytu elastycznego nie jest wyświetlana w formularzu **Plany świadczeń pracowniczych**.</span><span class="sxs-lookup"><span data-stu-id="5d232-118">The total credit value defined for a flex credit program doesn't display in the **Worker benefit plans** form.</span></span> <span data-ttu-id="5d232-119">Ponadto, jeśli ustawisz program elastycznych kredytów w celu uwzględnienia reguły **Brak**, podczas wybierania i zatwierdzania planów pojawi się komunikat o błędzie w formularzu **Plan świadczeń pracowniczych**.</span><span class="sxs-lookup"><span data-stu-id="5d232-119">Also, if you set a flex credit program to have a proration rule of **None**, you get an error in the **Worker benefit plan** form when selecting and confirming plans.</span></span>

## <a name="enable-benefits-management"></a><span data-ttu-id="5d232-120">Włączanie obszaru roboczego Zarządzanie świadczeniami</span><span class="sxs-lookup"><span data-stu-id="5d232-120">Enable Benefits management</span></span>

<span data-ttu-id="5d232-121">Ten artykuł opisuje sposób włączania funkcji w wersji zapoznawczej w module Human Resources.</span><span class="sxs-lookup"><span data-stu-id="5d232-121">This article describes how to turn on features in Human Resources.</span></span> <span data-ttu-id="5d232-122">Informuje również, które z istniejących funkcji w module Human Resources są zastępowane lub wyłączane przez obszar roboczy Zarządzanie świadczeniami po jego włączeniu.</span><span class="sxs-lookup"><span data-stu-id="5d232-122">It also tells which existing features in Human Resources that Benefits management replaces or are disabled once you turn on Benefits management.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5d232-123">Po włączeniu Zarządzania świadczeniami w środowisku **Produkcyjnym** nie można go wyłączyć.</span><span class="sxs-lookup"><span data-stu-id="5d232-123">After you enable Benefits management in a **Production** environment, you can't disable it.</span></span> <span data-ttu-id="5d232-124">Zaleca się włączanie i testowanie Zarządzania świadczeniami w środowisku **Piaskownicy** przed włączeniem go w środowisku **Produkcyjnym**.</span><span class="sxs-lookup"><span data-stu-id="5d232-124">We recommend enabling and testing Benefits management in a **Sandbox** environment before enabling it in a **Production** environment.</span></span> <span data-ttu-id="5d232-125">Istnieją znaczne różnice między funkcjami starszego świadczenia i nowymi funkcjami zarządzania świadczeniami, które wymagają dodatkowej konfiguracji i powinny być testowane przed wprowadzeniem do produkcji.</span><span class="sxs-lookup"><span data-stu-id="5d232-125">There are significant differences between the legacy Benefit functionality and new Benefits management functionality that require additional setup and should be tested prior to being placed into production.</span></span>

- [<span data-ttu-id="5d232-126">Zarządzanie funkcjami</span><span class="sxs-lookup"><span data-stu-id="5d232-126">Manage features</span></span>](hr-admin-manage-features.md)

## <a name="configure-employee-information"></a><span data-ttu-id="5d232-127">Skonfiguruj informacje dotyczące pracowników</span><span class="sxs-lookup"><span data-stu-id="5d232-127">Configure employee information</span></span>

<span data-ttu-id="5d232-128">Aby można było zarejestrować pracowników w ramach świadczeń, musisz podać wymagane informacje.</span><span class="sxs-lookup"><span data-stu-id="5d232-128">Before you can enroll employees in benefits, you must provide required information.</span></span> <span data-ttu-id="5d232-129">Należy zarejestrować pracownika w **Planie stałych wynagrodzeń** według daty rozpoczęcia, a następnie wybrać opcję **Częstotliwość wypłat świadczenia** w **Szczegóły zatrudnienia** w formularzu **Pracownik**.</span><span class="sxs-lookup"><span data-stu-id="5d232-129">You must enroll an employee in a **Fixed compensation plan** on their start date, and you must select a **Benefit pay frequency** in **Employment details** on the **Worker** form.</span></span>

<span data-ttu-id="5d232-130">Jeśli użytkownik ma pracownika, który otrzymuje dodatkowe wynagrodzenie, na przykład prowizje, może dodać kwotę **Świadczenia do wynagrodzenia rocznego** z rekordu pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="5d232-130">If you have an employee who receives supplemental compensation like commissions, you can add a **Benefits annual salary** amount from the employee record.</span></span> <span data-ttu-id="5d232-131">Przy ustalaniu kwot pokrycia w Human Resources zamiast kwoty rocznej dla stałej płacy będzie używana kwota **Świadczenia do wynagrodzenia rocznego**.</span><span class="sxs-lookup"><span data-stu-id="5d232-131">Human Resources will use the **Benefits annual salary** amount when determining coverage amounts, instead of the fixed compensation annual amount.</span></span> <span data-ttu-id="5d232-132">**Świadczenia do wynagrodzenia rocznego** musi być ważne na dzień rozpoczęcia lub początek okresu świadczenia, w zależności od tego, która z nich jest najpóźniejsza.</span><span class="sxs-lookup"><span data-stu-id="5d232-132">The **Benefits annual salary** must be valid as of the employee’s start date or the beginning of the benefit period, whichever is latest.</span></span> <span data-ttu-id="5d232-133">Jeżeli dla pracownika zostanie odnotowane zarówno stałe wynagrodzenie, jak i kwota rocznego wynagrodzenia za świadczenia, przy określaniu kwot pokrycia będzie się uwzględniać roczne wynagrodzenie za świadczenia.</span><span class="sxs-lookup"><span data-stu-id="5d232-133">If both a fixed compensation and benefits annual salary amount is recorded for an employee, the benefits annual salary will be used in determining coverage amounts.</span></span>

<span data-ttu-id="5d232-134">Podczas tworzenia planu świadczeń, w którym używane są stawki oparte na płci lub wieku, należy wprowadzić datę urodzenia i płeć dla pracownika, aby obliczyć koszty świadczeń.</span><span class="sxs-lookup"><span data-stu-id="5d232-134">When you create a benefit plan that uses rates that are based on gender or age, you must enter a birth date and gender for the employee to calculate the benefit cost.</span></span>

## <a name="configure-benefits-management"></a><span data-ttu-id="5d232-135">Konfigurowanie zarządzania świadczeniami</span><span class="sxs-lookup"><span data-stu-id="5d232-135">Configure Benefits management</span></span>

<span data-ttu-id="5d232-136">Zanim będzie można tworzyć plany świadczeń dla pracowników, należy skonfigurować opcje dla planów.</span><span class="sxs-lookup"><span data-stu-id="5d232-136">Before you can create benefit plans for your employees, you need to configure options for the plans.</span></span>

- [<span data-ttu-id="5d232-137">Ustawianie parametrów obszaru roboczego Zarządzanie świadczeniami</span><span class="sxs-lookup"><span data-stu-id="5d232-137">Set Benefits management parameters</span></span>](hr-benefits-setup-parameters.md)
- [<span data-ttu-id="5d232-138">Konfigurowanie reguł i opcji uprawnień</span><span class="sxs-lookup"><span data-stu-id="5d232-138">Configure eligibility rules and options</span></span>](hr-benefits-setup-eligibility-rules.md)
- [<span data-ttu-id="5d232-139">Konfigurowanie opcji uprawnień do kontaktu osobistego</span><span class="sxs-lookup"><span data-stu-id="5d232-139">Configure personal contact eligibility options</span></span>](hr-benefits-setup-contact-eligibility-options.md)
- [<span data-ttu-id="5d232-140">Tworzenie opcji zapotrzebowania</span><span class="sxs-lookup"><span data-stu-id="5d232-140">Create coverage options</span></span>](hr-benefits-setup-coverage-options.md)
- [<span data-ttu-id="5d232-141">Konfigurowanie częstotliwości płatności</span><span class="sxs-lookup"><span data-stu-id="5d232-141">Set up payment frequencies</span></span>](hr-benefits-setup-payment-frequencies.md)
- [<span data-ttu-id="5d232-142">Konfigurowanie typów zdarzeń zmiany sytuacji życiowej</span><span class="sxs-lookup"><span data-stu-id="5d232-142">Configure life event types</span></span>](hr-benefits-setup-life-event-types.md)
- [<span data-ttu-id="5d232-143">Tworzenie typów planu</span><span class="sxs-lookup"><span data-stu-id="5d232-143">Create plan types</span></span>](hr-benefits-setup-plan-types.md)
- [<span data-ttu-id="5d232-144">Ustawianie kodów przyczyn</span><span class="sxs-lookup"><span data-stu-id="5d232-144">Set up reason codes</span></span>](hr-benefits-setup-reason-codes.md)
- [<span data-ttu-id="5d232-145">Ustawianie kodów warstw</span><span class="sxs-lookup"><span data-stu-id="5d232-145">Set up tier codes</span></span>](hr-benefits-setup-tier-codes.md)
- [<span data-ttu-id="5d232-146">Konfigurowanie stawek</span><span class="sxs-lookup"><span data-stu-id="5d232-146">Configure rates</span></span>](hr-benefits-setup-rates.md)
- [<span data-ttu-id="5d232-147">Konfigurowanie potrąceń</span><span class="sxs-lookup"><span data-stu-id="5d232-147">Configure deductions</span></span>](hr-benefits-setup-deductions.md)
- [<span data-ttu-id="5d232-148">Konfigurowanie dni oczekiwania</span><span class="sxs-lookup"><span data-stu-id="5d232-148">Configure waiting days</span></span>](hr-benefits-setup-waiting-days.md)
- [<span data-ttu-id="5d232-149">Konfigurowanie okresów oczekiwania</span><span class="sxs-lookup"><span data-stu-id="5d232-149">Configure waiting periods</span></span>](hr-benefits-setup-waiting-periods.md)
- [<span data-ttu-id="5d232-150">Ustawianie reguł zaokrąglania</span><span class="sxs-lookup"><span data-stu-id="5d232-150">Set up rounding rules</span></span>](hr-benefits-setup-rounding-rules.md)
- [<span data-ttu-id="5d232-151">Tworzenie historii zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="5d232-151">Create employment categories</span></span>](hr-benefits-setup-employment-categories.md)
- [<span data-ttu-id="5d232-152">Konfigurowanie typów zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="5d232-152">Set up employment types</span></span>](hr-benefits-setup-employment-types.md)
- [<span data-ttu-id="5d232-153">Konfigurowanie samoobsługi pracownika etatowego</span><span class="sxs-lookup"><span data-stu-id="5d232-153">Configure employee self service</span></span>](hr-benefits-setup-employee-self-service.md)

## <a name="create-benefit-plans"></a><span data-ttu-id="5d232-154">Tworzenie planów świadczeń</span><span class="sxs-lookup"><span data-stu-id="5d232-154">Create benefit plans</span></span>

<span data-ttu-id="5d232-155">W tych artykułach przedstawiono sposób tworzenia programów świadczeń, w tym pakietów i programów kredytu elastycznego.</span><span class="sxs-lookup"><span data-stu-id="5d232-155">These articles show how to create benefit plans, including bundles and flex credit programs.</span></span>

- [<span data-ttu-id="5d232-156">Konfigurowanie planów świadczeń</span><span class="sxs-lookup"><span data-stu-id="5d232-156">Set up benefit plans</span></span>](hr-benefits-plans-setup.md)
- [<span data-ttu-id="5d232-157">Konfigurowanie elastycznych programów kredytów</span><span class="sxs-lookup"><span data-stu-id="5d232-157">Set up flex credit programs</span></span>](hr-benefits-plans-flex-credit-programs.md)

## <a name="process-benefit-plans"></a><span data-ttu-id="5d232-158">Przetwarzanie planów świadczeń</span><span class="sxs-lookup"><span data-stu-id="5d232-158">Process benefit plans</span></span>

<span data-ttu-id="5d232-159">Niektóre zmiany trzeba przetworzyć, aby stały się aktywne.</span><span class="sxs-lookup"><span data-stu-id="5d232-159">You need to process some of your changes to make them active.</span></span>

- [<span data-ttu-id="5d232-160">Przetwórz uprawnienia do świadczeń</span><span class="sxs-lookup"><span data-stu-id="5d232-160">Process enrollment eligibility</span></span>](hr-benefits-process-enrollment-eligibility.md)
- [<span data-ttu-id="5d232-161">Przetwarzanie zmian sytuacji życiowej</span><span class="sxs-lookup"><span data-stu-id="5d232-161">Process life events</span></span>](hr-benefits-process-life-events.md)
- [<span data-ttu-id="5d232-162">Przetwarzanie wybranych zmian sytuacji życiowej</span><span class="sxs-lookup"><span data-stu-id="5d232-162">Process life event changes</span></span>](hr-benefits-process-life-event-changes.md)
- [<span data-ttu-id="5d232-163">Przetwórz uprawnienia do świadczeń z powodu zmiany sytuacji życiowej</span><span class="sxs-lookup"><span data-stu-id="5d232-163">Process life event eligibility</span></span>](hr-benefits-process-life-event-eligibility.md)
- [<span data-ttu-id="5d232-164">Przetwórz zmiany stawki</span><span class="sxs-lookup"><span data-stu-id="5d232-164">Process rate changes</span></span>](hr-benefits-process-rate-changes.md)

