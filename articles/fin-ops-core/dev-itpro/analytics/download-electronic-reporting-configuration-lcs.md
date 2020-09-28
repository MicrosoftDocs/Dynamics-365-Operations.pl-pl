---
title: Pobieranie konfiguracji modułu Raportowanie elektroniczne z usługi Lifecycle Services
description: Ten temat wyjaśnia sposób pobierania konfiguracji modułu Raportowanie elektroniczne (ER) z usługi Microsoft Dynamics Lifecycle Services (LCS).
author: NickSelin
manager: AnnBe
ms.date: 08/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionImport, ERWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 8a18427114bddb7c72024a8d96d33f3fbf8dbe17
ms.sourcegitcommit: 9857d5cbdc0ab2fc9db049ac5ad118fc2b29bedc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/14/2020
ms.locfileid: "3810626"
---
# <a name="download-electronic-reporting-configurations-from-lifecycle-services"></a><span data-ttu-id="ea526-103">Pobieranie konfiguracji Raportowania elektronicznego z usługi Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="ea526-103">Download Electronic reporting configurations from Lifecycle Services</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ea526-104">W tym temacie wyjaśniono, jak pobrać najnowszą wersję [konfiguracji modułu raportowania elektronicznego (ER)](general-electronic-reporting.md#Configuration) z [biblioteki udostępnionych elementów](../lifecycle-services/asset-library.md) w Microsoft Dynamics Lifecycle Service (usługi LCS).</span><span class="sxs-lookup"><span data-stu-id="ea526-104">This topic explains how to download the newest version of [Electronic reporting (ER) configurations](general-electronic-reporting.md#Configuration) from the [Shared asset library](../lifecycle-services/asset-library.md) in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

1. <span data-ttu-id="ea526-105">Zaloguj się do aplikacji przy użyciu jednej z następujących ról:</span><span class="sxs-lookup"><span data-stu-id="ea526-105">Sign in to the application by using one of the following roles:</span></span>

    - <span data-ttu-id="ea526-106">Deweloper raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="ea526-106">Electronic reporting developer</span></span>
    - <span data-ttu-id="ea526-107">Konsultant funkcjonalny raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="ea526-107">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="ea526-108">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="ea526-108">System administrator</span></span>

2. <span data-ttu-id="ea526-109">Wybierz kolejno opcje **Administrowanie organizacją** &gt; **Obszary robocze** &gt; **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="ea526-109">Go to **Organization administration** &gt; **Workspaces** &gt; **Electronic reporting**.</span></span>
3. <span data-ttu-id="ea526-110">W obszarze **Dostawcy konfiguracji** wybierz kafelek **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="ea526-110">In the **Configuration providers** section, select the **Microsoft** tile.</span></span>
4. <span data-ttu-id="ea526-111">Na kafelku **Microsoft** wybierz **Repozytoria**.</span><span class="sxs-lookup"><span data-stu-id="ea526-111">On the **Microsoft** tile, select **Repositories**.</span></span>

    <span data-ttu-id="ea526-112">[![Kafelek Microsoft na stronie konfiguracje lokalizacji](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)</span><span class="sxs-lookup"><span data-stu-id="ea526-112">[![Microsoft tile on the Localization configurations page](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)</span></span>

5. <span data-ttu-id="ea526-113">Na stronie **Repozytoria konfiguracji** w siatce zaznacz istniejące repozytorium typu **LCS**.</span><span class="sxs-lookup"><span data-stu-id="ea526-113">On the **Configuration repositories** page, in the grid, select the existing repository of the **LCS** type.</span></span> <span data-ttu-id="ea526-114">Jeśli to repozytorium nie jest wyświetlane w siatce, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="ea526-114">If this repository doesn't appear in the grid, follow these steps:</span></span>

    1. <span data-ttu-id="ea526-115">Wybierz **Dodaj**, aby dodać repozytorium.</span><span class="sxs-lookup"><span data-stu-id="ea526-115">Select **Add** to add a repository.</span></span>
    2. <span data-ttu-id="ea526-116">Jako typ repozytorium wybierz **LCS**.</span><span class="sxs-lookup"><span data-stu-id="ea526-116">Select **LCS** as the repository type.</span></span>
    3. <span data-ttu-id="ea526-117">Kliknij opcję **Utwórz repozytorium**.</span><span class="sxs-lookup"><span data-stu-id="ea526-117">Select **Create repository**.</span></span>
    4. <span data-ttu-id="ea526-118">Jeśli zostanie wyświetlony monit o autoryzację, postępuj zgodnie z instrukcjami wyświetlanymi na ekranie.</span><span class="sxs-lookup"><span data-stu-id="ea526-118">If you're prompted about authorization, follow the on-screen instructions.</span></span>
    5. <span data-ttu-id="ea526-119">Wprowadź nazwę i opis repozytorium.</span><span class="sxs-lookup"><span data-stu-id="ea526-119">Enter a name and description for the repository.</span></span>
    6. <span data-ttu-id="ea526-120">Wybierz przycisk **OK**, aby potwierdzić wprowadzenie nowego repozytorium.</span><span class="sxs-lookup"><span data-stu-id="ea526-120">Select **OK** to confirm the new repository entry.</span></span>
    7. <span data-ttu-id="ea526-121">W siatce wybierz nowe repozytorium typu **LCS**.</span><span class="sxs-lookup"><span data-stu-id="ea526-121">In the grid, select the new repository of the **LCS** type.</span></span>

6. <span data-ttu-id="ea526-122">Wybierz **Otwórz**, aby wyświetlić listę konfiguracji modułu ER dla wybranego repozytorium.</span><span class="sxs-lookup"><span data-stu-id="ea526-122">Select **Open** to view the list of ER configurations for the selected repository.</span></span>

    <span data-ttu-id="ea526-123">[![Strona repozytorium konfiguracji](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)</span><span class="sxs-lookup"><span data-stu-id="ea526-123">[![Configuration repositories page](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)</span></span>

    > [!TIP]
    > <span data-ttu-id="ea526-124">Jeśli występują problemy z dostępem do repozytorium usługi LCS w celu pobrania konfiguracji z biblioteki udostępnionych elementów w usłudze LCS, można pobrać konfiguracje z [repozytorium globalnego](er-download-configurations-global-repo.md).</span><span class="sxs-lookup"><span data-stu-id="ea526-124">If you have trouble accessing the LCS repository to download configurations from the Shared asset library in LCS, you can download configurations from the [Global repository](er-download-configurations-global-repo.md) instead.</span></span>

7. <span data-ttu-id="ea526-125">W drzewie konfiguracji w lewym okienku zaznacz wymaganą konfigurację ER.</span><span class="sxs-lookup"><span data-stu-id="ea526-125">In the configurations tree in the left pane, select the required ER configuration.</span></span>
8. <span data-ttu-id="ea526-126">Na skróconej karcie **Wersje** wybierz wymaganą wersję wybranej konfiguracji ER.</span><span class="sxs-lookup"><span data-stu-id="ea526-126">On the **Versions** FastTab, select the required version of the selected ER configuration.</span></span>
9. <span data-ttu-id="ea526-127">Wybierz opcję **Importuj**, aby pobrać wybraną wersję z usługi LCS do bieżącego wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="ea526-127">Select **Import** to download the selected version from LCS to the current instance.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ea526-128">Przycisk **Importuj** jest niedostępny dla wersji konfiguracji ER, które już się znajdują w bieżącym wystąpieniu.</span><span class="sxs-lookup"><span data-stu-id="ea526-128">The **Import** button is unavailable for ER configuration versions that are already present in the current instance.</span></span>

    <span data-ttu-id="ea526-129">[![Strona Repozytorium konfiguracji](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)</span><span class="sxs-lookup"><span data-stu-id="ea526-129">[![Configuration repository page](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)</span></span>

> [!NOTE]
> <span data-ttu-id="ea526-130">W zależności od ustawień ER podczas importowania konfiguracji jest sprawdzana ich poprawność.</span><span class="sxs-lookup"><span data-stu-id="ea526-130">Depending on the ER settings, configurations are validated after they are imported.</span></span> <span data-ttu-id="ea526-131">Możesz otrzymywać powiadomienia o wszelkich wykrytych problemach z niespójnością.</span><span class="sxs-lookup"><span data-stu-id="ea526-131">You might be notified about any inconsistency issues that are discovered.</span></span> <span data-ttu-id="ea526-132">Przed rozpoczęciem używania zaimportowanej wersji konfiguracji należy rozwiązać te problemy.</span><span class="sxs-lookup"><span data-stu-id="ea526-132">You must resolve those issues before you can use the imported configuration version.</span></span> <span data-ttu-id="ea526-133">Aby uzyskać więcej informacji, zobacz listę pokrewnych tematów.</span><span class="sxs-lookup"><span data-stu-id="ea526-133">For more information, see the list of related topics for this topic.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ea526-134">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="ea526-134">Additional resources</span></span>

[<span data-ttu-id="ea526-135">Omówienie raportowania elektronicznego (ER)</span><span class="sxs-lookup"><span data-stu-id="ea526-135">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="ea526-136">Pobieranie konfiguracji ER z globalnego repozytorium usługi Configuration service</span><span class="sxs-lookup"><span data-stu-id="ea526-136">Download ER configurations from the Global repository of Configuration service</span></span>](er-download-configurations-global-repo.md)
