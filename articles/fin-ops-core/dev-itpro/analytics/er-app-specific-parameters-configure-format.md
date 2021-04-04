---
title: Skonfiguruj formaty ER do używania parametrów określonych dla firmy
description: W tym temacie wyjaśniono, w jaki sposób można skonfigurować format raportowania elektronicznego (ER) do używania z określonymi dla firmy parametrami.
author: NickSelin
manager: AnnBe
ms.date: 10/26/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 9253191f9cd10e0b3c87d61991598f9b791c35d9
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570741"
---
# <a name="configure-er-formats-to-use-parameters-that-are-specified-per-legal-entity"></a><span data-ttu-id="36812-103">Skonfiguruj formaty ER do używania parametrów określonych dla firmy</span><span class="sxs-lookup"><span data-stu-id="36812-103">Configure ER formats to use parameters that are specified per legal entity</span></span>

[!include[banner](../includes/banner.md)]

## <a name="overview"></a><span data-ttu-id="36812-104">Omówienie</span><span class="sxs-lookup"><span data-stu-id="36812-104">Overview</span></span>

<span data-ttu-id="36812-105">W wielu formatach elektronicznego raportowania (ER), które należy zaprojektować, należy filtrować dane przy użyciu zbioru wartości, które są właściwe dla poszczególnych firm danego wystąpienia (np. zestawy kodów podatków do filtrowania transakcji podatkowych).</span><span class="sxs-lookup"><span data-stu-id="36812-105">In many of the Electronic reporting (ER) formats that you will design, you must filter data by using a set of values that are specific to each legal entity of your instance (for example, a set of tax codes to filter tax transactions).</span></span> <span data-ttu-id="36812-106">Obecnie, jeśli filtrowanie tego typu jest skonfigurowane w formacie ER, wartości zależne od firmy (np. kody podatków) są używane w wyrażeniach formatu ER w celu określenia reguł filtrowania danych.</span><span class="sxs-lookup"><span data-stu-id="36812-106">Currently, when filtering of this type is configured in an ER format, values that are dependent on the legal entity (for example, tax codes) are used in expressions of the ER format to specify data filtering rules.</span></span> <span data-ttu-id="36812-107">Z tego względu format ER jest zgodny z daną firmą, a w celu wygenerowania wymaganych raportów należy utworzyć pochodne kopie oryginalnego formatu ER dla każdej firmy, w której ma być uruchamiany format ER.</span><span class="sxs-lookup"><span data-stu-id="36812-107">Therefore, the ER format is made legal entity–specific, and to generate the required reports, you must create derived copies of the original ER format for each legal entity where you have to run the ER format.</span></span> <span data-ttu-id="36812-108">Każdy pochodny format ER musi być edytowany w celu przeniesienia do niego wartości właściwych dla firmy, który jest zmieniany w systemie, o ile oryginalna (podstawowa) wersja została zaktualizowana, wyeksportowana ze środowiska testowego i zaimportowana do środowiska produkcyjnego, jeśli musi zostać wdrożona do produkcji użycia itd.</span><span class="sxs-lookup"><span data-stu-id="36812-108">Each derived ER format must be edited to bring legal entity–specific values into it, rebased whenever the original (base) version has been updated, exported from a test environment and imported into a production environment when it must be deployed for production use, and so on.</span></span> <span data-ttu-id="36812-109">Dlatego obsługa tego typu skonfigurowanego rozwiązania ER jest dość skomplikowana i czasochłonna z kilku powodów:</span><span class="sxs-lookup"><span data-stu-id="36812-109">Therefore, maintenance of this type of configured ER solution is quite complex and time-consuming for several reasons:</span></span>

-   <span data-ttu-id="36812-110">Im więcej jest firm, tym więcej konfiguracji formatu ER trzeba będzie zachować.</span><span class="sxs-lookup"><span data-stu-id="36812-110">The more legal entities there are, the more ER format configurations must be maintained.</span></span>
-   <span data-ttu-id="36812-111">Obsługa konfiguracji ER wymaga, aby użytkownicy biznesowi mieli wiedzę na temat ER.</span><span class="sxs-lookup"><span data-stu-id="36812-111">Maintenance of ER configurations requires that business users have ER knowledge.</span></span>

<span data-ttu-id="36812-112">Funkcja parametrów specyficznych dla aplikacji ER umożliwia użytkownikom zaawansowanym konfigurowanie filtrowania danych w formacie ER, tak aby były oparte na zbiorze reguł abstrakcyjnych.</span><span class="sxs-lookup"><span data-stu-id="36812-112">The ER application-specific parameters feature lets power users configure data filtering in an ER format so that it's based on a set of abstract rules.</span></span> <span data-ttu-id="36812-113">Ten zbiór reguł może być skonfigurowany do korzystania ze źródeł danych dostępnych w formacie ER.</span><span class="sxs-lookup"><span data-stu-id="36812-113">This set of rules can be configured to use the data sources that are available in an ER format.</span></span> <span data-ttu-id="36812-114">Użytkownicy biznesowi mogą następnie określać rzeczywiste reguły poza strukturą ER za pomocą interfejsu użytkownika (UI), który jest generowany automatycznie na podstawie ustawień odpowiedniego formatu ER i bieżących danych firmy, do których mają dostęp dane formatu ER źródłem.</span><span class="sxs-lookup"><span data-stu-id="36812-114">Business users can then specify real rules beyond the ER framework by using the user interface (UI) that is automatically generated based on the settings of the corresponding ER format and the current legal entity data that will be accessed by the ER format's data sources.</span></span> <span data-ttu-id="36812-115">Zbiór reguł określonych dla formatu ER można wyeksportować z bieżącej firmy w wystąpieniu Dynamics 365 Finance (Finance).</span><span class="sxs-lookup"><span data-stu-id="36812-115">The set of rules that is specified for an ER format can be exported from the current legal entity of the Dynamics 365 Finance (Finance) instance.</span></span> <span data-ttu-id="36812-116">Może on następnie zostać zaimportowany do innego podmiotu prawnego o tej samej instancji Finance lub innym wystąpieniu jako zbiór reguł dla tego samego formatu ER.</span><span class="sxs-lookup"><span data-stu-id="36812-116">It can then be imported into another legal entity of either the same Finance instance or a different instance as a set of rules for the same ER format.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="36812-117">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="36812-117">Prerequisites</span></span>

<span data-ttu-id="36812-118">Aby uzupełnić przykłady w tym temacie, musisz mieć dostęp, dostęp do wystąpienia Regulatory Configuration Service (RCS), które zostało zainicjowane dla tej samej dzierżawy co Finance dla jednej z następujących ról:</span><span class="sxs-lookup"><span data-stu-id="36812-118">To complete the examples in this topic, you must have access to the instance of Regulatory Configuration Services (RCS) that has been provisioned for the same tenant as Finance for one of the following roles:</span></span>

- <span data-ttu-id="36812-119">Deweloper raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="36812-119">Electronic reporting developer</span></span>
- <span data-ttu-id="36812-120">Konsultant funkcjonalny raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="36812-120">Electronic reporting functional consultant</span></span>
- <span data-ttu-id="36812-121">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="36812-121">System administrator</span></span>

<span data-ttu-id="36812-122">Zaleca się wykonanie kroków opisanych w temacie [Obsługa sparametryzowanych wywołań źródeł danych narzędzia Raportowanie elektroniczne typu pola obliczeniowego](er-calculated-field-type.md).</span><span class="sxs-lookup"><span data-stu-id="36812-122">We recommend that you complete the steps in the [Support parameterized calls of ER data sources of CALCULATED FIELD type](er-calculated-field-type.md) topic.</span></span> <span data-ttu-id="36812-123">Jeśli wykonano już te kroki, można pominąć kroki opisane w sekcji **Importowanie konfiguracji zadania do RCS**.</span><span class="sxs-lookup"><span data-stu-id="36812-123">If you've already completed those steps, you can skip the steps in the **Import ER configurations into RCS** section that follows.</span></span>

## <a name="import-er-configurations-into-rcs"></a><span data-ttu-id="36812-124">Importowanie konfiguracji ER do RCS</span><span class="sxs-lookup"><span data-stu-id="36812-124">Import ER configurations into RCS</span></span>

<span data-ttu-id="36812-125">W [centrum pobierania firmy Microsoft](https://go.microsoft.com/fwlink/?linkid=851448) pobierz spakowany skompresowany plik **Obsługa sparametryzowanych wywołań źródeł danych narzędzia Raportowanie elektroniczne typu pola obliczeniowego**.</span><span class="sxs-lookup"><span data-stu-id="36812-125">From [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=851448), download the **Support parameterized calls of ER data sources of CALCULATED FIELD type** zip file.</span></span> <span data-ttu-id="36812-126">Plik skompresowany zawiera następujące konfiguracje ER, które muszą zostać wyodrębnione i zapisane lokalnie.</span><span class="sxs-lookup"><span data-stu-id="36812-126">This zip file contains the following ER configurations that must be extracted and stored locally.</span></span>

| <span data-ttu-id="36812-127">**Opis zawartości**</span><span class="sxs-lookup"><span data-stu-id="36812-127">**Content description**</span></span>                        | <span data-ttu-id="36812-128">**Nazwa pliku**</span><span class="sxs-lookup"><span data-stu-id="36812-128">**File name**</span></span>                                        |
|------------------------------------------------|------------------------------------------------------|
| <span data-ttu-id="36812-129">Plik przykładowa **konfiguracja modelu danych ER**</span><span class="sxs-lookup"><span data-stu-id="36812-129">Sample **ER data model** configuration file</span></span>    | <span data-ttu-id="36812-130">Model do nauczenia sparametryzowanych calls.version.1.xml.</span><span class="sxs-lookup"><span data-stu-id="36812-130">Model to learn parameterized calls.version.1.xml</span></span>     |
| <span data-ttu-id="36812-131">Plik przykładowa konfiguracja **metadanych ER**</span><span class="sxs-lookup"><span data-stu-id="36812-131">Sample **ER metadata** configuration file</span></span>      | <span data-ttu-id="36812-132">Dane do nauczenia sparametryzowanych calls.version.1.xml.</span><span class="sxs-lookup"><span data-stu-id="36812-132">Metadata to learn parameterized calls.version.1.xml</span></span>  |
| <span data-ttu-id="36812-133">Plik przykładowa konfiguracja **mapowania modelu ER**</span><span class="sxs-lookup"><span data-stu-id="36812-133">Sample **ER model mapping** configuration file</span></span> | <span data-ttu-id="36812-134">Mapowanie do nauczenia sparametryzowanych calls.version.1.xml.</span><span class="sxs-lookup"><span data-stu-id="36812-134">Mapping to learn parameterized calls.version.1.1.xml</span></span> |
| <span data-ttu-id="36812-135">Plik Przykładowa konfiguracja **formatu ER**</span><span class="sxs-lookup"><span data-stu-id="36812-135">Sample **ER format** configuration</span></span>             | <span data-ttu-id="36812-136">Format do nauczenia sparametryzowanych calls.version.1.xml.</span><span class="sxs-lookup"><span data-stu-id="36812-136">Format to learn parameterized calls.version.1.1.xml</span></span>  |

<span data-ttu-id="36812-137">Następnie zaloguj się do swojego wystąpienia RCS.</span><span class="sxs-lookup"><span data-stu-id="36812-137">Next, sign in to your RCS instance.</span></span>

<span data-ttu-id="36812-138">W tym przykładzie utworzysz konfigurację dla przykładowej Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="36812-138">In this example, you will create a configuration for the Litware, Inc sample company.</span></span> <span data-ttu-id="36812-139">Aby ukończyć tę procedurę, musisz wykonać czynności opisane w temacie w RCS [Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="36812-139">Before you can complete this procedure, you must complete the steps in the [Create a configuration provider and mark it as active](tasks/er-configuration-provider-mark-it-active-2016-11.md) topic in RCS.</span></span>

1.  <span data-ttu-id="36812-140">Na domyślnym pulpicie nawigacyjnym wybierz opcję **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="36812-140">On the default dashboard, select **Electronic reporting**.</span></span>
2.  <span data-ttu-id="36812-141">Wybierz **Raportowanie konfiguracji**.</span><span class="sxs-lookup"><span data-stu-id="36812-141">Select **Reporting configurations**.</span></span>
3.  <span data-ttu-id="36812-142">Zaimportuj pobrane wcześniej konfiguracje ER do RCS w następującej kolejności: model danych, metadane, mapowanie modelu, format.</span><span class="sxs-lookup"><span data-stu-id="36812-142">Import the ER configurations that you downloaded earlier into RCS, in the following order: data model, metadata, model mapping, and format.</span></span> <span data-ttu-id="36812-143">Dla każdej konfiguracji ER wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="36812-143">For each ER configuration, follow these steps:</span></span>

    1.  <span data-ttu-id="36812-144">Wybierz **Zamień**.</span><span class="sxs-lookup"><span data-stu-id="36812-144">Select **Exchange**.</span></span>
    2.  <span data-ttu-id="36812-145">Wybierz **Załaduj z pliku XML**.</span><span class="sxs-lookup"><span data-stu-id="36812-145">Select **Load from XML file**.</span></span>
    3.  <span data-ttu-id="36812-146">Kliknij przycisk **Przeglądaj**, aby wybrać plik wymaganej konfiguracji ER w formacie XML.</span><span class="sxs-lookup"><span data-stu-id="36812-146">Select **Browse** to select the file for the required ER configuration in XML format.</span></span>
    4.  <span data-ttu-id="36812-147">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="36812-147">Select **OK**.</span></span>

## <a name="review-the-er-solution-that-is-provided"></a><span data-ttu-id="36812-148">Przejrzyj dostarczone rozwiązanie ER</span><span class="sxs-lookup"><span data-stu-id="36812-148">Review the ER solution that is provided</span></span>

1.  <span data-ttu-id="36812-149">W drzewie konfiguracji rozwiń zawartość **Model, aby uzyskać informacje o elementach sparametryzowanych wywołań**.</span><span class="sxs-lookup"><span data-stu-id="36812-149">In the configuration tree, expand the contents of the **Model to learn parameterized calls** item.</span></span>
2.  <span data-ttu-id="36812-150">Wybierz opcję **Format do nauczenia sparametryzowanych wywołań**.</span><span class="sxs-lookup"><span data-stu-id="36812-150">Select the **Format to learn parameterized calls** item.</span></span>
3.  <span data-ttu-id="36812-151">Wybierz opcję **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="36812-151">Select **Designer**.</span></span>
4.  <span data-ttu-id="36812-152">Wybierz **Rozwiń/zwiń**.</span><span class="sxs-lookup"><span data-stu-id="36812-152">Select **Expand/Collapse**.</span></span>

    <span data-ttu-id="36812-153">**Format wywołania sparametryzowanych wywołań** formatu ER jest przeznaczony do generowania deklaracji podatkowej w formacie XML, który przedstawia kilka poziomów opodatkowania (zwykły, ograniczony i brak)</span><span class="sxs-lookup"><span data-stu-id="36812-153">The **Format to learn parameterized calls** ER format is designed to generate a tax statement in XML format that presents several levels of taxation (regular, reduced, and none).</span></span> <span data-ttu-id="36812-154">Każdy poziom ma inną liczbę szczegółów.</span><span class="sxs-lookup"><span data-stu-id="36812-154">Each level has a different number of details.</span></span>

    ![Strona projektanta operacji ER](./media/RCS-AppSpecParms-ReviewFormat.PNG)

5.  <span data-ttu-id="36812-156">Na karcie **mapowanie** rozwiń pozycje **model**, **dane** i **podsumowanie**.</span><span class="sxs-lookup"><span data-stu-id="36812-156">On the **Mapping** tab, expand the **Model**, **Data**, and **Summary** items.</span></span>

    <span data-ttu-id="36812-157">Źródło **Model.Data.Summary** podsumowanie zwraca listę transakcji podatkowych.</span><span class="sxs-lookup"><span data-stu-id="36812-157">The **Model.Data.Summary** data source returns the list of tax transactions.</span></span> <span data-ttu-id="36812-158">Transakcje te są podsumowane według kodu podatkowego.</span><span class="sxs-lookup"><span data-stu-id="36812-158">These transactions are summarized by tax code.</span></span> <span data-ttu-id="36812-159">Dla tego źródła danych pole obliczeniowe **Model.Data.Summary.Level** na poziomie zostało skonfigurowane w taki sposób, aby zwracała kod poziomu opodatkowania każdego rekordu zbiorczego.</span><span class="sxs-lookup"><span data-stu-id="36812-159">For this data source, the **Model.Data.Summary.Level** calculated field has been configured to return the code for the taxation level of each summarized record.</span></span> <span data-ttu-id="36812-160">Obliczone pole **Model.Data.Summary.Level** zawiera źródło danych w czasie wykonywania obliczone pole zwraca kod poziomu opodatkowania (**Zwykłe**, **Obniżone**, **Brak** lub **Inne**) jako wartość tekstową.</span><span class="sxs-lookup"><span data-stu-id="36812-160">For any tax code that can be retrieved from the **Model.Data.Summary** data source at runtime, the calculated field returns the taxation level code (**Regular**, **Reduced**, **None**, or **Other**) as a text value.</span></span> <span data-ttu-id="36812-161">Pole **Model.Data.Summary.Level** służy do filtrowania rekordów **Model.Data.Summary** i wprowadź filtrowane dane w każdym elemencie XML, który reprezentuje poziom opodatkowania, przy użyciu pól **Model.Data2.Level1**, **Model.Data2.Level2** i **Model.Data2.Level3**.</span><span class="sxs-lookup"><span data-stu-id="36812-161">The **Model.Data.Summary.Level** calculated field is used to filter records of the **Model.Data.Summary** data source and enter the filtered data in each XML element that represents a taxation level by using the **Model.Data2.Level1**, **Model.Data2.Level2**, and **Model.Data2.Level3** fields.</span></span>

    ![Strona projektanta operacji ER](./media/RCS-AppSpecParms-ReviewFormat-Data2Fld.PNG)

    <span data-ttu-id="36812-163">Pole **Model.Data.Summary.Level** zostało skonfigurowane w taki sposób, aby zawierało wyrażenie ER.</span><span class="sxs-lookup"><span data-stu-id="36812-163">The **Model.Data.Summary.Level** calculated field has been configured so that it contains an ER expression.</span></span> <span data-ttu-id="36812-164">Należy zwrócić uwagę, że kody podatków (**VAT19**, **InVAT19**, **VAT7**, **InVAT7**, **THIRD** i **InVAT0**) są mocno zakodowane w tej konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="36812-164">Note that tax codes (**VAT19**, **InVAT19**, **VAT7**, **InVAT7**, **THIRD**, and **InVAT0**) are hardcoded into this configuration.</span></span> <span data-ttu-id="36812-165">W związku z tym ten format ER jest zależny od firmy, w której skonfigurowano kody podatków.</span><span class="sxs-lookup"><span data-stu-id="36812-165">Therefore, this ER format is dependent on the legal entity where these tax codes were configured.</span></span>

    ![Strona projektanta operacji ER](./media/RCS-AppSpecParms-ReviewFormat-LevelFld.PNG)

    <span data-ttu-id="36812-167">Aby obsługiwać różne zestawy kodów podatków dla poszczególnych firm, należy wykonać następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="36812-167">To support a different set of tax codes for each legal entity, you must follow these steps:</span></span>

    - <span data-ttu-id="36812-168">Utwórz pochodną wersję formatu ER dla każdej firmy.</span><span class="sxs-lookup"><span data-stu-id="36812-168">Create a derived version of the ER format for each legal entity.</span></span>
    - <span data-ttu-id="36812-169">Umożliwia zaktualizowanie kodów podatków w polu obliczeniowym **Model.Data.Summary.Level** na podstawie ustawienia firmy.</span><span class="sxs-lookup"><span data-stu-id="36812-169">Update the tax codes in the **Model.Data.Summary.Level** calculated field, based on the legal entity setting.</span></span>

6.  <span data-ttu-id="36812-170">Zamknij stronę **Projektowanie formuły**.</span><span class="sxs-lookup"><span data-stu-id="36812-170">Close the **Format designer** page.</span></span>

## <a name="create-a-derived-format"></a><span data-ttu-id="36812-171">Tworzenie pochodnego formatu</span><span class="sxs-lookup"><span data-stu-id="36812-171">Create a derived format</span></span>

<span data-ttu-id="36812-172">Następnie użytkownik korzysta z funkcji parametrów specyficznych dla aplikacji ER w celu obsługi różnych kodów podatków dla każdej firmy w jednym formacie ER.</span><span class="sxs-lookup"><span data-stu-id="36812-172">Next, you will use the ER application-specific parameters feature to support a different set of tax codes for each legal entity in a single ER format.</span></span>

1.  <span data-ttu-id="36812-173">W drzewie konfiguracji rozwiń zawartość **Model, aby uzyskać informacje o elementach sparametryzowanych wywołań**.</span><span class="sxs-lookup"><span data-stu-id="36812-173">In the configuration tree, expand the contents of the **Model to learn parameterized calls** item.</span></span>
2.  <span data-ttu-id="36812-174">Wybierz opcję **Format do nauczenia sparametryzowanych wywołań**.</span><span class="sxs-lookup"><span data-stu-id="36812-174">Select the **Format to learn parameterized calls** item.</span></span>
3.  <span data-ttu-id="36812-175">Wybierz **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="36812-175">Select **Create configuration**.</span></span>
4.  <span data-ttu-id="36812-176">Wybierz opcję **pochodną z Nazwy: Format, aby poznać wywołania sparametryzowane Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="36812-176">Select the **Derive from Name: Format to learn parameterized calls, Microsoft** option.</span></span>
5.  <span data-ttu-id="36812-177">W polu **nazwa** wprowadź **Format, aby uzyskać informacje o wyszukiwaniu danych LE**.</span><span class="sxs-lookup"><span data-stu-id="36812-177">In the **Name** field, enter **Format to learn how to lookup LE data**.</span></span>
6.  <span data-ttu-id="36812-178">Wybierz **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="36812-178">Select **Create configuration**.</span></span>

## <a name="configure-a-derived-format"></a><span data-ttu-id="36812-179">Konfiguruj format pochodny</span><span class="sxs-lookup"><span data-stu-id="36812-179">Configure a derived format</span></span>

### <a name="add-a-format-enumeration"></a><span data-ttu-id="36812-180">Dodaj wyliczenie formatów</span><span class="sxs-lookup"><span data-stu-id="36812-180">Add a format enumeration</span></span>

<span data-ttu-id="36812-181">Następnie zostanie dodane nowe Wyliczenie formatu ER.</span><span class="sxs-lookup"><span data-stu-id="36812-181">Next, you will add a new ER format enumeration.</span></span> <span data-ttu-id="36812-182">Wartości tego wyliczenia formatu będą prezentowane użytkownikom biznesowym, którzy będą określać zestawy podatków zależne od firm dla różnych poziomów opodatkowania, które są używane w formacie ER.</span><span class="sxs-lookup"><span data-stu-id="36812-182">The values of this format enumeration will be presented to business users, who will specify legal entity–dependent sets of tax codes for the various taxation levels that are used in the ER format.</span></span>

1.  <span data-ttu-id="36812-183">Wybierz opcję **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="36812-183">Select **Designer**.</span></span>
2.  <span data-ttu-id="36812-184">Wybierz **wyliczenia formatów**.</span><span class="sxs-lookup"><span data-stu-id="36812-184">Select **Format enumerations**.</span></span>
3.  <span data-ttu-id="36812-185">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="36812-185">Select **Add**.</span></span>
4.  <span data-ttu-id="36812-186">W polu **Nazwa** wpisz **Lista poziomów opodatkowania**.</span><span class="sxs-lookup"><span data-stu-id="36812-186">In the **Name** field, enter **List of taxation levels**.</span></span>
5.  <span data-ttu-id="36812-187">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="36812-187">Select **Save**.</span></span>
6.  <span data-ttu-id="36812-188">Na karcie **Wartości wyliczenia formatu** wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="36812-188">On the **Format enumeration values** tab, select **Add**.</span></span>
7.  <span data-ttu-id="36812-189">W polu **Nazwa** wpisz **zwykłe opodatkowanie**.</span><span class="sxs-lookup"><span data-stu-id="36812-189">In the **Name** field, enter **Regular taxation**.</span></span>
8.  <span data-ttu-id="36812-190">Wybierz ponownie przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="36812-190">Select **Add** again.</span></span>
9.  <span data-ttu-id="36812-191">W polu **Nazwa** wpisz **obniżone opodatkowanie**.</span><span class="sxs-lookup"><span data-stu-id="36812-191">In the **Name** field, enter **Reduced taxation**.</span></span>
10. <span data-ttu-id="36812-192">Wybierz ponownie przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="36812-192">Select **Add** again.</span></span>
11. <span data-ttu-id="36812-193">W polu **Nazwa** wpisz **Brak opodatkowania**.</span><span class="sxs-lookup"><span data-stu-id="36812-193">In the **Name** field, enter **No taxation**.</span></span>
12. <span data-ttu-id="36812-194">Wybierz ponownie przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="36812-194">Select **Add** again.</span></span>
13. <span data-ttu-id="36812-195">W polu **Nazwa** wprowadź nazwę **Inne**.</span><span class="sxs-lookup"><span data-stu-id="36812-195">In the **Name** field, enter **Other**.</span></span>

    ![Strona projektanta operacji ER](./media/RCS-AppSpecParms-ConfigureFormat-Enum.PNG)

    <span data-ttu-id="36812-197">Ponieważ użytkownicy biznesowi mogą stosować różne języki do określania zestawów kodów podatków zależnych od firm, zaleca się przetłumaczenie wartości tego wyliczenia na języki skonfigurowane jako preferowane języki dla tych użytkowników w Finance.</span><span class="sxs-lookup"><span data-stu-id="36812-197">Because the business users might use different languages to specify legal entity–dependent sets of tax codes, we recommend that you translate the values of this enumeration into the languages that are configured as the preferred languages for those users in Finance.</span></span>

14. <span data-ttu-id="36812-198">Wybierz rekord **Brak opodatkowania**.</span><span class="sxs-lookup"><span data-stu-id="36812-198">Select the **No taxation** record.</span></span>
15. <span data-ttu-id="36812-199">Kliknij opcję w polu **etykieta**.</span><span class="sxs-lookup"><span data-stu-id="36812-199">Click in the **Label** field.</span></span>
16. <span data-ttu-id="36812-200">Wybierz **Tłumacz**.</span><span class="sxs-lookup"><span data-stu-id="36812-200">Select **Translate**.</span></span>
17. <span data-ttu-id="36812-201">W okienku **tłumaczenie tekstu** w polu **Identyfikator etykiety** wprowadź **LBL_LEVELENUM_NO**.</span><span class="sxs-lookup"><span data-stu-id="36812-201">In the **Text translation** pane, in the **Label Id** field, enter **LBL_LEVELENUM_NO**.</span></span>
18. <span data-ttu-id="36812-202">W polu **tekst w języku domyślnym** wprowadź wartość **Brak opodatkowania**.</span><span class="sxs-lookup"><span data-stu-id="36812-202">In the **Text in default language** field, enter **No taxation**.</span></span>
19. <span data-ttu-id="36812-203">W polu **Język** wybierz **DE**.</span><span class="sxs-lookup"><span data-stu-id="36812-203">In the **Language** field, select **DE**.</span></span>
20. <span data-ttu-id="36812-204">W polu **Przetłumaczony tekst** wprowadź tekst **keine Besteuerung**.</span><span class="sxs-lookup"><span data-stu-id="36812-204">In the **Translated text** field, enter **keine Besteuerung**.</span></span>
21. <span data-ttu-id="36812-205">Wybierz **Tłumacz**.</span><span class="sxs-lookup"><span data-stu-id="36812-205">Select **Translate**.</span></span>

    ![Strona projektanta operacji ER](./media/RCS-AppSpecParms-ConfigureFormat-EnumTranslate.PNG)

22. <span data-ttu-id="36812-207">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="36812-207">Select **Save**.</span></span>
23. <span data-ttu-id="36812-208">Zamknij stronę **wyliczenia formatów**.</span><span class="sxs-lookup"><span data-stu-id="36812-208">Close the **Format enumerations** page.</span></span>

### <a name="add-a-new-lookup-data-source"></a><span data-ttu-id="36812-209">Dodaj nowe źródło danych wyszukiwania</span><span class="sxs-lookup"><span data-stu-id="36812-209">Add a new lookup data source</span></span>

<span data-ttu-id="36812-210">Następnie należy dodać nowe źródło danych w celu określenia sposobu, w jaki użytkownicy biznesowi będą określać reguły zależne od firmy w celu rozpoznania poprawnego poziomu opodatkowania dla każdego rekordu transakcji zbiorczej.</span><span class="sxs-lookup"><span data-stu-id="36812-210">Next, you will add a new data source to specify how business users will specify legal entity–dependent rules to recognize the correct taxation level for each summarized transaction record.</span></span>

1.  <span data-ttu-id="36812-211">Na karcie **mapowanie** wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="36812-211">On the **Mapping** tab, select **Add**.</span></span>
2.  <span data-ttu-id="36812-212">Wybierz **wyliczenia formatów\wyszukiwanie**.</span><span class="sxs-lookup"><span data-stu-id="36812-212">Select **Format enumeration\Lookup**.</span></span>

    <span data-ttu-id="36812-213">Użytkownik stwierdził, że każda reguła określona przez użytkowników biznesowych w celu rozpoznania poziomu opodatkowania zwróci wartość wyliczenia formatu ER.</span><span class="sxs-lookup"><span data-stu-id="36812-213">You just identified that each rule that business users specify for taxation level recognition will return a value of an ER format enumeration.</span></span> <span data-ttu-id="36812-214">Należy zauważyć, że typ źródła danych **wyszukiwania** może być dostępny w **modelu danych** i blokach **Dynamics 365 for Operations** oprócz bloku **wyliczenia formatu**.</span><span class="sxs-lookup"><span data-stu-id="36812-214">Notice that the **Lookup** data source type can be accessed under the **Data model** and **Dynamics 365 for Operations** blocks in addition to the **Format enumeration** block.</span></span> <span data-ttu-id="36812-215">W związku z tym wyliczenia modeli danych ER i wyliczenia aplikacji mogą służyć do określenia typu wartości zwracanych dla źródeł danych tego typu.</span><span class="sxs-lookup"><span data-stu-id="36812-215">Therefore, ER data model enumerations and application enumerations can be used to specify the type of values that is are returned for data sources of that type.</span></span>
    
3.  <span data-ttu-id="36812-216">W polu **Nazwa** wpisz **Reguła**.</span><span class="sxs-lookup"><span data-stu-id="36812-216">In the **Name** field, enter **Selector**.</span></span>
4.  <span data-ttu-id="36812-217">W polu **Wyliczenie formatów** wybierz **Lista poziomów opodatkowania**.</span><span class="sxs-lookup"><span data-stu-id="36812-217">In the **Format enumeration** field, select **List of taxation levels**.</span></span>

    <span data-ttu-id="36812-218">Określono tylko, że dla każdej reguły określonej w tym źródle danych użytkownik biznesowy musi wybrać jedną z wartości z **listy poziomów opodatkowania** do wyliczenia jako wartość zwróconą.</span><span class="sxs-lookup"><span data-stu-id="36812-218">You just specified that, for each rule that is specified in this data source, a business user must select one of the values of the **List of taxation levels** format enumeration as a returned value.</span></span>
    
5.  <span data-ttu-id="36812-219">Wybierz **Edytuj wyszukiwania**.</span><span class="sxs-lookup"><span data-stu-id="36812-219">Select **Edit lookup**.</span></span>
6.  <span data-ttu-id="36812-220">Wybierz **Kolumny**.</span><span class="sxs-lookup"><span data-stu-id="36812-220">Select **Columns**.</span></span>
7.  <span data-ttu-id="36812-221">Rozwiń **Model**.</span><span class="sxs-lookup"><span data-stu-id="36812-221">Expand the **Model** item.</span></span>
8.  <span data-ttu-id="36812-222">Rozwiń pozycję **Dane**.</span><span class="sxs-lookup"><span data-stu-id="36812-222">Expand the **Data** item.</span></span>
9.  <span data-ttu-id="36812-223">Rozwiń pozycję **Podatek**.</span><span class="sxs-lookup"><span data-stu-id="36812-223">Expand the **Tax** item.</span></span>
10. <span data-ttu-id="36812-224">Wybierz pozycję **Model.Data.Tax.Code**.</span><span class="sxs-lookup"><span data-stu-id="36812-224">Select the **Model.Data.Tax.Code** item.</span></span>
11. <span data-ttu-id="36812-225">Wybierz przycisk **Dodaj** (Strzałka w prawo).</span><span class="sxs-lookup"><span data-stu-id="36812-225">Select the **Add** button (the right arrow).</span></span>

    ![Strona projektanta operacji ER](./media/RCS-AppSpecParms-ConfigureFormat-Lookup1.PNG)

    <span data-ttu-id="36812-227">Właśnie określono, że dla każdej reguły określonej w tym źródle danych do rozpoznawania poziomu opodatkowania użytkownik biznesowy musi wybrać jeden z kodów podatkowych jako warunek.</span><span class="sxs-lookup"><span data-stu-id="36812-227">You just specified that, for each rule that is specified in this data source for taxation level recognition, a business user must select one of the tax codes as a condition.</span></span> <span data-ttu-id="36812-228">Lista kodów podatków, które może wybrać użytkownik biznesowy, zostanie zwrócona przez źródło danych **Model.Data.Tax**.</span><span class="sxs-lookup"><span data-stu-id="36812-228">The list of tax codes that the business user can select will be returned by the **Model.Data.Tax** data source.</span></span> <span data-ttu-id="36812-229">Ponieważ to źródło danych zawiera pole **nazwa**, nazwa kodu podatku będzie wyświetlana dla każdej wartości kodu podatku w wyszukiwaniu prezentowanemu użytkownikowi biznesowemu.</span><span class="sxs-lookup"><span data-stu-id="36812-229">Because this data source contains the **Name** field, the name of the tax code will be shown for each tax code value in the lookup that is presented to the business user.</span></span>
    
12. <span data-ttu-id="36812-230">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="36812-230">Select **OK**.</span></span>

    ![Strona projektanta operacji ER](./media/RCS-AppSpecParms-ConfigureFormat-Lookup2.PNG)

    <span data-ttu-id="36812-232">Użytkownicy biznesowi mogą dodawać wiele reguł w postaci rekordów tego źródła danych.</span><span class="sxs-lookup"><span data-stu-id="36812-232">Business users can add multiple rules as records of this data source.</span></span> <span data-ttu-id="36812-233">Każdy rekord będzie numerowany według kodu wiersza.</span><span class="sxs-lookup"><span data-stu-id="36812-233">Each record will be numbered by a line code.</span></span> <span data-ttu-id="36812-234">Reguły będą oceniane w kolejności rosnącego numeru wiersza.</span><span class="sxs-lookup"><span data-stu-id="36812-234">Rules will be evaluated in order of increasing line number.</span></span>

    <span data-ttu-id="36812-235">Ponieważ pole **kod podatku** zostało wybrane jako warunek dla reguł w tym źródle danych wyszukiwania, a **kod podatku** jest skonfigurowany jako pole typu **ciąg znaków**, każda reguła będzie oceniana w czasie wykonywania przez porównanie kodu podatku przekazanego do źródła danych z kodem podatku zdefiniowanym w tym rekordzie źródła danych.</span><span class="sxs-lookup"><span data-stu-id="36812-235">Because you selected the **Tax code** field as a condition for rules in this lookup data source, and because **Tax code** is set up as a field of the **String** data type, each rule will be evaluated at runtime by comparing the tax code that is passed to the data source with the tax code that is defined in this record of the data source.</span></span>

    <span data-ttu-id="36812-236">Gdy zostanie znaleziona reguła, która spełnia skonfigurowany warunek, to źródło danych zwraca wartość wyszukiwania reguły zdefiniowanej w polu **wynik wyszukiwania**.</span><span class="sxs-lookup"><span data-stu-id="36812-236">When a rule that satisfies the configured condition is found, this data source returns the lookup value of the rule that is defined in the **Lookup result** field.</span></span> <span data-ttu-id="36812-237">Jeśli nie zostanie znaleziona żadna reguła, zostanie zgłoszony wyjątek w celu powiadomienia użytkownika, że bieżące źródło danych nie może zwrócić poprawnej wartości.</span><span class="sxs-lookup"><span data-stu-id="36812-237">If no rule is found, an exception is thrown to notify the user that the current data source can't return a correct value.</span></span>

13. <span data-ttu-id="36812-238">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="36812-238">Select **Save**.</span></span>
14. <span data-ttu-id="36812-239">Zamknij stronę **Projektowanie wyszukiwania**.</span><span class="sxs-lookup"><span data-stu-id="36812-239">Close the **Lookup designer** page.</span></span>
15. <span data-ttu-id="36812-240">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="36812-240">Select **OK**.</span></span>

    <span data-ttu-id="36812-241">Należy zauważyć, że dodano nowe źródło danych, które zwróci poziom opodatkowania jako wartość **listy poziomów opodatkowania** dla dowolnego kodu podatku przekazanego do źródła danych jako argumentu parametru **kodu** typu danych **ciągu**.</span><span class="sxs-lookup"><span data-stu-id="36812-241">Notice that you added a new data source that will return the taxation level as the value of the **List of taxation levels** format enumeration for any tax code that is passed to the data source as the argument of the **Code** parameter of the **String** data type.</span></span>
    
    ![Strona projektanta operacji ER](./media/RCS-AppSpecParms-ConfigureFormat-SelectorFld.PNG)

    <span data-ttu-id="36812-243">Należy zauważyć, że Ocena skonfigurowanych reguł zależy od typu danych pól, które zostały wybrane w celu zdefiniowania warunków tych reguł.</span><span class="sxs-lookup"><span data-stu-id="36812-243">Note that the evaluation of configured rules depends on the data type of the fields that have been selected to define conditions of those rules.</span></span> <span data-ttu-id="36812-244">Po wybraniu pola, które jest skonfigurowane jako pole typu danych **numerycznych** lub **dat**, kryteria różnią się od kryteriów opisanych wcześniej dla typu **ciąg**.</span><span class="sxs-lookup"><span data-stu-id="36812-244">When you select a field that is configured as a field of either the **Numeric** or **Date** data type, the criteria will differ from the criteria that were described earlier for the **String** data type.</span></span> <span data-ttu-id="36812-245">W przypadku pól **numerycznych** i **dat** reguła musi być określona jako zakres wartości.</span><span class="sxs-lookup"><span data-stu-id="36812-245">For **Numeric** and **Date** fields, the rule must be specified as a range of values.</span></span> <span data-ttu-id="36812-246">Warunek reguły zostanie wówczas uznany za spełniony, gdy wartość przekazywana do źródła danych znajduje się w skonfigurowanym zakresie.</span><span class="sxs-lookup"><span data-stu-id="36812-246">The condition of the rule will then be considered satisfied when a value that is passed to the data source is in the configured range.</span></span>
    
    <span data-ttu-id="36812-247">Ilustracja poniżej zawiera przykład tego rodzaju ustawień.</span><span class="sxs-lookup"><span data-stu-id="36812-247">The following illustration shows an example of this type of setup.</span></span> <span data-ttu-id="36812-248">Oprócz pole **Model.Data.Tax.Code** w typie danych **Ciąg** w polu **Model.Tax.Summary.Base** w **właściwe** służy do określania warunków dla źródła danych wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="36812-248">In addition to the **Model.Data.Tax.Code** field of the **String** data type, the **Model.Tax.Summary.Base** field of the **Real** data type is used to specify conditions for a lookup data source.</span></span>
    
    ![Strona projektanta operacji ER](./media/RCS-AppSpecParms-ConfigureFormat-SelectorFld2.PNG)

    <span data-ttu-id="36812-250">Ponieważ pola **Model.Data.Tax.Code** i **Model.Tax.Summary.Base** są wybrane, każda reguła tego źródła danych zostanie skonfigurowana w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="36812-250">Because the **Model.Data.Tax.Code** and **Model.Tax.Summary.Base** fields are selected for this lookup data source, each rule of this data source will be configured in the following way:</span></span>
    
    -   <span data-ttu-id="36812-251">Na wyświetlonej liście należy wybrać wartość w polu **Lista poziomów opodatkowania** jako wartość zwróconą.</span><span class="sxs-lookup"><span data-stu-id="36812-251">In the list that is presented, the value of the **List of taxation levels** format enumeration must be selected as a returned value.</span></span>
    -   <span data-ttu-id="36812-252">Kod podatku musi zostać wprowadzony jako warunek tej reguły.</span><span class="sxs-lookup"><span data-stu-id="36812-252">The tax code must be entered as a condition of this rule.</span></span> <span data-ttu-id="36812-253">Mają być tylko kody podatków podane przez **Model.Data.Tax** są odpowiednie.</span><span class="sxs-lookup"><span data-stu-id="36812-253">Only tax codes that are provided by the **Model.Data.Tax** data source are applicable.</span></span>
    -   <span data-ttu-id="36812-254">Minimalna i maksymalna wartość kwoty podstawy podatku musi zostać wprowadzona jako warunki tej reguły.</span><span class="sxs-lookup"><span data-stu-id="36812-254">Minimum and maximum values of the tax base amount must be entered as conditions of this rule.</span></span>

    <span data-ttu-id="36812-255">Oto, jak Każda reguła tego źródła danych będzie oceniana w czasie wykonywania:</span><span class="sxs-lookup"><span data-stu-id="36812-255">Here is how each rule of this data source will be evaluated at runtime:</span></span>
    -   <span data-ttu-id="36812-256">Czy kod typu danych **Ciąg**, który został przekazany do tego źródła danych, jest równy kodowi podatku reguły?</span><span class="sxs-lookup"><span data-stu-id="36812-256">Does the code of the **String** data type that was passed to this data source equal the tax code of a rule?</span></span>
    -   <span data-ttu-id="36812-257">Czy wartość **rzeczywistego** typu danych przekazywana do tego źródła danych odpada między określonymi wartościami minimalnymi i maksymalnymi?</span><span class="sxs-lookup"><span data-stu-id="36812-257">Does the value of the **Real** data type that was passed to this data source fall between specific minimum and maximum values?</span></span>

    <span data-ttu-id="36812-258">Reguła będzie uważana za stosowaną, gdy spełnione są oba warunki.</span><span class="sxs-lookup"><span data-stu-id="36812-258">A rule will be considered applicable when both conditions are satisfied.</span></span>

### <a name="translate-the-label-of-the-lookup-data-source-that-was-added"></a><span data-ttu-id="36812-259">Przetłumacz etykietę dodanego źródła danych wyszukiwania</span><span class="sxs-lookup"><span data-stu-id="36812-259">Translate the label of the lookup data source that was added</span></span>

<span data-ttu-id="36812-260">Ponieważ użytkownicy biznesowi mogą używać różnych języków do określania zestawów kodów podatkowych zależnych od podmiotów prawnych, zalecamy przetłumaczenie etykiety każdego dodanego źródła danych wyszukiwania, aby była ona wyświetlana w preferowanym języku każdego użytkownika na odpowiedniej stronie.</span><span class="sxs-lookup"><span data-stu-id="36812-260">Because business users might use different languages to specify legal entity–dependent sets of tax codes, we recommend that you translate the label of any lookup data source that you add, so that it's presented in each user's preferred language on the corresponding page.</span></span>

1.  <span data-ttu-id="36812-261">Wybierz źródło danych **Model.Data.Selector**.</span><span class="sxs-lookup"><span data-stu-id="36812-261">Select the **Model.Data.Selector** data source.</span></span>
2.  <span data-ttu-id="36812-262">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="36812-262">Select **Edit**.</span></span>
3.  <span data-ttu-id="36812-263">Kliknij opcję w polu **etykieta**.</span><span class="sxs-lookup"><span data-stu-id="36812-263">Click in the **Label** field.</span></span>
4.  <span data-ttu-id="36812-264">Wybierz **Tłumacz**.</span><span class="sxs-lookup"><span data-stu-id="36812-264">Select **Translate**.</span></span>
5.  <span data-ttu-id="36812-265">W okienku **tłumaczenie tekstu** w polu **Identyfikator etykiety** wprowadź **LBL_SELECTOR_DS**.</span><span class="sxs-lookup"><span data-stu-id="36812-265">In the **Text translation** pane, in the **Label Id** field, enter **LBL_SELECTOR_DS**.</span></span>
6.  <span data-ttu-id="36812-266">W polu **tekst w języku domyślnym** wprowadź opcję **Wybierz kod podatku według kodu podatku**.</span><span class="sxs-lookup"><span data-stu-id="36812-266">In the **Text in default language** field, enter **Select tax level by tax code**.</span></span>
7.  <span data-ttu-id="36812-267">W polu **Język** wybierz **DE**.</span><span class="sxs-lookup"><span data-stu-id="36812-267">In the **Language** field, select **DE**.</span></span>
8.  <span data-ttu-id="36812-268">W polu **przetłumaczony tekst** wprowadź **Steuerebene für Steuerkennzeichen auswählen**.</span><span class="sxs-lookup"><span data-stu-id="36812-268">In the **Translated text** field, enter **Steuerebene für Steuerkennzeichen auswählen**.</span></span>
9.  <span data-ttu-id="36812-269">Wybierz **Tłumacz**.</span><span class="sxs-lookup"><span data-stu-id="36812-269">Select **Translate**.</span></span>
10. <span data-ttu-id="36812-270">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="36812-270">Select **OK**.</span></span>

    ![Strona projektanta operacji ER](./media/RCS-AppSpecParms-ConfigureFormat-SelectorFldTranslate.PNG)

### <a name="add-a-new-field-to-consume-the-configured-lookup"></a><span data-ttu-id="36812-272">Dodaj nowe pole, aby użyć skonfigurowanego wyszukiwania</span><span class="sxs-lookup"><span data-stu-id="36812-272">Add a new field to consume the configured lookup</span></span>

1.  <span data-ttu-id="36812-273">Rozwiń **Model.Data**.</span><span class="sxs-lookup"><span data-stu-id="36812-273">Expand the **Model.Data** item.</span></span>
2.  <span data-ttu-id="36812-274">Wybierz pozycję **Model.Data.Tax.Summary**.</span><span class="sxs-lookup"><span data-stu-id="36812-274">Select the **Model.Data.Summary** item.</span></span>
3.  <span data-ttu-id="36812-275">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="36812-275">Select **Add**.</span></span>
4.  <span data-ttu-id="36812-276">Wybierz **Funkcje/Pole obliczeniowe**.</span><span class="sxs-lookup"><span data-stu-id="36812-276">Select **Functions/Calculated field**.</span></span>
5.  <span data-ttu-id="36812-277">W polu **Nazwa** wpisz **LevelByLookup**.</span><span class="sxs-lookup"><span data-stu-id="36812-277">In the **Name** field, enter **LevelByLookup**.</span></span>
6.  <span data-ttu-id="36812-278">Wybierz opcję **Edytuj formułę**.</span><span class="sxs-lookup"><span data-stu-id="36812-278">Select **Edit formula**.</span></span>
7.  <span data-ttu-id="36812-279">W **polu formuła** wprowadź **Model.Selector(Model.Data.Summary.Code)**.</span><span class="sxs-lookup"><span data-stu-id="36812-279">In the **Formula field**, enter **Model.Selector(Model.Data.Summary.Code)**.</span></span>
8.  <span data-ttu-id="36812-280">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="36812-280">Select **Save**.</span></span>

    ![Strona projektanta operacji ER](./media/RCS-AppSpecParms-ConfigureFormat-AddLevelByLookupFld.PNG)

9.  <span data-ttu-id="36812-282">Zamknij stronę **Edytor formuł**.</span><span class="sxs-lookup"><span data-stu-id="36812-282">Close the **Formula editor** page.</span></span>
10. <span data-ttu-id="36812-283">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="36812-283">Select **OK**.</span></span>

    ![Strona projektanta operacji ER](./media/RCS-AppSpecParms-ConfigureFormat-AddLevelByLookupFld2.PNG)

    <span data-ttu-id="36812-285">Należy zauważyć, że dodane pole obliczeniowe **LevelByLookup** będzie zwracać poziom opodatkowania jako wartość **listy poziomów opodatkowania** dla każdego rekordu zsumowanej transakcji podatkowej.</span><span class="sxs-lookup"><span data-stu-id="36812-285">Notice that the **LevelByLookup** calculated field that you added will return the taxation level as the value of the **List of taxation levels** format enumeration for each summarized tax transactions record.</span></span> <span data-ttu-id="36812-286">Kod podatku rekordu zostanie przekazany do wyszukiwania źródła danych **Model.Selector** zostanie użyta lista reguł wyszukiwania selektorów, a dla tego źródła danych zostanie wykorzystana opcja</span><span class="sxs-lookup"><span data-stu-id="36812-286">The tax code of the record will be passed to the **Model.Selector** lookup data source, and the set of rules for this data source will be used to select the correct taxation level.</span></span>

### <a name="add-a-new-format-enumeration-based-data-source"></a><span data-ttu-id="36812-287">Dodaj nowe źródło danych oparte na wyliczeniu</span><span class="sxs-lookup"><span data-stu-id="36812-287">Add a new format enumeration-based data source</span></span>

<span data-ttu-id="36812-288">Następnie należy dodać nowe źródło danych odwołujące się do wyliczenia formatu, które zostało dodane wcześniej.</span><span class="sxs-lookup"><span data-stu-id="36812-288">Next, you will add a new data source that refers to the format enumeration that you added earlier.</span></span> <span data-ttu-id="36812-289">Wartości tego źródła danych będą używane w wyrażeniu formatu ER w późniejszym terminie.</span><span class="sxs-lookup"><span data-stu-id="36812-289">Values of this data source will be used in an ER format expression later.</span></span>

1.  <span data-ttu-id="36812-290">Wybierz **Dodaj element główny**.</span><span class="sxs-lookup"><span data-stu-id="36812-290">Select **Add root**.</span></span>
2.  <span data-ttu-id="36812-291">Wybierz **Wyliczenia formatów\Wyliczenia**.</span><span class="sxs-lookup"><span data-stu-id="36812-291">Select **Format enumerations\Enumeration**.</span></span>
3.  <span data-ttu-id="36812-292">W polu **Nazwa** wpisz **TaxationLevel**.</span><span class="sxs-lookup"><span data-stu-id="36812-292">In the **Name** field, enter **TaxationLevel**.</span></span>
4.  <span data-ttu-id="36812-293">W polu **Wyliczenie formatów** wybierz **Lista poziomów opodatkowania**.</span><span class="sxs-lookup"><span data-stu-id="36812-293">In the **Format enumeration** field, select **List of taxation levels**.</span></span>
5.  <span data-ttu-id="36812-294">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="36812-294">Select **Save**.</span></span>

### <a name="modify-an-existing-field-to-start-to-use-the-lookup"></a><span data-ttu-id="36812-295">Zmodyfikuj istniejące pole, aby rozpocząć korzystanie z wyszukiwania</span><span class="sxs-lookup"><span data-stu-id="36812-295">Modify an existing field to start to use the lookup</span></span>

<span data-ttu-id="36812-296">Następnie zmodyfikuj istniejące pole obliczeniowe, tak aby używało skonfigurowanego źródła danych wyszukiwania do zwrócenia poprawnej wartości poziomu opodatkowania, w zależności od kodu podatku.</span><span class="sxs-lookup"><span data-stu-id="36812-296">Next, you will modify the existing calculated field so that it uses the configured lookup data source to return the correct taxation level value, depending on the tax code.</span></span>

1.  <span data-ttu-id="36812-297">Wybierz pozycję **Model.Data.Tax.Level**.</span><span class="sxs-lookup"><span data-stu-id="36812-297">Select the **Model.Data.Summary.Level** item.</span></span>
2.  <span data-ttu-id="36812-298">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="36812-298">Select **Edit**.</span></span>
3.  <span data-ttu-id="36812-299">Wybierz opcję **Edytuj formułę**.</span><span class="sxs-lookup"><span data-stu-id="36812-299">Select **Edit formula**.</span></span>

    <span data-ttu-id="36812-300">Zauważ, że bieżące wyrażenie dla pola **Model.Data.Summary.Level** zawiera następujące kody podatków w postaci stałej:</span><span class="sxs-lookup"><span data-stu-id="36812-300">Notice that the current expression of the **Model.Data.Summary.Level** field includes the following hard-coded tax codes:</span></span>
    
    <span data-ttu-id="36812-301">CASE (@. Kod, „VAT19”, „regularny”, „InVAT19”, „regularny”, „VAT7”, „obniżony”, „InVAT7”, „obniżony”, „Trzeci”, „Brak”, „InVAT0”, „Brak”, „inne”)</span><span class="sxs-lookup"><span data-stu-id="36812-301">CASE (@.Code, "VAT19", "Regular", "InVAT19", "Regular", "VAT7", "Reduced", "InVAT7", "Reduced", "THIRD", "None", "InVAT0", "None", "Other")</span></span>

4.  <span data-ttu-id="36812-302">W polu **formuła** wprowadź **CASE(@.LevelByLookup, TaxationLevel.'Regular taxation', "Regular", TaxationLevel.'Reduced taxation', "Reduced", TaxationLevel.'No taxation', "None", "Other")**.</span><span class="sxs-lookup"><span data-stu-id="36812-302">In the **Formula** field, enter **CASE(@.LevelByLookup, TaxationLevel.'Regular taxation', "Regular", TaxationLevel.'Reduced taxation', "Reduced", TaxationLevel.'No taxation', "None", "Other")**.</span></span>

    ![Strona projektanta operacji ER](./media/RCS-AppSpecParms-ConfigureFormat-ChangeLookupFld.PNG)
    
    <span data-ttu-id="36812-304">Zwróć uwagę, że wyrażenie w polu **Model.Data.Summary.Level** zwróci teraz poziom opodatkowania na podstawie kodu podatku bieżącego rekordu oraz zbioru reguł, które użytkownik biznes skonfigurowa w **Model.Data.Selector** wyszukiwaniu źródła danych.</span><span class="sxs-lookup"><span data-stu-id="36812-304">Notice that the expression of the **Model.Data.Summary.Level** field will now return the taxation level, based on the tax code of the current record and the set of rules that that a business user configures in the **Model.Data.Selector** lookup data source.</span></span>
    
5.  <span data-ttu-id="36812-305">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="36812-305">Select **Save**.</span></span>
6.  <span data-ttu-id="36812-306">Zamknij stronę **Projektowanie formuły**.</span><span class="sxs-lookup"><span data-stu-id="36812-306">Close **Formula designer** page.</span></span>
7.  <span data-ttu-id="36812-307">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="36812-307">Select **OK**.</span></span>
8.  <span data-ttu-id="36812-308">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="36812-308">Select **Save**.</span></span>
9.  <span data-ttu-id="36812-309">Zamknij stronę **Projektant formatu**.</span><span class="sxs-lookup"><span data-stu-id="36812-309">Close **Format designer** page.</span></span>

## <a name="complete-the-draft-version-of-a-derived-format"></a><span data-ttu-id="36812-310">Pełna skorygowana wersja robocza pochodnego formatu</span><span class="sxs-lookup"><span data-stu-id="36812-310">Complete the draft version of a derived format</span></span>

1.  <span data-ttu-id="36812-311">W obszarze **wersje** na skróconej karcie wybierz opcję **Zmień stan**.</span><span class="sxs-lookup"><span data-stu-id="36812-311">On the **Versions** fast tab, select **Change status**.</span></span>
2.  <span data-ttu-id="36812-312">Wybierz opcję **Zakończone**.</span><span class="sxs-lookup"><span data-stu-id="36812-312">Select **Complete**.</span></span>
3.  <span data-ttu-id="36812-313">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="36812-313">Select **OK**.</span></span>

## <a name="export-completed-version-of-modified-format"></a><span data-ttu-id="36812-314">Eksport skończonej wersji formatu zmodyfikowanego</span><span class="sxs-lookup"><span data-stu-id="36812-314">Export completed version of modified format</span></span>

1.  <span data-ttu-id="36812-315">W drzewie konfigurację wybierz **Format, aby uzyskać informacje o wyszukiwaniu danych LE**.</span><span class="sxs-lookup"><span data-stu-id="36812-315">In the configuration tree, select the **Format to learn how to lookup LE data** item.</span></span>
2.  <span data-ttu-id="36812-316">Na karcie **wersje** szybkie wybierz rekord o stanie **zakończone**.</span><span class="sxs-lookup"><span data-stu-id="36812-316">On the **Versions** fast tab, select the record that has a status of **Completed**.</span></span>
3.  <span data-ttu-id="36812-317">Wybierz **Zamień**.</span><span class="sxs-lookup"><span data-stu-id="36812-317">Select **Exchange**.</span></span>
4.  <span data-ttu-id="36812-318">Wybierz **Eksportuj jako plik XML**.</span><span class="sxs-lookup"><span data-stu-id="36812-318">Select **Export as XML file**.</span></span>
5.  <span data-ttu-id="36812-319">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="36812-319">Select **OK**.</span></span>
6.  <span data-ttu-id="36812-320">Przeglądarka sieci Web pobiera **Format, aby uzyskać informacje o wyszukiwaniu danych LE.xml**.</span><span class="sxs-lookup"><span data-stu-id="36812-320">The web browser downloads a **Format to learn how to lookup LE data.xml** file.</span></span> <span data-ttu-id="36812-321">Zapisz ten plik lokalnie.</span><span class="sxs-lookup"><span data-stu-id="36812-321">Store this file locally.</span></span>

<span data-ttu-id="36812-322">Powtórz kroki w tej sekcji dla elementów nadrzędnych **Format, aby uzyskać informacje o wyszukiwaniu danych LE** i lokalnie zapisać następujące pliki:</span><span class="sxs-lookup"><span data-stu-id="36812-322">Repeat steps in this section for parent items of the **Format to learn how to lookup LE data** format, and store the following files locally:</span></span>

-   <span data-ttu-id="36812-323">Wybierz opcję Format do nauczenia sparametryzowanych wywołań.xml</span><span class="sxs-lookup"><span data-stu-id="36812-323">Format to learn parameterized calls.xml</span></span>
-   <span data-ttu-id="36812-324">Wybierz opcję mapowanie, aby poznać wywołania sparametryzowane.xml</span><span class="sxs-lookup"><span data-stu-id="36812-324">Mapping to learn parameterized calls.xml</span></span>
-   <span data-ttu-id="36812-325">Model do nauczenia sparametryzowanych wywołań.xml</span><span class="sxs-lookup"><span data-stu-id="36812-325">Model to learn parameterized calls.xml</span></span>

<span data-ttu-id="36812-326">Aby dowiedzieć się, jak wyszukać format ER **Format, aby uzyskać informacje o wyszukiwaniu danych LE** skonfigurować zestawy kodów podatkowych zależne od podmiotu prawnego w celu filtrowania transakcji podatkowych według różnych poziomów opodatkowania należy wykonać kroki opisane w temacie [Umożliwia konfigurowanie parametrów formatu ER dla firmy](er-app-specific-parameters-set-up.md).</span><span class="sxs-lookup"><span data-stu-id="36812-326">To learn how to use the configured **Format to learn how to lookup LE data** ER format to set up legal entity–dependent sets of tax codes to filter tax transactions by different taxation levels, complete the steps in the [Set up the parameters of an ER format per legal entity](er-app-specific-parameters-set-up.md) topic.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="36812-327">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="36812-327">Additional resources</span></span>

[<span data-ttu-id="36812-328">Projektant formuł w module Raportowanie elektroniczne</span><span class="sxs-lookup"><span data-stu-id="36812-328">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="36812-329">Umożliwia konfigurowanie parametrów formatu ER dla firmy</span><span class="sxs-lookup"><span data-stu-id="36812-329">Set up the parameters of an ER format per legal entity</span></span>](er-app-specific-parameters-set-up.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]