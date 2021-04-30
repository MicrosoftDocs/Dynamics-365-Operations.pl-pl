---
title: Importowanie zaktualizowanych wersji konfiguracji programu ER
description: W tym temacie opisano sposób importowania zaktualizowanych wersji konfiguracji raportowania elektronicznego (ER) z globalnego repozytorium usługi Configuration service.
author: NickSelin
ms.date: 06/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionImport, ERWorkspace, ERSolutionRepositoryTable
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 724048991fc8864ef72a5155af66b9c709f4b875
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5893963"
---
# <a name="import-updated-versions-of-er-configurations"></a><span data-ttu-id="04e57-103">Importowanie zaktualizowanych wersji konfiguracji programu ER</span><span class="sxs-lookup"><span data-stu-id="04e57-103">Import updated versions of ER configurations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="04e57-104">[Repozytoria](general-electronic-reporting.md#Repository) raportowania elektronicznego (ER) są używane do udostępniania [konfiguracji ER](general-electronic-reporting.md#Configuration).</span><span class="sxs-lookup"><span data-stu-id="04e57-104">Electronic reporting (ER) [repositories](general-electronic-reporting.md#Repository) are used to share [ER configurations](general-electronic-reporting.md#Configuration).</span></span> <span data-ttu-id="04e57-105">Można [importować](download-electronic-reporting-configuration-lcs.md) konfiguracjeER z różnych repozytoriów do danego wystąpienia rozwiązania Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="04e57-105">You can [import](download-electronic-reporting-configuration-lcs.md) ER configurations from different repositories into your instance of Microsoft Dynamics 365 Finance.</span></span> <span data-ttu-id="04e57-106">Podczas importowania konfiguracji ER [dostawcy konfiguracji](general-electronic-reporting.md#Provider) mogą publikować nowe [wersje](general-electronic-reporting.md#component-versioning) repozytoriów, tak aby można je było udostępniać.</span><span class="sxs-lookup"><span data-stu-id="04e57-106">When you import ER configurations, [configuration providers](general-electronic-reporting.md#Provider) can publish new [versions](general-electronic-reporting.md#component-versioning) repositories so that they can be shared.</span></span>

<span data-ttu-id="04e57-107">W tym temacie opisano sposób importowania zaktualizowanych wersji konfiguracji ER z globalnego repozytorium usługi Configuration service.</span><span class="sxs-lookup"><span data-stu-id="04e57-107">This topic explains how to import updated versions of ER configurations from the Global repository of the Configuration service.</span></span> <span data-ttu-id="04e57-108">Aby uzyskać więcej informacji, należy zapoznać się z tematem [Microsoft Dynamics 365 for Finance and Operations - Regulatory Services, Configuration service](/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).</span><span class="sxs-lookup"><span data-stu-id="04e57-108">For more information, see [Microsoft Dynamics 365 for Finance and Operations - Regulatory Services, Configuration service](/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).</span></span>

## <a name="review-the-available-updated-versions"></a><span data-ttu-id="04e57-109">Przejrzyj dostępne zaktualizowane wersje</span><span class="sxs-lookup"><span data-stu-id="04e57-109">Review the available updated versions</span></span>

1. <span data-ttu-id="04e57-110">Zaloguj się do programu Finance przy użyciu jednej z następujących ról:</span><span class="sxs-lookup"><span data-stu-id="04e57-110">Sign in to Finance by using one of the following roles:</span></span>

    - <span data-ttu-id="04e57-111">Deweloper raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="04e57-111">Electronic reporting developer</span></span>
    - <span data-ttu-id="04e57-112">Konsultant funkcjonalny raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="04e57-112">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="04e57-113">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="04e57-113">System administrator</span></span>

2. <span data-ttu-id="04e57-114">Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="04e57-114">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="04e57-115">Na stronie **Konfiguracje lokalizacji** w sekcji **Powiązane łącza** wybierz kafelek **Import aktualizacji wersji konfiguracji**.</span><span class="sxs-lookup"><span data-stu-id="04e57-115">On the **Localization configurations** page, in the **Related links** section, select **Import configurations versions updates**.</span></span>

    ![Strona lokalizacji konfiguracji](./media/er-download-updated-versions-global-repo1.png)

4. <span data-ttu-id="04e57-117">W oknie dialogowym **Importowanie aktualizacji wersji konfiguracji ER** w polu **Tryb uruchamiania** wybierz opcję **Wyświetl tylko dostępne aktualizacje**.</span><span class="sxs-lookup"><span data-stu-id="04e57-117">In the **Import electronic reporting configurations versions updates** dialog box, in the **Run mode** field, select **Only show available updates**.</span></span> <span data-ttu-id="04e57-118">Następnie wybierz opcję **OK**.</span><span class="sxs-lookup"><span data-stu-id="04e57-118">Then select **OK**.</span></span> 

    ![Pole tryb uruchamiania ustawione w taki sposób, aby pokazywać tylko dostępne aktualizacje](./media/er-download-updated-versions-global-repo2.png)

5. <span data-ttu-id="04e57-120">Przejrzyj odebrane komunikaty.</span><span class="sxs-lookup"><span data-stu-id="04e57-120">Review the messages that you receive.</span></span> <span data-ttu-id="04e57-121">Komunikaty te zawierają następujące informacje na temat konfiguracji ER w bieżącym wystąpieniu Finance oraz w jaki sposób odnoszą się one do zawartości repozytorium globalnego:</span><span class="sxs-lookup"><span data-stu-id="04e57-121">These messages provide the following information about the ER configurations in the current Finance instance and how they compare to the content of the Global repository:</span></span>

    - <span data-ttu-id="04e57-122">Łączna liczba konfiguracji ER</span><span class="sxs-lookup"><span data-stu-id="04e57-122">The total number of ER configurations</span></span>
    - <span data-ttu-id="04e57-123">Konfiguracje ER, które nie znajdują się w repozytorium globalnym</span><span class="sxs-lookup"><span data-stu-id="04e57-123">ER configurations that aren't present in the Global repository</span></span>
    - <span data-ttu-id="04e57-124">Konfiguracje ER, dla których najnowsza wersja jest już dostępna w bieżącym wystąpieniu Finance (aby wyświetlić pełną listę tych konfiguracji ER, należy wybrać łącze **Szczegóły wiadomości**).</span><span class="sxs-lookup"><span data-stu-id="04e57-124">ER configurations for which the latest version is already available in the current Finance instance (To view the full list of these ER configurations, select the **Message details** link.)</span></span>

        ![„Najnowsze wersje następujących konfiguracji zostały już zaimportowane” – komunikat i jego szczegóły](./media/er-download-updated-versions-global-repo3.png)

    - <span data-ttu-id="04e57-126">Konfiguracje ER, dla których najnowsza wersja jest już dostępna w repozytorium globalnym i które mogą być zaimportowane do bieżącego wystąpienia Finance (aby wyświetlić pełną listę tych konfiguracji ER, należy wybrać łącze **Szczegóły wiadomości**).</span><span class="sxs-lookup"><span data-stu-id="04e57-126">ER configurations for which the latest version is available in the Global repository and can be imported into the current Finance instance (To view the full list of these ER configurations, select the **Message details** link.)</span></span>

        ![„Dostępne aktualizacje” – komunikat i jego szczegóły](./media/er-download-updated-versions-global-repo4.png)

## <a name="import-available-updated-versions"></a><span data-ttu-id="04e57-128">Importowanie dostępnych wersji aktualizacji</span><span class="sxs-lookup"><span data-stu-id="04e57-128">Import available updated versions</span></span>

1. <span data-ttu-id="04e57-129">Zaloguj się do programu Finance przy użyciu jednej z następujących ról:</span><span class="sxs-lookup"><span data-stu-id="04e57-129">Sign in to Finance by using one of the following roles:</span></span>

    - <span data-ttu-id="04e57-130">Deweloper raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="04e57-130">Electronic reporting developer</span></span>
    - <span data-ttu-id="04e57-131">Konsultant funkcjonalny raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="04e57-131">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="04e57-132">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="04e57-132">System administrator</span></span>

2. <span data-ttu-id="04e57-133">Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="04e57-133">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="04e57-134">Na stronie **Konfiguracje lokalizacji** w sekcji **Powiązane łącza** wybierz kafelek **Import aktualizacji wersji konfiguracji**.</span><span class="sxs-lookup"><span data-stu-id="04e57-134">On the **Localization configurations** page, in the **Related links** section, select **Import configurations versions updates**.</span></span>
4. <span data-ttu-id="04e57-135">W oknie dialogowym **Importowanie wersji konfiguracji raportowania elektronicznego** w polu **Tryb uruchamiania** wybierz opcję **Importuj najnowsze aktualizacje**, aby zaimportować najnowsze wersje konfiguracji ER z repozytorium globalnego do bieżącego wystąpienia Finance.</span><span class="sxs-lookup"><span data-stu-id="04e57-135">In the **Import electronic reporting configurations versions updates** dialog box, in the **Run mode** field, select **Import latest updates** to import the latest versions of ER configurations from the Global repository into the current Finance instance.</span></span>
5. <span data-ttu-id="04e57-136">Aby zaplanować zadanie wsadowe importowania, na skróconej karcie **Uruchom w tle** ustaw wartość opcji **Przetwarzanie wsadowe** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="04e57-136">To schedule a batch job for the import, on the **Run in the background** FastTab, set the **Batch processing** option to **Yes**.</span></span> <span data-ttu-id="04e57-137">Jeśli chcesz okresowo powtarzać import, skonfiguruj wymagany cykl.</span><span class="sxs-lookup"><span data-stu-id="04e57-137">If you want to repeat the import periodically, configure the required recurrence.</span></span>

    ![Pole tryb uruchamiania ustawione na importowanie najnowszych aktualizacji](./media/er-download-updated-versions-global-repo5.png)

6. <span data-ttu-id="04e57-139">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="04e57-139">Select **OK**.</span></span>
7. <span data-ttu-id="04e57-140">Aby dowiedzieć się, jakie wersje konfiguracji zostały zaimportowane, wykonaj jedną z następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="04e57-140">To learn what configuration versions have been imported, follow one of these steps:</span></span>

    - <span data-ttu-id="04e57-141">Jeśli import zostanie uruchomiony interaktywnie zamiast używania zadania wsadowego, należy przejrzeć otrzymane komunikaty.</span><span class="sxs-lookup"><span data-stu-id="04e57-141">If you run the import interactively instead of using a batch job, review the messages that you receive.</span></span>

        ![Komunikaty odebrane podczas interaktywnego przebiegu importu](./media/er-download-updated-versions-global-repo6.png)

    - <span data-ttu-id="04e57-143">W przypadku uruchomienia operacji importowania w trybie wsadowym należy wykonać następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="04e57-143">If you run the import in batch mode, follow these steps:</span></span>

        1. <span data-ttu-id="04e57-144">Wybierz kolejno opcje **Wspólne** \> **Zapytania** \> **Zadania wsadowe** \> **Moje zadania wsadowe**.</span><span class="sxs-lookup"><span data-stu-id="04e57-144">Go to **Common** \> **Inquiries** \> **Batch jobs** \> **My batch jobs**.</span></span>
        2. <span data-ttu-id="04e57-145">Znajdź i zaznacz zadanie **Importowania wersji konfiguracji raportowania elektronicznego**, a następnie w okienku akcji na karcie **Zadanie wsadowe** wybierz opcję **Historia zadań wsadowych**, aby wyświetlić historię zadań.</span><span class="sxs-lookup"><span data-stu-id="04e57-145">Find and select the **Import electronic reporting configurations versions updates** job, and then, on the Action Pane, on the **Batch job** tab, select **Batch job history** to view the job history.</span></span>
        3. <span data-ttu-id="04e57-146">Na stronie **Historia zadań wsadowych** wybierz pozycję **Dziennik**.</span><span class="sxs-lookup"><span data-stu-id="04e57-146">On the **Batch job history** page, select **Log**.</span></span> <span data-ttu-id="04e57-147">Następnie w odebranej wiadomości wybierz łącze **Szczegóły komunikatu**, aby wyświetlić dziennik zadań.</span><span class="sxs-lookup"><span data-stu-id="04e57-147">Then, in the message that you receive, select the **Message details** link to view the job log.</span></span>

        ![Dziennik zadań](./media/er-download-updated-versions-global-repo7.png)

> [!IMPORTANT]
> <span data-ttu-id="04e57-149">Nie zaleca się planowania cyklicznego zadania wsadowego w celu zaimportowania zaktualizowanych wersji konfiguracji ER bezpośrednio z repozytorium globalnego do środowiska produkcyjnego, ponieważ importowane wersje są natychmiast dostępne do użycia.</span><span class="sxs-lookup"><span data-stu-id="04e57-149">We don't recommend that you schedule a recurring batch job to import updated versions of ER configurations directly from the Global repository into a production environment, because the imported versions will immediately be available for use.</span></span> <span data-ttu-id="04e57-150">Zamiast tego należy użyć tej metody w celu wdrożenia wersji konfiguracji systemu w środowisku piaskownicy.</span><span class="sxs-lookup"><span data-stu-id="04e57-150">Instead, use this approach to deploy versions of ER configurations to a sandbox environment.</span></span> <span data-ttu-id="04e57-151">Następnie można je ocenić w środowisku piaskownicy przed wdrożeniem w środowisku produkcyjnym.</span><span class="sxs-lookup"><span data-stu-id="04e57-151">They can then be evaluated in the sandbox environment before they are deployed to a production environment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="04e57-152">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="04e57-152">Additional resources</span></span>

- [<span data-ttu-id="04e57-153">Omówienie raportowania elektronicznego (ER)</span><span class="sxs-lookup"><span data-stu-id="04e57-153">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="04e57-154">Pobieranie konfiguracji ER z globalnego repozytorium usługi Configuration service</span><span class="sxs-lookup"><span data-stu-id="04e57-154">Download ER configurations from the Global repository of Configuration service</span></span>](er-download-configurations-global-repo.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]