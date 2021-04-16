---
title: Omówienie zarządzania świadczeniami
description: Omówienie funkcji Zarządzanie świadczeniami w Dynamics 365 Human Resources. Zaoferuj pracownikom rozszerzone opcje zarządzania świadczeniami w przyjaznym internetowym środowisku.
author: andreabichsel
ms.date: 09/17/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 34b0916e0bf618590bcc56a9a3bc7c61576361cc
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5805785"
---
# <a name="benefits-management-overview"></a><span data-ttu-id="fa7ea-104">Omówienie obszaru roboczego Zarządzanie świadczeniami</span><span class="sxs-lookup"><span data-stu-id="fa7ea-104">Benefits management overview</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="fa7ea-105">Aby zachować konkurencyjność, należy oferować bogaty zestaw świadczeń, który pomoże przyciągnąć i utrzymać najlepszych pracowników.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-105">To remain competitive, you must offer a rich set of benefits to attract and retain your best employees.</span></span> <span data-ttu-id="fa7ea-106">Oprócz standardowych świadczeń, takich jak opieka medyczna i dentystyczna, można również zaoferować rozszerzone usługi, takie jak pomoc we wdrożeniu do pracy, programy rekreacyjne i dodatki na odzież roboczą.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-106">In addition to standard benefits like medical and dental coverage, you might also want to offer expanded services like adoption assistance, recreation programs, and clothing allowances.</span></span> <span data-ttu-id="fa7ea-107">Funkcja Zarządzanie świadczeniami dostępna w Microsoft Dynamics 365 Human Resources stanowi elastyczne rozwiązanie, które obsługuje wiele różnych opcji świadczeń.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-107">Benefits management in Microsoft Dynamics 365 Human Resources provides you with a flexible solution that supports a wide variety of benefit options.</span></span> <span data-ttu-id="fa7ea-108">Moduł Human Resources zawiera również przyjazne środowisko obsługi pracownika, które eksponuje oferty pracodawcy.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-108">Human Resources also includes an easy-to-use employee experience that showcases your offerings.</span></span>

- <span data-ttu-id="fa7ea-109">Rozszerzona funkcjonalność planów świadczeń umożliwia tworzenie unikatowych planów świadczeń i zarządzanie nimi oraz obsługę skomplikowanych tabel stawek i zagnieżdżonych warstw.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-109">Enhanced benefits plans let you create and manage unique benefit plans and support complex benefit rate tables and nested tiers.</span></span> <span data-ttu-id="fa7ea-110">Istnieje możliwość łatwego tworzenia programów świadczeń, pakietów i reguł automatycznego rejestrowania, aby ułatwić pracownikom obsługę.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-110">You can easily create benefit programs, bundles, and auto-enrollment rules for an easier employee experience.</span></span>

- <span data-ttu-id="fa7ea-111">Programy kredytu elastycznego umożliwiają obliczanie proporcjonalne w celu uwzględnienia przejścia na emeryturę i innych zmian sytuacji życiowej.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-111">Flex credit programs let you prorate to support retirement and other life events.</span></span>

- <span data-ttu-id="fa7ea-112">Rozbudowane reguły uprawnień pomagają udostępniać odpowiednie świadczenia odpowiednim pracownikom.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-112">Extensive eligibility rules ensure you make the right benefits available to the right employees.</span></span>

- <span data-ttu-id="fa7ea-113">Internetowa rejestracja na świadczenia ułatwia pracownikom korzystanie z systemu.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-113">Online benefits enrollment provides an easy experience for your employees.</span></span>

- <span data-ttu-id="fa7ea-114">Przetwarzanie kwalifikowanych zdarzeń życiowych obsługuje przyszłe zdarzenia życiowe.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-114">Qualified life event processing supports future life events.</span></span>

<span data-ttu-id="fa7ea-115">Jeśli chcesz przejść do danych demonstracyjnych, musisz ponownie wdrożyć środowisko piaskownicy.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-115">If you would like to access the demo data, you'll need to redeploy your sandbox environment.</span></span>

## <a name="enable-benefits-management"></a><span data-ttu-id="fa7ea-116">Włączanie obszaru roboczego Zarządzanie świadczeniami</span><span class="sxs-lookup"><span data-stu-id="fa7ea-116">Enable Benefits management</span></span>

<span data-ttu-id="fa7ea-117">Ten temat opisuje sposób włączania funkcji w wersji zapoznawczej w module Human Resources.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-117">This topic describes how to turn on features in Human Resources.</span></span> <span data-ttu-id="fa7ea-118">Informuje również, które z istniejących funkcji w module Human Resources są zastępowane lub wyłączane przez obszar roboczy Zarządzanie świadczeniami po jego włączeniu.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-118">It also tells which existing features in Human Resources that Benefits management replaces or are disabled once you turn on Benefits management.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fa7ea-119">Po włączeniu Zarządzania świadczeniami w środowisku **Produkcyjnym** nie można go wyłączyć.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-119">After you enable Benefits management in a **Production** environment, you can't disable it.</span></span> <span data-ttu-id="fa7ea-120">Zaleca się włączanie i testowanie Zarządzania świadczeniami w środowisku **Piaskownicy** przed włączeniem go w środowisku **Produkcyjnym**.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-120">We recommend enabling and testing Benefits management in a **Sandbox** environment before enabling it in a **Production** environment.</span></span> <span data-ttu-id="fa7ea-121">Istnieją znaczne różnice między funkcjami starszego świadczenia i nowymi funkcjami zarządzania świadczeniami, które wymagają dodatkowej konfiguracji i powinny być testowane przed wprowadzeniem do produkcji.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-121">There are significant differences between the legacy Benefit functionality and new Benefits management functionality that require additional setup and should be tested prior to being placed into production.</span></span>

- [<span data-ttu-id="fa7ea-122">Zarządzanie funkcjami</span><span class="sxs-lookup"><span data-stu-id="fa7ea-122">Manage features</span></span>](hr-admin-manage-features.md)

## <a name="configure-employee-information"></a><span data-ttu-id="fa7ea-123">Skonfiguruj informacje dotyczące pracowników</span><span class="sxs-lookup"><span data-stu-id="fa7ea-123">Configure employee information</span></span>

<span data-ttu-id="fa7ea-124">Aby można było zarejestrować pracowników w ramach świadczeń, musisz podać wymagane informacje.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-124">Before you can enroll employees in benefits, you must provide required information.</span></span> <span data-ttu-id="fa7ea-125">Należy zarejestrować pracownika w **Planie stałych wynagrodzeń** według daty rozpoczęcia, a następnie wybrać opcję **Częstotliwość wypłat świadczenia** w **Szczegóły zatrudnienia** w formularzu **Pracownik**.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-125">You must enroll an employee in a **Fixed compensation plan** on their start date, and you must select a **Benefit pay frequency** in **Employment details** on the **Worker** form.</span></span>

<span data-ttu-id="fa7ea-126">Jeśli użytkownik ma pracownika, który otrzymuje dodatkowe wynagrodzenie, na przykład prowizje, może dodać kwotę **Świadczenia do wynagrodzenia rocznego** z rekordu pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-126">If you have an employee who receives supplemental compensation like commissions, you can add a **Benefits annual salary** amount from the employee record.</span></span> <span data-ttu-id="fa7ea-127">Przy ustalaniu kwot pokrycia w Human Resources zamiast kwoty rocznej dla stałej płacy będzie używana kwota **Świadczenia do wynagrodzenia rocznego**.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-127">Human Resources will use the **Benefits annual salary** amount when determining coverage amounts, instead of the fixed compensation annual amount.</span></span> <span data-ttu-id="fa7ea-128">**Świadczenia do wynagrodzenia rocznego** musi być ważne na dzień rozpoczęcia lub początek okresu świadczenia, w zależności od tego, która z nich jest najpóźniejsza.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-128">The **Benefits annual salary** must be valid as of the employee’s start date or the beginning of the benefit period, whichever is latest.</span></span> <span data-ttu-id="fa7ea-129">Jeżeli dla pracownika zostanie odnotowane zarówno stałe wynagrodzenie, jak i kwota rocznego wynagrodzenia za świadczenia, przy określaniu kwot pokrycia będzie się uwzględniać roczne wynagrodzenie za świadczenia.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-129">If both a fixed compensation and benefits annual salary amount is recorded for an employee, the benefits annual salary will be used in determining coverage amounts.</span></span>

<span data-ttu-id="fa7ea-130">Podczas tworzenia planu świadczeń, w którym używane są stawki oparte na płci lub wieku, należy wprowadzić datę urodzenia i płeć dla pracownika, aby obliczyć koszty świadczeń.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-130">When you create a benefit plan that uses rates that are based on gender or age, you must enter a birth date and gender for the employee to calculate the benefit cost.</span></span>

## <a name="configure-benefits-management"></a><span data-ttu-id="fa7ea-131">Konfigurowanie zarządzania świadczeniami</span><span class="sxs-lookup"><span data-stu-id="fa7ea-131">Configure Benefits management</span></span>

<span data-ttu-id="fa7ea-132">Zanim będzie można tworzyć plany świadczeń dla pracowników, należy skonfigurować opcje dla planów.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-132">Before you can create benefit plans for your employees, you need to configure options for the plans.</span></span>

- [<span data-ttu-id="fa7ea-133">Ustawianie parametrów obszaru roboczego Zarządzanie świadczeniami</span><span class="sxs-lookup"><span data-stu-id="fa7ea-133">Set Benefits management parameters</span></span>](hr-benefits-setup-parameters.md)
- [<span data-ttu-id="fa7ea-134">Konfigurowanie reguł i opcji uprawnień</span><span class="sxs-lookup"><span data-stu-id="fa7ea-134">Configure eligibility rules and options</span></span>](hr-benefits-setup-eligibility-rules.md)
- [<span data-ttu-id="fa7ea-135">Konfigurowanie opcji uprawnień do kontaktu osobistego</span><span class="sxs-lookup"><span data-stu-id="fa7ea-135">Configure personal contact eligibility options</span></span>](hr-benefits-setup-contact-eligibility-options.md)
- [<span data-ttu-id="fa7ea-136">Tworzenie opcji zapotrzebowania</span><span class="sxs-lookup"><span data-stu-id="fa7ea-136">Create coverage options</span></span>](hr-benefits-setup-coverage-options.md)
- [<span data-ttu-id="fa7ea-137">Konfigurowanie częstotliwości płatności</span><span class="sxs-lookup"><span data-stu-id="fa7ea-137">Set up payment frequencies</span></span>](hr-benefits-setup-payment-frequencies.md)
- [<span data-ttu-id="fa7ea-138">Konfigurowanie typów zdarzeń zmiany sytuacji życiowej</span><span class="sxs-lookup"><span data-stu-id="fa7ea-138">Configure life event types</span></span>](hr-benefits-setup-life-event-types.md)
- [<span data-ttu-id="fa7ea-139">Tworzenie typów planu</span><span class="sxs-lookup"><span data-stu-id="fa7ea-139">Create plan types</span></span>](hr-benefits-setup-plan-types.md)
- [<span data-ttu-id="fa7ea-140">Ustawianie kodów przyczyn</span><span class="sxs-lookup"><span data-stu-id="fa7ea-140">Set up reason codes</span></span>](hr-benefits-setup-reason-codes.md)
- [<span data-ttu-id="fa7ea-141">Ustawianie kodów warstw</span><span class="sxs-lookup"><span data-stu-id="fa7ea-141">Set up tier codes</span></span>](hr-benefits-setup-tier-codes.md)
- [<span data-ttu-id="fa7ea-142">Konfigurowanie stawek</span><span class="sxs-lookup"><span data-stu-id="fa7ea-142">Configure rates</span></span>](hr-benefits-setup-rates.md)
- [<span data-ttu-id="fa7ea-143">Konfigurowanie potrąceń</span><span class="sxs-lookup"><span data-stu-id="fa7ea-143">Configure deductions</span></span>](hr-benefits-setup-deductions.md)
- [<span data-ttu-id="fa7ea-144">Konfigurowanie dni oczekiwania</span><span class="sxs-lookup"><span data-stu-id="fa7ea-144">Configure waiting days</span></span>](hr-benefits-setup-waiting-days.md)
- [<span data-ttu-id="fa7ea-145">Konfigurowanie okresów oczekiwania</span><span class="sxs-lookup"><span data-stu-id="fa7ea-145">Configure waiting periods</span></span>](hr-benefits-setup-waiting-periods.md)
- [<span data-ttu-id="fa7ea-146">Ustawianie reguł zaokrąglania</span><span class="sxs-lookup"><span data-stu-id="fa7ea-146">Set up rounding rules</span></span>](hr-benefits-setup-rounding-rules.md)
- [<span data-ttu-id="fa7ea-147">Tworzenie historii zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="fa7ea-147">Create employment categories</span></span>](hr-benefits-setup-employment-categories.md)
- [<span data-ttu-id="fa7ea-148">Konfigurowanie typów zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="fa7ea-148">Set up employment types</span></span>](hr-benefits-setup-employment-types.md)
- [<span data-ttu-id="fa7ea-149">Konfigurowanie samoobsługi pracownika etatowego</span><span class="sxs-lookup"><span data-stu-id="fa7ea-149">Configure employee self service</span></span>](hr-benefits-setup-employee-self-service.md)

## <a name="create-benefit-plans"></a><span data-ttu-id="fa7ea-150">Tworzenie planów świadczeń</span><span class="sxs-lookup"><span data-stu-id="fa7ea-150">Create benefit plans</span></span>

<span data-ttu-id="fa7ea-151">W tych artykułach przedstawiono sposób tworzenia programów świadczeń, w tym pakietów i programów kredytu elastycznego.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-151">These articles show how to create benefit plans, including bundles and flex credit programs.</span></span>

- [<span data-ttu-id="fa7ea-152">Konfigurowanie planów świadczeń</span><span class="sxs-lookup"><span data-stu-id="fa7ea-152">Set up benefit plans</span></span>](hr-benefits-plans-setup.md)
- [<span data-ttu-id="fa7ea-153">Konfigurowanie elastycznych programów kredytów</span><span class="sxs-lookup"><span data-stu-id="fa7ea-153">Set up flex credit programs</span></span>](hr-benefits-plans-flex-credit-programs.md)

## <a name="process-benefit-plans"></a><span data-ttu-id="fa7ea-154">Przetwarzanie planów świadczeń</span><span class="sxs-lookup"><span data-stu-id="fa7ea-154">Process benefit plans</span></span>

<span data-ttu-id="fa7ea-155">Niektóre zmiany trzeba przetworzyć, aby stały się aktywne.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-155">You need to process some of your changes to make them active.</span></span>

- [<span data-ttu-id="fa7ea-156">Przetwórz uprawnienia do świadczeń</span><span class="sxs-lookup"><span data-stu-id="fa7ea-156">Process enrollment eligibility</span></span>](hr-benefits-process-enrollment-eligibility.md)
- [<span data-ttu-id="fa7ea-157">Przetwarzanie zmian sytuacji życiowej</span><span class="sxs-lookup"><span data-stu-id="fa7ea-157">Process life events</span></span>](hr-benefits-process-life-events.md)
- [<span data-ttu-id="fa7ea-158">Przetwarzanie wybranych zmian sytuacji życiowej</span><span class="sxs-lookup"><span data-stu-id="fa7ea-158">Process life event changes</span></span>](hr-benefits-process-life-event-changes.md)
- [<span data-ttu-id="fa7ea-159">Przetwórz uprawnienia do świadczeń z powodu zmiany sytuacji życiowej</span><span class="sxs-lookup"><span data-stu-id="fa7ea-159">Process life event eligibility</span></span>](hr-benefits-process-life-event-eligibility.md)
- [<span data-ttu-id="fa7ea-160">Przetwórz zmiany stawki</span><span class="sxs-lookup"><span data-stu-id="fa7ea-160">Process rate changes</span></span>](hr-benefits-process-rate-changes.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]