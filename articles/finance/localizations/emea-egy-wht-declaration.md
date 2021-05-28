---
title: Deklaracja potrąconej zaliczki na podatek dla Egiptu
description: W tym temacie wyjaśniono, jak skonfigurować i wygenerować deklaracje podatku u źródła dla Egiptu.
author: sndray
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: ''
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2017-06-20
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 8c9aaa3868167806ce3189d724621991ec7e53eb
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022818"
---
#  <a name="withholding-tax-declaration-for-egypt-eg-00005"></a><span data-ttu-id="05af3-103">Deklaracja potrąconej zaliczki na podatek dla Egiptu (EG-00005)</span><span class="sxs-lookup"><span data-stu-id="05af3-103">Withholding tax declaration for Egypt (EG-00005)</span></span>

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

## <a name="overview"></a><span data-ttu-id="05af3-104">Omówienie</span><span class="sxs-lookup"><span data-stu-id="05af3-104">Overview</span></span>
<span data-ttu-id="05af3-105">W tym temacie wyjaśniono, jak skonfigurować i wygenerować deklarację podatku u źródła oraz formularze 41 i 11 deklaracji podatku u źródła dla osób prawnych w Egipcie</span><span class="sxs-lookup"><span data-stu-id="05af3-105">This topic explains how to set up and generate the withholding tax declaration and the withholding tax declaration forms 41 and 11 for legal entities in Egypt</span></span> 

<span data-ttu-id="05af3-106">Wszystkie jednostki Te muszą przygotować formularz 41, który podsumowuje wszystkie podatki zatrzymane od lokalnych dostawców i usługodawców.</span><span class="sxs-lookup"><span data-stu-id="05af3-106">All Egyptian entities must prepare the form  41 which summarizes all taxes that are retained from local suppliers and service providers.</span></span> <span data-ttu-id="05af3-107">Oprócz formularza 41 należy wygenerować formularz 11, aby wyszczególnić wszystkie zatrzymane podatki od dostawców zagranicznych.</span><span class="sxs-lookup"><span data-stu-id="05af3-107">In addition to form 41, form 11 must be generated to detail all of the retained taxed from foreign providers.</span></span> 

<span data-ttu-id="05af3-108">Raport **Deklaracji potrąconej zaliczki na podatek** w Dynamics 365 Finance zawiera następujące raporty:</span><span class="sxs-lookup"><span data-stu-id="05af3-108">The **Withholding tax declaration** report in Dynamics 365 Finance includes the following reports:</span></span>

- <span data-ttu-id="05af3-109">Formularz deklaracji Nie.</span><span class="sxs-lookup"><span data-stu-id="05af3-109">Declaration form No.</span></span> <span data-ttu-id="05af3-110">41</span><span class="sxs-lookup"><span data-stu-id="05af3-110">41</span></span>
- <span data-ttu-id="05af3-111">Formularz deklaracji Nie.</span><span class="sxs-lookup"><span data-stu-id="05af3-111">Declaration form No.</span></span> <span data-ttu-id="05af3-112">11</span><span class="sxs-lookup"><span data-stu-id="05af3-112">11</span></span>
    
    
## <a name="prerequisites"></a><span data-ttu-id="05af3-113">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="05af3-113">Prerequisites</span></span>
<span data-ttu-id="05af3-114">Podstawowy adres firmy musi być w Egipcie.</span><span class="sxs-lookup"><span data-stu-id="05af3-114">The primary address of the legal entity must be in Egypt.</span></span>
<span data-ttu-id="05af3-115">W obszarze roboczym **Zarządzanie funkcjami** włącz następujące funkcje:</span><span class="sxs-lookup"><span data-stu-id="05af3-115">In the **Feature management** workspace, the following feature must be enabled:</span></span>

   - <span data-ttu-id="05af3-116">**Globalna potrącona zaliczka na podatek**</span><span class="sxs-lookup"><span data-stu-id="05af3-116">**Global withholding tax**</span></span>

<span data-ttu-id="05af3-117">Aby uzyskać więcej informacji o włączaniu funkcji, zobacz [Zarządzanie funkcjami — omówienie.](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)</span><span class="sxs-lookup"><span data-stu-id="05af3-117">For more information about how to enable features, see [Feature management overview.](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)</span></span>

1. <span data-ttu-id="05af3-118">Przejdź do **Podatek** > **Konfiguracja** > **Parametry** > **Parametry księgi głównej**, a następnie na karcie **Potrącona zaliczka** na podatek ustaw opcję **Włącz globalną potrącanie zaliczki na podatek** na wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="05af3-118">Go to **Tax** > **Setup** > **Parameters** > **General ledger parameters**, and on the **Withholding tax** tab, set **Enable global withholding tax** to **Yes**.</span></span>
2. <span data-ttu-id="05af3-119">W obszarze roboczym **Raportowanie elektroniczne** zaimportuj następujące formaty raportowania elektronicznego z repozytorium:</span><span class="sxs-lookup"><span data-stu-id="05af3-119">In the **Electronic reporting** workspace, import the following Electronic reporting formats from the repository:</span></span>

    - <span data-ttu-id="05af3-120">Deklaracja WHT Excel (EG)</span><span class="sxs-lookup"><span data-stu-id="05af3-120">WHT Declaration Excel (EG)</span></span>

    > [!NOTE]
    > <span data-ttu-id="05af3-121">Powyższy format jest oparty na **Modelu deklaracji podatkowej** i korzysta z **Mapowania modelu deklaracji podatkowej**.</span><span class="sxs-lookup"><span data-stu-id="05af3-121">The format above is based on the **Tax declaration model** and uses the **Tax declaration model mapping**.</span></span> <span data-ttu-id="05af3-122">Ta dodatkowa konfiguracja jest automatycznie importowana.</span><span class="sxs-lookup"><span data-stu-id="05af3-122">This additional configuration is automatically imported.</span></span>

<span data-ttu-id="05af3-123">Aby uzyskać więcej informacji dotyczących importowania konfiguracji raportowania elektronicznego, zobacz temat [Pobieranie konfiguracji raportowania elektronicznego z usługi Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span><span class="sxs-lookup"><span data-stu-id="05af3-123">For more information about how to import Electronic reporting configurations, see [Download Electronic reporting configurations from Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span></span>

## <a name="download-electronic-reporting-configurations"></a><span data-ttu-id="05af3-124">Pobieranie konfiguracji raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="05af3-124">Download Electronic reporting configurations</span></span>

<span data-ttu-id="05af3-125">Wdrażanie formularzy deklaracji WHT dla Egiptu opiera się na konfiguracjach elektronicznego raportowania (ER).</span><span class="sxs-lookup"><span data-stu-id="05af3-125">The implementation of the WHT declaration forms for Egypt is based on Electronic reporting (ER) configurations.</span></span> <span data-ttu-id="05af3-126">Aby uzyskać więcej informacji o możliwościach i pojęciach dotyczących raportowania konfigurowalnego, zobacz temat [Raportowanie elektroniczne](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="05af3-126">For more information about the capabilities and concepts of configurable reporting, see [Electronic reporting](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).</span></span>

<span data-ttu-id="05af3-127">W przypadku środowisk produkcyjnych i testów akceptacyjnych użytkownika (UAT) postępuj zgodnie z instrukcjami w temacie [Pobieranie konfiguracji raportowania elektronicznego z usługi Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span><span class="sxs-lookup"><span data-stu-id="05af3-127">For production and user acceptance testing (UAT) environments, follow the instructions in the topic, [Download Electronic reporting configurations from Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span></span>

<span data-ttu-id="05af3-128">Aby wygenerować deklaracje potrącenia podatku w egipskiej osobie prawnej, musisz przesłać następujące konfiguracje:</span><span class="sxs-lookup"><span data-stu-id="05af3-128">To generate the Withholding declarations in an Egyptian legal entity, you need to upload the following configurations:</span></span>

- <span data-ttu-id="05af3-129">Wersja pliku model.version.82.xml lub jego nowsza wersja</span><span class="sxs-lookup"><span data-stu-id="05af3-129">Tax declaration model.version.82.xml or later version</span></span>
- <span data-ttu-id="05af3-130">Wersja pliku mapping.version.82.133.xml lub jego nowsza wersja</span><span class="sxs-lookup"><span data-stu-id="05af3-130">Tax declaration model mapping.version.82.133.xml or a later version</span></span>
- <span data-ttu-id="05af3-131">Deklaracja WHT Excel (EG).version.82.21 lub nowsza wersja</span><span class="sxs-lookup"><span data-stu-id="05af3-131">WHT Declaration Excel (EG).version.82.21  or a later version</span></span>

<span data-ttu-id="05af3-132">Po pobraniu konfiguracji ER z usługi Lifecycle Services (LCS) lub repozytorium globalnego wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="05af3-132">After you finish downloading the ER configurations from Lifecycle Services (LCS) or the global repository, complete the following steps.</span></span>

1. <span data-ttu-id="05af3-133">W obszarze roboczym **Raportowanie elektroniczne** wybierz kafelek **Konfiguracje raportowania**.</span><span class="sxs-lookup"><span data-stu-id="05af3-133">Go to the **Electronic reporting** workspace and select the **Reporting configurations** tile.</span></span>
1. <span data-ttu-id="05af3-134">Na stronie **Konfiguracje**, w okienku akcji wybierz **Import/eksport > Załaduj z pliku XML**.</span><span class="sxs-lookup"><span data-stu-id="05af3-134">On the **Configurations** page, on the Action Pane, select **Exchange > Load from XML file**.</span></span>
1. <span data-ttu-id="05af3-135">Przekaż wszystkie pliki w kolejności, w jakiej są one wymienione w poprzednich plikach.</span><span class="sxs-lookup"><span data-stu-id="05af3-135">Upload all the files in the order in which they are listed in the previous bullets.</span></span> <span data-ttu-id="05af3-136">Po przekazaniu wszystkich konfiguracji drzewo konfiguracji powinno być obecne w Finance.</span><span class="sxs-lookup"><span data-stu-id="05af3-136">After all of the configurations are uploaded, the configuration tree should be present in Finance.</span></span>

## <a name="set-up-application-specific-parameters"></a><span data-ttu-id="05af3-137">Konfigurowanie parametrów specyficznych dla aplikacji</span><span class="sxs-lookup"><span data-stu-id="05af3-137">Set up application-specific parameters</span></span>

<span data-ttu-id="05af3-138">Opcja parametrów specyficznych dla aplikacji umożliwia użytkownikom określenie kryteriów klasyfikacji i obliczania transakcji podatkowych w każdym wierszu generowanego raportu, w zależności od konfiguracji **grupy pozycji potrąconej zaliczki na podatek** lub innych kryteriów określonych w definicji wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="05af3-138">The application-specific parameters option lets users establish the criteria of how the tax transactions will be classified and calculated in each line of a generated report depending on the configuration of **withholding tax item group** or other criteria established in the definition of lookup.</span></span>

<span data-ttu-id="05af3-139">Formularz 41 deklaracji potrąconej zaliczki na podatek zawiera określoną kolumnę, w której transakcja potrąconej zaliczki na podatek musi zostać sklasyfikowana zgodnie z klasyfikacją urzędu skarbowego o nazwie **Typ kodu rabatu**.</span><span class="sxs-lookup"><span data-stu-id="05af3-139">Withholding declaration form 41 includes a specific column where the withholding tax transaction must be classified in accordance with the tax authority classification named **Discount code type**.</span></span> <span data-ttu-id="05af3-140">Zamiast ująć te nowe klasyfikacje jako nowe dane wprowadzania podczas księgowania transakcji, klasyfikacje będą ustalane na podstawie różnych wyszukiwania wprowadzonych w **Konfiguracje** > **Konfigurowanie parametrów specyficznych dla aplikacji** > **Konfiguracja**, aby spełnić wymagania zgłaszania zaliczki w Egipcie.</span><span class="sxs-lookup"><span data-stu-id="05af3-140">Instead of including these new classifications as new entry data when the transactions are posted, the classifications will be determined based on the different lookups introduced in **Configurations** > **Set up application-specific parameters** > **Setup** to meet the requirements of withholding reports for Egypt.</span></span> 

<span data-ttu-id="05af3-141">Następująca konfiguracja służy do klasyfikowania transakcji w raporcie Deklaracja potrąconej zaliczki na podatek 41:</span><span class="sxs-lookup"><span data-stu-id="05af3-141">The following configuration is used to classify the transactions in the Withholding declaration form 41 report:</span></span>

- <span data-ttu-id="05af3-142">**DiscountTaxTypeLookup** -> Kolumna nr 18</span><span class="sxs-lookup"><span data-stu-id="05af3-142">**DiscountTaxTypeLookup**-> Column No 18</span></span> 

<span data-ttu-id="05af3-143">Wykonaj następujące kroki, aby skonfigurować różne wyszukiwania używane do generowania deklaracji WHT i powiązanych raportów księgowych.</span><span class="sxs-lookup"><span data-stu-id="05af3-143">Complete the following steps to set up the different lookups used to generate the WHT declaration and related books reports.</span></span> 

1. <span data-ttu-id="05af3-144">W obszarze roboczym **Raportowanie elektroniczne** wybierz **Konfiguracje** > **Konfiguracja**, aby skonfigurować zasady określania, w jaki sposób transakcje są klasyfikowane w raporcie deklaracji WHT.</span><span class="sxs-lookup"><span data-stu-id="05af3-144">In the **Electronic reporting** workspace, select **Configurations** > **Setup** to set up the rules to identify how transactions are classified in the WHT declaration report.</span></span> 
2. <span data-ttu-id="05af3-145">Wybierz bieżącą wersję, a na skróconej karcie **Wyszukiwania** wybierz nazwę wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="05af3-145">Select the current version, and on the **Lookups** FastTab, select the lookup name.</span></span> <span data-ttu-id="05af3-146">Na przykład **DiscountTaxTypeLookup**.</span><span class="sxs-lookup"><span data-stu-id="05af3-146">For example, **DiscountTaxTypeLookup**.</span></span> <span data-ttu-id="05af3-147">To wyszukiwania identyfikują listę typów rabatów wymaganych przez urząd skarbowy.</span><span class="sxs-lookup"><span data-stu-id="05af3-147">This lookup identifies the list of discount types required by the tax authority.</span></span>
3. <span data-ttu-id="05af3-148">Na skróconej karcie **Warunki** wybierz pozycję **Dodaj**, a w nowym wierszu w kolumnie **Wynik wyszukiwania** zaznacz powiązany wiersz reprezentujący klasyfikację w **Kolumnie 18**.</span><span class="sxs-lookup"><span data-stu-id="05af3-148">On the **Conditions** FastTab, select **Add** and in the new line in the **Lookup result** column, select the related line that represents the classification in the **Column 18**.</span></span>
4. <span data-ttu-id="05af3-149">W kolumnie **Grupa pozycji podatku u źródła** wybierz powiązany kod, który jest używany do identyfikacji klasyfikacji.</span><span class="sxs-lookup"><span data-stu-id="05af3-149">In the **Withholding tax item group** column, select the related code that's used to identify the classification.</span></span> <span data-ttu-id="05af3-150">Na przykład **Dozwolony rabat**.</span><span class="sxs-lookup"><span data-stu-id="05af3-150">For example, **Allowed discount**.</span></span>  
5. <span data-ttu-id="05af3-151">Powtórz kroki 3 i 4 dla wszystkich dostępnych wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="05af3-151">Repeat steps 3 and 4 for all available lookups.</span></span>
6. <span data-ttu-id="05af3-152">Wybierz znowu opcję **Dodaj**, aby uwzględnić ostateczny wiersz rekordu, a następnie w kolumnie **Wynik wyszukiwania** wybierz opcję **Nie dotyczy**.</span><span class="sxs-lookup"><span data-stu-id="05af3-152">Select **Add** again to include the final record line, and in the **Lookup result** column, select **Not applicable**.</span></span> 
7. <span data-ttu-id="05af3-153">W kolumnach pozostałych wybierz opcję **Niepuste**.</span><span class="sxs-lookup"><span data-stu-id="05af3-153">In the remaining columns, select **Not blank**.</span></span> 

> [!NOTE]

## <a name="set-up-general-ledger-parameters"></a><span data-ttu-id="05af3-154">Konfigurowanie parametrów księgi głównej</span><span class="sxs-lookup"><span data-stu-id="05af3-154">Set up General ledger parameters</span></span>

<span data-ttu-id="05af3-155">Aby wygenerować raporty formularza deklaracji WHT w formacie Microsoft Excel, zdefiniuj format raportu elektronicznego na stronie **Parametry księgi głównej**.</span><span class="sxs-lookup"><span data-stu-id="05af3-155">To generate the WHT declaration form reports in Microsoft Excel, define an ER format on the **General ledger parameters** page.</span></span>

1. <span data-ttu-id="05af3-156">Wybierz kolejno opcje **Podatek** > **Ustawienia** > **Parametry księgi głównej**.</span><span class="sxs-lookup"><span data-stu-id="05af3-156">Go to **Tax** > **Setup** > **General ledger parameters**.</span></span>
2. <span data-ttu-id="05af3-157">Na karcie **Potrącona zaliczka** na podatek w polu **Mapowanie formatu deklaracji WHT** wybierz pozycję **Deklaracja WHT Excel (EG)**.</span><span class="sxs-lookup"><span data-stu-id="05af3-157">On the **Withholding tax** tab, in the **WHT declaration format mapping** field, select **WHT Declaration Excel (EG)**.</span></span> <span data-ttu-id="05af3-158">Jeśli pole to jest puste, standardowy raport podatku zostanie wygenerowany w formacie SSRS.</span><span class="sxs-lookup"><span data-stu-id="05af3-158">If you leave the field blank, the standard sales tax report will be generated in SSRS format.</span></span>


![Formularz deklaracji](media/egypt-wht-declaration-setup1.png)

## <a name="generate-the-withholding-declaration-forms"></a><span data-ttu-id="05af3-160">Generowanie formularzy deklaracji potrąconej zaliczki na podatek</span><span class="sxs-lookup"><span data-stu-id="05af3-160">Generate the Withholding declaration forms</span></span>
<span data-ttu-id="05af3-161">Proces przygotowywania i przesyłania formularza deklaracji potrąconej zaliczki na podatek dla określonego okresu jest oparty na transakcjach potrącenia zaliczki na podatek zaksięgowanych podczas zadania rozliczania i księgowania podatku od płatności.</span><span class="sxs-lookup"><span data-stu-id="05af3-161">The process of preparing and submitting a Withholding declaration form for a specific period is based on the withholding tax transactions posted during the settle and post payment tax job.</span></span> <span data-ttu-id="05af3-162">Aby uzyskać więcej informacji na temat globalnej potrąconej zaliczki na podatek, zobacz [Globalna potrącona zaliczka na podatek](../general-ledger/global-withholding-tax-overview.md).</span><span class="sxs-lookup"><span data-stu-id="05af3-162">For more information about global withholding tax, see [Global withholding tax](../general-ledger/global-withholding-tax-overview.md).</span></span>

<span data-ttu-id="05af3-163">Aby wygenerować raport deklaracji podatkowej, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="05af3-163">Complete the following steps to generate the tax declaration report.</span></span>

1. <span data-ttu-id="05af3-164">Przejdź do **Podatek** > **Deklaracje** > **Zaliczka na podatek** > \**Płatność zaliczki na podatek*.</span><span class="sxs-lookup"><span data-stu-id="05af3-164">Go to **Tax** > **Declarations** > **Withholding tax** > \**Withholding tax payment*.</span></span>
2. <span data-ttu-id="05af3-165">Wybierz okres rozliczeniowy, a następnie datę rozpoczęcia dla raportu.</span><span class="sxs-lookup"><span data-stu-id="05af3-165">Select the settlement period and then select the from date for the report.</span></span> 
3. <span data-ttu-id="05af3-166">Wprowadź datę transakcji, a następnie wybierz opcję **OK**.</span><span class="sxs-lookup"><span data-stu-id="05af3-166">Enter the transaction date and then select **OK**.</span></span>
4. <span data-ttu-id="05af3-167">W otwieraowym oknie dialogowym wybierz jeden lub więcej typów formularzy \*\*Formularz nr 41 \*\*, **Formularz nr 11** lub **Brak**.</span><span class="sxs-lookup"><span data-stu-id="05af3-167">In the dialog box that opens, select one or more of the form types \*\*Form No 41 \*\*, **Form No 11**, or **None**.</span></span> <span data-ttu-id="05af3-168">W przypadku wybrania opcji **Brak** zostanie wygenerowany raport standardowy.</span><span class="sxs-lookup"><span data-stu-id="05af3-168">If you select **None**, the standard report is generated.</span></span> 
5. <span data-ttu-id="05af3-169">Wybierz język.</span><span class="sxs-lookup"><span data-stu-id="05af3-169">Select the language.</span></span> <span data-ttu-id="05af3-170">Wszystkie raporty są tłumaczone w języku **en-us** i **ar-eg**.</span><span class="sxs-lookup"><span data-stu-id="05af3-170">All reports are translated in **en-us** and **ar-eg**.</span></span>
6. <span data-ttu-id="05af3-171">Wprowadź oddział i nazwę banku, w którym zostanie zapłacony podatek.</span><span class="sxs-lookup"><span data-stu-id="05af3-171">Enter the branch and name of the bank where the tax payment will be paid.</span></span>
7. <span data-ttu-id="05af3-172">Wybierz typ biznesowy, a następnie wprowadź czek i numery dokumentów.</span><span class="sxs-lookup"><span data-stu-id="05af3-172">Select the business type and then enter the check and document numbers.</span></span> 
8. <span data-ttu-id="05af3-173">Wprowadź typ jednostki.</span><span class="sxs-lookup"><span data-stu-id="05af3-173">Enter the entity type.</span></span> 
9. <span data-ttu-id="05af3-174">Wprowadź nazwisko zarejestrowanej osoby w celu przypisania formularza i wybierz **OK**, aby potwierdzić generowanie raportu.</span><span class="sxs-lookup"><span data-stu-id="05af3-174">Enter the name of person registered to assign the form and select **OK** to confirm the report generation.</span></span> 

 
[!INCLUDE[footer-include](../../includes/footer-banner.md)]
