---
title: "Pobieranie konfiguracji modułu Raportowanie elektroniczne z usługi Lifecycle Services"
description: "Ten temat wyjaśnia sposób pobierania konfiguracji modułu Raportowanie elektroniczne (ER) z usługi Microsoft Dynamics Lifecycle Services (LCS)."
author: NickSelin
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
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
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 8fae33fbe2d1433e4263ed4087dad2bc894e0b84
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="download-electronic-reporting-configurations-from-lifecycle-services"></a><span data-ttu-id="55704-103">Pobieranie konfiguracji modułu Raportowanie elektroniczne z usługi Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="55704-103">Download Electronic reporting configurations from Lifecycle Services</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="55704-104">Ten temat wyjaśnia sposób pobierania konfiguracji modułu Raportowanie elektroniczne (ER) z usługi Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="55704-104">This topic explains how to download Electronic reporting (ER) configurations from Microsoft Dynamics Lifecycle Services (LCS).</span></span>

<span data-ttu-id="55704-105">Ten samouczek prowadzi przez proces pobierania najnowszej wersji konfiguracji modułu Raportowanie elektroniczne (ER) z usługi Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="55704-105">This tutorial guides you through the process of downloading the newest version of Electronic reporting (ER) configurations from Microsoft Dynamics Lifecycle Services (LCS).</span></span>

1.  <span data-ttu-id="55704-106">Zaloguj się do programu Finance and Operations przy użyciu jednej z następujących ról:</span><span class="sxs-lookup"><span data-stu-id="55704-106">Sign in to Finance and Operations by using one of the following roles:</span></span>
    -   <span data-ttu-id="55704-107">Deweloper raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="55704-107">Electronic reporting developer</span></span>
    -   <span data-ttu-id="55704-108">Konsultant funkcjonalny raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="55704-108">Electronic reporting functional consultant</span></span>
    -   <span data-ttu-id="55704-109">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="55704-109">System administrator</span></span>

2.  <span data-ttu-id="55704-110">Wybierz kolejno opcje **Administrowanie organizacją** &gt; **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="55704-110">Go to **Organization administration** &gt; **Electronic reporting**.</span></span>
3.  <span data-ttu-id="55704-111">W obszarze **Dostawcy konfiguracji** wybierz kafelek **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="55704-111">In the **Configuration providers** section, select the **Microsoft** tile.</span></span>
4.  <span data-ttu-id="55704-112">Na kafelku **Microsoft** kliknij opcję **Repozytoria**.</span><span class="sxs-lookup"><span data-stu-id="55704-112">On the **Microsoft** tile, click **Repositories**.</span></span> <span data-ttu-id="55704-113">[![update-er-from-lcs-for-ms-open-ms-repositories-list](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)</span><span class="sxs-lookup"><span data-stu-id="55704-113">[![update-er-from-lcs-for-ms-open-ms-repositories-list](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)</span></span>
5.  <span data-ttu-id="55704-114">Na stronie **Repozytoria konfiguracji** w siatce zaznacz istniejące repozytorium typu **LCS**.</span><span class="sxs-lookup"><span data-stu-id="55704-114">On the **Configuration repositories** page, in the grid, select the existing repository of the **LCS** type.</span></span> <span data-ttu-id="55704-115">Jeśli to repozytorium nie jest wyświetlane w siatce, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="55704-115">If this repository doesn't appear in the grid, follow these steps:</span></span>
    1.  <span data-ttu-id="55704-116">Kliknij przycisk **Dodaj**, aby dodać nowe repozytorium.</span><span class="sxs-lookup"><span data-stu-id="55704-116">Click **Add** to add a new repository.</span></span>
    2.  <span data-ttu-id="55704-117">Jako typ repozytorium wybierz **LCS**.</span><span class="sxs-lookup"><span data-stu-id="55704-117">Select **LCS** as the repository type.</span></span>
    3.  <span data-ttu-id="55704-118">Kliknij opcję **Utwórz repozytorium**.</span><span class="sxs-lookup"><span data-stu-id="55704-118">Click **Create repository**.</span></span>
    4. <span data-ttu-id="55704-119">W przypadku wyświetlenia monitu postępuj zgodnie z instrukcjami autoryzacji.</span><span class="sxs-lookup"><span data-stu-id="55704-119">If prompted, follow the authorization instructions.</span></span>
    5.  <span data-ttu-id="55704-120">Wprowadź nazwę i opis repozytorium.</span><span class="sxs-lookup"><span data-stu-id="55704-120">Enter a name and description for the repository.</span></span>
    6.  <span data-ttu-id="55704-121">Kliknij przycisk **OK**, aby potwierdzić wprowadzenie nowego repozytorium.</span><span class="sxs-lookup"><span data-stu-id="55704-121">Click **OK** to confirm the new repository entry.</span></span>
    7.  <span data-ttu-id="55704-122">W siatce wybierz nowe repozytorium typu **LCS**.</span><span class="sxs-lookup"><span data-stu-id="55704-122">In the grid, select the new repository of the **LCS** type.</span></span>

6.  <span data-ttu-id="55704-123">Kliknij opcję **Otwórz**, aby wyświetlić listę konfiguracji modułu ER dla wybranego repozytorium.</span><span class="sxs-lookup"><span data-stu-id="55704-123">Click **Open** to view the list of ER configurations for the selected repository.</span></span> <span data-ttu-id="55704-124">[![update-er-from-lcs-for-ms-make-lcs-repository](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)</span><span class="sxs-lookup"><span data-stu-id="55704-124">[![update-er-from-lcs-for-ms-make-lcs-repository](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)</span></span>
7.  <span data-ttu-id="55704-125">W drzewie konfiguracji w lewym okienku zaznacz wymaganą konfigurację ER.</span><span class="sxs-lookup"><span data-stu-id="55704-125">In the configurations tree in the left pane, select the ER configuration that you require.</span></span>
8.  <span data-ttu-id="55704-126">Na skróconej karcie **Wersje** wybierz wymaganą wersję wybranej konfiguracji ER.</span><span class="sxs-lookup"><span data-stu-id="55704-126">On the **Versions** FastTab, select the required version of the selected ER configuration.</span></span>
9.  <span data-ttu-id="55704-127">Kliknij opcję **Importuj**, aby pobrać wybraną wersję z usługi LCS do bieżącego wystąpienia programu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="55704-127">Click **Import** to download the selected version from LCS to the current Finance and Operations instance.</span></span> <span data-ttu-id="55704-128">**Uwaga:** Przycisk **Importuj** jest niedostępny dla wersji konfiguracji ER, które już się znajdują w bieżącym wystąpieniu programu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="55704-128">**Note:** The **Import** button is unavailable for ER configuration versions that are already present in the current Finance and Operations instance.</span></span> <span data-ttu-id="55704-129">[![update-er-from-lcs-for-ms-download-configuration](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)</span><span class="sxs-lookup"><span data-stu-id="55704-129">[![update-er-from-lcs-for-ms-download-configuration](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)</span></span>

<span data-ttu-id="55704-130">**Uwaga:** W zależności od ustawień ER podczas importowania konfiguracji jest sprawdzana ich poprawność.</span><span class="sxs-lookup"><span data-stu-id="55704-130">**Note:** Depending on the ER settings, configurations are validated after they are imported.</span></span> <span data-ttu-id="55704-131">Możesz otrzymywać powiadomienia o wszelkich wykrytych problemach z niespójnością.</span><span class="sxs-lookup"><span data-stu-id="55704-131">You might be notified about any inconsistency issues that are discovered.</span></span> <span data-ttu-id="55704-132">Przed rozpoczęciem używania zaimportowanej wersji konfiguracji należy rozwiązać te problemy.</span><span class="sxs-lookup"><span data-stu-id="55704-132">You must resolve those issues before you can use the imported configuration version.</span></span> <span data-ttu-id="55704-133">Aby uzyskać więcej informacji, zobacz listę pokrewnych artykułów do tego tematu.</span><span class="sxs-lookup"><span data-stu-id="55704-133">For more information, see the list of related articles for this topic.</span></span>

<a name="see-also"></a><span data-ttu-id="55704-134">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="55704-134">See also</span></span>
--------

[<span data-ttu-id="55704-135">Raportowanie elektroniczne — omówienie</span><span class="sxs-lookup"><span data-stu-id="55704-135">Electronic reporting overview</span></span>](general-electronic-reporting.md)




