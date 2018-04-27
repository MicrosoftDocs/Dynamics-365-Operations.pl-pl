---
title: "Dodawanie analizy do obszarów roboczych za pomocą usługi Power BI Embedded"
description: "W tym temacie przedstawiono sposób osadzenia raportu programu Power BI na karcie Analizy w obszarze roboczym."
author: tjvass
manager: AnnBe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application user, IT Pro
ms.reviewer: robinr
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: d8cd3a6b3cbfa1219f0ebcf9d4d2132197167220
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---

# <a name="add-analytics-to-workspaces-by-using-power-bi-embedded"></a><span data-ttu-id="953ed-103">Dodawanie analizy do obszarów roboczych za pomocą usługi Power BI Embedded</span><span class="sxs-lookup"><span data-stu-id="953ed-103">Add analytics to workspaces by using Power BI Embedded</span></span>

[!INCLUDE [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="953ed-104">Ta funkcja jest obsługiwana w programie Dynamics 365 for Finance and Operations (w wersji 7.2 i nowszych).</span><span class="sxs-lookup"><span data-stu-id="953ed-104">This feature is supported in Dynamics 365 for Finance and Operations (version 7.2 and later).</span></span>

## <a name="introduction"></a><span data-ttu-id="953ed-105">Wprowadzenie</span><span class="sxs-lookup"><span data-stu-id="953ed-105">Introduction</span></span>
<span data-ttu-id="953ed-106">W tym temacie przedstawiono sposób osadzenia raportu programu Microsoft Power BI na karcie **Analizy** w obszarze roboczym.</span><span class="sxs-lookup"><span data-stu-id="953ed-106">This topic shows how to embed a Microsoft Power BI report on the **Analytics** tab of a workspace.</span></span> <span data-ttu-id="953ed-107">W przedstawionym tutaj przykładzie rozszerzymy obszar roboczy **Zarządzanie rezerwacjami** w aplikacji Zarządzanie flotą w celu osadzenia analitycznego obszaru roboczego na karcie **Analizy**.</span><span class="sxs-lookup"><span data-stu-id="953ed-107">For the example that is given here, we will extend the **Reservation management** workspace in the Fleet Management application to embed an analytical workspace on an **Analytics** tab.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="953ed-108">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="953ed-108">Prerequisites</span></span>
+ <span data-ttu-id="953ed-109">Dostęp do środowiska deweloperskiego, w którym działa aktualizacja platformy 8 lub nowsza.</span><span class="sxs-lookup"><span data-stu-id="953ed-109">Access to a developer environment that runs Platform update 8 or later.</span></span>
+ <span data-ttu-id="953ed-110">Raport analityczny (plik .pbix), który został utworzony przy użyciu aplikacji Microsoft Power BI Desktop i ma model danych pochodzący z bazy danych magazynu jednostek.</span><span class="sxs-lookup"><span data-stu-id="953ed-110">An analytical report (.pbix file) that was created by using Microsoft Power BI Desktop, and that has a data model that is sourced from the Entity store database.</span></span>

## <a name="overview"></a><span data-ttu-id="953ed-111">Przegląd</span><span class="sxs-lookup"><span data-stu-id="953ed-111">Overview</span></span>
<span data-ttu-id="953ed-112">Niezależnie od tego, czy rozszerzasz istniejący obszar roboczy aplikacji, czy wprowadzasz nowy własny obszar roboczy, możesz za pomocą osadzonych widoków analitycznych przekazywać wnikliwy i interaktywny obraz danych biznesowych.</span><span class="sxs-lookup"><span data-stu-id="953ed-112">Whether you extend an existing application workspace or introduce a new workspace of your own, you can use embedded analytical views to deliver insightful and interactive views of your business data.</span></span> <span data-ttu-id="953ed-113">Proces dodawania karty analitycznego obszaru roboczego składa się z czterech etapów.</span><span class="sxs-lookup"><span data-stu-id="953ed-113">The process for adding an analytical workspace tab has four steps.</span></span>

1. <span data-ttu-id="953ed-114">Dodanie pliku .pbix jako zasobu usługi Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="953ed-114">Add a .pbix file as a Dynamics 365 resource.</span></span>
2. <span data-ttu-id="953ed-115">Zdefiniowanie karty analitycznego obszaru roboczego.</span><span class="sxs-lookup"><span data-stu-id="953ed-115">Define an analytical workspace tab.</span></span>
3. <span data-ttu-id="953ed-116">Osadzenie zasobu .pbix na karcie obszaru roboczego.</span><span class="sxs-lookup"><span data-stu-id="953ed-116">Embed the .pbix resource on the workspace tab.</span></span>
4. <span data-ttu-id="953ed-117">Opcjonalnie: Dodanie rozszerzeń w celu dostosowania widoku.</span><span class="sxs-lookup"><span data-stu-id="953ed-117">Optional: Add extensions to customize the view.</span></span>

> [!NOTE]
> <span data-ttu-id="953ed-118">Aby uzyskać więcej informacji na temat tworzenia raportów analitycznych, zobacz [Wprowadzenie do programu Power BI Desktop](https://powerbi.microsoft.com/en-us/documentation/powerbi-desktop-getting-started/).</span><span class="sxs-lookup"><span data-stu-id="953ed-118">For more information about how to create analytical reports, see [Getting started with Power BI Desktop](https://powerbi.microsoft.com/en-us/documentation/powerbi-desktop-getting-started/).</span></span> <span data-ttu-id="953ed-119">Ta strona jest świetnym źródłem informacji, które mogą pomóc tworzyć zaawansowane rozwiązania do sprawozdawczości analitycznej.</span><span class="sxs-lookup"><span data-stu-id="953ed-119">This page is a great source for insights that can help you create compelling analytical reporting solutions.</span></span>

## <a name="add-a-pbix-file-as-a-resource"></a><span data-ttu-id="953ed-120">Dodanie pliku .pbix jako zasobu</span><span class="sxs-lookup"><span data-stu-id="953ed-120">Add a .pbix file as a resource</span></span>
<span data-ttu-id="953ed-121">Przed rozpoczęciem należy utworzyć lub pozyskać raport programu Power BI, który zostanie osadzony w obszarze roboczym.</span><span class="sxs-lookup"><span data-stu-id="953ed-121">Before you begin, you must create or obtain the Power BI report that you will embed in the workspace.</span></span> <span data-ttu-id="953ed-122">Aby uzyskać więcej informacji na temat tworzenia raportów analitycznych, zobacz [Wprowadzenie do programu Power BI Desktop](https://powerbi.microsoft.com/en-us/documentation/powerbi-desktop-getting-started/).</span><span class="sxs-lookup"><span data-stu-id="953ed-122">For more information about how to create analytical reports, see [Getting started with Power BI Desktop](https://powerbi.microsoft.com/en-us/documentation/powerbi-desktop-getting-started/).</span></span>

<span data-ttu-id="953ed-123">Wykonaj poniższe kroki, aby dodać plik .pbix jako artefakt projektu programu Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="953ed-123">Follow these steps to add a .pbix file as a Visual Studio project artifact.</span></span>

1. <span data-ttu-id="953ed-124">Utwórz nowy projekt w odpowiednim modelu.</span><span class="sxs-lookup"><span data-stu-id="953ed-124">Create a new project in the appropriate model.</span></span>
2. <span data-ttu-id="953ed-125">W Eksploratorze rozwiązań zaznacz projekt, kliknij go prawym przyciskiem myszy, a następnie wybierz kolejno polecenia **Dodaj** > **Nowy element**.</span><span class="sxs-lookup"><span data-stu-id="953ed-125">In Solution Explorer, select the project, right-click, and then select **Add** > **New Item**.</span></span>
3. <span data-ttu-id="953ed-126">W oknie dialogowym **Dodaj nowy element** w obszarze **Artefakty operacji** zaznacz szablon **Zasób**.</span><span class="sxs-lookup"><span data-stu-id="953ed-126">In the **Add New Item** dialog box, under **Operations Artifacts**, select the **Resource** template.</span></span>
4. <span data-ttu-id="953ed-127">Wprowadź nazwę, która będzie służyć to odwoływania się do raportu w metadanych języka X++, a następnie kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="953ed-127">Enter a name that will be used to reference the report in X++ metadata, and then click **Add**.</span></span>

    ![Okno dialogowe Dodaj nowy element](media/analytical-workspace-add.png)

5. <span data-ttu-id="953ed-129">Znajdź plik .pbix zawierający definicję raportu analitycznego, a następnie kliknij przycisk **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="953ed-129">Find the .pbix file that contains the definition of the analytical report, and then click **Open**.</span></span>

    ![Okno dialogowe Wybierz plik zasobów](media/analytical-workspace-select-resource.png)

<span data-ttu-id="953ed-131">Teraz gdy masz dodany plik .pbix jako zasób usługi Dynamics 365, można osadzać raporty w obszarach roboczych i dodawać bezpośrednie łącza do nich przy użyciu elementów menu.</span><span class="sxs-lookup"><span data-stu-id="953ed-131">Now that you've added the .pbix file as a Dynamics 365 resource, you can embed the reports in workspaces and add direct links by using menu items.</span></span>

## <a name="add-a-tab-control-to-an-application-workspace"></a><span data-ttu-id="953ed-132">Dodawanie formantu karty do obszaru roboczego aplikacji</span><span class="sxs-lookup"><span data-stu-id="953ed-132">Add a tab control to an application workspace</span></span>
<span data-ttu-id="953ed-133">W tym przykładzie rozszerzymy obszar roboczy **Zarządzanie rezerwacjami** w modelu Zarządzanie flotą poprzez dodanie karty **Analizy** do definicji formularza **FMClerkWorkspace**.</span><span class="sxs-lookup"><span data-stu-id="953ed-133">In this example, we will extend the **Reservation management** workspace in the Fleet Management model by adding the **Analytics** tab to the definition of the **FMClerkWorkspace** form.</span></span>

<span data-ttu-id="953ed-134">Na poniższej ilustracji widać, jak formularz **FMClerkWorkspace** wygląda w projektancie w programie Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="953ed-134">The following illustration shows what the **FMClerkWorkspace** form looks like in the designer in Microsoft Visual Studio.</span></span>

![Formularz FMClerkWorkspace przed zmianami](media/analytical-workspace-definition-before.png)

<span data-ttu-id="953ed-136">Wykonaj następujące kroki w celu rozszerzenia definicji formularza dla obszaru roboczego **Zarządzanie rezerwacjami**.</span><span class="sxs-lookup"><span data-stu-id="953ed-136">Follow these steps to extend the form definition for the **Reservation management** workspace.</span></span>

1. <span data-ttu-id="953ed-137">Otwórz projektanta formularzy w celu rozszerzenia definicji projektu.</span><span class="sxs-lookup"><span data-stu-id="953ed-137">Open the form designer to extend the design definition.</span></span>
2. <span data-ttu-id="953ed-138">W definicji projektu zaznacz górny element o nazwie **Projekt | Wzorzec: Działający obszar roboczy**.</span><span class="sxs-lookup"><span data-stu-id="953ed-138">In the design definition, select the top element that is labeled **Design | Pattern: Workspace Operational**.</span></span>
3. <span data-ttu-id="953ed-139">Kliknij prawym przyciskiem myszy, a następnie wybierz kolejno opcje **Nowy** > **Karta**, aby dodać nowy formant o nazwie **FormTabControl1**.</span><span class="sxs-lookup"><span data-stu-id="953ed-139">Right-click, and then select **New** > **Tab** to add a new control that is named **FormTabControl1**.</span></span>
4. <span data-ttu-id="953ed-140">W projektancie formularza wybierz opcję **FormTabControl1**.</span><span class="sxs-lookup"><span data-stu-id="953ed-140">In the form designer, select **FormTabControl1**.</span></span>
5. <span data-ttu-id="953ed-141">Kliknij prawym przyciskiem myszy, a następnie wybierz opcję **Strona nowej karty**, aby dodać nową kartę.</span><span class="sxs-lookup"><span data-stu-id="953ed-141">Right-click, and then select **New Tab Page** to add a new tab page.</span></span>
6. <span data-ttu-id="953ed-142">Zmień nazwę karty na bardziej sugestywną, taką jak **Obszar roboczy**.</span><span class="sxs-lookup"><span data-stu-id="953ed-142">Rename the tab page to something meaningful, such as **Workspace**.</span></span>
7. <span data-ttu-id="953ed-143">W projektancie formularza wybierz opcję **FormTabControl1**.</span><span class="sxs-lookup"><span data-stu-id="953ed-143">In the form designer, select **FormTabControl1**.</span></span>
8. <span data-ttu-id="953ed-144">Kliknij prawym przyciskiem myszy, a następnie wybierz opcję **Strona nowej karty**.</span><span class="sxs-lookup"><span data-stu-id="953ed-144">Right-click, and then select **New Tab Page**.</span></span>
9. <span data-ttu-id="953ed-145">Zmień nazwę karty na bardziej sugestywną, taką jak **Analizy**.</span><span class="sxs-lookup"><span data-stu-id="953ed-145">Rename the tab page to something meaningful, such as **Analytics**.</span></span>
10. <span data-ttu-id="953ed-146">W projektancie formularza wybierz opcję **Analizy (karta)**.</span><span class="sxs-lookup"><span data-stu-id="953ed-146">In the form designer, select **Analytics (Tab Page)**.</span></span>
11. <span data-ttu-id="953ed-147">We właściwości **Podpis** ustaw wartość **Analizy**.</span><span class="sxs-lookup"><span data-stu-id="953ed-147">Set the **Caption** property to **Analytics**.</span></span>
12. <span data-ttu-id="953ed-148">Kliknij formant prawym przyciskiem myszy, a następnie wybierz kolejno opcje **Nowy** > **Grupa**, aby dodać nowy formant grupy formularzy.</span><span class="sxs-lookup"><span data-stu-id="953ed-148">Right-click the control, and then select **New** > **Group** to add a new form group control.</span></span>
13. <span data-ttu-id="953ed-149">Zmień nazwę grupy formularzy na bardziej sugestywną, taką jak **powerBIReportGroup**.</span><span class="sxs-lookup"><span data-stu-id="953ed-149">Rename the form group to something meaningful, such as **powerBIReportGroup**.</span></span>
14. <span data-ttu-id="953ed-150">W projektancie formularza wybierz opcję **PanoramaBody (karta)**, a następnie przeciągnij formant na kartę **Obszar roboczy**.</span><span class="sxs-lookup"><span data-stu-id="953ed-150">In the form designer, select **PanoramaBody (Tab)**, and then drag the control onto the **Workspace** tab.</span></span>
15. <span data-ttu-id="953ed-151">W definicji projektu zaznacz górny element o nazwie **Projekt | Wzorzec: Działający obszar roboczy**.</span><span class="sxs-lookup"><span data-stu-id="953ed-151">In the design definition, select the top element that is labeled **Design | Pattern: Workspace Operational**.</span></span>
16. <span data-ttu-id="953ed-152">Kliknij prawym przyciskiem myszy, a następnie wybierz opcję **Usuń wzorzec**.</span><span class="sxs-lookup"><span data-stu-id="953ed-152">Right-click, and then select **Remove pattern**.</span></span>
17. <span data-ttu-id="953ed-153">Ponownie kliknij prawym przyciskiem myszy, a następnie wybierz kolejno opcje **Dodaj wzorzec** > **Obszar roboczy na kartach**.</span><span class="sxs-lookup"><span data-stu-id="953ed-153">Right-click again, and then select **Add pattern** > **Workspace Tabbed**.</span></span>
18. <span data-ttu-id="953ed-154">Wykonaj kompilację, aby sprawdzić działanie wprowadzonych zmian.</span><span class="sxs-lookup"><span data-stu-id="953ed-154">Perform a build to verify your changes.</span></span>

<span data-ttu-id="953ed-155">Na poniższej ilustracji widać, jak projekt wygląda po zastosowaniu tych zmian.</span><span class="sxs-lookup"><span data-stu-id="953ed-155">The following illustration shows what the design looks like after these changes are applied.</span></span>

![Formularz FMClerkWorkspace po zmianach](media/analytical-workspace-definition-after.png)

<span data-ttu-id="953ed-157">Teraz gdy masz dodane formanty formularza, które będą używany do osadzania raportu w obszarze roboczym, należy zdefiniować rozmiar formantu nadrzędnego, aby zmieścił układ.</span><span class="sxs-lookup"><span data-stu-id="953ed-157">Now that you've added the form controls that will be used to embed the workspace report, you must define the size of the parent control so that it accommodates the layout.</span></span> <span data-ttu-id="953ed-158">Domyślnie w raporcie będą widoczne strony **Okienko filtrów** i **Karta**.</span><span class="sxs-lookup"><span data-stu-id="953ed-158">By default, both the **Filters Pane** page and the **Tab** page will be visible on the report.</span></span> <span data-ttu-id="953ed-159">Można jednak zmienić widoczność tych formantów zgodnie z potrzebami docelowego odbiorcy raportu.</span><span class="sxs-lookup"><span data-stu-id="953ed-159">However, you can change the visibility of these controls as appropriate for the target consumer of the report.</span></span>

> [!NOTE]
> <span data-ttu-id="953ed-160">W przypadku osadzonych obszarów roboczych zalecamy, aby dla zachowania spójności za pomocą rozszerzeń ukryć strony **Okienko filtrów** i **Karta**.</span><span class="sxs-lookup"><span data-stu-id="953ed-160">For embedded workspaces, we recommend that you use extensions to hide both the **Filters Pane** and **Tab** pages, for consistency.</span></span>

<span data-ttu-id="953ed-161">Zadanie rozszerzania definicji formularza raportu zostało zakończone.</span><span class="sxs-lookup"><span data-stu-id="953ed-161">You've now completed the task of extending the application form definition.</span></span> <span data-ttu-id="953ed-162">Aby uzyskać więcej informacji o używaniu rozszerzeń do wprowadzania dostosowań, zobacz [Dostosowywanie: Nakładanie i rozszerzenia](../extensibility/customization-overlayering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="953ed-162">For more information about how to use extensions to do customizations, see  [Customization: Overlayering and extensions](../extensibility/customization-overlayering-extensions.md).</span></span>

## <a name="add-x-business-logic-to-embed-a-viewer-control"></a><span data-ttu-id="953ed-163">Dodawanie logiki biznesowej języka X++ w celu osadzenia formantu podglądu</span><span class="sxs-lookup"><span data-stu-id="953ed-163">Add X++ business logic to embed a viewer control</span></span>
<span data-ttu-id="953ed-164">Wykonaj następujące kroki, aby dodać logikę biznesową, która inicjuje formant podglądu raportów znajdujący się w obszarze roboczym **Zarządzanie rezerwacjami**.</span><span class="sxs-lookup"><span data-stu-id="953ed-164">Follow these steps to add business logic that initializes the report viewer control that is embedded in the **Reservation management** workspace.</span></span>

1. <span data-ttu-id="953ed-165">Otwórz projektanta formularza **FMClerkWorkspace** w celu rozszerzenia definicji projektu.</span><span class="sxs-lookup"><span data-stu-id="953ed-165">Open the **FMClerkWorkspace** form designer to extend the design definition.</span></span>
2. <span data-ttu-id="953ed-166">Naciśnij klawisz F7, aby uzyskać dostęp do kodu źródłowego kryjącego się za definicją kodu.</span><span class="sxs-lookup"><span data-stu-id="953ed-166">Press F7 to access the code behind the code definition.</span></span>
3. <span data-ttu-id="953ed-167">Dodaj następujący kod źródłowy języka X++.</span><span class="sxs-lookup"><span data-stu-id="953ed-167">Add the following X++ code.</span></span>

    ```
    [Form] 
    public class FMClerkWorkspace extends FormRun
    {
        private boolean initReportControl = true;     
        protected void initAnalyticalReport()
        {
            if (!initReportControl)
            {
                return;
            }
            // Note: secure entry point into the Workspace's Analytics report
            if (Global::hasMenuItemAccess(menuItemDisplayStr(FMClerkWorkspace), MenuItemType::Display))
            {
                FMPBIWorkspaceController controller = new FMPBIWorkspaceController();
                PBIReportHelper::initializeReportControl('FMPBIWorkspaces', powerBIReportGroup);
            }
            initReportControl = false;
    }
        /// <summary>
        /// Initializes the form.
        /// </summary>
        public void init()
        {
            super();
            this.initAnalyticalReport();
        }
    }
    ```

4. <span data-ttu-id="953ed-168">Wykonaj kompilację, aby sprawdzić działanie wprowadzonych zmian.</span><span class="sxs-lookup"><span data-stu-id="953ed-168">Perform a build to verify your changes.</span></span>

<span data-ttu-id="953ed-169">Zadanie dodawania logiki biznesowej inicjującej formant podglądu osadzonego raportu zostało zakończone.</span><span class="sxs-lookup"><span data-stu-id="953ed-169">You've now completed the task of adding business logic to initialize the embedded report viewer control.</span></span> <span data-ttu-id="953ed-170">Na poniższej ilustracji widać, jak obszar roboczy wygląda po zastosowaniu tych zmian.</span><span class="sxs-lookup"><span data-stu-id="953ed-170">The following illustration shows what the workspace looks like after these changes are applied.</span></span>

![Raport osadzony w obszarze roboczym](media/analytical-workspace-final.png)

> [!NOTE]
> <span data-ttu-id="953ed-172">Korzystając z kart obszaru roboczego pod tytułem strony, można przejść do istniejącego widoku operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="953ed-172">You can access the existing operational view by using the workspace tabs below the page title.</span></span>

## <a name="reference"></a><span data-ttu-id="953ed-173">Odwołanie</span><span class="sxs-lookup"><span data-stu-id="953ed-173">Reference</span></span>

### <a name="pbireporthelperinitializereportcontrol-method"></a><span data-ttu-id="953ed-174">Metoda PBIReportHelper.initializeReportControl</span><span class="sxs-lookup"><span data-stu-id="953ed-174">PBIReportHelper.initializeReportControl method</span></span>
<span data-ttu-id="953ed-175">Ten rozdział zawiera informacje o klasie pomocy służącej do osadzania raportu programu Power BI (zasobu .pbix) w formancie grupy formularzy.</span><span class="sxs-lookup"><span data-stu-id="953ed-175">This section provides information about the helper class that is used to embed a Power BI report (.pbix resource) in a form group control.</span></span>

#### <a name="syntax"></a><span data-ttu-id="953ed-176">Składnia</span><span class="sxs-lookup"><span data-stu-id="953ed-176">Syntax</span></span>
```
public static void initializeReportControl(
     str                 _resourceName,
     FormGroupControl    _formGroupControl,
     str                 _defaultPageName = '',
     boolean             _showFilterPane = false,
     boolean             _showNavPane = false,
     List                _defaultFilters = new List(Types::Class))
```

#### <a name="parameters"></a><span data-ttu-id="953ed-177">Parametry</span><span class="sxs-lookup"><span data-stu-id="953ed-177">Parameters</span></span>

|       <span data-ttu-id="953ed-178">Nazwisko</span><span class="sxs-lookup"><span data-stu-id="953ed-178">Name</span></span>       |                                                              <span data-ttu-id="953ed-179">opis</span><span class="sxs-lookup"><span data-stu-id="953ed-179">Description</span></span>                                                               |
|------------------|----------------------------------------------------------------------------------------------------------------------------------------|
|   <span data-ttu-id="953ed-180">resourceName</span><span class="sxs-lookup"><span data-stu-id="953ed-180">resourceName</span></span>   |                                                    <span data-ttu-id="953ed-181">Nazwa zasobu .pbix.</span><span class="sxs-lookup"><span data-stu-id="953ed-181">The name of the .pbix resource.</span></span>                                                     |
| <span data-ttu-id="953ed-182">formGroupControl</span><span class="sxs-lookup"><span data-stu-id="953ed-182">formGroupControl</span></span> |                                    <span data-ttu-id="953ed-183">Formant grupy formularzy, do którego ma zostać zastosowany formant raportu narzędzia Power BI.</span><span class="sxs-lookup"><span data-stu-id="953ed-183">The form group control to apply the Power BI report control to.</span></span>                                     |
| <span data-ttu-id="953ed-184">defaultPageName</span><span class="sxs-lookup"><span data-stu-id="953ed-184">defaultPageName</span></span>  |                                                         <span data-ttu-id="953ed-185">Domyślna nazwa strony.</span><span class="sxs-lookup"><span data-stu-id="953ed-185">The default page name.</span></span>                                                         |
|  <span data-ttu-id="953ed-186">showFilterPane</span><span class="sxs-lookup"><span data-stu-id="953ed-186">showFilterPane</span></span>  |   <span data-ttu-id="953ed-187">Wartość logiczna wskazująca, czy okienko filtrów powinno być wyświetlane (<strong>true</strong>), czy ukryte (<strong>false</strong>).</span><span class="sxs-lookup"><span data-stu-id="953ed-187">A Boolean value that indicates whether the filter pane should be shown (<strong>true</strong>) or hidden (<strong>false</strong>).</span></span>   |
|   <span data-ttu-id="953ed-188">showNavPane</span><span class="sxs-lookup"><span data-stu-id="953ed-188">showNavPane</span></span>    | <span data-ttu-id="953ed-189">Wartość logiczna wskazująca, czy okienko nawigacji powinno być wyświetlane (<strong>true</strong>), czy ukryte (<strong>false</strong>).</span><span class="sxs-lookup"><span data-stu-id="953ed-189">A Boolean value that indicates whether the navigation pane should be shown (<strong>true</strong>) or hidden (<strong>false</strong>).</span></span> |
|  <span data-ttu-id="953ed-190">defaultFilters</span><span class="sxs-lookup"><span data-stu-id="953ed-190">defaultFilters</span></span>  |                                              <span data-ttu-id="953ed-191">Domyślne filtry raportu programu Power BI.</span><span class="sxs-lookup"><span data-stu-id="953ed-191">The default filters for the Power BI report.</span></span>                                              |


