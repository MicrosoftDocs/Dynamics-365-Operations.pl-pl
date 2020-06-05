---
title: Tworzenie konfiguracji raportowania elektronicznego w RCS i przekazywanie ich do repozytorium globalnego
description: W tym temacie objaśniono sposób tworzenia konfiguracji Raportowania elektronicznego (ER) w usługach Microsoft Regulatory Configuration Services (RCS) i przekazywania jej do repozytorium globalnego.
author: JaneA07
manager: AnnBe
ms.date: 05/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace, RCS
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 0e194a8b777f984412d81e315f92ab4bb8a3b0c9
ms.sourcegitcommit: 204cec8ca2a6c4474d21dbcd408e369131a47856
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/13/2020
ms.locfileid: "3371263"
---
# <a name="create-er-configurations-in-regulatory-configuration-services-rcs-and-upload-them-to-the-global-repository"></a><span data-ttu-id="53f9c-103">Tworzenie konfiguracji raportowania elektronicznego w usługach Regulatory Configuration Services (RCS) i przekazywanie ich do repozytorium globalnego</span><span class="sxs-lookup"><span data-stu-id="53f9c-103">Create ER configurations in Regulatory Configuration Services (RCS) and upload them to the Global repository</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="53f9c-104">Do projektowania konfiguracji Raportowania elektronicznego (ER) można używać usług Regulatory Configuration Services (RCS) firmy Microsoft, a następnie publikować je, aby umożliwić ich używanie w organizacji.</span><span class="sxs-lookup"><span data-stu-id="53f9c-104">You can use Microsoft Regulatory Configuration Services (RCS) to design Electronic reporting (ER) configurations and publish them so that they can be used in your organization.</span></span>

<span data-ttu-id="53f9c-105">W poniższych procedurach opisano, jak użytkownik w roli administratora systemu lub dewelopera Raportowania elektronicznego może utworzyć pochodną wersję konfiguracji ER, która została skonfigurowana w wystąpieniu usług RCS, a następnie przekazać pochodną konfigurację do repozytorium globalnego.</span><span class="sxs-lookup"><span data-stu-id="53f9c-105">The following procedures explain how a user in the System Administrator or Electronic Reporting Developer role can create a derived version of an ER configuration that has been configured in an RCS instance, and then upload the derived configuration to the Global repository.</span></span> 

<span data-ttu-id="53f9c-106">Przed wykonaniem tych procedur należy najpierw spełnić następujące warunki wstępne:</span><span class="sxs-lookup"><span data-stu-id="53f9c-106">Before you can complete those procedures, you must complete the following prerequisites:</span></span>

- <span data-ttu-id="53f9c-107">Uzyskanie dostępu do wystąpienia usług RCS.</span><span class="sxs-lookup"><span data-stu-id="53f9c-107">Access an RCS instance.</span></span>
- <span data-ttu-id="53f9c-108">Utworzenie aktywnego dostawcy konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="53f9c-108">Create an active configuration provider.</span></span> <span data-ttu-id="53f9c-109">Dalsze informacje znajdują się w temacie [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="53f9c-109">For more information, see [Create configuration providers and mark them as active](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>

<span data-ttu-id="53f9c-110">Należy również upewnić się, że dla firmy aprowizowano środowisko RCS.</span><span class="sxs-lookup"><span data-stu-id="53f9c-110">You must also make sure that an RCS environment is provisioned for your company.</span></span>

1. <span data-ttu-id="53f9c-111">W aplikacji Finance and Operations przejdź do obszaru **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="53f9c-111">In a Finance and Operations app, go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="53f9c-112">Jeśli w firmie nie aprowizowano środowiska RCS, wybierz pozycję zewnętrzną **Regulatory services — Konfiguracja** i postępować zgodnie z instrukcjami w celu aprowizowania środowiska RCS.</span><span class="sxs-lookup"><span data-stu-id="53f9c-112">If no RCS environment is provisioned for your company, select **Regulatory services – Configuration external**, and then follow the instructions to provision one.</span></span>

<span data-ttu-id="53f9c-113">Jeśli już aprowizowano środowisko RCS, należy skorzystać z adresu URL strony, aby uzyskać do niego dostęp, wybierając opcję logowania.</span><span class="sxs-lookup"><span data-stu-id="53f9c-113">If an RCS environment has been already provisioned for your company, use the page URL to access it by selecting the sign-in option.</span></span>

## <a name="create-a-derived-version-of-a-configuration-in-rcs"></a><span data-ttu-id="53f9c-114">Tworzenie wersji pochodnej konfiguracji w usługach RCS</span><span class="sxs-lookup"><span data-stu-id="53f9c-114">Create a derived version of a configuration in RCS</span></span>

1. <span data-ttu-id="53f9c-115">W obszarze roboczym **Raportowanie elektroniczne** sprawdź, czy masz aktywnego dostawcę konfiguracji dla organizacji.</span><span class="sxs-lookup"><span data-stu-id="53f9c-115">In the **Electronic reporting** workspace, verify that you have an active configuration provider for your organization.</span></span> 
2. <span data-ttu-id="53f9c-116">Wybierz **Raportowanie konfiguracji**.</span><span class="sxs-lookup"><span data-stu-id="53f9c-116">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="53f9c-117">Wybierz konfigurację, z której chcesz uzyskać nową wersję.</span><span class="sxs-lookup"><span data-stu-id="53f9c-117">Select the configuration that you want to derive a new version from.</span></span> <span data-ttu-id="53f9c-118">Możesz użyć pola filtru nad drzewem, aby zawęzić wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="53f9c-118">You can use the filter field above the tree to narrow your search.</span></span>
4. <span data-ttu-id="53f9c-119">Wybierz pozycję **Utwórz konfigurację** \> **Pochodzi od nazwy**.</span><span class="sxs-lookup"><span data-stu-id="53f9c-119">Select **Create configuration** \> **Derive from Name**.</span></span>
5. <span data-ttu-id="53f9c-120">Wprowadź nazwę i opis, a następnie wybierz opcję **Utwórz konfigurację**, aby utworzyć nową wersję pochodną.</span><span class="sxs-lookup"><span data-stu-id="53f9c-120">Enter a name and description, and then select **Create configuration** to create a new derived version.</span></span>
6. <span data-ttu-id="53f9c-121">Wybierz nową konfigurację pochodną, dodaj opis wersji, a następnie wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="53f9c-121">Select the newly derived configuration, add a description of the version, and then select **OK**.</span></span> <span data-ttu-id="53f9c-122">Stan konfiguracji zostanie zmieniony na **Zakończono**.</span><span class="sxs-lookup"><span data-stu-id="53f9c-122">The status of the configuration to is changed to **Completed**.</span></span>

![Nowa wersja konfiguracji w usługach RCS](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/Janeaug_RCSdocs/articles/finance/localizations/media/RCS_CompleteConfig.JPG)

> [!NOTE]
> <span data-ttu-id="53f9c-124">Po zmianie stanu konfiguracji może pojawić się komunikat o błędzie weryfikacji, który jest związany z dołączonymi aplikacjami.</span><span class="sxs-lookup"><span data-stu-id="53f9c-124">When the configuration status is changed, you might receive a validation error message that is related to the connected applications.</span></span> <span data-ttu-id="53f9c-125">Aby wyłączyć weryfikowanie, w okienku akcji na karcie **Konfiguracje** wybierz pozycję **Parametry użytkownika**, a następnie ustaw opcję **Pomiń weryfikację przy zmianie stanu konfiguracji i zmianie bazy** na **Tak**</span><span class="sxs-lookup"><span data-stu-id="53f9c-125">To turn off the validation, on the Action Pane on the **Configurations** tab, select **User parameters**, and then set the **Skip validation at configuration's status change and rebase** option to **Yes**</span></span> 

## <a name="upload-a-configuration-to-the-global-repository"></a><span data-ttu-id="53f9c-126">Przekazywanie konfiguracji do repozytorium globalnego</span><span class="sxs-lookup"><span data-stu-id="53f9c-126">Upload a configuration to the Global repository</span></span>

<span data-ttu-id="53f9c-127">Aby udostępnić organizacji nową lub pochodną konfigurację, można ją przekazać do repozytorium globalnego.</span><span class="sxs-lookup"><span data-stu-id="53f9c-127">To share a new or derived configuration with your organization, you can upload it to the Global repository.</span></span>

1. <span data-ttu-id="53f9c-128">Wybierz zakończoną wersję konfiguracji, a następnie wybierz pozycję **Przekaż do repozytorium**.</span><span class="sxs-lookup"><span data-stu-id="53f9c-128">Select the completed version of the configuration, and then select **Upload into repository**.</span></span>
2. <span data-ttu-id="53f9c-129">Wybierz opcję **Globalne (Microsoft)**, a następnie wybierz pozycję **Przekaż**.</span><span class="sxs-lookup"><span data-stu-id="53f9c-129">Select the **Global (Microsoft)** option, and then select **Upload**.</span></span>

    ![Opcje przekazywania do repozytorium](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/Janeaug_RCSdocs/articles/finance/localizations/media/RCS_Upload_to_GlobalRepo_options.JPG)

3. <span data-ttu-id="53f9c-131">W wyświetlonym oknie wiadomości z potwierdzeniem wybierz przycisk **Tak**.</span><span class="sxs-lookup"><span data-stu-id="53f9c-131">In the confirmation message box, select **Yes**.</span></span> 
4. <span data-ttu-id="53f9c-132">W razie potrzeby zaktualizuj opis wersji, a następnie wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="53f9c-132">Update the description of the version as required, and then select **OK**.</span></span> 

<span data-ttu-id="53f9c-133">Stan konfiguracji jest aktualizowany do wartości **Udostępnij**, a konfiguracja jest przekazywana do repozytorium globalnego.</span><span class="sxs-lookup"><span data-stu-id="53f9c-133">The status of the configuration is updated to **Share**, and the configuration is uploaded to the Global repository.</span></span> <span data-ttu-id="53f9c-134">W tym miejscu można pracować w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="53f9c-134">From there, you can work with it in the following ways:</span></span>

- <span data-ttu-id="53f9c-135">Zaimportuj ją do wystąpienia rozwiązania Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="53f9c-135">Import it into your Dynamics 365 instance.</span></span> <span data-ttu-id="53f9c-136">Aby uzyskać więcej informacji, zobacz temat [(ER) Importowanie konfiguracji z usług RCS](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md).</span><span class="sxs-lookup"><span data-stu-id="53f9c-136">For more information, see [(ER) Import configurations from RCS](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md).</span></span>
- <span data-ttu-id="53f9c-137">Udostępnij ją firmie lub organizacji zewnętrznej, zobacz temat [RCS — udostępnianie konfiguracji Raportowania elektronicznego (ER) organizacjom zewnętrznymi](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/Janeaug_RCSdocs/articles/finance/localizations/media/rcs-global-share-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="53f9c-137">Share it with a third party or an external organization, see [RCS Share Electronic reporting (ER) configurations with external organizations](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/Janeaug_RCSdocs/articles/finance/localizations/media/rcs-global-share-configuration.md)</span></span>

![Wersja konfiguracji pochodnej Intrastat Contoso w repozytorium globalnym](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/Janeaug_RCSdocs/articles/finance/localizations/media/RCS_Config_upload_GlobalRepo.JPG)
