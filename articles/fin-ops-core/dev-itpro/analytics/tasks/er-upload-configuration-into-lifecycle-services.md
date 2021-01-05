---
title: Przekazywanie konfiguracji do usługi Lifecycle Services
description: Ten temat wyjaśnia, jak użytkownik w roli Administrator systemu lub Deweloper raportowania elektronicznego może utworzyć nową konfigurację raportowania elektronicznego (ER) i przekazać ją do usługi Microsoft Dynamics Lifecycle Services (LCS).
author: NickSelin
manager: AnnBe
ms.date: 09/14/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2ebafb52882fd33f4f0ef140c5d23d3288af97a2
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684170"
---
# <a name="upload-a-configuration-into-lifecycle-services"></a><span data-ttu-id="4d536-103">Przekazywanie konfiguracji do usługi Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="4d536-103">Upload a configuration into Lifecycle Services</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4d536-104">Ten temat wyjaśnia, jak użytkownik w roli Administrator systemu lub Deweloper raportowania elektronicznego może utworzyć nową konfigurację [raportowania elektronicznego (ER)](../general-electronic-reporting.md#Configuration) i przekazać ją do [biblioteki zasobów na poziomie projektu](../../lifecycle-services/asset-library.md) w Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="4d536-104">This topic explains how a user in the System administrator or Electronic reporting developer role can create a new [Electronic reporting (ER) configuration](../general-electronic-reporting.md#Configuration) and upload it into the [project-level Asset library](../../lifecycle-services/asset-library.md) in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

<span data-ttu-id="4d536-105">W tym przykładzie utworzysz konfigurację dla przykładowej firmy Litware, Inc. i przekażesz ją do usługi LCS. Podane kroki można ukończyć dla dowolnej firmy, ponieważ konfiguracje ER są współużytkowane przez wszystkie firmy.</span><span class="sxs-lookup"><span data-stu-id="4d536-105">In this example, you will create a configuration and upload it into LCS for a sample company that is named Litware, Inc. These steps can be completed in any company, because ER configurations are shared among companies.</span></span> <span data-ttu-id="4d536-106">Aby wykonać te kroki, należy najpierw wykonać kroki w temacie [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywne](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="4d536-106">To complete these steps, you must first complete the steps in [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> <span data-ttu-id="4d536-107">Wymagany jest również dostęp do usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="4d536-107">Access to LCS is also required.</span></span>

1. <span data-ttu-id="4d536-108">Zaloguj się do aplikacji przy użyciu jednej z następujących ról:</span><span class="sxs-lookup"><span data-stu-id="4d536-108">Sign in to the application by using one of the following roles:</span></span>

    - <span data-ttu-id="4d536-109">Deweloper raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="4d536-109">Electronic reporting developer</span></span>
    - <span data-ttu-id="4d536-110">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="4d536-110">System administrator</span></span>

2. <span data-ttu-id="4d536-111">Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="4d536-111">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="4d536-112">Wybierz firmę **Litware, Inc.**” i ustaw ją jako **aktywną**.</span><span class="sxs-lookup"><span data-stu-id="4d536-112">Select **Litware, Inc.**, and mark it as **Active**.</span></span>
4. <span data-ttu-id="4d536-113">Wybierz **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="4d536-113">Select **Configurations**.</span></span>

<a name="accessconditions"></a>
> [!NOTE]
> <span data-ttu-id="4d536-114">Upewnij się, że bieżący użytkownik Dynamics 365 Finance jest członkiem projektu usługi LCS zawierającego [bibliotekę elementów zawartości](../../lifecycle-services/asset-library.md#asset-library-support), która jest używana do importowania konfiguracji ER.</span><span class="sxs-lookup"><span data-stu-id="4d536-114">Make sure that the current Dynamics 365 Finance user is a member of the LCS project that contains the [Asset library](../../lifecycle-services/asset-library.md#asset-library-support) that is used to import ER configurations.</span></span>
>
> <span data-ttu-id="4d536-115">Nie można uzyskać dostępu do projektu LCS z poziomu repozytorium ER, które reprezentuje domenę inną niż domena używana w Finance.</span><span class="sxs-lookup"><span data-stu-id="4d536-115">You can't access an LCS project from an ER repository that represents a different domain than the domain that is used in Finance.</span></span> <span data-ttu-id="4d536-116">Jeśli zostanie podjęta taka próba, zostanie wyświetlona pusta lista projektów LCS i nie będzie można importować konfiguracji ER z biblioteki elementów zawartości na poziomie projektu w usłudze LCS.</span><span class="sxs-lookup"><span data-stu-id="4d536-116">If you try, an empty list of LCS projects will be shown, and you won't be able to import ER configurations from the project-level Asset library in LCS.</span></span> <span data-ttu-id="4d536-117">Aby uzyskać dostęp do bibliotek elementów zawartości na poziomie projektu z repozytorium ER używanego do importowania konfiguracji ER, należy zalogować się do Finance przy użyciu poświadczeń użytkownika, który należy do dzierżawy (domeny), dla którego została zainicjowana bieżąca instancja Finance.</span><span class="sxs-lookup"><span data-stu-id="4d536-117">To access project-level Asset libraries from an ER repository that is used to import ER configurations, sign in to Finance by using the credentials of a user who belongs to the tenant (domain) that the current Finance instance has been provisioned for.</span></span>

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="4d536-118">Tworzenie nowej konfiguracji modelu danych</span><span class="sxs-lookup"><span data-stu-id="4d536-118">Create a new data model configuration</span></span>

1. <span data-ttu-id="4d536-119">Przejdź do opcji **Administrowanie organizacją \> Raporty elektroniczne \> Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="4d536-119">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
2. <span data-ttu-id="4d536-120">Wybierz przycisk **Utwórz konfigurację** na stronie **konfiguracje**, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="4d536-120">On the **Configurations** page, select **Create configuration** to open the drop-down dialog box.</span></span>

    <span data-ttu-id="4d536-121">W tym przykładzie utworzysz konfigurację, która zawiera przykładowy model danych dla dokumentów elektronicznych.</span><span class="sxs-lookup"><span data-stu-id="4d536-121">In this example, you will create a configuration that contains a sample data model for electronic documents.</span></span> <span data-ttu-id="4d536-122">Ta konfiguracja modelu danych zostanie później przekazana do usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="4d536-122">This data model configuration will be uploaded into LCS later.</span></span>

3. <span data-ttu-id="4d536-123">W polu **Nazwa** wpisz **Konfiguracja przykładowego modelu**.</span><span class="sxs-lookup"><span data-stu-id="4d536-123">In the **Name** field, enter **Sample model configuration**.</span></span>
4. <span data-ttu-id="4d536-124">W polu **Opis** wpisz **Konfiguracja przykładowego modelu**.</span><span class="sxs-lookup"><span data-stu-id="4d536-124">In the **Description** field, enter **Sample model configuration**.</span></span>
5. <span data-ttu-id="4d536-125">Wybierz **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="4d536-125">Select **Create configuration**.</span></span>
6. <span data-ttu-id="4d536-126">Wybierz **Projektanta modelu**.</span><span class="sxs-lookup"><span data-stu-id="4d536-126">Select **Model designer**.</span></span>
7. <span data-ttu-id="4d536-127">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="4d536-127">Select **New**.</span></span>
8. <span data-ttu-id="4d536-128">W polu **Nazwa** wpisz **Punkt wejścia**.</span><span class="sxs-lookup"><span data-stu-id="4d536-128">In the **Name** field, enter **Entry point**.</span></span>
9. <span data-ttu-id="4d536-129">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="4d536-129">Select **Add**.</span></span>
10. <span data-ttu-id="4d536-130">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="4d536-130">Select **Save**.</span></span>
11. <span data-ttu-id="4d536-131">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="4d536-131">Close the page.</span></span>
12. <span data-ttu-id="4d536-132">Wybierz opcję **Zmień stan**.</span><span class="sxs-lookup"><span data-stu-id="4d536-132">Select **Change status**.</span></span>
13. <span data-ttu-id="4d536-133">Wybierz opcję **Zakończone**.</span><span class="sxs-lookup"><span data-stu-id="4d536-133">Select **Complete**.</span></span>
14. <span data-ttu-id="4d536-134">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="4d536-134">Select **OK**.</span></span>
15. <span data-ttu-id="4d536-135">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="4d536-135">Close the page.</span></span>

## <a name="register-a-new-repository"></a><span data-ttu-id="4d536-136">Rejestrowanie nowego repozytorium</span><span class="sxs-lookup"><span data-stu-id="4d536-136">Register a new repository</span></span>

1. <span data-ttu-id="4d536-137">Wybierz kolejno opcje **Administrowanie organizacją \> Obszary robocze \> Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="4d536-137">Go to **Organization administration \> Workspaces \> Electronic reporting**.</span></span>

2. <span data-ttu-id="4d536-138">W obszarze **Dostawcy konfiguracji** wybierz kafelek **Litware, Inc.**.</span><span class="sxs-lookup"><span data-stu-id="4d536-138">In the **Configuration providers** section, select the **Litware, Inc.** tile.</span></span>

3. <span data-ttu-id="4d536-139">Na kafelku **Litware, Inc.** wybierz **Repozytoria**.</span><span class="sxs-lookup"><span data-stu-id="4d536-139">On the **Litware, Inc.** tile, select **Repositories**.</span></span>

    <span data-ttu-id="4d536-140">Teraz można otworzyć listę repozytoriów dostawcy konfiguracji firmy Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="4d536-140">You can now open the list of repositories for the Litware, Inc. configuration provider.</span></span>

4. <span data-ttu-id="4d536-141">Wybierz przycisk **Dodaj**, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="4d536-141">Select **Add** to open the drop-down dialog box.</span></span>

    <span data-ttu-id="4d536-142">Teraz można dodać nowe repozytorium.</span><span class="sxs-lookup"><span data-stu-id="4d536-142">You can now add a new repository.</span></span>

5. <span data-ttu-id="4d536-143">W polu **Typ repozytorium konfiguracji** wpisz **LCS**.</span><span class="sxs-lookup"><span data-stu-id="4d536-143">In the **Configuration repository enter** field, select **LCS**.</span></span>
6. <span data-ttu-id="4d536-144">Kliknij opcję **Utwórz repozytorium**.</span><span class="sxs-lookup"><span data-stu-id="4d536-144">Select **Create repository**.</span></span>
7. <span data-ttu-id="4d536-145">W polu **Projekt** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="4d536-145">In the **Project** field, enter or select a value.</span></span>

    <span data-ttu-id="4d536-146">W tym przykładzie wybierz projekt LCS.</span><span class="sxs-lookup"><span data-stu-id="4d536-146">For this example, select the desired LCS project.</span></span> <span data-ttu-id="4d536-147">Trzeba mieć [dostęp](#accessconditions) do projektu.</span><span class="sxs-lookup"><span data-stu-id="4d536-147">You must have [access](#accessconditions) to the project.</span></span>

8. <span data-ttu-id="4d536-148">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="4d536-148">Select **OK**.</span></span>

    <span data-ttu-id="4d536-149">Wypełnij wpis nowego repozytorium.</span><span class="sxs-lookup"><span data-stu-id="4d536-149">Complete a new repository entry.</span></span>

9. <span data-ttu-id="4d536-150">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="4d536-150">In the list, mark the selected row.</span></span>

    <span data-ttu-id="4d536-151">W tym przykładzie wybierz rekord repozytorium **LCS**.</span><span class="sxs-lookup"><span data-stu-id="4d536-151">For this example, select the **LCS** repository record.</span></span>

    <span data-ttu-id="4d536-152">Należy zauważyć, że zarejestrowane repozytorium jest oznaczone przez bieżącego dostawcę.</span><span class="sxs-lookup"><span data-stu-id="4d536-152">Note that a registered repository is marked by the current provider.</span></span> <span data-ttu-id="4d536-153">Innymi słowy, tylko konfiguracje należące do tego dostawcy mogą być umieszczane w tym repozytorium i w związku z tym przekazywane do wybranego projektu usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="4d536-153">In other words, only configurations that are owned by that provider can be put in this repository and therefore uploaded into the selected LCS project.</span></span>

10. <span data-ttu-id="4d536-154">Kliknij przycisk **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="4d536-154">Select **Open**.</span></span>

    <span data-ttu-id="4d536-155">Otwórz repozytorium, aby wyświetlić listę konfiguracji raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="4d536-155">You open the repository to view the list of ER configurations.</span></span> <span data-ttu-id="4d536-156">Lista będzie pusta, jeśli ten projekt nie był jeszcze używany w udostępnianiu konfiguracji raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="4d536-156">If the selected project hasn't yet been used for ER configurations sharing, the list will be empty.</span></span>

11. <span data-ttu-id="4d536-157">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="4d536-157">Close the page.</span></span>
12. <span data-ttu-id="4d536-158">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="4d536-158">Close the page.</span></span>

## <a name="upload-a-configuration-into-lcs"></a><span data-ttu-id="4d536-159">Przesyłanie konfiguracji do usługi LCS</span><span class="sxs-lookup"><span data-stu-id="4d536-159">Upload a configuration into LCS</span></span>

1. <span data-ttu-id="4d536-160">Przejdź do opcji **Administrowanie organizacją \> Raporty elektroniczne \> Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="4d536-160">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
2. <span data-ttu-id="4d536-161">Na stronie **Konfiguracje** w drzewie konfiguracji wybierz pozycję **Przykładowy model konfiguracji**.</span><span class="sxs-lookup"><span data-stu-id="4d536-161">On the **Configurations** page, in the configurations tree, select **Sample model configuration**.</span></span>

    <span data-ttu-id="4d536-162">Musisz zaznaczyć utworzone konfiguracje, które zostały już ukończone.</span><span class="sxs-lookup"><span data-stu-id="4d536-162">You must select a created configuration that has been already completed.</span></span>

3. <span data-ttu-id="4d536-163">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="4d536-163">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="4d536-164">W tym przykładzie zaznacz wersję wybranej konfiguracji ze stanem **Zakończono**.</span><span class="sxs-lookup"><span data-stu-id="4d536-164">For this example, select the version of the selected configuration that has a status of **Completed**.</span></span>

4. <span data-ttu-id="4d536-165">Wybierz opcję **Zmień stan**.</span><span class="sxs-lookup"><span data-stu-id="4d536-165">Select **Change status**.</span></span>
5. <span data-ttu-id="4d536-166">Wybierz opcję **Udostępnij**.</span><span class="sxs-lookup"><span data-stu-id="4d536-166">Select **Share**.</span></span>

    <span data-ttu-id="4d536-167">Stan konfiguracji zmienia się z **Zakończono** na **Współużytkowana** gdy konfiguracja jest opublikowana w usłudze LCS.</span><span class="sxs-lookup"><span data-stu-id="4d536-167">The status of the configuration is changed from **Completed** to **Shared** when the configuration is published in LCS.</span></span>

6. <span data-ttu-id="4d536-168">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="4d536-168">Select **OK**.</span></span>
7. <span data-ttu-id="4d536-169">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="4d536-169">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="4d536-170">W tym przykładzie zaznacz wersję tej konfiguracji mającą stan **Udostępniono**.</span><span class="sxs-lookup"><span data-stu-id="4d536-170">For this example, select the configuration version that has a status of **Shared**.</span></span>

    <span data-ttu-id="4d536-171">Należy zauważyć, że stan wybranej wersji został zmieniony z **Zakończono** na **Udostępniono**.</span><span class="sxs-lookup"><span data-stu-id="4d536-171">Note that the status of the selected version was changed from **Completed** to **Shared**.</span></span>

8. <span data-ttu-id="4d536-172">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="4d536-172">Close the page.</span></span>
9. <span data-ttu-id="4d536-173">Wybierz **Repozytoria**.</span><span class="sxs-lookup"><span data-stu-id="4d536-173">Select **Repositories**.</span></span>

    <span data-ttu-id="4d536-174">Teraz można otworzyć listę repozytoriów dostawcy konfiguracji firmy Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="4d536-174">You can now open the list of repositories for the Litware, Inc. configuration provider.</span></span>

10. <span data-ttu-id="4d536-175">Kliknij przycisk **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="4d536-175">Select **Open**.</span></span>

    <span data-ttu-id="4d536-176">W tym przykładzie wybierz rekord repozytorium **LCS** i otwórz je.</span><span class="sxs-lookup"><span data-stu-id="4d536-176">For this example, select the **LCS** repository, and open it.</span></span>

    <span data-ttu-id="4d536-177">Należy zwrócić uwagę, że wybrana konfiguracja jest wyświetlana jako element zawartości wybranego projektu usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="4d536-177">Notice that the selected configuration is shown as an asset of the selected LCS project.</span></span>

11. <span data-ttu-id="4d536-178">Otwórz LCS, przechodząc na <https://lcs.dynamics.com>.</span><span class="sxs-lookup"><span data-stu-id="4d536-178">Open LCS by going to <https://lcs.dynamics.com>.</span></span>
12. <span data-ttu-id="4d536-179">Otwórz projekt, który został użyty wcześniej do rejestracji repozytorium.</span><span class="sxs-lookup"><span data-stu-id="4d536-179">Open a project that was used earlier for repository registration.</span></span>
13. <span data-ttu-id="4d536-180">Otwórz bibliotekę elementów zawartości projektu.</span><span class="sxs-lookup"><span data-stu-id="4d536-180">Open the Asset library of the project.</span></span>
14. <span data-ttu-id="4d536-181">Wybierz typ elementu **Konfiguracja GER**.</span><span class="sxs-lookup"><span data-stu-id="4d536-181">Select the **GER configuration** asset type.</span></span>

    <span data-ttu-id="4d536-182">Przekazana konfiguracja ER powinna zostać wyświetlona na liście.</span><span class="sxs-lookup"><span data-stu-id="4d536-182">The ER configuration that you uploaded should be listed.</span></span>

    <span data-ttu-id="4d536-183">Należy zauważyć, że przekazaną konfigurację usługi LCS można zaimportować do innego wystąpienia, jeśli dostawcy mają dostęp do tego projektu usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="4d536-183">Note that the uploaded LCS configuration can be imported into another instance if providers have access to this LCS project.</span></span>
