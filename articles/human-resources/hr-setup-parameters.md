---
title: Konfigurowanie parametrów rozwiązania Human Resources
description: W tym temacie wyjaśniono, jak skonfigurować parametry specyficzne dla firmy w Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HRMParameters, HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 51941
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 74bdf891ffa7a9d875e23cf46aeee1dbaf86db48
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5802414"
---
# <a name="configure-human-resources-parameters"></a><span data-ttu-id="f45d4-103">Konfigurowanie parametrów rozwiązania Human Resources</span><span class="sxs-lookup"><span data-stu-id="f45d4-103">Configure Human resources parameters</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="f45d4-104">Niektóre parametry modułu Zasobów ludzkich są wspólne dla wielu firm, podczas gdy inne parametry są specyficzne dla firm.</span><span class="sxs-lookup"><span data-stu-id="f45d4-104">The settings of some Human resources parameters are shared across companies, while the settings of other parameters are company-specific.</span></span> <span data-ttu-id="f45d4-105">W tym temacie wyjaśniono, jak skonfigurować parametry Zasobów ludzkich.</span><span class="sxs-lookup"><span data-stu-id="f45d4-105">This topic explains how to set up company-specific Human resources parameters.</span></span>

<span data-ttu-id="f45d4-106">Do ustawiania parametrów Zasobów ludzkich służą dwie strony.</span><span class="sxs-lookup"><span data-stu-id="f45d4-106">Two pages are used to set Human resources parameters.</span></span> <span data-ttu-id="f45d4-107">W przypadku parametrów współużytkowanych przez firmy, użyj strony **Udostępniane parametry zasobów ludzkich**.</span><span class="sxs-lookup"><span data-stu-id="f45d4-107">For parameters that are shared across companies, you use the **Human resources shared parameters** page.</span></span> <span data-ttu-id="f45d4-108">W przypadku parametrów specyficznych dla firmy (ustawienie dotyczy tylko jednej firmy), użyj strony **Parametry zasobów ludzkich**.</span><span class="sxs-lookup"><span data-stu-id="f45d4-108">For parameters that are company-specific (in other words, the settings apply to a single company), you use the **Human resource parameters** page.</span></span>

![Przejdź do parametrów zasobów ludzkich](./media/hr-employee-self-service-human-resources-parameters.png)

<span data-ttu-id="f45d4-110">Na stronie **parametrów zasobów ludzkich** ustawienia są podzielone na sześciu kartach:</span><span class="sxs-lookup"><span data-stu-id="f45d4-110">On the **Human resources parameters** page, the settings are divided among six tabs:</span></span>

- <span data-ttu-id="f45d4-111">**Ogólny**</span><span class="sxs-lookup"><span data-stu-id="f45d4-111">**General**</span></span>
- <span data-ttu-id="f45d4-112">**Rekrutacja** (tej karty nie ma w aplikacji Dynamics 365 Human Resources)</span><span class="sxs-lookup"><span data-stu-id="f45d4-112">**Recruitment** (this tab isn't included in Dynamics 365 Human Resources)</span></span>
- <span data-ttu-id="f45d4-113">**Kompensacja**</span><span class="sxs-lookup"><span data-stu-id="f45d4-113">**Compensation**</span></span>
- <span data-ttu-id="f45d4-114">**Sekwencje identyfikatorów**</span><span class="sxs-lookup"><span data-stu-id="f45d4-114">**Number sequences**</span></span>
- <span data-ttu-id="f45d4-115">**FMLA**</span><span class="sxs-lookup"><span data-stu-id="f45d4-115">**FMLA**</span></span>
- <span data-ttu-id="f45d4-116">**Samoobsługa pracownika etatowego**</span><span class="sxs-lookup"><span data-stu-id="f45d4-116">**Employee self service**</span></span>
- <span data-ttu-id="f45d4-117">**Samoobsługa menedżera**</span><span class="sxs-lookup"><span data-stu-id="f45d4-117">**Manager self service**</span></span>
- <span data-ttu-id="f45d4-118">**Zarządzanie świadczeniami**</span><span class="sxs-lookup"><span data-stu-id="f45d4-118">**Benefits management**</span></span>
- <span data-ttu-id="f45d4-119">**Urlopy i nieobecności**</span><span class="sxs-lookup"><span data-stu-id="f45d4-119">**Leave and absence**</span></span>
- <span data-ttu-id="f45d4-120">**Metody płatności**</span><span class="sxs-lookup"><span data-stu-id="f45d4-120">**Payment methods**</span></span>

<span data-ttu-id="f45d4-121">Każda karta zawiera informacje dotyczące jednej firmy.</span><span class="sxs-lookup"><span data-stu-id="f45d4-121">Each tab contains information that pertains to a single company.</span></span>

## <a name="general"></a><span data-ttu-id="f45d4-122">Ogólny</span><span class="sxs-lookup"><span data-stu-id="f45d4-122">General</span></span>

<span data-ttu-id="f45d4-123">Ustawienia wprowadzone na karcie **Ogólne** definiują wygląd informacji o nieobecności, urazach, chorobach i zatrudnianiu nowych pracowników.</span><span class="sxs-lookup"><span data-stu-id="f45d4-123">The settings on the **General** tab define the appearance of information about absence, injury and illness, and new hires.</span></span> <span data-ttu-id="f45d4-124">Ustawienia na tej karcie definiują także niektóre domyślne wpisy pojawiające się podczas pracy.</span><span class="sxs-lookup"><span data-stu-id="f45d4-124">The settings on this tab also define some default entries that appear as you work.</span></span> <span data-ttu-id="f45d4-125">W szczególności ta karta umożliwia:</span><span class="sxs-lookup"><span data-stu-id="f45d4-125">Specifically, this tab lets you:</span></span>

- <span data-ttu-id="f45d4-126">Wybierz kolor, który ma być zastosowany do otwartych transakcji nieobecności</span><span class="sxs-lookup"><span data-stu-id="f45d4-126">Select a color to apply to open absence transactions</span></span>
- <span data-ttu-id="f45d4-127">Umożliwia określenie arkusza stylów, który będzie używany dla raportów</span><span class="sxs-lookup"><span data-stu-id="f45d4-127">Specify the style sheet to use for reports</span></span>
- <span data-ttu-id="f45d4-128">Włącz integrację między kursami szkoleniowmi a rejestracją nieobecności</span><span class="sxs-lookup"><span data-stu-id="f45d4-128">Enable the integration between training courses and absence registration</span></span>
- <span data-ttu-id="f45d4-129">Umożliwia wybranie kodu nieobecności używanego do kontrolowania tej integracji.</span><span class="sxs-lookup"><span data-stu-id="f45d4-129">Select the absence code that is used to control this integration.</span></span>
- <span data-ttu-id="f45d4-130">Wskaż, jak długo mają utrzymywać się przypadki obrażeń i chorób.</span><span class="sxs-lookup"><span data-stu-id="f45d4-130">Indicate how long to keep injury and illness case incidents.</span></span>
- <span data-ttu-id="f45d4-131">Umożliwia określenie domyślnego numeru identyfikacyjnego wyświetlanego podczas zatrudniania nowego pracownika.</span><span class="sxs-lookup"><span data-stu-id="f45d4-131">Specify the default identification number shown when a new worker is hired.</span></span>

![Karta Ogólne](./media/hr-setup-parameters-general.png)

## <a name="recruitment"></a><span data-ttu-id="f45d4-133">Rekrutacja</span><span class="sxs-lookup"><span data-stu-id="f45d4-133">Recruitment</span></span>

<span data-ttu-id="f45d4-134">Ustawienia na karcie **Rekrutacja** określają typy dokumentów używane do korespondencji automatycznie wysyłanej do kandydatów.</span><span class="sxs-lookup"><span data-stu-id="f45d4-134">The settings on the **Recruitment** tab define the document types used for correspondence automatically sent to applicants.</span></span> <span data-ttu-id="f45d4-135">Można także wskazać projekt rekrutacji używany dla niechcianych zgłoszeń.</span><span class="sxs-lookup"><span data-stu-id="f45d4-135">You can also indicate the recruitment project used for unsolicited applications.</span></span>

<span data-ttu-id="f45d4-136">Okres zdefiniowany dla wiekowania projektu rekrutacji określa projekty rekrutacji uwzględnione w kafelku **Projekty wiekowania** w obszarze roboczym **Zarządzanie rekrutacją**.</span><span class="sxs-lookup"><span data-stu-id="f45d4-136">The period defined for recruitment project aging determines the recruitment projects included on the **Aging projects** tile in the **Recruitment management** workspace.</span></span> <span data-ttu-id="f45d4-137">Okres zdefiniowany dla ostrzeżenia o ostatecznym terminie zgłoszenia jest używany do wyświetlania projektów rekrutacji, których ostateczny termin zgłoszeń się zbliża i jest określony w kafelku **Zbliża się ostateczny termin zgłoszenia** w obszarze roboczym **Rekrutacja**.</span><span class="sxs-lookup"><span data-stu-id="f45d4-137">The period defined for the application deadline warning is used to display recruitment projects that are approaching their application deadline on the **Application deadline approaching** tile in the **Recruitment** workspace.</span></span>

<span data-ttu-id="f45d4-138">Aby uzyskać więcej informacji o rekrutacji, zobacz temat [Rekrutowanie kandydatów do pracy](hr-personnel-recruit.md).</span><span class="sxs-lookup"><span data-stu-id="f45d4-138">For more information about recruiting, see [Recruit job candidates](hr-personnel-recruit.md).</span></span>

## <a name="compensation"></a><span data-ttu-id="f45d4-139">Kompensacja</span><span class="sxs-lookup"><span data-stu-id="f45d4-139">Compensation</span></span>

<span data-ttu-id="f45d4-140">W Dynamics 365 Finance ustawienia wprowadzone na karcie **Wynagrodzenie** określają, czy użytkownicy muszą potwierdzać, że chcą zapisać informacje dla systemu wynagrodzeń o stałej lub zmiennej wysokości.</span><span class="sxs-lookup"><span data-stu-id="f45d4-140">In Dynamics 365 Finance, the settings on the **Compensation** tab define whether users must confirm that they want to save information for a fixed or variable compensation plan.</span></span> <span data-ttu-id="f45d4-141">W wybrania **Włącz weryfikację zapisu** kiedy użytkownik zamknie stronę związaną z wynagrodzeniami, otrzyma wiadomość z zapytaniem, czy chce zapisać rekord.</span><span class="sxs-lookup"><span data-stu-id="f45d4-141">If you select **Enable save validation**, when users close a compensation-related page, they receive a message that asks whether they want to save the record.</span></span> <span data-ttu-id="f45d4-142">Niektóre strony w module Zarządzania wynagrodzeniami nie zezwalają na usuwanie informacji.</span><span class="sxs-lookup"><span data-stu-id="f45d4-142">Some pages in Compensation management don't let users delete information.</span></span> <span data-ttu-id="f45d4-143">Dzięki pytaniu użytkowników, czy chcą zapisać informacje, można ograniczyć ilość zapisywanych danych, których potem nie można usunąć.</span><span class="sxs-lookup"><span data-stu-id="f45d4-143">By prompting users to verify that they want to save information, you might be able to limit the amount of information that is saved but can't be deleted later.</span></span> <span data-ttu-id="f45d4-144">Jeśli pole wyboru **Włącz weryfikację zapisu** nie jest zaznaczone, rekordy będą natychmiast zapisywane, być może zanim użytkownik będzie gotowy.</span><span class="sxs-lookup"><span data-stu-id="f45d4-144">If you clear **Enable save validation**, records save immediately, possibly before the user is ready.</span></span> <span data-ttu-id="f45d4-145">W przypadku korzystania z funkcji Zarządzania wydajnością można wybrać model oceniania na karcie **Wynagrodzenie** zamiast modelu przypisanego do systemów wynagrodzeń przy ocenie wydajności.</span><span class="sxs-lookup"><span data-stu-id="f45d4-145">If you're using Performance management, the **Compensation** tab also lets you select a rating model to use instead of the model assigned to compensation plans when rating performance.</span></span>

<span data-ttu-id="f45d4-146">W obszarze Zasoby ludzkie można użyć karty **Wynagrodzenie**, aby ograniczyć dostęp do planów wynagrodzeń i ustawić walutę domyślną.</span><span class="sxs-lookup"><span data-stu-id="f45d4-146">In Human Resources, you can use the **Compensation** tab to choose to restrict access to compensation plans and to set a default currency.</span></span>

<span data-ttu-id="f45d4-147">Aby uzyskać więcej informacji o planach wynagrodzeń, zobacz [Omówienie planów wynagrodzeń](hr-compensation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f45d4-147">For more information about compensation, see [Compensation plans overview](hr-compensation-overview.md).</span></span>

![Karta Wynagrodzenie](./media/hr-setup-parameters-compensation.png)

## <a name="number-sequences"></a><span data-ttu-id="f45d4-149">Sekwencje identyfikatorów</span><span class="sxs-lookup"><span data-stu-id="f45d4-149">Number sequences</span></span>

<span data-ttu-id="f45d4-150">Ustawienia na karcie **Sekwencja numerów** decydują o sekwencjach używanych do automatycznego przypisywania identyfikatorów do towarów w zasobach ludzkich, takich jak:</span><span class="sxs-lookup"><span data-stu-id="f45d4-150">The settings on the **Number sequence** tab determine the sequences used to automatically assign IDs to items in Human Resources, such as:</span></span>

- <span data-ttu-id="f45d4-151">Aplikacje</span><span class="sxs-lookup"><span data-stu-id="f45d4-151">Applications</span></span>
- <span data-ttu-id="f45d4-152">Rejestracje nieobecności</span><span class="sxs-lookup"><span data-stu-id="f45d4-152">Absence registrations</span></span>
- <span data-ttu-id="f45d4-153">Wyniki procesu związanego z wynagrodzeniem</span><span class="sxs-lookup"><span data-stu-id="f45d4-153">Compensation process results</span></span>
- <span data-ttu-id="f45d4-154">Numery przypadków</span><span class="sxs-lookup"><span data-stu-id="f45d4-154">Case numbers</span></span>
- <span data-ttu-id="f45d4-155">Kursy</span><span class="sxs-lookup"><span data-stu-id="f45d4-155">Courses</span></span>
- <span data-ttu-id="f45d4-156">Programy kursów</span><span class="sxs-lookup"><span data-stu-id="f45d4-156">Course agendas</span></span>

<span data-ttu-id="f45d4-157">Aby obsługiwać odwołania numeracji i kody, użyj strony listy **Sekwencje identyfikatorów** (wybierz **Administrowanie organizacją > Sekwencje identyfikatorów > Sekwencje identyfikatorów**).</span><span class="sxs-lookup"><span data-stu-id="f45d4-157">To maintain number sequence references and codes, use the **Number sequences** list page (select **Organization administration > Number sequences > Number sequences**).</span></span>

<span data-ttu-id="f45d4-158">Aby uzyskać więcej informacji, zobacz temat [Omówienie sekwencji identyfikatorów](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/number-sequence-overview?toc=/dynamics365/human-resources/toc.json).</span><span class="sxs-lookup"><span data-stu-id="f45d4-158">For more information, see [Number sequences overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/number-sequence-overview?toc=/dynamics365/human-resources/toc.json).</span></span>

> [!NOTE]
> <span data-ttu-id="f45d4-159">Liczba przepracowanych godzin nie może przekroczyć 1250, a staż pracy nie może przekroczyć 12 miesięcy.</span><span class="sxs-lookup"><span data-stu-id="f45d4-159">The number of hours that are worked can't exceed 1,250, and the length of employment can't exceed 12 months.</span></span> <span data-ttu-id="f45d4-160">Te maksymalne wartości są zgodne z prawem federalnym w Stanach Zjednoczonych.</span><span class="sxs-lookup"><span data-stu-id="f45d4-160">These maximum values are in accordance with federal law in the United States.</span></span>

![Karta Sekwencje numerów](./media/hr-setup-parameters-number-sequences.png)

## <a name="fmla"></a><span data-ttu-id="f45d4-162">FMLA</span><span class="sxs-lookup"><span data-stu-id="f45d4-162">FMLA</span></span>

<span data-ttu-id="f45d4-163">Na karcie FMLA są ustawiane wymagania dotyczące uprawnień FMLA i godziny uprawnień FMLA.</span><span class="sxs-lookup"><span data-stu-id="f45d4-163">On the FMLA tab, you set FMLA eligibility requirements and FMLA entitlement hours.</span></span> <span data-ttu-id="f45d4-164">Aby uzyskać więcej informacji, zobacz [Konfigurowanie parametrów urlopu i nieobecności](hr-leave-and-absence-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="f45d4-164">For more information, see [Configure leave and absence parameters](hr-leave-and-absence-parameters.md).</span></span>

![Karta FMLA](./media/hr-setup-parameters-fmla.png)

## <a name="employee-self-service"></a><span data-ttu-id="f45d4-166">Samoobsługa pracownika etatowego</span><span class="sxs-lookup"><span data-stu-id="f45d4-166">Employee self service</span></span>

<span data-ttu-id="f45d4-167">Ustawienia na karcie **Samoobsługa pracownika etatowego** mają wpływ na sposób, w jaki samoobsługa pracownika etatowego jest wyświetlana pracownikom etatowym.</span><span class="sxs-lookup"><span data-stu-id="f45d4-167">The settings on the **Employee self service** tab affect how Employee self service appears to employees.</span></span> <span data-ttu-id="f45d4-168">Na tej karcie można:</span><span class="sxs-lookup"><span data-stu-id="f45d4-168">On this tab, you can:</span></span>

- <span data-ttu-id="f45d4-169">Wprowadź nazwę obszaru roboczego samoobsługi pracownika</span><span class="sxs-lookup"><span data-stu-id="f45d4-169">Enter a name for the Employee self service workspace</span></span>
- <span data-ttu-id="f45d4-170">Wybierz, jakie informacje menedżer może wprowadzić dla pracowników</span><span class="sxs-lookup"><span data-stu-id="f45d4-170">Select which information a manager can enter for employees</span></span>
- <span data-ttu-id="f45d4-171">Dodawanie przydatnych łączy dla pracowników</span><span class="sxs-lookup"><span data-stu-id="f45d4-171">Add useful links for employees</span></span>
- <span data-ttu-id="f45d4-172">Zablokuj pracownikom możliwość dodawania lub edytowania biznesowych danych kontaktowych.</span><span class="sxs-lookup"><span data-stu-id="f45d4-172">Restrict employees from adding or editing business contact details.</span></span> <span data-ttu-id="f45d4-173">Aby uzyskać więcej informacji, zobacz temat [Ogranicz edycję danych osobowych](hr-employee-self-service-restrict-editing.md).</span><span class="sxs-lookup"><span data-stu-id="f45d4-173">For more information, see [Restrict editing of personal information](hr-employee-self-service-restrict-editing.md).</span></span>

<span data-ttu-id="f45d4-174">Aby uzyskać więcej informacji dotyczących konfigurowania funkcji samoobsługi pracowników etatowych, zobacz [Omówienie samoobsługi dla pracownika etatowego i menedżera](hr-employee-manager-self-service-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f45d4-174">For more information about setting up Employee self service, see [Employee and Manager self service overview](hr-employee-manager-self-service-overview.md).</span></span>

![Karta Samoobsługa pracownika etatowego](./media/hr-setup-parameters-employee-self-service.png)

## <a name="manager-self-service"></a><span data-ttu-id="f45d4-176">Samoobsługa menedżera</span><span class="sxs-lookup"><span data-stu-id="f45d4-176">Manager self service</span></span>

<span data-ttu-id="f45d4-177">Ustawienia na karcie **Samoobsługa menedżera** wpływają na to, co menedżerowie widzą w samoobsługi menedżera.</span><span class="sxs-lookup"><span data-stu-id="f45d4-177">The settings on the **Manager self service** tab affect what managers see in Manager self service.</span></span> <span data-ttu-id="f45d4-178">Na tej karcie można skonfigurować następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="f45d4-178">On this tab, you can configure the following options:</span></span>

- <span data-ttu-id="f45d4-179">Zakres wygasających rekordów</span><span class="sxs-lookup"><span data-stu-id="f45d4-179">The range for expiring records</span></span>
- <span data-ttu-id="f45d4-180">Informacje, które menedżerowie mogą wyświetlać w wygasających rekordach</span><span class="sxs-lookup"><span data-stu-id="f45d4-180">Information managers can view in expiring records</span></span>
- <span data-ttu-id="f45d4-181">Określa, czy menedżerowie mogą wyświetlać otwarte stanowiska w raportach rozszerzonych</span><span class="sxs-lookup"><span data-stu-id="f45d4-181">Whether managers can view open positions for extended reports</span></span>
- <span data-ttu-id="f45d4-182">Widoki odchodzących pracowników</span><span class="sxs-lookup"><span data-stu-id="f45d4-182">Views of exiting workers</span></span>
- <span data-ttu-id="f45d4-183">Przydatne łącza dla menedżerów</span><span class="sxs-lookup"><span data-stu-id="f45d4-183">Useful links for managers</span></span>

<span data-ttu-id="f45d4-184">Aby uzyskać więcej informacji dotyczących konfigurowania funkcji samoobsługi menedżerów, zobacz [Omówienie samoobsługi dla pracownika etatowego i menedżera](hr-employee-manager-self-service-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f45d4-184">For more information about setting up Manager self service, see [Employee and Manager self service overview](hr-employee-manager-self-service-overview.md).</span></span>

![Karta Samoobsługa menedżera](./media/hr-setup-parameters-manager-self-service.png)

## <a name="benefits-management"></a><span data-ttu-id="f45d4-186">Zarządzanie świadczeniami</span><span class="sxs-lookup"><span data-stu-id="f45d4-186">Benefits management</span></span>

<span data-ttu-id="f45d4-187">Na karcie Zarządzanie świadczeniami możesz skonfigurować opcje poczty e-mail dotyczące zarządzania świadczeniami.</span><span class="sxs-lookup"><span data-stu-id="f45d4-187">On the Benefits management tab, you can configure email options for Benefits management.</span></span> <span data-ttu-id="f45d4-188">Aby uzyskać więcej informacji na temat konfiguracji i użytkowania funkcji Zarządzanie świadczeniami, zobacz [Zarządzanie świadczeniami - omówienie](hr-benefits-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f45d4-188">For information about setting up and using Benefits management, see [Benefits management overview](hr-benefits-management-overview.md).</span></span>

![Karta Zarządzanie świadczeniami](./media/hr-setup-parameters-benefits-management.png)

## <a name="leave-and-absence"></a><span data-ttu-id="f45d4-190">Urlopy i nieobecności</span><span class="sxs-lookup"><span data-stu-id="f45d4-190">Leave and absence</span></span>

<span data-ttu-id="f45d4-191">Aby uzyskać więcej informacji dotyczących konfigurowania i korzystania z Urlopów i nieobecności, zobacz [Zarządzanie urlopami i nieobecnościami](hr-leave-and-absence-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f45d4-191">For information about setting up and using Leave and absence, see [Leave and absence overview](hr-leave-and-absence-overview.md).</span></span>

## <a name="payment-methods"></a><span data-ttu-id="f45d4-192">Metody płatności</span><span class="sxs-lookup"><span data-stu-id="f45d4-192">Payment methods</span></span>

<span data-ttu-id="f45d4-193">Na karcie **Metody płatności** możesz wybrać metody płatności obsługiwane przez organizację.</span><span class="sxs-lookup"><span data-stu-id="f45d4-193">On the **Payment methods** tab, you can select the payment methods supported by your organization.</span></span> <span data-ttu-id="f45d4-194">Aby uzyskać więcej informacji o konfiguracji planów wynagrodzeń, zobacz [Omówienie planów wynagrodzeń](hr-compensation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f45d4-194">For more information about configuring compensation, see [Compensation plans overview](hr-compensation-overview.md).</span></span>

![Karta Metody płatności](./media/hr-setup-parameters-payment-methods.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]