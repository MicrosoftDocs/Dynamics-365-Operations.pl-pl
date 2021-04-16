---
title: Importowanie konfiguracji z usługi Lifecycle Services
description: W tym temacie opisano sposób importowania nowej wersji konfiguracji raportowania elektronicznego z usług Microsoft Dynamics Lifecycle Services (LCS).
author: NickSelin
ms.date: 09/14/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionRepositoryTable, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 674d0dc02b4a53e455a15a06fdb7f24ca3036ba3
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5752371"
---
# <a name="import-a-configuration-from-lifecycle-services"></a><span data-ttu-id="7adae-103">Importowanie konfiguracji z usługi Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="7adae-103">Import a configuration from Lifecycle Services</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7adae-104">Ten temat wyjaśnia, jak użytkownik w roli Administrator systemu lub Deweloper raportowania elektronicznego może zaimportować nową wersję konfiguracji [raportowania elektronicznego (ER)](../general-electronic-reporting.md#Configuration) z [biblioteki zasobów na poziomie projektu](../../lifecycle-services/asset-library.md) w Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="7adae-104">This topic explains how a user in the System administrator or Electronic reporting developer role can import a new version of an [Electronic reporting (ER) configuration](../general-electronic-reporting.md#Configuration) from the [project-level Asset library](../../lifecycle-services/asset-library.md) in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

<span data-ttu-id="7adae-105">W tym przykładzie wybierzesz żądaną wersję konfiguracji raportowania elektronicznego dla przykładowej firmy Litware, Inc. i zaimportujesz ją. Podane kroki można wykonać dla dowolnej firmy, ponieważ konfiguracje ER są współużytkowane przez wszystkie firmy.</span><span class="sxs-lookup"><span data-stu-id="7adae-105">In this example, you will select the desired version of the ER configuration and import it for a sample company that is named Litware, Inc. These steps can be completed in any company, because ER configurations are shared among companies.</span></span> <span data-ttu-id="7adae-106">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze [Przekazywanie konfiguracji ER do usługi Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span><span class="sxs-lookup"><span data-stu-id="7adae-106">To complete these steps, you must first complete the steps in [Upload a configuration into Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span></span> <span data-ttu-id="7adae-107">Wymagany jest również dostęp do usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="7adae-107">Access to LCS is also required.</span></span>

1. <span data-ttu-id="7adae-108">Zaloguj się do aplikacji przy użyciu jednej z następujących ról:</span><span class="sxs-lookup"><span data-stu-id="7adae-108">Sign in to the application by using one of the following roles:</span></span>

    - <span data-ttu-id="7adae-109">Deweloper raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="7adae-109">Electronic reporting developer</span></span>
    - <span data-ttu-id="7adae-110">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="7adae-110">System administrator</span></span>

2. <span data-ttu-id="7adae-111">Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="7adae-111">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="7adae-112">Wybierz **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="7adae-112">Select **Configurations**.</span></span>

<a name="accessconditions"></a>
> [!NOTE]
> <span data-ttu-id="7adae-113">Upewnij się, że bieżący użytkownik Dynamics 365 Finance jest członkiem projektu usługi LCS zawierającego [dostęp](../../lifecycle-services/asset-library.md#asset-library-support) do biblioteki elementów zawartości, do której użytkownik chce uzyskać dostęp na potrzeby importowania konfiguracji ER.</span><span class="sxs-lookup"><span data-stu-id="7adae-113">Make sure that the current Dynamics 365 Finance user is a member of the LCS project that contains the Asset library that the user wants to [access](../../lifecycle-services/asset-library.md#asset-library-support) to import ER configurations.</span></span>
>
> <span data-ttu-id="7adae-114">Nie można uzyskać dostępu do projektu LCS z poziomu repozytorium ER, które reprezentuje domenę inną niż domena używana w Finance.</span><span class="sxs-lookup"><span data-stu-id="7adae-114">You can't access an LCS project from an ER repository that represents a different domain than the domain that is used in Finance.</span></span> <span data-ttu-id="7adae-115">Jeśli zostanie podjęta taka próba, zostanie wyświetlona pusta lista projektów LCS i nie będzie można importować konfiguracji ER z biblioteki elementów zawartości na poziomie projektu w usłudze LCS.</span><span class="sxs-lookup"><span data-stu-id="7adae-115">If you try, an empty list of LCS projects will be shown, and you won't be able to import ER configurations from the project-level Asset library in LCS.</span></span> <span data-ttu-id="7adae-116">Aby uzyskać dostęp do bibliotek elementów zawartości na poziomie projektu z repozytorium ER używanego do importowania konfiguracji ER, należy zalogować się do Finance przy użyciu poświadczeń użytkownika, który należy do dzierżawy (domeny), dla którego została zainicjowana bieżąca instancja Finance.</span><span class="sxs-lookup"><span data-stu-id="7adae-116">To access project-level Asset libraries from an ER repository that is used to import ER configurations, sign in to Finance by using the credentials of a user who belongs to the tenant (domain) that the current Finance instance has been provisioned for.</span></span>

## <a name="delete-a-shared-version-of-a-data-model-configuration"></a><span data-ttu-id="7adae-117">Usuwanie udostępnionej wersji konfiguracji modelu danych</span><span class="sxs-lookup"><span data-stu-id="7adae-117">Delete a shared version of a data model configuration</span></span>

1. <span data-ttu-id="7adae-118">Na stronie **Konfiguracje** w drzewie konfiguracji wybierz pozycję **Przykładowy model konfiguracji**.</span><span class="sxs-lookup"><span data-stu-id="7adae-118">On the **Configurations** page, in the configurations tree, select **Sample model configuration**.</span></span>

    <span data-ttu-id="7adae-119">Utworzona pierwsza wersja konfiguracji przykładowego modelu danych została utworzona i opublikowana w usłudze LCS podczas procedury [Przekazywanie konfiguracji ER do usługi Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span><span class="sxs-lookup"><span data-stu-id="7adae-119">You created the first version of a sample data model configuration and published it to LCS when you completed the steps in [Upload a configuration into Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span></span> <span data-ttu-id="7adae-120">W tej procedurze usuniesz tę wersję konfiguracji raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="7adae-120">In this procedure, you will delete that version of the ER configuration.</span></span> <span data-ttu-id="7adae-121">Następnie ta wersja zostanie zaimportowana z usługi LCS w dalszej części tego tematu.</span><span class="sxs-lookup"><span data-stu-id="7adae-121">You will then import that version from LCS later in this topic.</span></span>

2. <span data-ttu-id="7adae-122">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="7adae-122">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="7adae-123">W tym przykładzie zaznacz wersję tej konfiguracji mającą stan **Udostępniono**.</span><span class="sxs-lookup"><span data-stu-id="7adae-123">For this example, select the version of the configuration that has a status of **Shared**.</span></span> <span data-ttu-id="7adae-124">Ten stan wskazuje, że konfiguracja została opublikowana w usłudze LCS.</span><span class="sxs-lookup"><span data-stu-id="7adae-124">This status indicates that the configuration has been published to LCS.</span></span>

3. <span data-ttu-id="7adae-125">Wybierz opcję **Zmień stan**.</span><span class="sxs-lookup"><span data-stu-id="7adae-125">Select **Change status**.</span></span>
4. <span data-ttu-id="7adae-126">Kliknij przycisk **Wycofaj**.</span><span class="sxs-lookup"><span data-stu-id="7adae-126">Select **Discontinue**.</span></span>

    <span data-ttu-id="7adae-127">Zmieniając stan wybranej wersji z **Udostępniono** na **Wycofano**, wersja staje się możliwa usunięcia.</span><span class="sxs-lookup"><span data-stu-id="7adae-127">By changing the status of the selected version from **Shared** to **Discontinued**, you make the version available for deletion.</span></span>

5. <span data-ttu-id="7adae-128">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="7adae-128">Select **OK**.</span></span>
6. <span data-ttu-id="7adae-129">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="7adae-129">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="7adae-130">W tym przykładzie zaznacz wersję tej konfiguracji mającą stan **Wycofano**.</span><span class="sxs-lookup"><span data-stu-id="7adae-130">For this example, select the version of the configuration that has a status of **Discontinued**.</span></span>

7. <span data-ttu-id="7adae-131">Wybierz opcję **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="7adae-131">Select **Delete**.</span></span>
8. <span data-ttu-id="7adae-132">Wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="7adae-132">Select **Yes**.</span></span>

    <span data-ttu-id="7adae-133">Należy zauważyć, że teraz jest dostępna tylko wersja robocza 2 wybranej konfiguracji przykładowego modelu danych.</span><span class="sxs-lookup"><span data-stu-id="7adae-133">Notice that the only draft version 2 of the selected data model configuration is now available.</span></span>

9. <span data-ttu-id="7adae-134">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7adae-134">Close the page.</span></span>

## <a name="import-a-shared-version-of-a-data-model-configuration-from-lcs"></a><span data-ttu-id="7adae-135">Importowanie udostępnionej wersji konfiguracji modelu danych z usługi LCS</span><span class="sxs-lookup"><span data-stu-id="7adae-135">Import a shared version of a data model configuration from LCS</span></span>

1. <span data-ttu-id="7adae-136">Wybierz kolejno opcje **Administrowanie organizacją \> Obszary robocze \> Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="7adae-136">Go to **Organization administration \> Workspaces \> Electronic reporting**.</span></span>

2. <span data-ttu-id="7adae-137">W obszarze **Dostawcy konfiguracji** wybierz kafelek **Litware, Inc.**.</span><span class="sxs-lookup"><span data-stu-id="7adae-137">In the **Configuration providers** section, select the **Litware, Inc.** tile.</span></span>

3. <span data-ttu-id="7adae-138">Na kafelku **Litware, Inc.** wybierz **Repozytoria**.</span><span class="sxs-lookup"><span data-stu-id="7adae-138">On the **Litware, Inc.** tile, select **Repositories**.</span></span>

    <span data-ttu-id="7adae-139">Teraz można otworzyć listę repozytoriów dostawcy konfiguracji firmy Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="7adae-139">You can now open the list of repositories for the Litware, Inc. configuration provider.</span></span>

4. <span data-ttu-id="7adae-140">Kliknij przycisk **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="7adae-140">Select **Open**.</span></span>

    <span data-ttu-id="7adae-141">W tym przykładzie wybierz rekord repozytorium **LCS** i otwórz je.</span><span class="sxs-lookup"><span data-stu-id="7adae-141">For this example, select the **LCS** repository, and open it.</span></span> <span data-ttu-id="7adae-142">Musisz mieć [dostęp](#accessconditions) do projektu usługi LCS i do biblioteki elementów zawartości, do której ma dostęp wybrane repozytorium ER.</span><span class="sxs-lookup"><span data-stu-id="7adae-142">You must have [access](#accessconditions) to the LCS project and to the Asset library that is accessed by the selected ER repository.</span></span>

5. <span data-ttu-id="7adae-143">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="7adae-143">In the list, mark the selected row.</span></span>

    <span data-ttu-id="7adae-144">Na potrzeby tego przykładu, na liście wersji zaznacz pierwszą wersję **konfiguracji przykładowego modelu**.</span><span class="sxs-lookup"><span data-stu-id="7adae-144">For this example, select the first version of **Sample model configuration** in the version list.</span></span>

6. <span data-ttu-id="7adae-145">Wybierz opcję **Importuj**.</span><span class="sxs-lookup"><span data-stu-id="7adae-145">Select **Import**.</span></span>
7. <span data-ttu-id="7adae-146">Potwierdź import wybranej wersji z usługi LCS klikając **Tak**.</span><span class="sxs-lookup"><span data-stu-id="7adae-146">Select **Yes** to confirm the import of the selected version from LCS.</span></span>

    <span data-ttu-id="7adae-147">Komunikat informacyjny potwierdza, że wybrana wersja została pomyślnie zaimportowana.</span><span class="sxs-lookup"><span data-stu-id="7adae-147">An informational message confirms that the selected version was successfully imported.</span></span>

8. <span data-ttu-id="7adae-148">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7adae-148">Close the page.</span></span>
9. <span data-ttu-id="7adae-149">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7adae-149">Close the page.</span></span>
10. <span data-ttu-id="7adae-150">Wybierz **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="7adae-150">Select **Configurations**.</span></span>
11. <span data-ttu-id="7adae-151">W drzewie zaznacz element **Konfiguracja przykładowego modelu**.</span><span class="sxs-lookup"><span data-stu-id="7adae-151">In the tree, select **Sample model configuration**.</span></span>
12. <span data-ttu-id="7adae-152">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="7adae-152">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="7adae-153">W tym przykładzie zaznacz wersję tej konfiguracji mającą stan **Udostępniono**.</span><span class="sxs-lookup"><span data-stu-id="7adae-153">For this example, select the version of the configuration that has a status of **Shared**.</span></span>

    <span data-ttu-id="7adae-154">Należy zauważyć, że teraz jest również dostępna udostępniona wersja 1 wybranej konfiguracji przykładowego modelu danych.</span><span class="sxs-lookup"><span data-stu-id="7adae-154">Notice that shared version 1 of the selected data model configuration is also available now.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]