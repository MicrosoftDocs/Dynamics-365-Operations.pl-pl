---
title: Umożliwia konfigurowanie parametrów formatu ER dla firmy
description: W tym temacie wyjaśniono, w jaki sposób można skonfigurować parametry formatu raportowania elektronicznego (ER) dla firmy.
author: NickSelin
manager: AnnBe
ms.date: 10/29/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERLookupDesigner, ERComponentLookupStructureEditing
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: Release 8.1.3
ms.openlocfilehash: b51a7ae8587a3cbb65efc4af574929efcbc8fbf8
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681479"
---
# <a name="set-up-the-parameters-of-an-er-format-per-legal-entity"></a><span data-ttu-id="a3f68-103">Umożliwia konfigurowanie parametrów formatu ER dla firmy</span><span class="sxs-lookup"><span data-stu-id="a3f68-103">Set up the parameters of an ER format per legal entity</span></span>

[!include[banner](../includes/banner.md)]

## <a name="prerequisites"></a><span data-ttu-id="a3f68-104">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="a3f68-104">Prerequisites</span></span>

<span data-ttu-id="a3f68-105">Aby wykonać te kroki, należy najpierw wykonać kroki w temacie [Skonfiguruj ER, aby używać parametrów określonych dla danej firmy](er-app-specific-parameters-configure-format.md).</span><span class="sxs-lookup"><span data-stu-id="a3f68-105">To complete these steps, you must first complete the steps in the [Configure ER formats to use parameters that are specified per legal entity](er-app-specific-parameters-configure-format.md) topic.</span></span>

<span data-ttu-id="a3f68-106">Aby wykonać przykłady opisane w tym temacie, trzeba mieć dostęp do rozwiązania Microsoft Dynamics 365 Finance (Finance) dla jednej z następujących ról:</span><span class="sxs-lookup"><span data-stu-id="a3f68-106">To complete the examples in this topic, you must have access to Microsoft Dynamics 365 Finance (Finance) for one of the following roles:</span></span>

- <span data-ttu-id="a3f68-107">Deweloper raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="a3f68-107">Electronic reporting developer</span></span>
- <span data-ttu-id="a3f68-108">Konsultant funkcjonalny raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="a3f68-108">Electronic reporting functional consultant</span></span>
- <span data-ttu-id="a3f68-109">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="a3f68-109">System administrator</span></span>

## <a name="import-er-configurations"></a><span data-ttu-id="a3f68-110">Importowanie konfiguracji ER</span><span class="sxs-lookup"><span data-stu-id="a3f68-110">Import ER configurations</span></span>

1.  <span data-ttu-id="a3f68-111">Zaloguj się do swojego środowiska.</span><span class="sxs-lookup"><span data-stu-id="a3f68-111">Sign in to your environment.</span></span>
2.  <span data-ttu-id="a3f68-112">Na domyślnym pulpicie nawigacyjnym wybierz opcję **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-112">On the default dashboard, select **Electronic reporting**.</span></span>
3.  <span data-ttu-id="a3f68-113">Wybierz **Raportowanie konfiguracji**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-113">Select **Reporting configurations**.</span></span>
4.  <span data-ttu-id="a3f68-114">Do bieżącej instancji modułu finanse są importowane konfiguracje, które zostały wyeksportowane z Regulatory Configuration Services (RCS) podczas wykonywania kroków w temacie [Skonfiguruj ER, aby używać parametrów określonych dla danej firmy](er-app-specific-parameters-configure-format.md).</span><span class="sxs-lookup"><span data-stu-id="a3f68-114">Import, into the current instance of Finance, the configurations that you exported from Regulatory Configuration Services (RCS) while you were completing the steps in the [Configure ER formats to use parameters that are specified per legal entity](er-app-specific-parameters-configure-format.md) topic.</span></span> <span data-ttu-id="a3f68-115">Należy wykonać następujące kroki dla każdej konfiguracji elektronicznego raportowania (ER) w następującej kolejności: model danych, mapowanie modelu i formaty.</span><span class="sxs-lookup"><span data-stu-id="a3f68-115">Follow these steps for each Electronic reporting (ER) configuration, in the following order: data model, model mapping, and formats.</span></span>

    1. <span data-ttu-id="a3f68-116">Wybierz **Import/eksport \> Załaduj z pliku XML**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-116">Select **Exchange \> Load from XML file**.</span></span>
    2. <span data-ttu-id="a3f68-117">Kliknij przycisk **Przeglądaj**, aby wybrać plik wymaganej konfiguracji ER w formacie XML.</span><span class="sxs-lookup"><span data-stu-id="a3f68-117">Select **Browse** to select the file for the required ER configuration in XML format.</span></span>
    3. <span data-ttu-id="a3f68-118">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-118">Select **OK**.</span></span>
    
    <span data-ttu-id="a3f68-119">Na poniższej ilustracji przedstawiono konfiguracje, które muszą zostać wykonane po zakończeniu pracy.</span><span class="sxs-lookup"><span data-stu-id="a3f68-119">The following illustration shows the configurations that you must have when you've finished.</span></span>

    ![Strona konfiguracji raportowania elektronicznego](./media/GER-AppSpecParms-ImportedConfigurations.PNG)

## <a name="set-up-parameters-for-the-demf-company"></a><span data-ttu-id="a3f68-121">Konfigurowanie parametrów dla firmy DEMF</span><span class="sxs-lookup"><span data-stu-id="a3f68-121">Set up parameters for the DEMF company</span></span>

<span data-ttu-id="a3f68-122">Strukturę ER można stosować do konfigurowania parametrów specyficznych dla aplikacji dla formatu ER.</span><span class="sxs-lookup"><span data-stu-id="a3f68-122">You can use the ER framework to set up application-specific parameters for an ER format.</span></span>

1.  <span data-ttu-id="a3f68-123">Wybierz firmę **DEMF**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-123">Select the **DEMF** legal entity.</span></span>
2.  <span data-ttu-id="a3f68-124">W drzewie konfiguracji wybierz **Format, aby uzyskać informacje o wyszukiwaniu danych LE**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-124">In the configurations tree, select the **Format to learn how to lookup LE data** format.</span></span>
3.  <span data-ttu-id="a3f68-125">W okienku akcji na karcie **Konfiguracje** w grupie **Parametry specyficzne dla aplikacji** wybierz opcję **Konfiguracja**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-125">On the Action Pane, on the **Configurations** tab, in the **Application specific parameters** group, select **Setup**.</span></span>

    ![Strona parametry specyficzne dla aplikacji ER](./media/GER-AppSpecParms-LookupForm.PNG)
    
    <span data-ttu-id="a3f68-127">Na stronie **parametry właściwe dla aplikacji** można skonfigurować **reguły** dotyczące źródła danych **formatu**, aby dowiedzieć się, jak wyszukać format danych LE.</span><span class="sxs-lookup"><span data-stu-id="a3f68-127">On the **Application specific parameters** page, you can configure the rules for the **Selector** data source of the **Format to learn how to lookup LE data** format.</span></span>
    
    <span data-ttu-id="a3f68-128">Jeśli podstawowy format ER będzie zawierał kilka źródeł danych typu **wyszukiwania**, przed rozpoczęciem konfigurowania reguły dla źródła danych należy wybrać żądane źródło danych na skróconej karcie **wyszukiwania**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-128">If the base ER format will contain several data sources of the **Lookup** type, you must select the desired data source on the **Lookups** FastTab before you can start to configure the set of rules for the data source.</span></span>
    
    <span data-ttu-id="a3f68-129">Dla każdego źródła danych można skonfigurować oddzielne reguły dla każdej wersji wybranego formatu ER.</span><span class="sxs-lookup"><span data-stu-id="a3f68-129">For each data source, you can configure separate rules for each version of the selected ER format.</span></span>
    
    <span data-ttu-id="a3f68-130">Cały zbiór reguł dla wszystkich źródeł danych wyszukiwania, które są dostępne w wybranej wersji podstawowego formatu modelu ER, tworzy parametry specyficzne dla aplikacji dla formatu ER.</span><span class="sxs-lookup"><span data-stu-id="a3f68-130">The whole set of rules for all lookup data sources that are available in the selected version of the base ER format makes up the application-specific parameters for the ER format.</span></span>

4.  <span data-ttu-id="a3f68-131">Wybierz wersję **1.1.1** formatu ER.</span><span class="sxs-lookup"><span data-stu-id="a3f68-131">Select version **1.1.1** of the ER format.</span></span>
5.  <span data-ttu-id="a3f68-132">Na skróconej karcie **Warunki** wybierz pozycję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-132">On the **Conditions** FastTab, select **Add**.</span></span>
6.  <span data-ttu-id="a3f68-133">W polu **Kod** w nowym rekordzie i wybierz strzałkę rozwijaną, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="a3f68-133">In the **Code** field of the new record, select the drop-down arrow to open the lookup.</span></span>

    <span data-ttu-id="a3f68-134">W wyszukiwaniu zostanie wystawiona lista kodów podatku do wybrania.</span><span class="sxs-lookup"><span data-stu-id="a3f68-134">The lookup presents the list of tax codes for selection.</span></span> <span data-ttu-id="a3f68-135">Ta lista jest zwracana przez **Model.Data.Tax** źródło danych podatkowych skonfigurowane w podstawowym formacie ER.</span><span class="sxs-lookup"><span data-stu-id="a3f68-135">This list is returned by the **Model.Data.Tax** data source that has been configured in the base ER format.</span></span> <span data-ttu-id="a3f68-136">Ponieważ to źródło danych zawiera pole **nazwa**, nazwa każdego kodu podatku jest wyświetlana w wyszukiwaniu.</span><span class="sxs-lookup"><span data-stu-id="a3f68-136">Because this data source contains the **Name** field, the name of each tax code appears in the lookup.</span></span>

    ![Strona parametry specyficzne dla aplikacji ER](./media/GER-AppSpecParms-LookupForm-CodeFldPicker.PNG)
    
7.  <span data-ttu-id="a3f68-138">Wybierz kod podatku **VAT19**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-138">Select the **VAT19** tax code.</span></span>
8.  <span data-ttu-id="a3f68-139">W polu **Wynik wyszukiwania** w nowym rekordzie i wybierz strzałkę rozwijaną, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="a3f68-139">In the **Lookup result** field of the new record, select the drop-down arrow to open the lookup.</span></span> <span data-ttu-id="a3f68-140">W wyszukiwaniu zostanie wystawiona lista wartości dla wyliczenia formatu TaxationLevel do wybrania.</span><span class="sxs-lookup"><span data-stu-id="a3f68-140">The lookup presents the list of values for the TaxationLevel format enumeration for selection.</span></span>

    <span data-ttu-id="a3f68-141">Należy zauważyć, że jeśli jako preferowany język użytkownika, do którego użytkownik jest zalogowany, jest wybrana jako niemiecki, etykiety wartości w wyszukiwaniu będą w języku niemieckim, pod warunkiem, że zostały przetłumaczone w podstawowym formacie ER.</span><span class="sxs-lookup"><span data-stu-id="a3f68-141">Note that, if German is selected as the preferred language of the user that you're signed in as, the labels of the values in the lookup will be in German, provided that they have been translated in the base ER format.</span></span> <span data-ttu-id="a3f68-142">Ponadto, jeśli etykieta źródła danych wyszukiwania została przetłumaczona, etykieta zostanie wyświetlona w preferowanym języku użytkownika na karcie **wyszukiwania**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-142">Additionally, if the label of a lookup data source has been translated, that label will appear in the user's preferred language on the **Lookups** tab.</span></span>

    ![Strona parametry specyficzne dla aplikacji ER](./media/GER-AppSpecParms-LookupForm-LookupFldPicker.PNG)

9.  <span data-ttu-id="a3f68-144">Umożliwia wybór wartości **zwykłego opodatkowania**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-144">Select the **Regular taxation** value.</span></span>

    <span data-ttu-id="a3f68-145">Dodając ten rekord, należy zdefiniować następującą regułę: ilekroć jest wymagane źródło danych wyszukiwania **reguły**, a kod podatku **VAT19** jest przekazywany jako argument, **zwykłe opodatkowanie** zostanie zwrócony jako żądany poziom opodatkowania.</span><span class="sxs-lookup"><span data-stu-id="a3f68-145">By adding this record, you define the following rule: Whenever the **Selector** lookup data source is requested, and the **VAT19** tax code is passed as an argument, **Regular taxation** will be returned as the requested taxation level.</span></span>

10. <span data-ttu-id="a3f68-146">Wybierz opcję **Dodaj**, a następnie wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="a3f68-146">Select **Add**, and then follow these steps:</span></span>

    1. <span data-ttu-id="a3f68-147">W polu **Kod** wybierz kod **InVAT19**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-147">In the **Code** field, select the **InVAT19** tax code.</span></span>
    2. <span data-ttu-id="a3f68-148">W polu **wynik wyszukiwania** wybierz wartość **zwykłe opodatkowanie**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-148">In the **Lookup result** field, select the **Regular taxation** value.</span></span>
    
11. <span data-ttu-id="a3f68-149">Wybierz znowu opcję **Dodaj**, a następnie wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="a3f68-149">Select **Add** again, and then follow these steps:</span></span>

    1. <span data-ttu-id="a3f68-150">W polu **Kod** wybierz kod **VAT7**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-150">In the **Code** field, select the **VAT7** tax code.</span></span>
    2. <span data-ttu-id="a3f68-151">W polu **wynik wyszukiwania** wybierz wartość **obniżone opodatkowanie**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-151">In the **Lookup result** field, select the **Reduced taxation** value.</span></span>
    
12. <span data-ttu-id="a3f68-152">Wybierz znowu opcję **Dodaj**, a następnie wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="a3f68-152">Select **Add** again, and then follow these steps:</span></span>

    1. <span data-ttu-id="a3f68-153">W polu **Kod** wybierz kod **InVAT7**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-153">In the **Code** field, select the **InVAT7** tax code.</span></span>
    2. <span data-ttu-id="a3f68-154">W polu **wynik wyszukiwania** wybierz wartość **obniżone opodatkowanie**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-154">In the **Lookup result** field, select the **Reduced taxation** value.</span></span>
    
13. <span data-ttu-id="a3f68-155">Wybierz znowu opcję **Dodaj**, a następnie wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="a3f68-155">Select **Add** again, and then follow these steps:</span></span>

    1. <span data-ttu-id="a3f68-156">W polu **Kod** wybierz kod **THIRD**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-156">In the **Code** field, select the **THIRD** tax code.</span></span>
    2. <span data-ttu-id="a3f68-157">W polu **wynik wyszukiwania** wybierz wartość **brak opodatkowania**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-157">In the **Lookup result** field, select the **No taxation** value.</span></span>
    
14. <span data-ttu-id="a3f68-158">Wybierz znowu opcję **Dodaj**, a następnie wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="a3f68-158">Select **Add** again, and then follow these steps:</span></span>

    1. <span data-ttu-id="a3f68-159">W polu **Kod** wybierz kod **InVAT0**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-159">In the **Code** field, select the **InVAT0** tax code.</span></span>
    2. <span data-ttu-id="a3f68-160">W polu **wynik wyszukiwania** wybierz wartość **brak opodatkowania**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-160">In the **Lookup result** field, select the **No taxation** value.</span></span>
    
15. <span data-ttu-id="a3f68-161">Wybierz znowu opcję **Dodaj**, a następnie wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="a3f68-161">Select **Add** again, and then follow these steps:</span></span>

    1. <span data-ttu-id="a3f68-162">W polu **kod** wybierz opcję **\*Nie pusty\***.</span><span class="sxs-lookup"><span data-stu-id="a3f68-162">In the **Code** field, select the **\*Not blank\*** option.</span></span>
    2. <span data-ttu-id="a3f68-163">W polu **wynik wyszukiwania** wybierz wartość **Inne opodatkowanie**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-163">In the **Lookup result** field, select the **Other** value.</span></span>
    
    <span data-ttu-id="a3f68-164">Dodając ostatni rekord, należy zdefiniować następującą regułę: Ilekroć kod podatkowy przekazany jako argument nie spełnia żadnej z poprzednich reguł, źródło danych odnośnika zwróci **Inne** jako żądany poziom opodatkowania.</span><span class="sxs-lookup"><span data-stu-id="a3f68-164">By adding this last record, you define the following rule: Whenever the tax code that is passed as an argument doesn't satisfy any of the previous rules, the lookup data source will return **Other** as the requested taxation level.</span></span>

    ![Strona parametry specyficzne dla aplikacji ER](./media/GER-AppSpecParms-LookupForm-RulesSet.PNG)
    
16. <span data-ttu-id="a3f68-166">W polu **Stan** wybierz opcję **ukończone**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-166">In the **State** field, select **Completed**.</span></span>

    <span data-ttu-id="a3f68-167">Jeśli zostanie uruchomiona wersja formatu ER o stanie **ukończona** lub **udostępniona**, ten zbiór reguł musi być w stanie **ukończone**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-167">When you run an ER format version that has a status of either **Completed** or **Shared**, this set of rules must be in the **Completed** state.</span></span> <span data-ttu-id="a3f68-168">W przeciwnym razie wykonanie podstawowego formatu ER zostanie przerwane, jeśli format będzie próbował załadować dane z tego zbioru reguł podczas uruchamiania źródła danych wyszukiwania **reguły**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-168">Otherwise, execution of the base ER format will be interrupted when the format tries to load data from this set of rules while the **Selector** lookup data source is being run.</span></span>
    
    <span data-ttu-id="a3f68-169">Po uruchomieniu wersji formatu ER o stanie **wersja robocza**, podstawowy format ER może uzyskać dostęp do tego zbioru reguł niezależnie od jego stanu.</span><span class="sxs-lookup"><span data-stu-id="a3f68-169">When you run an ER format version that has a status of **Draft**, the base ER format can access this set of rules, regardless of its state.</span></span>
    
17. <span data-ttu-id="a3f68-170">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-170">Select **Save**.</span></span>
18. <span data-ttu-id="a3f68-171">Zamknij stronę **Parametry specyficzne dla aplikacji**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-171">Close the **Application specific parameters** page.</span></span>

## <a name="run-the-er-format-in-the-demf-company"></a><span data-ttu-id="a3f68-172">Uruchom format ER w firmie DEMF</span><span class="sxs-lookup"><span data-stu-id="a3f68-172">Run the ER format in the DEMF company</span></span>

1.  <span data-ttu-id="a3f68-173">W drzewie konfiguracji wybierz **Format, aby uzyskać informacje o wyszukiwaniu danych LE**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-173">In the configurations tree, select the **Format to learn how to lookup LE data** format.</span></span>
2.  <span data-ttu-id="a3f68-174">W okienku akcji wybierz opcję **Uruchom**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-174">On the Action Pane, select **Run**.</span></span>
3.  <span data-ttu-id="a3f68-175">W oknie dialogowym wybierz **Ok**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-175">In the dialog box that appears, select **OK**.</span></span>
4.  <span data-ttu-id="a3f68-176">Pobierz wygenerowane zestawienia i umieść je lokalnie.</span><span class="sxs-lookup"><span data-stu-id="a3f68-176">Download the statement that is generated and store it locally.</span></span>

    <span data-ttu-id="a3f68-177">W wygenerowanym zestawieniu należy zauważyć, że podsumowanie kodu podatku **InVAT7** zostało umieszczone na poziomie **Obniżony**, a podsumowania kodów podatków **VAT19** i **InVA19** zostały umieszczone na poziomie **zwykłe**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-177">In the generated statement, notice that the summary of the **InVAT7** tax code has been put on the **Reduced** level, and the summaries of the **VAT19** and **InVA19** tax codes have been put on the **Regular** level.</span></span> <span data-ttu-id="a3f68-178">Zachowanie to zależy od konfiguracji w zestawie reguł zależnych od firmy.</span><span class="sxs-lookup"><span data-stu-id="a3f68-178">This behavior is determined by the configuration in the legal entity–dependent set of rules.</span></span>
    
5.  <span data-ttu-id="a3f68-179">Wybierz kolejno opcje **Podatek \> Podatki pośrednie \> Podatek \> Kody podatków**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-179">Go to **Tax \> Indirect taxes \> Sales tax \> Sales tax codes**.</span></span>
6.  <span data-ttu-id="a3f68-180">Wybierz kod podatku **InVAT7**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-180">Select the **InVAT7** tax code.</span></span>
7.  <span data-ttu-id="a3f68-181">W okienku akcji, na karcie **kod podatku,** w grupie **informacje** wybierz opcję **zaksięgowany podatek**, aby wyświetlić informacje o wartościach podatku i zastosowaniu stawki podatkowej według kodu podatku.</span><span class="sxs-lookup"><span data-stu-id="a3f68-181">On the Action Pane, on the **Sales tax code** tab, in the **Inquiries** group, select **Posted sales tax** to view information about the tax value and applied tax rate per tax code.</span></span>

    ![Strona zaksięgowany podatek](./media/GER-AppSpecParms-Statement.PNG)

8.  <span data-ttu-id="a3f68-183">Zamknij strony Zaksięgowany podatek.</span><span class="sxs-lookup"><span data-stu-id="a3f68-183">Close the Posted sales tax page.</span></span>

## <a name="set-up-parameters-for-the-usmf-company"></a><span data-ttu-id="a3f68-184">Konfigurowanie parametrów dla firmy USMF</span><span class="sxs-lookup"><span data-stu-id="a3f68-184">Set up parameters for the USMF company</span></span>

1.  <span data-ttu-id="a3f68-185">Wybierz firmę **USMF**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-185">Select the **USMF** legal entity.</span></span>
2.  <span data-ttu-id="a3f68-186">Przejdź do opcji **Administrowanie organizacją \> Raporty elektroniczne \> Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-186">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
3.  <span data-ttu-id="a3f68-187">W drzewie konfiguracje rozwiń **Model do nauczenia sparametryzowanych wywoływań**, rozwiń **Format do nauczania sparametryzowanych wywołań**, a następnie wybierz **Format do nauczania wyszukiwania danych LE**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-187">In the configurations tree, expand the **Model to learn parameterized calls** item, expand the **Format to learn parameterized calls** item, and select the **Format to learn how to lookup LE data** format.</span></span>
4.  <span data-ttu-id="a3f68-188">W okienku akcji na karcie **Konfiguracje** w grupie **Parametry specyficzne dla aplikacji** wybierz opcję **Konfiguracja**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-188">On the Action Pane, on the **Configurations** tab, in the **Application specific parameters** group, select **Setup**.</span></span>
5.  <span data-ttu-id="a3f68-189">Wybierz wersję **1.1.1** wybranego formatu ER.</span><span class="sxs-lookup"><span data-stu-id="a3f68-189">Select version **1.1.1** of the selected ER format.</span></span>
6.  <span data-ttu-id="a3f68-190">Na skróconej karcie **Warunki** wybierz pozycję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-190">On the **Conditions** FastTab, select **Add**.</span></span>
7.  <span data-ttu-id="a3f68-191">W polu **Kod** w nowym rekordzie i wybierz strzałkę rozwijaną, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="a3f68-191">In the **Code** field of the new record, select the drop-down arrow to open the lookup.</span></span>

    <span data-ttu-id="a3f68-192">W wyszukiwaniu zostanie wystawiona lista kodów podatków do wybrania dla podatku firmy **USMF**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-192">The lookup now presents the list of tax codes for the **USMF** company tax for selection.</span></span>

    ![Strona parametry specyficzne dla aplikacji ER](./media/GER-AppSpecParms-LookupForm-CodeFldPicker2.PNG)
    
8.  <span data-ttu-id="a3f68-194">Wybierz kod podatku **EXEMPT**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-194">Select the **EXEMPT** tax code.</span></span>
9.  <span data-ttu-id="a3f68-195">W polu **wynik wyszukiwania w nowym rekordzie** wybierz wartość **Brak opodatkowania**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-195">In the **Lookup resul** t field of the new record, select the **No taxation** value.</span></span>
10. <span data-ttu-id="a3f68-196">Wybierz ponownie przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-196">Select **Add** again.</span></span>
11. <span data-ttu-id="a3f68-197">W polu **kod** nowego rekordu wybierz opcję **\*Nie pusty\***.</span><span class="sxs-lookup"><span data-stu-id="a3f68-197">In the **Code** field of the new record, select the **\*Not blank\*** option.</span></span>
12. <span data-ttu-id="a3f68-198">W polu **wynik wyszukiwania** w nowym rekordzie wybierz wartość **Zwykłe opodatkowanie**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-198">In the **Lookup result** field of the new record, select the **Regular taxation** value.</span></span>
13. <span data-ttu-id="a3f68-199">W polu **Stan** wybierz opcję **ukończone**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-199">In the **State** field, select **Completed**.</span></span>
14. <span data-ttu-id="a3f68-200">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-200">Select **Save**.</span></span>

    ![Strona parametry specyficzne dla aplikacji ER](./media/GER-AppSpecParms-LookupForm-RulesSet2.PNG)
    
15. <span data-ttu-id="a3f68-202">Zamknij stronę **Parametry specyficzne dla aplikacji**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-202">Close the **Application specific parameters** page.</span></span>

## <a name="run-the-er-format-in-the-usmf-company"></a><span data-ttu-id="a3f68-203">Uruchom format ER w firmie USMF</span><span class="sxs-lookup"><span data-stu-id="a3f68-203">Run the ER format in the USMF company</span></span>

1.  <span data-ttu-id="a3f68-204">W drzewie konfiguracji wybierz **Format, aby uzyskać informacje o wyszukiwaniu danych LE**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-204">In the configurations tree, select the **Format to learn how to lookup LE data** format.</span></span>
2.  <span data-ttu-id="a3f68-205">W okienku akcji wybierz opcję **Uruchom**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-205">On the Action Pane, select **Run**.</span></span>
3.  <span data-ttu-id="a3f68-206">W oknie dialogowym wybierz **Ok**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-206">In the dialog box that appears, select **OK**.</span></span>
4.  <span data-ttu-id="a3f68-207">Pobierz wygenerowane zestawienia i umieść je lokalnie.</span><span class="sxs-lookup"><span data-stu-id="a3f68-207">Download the statement that is generated and store it locally.</span></span>

    <span data-ttu-id="a3f68-208">W wygenerowanym wyciągu należy zauważyć, że teraz ponownie użyto tego samego formatu ER dla innej firmy, ale bez wprowadzania jakichkolwiek zmian w formacie ER.</span><span class="sxs-lookup"><span data-stu-id="a3f68-208">In the generated statement, notice that you've now reused the same ER format for a different legal entity, but without making any adjustments to the ER format.</span></span>

## <a name="reuse-legal-entitydependent-parameters"></a><span data-ttu-id="a3f68-209">Ponowne użycie podmiotu prawnego — parametry zależne</span><span class="sxs-lookup"><span data-stu-id="a3f68-209">Reuse legal entity–dependent parameters</span></span>

### <a name="export-parameters"></a><span data-ttu-id="a3f68-210">Parametry eksportu</span><span class="sxs-lookup"><span data-stu-id="a3f68-210">Export parameters</span></span>

1.  <span data-ttu-id="a3f68-211">Wybierz kolejno opcje **Administrowanie organizacją \> Obszary robocze \> Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-211">Go to **Organization administration \> Workspaces \> Electronic reporting**.</span></span>
2.  <span data-ttu-id="a3f68-212">Wybierz **Raportowanie konfiguracji**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-212">Select **Reporting configurations**.</span></span>
3.  <span data-ttu-id="a3f68-213">W drzewie konfiguracji wybierz **Format, aby uzyskać informacje o wyszukiwaniu danych LE**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-213">In the configurations tree, select the **Format to learn how to lookup LE data** format.</span></span>
4.  <span data-ttu-id="a3f68-214">W okienku akcji na karcie **Konfiguracje** w grupie **Parametry specyficzne dla aplikacji** wybierz opcję **Konfiguracja**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-214">On the Action Pane, on the **Configurations** tab, in the **Application specific parameters** group, select **Setup**.</span></span>
5.  <span data-ttu-id="a3f68-215">Wybierz wersję **1.1.1** formatu ER.</span><span class="sxs-lookup"><span data-stu-id="a3f68-215">Select version **1.1.1** of the ER format.</span></span>
6.  <span data-ttu-id="a3f68-216">W okienku akcji wybierz pozycję **Eksportuj**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-216">On the Action Pane, select **Export**.</span></span>
7.  <span data-ttu-id="a3f68-217">Pobierz wygenerowane pliku i umieść je lokalnie.</span><span class="sxs-lookup"><span data-stu-id="a3f68-217">Download the file that is generated and store it locally.</span></span>

    <span data-ttu-id="a3f68-218">Skonfigurowany zbiór parametrów specyficznych dla aplikacji został teraz wyeksportowany jako plik XML.</span><span class="sxs-lookup"><span data-stu-id="a3f68-218">The configured set of application-specific parameters has now been exported as an XML file.</span></span>

### <a name="import-parameters"></a><span data-ttu-id="a3f68-219">Parametry importu</span><span class="sxs-lookup"><span data-stu-id="a3f68-219">Import parameters</span></span>

1.  <span data-ttu-id="a3f68-220">Wybierz wersję **1.1.2** formatu ER.</span><span class="sxs-lookup"><span data-stu-id="a3f68-220">Select version **1.1.2** of the ER format.</span></span>
2.  <span data-ttu-id="a3f68-221">W okienku akcji wybierz pozycję **Importuj**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-221">On the Action Pane, select **Import**.</span></span>
3.  <span data-ttu-id="a3f68-222">Wybierz **Tak**, aby potwierdzić zamiar zastąpienia istniejących parametrów specyficznych dla aplikacji dla tej wersji formatu.</span><span class="sxs-lookup"><span data-stu-id="a3f68-222">Select **Yes** to confirm that you want to override the existing application-specific parameters for this format version.</span></span>
4.  <span data-ttu-id="a3f68-223">Wybierz przycisk **Przeglądaj**, aby znaleźć plik zawierający wyeksportowane parametry właściwe dla aplikacji dla wersji **1.1.1**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-223">Select **Browse** to find the file that contains the exported application-specific parameters for version **1.1.1**.</span></span>
5.  <span data-ttu-id="a3f68-224">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-224">Select **OK**.</span></span>

    <span data-ttu-id="a3f68-225">Wersja **1.1.2** formatu ER zawiera teraz te same parametry właściwe dla aplikacji, które zostały pierwotnie skonfigurowane dla wersji **1.1.1**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-225">Version **1.1.2** of the ER format now has the same application-specific parameters that you originally configured for version **1.1.1**.</span></span>
    
    <span data-ttu-id="a3f68-226">Należy zauważyć, że parametry właściwe dla aplikacji w formacie ER są zależne od firmy.</span><span class="sxs-lookup"><span data-stu-id="a3f68-226">Note that the application-specific parameters of an ER format are legal entity–dependent.</span></span> <span data-ttu-id="a3f68-227">Aby ponownie użyć parametrów specyficznych dla aplikacji, które zostały skonfigurowane dla jednego podmiotu prawnego w innej firmie, należy je wyeksportować w pierwszej firmie, a następnie zaimportować po zalogowaniu się do innej firmy.</span><span class="sxs-lookup"><span data-stu-id="a3f68-227">To reuse the application-specific parameters that were configured for one legal entity in a different legal entity, you must export them while you're signed in to the first legal entity and then import them after you sign in to the other legal entity.</span></span>

    <span data-ttu-id="a3f68-228">Można również skorzystać z tej metody w celu przetransferowania parametrów formatu ER specyficznych dla aplikacji, które zostały pierwotnie skonfigurowane w jednym wystąpieniu Finance, do innego wystąpienia Finance.</span><span class="sxs-lookup"><span data-stu-id="a3f68-228">You can also use this approach to transfer an ER format related application-specific parameters that were originally configured in one instance of Finance to another instance of Finance.</span></span>

    <span data-ttu-id="a3f68-229">Należy pamiętać, że w przypadku konfigurowania parametrów specyficznych dla aplikacji dla jednej wersji formatu ER i importowania wyższej wersji tego samego formatu do bieżącego wystąpienia finansów, istniejące parametry specyficzne dla danej aplikacji nie będą stosowane dla wersji zaimportowanej.</span><span class="sxs-lookup"><span data-stu-id="a3f68-229">Be aware that if you configure application-specific parameters for one version of an ER format and import a higher version of the same format into the current Finance instance, the existing application-specific parameters won't be applied for the imported version.</span></span>
    
    <span data-ttu-id="a3f68-230">Należy również pamiętać, że po wybraniu pliku do zaimportowania struktura parametrów specyficznych dla aplikacji w tym pliku jest porównywana ze strukturą odpowiedniego źródła danych typu **wyszukiwania** w formacie ER, który został wybrany do importu.</span><span class="sxs-lookup"><span data-stu-id="a3f68-230">Also be aware that, when you select a file for import, the structure of the application-specific parameters in that file is compared with the structure of the corresponding data source of the **Lookup** type in the ER format that is selected for import.</span></span> <span data-ttu-id="a3f68-231">Import jest wykonywany, gdy struktura każdego parametru specyficznego dla aplikacji odpowiada strukturze odpowiedniego źródła danych w formacie ER wybranym do importu.</span><span class="sxs-lookup"><span data-stu-id="a3f68-231">The import is done when the structure of each application-specific parameter matches the structure of the corresponding data source in the ER format that is selected for import.</span></span> <span data-ttu-id="a3f68-232">Jeśli struktury nie są zgodne, zostanie wyświetlony komunikat ostrzegawczy informujący o tym, że nie można wykonać importu.</span><span class="sxs-lookup"><span data-stu-id="a3f68-232">If the structures don't match, you receive a warning message that states that the import can't be done.</span></span> <span data-ttu-id="a3f68-233">W przypadku wymuszenia importu, istniejące parametry specyficzne dla aplikacji dla wybranego formatu ER zostaną oczyszczone i należy je skonfigurować od początku.</span><span class="sxs-lookup"><span data-stu-id="a3f68-233">If you force the import to be done, the existing application-specific parameters for the selected ER format will be cleaned up, and you must set them up from the beginning.</span></span>

## <a name="relationship-between-application-specific-parameters-and-an-er-format"></a><span data-ttu-id="a3f68-234">Relacja między parametrami specyficznymi dla aplikacji a formatem ER</span><span class="sxs-lookup"><span data-stu-id="a3f68-234">Relationship between application-specific parameters and an ER format</span></span>

<span data-ttu-id="a3f68-235">Relacja między formatem ER a jego parametrami specyficznymi dla aplikacji jest ustalana na podstawie unikatowego kodu identyfikacyjnego w formacie obiektu ER.</span><span class="sxs-lookup"><span data-stu-id="a3f68-235">The relationship between an ER format and its application-specific parameters is established by the ER format's instance-independent unique identification code.</span></span> <span data-ttu-id="a3f68-236">Dlatego po usunięciu formatu ER z Finance, parametry właściwe dla aplikacji skonfigurowane dla formatu ER są przechowywane w bieżącym wystąpieniu Finance.</span><span class="sxs-lookup"><span data-stu-id="a3f68-236">Therefore, when you remove an ER format from Finance, the application-specific parameters that are configured for the ER format are kept in the current instance of Finance.</span></span> <span data-ttu-id="a3f68-237">Dostęp do nich jest możliwy po powrotnym zaimportowaniu podstawowego formatu ER do tego wystąpienia Finance.</span><span class="sxs-lookup"><span data-stu-id="a3f68-237">They can be accessed whenever the base ER format is reimported into this instance of Finance.</span></span>

## <a name="access-application-specific-parameters-by-using-the-er-framework"></a><span data-ttu-id="a3f68-238">Uzyskiwanie dostępu do parametrów specyficznych dla aplikacji przy użyciu struktury ER</span><span class="sxs-lookup"><span data-stu-id="a3f68-238">Access application-specific parameters by using the ER framework</span></span>

<span data-ttu-id="a3f68-239">W powyższym przykładzie uzyskano dostęp do parametrów specyficznych dla aplikacji w formacie ER przy użyciu struktury ER.</span><span class="sxs-lookup"><span data-stu-id="a3f68-239">In the preceding example, you have accessed application-specific parameters of an ER format by using the ER framework.</span></span> <span data-ttu-id="a3f68-240">Takie rozwiązanie nie pozwala na ograniczenie dostępu do parametrów specyficznych dla aplikacji w określonym formacie ER.</span><span class="sxs-lookup"><span data-stu-id="a3f68-240">This approach doesn't let you restrict access to the application-specific parameters of a specific ER format.</span></span> <span data-ttu-id="a3f68-241">Jeśli konieczne jest zastosowanie takich ograniczeń, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a3f68-241">If you must apply such restrictions, follow these steps.</span></span> 

1.  <span data-ttu-id="a3f68-242">Należy ponownie użyć istniejącego elementu menu **ERSolutionAppSpecificParametersDesigner** lub zaimplementować własny element menu **ERSolutionAppSpecificParametersDesigner**.</span><span class="sxs-lookup"><span data-stu-id="a3f68-242">Either reuse an existing **ERSolutionAppSpecificParametersDesigner** menu item, or implement your own **ERSolutionAppSpecificParametersDesigner** menu item.</span></span>

    ![Strona Visual Studio](./media/GER-AppSpecParms-LookupForm-Access1.PNG)
    
2.  <span data-ttu-id="a3f68-244">Wykonaj jeden z następujących kroków:</span><span class="sxs-lookup"><span data-stu-id="a3f68-244">Follow one of these steps:</span></span>

    1.  <span data-ttu-id="a3f68-245">Utwórz nowy przycisk elementu menu i połącz go z odpowiednim rekordem z tabeli **ERSolutionTable**, ustawiając właściwość **źródła danych** na **ERSolutionTable.**</span><span class="sxs-lookup"><span data-stu-id="a3f68-245">Create a new menu item button, and link it to the corresponding record from the **ERSolutionTable** table by setting its **Data Source** property to **ERSolutionTable**.</span></span>
    
        ![Strona Visual Studio](./media/GER-AppSpecParms-LookupForm-Access2.PNG)
        
    2.  <span data-ttu-id="a3f68-247">Utwórz prosty przycisk i Zastąp **klikniętą** metodę, tak jak to pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="a3f68-247">Create a simple button, and override the **Clicked** method as shown in the following example.</span></span>
    
        <span data-ttu-id="a3f68-248">Korzystając z tego podejścia, można określić unikatowy identyfikator rozwiązania (zdefiniowany za pomocą wartości **GUID**), aby umożliwić dostęp do parametrów specyficznych dla aplikacji w oddzielnym formacie ER i kopiach podrzędnych, które zostały z niego utworzone.</span><span class="sxs-lookup"><span data-stu-id="a3f68-248">By using this approach, you can specify a unique solution ID (defined via the **GUID** value) to allow access to the application-specific parameters of only a specific ER format and descendant copies that have been derived from it.</span></span>
        
        ```xpp
        public void clicked()
            {
                super();

                ERSolutionTable solutionTableRecord = ERSolutionTable::findByGUID(str2Guid('ADACCB2F-EFD1-4C90-877D-7E1E5D1AEE92'));

                Args args = new Args();
                args.record(solutionTableRecord);
                args.caller(this);

                new MenuFunction(menuItemDisplayStr(ERSolutionAppSpecificParametersDesigner), MenuItemType::Display)
                    .run(args);
            }
        ```

## <a name="additional-resources"></a><span data-ttu-id="a3f68-249">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="a3f68-249">Additional resources</span></span>

[<span data-ttu-id="a3f68-250">Projektant formuł w module Raportowanie elektroniczne</span><span class="sxs-lookup"><span data-stu-id="a3f68-250">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="a3f68-251">Skonfiguruj formaty ER do używania parametrów określonych dla firmy</span><span class="sxs-lookup"><span data-stu-id="a3f68-251">Configure ER formats to use parameters that are specified per legal entity</span></span>](er-app-specific-parameters-configure-format.md)
