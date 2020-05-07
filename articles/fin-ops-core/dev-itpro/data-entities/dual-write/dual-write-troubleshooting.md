---
title: Rozwiązywanie ogólnych problemów
description: Ten temat zawiera informacje dotyczące ogólnego rozwiązywania problemów dotyczących integracji o podwójnym zapisie między aplikacjami Finance and Operations i Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: d5d9dbce0c74d32107db6bbae033b921e4201693
ms.sourcegitcommit: e06da171b9cba8163893e30244c52a9ce0901146
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/21/2020
ms.locfileid: "3275657"
---
# <a name="general-troubleshooting"></a><span data-ttu-id="14dfe-103">Rozwiązywanie ogólnych problemów</span><span class="sxs-lookup"><span data-stu-id="14dfe-103">General troubleshooting</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="14dfe-104">Ten temat zawiera informacje dotyczące ogólnego rozwiązywania problemów dotyczących integracji o podwójnym zapisie między aplikacjami Finance and Operations i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="14dfe-104">This topic provides general troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="14dfe-105">Niektóre problemy, których ten problem może wymagać od roli administratora systemu lub poświadczeń administratora dzierżawcy Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="14dfe-105">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="14dfe-106">W sekcji dotyczącej każdego zagadnienia wyjaśniono, czy określona rola lub poświadczenia są wymagane.</span><span class="sxs-lookup"><span data-stu-id="14dfe-106">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="when-you-try-to-install-the-dual-write-package-by-using-the-package-deployer-tool-no-available-solutions-are-shown"></a><span data-ttu-id="14dfe-107">Podczas próby zainstalowania pakietu podwójnego odpisu za pomocą narzędzia package deployer nie są wyświetlane żadne dostępne rozwiązania</span><span class="sxs-lookup"><span data-stu-id="14dfe-107">When you try to install the dual-write package by using the package deployer tool, no available solutions are shown</span></span>

<span data-ttu-id="14dfe-108">Niektóre wersje narzędzia package deployer są niezgodne z pakietem rozwiązania podwójnego zapisywania.</span><span class="sxs-lookup"><span data-stu-id="14dfe-108">Some versions of the package deployer tool are incompatible with the dual-write solution package.</span></span> <span data-ttu-id="14dfe-109">Aby pomyślnie zainstalować pakiet, należy pamiętać o użyciu [wersji 9.1.0.20](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.PackageDeployment.Wpf/9.1.0.20) lub nowszej narzędzia package deployer.</span><span class="sxs-lookup"><span data-stu-id="14dfe-109">To successfully install the package, be sure to use [version 9.1.0.20](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.PackageDeployment.Wpf/9.1.0.20) or later of the package deployer tool.</span></span>

<span data-ttu-id="14dfe-110">Po zainstalowaniu narzędzia package deployer zainstaluj pakiet rozwiązania, wykonując poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="14dfe-110">After you install the package deployer tool, install the solution package by following these steps.</span></span>

1. <span data-ttu-id="14dfe-111">Pobierz najnowszy plik pakietu rozwiązania z Yammer.com.</span><span class="sxs-lookup"><span data-stu-id="14dfe-111">Download the latest solution package file from Yammer.com.</span></span> <span data-ttu-id="14dfe-112">Po pobraniu pliku zip Package kliknij go prawym przyciskiem myszy i wybierz polecenie **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="14dfe-112">After the package zip file is downloaded, right-click it, and select **Properties**.</span></span> <span data-ttu-id="14dfe-113">Zaznacz pole wyboru **Odblokuj**, a następnie kliknij przycisk **Zastosuj**.</span><span class="sxs-lookup"><span data-stu-id="14dfe-113">Select the **Unblock** check box, and then select **Apply**.</span></span> <span data-ttu-id="14dfe-114">Jeśli pole wyboru **Odblokuj** nie jest widoczne, plik zip jest już odblokowany i można pominąć ten krok.</span><span class="sxs-lookup"><span data-stu-id="14dfe-114">If you don't see the **Unblock** check box, the zip file is already unblocked, and you can skip this step.</span></span>

    ![Okno dialogowe Właściwości](media/unblock_option.png)

2. <span data-ttu-id="14dfe-116">Wyodrębnij plik zip pakietu i skopiuj wszystkie pliki w folderze **Dynamics365FinanceAndOperationsCommon. PackageDeployer.2.0.438**.</span><span class="sxs-lookup"><span data-stu-id="14dfe-116">Extract the package zip file, and copy all the files in the **Dynamics365FinanceAndOperationsCommon.PackageDeployer.2.0.438** folder.</span></span>

    ![Zawartość folderu Dynamics365FinanceAndOperationsCommon. PackageDeployer.2.0.438](media/extract_package.png)

3. <span data-ttu-id="14dfe-118">Wklej wszystkie skopiowane pliki do folderu **Narzędzia** narzędzia package deployer.</span><span class="sxs-lookup"><span data-stu-id="14dfe-118">Paste all the copied files into the **Tools** folder of the package deployer tool.</span></span> 
4. <span data-ttu-id="14dfe-119">Uruchom **PackageDeployerexe**, aby wybrać środowisko Common Data Service i zainstalować rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="14dfe-119">Run **PackageDeployer.exe** to select the Common Data Service environment and install the solutions.</span></span>

    ![Zawartość folderu Narzędzia](media/paste_copied_files.png)

## <a name="enable-and-view-the-plug-in-trace-log-in-common-data-service-to-view-error-details"></a><span data-ttu-id="14dfe-121">Umożliwia włączenie i wyświetlenie logowania śledzenia wtyczki w Common Data Service w celu wyświetlenia szczegółów błędu</span><span class="sxs-lookup"><span data-stu-id="14dfe-121">Enable and view the plug-in trace log in Common Data Service to view error details</span></span>

<span data-ttu-id="14dfe-122">**Wymagana rola do włączenia dziennika śledzenia i wyświetlenia błędów:** administrator systemu</span><span class="sxs-lookup"><span data-stu-id="14dfe-122">**Required role to turn on the trace log and view errors:** System admin</span></span>

<span data-ttu-id="14dfe-123">Aby włączyć śledzenie, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="14dfe-123">To turn on the trace log, follow these steps.</span></span>

1. <span data-ttu-id="14dfe-124">Zaloguj się do aplikacji Finance and Operations, otwórz stronę **Ustawień**, a następnie w obszarze **System** wybierz opcję **Administracja**.</span><span class="sxs-lookup"><span data-stu-id="14dfe-124">Sign in to the Finance and Operations app, open the **Settings** page, and then, under **System**, select **Administration**.</span></span>
2. <span data-ttu-id="14dfe-125">Na stronie **Administracja** wybierz opcję **Konfiguracja systemu**.</span><span class="sxs-lookup"><span data-stu-id="14dfe-125">On the **Administration** page, select **System Settings**.</span></span>
3. <span data-ttu-id="14dfe-126">Na karcie **Dostosowywanie**, w polu **Wtyczki i niestandardowe śledzenie działania przepływu pracy** zaznacz opcję **Wszystkie**, aby włączyć dziennik śledzenia wtyczek.</span><span class="sxs-lookup"><span data-stu-id="14dfe-126">On the **Customization** tab, in the **Plug-in and custom workflow activity tracing** field, select **All** to enable the plug-in trace log.</span></span> <span data-ttu-id="14dfe-127">Jeśli chcesz rejestrować dzienniki śledzenia tylko w przypadku wystąpienia wyjątków, możesz zamiast tego wybrać **Wyjątek**.</span><span class="sxs-lookup"><span data-stu-id="14dfe-127">If you want to log trace logs only when exceptions occur, you can select **Exception** instead.</span></span>


<span data-ttu-id="14dfe-128">Aby zobaczyć dziennik śledzenia, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="14dfe-128">To view the trace log, follow these steps.</span></span>

1. <span data-ttu-id="14dfe-129">Zaloguj się do aplikacji Finance and Operations, otwórz stronę **Ustawień**, a następnie w obszarze **Dostosowywanie** wybierz opcję **Dziennik śledzenia wtyczek**.</span><span class="sxs-lookup"><span data-stu-id="14dfe-129">Sign in to the Finance and Operations app, open the **Settings** page, and then, under **Customization**, select **Plug-in Trace Log**.</span></span>
2. <span data-ttu-id="14dfe-130">Znajdź dzienniki śledzenia, w których w polu **Nazwa typu** jest ustawiona wartość **Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PreCommmitPlugin**.</span><span class="sxs-lookup"><span data-stu-id="14dfe-130">Find the trace logs where the **Type Name** field is set to **Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PreCommmitPlugin**.</span></span>
3. <span data-ttu-id="14dfe-131">Kliknij dwukrotnie towar, aby wyświetlić pełny dziennik, a następnie w skróconej karcie **Wykonania** przejrzyj tekst **Bloku wiadomości**.</span><span class="sxs-lookup"><span data-stu-id="14dfe-131">Double-click an item to view the full log, and then, on the **Execution** FastTab, review the **Message Block** text.</span></span>

## <a name="enable-debug-mode-to-troubleshoot-live-synchronization-issues-in-finance-and-operations-apps"></a><span data-ttu-id="14dfe-132">Włącz tryb debugowania w celu rozwiązywania problemów z synchronizacją na żywo w aplikacjach Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="14dfe-132">Enable debug mode to troubleshoot live synchronization issues in Finance and Operations apps</span></span>

<span data-ttu-id="14dfe-133">**Wymagana rola do wyświetlania błędów:** błędy podwójnego zapisywania administratora systemu Common Data Service mogą pojawić się w aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="14dfe-133">**Required role to view the errors:** System admin Dual-write errors that originate in Common Data Service can appear in the Finance and Operations app.</span></span> <span data-ttu-id="14dfe-134">W niektórych przypadkach pełny tekst komunikatu o błędzie jest niedostępny, ponieważ wiadomość jest zbyt długa lub zawiera informacje identyfikacyjne (dane osobowe).</span><span class="sxs-lookup"><span data-stu-id="14dfe-134">In some cases, the full text of the error message isn't available because the message is too long or contains personally identifying information (PII).</span></span> <span data-ttu-id="14dfe-135">Pełne rejestrowanie błędów można włączyć, wykonując następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="14dfe-135">You can turn on verbose logging for errors by following these steps.</span></span>

1. <span data-ttu-id="14dfe-136">Wszystkie konfiguracje projektu w aplikacjach Finance and Operations mają właściwość **IsDebugMode** w jednostce **DualWriteProjectConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="14dfe-136">All project configurations in Finance and Operations apps have an **IsDebugMode** property in the **DualWriteProjectConfiguration** entity.</span></span> <span data-ttu-id="14dfe-137">Otwórz jednostkę **DualWriteProjectConfiguration** przy użyciu dodatku programu Excel.</span><span class="sxs-lookup"><span data-stu-id="14dfe-137">Open the **DualWriteProjectConfiguration** entity by using the Excel add-in.</span></span>

    > [!TIP]
    > <span data-ttu-id="14dfe-138">Łatwym sposobem otwarcia jednostki jest włączenie trybu **Projektowania** w dodatku Excel, a następnie dodanie **DualWriteProjectConfigurationEntity** do arkusza.</span><span class="sxs-lookup"><span data-stu-id="14dfe-138">An easy way to open the entity is to turn on **Design** mode in the Excel add-in and then add **DualWriteProjectConfigurationEntity** to the worksheet.</span></span> <span data-ttu-id="14dfe-139">Aby uzyskać więcej informacji, zobacz: [Otwieranie danych jednostki w programie Excel i aktualizowanie ich przy użyciu dodatku programu Excel](../../office-integration/use-excel-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="14dfe-139">For more information, see [Open entity data in Excel and update it by using the Excel add-in](../../office-integration/use-excel-add-in.md).</span></span>

2. <span data-ttu-id="14dfe-140">Właściwość **IsDebugMode** należy skonfigurować jako wartość **Tak** dla projektu.</span><span class="sxs-lookup"><span data-stu-id="14dfe-140">Set the **IsDebugMode** property to **Yes** for the project.</span></span>
3. <span data-ttu-id="14dfe-141">Uruchom scenariusz, który generuje błędy.</span><span class="sxs-lookup"><span data-stu-id="14dfe-141">Run the scenario that is generating errors.</span></span>
4. <span data-ttu-id="14dfe-142">Pełne dzienniki są dostępne w tabeli DualWriteErrorLog.</span><span class="sxs-lookup"><span data-stu-id="14dfe-142">The verbose logs are available in the DualWriteErrorLog table.</span></span> <span data-ttu-id="14dfe-143">Aby wyszukać dane w przeglądarce, należy wybrać następujący adres URL (w razie potrzeby zastąpić **XXX**):</span><span class="sxs-lookup"><span data-stu-id="14dfe-143">To look up data in the table browser, use the following URL (replace **XXX** as appropriate):</span></span>

    `https://XXXaos.cloudax.dynamics.com/?mi=SysTableBrowser&tableName=>DualWriteErrorLog`

## <a name="check-synchronization-errors-on-the-virtual-machine-for-the-finance-and-operations-app"></a><span data-ttu-id="14dfe-144">Sprawdź błędy synchronizacji na maszynie wirtualnej dla aplikacji Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="14dfe-144">Check synchronization errors on the virtual machine for the Finance and Operations app</span></span>

<span data-ttu-id="14dfe-145">**Wymagana rola w celu wyświetlania problemów:** Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="14dfe-145">**Required role to view the errors:** System administrator</span></span>

1. <span data-ttu-id="14dfe-146">Zaloguj się do Microsoft Dynamics LifeCycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="14dfe-146">Sign in to Microsoft Dynamics Lifecycle Services (LCS).</span></span>
2. <span data-ttu-id="14dfe-147">Otwórz projekt LCS, który wybrano do wykonania podwójnego zapisu.</span><span class="sxs-lookup"><span data-stu-id="14dfe-147">Open the LCS project that you chose to do the dual-write testing for.</span></span>
3. <span data-ttu-id="14dfe-148">Wybierz kafelek **Środowiska hostowane w chmurze**.</span><span class="sxs-lookup"><span data-stu-id="14dfe-148">Select the **Cloud-hosted environments** tile.</span></span>
4. <span data-ttu-id="14dfe-149">Użyj pulpitu zdalnego i zaloguj się do maszyny wirtualnej (VM) aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="14dfe-149">Use Remote Desktop to sign in to the virtual machine (VM) for the Finance and Operations app.</span></span> <span data-ttu-id="14dfe-150">Należy skorzystać z konta lokalnego podanego w usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="14dfe-150">Use the local account that is shown in LCS.</span></span>
5. <span data-ttu-id="14dfe-151">Otwórz Podgląd zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="14dfe-151">Open Event viewer.</span></span>
6. <span data-ttu-id="14dfe-152">Wybierz do **Dzienniki aplikacji i usług \> Microsoft \> Dynamics \> AX-DualWriteSync \> Operacyjny**.</span><span class="sxs-lookup"><span data-stu-id="14dfe-152">Select **Applications and Services Logs \> Microsoft \> Dynamics \> AX-DualWriteSync \> Operational**.</span></span>
7. <span data-ttu-id="14dfe-153">Przejrzyj listę ostatnio używanych błędów.</span><span class="sxs-lookup"><span data-stu-id="14dfe-153">Review the list of recent errors.</span></span>

## <a name="unlink-and-link-another-common-data-service-environment-from-a-finance-and-operations-app"></a><span data-ttu-id="14dfe-154">Odłącz i Połącz inne środowisko Common Data Service z poziomu aplikacji Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="14dfe-154">Unlink and link another Common Data Service environment from a Finance and Operations app</span></span>

<span data-ttu-id="14dfe-155">**Wymagana rola do rozłączenia środowiska:** administrator systemu dla każdej aplikacji Finance and Operations lub Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="14dfe-155">**Required role to unlink the environment:** System administrator for either Finance and Operations app or Common Data Service.</span></span>

1. <span data-ttu-id="14dfe-156">Zaloguj się do aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="14dfe-156">Sign in to the Finance and Operations app.</span></span>
2. <span data-ttu-id="14dfe-157">Przejdź do **Obszary robocze \> Zarządzanie danymi** i wybierz opcję **Podwójny zapis**.</span><span class="sxs-lookup"><span data-stu-id="14dfe-157">Go to **Workspaces \> Data management**, and select the **Dual Write** tile.</span></span>
3. <span data-ttu-id="14dfe-158">Zaznacz wszystkie uruchomione mapowania i wybierz **Zatrzymaj**.</span><span class="sxs-lookup"><span data-stu-id="14dfe-158">Select all running mappings, and then select **Stop**.</span></span>
4. <span data-ttu-id="14dfe-159">Wybierz **Odłącz środowisko**.</span><span class="sxs-lookup"><span data-stu-id="14dfe-159">Select **Unlink environment**.</span></span>
5. <span data-ttu-id="14dfe-160">Wybierz **tak**, aby potwierdzić operację.</span><span class="sxs-lookup"><span data-stu-id="14dfe-160">Select **Yes** to confirm the operation.</span></span>

<span data-ttu-id="14dfe-161">Teraz można połączyć nowe środowisko.</span><span class="sxs-lookup"><span data-stu-id="14dfe-161">You can now link a new environment.</span></span>

## <a name="unable-to-view-the-sales-order-line-information-form"></a><span data-ttu-id="14dfe-162">Nie można wyświetlić formularza informacji o wierszu zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="14dfe-162">Unable to view the sales order line Information form</span></span> 

<span data-ttu-id="14dfe-163">Po utworzeniu zamówienia sprzedaży w systemie Dynamics 365 Sales, kliknięcie **+ Dodaj produkty** może spowodować przekierowanie do formularza wiersza zamówienia Dynamics 365 Project Operations.</span><span class="sxs-lookup"><span data-stu-id="14dfe-163">When you create a sales order in Dynamics 365 Sales, clicking on **+ Add products** might redirect you to the Dynamics 365 Project Operations order line form.</span></span> <span data-ttu-id="14dfe-164">Nie ma sposobu na podstawie tego formularza, aby wyświetlić formularz **Informacji** o wierszu zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="14dfe-164">There is no way from that form to view the sales order line **Information** form.</span></span> <span data-ttu-id="14dfe-165">Opcja dotycząca **Informacji** nie jest wyświetlana w polu listy rozwijanej pod **Nowy wiersz zamówienia**.</span><span class="sxs-lookup"><span data-stu-id="14dfe-165">The option for **Information** does not appear in the dropdown below **New Order Line**.</span></span> <span data-ttu-id="14dfe-166">Dzieje się tak, ponieważ Project Operations zostało zainstalowane w danym środowisku.</span><span class="sxs-lookup"><span data-stu-id="14dfe-166">This happens because Project Operations has been installed in your environment.</span></span>

<span data-ttu-id="14dfe-167">Aby ponownie włączyć opcję formularza **Informacji**, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="14dfe-167">To re-enable the **Information** form option, follow these steps:</span></span>
1. <span data-ttu-id="14dfe-168">Umożliwia przejście do jednostki **Wiersza zamówienia**.</span><span class="sxs-lookup"><span data-stu-id="14dfe-168">Navigate to the **Order Line** entity.</span></span>
2. <span data-ttu-id="14dfe-169">Znajdź formularz **Informacje** w węźle formularze.</span><span class="sxs-lookup"><span data-stu-id="14dfe-169">Find the **Information** form under the forms node.</span></span> 
3. <span data-ttu-id="14dfe-170">Zaznacz formularz **Informacje** i kliknij pozycję **Włącz role zabezpieczeń**.</span><span class="sxs-lookup"><span data-stu-id="14dfe-170">Select the **Information** form and click **Enable security roles**.</span></span> 
4. <span data-ttu-id="14dfe-171">Zmień ustawienie zabezpieczeń, aby było **Wyświetlane dla wszystkich**.</span><span class="sxs-lookup"><span data-stu-id="14dfe-171">Change the security setting to **Display to everyone**.</span></span>
