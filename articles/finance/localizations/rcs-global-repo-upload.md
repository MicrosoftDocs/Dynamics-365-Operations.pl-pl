---
title: Tworzenie konfiguracji raportowania elektronicznego w RCS i przekazywanie ich do repozytorium globalnego
description: W tym temacie objaśniono sposób tworzenia konfiguracji Raportowania elektronicznego (ER) w usługach Microsoft Regulatory Configuration Services (RCS) i przekazywania jej do repozytorium globalnego.
author: JaneA07
manager: AnnBe
ms.date: 09/21/2020
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
ms.openlocfilehash: ef12c911c8953b181db1c0eff0874a3d8cfcb3da
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5005755"
---
# <a name="create-er-configurations-in-regulatory-configuration-services-rcs-and-upload-them-to-the-global-repository"></a><span data-ttu-id="0a23a-103">Tworzenie konfiguracji raportowania elektronicznego w usługach Regulatory Configuration Services (RCS) i przekazywanie ich do repozytorium globalnego</span><span class="sxs-lookup"><span data-stu-id="0a23a-103">Create ER configurations in Regulatory Configuration Services (RCS) and upload them to the Global repository</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0a23a-104">Do projektowania konfiguracji Raportowania elektronicznego (ER) można używać usług Regulatory Configuration Services (RCS) firmy Microsoft, a następnie publikować je, aby umożliwić ich używanie w organizacji.</span><span class="sxs-lookup"><span data-stu-id="0a23a-104">You can use Microsoft Regulatory Configuration Services (RCS) to design Electronic reporting (ER) configurations and publish them so that they can be used in your organization.</span></span>

<span data-ttu-id="0a23a-105">W poniższych procedurach opisano, jak użytkownik w roli administratora systemu lub dewelopera Raportowania elektronicznego może utworzyć pochodną wersję konfiguracji ER, która została skonfigurowana w wystąpieniu usług RCS, a następnie przekazać pochodną konfigurację do repozytorium globalnego.</span><span class="sxs-lookup"><span data-stu-id="0a23a-105">The following procedures explain how a user in the System Administrator or Electronic Reporting Developer role can create a derived version of an ER configuration that has been configured in an RCS instance, and then upload the derived configuration to the Global repository.</span></span> 

<span data-ttu-id="0a23a-106">Przed wykonaniem tych procedur należy najpierw spełnić następujące warunki wstępne:</span><span class="sxs-lookup"><span data-stu-id="0a23a-106">Before you can complete those procedures, you must complete the following prerequisites:</span></span>

- <span data-ttu-id="0a23a-107">Uzyskanie dostępu do wystąpienia usług RCS.</span><span class="sxs-lookup"><span data-stu-id="0a23a-107">Access an RCS instance.</span></span>
- <span data-ttu-id="0a23a-108">Utworzenie aktywnego dostawcy konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="0a23a-108">Create an active configuration provider.</span></span> <span data-ttu-id="0a23a-109">Dalsze informacje znajdują się w temacie [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="0a23a-109">For more information, see [Create configuration providers and mark them as active](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>

<span data-ttu-id="0a23a-110">Należy również upewnić się, że dla firmy aprowizowano środowisko RCS.</span><span class="sxs-lookup"><span data-stu-id="0a23a-110">You must also make sure that an RCS environment is provisioned for your company.</span></span>

1. <span data-ttu-id="0a23a-111">W aplikacji Finance and Operations przejdź do obszaru **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="0a23a-111">In a Finance and Operations app, go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="0a23a-112">Jeśli w firmie nie aprowizowano środowiska RCS, wybierz pozycję zewnętrzną **Regulatory services — Konfiguracja** i postępować zgodnie z instrukcjami w celu aprowizowania środowiska RCS.</span><span class="sxs-lookup"><span data-stu-id="0a23a-112">If no RCS environment is provisioned for your company, select **Regulatory services – Configuration external**, and then follow the instructions to provision one.</span></span>

<span data-ttu-id="0a23a-113">Jeśli już aprowizowano środowisko RCS, należy skorzystać z adresu URL strony, aby uzyskać do niego dostęp, wybierając opcję logowania.</span><span class="sxs-lookup"><span data-stu-id="0a23a-113">If an RCS environment has been already provisioned for your company, use the page URL to access it by selecting the sign-in option.</span></span>

## <a name="create-a-derived-version-of-a-configuration-in-rcs"></a><span data-ttu-id="0a23a-114">Tworzenie wersji pochodnej konfiguracji w usługach RCS</span><span class="sxs-lookup"><span data-stu-id="0a23a-114">Create a derived version of a configuration in RCS</span></span>

1. <span data-ttu-id="0a23a-115">W obszarze roboczym **Raportowanie elektroniczne** sprawdź, czy masz aktywnego dostawcę konfiguracji dla organizacji.</span><span class="sxs-lookup"><span data-stu-id="0a23a-115">In the **Electronic reporting** workspace, verify that you have an active configuration provider for your organization.</span></span> 
2. <span data-ttu-id="0a23a-116">Wybierz **Raportowanie konfiguracji**.</span><span class="sxs-lookup"><span data-stu-id="0a23a-116">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="0a23a-117">Wybierz konfigurację, z której chcesz uzyskać nową wersję.</span><span class="sxs-lookup"><span data-stu-id="0a23a-117">Select the configuration that you want to derive a new version from.</span></span> <span data-ttu-id="0a23a-118">Możesz użyć pola filtru nad drzewem, aby zawęzić wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="0a23a-118">You can use the filter field above the tree to narrow your search.</span></span>
4. <span data-ttu-id="0a23a-119">Wybierz pozycję **Utwórz konfigurację** \> **Pochodzi od nazwy**.</span><span class="sxs-lookup"><span data-stu-id="0a23a-119">Select **Create configuration** \> **Derive from Name**.</span></span>
5. <span data-ttu-id="0a23a-120">Wprowadź nazwę i opis, a następnie wybierz opcję **Utwórz konfigurację**, aby utworzyć nową wersję pochodną.</span><span class="sxs-lookup"><span data-stu-id="0a23a-120">Enter a name and description, and then select **Create configuration** to create a new derived version.</span></span>
6. <span data-ttu-id="0a23a-121">Wybierz nową konfigurację pochodną, dodaj opis wersji, a następnie wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a23a-121">Select the newly derived configuration, add a description of the version, and then select **OK**.</span></span> <span data-ttu-id="0a23a-122">Stan konfiguracji zostanie zmieniony na **Zakończono**.</span><span class="sxs-lookup"><span data-stu-id="0a23a-122">The status of the configuration to is changed to **Completed**.</span></span>

![Nowa wersja konfiguracji w usługach RCS](media/RCS_CompleteConfig.JPG)

> [!NOTE]
> <span data-ttu-id="0a23a-124">Po zmianie stanu konfiguracji może pojawić się komunikat o błędzie weryfikacji, który jest związany z dołączonymi aplikacjami.</span><span class="sxs-lookup"><span data-stu-id="0a23a-124">When the configuration status is changed, you might receive a validation error message that is related to the connected applications.</span></span> <span data-ttu-id="0a23a-125">Aby wyłączyć weryfikowanie, w okienku akcji na karcie **Konfiguracje** wybierz pozycję **Parametry użytkownika**, a następnie ustaw opcję **Pomiń weryfikację przy zmianie stanu konfiguracji i zmianie bazy** na **Tak**</span><span class="sxs-lookup"><span data-stu-id="0a23a-125">To turn off the validation, on the Action Pane on the **Configurations** tab, select **User parameters**, and then set the **Skip validation at configuration's status change and rebase** option to **Yes**</span></span> 

## <a name="upload-a-configuration-to-the-global-repository"></a><span data-ttu-id="0a23a-126">Przekazywanie konfiguracji do repozytorium globalnego</span><span class="sxs-lookup"><span data-stu-id="0a23a-126">Upload a configuration to the Global repository</span></span>

<span data-ttu-id="0a23a-127">Aby udostępnić organizacji nową lub pochodną konfigurację, można ją przekazać do repozytorium globalnego.</span><span class="sxs-lookup"><span data-stu-id="0a23a-127">To share a new or derived configuration with your organization, you can upload it to the Global repository.</span></span>

1. <span data-ttu-id="0a23a-128">Wybierz zakończoną wersję konfiguracji, a następnie wybierz pozycję **Przekaż do repozytorium**.</span><span class="sxs-lookup"><span data-stu-id="0a23a-128">Select the completed version of the configuration, and then select **Upload into repository**.</span></span>
2. <span data-ttu-id="0a23a-129">Wybierz opcję **Globalne (Microsoft)**, a następnie wybierz pozycję **Przekaż**.</span><span class="sxs-lookup"><span data-stu-id="0a23a-129">Select the **Global (Microsoft)** option, and then select **Upload**.</span></span>

    ![Opcje przekazywania do repozytorium](media/RCS_Upload_to_GlobalRepo_options.JPG)

3. <span data-ttu-id="0a23a-131">W wyświetlonym oknie wiadomości z potwierdzeniem wybierz przycisk **Tak**.</span><span class="sxs-lookup"><span data-stu-id="0a23a-131">In the confirmation message box, select **Yes**.</span></span> 
4. <span data-ttu-id="0a23a-132">W razie potrzeby zaktualizuj opis wersji, a następnie wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a23a-132">Update the description of the version as required, and then select **OK**.</span></span> 

<span data-ttu-id="0a23a-133">Stan konfiguracji jest aktualizowany do wartości **Udostępnij**, a konfiguracja jest przekazywana do repozytorium globalnego.</span><span class="sxs-lookup"><span data-stu-id="0a23a-133">The status of the configuration is updated to **Share**, and the configuration is uploaded to the Global repository.</span></span> <span data-ttu-id="0a23a-134">W tym miejscu można pracować w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="0a23a-134">From there, you can work with it in the following ways:</span></span>

- <span data-ttu-id="0a23a-135">Zaimportuj ją do wystąpienia rozwiązania Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="0a23a-135">Import it into your Dynamics 365 instance.</span></span> <span data-ttu-id="0a23a-136">Aby uzyskać więcej informacji, zobacz temat [(ER) Importowanie konfiguracji z usług RCS](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md).</span><span class="sxs-lookup"><span data-stu-id="0a23a-136">For more information, see [(ER) Import configurations from RCS](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md).</span></span>
- <span data-ttu-id="0a23a-137">Udostępnij ją firmie lub organizacji zewnętrznej, zobacz temat [RCS — udostępnianie konfiguracji Raportowania elektronicznego (ER) organizacjom zewnętrznymi](rcs-global-repo-share-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="0a23a-137">Share it with a third party or an external organization, see [RCS Share Electronic reporting (ER) configurations with external organizations](rcs-global-repo-share-configuration.md)</span></span>

    ![Wersja konfiguracji pochodnej Intrastat Contoso w repozytorium globalnym](media/RCS_Config_upload_GlobalRepo.JPG)

## <a name="delete-a-configuration-from-the-global-repository"></a><span data-ttu-id="0a23a-139">Usuwanie konfiguracji z repozytorium globalnego</span><span class="sxs-lookup"><span data-stu-id="0a23a-139">Delete a configuration from the Global repository</span></span>
<span data-ttu-id="0a23a-140">Wykonaj następujące kroki, aby usunąć konfigurację utworzoną przez organizację.</span><span class="sxs-lookup"><span data-stu-id="0a23a-140">Complete the following steps to delete a configuration that your organization has created.</span></span>

1. <span data-ttu-id="0a23a-141">W obszarze roboczym **Raportowanie elektroniczne** sprawdź, czy dostawca konfiguracji jest **Aktywny**.</span><span class="sxs-lookup"><span data-stu-id="0a23a-141">In the **Electronic reporting** workspace, verify that your configuration provider is **Active**.</span></span> <span data-ttu-id="0a23a-142">Dalsze informacje znajdują się w temacie [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="0a23a-142">For more information, see [Create configuration providers and mark them as active](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>
2. <span data-ttu-id="0a23a-143">Na aktywnym dostawcy konfiguracji wybierz pozycję **repozytorium**.</span><span class="sxs-lookup"><span data-stu-id="0a23a-143">On your active configuration provider, select **repository**.</span></span>
3. <span data-ttu-id="0a23a-144">Wybierz typ repozytorium **Globalne** i wybierz opcję **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="0a23a-144">Select the repository type **Global**, and select **Open**.</span></span>
4. <span data-ttu-id="0a23a-145">Na skróconej karcie **Filtr** znajdź konfigurację, którą chcesz usunąć, przy użyciu funkcji **Filtrowania**.</span><span class="sxs-lookup"><span data-stu-id="0a23a-145">On the **Filter** FastTab, find the configuration that you want to delete by using the **Filter** functionality.</span></span>
5. <span data-ttu-id="0a23a-146">W na skróconej karcie **Wersja** wybierz wersję konfiguracji, którą chcesz usunąć, a następnie wybierz opcję **Usuń**:</span><span class="sxs-lookup"><span data-stu-id="0a23a-146">On the **Version** FastTab, select the version of the configuration that you want to delete, and then select **Delete**:</span></span>

    ![Usuwanie konfiguracji z repozytorium globalnego](media/RCS_Delete_from_GlobalRepo.JPG)

6. <span data-ttu-id="0a23a-148">W wyświetlonym oknie wiadomości z potwierdzeniem wybierz przycisk **Tak**.</span><span class="sxs-lookup"><span data-stu-id="0a23a-148">In the confirmation message box, select **Yes**.</span></span>

    ![Komunikat potwierdzający usunięcie wersji konfiguracji](media/RCS_Delete_from_GlobalRepo_Msg.JPG)
 
<span data-ttu-id="0a23a-150">Wersja konfiguracji zostanie usunięta i zostanie wyświetlony komunikat z potwierdzeniem.</span><span class="sxs-lookup"><span data-stu-id="0a23a-150">The configuration version is deleted, and confirmation message is shown.</span></span> 

> [!NOTE]
> <span data-ttu-id="0a23a-151">Konfiguracje mogą być usuwane tylko przez dostawcę konfiguracji, który je utworzył.</span><span class="sxs-lookup"><span data-stu-id="0a23a-151">Configurations can only be deleted by the Configuration provider that created them.</span></span> <span data-ttu-id="0a23a-152">Jeśli konfiguracja została udostępniona innej organizacji, przed jej usunięciem należy cofnąć udostępnianie.</span><span class="sxs-lookup"><span data-stu-id="0a23a-152">If the configuration has been shared with another organization, the configuration will need to be unshared before you delete it.</span></span>
 
