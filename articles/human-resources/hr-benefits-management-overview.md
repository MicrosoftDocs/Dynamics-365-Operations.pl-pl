---
title: Omówienie zarządzania świadczeniami
description: Omówienie funkcji Zarządzanie świadczeniami w Dynamics 365 Human Resources. Zaoferuj pracownikom rozszerzone opcje zarządzania świadczeniami w przyjaznym internetowym środowisku.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
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
ms.openlocfilehash: 4157cb1f83d686d435f3d04e47c578df455376c9
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2020
ms.locfileid: "3429273"
---
# <a name="benefits-management-overview"></a><span data-ttu-id="cda18-104">Omówienie obszaru roboczego Zarządzanie świadczeniami</span><span class="sxs-lookup"><span data-stu-id="cda18-104">Benefits management overview</span></span>

<span data-ttu-id="cda18-105">Aby zachować konkurencyjność, należy oferować bogaty zestaw świadczeń, który pomoże przyciągnąć i utrzymać najlepszych pracowników.</span><span class="sxs-lookup"><span data-stu-id="cda18-105">To remain competitive, you must offer a rich set of benefits to attract and retain your best employees.</span></span> <span data-ttu-id="cda18-106">Oprócz standardowych świadczeń, takich jak opieka medyczna i dentystyczna, można również zaoferować rozszerzone usługi, takie jak pomoc we wdrożeniu do pracy, programy rekreacyjne i dodatki na odzież roboczą.</span><span class="sxs-lookup"><span data-stu-id="cda18-106">In addition to standard benefits like medical and dental coverage, you might also want to offer expanded services like adoption assistance, recreation programs, and clothing allowances.</span></span> <span data-ttu-id="cda18-107">Funkcja Zarządzanie świadczeniami dostępna w Microsoft Dynamics 365 Human Resources stanowi elastyczne rozwiązanie, które obsługuje wiele różnych opcji świadczeń.</span><span class="sxs-lookup"><span data-stu-id="cda18-107">Benefits management in Microsoft Dynamics 365 Human Resources provides you with a flexible solution that supports a wide variety of benefit options.</span></span> <span data-ttu-id="cda18-108">Moduł Human Resources zawiera również przyjazne środowisko obsługi pracownika, które eksponuje oferty pracodawcy.</span><span class="sxs-lookup"><span data-stu-id="cda18-108">Human Resources also includes an easy-to-use employee experience that showcases your offerings.</span></span>

- <span data-ttu-id="cda18-109">Rozszerzona funkcjonalność planów świadczeń umożliwia tworzenie unikatowych planów świadczeń i zarządzanie nimi oraz obsługę skomplikowanych tabel stawek i zagnieżdżonych warstw.</span><span class="sxs-lookup"><span data-stu-id="cda18-109">Enhanced benefits plans let you create and manage unique benefit plans and support complex benefit rate tables and nested tiers.</span></span> <span data-ttu-id="cda18-110">Istnieje możliwość łatwego tworzenia programów świadczeń, pakietów i reguł automatycznego rejestrowania, aby ułatwić pracownikom obsługę.</span><span class="sxs-lookup"><span data-stu-id="cda18-110">You can easily create benefit programs, bundles, and auto-enrollment rules for an easier employee experience.</span></span>

- <span data-ttu-id="cda18-111">Programy kredytu elastycznego umożliwiają obliczanie proporcjonalne w celu uwzględnienia przejścia na emeryturę i innych zmian sytuacji życiowej.</span><span class="sxs-lookup"><span data-stu-id="cda18-111">Flex credit programs let you prorate to support retirement and other life events.</span></span>

- <span data-ttu-id="cda18-112">Rozbudowane reguły uprawnień pomagają udostępniać odpowiednie świadczenia odpowiednim pracownikom.</span><span class="sxs-lookup"><span data-stu-id="cda18-112">Extensive eligibility rules ensure you make the right benefits available to the right employees.</span></span>

- <span data-ttu-id="cda18-113">Internetowa rejestracja na świadczenia ułatwia pracownikom korzystanie z systemu.</span><span class="sxs-lookup"><span data-stu-id="cda18-113">Online benefits enrollment provides an easy experience for your employees.</span></span>

- <span data-ttu-id="cda18-114">Przetwarzanie kwalifikowanych zdarzeń życiowych obsługuje przyszłe zdarzenia życiowe.</span><span class="sxs-lookup"><span data-stu-id="cda18-114">Qualified life event processing supports future life events.</span></span>

<span data-ttu-id="cda18-115">Jeśli chcesz przejść do danych demonstracyjnych, musisz ponownie wdrożyć środowisko piaskownicy.</span><span class="sxs-lookup"><span data-stu-id="cda18-115">If you would like to access the demo data, you'll need to redeploy your sandbox environment.</span></span>

## <a name="benefits-management-known-issues"></a><span data-ttu-id="cda18-116">Znane problemy związane z zarządzaniem korzyściami</span><span class="sxs-lookup"><span data-stu-id="cda18-116">Benefits management known issues</span></span>

### <a name="flex-credit-programs"></a><span data-ttu-id="cda18-117">Programy kredytów elastycznych</span><span class="sxs-lookup"><span data-stu-id="cda18-117">Flex credit programs</span></span>

<span data-ttu-id="cda18-118">Łączna wartość kredytu zdefiniowana dla programu kredytu elastycznego nie jest wyświetlana w formularzu **Plany świadczeń pracowniczych**.</span><span class="sxs-lookup"><span data-stu-id="cda18-118">The total credit value defined for a flex credit program doesn't display in the **Worker benefit plans** form.</span></span> <span data-ttu-id="cda18-119">Ponadto, jeśli ustawisz program elastycznych kredytów w celu uwzględnienia reguły **Brak**, podczas wybierania i zatwierdzania planów pojawi się komunikat o błędzie w formularzu **Plan świadczeń pracowniczych**.</span><span class="sxs-lookup"><span data-stu-id="cda18-119">Also, if you set a flex credit program to have a proration rule of **None**, you get an error in the **Worker benefit plan** form when selecting and confirming plans.</span></span>

## <a name="enable-benefits-management"></a><span data-ttu-id="cda18-120">Włączanie obszaru roboczego Zarządzanie świadczeniami</span><span class="sxs-lookup"><span data-stu-id="cda18-120">Enable Benefits management</span></span>

<span data-ttu-id="cda18-121">Ten artykuł opisuje sposób włączania funkcji w wersji zapoznawczej w module Human Resources.</span><span class="sxs-lookup"><span data-stu-id="cda18-121">This article describes how to turn on features in Human Resources.</span></span> <span data-ttu-id="cda18-122">Informuje również, które z istniejących funkcji w module Human Resources są zastępowane lub wyłączane przez obszar roboczy Zarządzanie świadczeniami po jego włączeniu.</span><span class="sxs-lookup"><span data-stu-id="cda18-122">It also tells which existing features in Human Resources that Benefits management replaces or are disabled once you turn on Benefits management.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cda18-123">Po włączeniu Zarządzania świadczeniami w środowisku **Produkcyjnym** nie można go wyłączyć.</span><span class="sxs-lookup"><span data-stu-id="cda18-123">After you enable Benefits management in a **Production** environment, you can't disable it.</span></span> <span data-ttu-id="cda18-124">Zaleca się włączanie i testowanie Zarządzania świadczeniami w środowisku **Piaskownicy** przed włączeniem go w środowisku **Produkcyjnym**.</span><span class="sxs-lookup"><span data-stu-id="cda18-124">We recommend enabling and testing Benefits management in a **Sandbox** environment before enabling it in a **Production** environment.</span></span> <span data-ttu-id="cda18-125">Istnieją znaczne różnice między funkcjami starszego świadczenia i nowymi funkcjami zarządzania świadczeniami, które wymagają dodatkowej konfiguracji i powinny być testowane przed wprowadzeniem do produkcji.</span><span class="sxs-lookup"><span data-stu-id="cda18-125">There are significant differences between the legacy Benefit functionality and new Benefits management functionality that require additional setup and should be tested prior to being placed into production.</span></span>

- [<span data-ttu-id="cda18-126">Zarządzanie funkcjami</span><span class="sxs-lookup"><span data-stu-id="cda18-126">Manage features</span></span>](hr-admin-manage-features.md)

## <a name="configure-employee-information"></a><span data-ttu-id="cda18-127">Skonfiguruj informacje dotyczące pracowników</span><span class="sxs-lookup"><span data-stu-id="cda18-127">Configure employee information</span></span>

<span data-ttu-id="cda18-128">Aby można było zarejestrować pracowników w ramach świadczeń, musisz podać wymagane informacje.</span><span class="sxs-lookup"><span data-stu-id="cda18-128">Before you can enroll employees in benefits, you must provide required information.</span></span> <span data-ttu-id="cda18-129">Należy zarejestrować pracownika w **Planie stałych wynagrodzeń** według daty rozpoczęcia, a następnie wybrać opcję **Częstotliwość wypłat świadczenia** w **Szczegóły zatrudnienia** w formularzu **Pracownik**.</span><span class="sxs-lookup"><span data-stu-id="cda18-129">You must enroll an employee in a **Fixed compensation plan** on their start date, and you must select a **Benefit pay frequency** in **Employment details** on the **Worker** form.</span></span>

<span data-ttu-id="cda18-130">Podczas tworzenia planu świadczeń, w którym używane są stawki oparte na płci lub wieku, należy wprowadzić datę urodzenia i płeć dla pracownika, aby obliczyć koszty świadczeń.</span><span class="sxs-lookup"><span data-stu-id="cda18-130">When you create a benefit plan that uses rates that are based on gender or age, you must enter a birth date and gender for the employee to calculate the benefit cost.</span></span>

## <a name="configure-benefits-management"></a><span data-ttu-id="cda18-131">Konfigurowanie zarządzania świadczeniami</span><span class="sxs-lookup"><span data-stu-id="cda18-131">Configure Benefits management</span></span>

<span data-ttu-id="cda18-132">Zanim będzie można tworzyć plany świadczeń dla pracowników, należy skonfigurować opcje dla planów.</span><span class="sxs-lookup"><span data-stu-id="cda18-132">Before you can create benefit plans for your employees, you need to configure options for the plans.</span></span>

- [<span data-ttu-id="cda18-133">Ustawianie parametrów obszaru roboczego Zarządzanie świadczeniami</span><span class="sxs-lookup"><span data-stu-id="cda18-133">Set Benefits management parameters</span></span>](hr-benefits-setup-parameters.md)
- [<span data-ttu-id="cda18-134">Konfigurowanie reguł i opcji uprawnień</span><span class="sxs-lookup"><span data-stu-id="cda18-134">Configure eligibility rules and options</span></span>](hr-benefits-setup-eligibility-rules.md)
- [<span data-ttu-id="cda18-135">Konfigurowanie opcji uprawnień do kontaktu osobistego</span><span class="sxs-lookup"><span data-stu-id="cda18-135">Configure personal contact eligibility options</span></span>](hr-benefits-setup-contact-eligibility-options.md)
- [<span data-ttu-id="cda18-136">Tworzenie opcji zapotrzebowania</span><span class="sxs-lookup"><span data-stu-id="cda18-136">Create coverage options</span></span>](hr-benefits-setup-coverage-options.md)
- [<span data-ttu-id="cda18-137">Konfigurowanie częstotliwości płatności</span><span class="sxs-lookup"><span data-stu-id="cda18-137">Set up payment frequencies</span></span>](hr-benefits-setup-payment-frequencies.md)
- [<span data-ttu-id="cda18-138">Konfigurowanie typów zdarzeń zmiany sytuacji życiowej</span><span class="sxs-lookup"><span data-stu-id="cda18-138">Configure life event types</span></span>](hr-benefits-setup-life-event-types.md)
- [<span data-ttu-id="cda18-139">Tworzenie typów planu</span><span class="sxs-lookup"><span data-stu-id="cda18-139">Create plan types</span></span>](hr-benefits-setup-plan-types.md)
- [<span data-ttu-id="cda18-140">Ustawianie kodów przyczyn</span><span class="sxs-lookup"><span data-stu-id="cda18-140">Set up reason codes</span></span>](hr-benefits-setup-reason-codes.md)
- [<span data-ttu-id="cda18-141">Ustawianie kodów warstw</span><span class="sxs-lookup"><span data-stu-id="cda18-141">Set up tier codes</span></span>](hr-benefits-setup-tier-codes.md)
- [<span data-ttu-id="cda18-142">Konfigurowanie stawek</span><span class="sxs-lookup"><span data-stu-id="cda18-142">Configure rates</span></span>](hr-benefits-setup-rates.md)
- [<span data-ttu-id="cda18-143">Konfigurowanie potrąceń</span><span class="sxs-lookup"><span data-stu-id="cda18-143">Configure deductions</span></span>](hr-benefits-setup-deductions.md)
- [<span data-ttu-id="cda18-144">Konfigurowanie dni oczekiwania</span><span class="sxs-lookup"><span data-stu-id="cda18-144">Configure waiting days</span></span>](hr-benefits-setup-waiting-days.md)
- [<span data-ttu-id="cda18-145">Konfigurowanie okresów oczekiwania</span><span class="sxs-lookup"><span data-stu-id="cda18-145">Configure waiting periods</span></span>](hr-benefits-setup-waiting-periods.md)
- [<span data-ttu-id="cda18-146">Ustawianie reguł zaokrąglania</span><span class="sxs-lookup"><span data-stu-id="cda18-146">Set up rounding rules</span></span>](hr-benefits-setup-rounding-rules.md)
- [<span data-ttu-id="cda18-147">Tworzenie historii zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="cda18-147">Create employment categories</span></span>](hr-benefits-setup-employment-categories.md)
- [<span data-ttu-id="cda18-148">Konfigurowanie typów zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="cda18-148">Set up employment types</span></span>](hr-benefits-setup-employment-types.md)
- [<span data-ttu-id="cda18-149">Konfigurowanie samoobsługi pracownika etatowego</span><span class="sxs-lookup"><span data-stu-id="cda18-149">Configure employee self service</span></span>](hr-benefits-setup-employee-self-service.md)

## <a name="create-benefit-plans"></a><span data-ttu-id="cda18-150">Tworzenie planów świadczeń</span><span class="sxs-lookup"><span data-stu-id="cda18-150">Create benefit plans</span></span>

<span data-ttu-id="cda18-151">W tych artykułach przedstawiono sposób tworzenia programów świadczeń, w tym pakietów i programów kredytu elastycznego.</span><span class="sxs-lookup"><span data-stu-id="cda18-151">These articles show how to create benefit plans, including bundles and flex credit programs.</span></span>

- [<span data-ttu-id="cda18-152">Konfigurowanie planów świadczeń</span><span class="sxs-lookup"><span data-stu-id="cda18-152">Set up benefit plans</span></span>](hr-benefits-plans-setup.md)
- [<span data-ttu-id="cda18-153">Konfigurowanie elastycznych programów kredytów</span><span class="sxs-lookup"><span data-stu-id="cda18-153">Set up flex credit programs</span></span>](hr-benefits-plans-flex-credit-programs.md)

## <a name="process-benefit-plans"></a><span data-ttu-id="cda18-154">Przetwarzanie planów świadczeń</span><span class="sxs-lookup"><span data-stu-id="cda18-154">Process benefit plans</span></span>

<span data-ttu-id="cda18-155">Niektóre zmiany trzeba przetworzyć, aby stały się aktywne.</span><span class="sxs-lookup"><span data-stu-id="cda18-155">You need to process some of your changes to make them active.</span></span>

- [<span data-ttu-id="cda18-156">Przetwórz uprawnienia do świadczeń</span><span class="sxs-lookup"><span data-stu-id="cda18-156">Process enrollment eligibility</span></span>](hr-benefits-process-enrollment-eligibility.md)
- [<span data-ttu-id="cda18-157">Przetwarzanie zmian sytuacji życiowej</span><span class="sxs-lookup"><span data-stu-id="cda18-157">Process life events</span></span>](hr-benefits-process-life-events.md)
- [<span data-ttu-id="cda18-158">Przetwarzanie wybranych zmian sytuacji życiowej</span><span class="sxs-lookup"><span data-stu-id="cda18-158">Process life event changes</span></span>](hr-benefits-process-life-event-changes.md)
- [<span data-ttu-id="cda18-159">Przetwórz uprawnienia do świadczeń z powodu zmiany sytuacji życiowej</span><span class="sxs-lookup"><span data-stu-id="cda18-159">Process life event eligibility</span></span>](hr-benefits-process-life-event-eligibility.md)
- [<span data-ttu-id="cda18-160">Przetwórz zmiany stawki</span><span class="sxs-lookup"><span data-stu-id="cda18-160">Process rate changes</span></span>](hr-benefits-process-rate-changes.md)

