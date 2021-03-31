---
title: Udostępnianie konfiguracji ER w oprogramowaniu RCS/repozytorium globalnym organizacjom zewnętrznym
description: W tym temacie objaśniono sposób udostępniania konfiguracji Raportowania elektronicznego (ER) w usługach Microsoft Regulatory Configuration Services (RCS)/repozytorium globalnym bezpośrednio organizacjom zewnętrznym.
author: JaneA07
manager: AnnBe
ms.date: 05/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace, RCS
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: e7ec24ddc532ee3b87108d076d5103538be903be
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5218837"
---
# <a name="share-electronic-reporting-er-configurations-in-regulatory-configuration-services-rcs-global-repository-with-external-organizations"></a><span data-ttu-id="68fe9-103">Udostępnianie konfiguracji Raportowania elektronicznego (ER) w repozytorium globalnym usług Microsoft Regulatory Configuration Services (RCS)organizacjom zewnętrznym</span><span class="sxs-lookup"><span data-stu-id="68fe9-103">Share Electronic reporting (ER) configurations in Regulatory Configuration Services (RCS) Global repository with external organizations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="68fe9-104">Do udostępniania konfiguracji Raportowania elektronicznego (ER) można używać usług Regulatory Configuration Services (RCS) firmy Microsoft, a następnie publikować je dla organizacji zewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="68fe9-104">You can use Microsoft Regulatory Configuration Services (RCS) to share Electronic reporting (ER) configurations and then publish them to external organizations.</span></span>

<span data-ttu-id="68fe9-105">Poniższe procedury opisują sposób, w jaki użytkownik RCS może udostępniać wersję konfiguracji ER, która została skonfigurowana w wystąpieniu usług RCS przy użyciu organizacji zewnętrznej.</span><span class="sxs-lookup"><span data-stu-id="68fe9-105">The following procedures explain how an RCS user can share a version of an ER configuration that has been configured in an RCS instance with an external organization.</span></span> <span data-ttu-id="68fe9-106">Przed wykonaniem tych procedur należy najpierw spełnić następujące warunki wstępne:</span><span class="sxs-lookup"><span data-stu-id="68fe9-106">Before you can complete those procedures, you must complete the following prerequisites:</span></span>

- <span data-ttu-id="68fe9-107">Uzyskanie dostępu do wystąpienia usług RCS.</span><span class="sxs-lookup"><span data-stu-id="68fe9-107">Access an RCS instance.</span></span>
- <span data-ttu-id="68fe9-108">Utworzenie aktywnego dostawcy konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="68fe9-108">Create an active configuration provider.</span></span> <span data-ttu-id="68fe9-109">Dalsze informacje znajdują się w temacie [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="68fe9-109">For more information, see [Create configuration providers and mark them as active](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>
- <span data-ttu-id="68fe9-110">Utworzenie i przekazanie nowej wersji konfiguracji ER.</span><span class="sxs-lookup"><span data-stu-id="68fe9-110">Create and upload a new version of an ER configuration.</span></span> <span data-ttu-id="68fe9-111">Aby uzyskać więcej informacji, zobacz temat [Tworzenie i przekazywanie nowej wersji konfiguracji Raportowania elektronicznego (ER)](rcs-global-repo-upload.md).</span><span class="sxs-lookup"><span data-stu-id="68fe9-111">For more information, see [Create and upload a new version of an Electronic reporting (ER) configuration](rcs-global-repo-upload.md).</span></span>

<span data-ttu-id="68fe9-112">Należy również upewnić się, że dla firmy aprowizowano środowisko RCS.</span><span class="sxs-lookup"><span data-stu-id="68fe9-112">You must also make sure that an RCS environment is provisioned for your company.</span></span>

1. <span data-ttu-id="68fe9-113">W aplikacji Finance and Operations przejdź do obszaru **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="68fe9-113">In a Finance and Operations app, go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="68fe9-114">Jeśli w firmie nie aprowizowano środowiska RCS, wybierz pozycję zewnętrzną **Regulatory services — Konfiguracja** i postępować zgodnie z instrukcjami w celu aprowizowania środowiska RCS.</span><span class="sxs-lookup"><span data-stu-id="68fe9-114">If no RCS environment is provisioned for your company, select **Regulatory services – Configuration external**, and then follow the instructions to provision one.</span></span>

<span data-ttu-id="68fe9-115">Jeśli już aprowizowano środowisko RCS, należy skorzystać z adresu URL strony, aby uzyskać do niego dostęp, wybierając opcję logowania.</span><span class="sxs-lookup"><span data-stu-id="68fe9-115">If an RCS environment has been already provisioned for your company, use the page URL to access it by selecting the sign-in option.</span></span>

## <a name="verify-the-configuration-that-you-want-to-share"></a><span data-ttu-id="68fe9-116">Weryfikowanie konfiguracji do udostępnienia</span><span class="sxs-lookup"><span data-stu-id="68fe9-116">Verify the configuration that you want to share</span></span>

<span data-ttu-id="68fe9-117">Wykonaj poniższe kroki, aby sprawdzić, czy konfiguracja, którą chcesz udostępnić, została już przekazana do repozytorium globalnego.</span><span class="sxs-lookup"><span data-stu-id="68fe9-117">Follow these steps to verify that the configuration that you want to share has already been uploaded to the Global repository.</span></span>

1. <span data-ttu-id="68fe9-118">W obszarze roboczym **Raportowanie elektroniczne** wybierz pozycję **Repozytoria** dla dostawcy konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="68fe9-118">In the **Electronic reporting** workspace, select **Repositories** for your configuration provider.</span></span>

    ![Dostawcy konfiguracji](media/1_RCS_Repo_for_config_provider.JPG)

2. <span data-ttu-id="68fe9-120">Wybierz pozycję **Repozytorium globalne** \> **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="68fe9-120">Select **Global repository** \> **Open**.</span></span>
3. <span data-ttu-id="68fe9-121">Wyszukaj konfigurację do udostępnienia.</span><span class="sxs-lookup"><span data-stu-id="68fe9-121">Search for the configuration that you want to share.</span></span> <span data-ttu-id="68fe9-122">Możesz użyć pola filtru, aby zawęzić wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="68fe9-122">You can use the filter field to narrow your search.</span></span> <span data-ttu-id="68fe9-123">Jeśli nie możesz znaleźć konfiguracji w repozytorium globalnym, postępuj zgodnie z instrukcjami w temacie [Tworzenie i przekazywanie nowej wersji konfiguracji Raportowania elektronicznego (ER)](rcs-global-repo-upload.md).</span><span class="sxs-lookup"><span data-stu-id="68fe9-123">If you can't find the configuration in the Global repository, follow the steps in [Create and upload a new version of an Electronic reporting (ER) configuration](rcs-global-repo-upload.md).</span></span>

## <a name="share-er-configurations-with-external-organizations"></a><span data-ttu-id="68fe9-124">Udostępnianie konfiguracji ER organizacjom zewnętrznym</span><span class="sxs-lookup"><span data-stu-id="68fe9-124">Share ER configurations with external organizations</span></span>

<span data-ttu-id="68fe9-125">Po utworzeniu konfiguracji w ramach dostawcy konfiguracji można udostępnić ją bezpośrednio organizacjom zewnętrznym, korzystając ze skróconej karty **Udostępnione** na stronie **globalnego repozytorium konfiguracji**.</span><span class="sxs-lookup"><span data-stu-id="68fe9-125">After a configuration has been created under your configuration provider, you can share it directly with external organizations by using the **Shared with** FastTab on the **Global configuration repository** page.</span></span>

1. <span data-ttu-id="68fe9-126">W obszarze roboczym **Raportowanie elektroniczne** wybierz pozycję **Repozytoria** dla dostawcy konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="68fe9-126">In the **Electronic reporting** workspace, select **Repositories** for your configuration provider.</span></span>
2. <span data-ttu-id="68fe9-127">Wybierz pozycję **Repozytorium globalne** \> **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="68fe9-127">Select **Global repository** \> **Open**.</span></span> 
3. <span data-ttu-id="68fe9-128">Wybierz konfigurację do udostępnienia.</span><span class="sxs-lookup"><span data-stu-id="68fe9-128">Select the configuration that you want to share.</span></span>
4. <span data-ttu-id="68fe9-129">Na skróconej karcie **Udostępnione** wybierz pozycję **Organizacje**.</span><span class="sxs-lookup"><span data-stu-id="68fe9-129">On the **Shared with** FastTab, select **Organization**.</span></span>

    ![Skrócona karta Udostępnione](media/1_RCS_Repo_for_Share_with_org.JPG)

5. <span data-ttu-id="68fe9-131">W oknie dialogowym wprowadź nazwę domeny dla organizacji zewnętrznej, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="68fe9-131">In the dialog box, enter the domain name for the external organization, and then select **OK**.</span></span>

    ![Okno dialogowe udostępniania wersji konfiguracji organizacji zewnętrznej](media/1_RCS_Repo_for_Share_with_form.JPG)

<span data-ttu-id="68fe9-133">Konfiguracja jest udostępniana organizacji zewnętrznej i jest dostępna dla tej organizacji w repozytorium globalnym.</span><span class="sxs-lookup"><span data-stu-id="68fe9-133">The configuration is shared with the external organization and is available to that organization in the Global repository.</span></span> <span data-ttu-id="68fe9-134">Z tego miejsca można ją zaimportować do wystąpienia usług RCS organizacji lub do jej wystąpień aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="68fe9-134">From there, it can be imported into the organization's instance of RCS or into its instances of Finance and Operations apps.</span></span>

6. <span data-ttu-id="68fe9-135">Aby cofnąć udostępnianie konfiguracji poprzednio udostępnionej organizacji zewnętrznej, wybierz konfigurację i kliknij pozycję **Anuluj udostępnianie**, a następnie wybierz przycisk **OK**</span><span class="sxs-lookup"><span data-stu-id="68fe9-135">To unshare a configuration that has been previously shared with an external organization, select the configuration and click **Unshare**, and then select **OK**</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]