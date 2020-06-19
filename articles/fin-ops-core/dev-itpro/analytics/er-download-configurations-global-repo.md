---
title: Pobieranie konfiguracji ER z globalnego repozytorium usługi Configuration service
description: W tym temacie opisano sposób pobierania konfiguracji raportowania elektronicznego (ER) z globalnego repozytorium usługi Configuration service.
author: NickSelin
manager: AnnBe
ms.date: 06/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionImport, ERWorkspace, ERSolutionRepositoryTable
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: ed31cdee74c9db26ba76ed263b5e0578cd04bc3d
ms.sourcegitcommit: 7816902b59aa61d9183d54b50a86e282661e3971
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/02/2020
ms.locfileid: "3421709"
---
# <a name="download-er-configurations-from-the-global-repository-of-configuration-service"></a><span data-ttu-id="08a12-103">Pobieranie konfiguracji ER z globalnego repozytorium usługi Configuration service</span><span class="sxs-lookup"><span data-stu-id="08a12-103">Download ER configurations from the Global repository of Configuration service</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="08a12-104">W tym temacie opisano sposób pobierania [konfiguracji raportowania elektronicznego (ER)](general-electronic-reporting.md#Configuration) z globalnego repozytorium usługi Configuration service.</span><span class="sxs-lookup"><span data-stu-id="08a12-104">This topic explains how to download [Electronic reporting (ER) configurations](general-electronic-reporting.md#Configuration) from the Global repository of configuration service.</span></span> <span data-ttu-id="08a12-105">Aby uzyskać więcej informacji, należy zapoznać się z tematem [Microsoft Dynamics 365 for Finance and Operations - Regulatory Services, Configuration service](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).</span><span class="sxs-lookup"><span data-stu-id="08a12-105">For more information, see [Microsoft Dynamics 365 for Finance and Operations - Regulatory Services, Configuration service](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).</span></span>

## <a name="open-configurations-repository"></a><span data-ttu-id="08a12-106">Otwieranie repozytorium konfiguracji</span><span class="sxs-lookup"><span data-stu-id="08a12-106">Open configurations repository</span></span>

1. <span data-ttu-id="08a12-107">Zaloguj się do aplikacji Dynamics 365 Finance przy użyciu jednej z następujących ról:</span><span class="sxs-lookup"><span data-stu-id="08a12-107">Sign in to the Dynamics 365 Finance application using one of the following roles:</span></span>

    - <span data-ttu-id="08a12-108">Deweloper raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="08a12-108">Electronic reporting developer</span></span>
    - <span data-ttu-id="08a12-109">Konsultant funkcjonalny raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="08a12-109">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="08a12-110">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="08a12-110">System administrator</span></span>

2. <span data-ttu-id="08a12-111">Wybierz kolejno opcje **Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="08a12-111">Go to **Organization administration > Workspaces > Electronic reporting**.</span></span>
3. <span data-ttu-id="08a12-112">W obszarze **Dostawcy konfiguracji** wybierz kafelek **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="08a12-112">In the **Configuration providers** section, select the **Microsoft** tile.</span></span>
3. <span data-ttu-id="08a12-113">Na kafelku **Microsoft** wybierz **Repozytoria**.</span><span class="sxs-lookup"><span data-stu-id="08a12-113">On the **Microsoft** tile, select **Repositories**.</span></span>

    ![Obszar roboczy raportowania elektronicznego](./media/er-download-configurations-global-repo-er-workspace.png)

4. <span data-ttu-id="08a12-115">Na stronie **Repozytoria konfiguracji** w siatce zaznacz istniejące repozytorium typu **Globalne**.</span><span class="sxs-lookup"><span data-stu-id="08a12-115">On the **Configuration repositories** page, in the grid, select the existing repository of the **Global** type.</span></span> <span data-ttu-id="08a12-116">Jeśli to repozytorium nie jest wyświetlane w siatce, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="08a12-116">If this repository doesn't appear in the grid, follow these steps:</span></span>

    1. <span data-ttu-id="08a12-117">Wybierz **Dodaj**, aby dodać nowe repozytorium.</span><span class="sxs-lookup"><span data-stu-id="08a12-117">Select **Add** to add a new repository.</span></span>
    2. <span data-ttu-id="08a12-118">Wybierz pozycję **Globalne** jako typ repozytorium, a następnie wybierz opcję **Utwórz repozytorium**.</span><span class="sxs-lookup"><span data-stu-id="08a12-118">Select **Global** as the repository type, and then select **Create repository**.</span></span>
    3. <span data-ttu-id="08a12-119">W przypadku wyświetlenia monitu postępuj zgodnie z instrukcjami autoryzacji.</span><span class="sxs-lookup"><span data-stu-id="08a12-119">If prompted, follow the authorization instructions.</span></span>
    4. <span data-ttu-id="08a12-120">Wprowadź nazwę i opis repozytorium, a następnie kliknij przycisk **OK**, aby potwierdzić nowy wpis repozytorium.</span><span class="sxs-lookup"><span data-stu-id="08a12-120">Enter a name and description for the repository and then select **OK** to confirm the new repository entry.</span></span>
    5. <span data-ttu-id="08a12-121">W siatce wybierz nowe repozytorium typu **Globalne**.</span><span class="sxs-lookup"><span data-stu-id="08a12-121">In the grid, select the new repository of the **Global** type.</span></span>

5. <span data-ttu-id="08a12-122">Wybierz **Otwórz**, aby wyświetlić listę konfiguracji modułu ER dla wybranego repozytorium.</span><span class="sxs-lookup"><span data-stu-id="08a12-122">Select **Open** to view the list of ER configurations for the selected repository.</span></span>

    ![Strona repozytorium konfiguracji](./media/er-download-configurations-global-repo-repositories-list.png)

## <a name="import-a-single-configuration"></a><span data-ttu-id="08a12-124">Importowanie pojedyńczej konfiguracji</span><span class="sxs-lookup"><span data-stu-id="08a12-124">Import a single configuration</span></span>

1. <span data-ttu-id="08a12-125">Na stronie **Repozytoria konfiguracji** w drzewie konfiguracje wybierz żądaną konfigurację encji.</span><span class="sxs-lookup"><span data-stu-id="08a12-125">On the **Configuration repositories** page, in the configurations tree, select the ER configuration that you want.</span></span>
2. <span data-ttu-id="08a12-126">Na skróconej karcie **Wersje** wybierz wymaganą wersję wybranej konfiguracji ER.</span><span class="sxs-lookup"><span data-stu-id="08a12-126">On the **Versions** FastTab, select the required version of the selected ER configuration.</span></span>
3. <span data-ttu-id="08a12-127">Wybierz **Importuj**, aby pobrać wybraną wersję z Globalnego repozytorium do bieżącego wystąpienia Finance.</span><span class="sxs-lookup"><span data-stu-id="08a12-127">Select **Import** to download the selected version from Global repository to the current Finance instance.</span></span>

    > [!NOTE]
    > <span data-ttu-id="08a12-128">Przycisk **Importuj** jest niedostępny dla wersji konfiguracji ER, które już się znajdują w bieżącym wystąpieniu Finance.</span><span class="sxs-lookup"><span data-stu-id="08a12-128">The **Import** button is unavailable for ER configuration versions that are already present in the current Finance instance.</span></span>

    ![Strona Repozytorium konfiguracji](./media/er-download-configurations-global-repo-repository-content.png)

## <a name="import-filtered-configurations"></a><span data-ttu-id="08a12-130">Importowanie filtrowanej konfiguracji</span><span class="sxs-lookup"><span data-stu-id="08a12-130">Import filtered configurations</span></span>

1. <span data-ttu-id="08a12-131">Na stronie **Repozytoria konfiguracji** w drzewie konfiguracje rozwiń skróconą kartę **Filtruj**.</span><span class="sxs-lookup"><span data-stu-id="08a12-131">On the **Configuration repositories** page, in the configurations tree, expand the **Filter** FastTab.</span></span>
2. <span data-ttu-id="08a12-132">W siatce **Znaczniki** dodaj potrzebne znaczniki.</span><span class="sxs-lookup"><span data-stu-id="08a12-132">In the **Tags** grid, add any tags that are needed.</span></span>
3. <span data-ttu-id="08a12-133">W polu **Zastosowanie kraju/regionu** wybierz odpowiednie kody krajów/regionów, a następnie wybierz opcję **Zastosuj filtr**.</span><span class="sxs-lookup"><span data-stu-id="08a12-133">In the **Country/region applicability** field, select the appropriate country/region codes, and then select  **Apply filter**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="08a12-134">Na skróconej karcie **Konfiguracje** są wyświetlane wszystkie konfiguracje spełniające określone warunki wyboru.</span><span class="sxs-lookup"><span data-stu-id="08a12-134">The **Configurations** FastTab shows all the configurations that satisfy the specified selection conditions.</span></span>

4. <span data-ttu-id="08a12-135">Na skróconej karcie **Konfiguracje** wybierz opcję **Importuj**, aby pobrać przefiltrowane konfiguracje z repozytorium globalnego do bieżącego wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="08a12-135">On the **Configurations** FastTab, select **Import** to download the filtered configurations from the Global repository to the current instance.</span></span>
5. <span data-ttu-id="08a12-136">Na skróconej karcie **Konfiguracji** wybierz opcję **Resetuj filtr**, aby wyczyścić określone warunki wyboru.</span><span class="sxs-lookup"><span data-stu-id="08a12-136">On the **Configurations** FastTab, select **Reset filter** to clean up the specified selection conditions.</span></span>

    ![Strona Repozytorium konfiguracji](./media/er-download-configurations-global-repo-filtered-configurations.png)

> [!NOTE]
> <span data-ttu-id="08a12-138">W zależności od ustawień ER podczas importowania konfiguracji jest sprawdzana ich poprawność.</span><span class="sxs-lookup"><span data-stu-id="08a12-138">Depending on the ER settings, configurations are validated after they are imported.</span></span> <span data-ttu-id="08a12-139">Możesz otrzymywać powiadomienia o wszelkich wykrytych problemach z niespójnością.</span><span class="sxs-lookup"><span data-stu-id="08a12-139">You might be notified about any inconsistency issues that are discovered.</span></span> <span data-ttu-id="08a12-140">Zanim będzie można użyć zaimportowanej wersji konfiguracji, należy rozwiązać problemy.</span><span class="sxs-lookup"><span data-stu-id="08a12-140">Before you can use the imported configuration version, you must resolve the issues.</span></span> <span data-ttu-id="08a12-141">Aby uzyskać więcej informacji, zobacz listę pokrewnych zasobów do tego tematu.</span><span class="sxs-lookup"><span data-stu-id="08a12-141">For more information, see the list of related resources for this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="08a12-142">Konfiguracje ER można skonfigurować jako zależne od innych konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="08a12-142">ER configurations can be configured as being dependent on other configurations.</span></span> <span data-ttu-id="08a12-143">Dlatego też, wraz z wybraną konfiguracją, inne konfiguracje mogą być importowane automatycznie.</span><span class="sxs-lookup"><span data-stu-id="08a12-143">Therefore, along with a selected configuration, other configurations might be automatically imported.</span></span> <span data-ttu-id="08a12-144">Więcej informacji o zależnościach konfiguracji zawiera sekcja [Definiowanie zależności konfiguracji raportowania elektronicznego od innych składników](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md).</span><span class="sxs-lookup"><span data-stu-id="08a12-144">For more about configuration dependencies, see [Define the dependency of ER configurations on other components](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="08a12-145">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="08a12-145">Additional resources</span></span>

[<span data-ttu-id="08a12-146">Omówienie raportowania elektronicznego (ER)</span><span class="sxs-lookup"><span data-stu-id="08a12-146">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
