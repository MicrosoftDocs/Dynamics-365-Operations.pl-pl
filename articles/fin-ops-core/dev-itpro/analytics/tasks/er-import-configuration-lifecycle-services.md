---
title: Importowanie konfiguracji z usługi Lifecycle Services
description: W tym temacie opisano sposób importowania nowej wersji konfiguracji raportowania elektronicznego z usług Microsoft Dynamics Lifecycle Services (LCS).
author: NickSelin
ms.date: 06/17/2021
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
ms.openlocfilehash: b58ecb8a7d6f52631dbca7642a4acbcf6ff895a3
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/17/2021
ms.locfileid: "6270844"
---
# <a name="import-a-configuration-from-lifecycle-services"></a><span data-ttu-id="5abe9-103">Importowanie konfiguracji z usługi Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="5abe9-103">Import a configuration from Lifecycle Services</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5abe9-104">Ten temat wyjaśnia, jak użytkownik w roli Administrator systemu lub Deweloper raportowania elektronicznego może zaimportować nową wersję konfiguracji [raportowania elektronicznego (ER)](../general-electronic-reporting.md#Configuration) z [biblioteki zasobów na poziomie projektu](../../lifecycle-services/asset-library.md) w Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="5abe9-104">This topic explains how a user in the System administrator or Electronic reporting developer role can import a new version of an [Electronic reporting (ER) configuration](../general-electronic-reporting.md#Configuration) from the [project-level Asset library](../../lifecycle-services/asset-library.md) in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5abe9-105">[Zrezygnowano](../../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release) z używania LCS jako repozytorium do przechowywania konfiguracji raportowania elektronicznego (ER).</span><span class="sxs-lookup"><span data-stu-id="5abe9-105">The use of LCS as a storage repository for ER configurations is being [deprecated](../../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release).</span></span> <span data-ttu-id="5abe9-106">Więcej informacji: [Regulatory Configuration Service (RCS) — wycofanie pamięci w Lifecycle Services (LCS)](../../../../finance/localizations/rcs-lcs-repo-dep-faq.md).</span><span class="sxs-lookup"><span data-stu-id="5abe9-106">For more information, see [Regulatory Configuration Service (RCS) – Lifecycle Services (LCS) storage deprecation](../../../../finance/localizations/rcs-lcs-repo-dep-faq.md).</span></span>

<span data-ttu-id="5abe9-107">W tym przykładzie wybierzesz żądaną wersję konfiguracji raportowania elektronicznego dla przykładowej firmy Litware, Inc. i zaimportujesz ją. Podane kroki można wykonać dla dowolnej firmy, ponieważ konfiguracje ER są współużytkowane przez wszystkie firmy.</span><span class="sxs-lookup"><span data-stu-id="5abe9-107">In this example, you will select the desired version of the ER configuration and import it for a sample company that is named Litware, Inc. These steps can be completed in any company, because ER configurations are shared among companies.</span></span> <span data-ttu-id="5abe9-108">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze [Przekazywanie konfiguracji ER do usługi Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span><span class="sxs-lookup"><span data-stu-id="5abe9-108">To complete these steps, you must first complete the steps in [Upload a configuration into Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span></span> <span data-ttu-id="5abe9-109">Wymagany jest również dostęp do usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="5abe9-109">Access to LCS is also required.</span></span>

1. <span data-ttu-id="5abe9-110">Zaloguj się do aplikacji przy użyciu jednej z następujących ról:</span><span class="sxs-lookup"><span data-stu-id="5abe9-110">Sign in to the application by using one of the following roles:</span></span>

    - <span data-ttu-id="5abe9-111">Deweloper raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="5abe9-111">Electronic reporting developer</span></span>
    - <span data-ttu-id="5abe9-112">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="5abe9-112">System administrator</span></span>

2. <span data-ttu-id="5abe9-113">Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="5abe9-113">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="5abe9-114">Wybierz **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="5abe9-114">Select **Configurations**.</span></span>

<a name="accessconditions"></a>
> [!NOTE]
> <span data-ttu-id="5abe9-115">Upewnij się, że bieżący użytkownik Dynamics 365 Finance jest członkiem projektu usługi LCS zawierającego [dostęp](../../lifecycle-services/asset-library.md#asset-library-support) do biblioteki elementów zawartości, do której użytkownik chce uzyskać dostęp na potrzeby importowania konfiguracji ER.</span><span class="sxs-lookup"><span data-stu-id="5abe9-115">Make sure that the current Dynamics 365 Finance user is a member of the LCS project that contains the Asset library that the user wants to [access](../../lifecycle-services/asset-library.md#asset-library-support) to import ER configurations.</span></span>
>
> <span data-ttu-id="5abe9-116">Nie można uzyskać dostępu do projektu LCS z poziomu repozytorium ER, które reprezentuje domenę inną niż domena używana w Finance.</span><span class="sxs-lookup"><span data-stu-id="5abe9-116">You can't access an LCS project from an ER repository that represents a different domain than the domain that is used in Finance.</span></span> <span data-ttu-id="5abe9-117">Jeśli zostanie podjęta taka próba, zostanie wyświetlona pusta lista projektów LCS i nie będzie można importować konfiguracji ER z biblioteki elementów zawartości na poziomie projektu w usłudze LCS.</span><span class="sxs-lookup"><span data-stu-id="5abe9-117">If you try, an empty list of LCS projects will be shown, and you won't be able to import ER configurations from the project-level Asset library in LCS.</span></span> <span data-ttu-id="5abe9-118">Aby uzyskać dostęp do bibliotek elementów zawartości na poziomie projektu z repozytorium ER używanego do importowania konfiguracji ER, należy zalogować się do Finance przy użyciu poświadczeń użytkownika, który należy do dzierżawy (domeny), dla którego została zainicjowana bieżąca instancja Finance.</span><span class="sxs-lookup"><span data-stu-id="5abe9-118">To access project-level Asset libraries from an ER repository that is used to import ER configurations, sign in to Finance by using the credentials of a user who belongs to the tenant (domain) that the current Finance instance has been provisioned for.</span></span>

## <a name="delete-a-shared-version-of-a-data-model-configuration"></a><span data-ttu-id="5abe9-119">Usuwanie udostępnionej wersji konfiguracji modelu danych</span><span class="sxs-lookup"><span data-stu-id="5abe9-119">Delete a shared version of a data model configuration</span></span>

1. <span data-ttu-id="5abe9-120">Na stronie **Konfiguracje** w drzewie konfiguracji wybierz pozycję **Przykładowy model konfiguracji**.</span><span class="sxs-lookup"><span data-stu-id="5abe9-120">On the **Configurations** page, in the configurations tree, select **Sample model configuration**.</span></span>

    <span data-ttu-id="5abe9-121">Utworzona pierwsza wersja konfiguracji przykładowego modelu danych została utworzona i opublikowana w usłudze LCS podczas procedury [Przekazywanie konfiguracji ER do usługi Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span><span class="sxs-lookup"><span data-stu-id="5abe9-121">You created the first version of a sample data model configuration and published it to LCS when you completed the steps in [Upload a configuration into Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span></span> <span data-ttu-id="5abe9-122">W tej procedurze usuniesz tę wersję konfiguracji raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="5abe9-122">In this procedure, you will delete that version of the ER configuration.</span></span> <span data-ttu-id="5abe9-123">Następnie ta wersja zostanie zaimportowana z usługi LCS w dalszej części tego tematu.</span><span class="sxs-lookup"><span data-stu-id="5abe9-123">You will then import that version from LCS later in this topic.</span></span>

2. <span data-ttu-id="5abe9-124">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="5abe9-124">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="5abe9-125">W tym przykładzie zaznacz wersję tej konfiguracji mającą stan **Udostępniono**.</span><span class="sxs-lookup"><span data-stu-id="5abe9-125">For this example, select the version of the configuration that has a status of **Shared**.</span></span> <span data-ttu-id="5abe9-126">Ten stan wskazuje, że konfiguracja została opublikowana w usłudze LCS.</span><span class="sxs-lookup"><span data-stu-id="5abe9-126">This status indicates that the configuration has been published to LCS.</span></span>

3. <span data-ttu-id="5abe9-127">Wybierz opcję **Zmień stan**.</span><span class="sxs-lookup"><span data-stu-id="5abe9-127">Select **Change status**.</span></span>
4. <span data-ttu-id="5abe9-128">Kliknij przycisk **Wycofaj**.</span><span class="sxs-lookup"><span data-stu-id="5abe9-128">Select **Discontinue**.</span></span>

    <span data-ttu-id="5abe9-129">Zmieniając stan wybranej wersji z **Udostępniono** na **Wycofano**, wersja staje się możliwa usunięcia.</span><span class="sxs-lookup"><span data-stu-id="5abe9-129">By changing the status of the selected version from **Shared** to **Discontinued**, you make the version available for deletion.</span></span>

5. <span data-ttu-id="5abe9-130">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="5abe9-130">Select **OK**.</span></span>
6. <span data-ttu-id="5abe9-131">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="5abe9-131">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="5abe9-132">W tym przykładzie zaznacz wersję tej konfiguracji mającą stan **Wycofano**.</span><span class="sxs-lookup"><span data-stu-id="5abe9-132">For this example, select the version of the configuration that has a status of **Discontinued**.</span></span>

7. <span data-ttu-id="5abe9-133">Wybierz opcję **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="5abe9-133">Select **Delete**.</span></span>
8. <span data-ttu-id="5abe9-134">Wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="5abe9-134">Select **Yes**.</span></span>

    <span data-ttu-id="5abe9-135">Należy zauważyć, że teraz jest dostępna tylko wersja robocza 2 wybranej konfiguracji przykładowego modelu danych.</span><span class="sxs-lookup"><span data-stu-id="5abe9-135">Notice that the only draft version 2 of the selected data model configuration is now available.</span></span>

9. <span data-ttu-id="5abe9-136">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="5abe9-136">Close the page.</span></span>

## <a name="import-a-shared-version-of-a-data-model-configuration-from-lcs"></a><span data-ttu-id="5abe9-137">Importowanie udostępnionej wersji konfiguracji modelu danych z usługi LCS</span><span class="sxs-lookup"><span data-stu-id="5abe9-137">Import a shared version of a data model configuration from LCS</span></span>

1. <span data-ttu-id="5abe9-138">Wybierz kolejno opcje **Administrowanie organizacją \> Obszary robocze \> Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="5abe9-138">Go to **Organization administration \> Workspaces \> Electronic reporting**.</span></span>

2. <span data-ttu-id="5abe9-139">W obszarze **Dostawcy konfiguracji** wybierz kafelek **Litware, Inc.**.</span><span class="sxs-lookup"><span data-stu-id="5abe9-139">In the **Configuration providers** section, select the **Litware, Inc.** tile.</span></span>

3. <span data-ttu-id="5abe9-140">Na kafelku **Litware, Inc.** wybierz **Repozytoria**.</span><span class="sxs-lookup"><span data-stu-id="5abe9-140">On the **Litware, Inc.** tile, select **Repositories**.</span></span>

    <span data-ttu-id="5abe9-141">Teraz można otworzyć listę repozytoriów dostawcy konfiguracji firmy Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="5abe9-141">You can now open the list of repositories for the Litware, Inc. configuration provider.</span></span>

4. <span data-ttu-id="5abe9-142">Kliknij przycisk **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="5abe9-142">Select **Open**.</span></span>

    <span data-ttu-id="5abe9-143">W tym przykładzie wybierz rekord repozytorium **LCS** i otwórz je.</span><span class="sxs-lookup"><span data-stu-id="5abe9-143">For this example, select the **LCS** repository, and open it.</span></span> <span data-ttu-id="5abe9-144">Musisz mieć [dostęp](#accessconditions) do projektu usługi LCS i do biblioteki elementów zawartości, do której ma dostęp wybrane repozytorium ER.</span><span class="sxs-lookup"><span data-stu-id="5abe9-144">You must have [access](#accessconditions) to the LCS project and to the Asset library that is accessed by the selected ER repository.</span></span>

5. <span data-ttu-id="5abe9-145">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="5abe9-145">In the list, mark the selected row.</span></span>

    <span data-ttu-id="5abe9-146">Na potrzeby tego przykładu, na liście wersji zaznacz pierwszą wersję **konfiguracji przykładowego modelu**.</span><span class="sxs-lookup"><span data-stu-id="5abe9-146">For this example, select the first version of **Sample model configuration** in the version list.</span></span>

6. <span data-ttu-id="5abe9-147">Wybierz opcję **Importuj**.</span><span class="sxs-lookup"><span data-stu-id="5abe9-147">Select **Import**.</span></span>
7. <span data-ttu-id="5abe9-148">Potwierdź import wybranej wersji z usługi LCS klikając **Tak**.</span><span class="sxs-lookup"><span data-stu-id="5abe9-148">Select **Yes** to confirm the import of the selected version from LCS.</span></span>

    <span data-ttu-id="5abe9-149">Komunikat informacyjny potwierdza, że wybrana wersja została pomyślnie zaimportowana.</span><span class="sxs-lookup"><span data-stu-id="5abe9-149">An informational message confirms that the selected version was successfully imported.</span></span>

8. <span data-ttu-id="5abe9-150">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="5abe9-150">Close the page.</span></span>
9. <span data-ttu-id="5abe9-151">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="5abe9-151">Close the page.</span></span>
10. <span data-ttu-id="5abe9-152">Wybierz **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="5abe9-152">Select **Configurations**.</span></span>
11. <span data-ttu-id="5abe9-153">W drzewie zaznacz element **Konfiguracja przykładowego modelu**.</span><span class="sxs-lookup"><span data-stu-id="5abe9-153">In the tree, select **Sample model configuration**.</span></span>
12. <span data-ttu-id="5abe9-154">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="5abe9-154">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="5abe9-155">W tym przykładzie zaznacz wersję tej konfiguracji mającą stan **Udostępniono**.</span><span class="sxs-lookup"><span data-stu-id="5abe9-155">For this example, select the version of the configuration that has a status of **Shared**.</span></span>

    <span data-ttu-id="5abe9-156">Należy zauważyć, że teraz jest również dostępna udostępniona wersja 1 wybranej konfiguracji przykładowego modelu danych.</span><span class="sxs-lookup"><span data-stu-id="5abe9-156">Notice that shared version 1 of the selected data model configuration is also available now.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
