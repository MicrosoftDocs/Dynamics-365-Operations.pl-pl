---
title: Rozpocznij pracę z dodatkiem Faktury elektroniczne dla Meksyku
description: Ten temat zawiera informacje, które pomogą w rozpoczęciu pracy z dodatkiem Faktury elektroniczne dla Meksyku w rozwiązaniach Microsoft Dynamics 365 Finance i Dynamics 365 Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: d719c3ba68458130d415c50319fdcdeafcfc783e
ms.sourcegitcommit: 025561f6a21fe8705493daa290f3f6bfb9f1b962
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "3836016"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-mexico"></a><span data-ttu-id="4188c-103">Rozpocznij pracę z dodatkiem Faktury elektroniczne dla Meksyku</span><span class="sxs-lookup"><span data-stu-id="4188c-103">Get started with the Electronic invoicing add-on for Mexico</span></span>

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

> [!IMPORTANT]
> <span data-ttu-id="4188c-104">Dodatek Faktury elektroniczne dla Meksyku może nie obsługiwać obecnie wszystkich funkcji dostępnych w dokumencie Comprobante Fiscal Digital por Internet (CFDI) i w powiązanej integracji, która jest wbudowana w Microsoft Dynamics 365 Finance lub Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="4188c-104">The Electronic invoicing add-on for Mexico might not currently support all the functions that are available in the Comprobante Fiscal Digital por Internet (CFDI) document, and in the related integration that is built into Microsoft Dynamics 365 Finance or Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="4188c-105">Ten temat zawiera informacje, które pomogą w rozpoczęciu pracy z dodatkiem Faktury elektroniczne dla Meksyku.</span><span class="sxs-lookup"><span data-stu-id="4188c-105">This topic provides information that will help you get started with the Electronic invoicing add-on for Mexico.</span></span> <span data-ttu-id="4188c-106">Przeprowadza użytkownika przez kolejne etapy konfiguracji, które są zależne od kraju w usługach Regulatory Configuration Services (RCS) i Finance.</span><span class="sxs-lookup"><span data-stu-id="4188c-106">It guides you through the configuration steps that are country-dependent in Regulatory Configuration Services (RCS) and Finance.</span></span> <span data-ttu-id="4188c-107">Ponadto prowadzi użytkownika przez kroki, które należy wykonać w obszarze Finance, aby przesłać fakturę CFDI za pośrednictwem tej usługi, a także sposób przeglądu wyników przetwarzania i stanu faktur CFDI.</span><span class="sxs-lookup"><span data-stu-id="4188c-107">It also guides you through the steps that you must follow in Finance to submit CFDI invoices through the service, and it explains how to review the processing results and the status of CFDI invoices.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4188c-108">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="4188c-108">Prerequisites</span></span>

<span data-ttu-id="4188c-109">Przed wykonaniem kroków opisanych w tym temacie należy wykonać kroki opisane w temacie [Rozpoczynanie pracy z dodatkiem Faktury elektroniczne](e-invoicing-get-started.md).</span><span class="sxs-lookup"><span data-stu-id="4188c-109">Before you complete the steps in this topic, you must complete the steps in [Get started with the Electronic invoicing add-on](e-invoicing-get-started.md).</span></span>

## <a name="rcs-setup"></a><span data-ttu-id="4188c-110">Konfiguracja RCS</span><span class="sxs-lookup"><span data-stu-id="4188c-110">RCS setup</span></span>

<span data-ttu-id="4188c-111">Podczas instalacji RCS należy wykonać następujące zadania:</span><span class="sxs-lookup"><span data-stu-id="4188c-111">During the RCS setup, you will complete these tasks:</span></span>

1. <span data-ttu-id="4188c-112">Importuj funkcję fakturowania elektronicznego do przetwarzania faktur CFDI.</span><span class="sxs-lookup"><span data-stu-id="4188c-112">Import the e-Invoicing feature for processing CFDI invoices.</span></span>
2. <span data-ttu-id="4188c-113">Przejrzyj konfiguracje formatów wymagane do generowania, przesyłania i odbierania odpowiedzi na temat faktur CFDI oraz przesyłania i odbierania odpowiedzi na anulowanie.</span><span class="sxs-lookup"><span data-stu-id="4188c-113">Review the format configurations that are required to generate, submit, and receive responses about CFDI invoices, and to submit and receive responses about cancellation.</span></span>
3. <span data-ttu-id="4188c-114">Skonfiguruj zdarzenia obsługujące scenariusze przesyłania faktur CFDI.</span><span class="sxs-lookup"><span data-stu-id="4188c-114">Configure the events that support the CFDI invoice submission scenarios.</span></span>
4. <span data-ttu-id="4188c-115">Publikuj funkcję fakturowania elektronicznego do faktur CFDI.</span><span class="sxs-lookup"><span data-stu-id="4188c-115">Publish the e-Invoicing feature for CFDI invoices.</span></span>

> [!NOTE]
> <span data-ttu-id="4188c-116">„Funkcja fakturowania elektronicznego” to ogólna nazwa zasobu, który jest skonfigurowany i opublikowany w celu wykorzystania serwera dodatku Faktury elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="4188c-116">"The e-Invoicing feature" is the generic name for the resource that is configured and published to consume the Electronic invoicing add-on server.</span></span> <span data-ttu-id="4188c-117">W takim przypadku faktura CFDI (MX) jest funkcją fakturowania elektronicznego, którą należy skonfigurować.</span><span class="sxs-lookup"><span data-stu-id="4188c-117">In this case, CFDI invoices (MX) are the e-Invoicing feature that you will set up.</span></span>

## <a name="import-the-e-invoicing-feature"></a><span data-ttu-id="4188c-118">Importuj funkcję fakturowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="4188c-118">Import the e-Invoicing feature</span></span>

1. <span data-ttu-id="4188c-119">Zaloguj się do swojego konta RCS.</span><span class="sxs-lookup"><span data-stu-id="4188c-119">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="4188c-120">Otwórz nowy obszar roboczy **Funkcje globalizacji**, a następnie w obszarze **Funkcje** wybierz kafelek **Fakturowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="4188c-120">In the **Globalization features** workspace, in the **Features** section, select the **e-Invoicing** tile.</span></span>
3. <span data-ttu-id="4188c-121">Na stronie **Funkcje fakturowania elektronicznego** wybierz opcję **Importuj** w celu zaimportowania funkcji **faktury CFDI (MX)** z repozytorium globalnego.</span><span class="sxs-lookup"><span data-stu-id="4188c-121">On the **e-Invoicing Features** page, select **Import** to import the **CFDI invoices (MX)** feature from the Global repository.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4188c-122">Jeśli na liście nie ma funkcji, wybierz opcję **Synchronizuj**, a następnie powtórz krok 3.</span><span class="sxs-lookup"><span data-stu-id="4188c-122">If you don't see the feature in the list, select **Synchronize**, and then repeat step 3.</span></span>

![Importowanie funkcji fakturowania CFDI (MX)](media/e-Invoicing-services-get-started-MEX-Select-Import-CFDI-feature.png)

<span data-ttu-id="4188c-124">Po zaimportowaniu funkcji **faktury CFDI (MX)** z repozytorium globalnego importowane są również wszystkie ustawienia funkcji, w tym konfiguracje i akcje.</span><span class="sxs-lookup"><span data-stu-id="4188c-124">When you import the **CFDI invoices (MX)** feature from the Global repository, all the feature settings, including configurations and actions, are also imported.</span></span>

### <a name="create-a-new-version-of-the-cfdi-invoices-mx-feature"></a><span data-ttu-id="4188c-125">Utwórz nową wersję funkcji faktur CFDI (MX)</span><span class="sxs-lookup"><span data-stu-id="4188c-125">Create a new version of the CFDI invoices (MX) feature</span></span>

<span data-ttu-id="4188c-126">Nową wersję można utworzyć, jeśli na przykład adresy URL muszą zostać zaktualizowane.</span><span class="sxs-lookup"><span data-stu-id="4188c-126">You can create a new version if, for example, URLs must be updated.</span></span> <span data-ttu-id="4188c-127">Aby uzyskać więcej informacji, zajrzyj do [faktury elektroniczne CFDI](tasks/mx-00010-e-invoicing-cfdi.md).</span><span class="sxs-lookup"><span data-stu-id="4188c-127">For more information, see [E-invoicing CFDI](tasks/mx-00010-e-invoicing-cfdi.md).</span></span>

- <span data-ttu-id="4188c-128">Na stronie **Funkcje fakturowania elektronicznego** na karcie **Wersje** wybierz **Nowa**.</span><span class="sxs-lookup"><span data-stu-id="4188c-128">On the **e-Invoicing Features** page, on the **Versions** tab, select **New**.</span></span>

![Dodawanie nowej wersji funkcji fakturowania elektronicznego](media/e-Invoicing-services-get-started-MEX-Select-New-e-Invoicing-feature.png)

### <a name="update-the-configuration-version"></a><span data-ttu-id="4188c-130">Aktualizacja wersji konfiguracji</span><span class="sxs-lookup"><span data-stu-id="4188c-130">Update the configuration version</span></span>

1. <span data-ttu-id="4188c-131">Na stronie **Funkcje fakturowania elektronicznego** na karcie **Konfiguracje** wybierz opcję **Dodaj** lub **Usuń**, aby zarządzać konfiguracjami wersji (konfiguracjami formatu pliku ER).</span><span class="sxs-lookup"><span data-stu-id="4188c-131">On the **e-Invoicing Features** page, on the **Configurations** tab, select **Add** or **Delete** to manage the configuration versions (ER file format configurations).</span></span>

    ![Zarządzanie konfiguracjami funkcji fakturowania elektronicznego](media/e-Invoicing-services-get-started-MEX-Manage-e-Invoicing-feature-Configurations.png)

    <span data-ttu-id="4188c-133">Podczas tworzenia nowej wersji wszystkie konfiguracje są dziedziczone z ostatniej opublikowanej wersji.</span><span class="sxs-lookup"><span data-stu-id="4188c-133">When you create a new version, all configurations are inherited from the last published version.</span></span> <span data-ttu-id="4188c-134">Aby można było przetwarzać faktury CFDI, wymagane są następujące konfiguracje:</span><span class="sxs-lookup"><span data-stu-id="4188c-134">To process CFDI invoices, the following configurations are required:</span></span>

    - <span data-ttu-id="4188c-135">Faktura CFDI (BusinessDocumentService)</span><span class="sxs-lookup"><span data-stu-id="4188c-135">CFDI invoice (BusinessDocumentService)</span></span>
    - <span data-ttu-id="4188c-136">Import komunikatu odpowiedzi CFDI</span><span class="sxs-lookup"><span data-stu-id="4188c-136">CFDI response message import</span></span>
    - <span data-ttu-id="4188c-137">Import dziennika błędów CFDI</span><span class="sxs-lookup"><span data-stu-id="4188c-137">CFDI error log import</span></span>
    - <span data-ttu-id="4188c-138">Żądanie anulowania CFDI (MX) (BusinessDocumentService)</span><span class="sxs-lookup"><span data-stu-id="4188c-138">CFDI cancelation request (MX) (BusinessDocumentService)</span></span>
    - <span data-ttu-id="4188c-139">Faktura CFDI (BusinessDocumentService)</span><span class="sxs-lookup"><span data-stu-id="4188c-139">CFDI invoice (BusinessDocumentService)</span></span>

2. <span data-ttu-id="4188c-140">Z listy wybierz wersję konfiguracji, a następnie wybierz opcję **Edytuj** lub **Wyświetl**, aby otworzyć stronę **Projektant formatów**, na której możesz edytować lub wyświetlić konfigurację.</span><span class="sxs-lookup"><span data-stu-id="4188c-140">In the list, select a configuration version, and then select **Edit** or **View** to open the **Format designer** page, where you can edit or view the configuration.</span></span>

    ![Otwieranie strony Projektanta formatów](media/e-Invoicing-services-get-started-MEX-Configuration-ER-format-designer.png)

3. <span data-ttu-id="4188c-142">Strona **Projektant formatów** umożliwia edytowanie i wyświetlanie konfiguracji plików formatu ER.</span><span class="sxs-lookup"><span data-stu-id="4188c-142">Use the **Format designer** page to edit and view the ER format file configurations.</span></span> <span data-ttu-id="4188c-143">Aby uzyskać więcej informacji, zobacz [Twórz konfiguracje dokumentów elektronicznych](../../dev-itpro/analytics/electronic-reporting-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="4188c-143">For more information, see [Create electronic document configurations](../../dev-itpro/analytics/electronic-reporting-configuration.md).</span></span>

    ![Strona projektanta formatu](media/e-Invoicing-services-get-started-MEX-ER-format-designer.png)

## <a name="manage-the-e-invoicing-feature-setups"></a><span data-ttu-id="4188c-145">Zarządzaj konfiguracjami funkcji fakturowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="4188c-145">Manage the e-Invoicing feature setups</span></span>

- <span data-ttu-id="4188c-146">Na stronie **Funkcje fakturowania elektronicznego** na karcie **Ustawienia** wybierz opcję **Dodaj**, **Usuń** lub **Edytuj**, aby zarządzać konfiguracjami funkcji fakturowania w systemie.</span><span class="sxs-lookup"><span data-stu-id="4188c-146">On the **e-Invoicing Features** page, on the **Setups** tab, select **Add**, **Delete**, or **Edit** to manage the e-Invoicing feature setups.</span></span>

![Zarządzanie konfiguracjami funkcji fakturowania elektronicznego](media/e-Invoicing-services-get-started-MEX-Manage-e-Invoicing-feature-Setup.png)

<span data-ttu-id="4188c-148">Aby przesłać faktury CFDI do autoryzacji (wygenerować plik XML, przesłać plik XML i przetworzyć odpowiedź), wymagane jest ustawienie funkcji **Faktura sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="4188c-148">To submit CFDI invoices for authorization (generate the XML file, submit the XML file, and process the response), the **Sales invoice** feature setup is required.</span></span>

<span data-ttu-id="4188c-149">Aby przesłać anulowanie faktury CFDI, wymagane są konfiguracje funkcji **Anulowania** i **Anuluj**.</span><span class="sxs-lookup"><span data-stu-id="4188c-149">To submit CFDI invoice cancellation, the **Cancellation** and **Cancel** feature setups are required.</span></span>

### <a name="configure-the-sales-invoice-feature-setup"></a><span data-ttu-id="4188c-150">Konfigurowanie ustawień funkcji faktur sprzedaży</span><span class="sxs-lookup"><span data-stu-id="4188c-150">Configure the Sales invoice feature setup</span></span>

1. <span data-ttu-id="4188c-151">Na stronie **Funkcje fakturowania elektronicznego** na karcie **Ustawienia** w kolumnie **Ustawienia funkcji** wybierz opcję **Faktura sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="4188c-151">On the **e-Invoicing Features** page, on the **Setups** tab, in the **Feature setup** column, select **Sales invoice**.</span></span>
2. <span data-ttu-id="4188c-152">Wybierz opcję **Edytuj**, aby skonfigurować akcje, reguły stosowalności i zmienne.</span><span class="sxs-lookup"><span data-stu-id="4188c-152">Select **Edit** to configure the actions, applicability rules, and variables.</span></span>

    ![Edytowanie konfiguracji funkcji fakturowania elektronicznego](media/e-Invoicing-services-get-started-MEX-Edit-e-Invoicing-feature-setup.png)

3. <span data-ttu-id="4188c-154">Na stronie **Ustawienia wersji funkcji** wybierz kartę **Akcje**, aby zarządzać listą akcji.</span><span class="sxs-lookup"><span data-stu-id="4188c-154">On the **Feature version setup** page, select the **Actions** tab to manage the list of actions.</span></span> <span data-ttu-id="4188c-155">Akcje definiują listę operacji, które muszą być uruchomione w kolejności sekwencyjnej, aby wykonać pełne wykonanie zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="4188c-155">Actions define a list of operations that must be run in sequential order to accomplish full execution of the event.</span></span>

    ![Karta Akcje](media/e-Invoicing-services-get-started-MEX-Select-Actions.png)

    | <span data-ttu-id="4188c-157">Identyfikator akcji</span><span class="sxs-lookup"><span data-stu-id="4188c-157">Action ID</span></span> | <span data-ttu-id="4188c-158">Akcja</span><span class="sxs-lookup"><span data-stu-id="4188c-158">Action</span></span>                   | <span data-ttu-id="4188c-159">Nazwa akcji</span><span class="sxs-lookup"><span data-stu-id="4188c-159">Action name</span></span>                                  | <span data-ttu-id="4188c-160">Opis akcji</span><span class="sxs-lookup"><span data-stu-id="4188c-160">Action description</span></span>                                          |
    |-----------|--------------------------|----------------------------------------------|-------------------------------------------------------------|
    | <span data-ttu-id="4188c-161">1</span><span class="sxs-lookup"><span data-stu-id="4188c-161">1</span></span>         | <span data-ttu-id="4188c-162">Przekształcanie dokumentu</span><span class="sxs-lookup"><span data-stu-id="4188c-162">Transform document</span></span>       | <span data-ttu-id="4188c-163">Wygeneruj fakturę elektroniczną CFDI bez znaku cyfrowego</span><span class="sxs-lookup"><span data-stu-id="4188c-163">Generate CFDI E-Invoice without digital sign</span></span> | <span data-ttu-id="4188c-164">Generuj fakturę elektroniczą CFDI.</span><span class="sxs-lookup"><span data-stu-id="4188c-164">Generate the CFDI e-invoice.</span></span>                                |
    | <span data-ttu-id="4188c-165">2</span><span class="sxs-lookup"><span data-stu-id="4188c-165">2</span></span>         | <span data-ttu-id="4188c-166">Podpisz dokument</span><span class="sxs-lookup"><span data-stu-id="4188c-166">Sign document</span></span>            | <span data-ttu-id="4188c-167">Znak cyfrowy</span><span class="sxs-lookup"><span data-stu-id="4188c-167">Digital sign</span></span>                                 | <span data-ttu-id="4188c-168">Podpisz cyfrowo fakturę elektroniczną do przesłania.</span><span class="sxs-lookup"><span data-stu-id="4188c-168">Digitally sign the e-invoice for submission.</span></span>                |
    | <span data-ttu-id="4188c-169">3</span><span class="sxs-lookup"><span data-stu-id="4188c-169">3</span></span>         | <span data-ttu-id="4188c-170">Wywołaj usługę meksykańskiego certyfikatu PAC</span><span class="sxs-lookup"><span data-stu-id="4188c-170">Call Mexican PAC service</span></span> | <span data-ttu-id="4188c-171">Prześlij fakturę elektroniczną CFDI</span><span class="sxs-lookup"><span data-stu-id="4188c-171">Submit CFDI E-Invoice</span></span>                        | <span data-ttu-id="4188c-172">Klient Windows Communication Foundation (WCF) przesyła fakturę elektroniczną CFDI.</span><span class="sxs-lookup"><span data-stu-id="4188c-172">The Windows Communication Foundation (WCF) client submits the CFDI e-invoice.</span></span> |
    | <span data-ttu-id="4188c-173">4</span><span class="sxs-lookup"><span data-stu-id="4188c-173">4</span></span>         | <span data-ttu-id="4188c-174">Przetwarzanie odpowiedzi</span><span class="sxs-lookup"><span data-stu-id="4188c-174">Process response</span></span>         | <span data-ttu-id="4188c-175">Analiza odpowiedzi usługi sieci Web</span><span class="sxs-lookup"><span data-stu-id="4188c-175">Analyze web service response</span></span>                 | <span data-ttu-id="4188c-176">Przeanalizuj odpowiedź usługi sieci Web i zwróć dziennik błędów.</span><span class="sxs-lookup"><span data-stu-id="4188c-176">Analyze the web service response, and return the error log.</span></span> |

### <a name="set-up-the-url-for-mexican-pac-web-services"></a><span data-ttu-id="4188c-177">Ustaw adres URL dla meksykańskich usług PAC sieci Web</span><span class="sxs-lookup"><span data-stu-id="4188c-177">Set up the URL for Mexican PAC web services</span></span> 

1. <span data-ttu-id="4188c-178">Na stronie **Ustawienia wersji funkcji** na karcie **Akcje** na skróconej karcie **Akcje** wybierz opcję **Wywołaj usługę meksykańskiego certyfikatu PAC**.</span><span class="sxs-lookup"><span data-stu-id="4188c-178">On the **Feature version setup** page, on the **Actions** tab, on the **Actions** FastTab, select **Call Mexican PAC service**.</span></span>
2. <span data-ttu-id="4188c-179">Na skróconej karcie **Parametry** w polu **Parametr adresu URL**, wprowadź adres URL usługi sieciowej do przesyłania faktur CFDI.</span><span class="sxs-lookup"><span data-stu-id="4188c-179">On the **Parameters** FastTab, in the **URL address** field, enter the URL of the web service for CFDI invoice submission.</span></span>

> [!NOTE]
> <span data-ttu-id="4188c-180">Wykonaj te same kroki w celu zaktualizowania adresu URL dla akcji **Wywołaj usługę meksykańskiego certyfikatu PAC** dla ustawień funkcji **Anuluj** i **Żądanie anulowania**.</span><span class="sxs-lookup"><span data-stu-id="4188c-180">Use the same steps to update the URL for **Call Mexican PAC service** action for the **Cancel** and **Cancelation request** feature setups.</span></span>

## <a name="assign-the-draft-version-to-an-e-invoicing-environment"></a><span data-ttu-id="4188c-181">Przypisz wersję roboczą do środowiska fakturowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="4188c-181">Assign the Draft version to an e-Invoicing environment</span></span>

1. <span data-ttu-id="4188c-182">Na stronie **Funkcje fakturowania elektronicznego** na karcie **Środowisko** wybierz **Włącz**.</span><span class="sxs-lookup"><span data-stu-id="4188c-182">On the **e-Invoicing Features** page, on the **Environments** tab, select **Enable**.</span></span>
2. <span data-ttu-id="4188c-183">W polu **Środowiska** wybierz środowisko.</span><span class="sxs-lookup"><span data-stu-id="4188c-183">In the **Environment** field, select the environment.</span></span>
3. <span data-ttu-id="4188c-184">W polu **Obowiązuje od** wybierz datę, kiedy nowe środowisko powinno zostać wprowadzone.</span><span class="sxs-lookup"><span data-stu-id="4188c-184">In the **Effective from** field, select the date when the environment should become effective.</span></span>
3. <span data-ttu-id="4188c-185">Wybierz **Włącz**.</span><span class="sxs-lookup"><span data-stu-id="4188c-185">Select **Enable**.</span></span>

![Włączanie środowiska fakturowania elektronicznego](media/e-Invoicing-services-get-started-MEX-Enable-e-Invoicing-Environment.png)

## <a name="change-the-version-status-to-completed"></a><span data-ttu-id="4188c-187">Zmień stan wersji na Ukończone</span><span class="sxs-lookup"><span data-stu-id="4188c-187">Change the version status to Completed</span></span>

1. <span data-ttu-id="4188c-188">Na stronie **Funkcje fakturowania elektronicznego** na karcie **Wersje** wybierz wersję funkcji fakturowania elektronicznego, która ma stan **Wersja robocza**.</span><span class="sxs-lookup"><span data-stu-id="4188c-188">On the **e-Invoicing Features** page, on the **Versions** tab, select the version of the e-Invoicing feature that has a status of **Draft**.</span></span>
2. <span data-ttu-id="4188c-189">Wybierz **Zmień status \> Zakończone**.</span><span class="sxs-lookup"><span data-stu-id="4188c-189">Select **Change status \> Complete**.</span></span>

## <a name="change-the-version-status-to-published"></a><span data-ttu-id="4188c-190">Zmień stan wersji na Opublikowane</span><span class="sxs-lookup"><span data-stu-id="4188c-190">Change the version status to Published</span></span>

- <span data-ttu-id="4188c-191">Na stronie **Funkcje fakturowania elektronicznego** na karcie **Wersje** wybierz pozycję **Zmień stan \> Opublikuj**.</span><span class="sxs-lookup"><span data-stu-id="4188c-191">On the **e-Invoicing Features** page, on the **Versions** tab, select **Change status \> Publish**.</span></span>

## <a name="publish-the-e-invoicing-feature"></a><span data-ttu-id="4188c-192">Opublikuj funkcję fakturowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="4188c-192">Publish the e-Invoicing feature</span></span>

1. <span data-ttu-id="4188c-193">Na stronie **Funkcje fakturowania elektronicznego** wybierz kartę **Wersje**, aby zarządzać stanem funkcji **faktury CFDI (MX)**.</span><span class="sxs-lookup"><span data-stu-id="4188c-193">On the **e-Invoicing Features** page, select the **Versions** tab to manage the status of the **CFDI invoices (MX)** feature.</span></span>
2. <span data-ttu-id="4188c-194">Abyzmienić stan funkcji, wybierz opcję **Zmień stan**.</span><span class="sxs-lookup"><span data-stu-id="4188c-194">Select **Change status** to change the status of the feature.</span></span>

![Zmiana stanu funkcji fakturowania elektronicznego](media/e-Invoicing-services-get-started-MEX-Change-status-of-e-Invoicing-feature.png)

## <a name="set-up-electronic-invoicing-add-on-integration-in-finance"></a><span data-ttu-id="4188c-196">Skonfiguruj integrację dodatku Faktury elektroniczne w Finance</span><span class="sxs-lookup"><span data-stu-id="4188c-196">Set up Electronic invoicing add-on integration in Finance</span></span>

<span data-ttu-id="4188c-197">Aby skonfigurować dodatek Faktury elektroniczne w Finance, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="4188c-197">To set up the Electronic invoicing add-on in Finance, you will complete these tasks:</span></span>

1. <span data-ttu-id="4188c-198">Umożliwia zaimportowanie modelu danych ER, mapowania modelu danych ER i formatów wymaganych dla faktur CFDI.</span><span class="sxs-lookup"><span data-stu-id="4188c-198">Import the ER data model, the ER data model mapping, and the formats that are required for CFDI invoices.</span></span>
2. <span data-ttu-id="4188c-199">Skonfiguruj typy odpowiedzi w celu zaktualizowania faktur CFDI.</span><span class="sxs-lookup"><span data-stu-id="4188c-199">Configure response types for updating the CFDI invoices.</span></span> <span data-ttu-id="4188c-200">Te typy odpowiedzi są używane w odpowiedziach pochodzących od serwera autoryzowanego dostawcy certyfikatów (PAC).</span><span class="sxs-lookup"><span data-stu-id="4188c-200">These response types are used for the response from the authorized certification provider (PAC) server.</span></span>

### <a name="import-the-er-data-model-er-data-model-mapping-and-context-configurations-for-cfdi-invoices"></a><span data-ttu-id="4188c-201">Importuj model danych modelu ER, mapowanie modelu danych ER i konfiguracje kontekstowe dla faktur CFDI</span><span class="sxs-lookup"><span data-stu-id="4188c-201">Import the ER data model, ER data model mapping, and context configurations for CFDI invoices</span></span>

1. <span data-ttu-id="4188c-202">Zaloguj się do Finance.</span><span class="sxs-lookup"><span data-stu-id="4188c-202">Sign in to Finance.</span></span>
2. <span data-ttu-id="4188c-203">W obszarze roboczym **Raportowanie elektroniczne** w sekcji **Dostawcy konfiguracji** wybierz kafelek **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="4188c-203">In the **Electronic reporting** workspace, in the **Configuration providers** section, select the **Microsoft** title.</span></span> <span data-ttu-id="4188c-204">Upewnij się, że ten dostawca konfiguracji jest skonfigurowany jako **Aktywny**.</span><span class="sxs-lookup"><span data-stu-id="4188c-204">Make sure that this configuration provider is set to **Active**.</span></span> <span data-ttu-id="4188c-205">Aby uzyskać informacje o tym, jak ustawić dostawcę jako **Aktywny**, zobacz [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11).</span><span class="sxs-lookup"><span data-stu-id="4188c-205">For information about how to set a provider to **Active**, see [Create configuration providers and mark them as active](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11).</span></span>
3. <span data-ttu-id="4188c-206">Wybierz **Repozytoria**.</span><span class="sxs-lookup"><span data-stu-id="4188c-206">Select **Repositories**.</span></span>
4. <span data-ttu-id="4188c-207">Wybierz pozycję **Zasób globalny \> Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="4188c-207">Select **Global resource \> Open**.</span></span>
5. <span data-ttu-id="4188c-208">Importowanie **Model faktury**, **Mapowanie modelu faktury**, **Format faktury CFDI (MX)**, **Format żądania anulowania faktury CFDI (MX)** oraz **Format anulowania faktury CFDI (MX)**.</span><span class="sxs-lookup"><span data-stu-id="4188c-208">Import **Invoice model**, **Invoice model mapping**, **CFDI invoice format (MX)**, **CFDI invoice cancelation request format (MX)**, and **CFDI invoice cancel format (MX)**.</span></span>

### <a name="turn-on-the-feature-for-processing-cfdi-invoices"></a><span data-ttu-id="4188c-209">Włącz funkcję przetwarzania faktur CFDI</span><span class="sxs-lookup"><span data-stu-id="4188c-209">Turn on the feature for processing CFDI invoices</span></span>

1. <span data-ttu-id="4188c-210">Przejdź do **Administrowanie organizacją \> Konfiguracja \> Parametry dokumentu elektronicznego**.</span><span class="sxs-lookup"><span data-stu-id="4188c-210">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="4188c-211">Na karcie **Funkcje** zaznacz pole wyboru **Włącz** dla wierszy odnośników funkcji **MX-00010** i **MX-00016**.</span><span class="sxs-lookup"><span data-stu-id="4188c-211">On the **Features** tab, select the **Enable** check box in the rows for feature references **MX-00010** and **MX-00016**.</span></span>

![Włączanie funkcji przetwarzania faktur CFDI](media/e-Invoicing-services-get-started-MEX-Enable-CFDI-feature.png)

### <a name="import-er-configurations-and-set-up-the-response-types-for-updating-cfdi-invoices"></a><span data-ttu-id="4188c-213">Importowanie konfiguracji modułu ER i konfigurowanie typów odpowiedzi dla aktualizacji faktur CFDI</span><span class="sxs-lookup"><span data-stu-id="4188c-213">Import ER configurations and set up the response types for updating CFDI invoices</span></span>

#### <a name="import-er-configurations"></a><span data-ttu-id="4188c-214">Importowanie konfiguracji ER</span><span class="sxs-lookup"><span data-stu-id="4188c-214">Import ER configurations</span></span>

1. <span data-ttu-id="4188c-215">W obszarze roboczym **Raportowanie elektroniczne** w sekcji **Dostawcy konfiguracji** wybierz kafelek **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="4188c-215">In the **Electronic reporting** workspace, in the **Configuration providers** section, select the **Microsoft** title.</span></span>
3. <span data-ttu-id="4188c-216">Wybierz **Repozytoria**.</span><span class="sxs-lookup"><span data-stu-id="4188c-216">Select **Repositories**.</span></span>
4. <span data-ttu-id="4188c-217">Wybierz pozycję **Zasób globalny \> Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="4188c-217">Select **Global resource \> Open**.</span></span>
5. <span data-ttu-id="4188c-218">Importowanie **Modelu wiadomości odpowiedzi**, **Dziennik błędów importowania CFDI (MX)**, **Dziennik błędów importowania (MX)** oraz **Import wiadomości odpowiedzi CFDI (MX)**.</span><span class="sxs-lookup"><span data-stu-id="4188c-218">Import **Response message model**, **CFDI error log import (MX)**, **CFDI error log import (MX)**, and **CFDI response message import (MX)**.</span></span>

#### <a name="set-up-the-response-types"></a><span data-ttu-id="4188c-219">Konfigurowanie typów odpowiedzi</span><span class="sxs-lookup"><span data-stu-id="4188c-219">Set up the response types</span></span>

1. <span data-ttu-id="4188c-220">Przejdź do **Administrowanie organizacją \> Konfiguracja \> Parametry dokumentu elektronicznego**.</span><span class="sxs-lookup"><span data-stu-id="4188c-220">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="4188c-221">Na karcie **Dokument elektroniczny** wybierz przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="4188c-221">On the **Electronic document** tab, select **Add**.</span></span>
3. <span data-ttu-id="4188c-222">Wprowadź Arkusz faktur odbiorcy, a następnie w polu **Nazwa tabeli** wybierz fakturę projektu.</span><span class="sxs-lookup"><span data-stu-id="4188c-222">Enter the customer invoice journal, and then, in the **Table name** field, select the project invoice.</span></span>
4. <span data-ttu-id="4188c-223">Dla każdej tabeli zdefiniuj powiązany kontekst dokumentu:</span><span class="sxs-lookup"><span data-stu-id="4188c-223">For each table, define a related document context:</span></span>

    - <span data-ttu-id="4188c-224">W przypadku **Arkusza faktur dla odbiorcy** wpisz **Kontekst faktury dla odbiorcy**.</span><span class="sxs-lookup"><span data-stu-id="4188c-224">For **Customer invoice journal**, enter **Customer invoice context**.</span></span>
    - <span data-ttu-id="4188c-225">W przypadku **Faktury projektu** wpisz **Kontekst faktury projektu**.</span><span class="sxs-lookup"><span data-stu-id="4188c-225">For **Project invoice**, enter **Project invoice context**.</span></span>

4. <span data-ttu-id="4188c-226">Wybierz **Typy odpowiedzi**, aby skonfigurować typy odpowiedzi, które mogą być zwracane z dodatku Faktury elektroniczne i uwzględnione w arkuszu faktur dla odbiorcy lub fakturze projektu.</span><span class="sxs-lookup"><span data-stu-id="4188c-226">Select **Response types** to configure the response types that can be returned from the Electronic invoicing add-on and included in a customer invoice journal or project invoice.</span></span>
5. <span data-ttu-id="4188c-227">Wybierz **Nowe** i następnie w polu **Typ odpowiedzi** wybierz **Odpowiedź**.</span><span class="sxs-lookup"><span data-stu-id="4188c-227">Select **New**, and then, in the **Response type** field, select **Response**.</span></span>
6. <span data-ttu-id="4188c-228">W polu **Stan przesyłania** wybierz **W trakcie**.</span><span class="sxs-lookup"><span data-stu-id="4188c-228">In the **Submission status** field, select **Pending**.</span></span>
7. <span data-ttu-id="4188c-229">W polu **Mapowanie modelu** wybierz opcję **Format importu wiadomości odpowiedzi - odwzorowanie modelu z wiadomości odpowiedzi**.</span><span class="sxs-lookup"><span data-stu-id="4188c-229">In the **Model mapping** field, select **Response message import format – Model mapping from response message**.</span></span>
8. <span data-ttu-id="4188c-230">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="4188c-230">Select **Save**.</span></span>
9. <span data-ttu-id="4188c-231">Wybierz **Nowe** i następnie w polu **Typ odpowiedzi** wybierz **ResponseData**.</span><span class="sxs-lookup"><span data-stu-id="4188c-231">Select **New**, and then, in the **Response type** field, select **ResponseData**.</span></span>
10. <span data-ttu-id="4188c-232">W polu **Stan przesyłania** wybierz **W trakcie**.</span><span class="sxs-lookup"><span data-stu-id="4188c-232">In the **Submission status** field, select **Pending**.</span></span>
11. <span data-ttu-id="4188c-233">W polu **Mapowanie modelu** wybierz opcję **Format importu danych odpowiedzi CFDI (szczegóły) - Import danych odpowiedzi**.</span><span class="sxs-lookup"><span data-stu-id="4188c-233">In the **Model mapping** field, select **CFDI response data import format (details) – Response data import**.</span></span>
12. <span data-ttu-id="4188c-234">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="4188c-234">Select **Save**.</span></span>

## <a name="process-electronic-invoices-in-finance"></a><span data-ttu-id="4188c-235">Przetwarzanie faktur elektronicznych w Finance</span><span class="sxs-lookup"><span data-stu-id="4188c-235">Process electronic invoices in Finance</span></span> 

<span data-ttu-id="4188c-236">Podczas przetwarzania faktur CFDI w Finance za pomocą dodatku Faktury elektroniczne możesz wykonywać następujące zadania:</span><span class="sxs-lookup"><span data-stu-id="4188c-236">During the processing of CFDI invoices in Finance through the Electronic invoicing add-on, you can perform the following tasks:</span></span>

- <span data-ttu-id="4188c-237">Prześlij faktury elektroniczne CFDI.</span><span class="sxs-lookup"><span data-stu-id="4188c-237">Submit CFDI invoices.</span></span>
- <span data-ttu-id="4188c-238">Wyświetl dzienniki wykonywania przesyłania.</span><span class="sxs-lookup"><span data-stu-id="4188c-238">View the submission execution logs.</span></span>
- <span data-ttu-id="4188c-239">Prześlij anulowanie faktury CFDI.</span><span class="sxs-lookup"><span data-stu-id="4188c-239">Submit the cancellation of a CFDI invoice.</span></span>

### <a name="submit-cfdi-invoices"></a><span data-ttu-id="4188c-240">Prześlij faktury elektroniczne CFDI</span><span class="sxs-lookup"><span data-stu-id="4188c-240">Submit CFDI invoices</span></span>

<span data-ttu-id="4188c-241">Po włączeniu funkcji **Konfigurowalna integracja z dodatkiem Faktur elektronicznych** nie można już używać procesu **Eksport/Import faktury elektronicznej** (**Rozrachunki z odbiorcami \> Faktury \> Faktury elektroniczne**) do przesyłania faktrur CFDI.</span><span class="sxs-lookup"><span data-stu-id="4188c-241">After you turn on the **Configurable Electronic invoicing add-on integration** feature, the **Export/Import electronic invoice** process (**Accounts receivable \> Invoices \> E-invoices**) for submitting CFDI invoices can no longer be used.</span></span> <span data-ttu-id="4188c-242">Zastępuje go nowym procesem o nazwie **Prześlij dokumenty elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="4188c-242">It's replaced by a new process that is named **Submit electronic documents**.</span></span>

> [!NOTE]
> <span data-ttu-id="4188c-243">Przed użyciem nowego procesu **Przesyłania dokumentów elektronicznych** należy sprawdzić, czy zostało zakończone wymagane ustawienie meksykańskiego fakturowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="4188c-243">Before you use the new **Submit electronic documents** process, verify that the setup that is required for Mexican e-invoices was completed.</span></span> <span data-ttu-id="4188c-244">Aby uzyskać więcej informacji, zobacz [CFDI wersja układu 3.3](https://docs.microsoft.com/dynamics365/finance/localizations/latam-mex-cfdi-3-3).</span><span class="sxs-lookup"><span data-stu-id="4188c-244">For more information, see [CFDI layout version 3.3](https://docs.microsoft.com/dynamics365/finance/localizations/latam-mex-cfdi-3-3).</span></span>

1. <span data-ttu-id="4188c-245">Przejdź do **Administrowanie organizacją \> Okresowe \> Dokumenty elektroniczne \> Prześlij dokumenty elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="4188c-245">Go to **Organization administration \> Periodic \> Electronic documents \> Submit electronic documents**.</span></span>
2. <span data-ttu-id="4188c-246">W przypadku pierwszego przesłania dokumentu należy zawsze w ustawieniu opcji **Ponowne przesłanie dokumentów** wybrać wartość **Nie**.</span><span class="sxs-lookup"><span data-stu-id="4188c-246">For the first submission of any document, always set the **Resubmit documents** option to **No**.</span></span> <span data-ttu-id="4188c-247">Jeśli konieczne jest ponowne przesłanie dokumentu za pośrednictwem usługi, należy skonfigurować tę opcję na wartość **Ttak**.</span><span class="sxs-lookup"><span data-stu-id="4188c-247">If you must resubmit a document through the service, set this option to **Yes**.</span></span>
3. <span data-ttu-id="4188c-248">Na skróconej karcie **Rekordy do uwzględnienia** wybierz opcję **Filtruj**, aby otworzyć okno dialogowe **Zapytania**, w którym można utworzyć kwerendę w celu wybrania dokumentów do przesłania.</span><span class="sxs-lookup"><span data-stu-id="4188c-248">On the **Records to include** FastTab, select **Filter** to open the **Inquiry** dialog box, where you can build a query to select documents for submission.</span></span>

![Przesyłanie dokumentu CFDI](media/e-Invoicing-services-get-started-MEX-Submit-CFDI-document.png)

> [!NOTE]
> <span data-ttu-id="4188c-250">Podczas pierwszej próby przesłania dokumentu za pośrednictwem usługi zostaniesz poproszony o potwierdzenie połączenia z dodatkiem Faktury elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="4188c-250">During your first attempt to submit a document through the service, you will be prompted to confirm the connection with the Electronic invoicing add-on.</span></span> <span data-ttu-id="4188c-251">Wybierz **Kliknij tutaj, aby połaczyć się się z usługą Elektronicznego przesyłania dokumentów**.</span><span class="sxs-lookup"><span data-stu-id="4188c-251">Select **Click here to connect to Electronic Document Submission Service**.</span></span>

### <a name="view-submission-logs"></a><span data-ttu-id="4188c-252">Wyświetlanie dzienników przesyłania</span><span class="sxs-lookup"><span data-stu-id="4188c-252">View submission logs</span></span>

<span data-ttu-id="4188c-253">Dzienniki przesyłania można przeglądać dla wszystkich przesłanych dokumentów lub tylko dla jednego przesłanego dokumentu.</span><span class="sxs-lookup"><span data-stu-id="4188c-253">You can view the submission logs for all submitted documents or for just one submitted document.</span></span>

#### <a name="view-all-submission-logs"></a><span data-ttu-id="4188c-254">Wyświetlanie wszystkich dzienników przesyłania</span><span class="sxs-lookup"><span data-stu-id="4188c-254">View all submission logs</span></span>

<span data-ttu-id="4188c-255">Po włączeniu funkcji **Konfigurowalna integracja z dodatkiem Faktur elektronicznych** dostępna jest nowa strona, na której możesz śledzić proces składania dokumentów.</span><span class="sxs-lookup"><span data-stu-id="4188c-255">After you turn on the **Configurable Electronic invoicing add-on integration** feature, a new page is available that lets you follow up on the document submission process.</span></span> <span data-ttu-id="4188c-256">Możesz użyć tej strony, aby wyświetlić dzienniki przesyłania wszystkich przesłanych dokumentów.</span><span class="sxs-lookup"><span data-stu-id="4188c-256">You can use this page to view the submission logs for all submitted documents.</span></span>

1. <span data-ttu-id="4188c-257">Przejdź do **Administrowanie organizacją \> Okresowe \> Dokumenty elektroniczne \> Dziennik przsyłania dokumentów elektronicznych**.</span><span class="sxs-lookup"><span data-stu-id="4188c-257">Go to **Organization administration \> Periodic \> Electronic documents \> Electronic document submission log**.</span></span>
2. <span data-ttu-id="4188c-258">W polu **Typ dokumentu** wybierz opcję **Arkusz faktur dla odbiorcy**, aby odfiltrować wymagane dokumenty elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="4188c-258">In the **Document type** field, select **Customer invoice journal** to filter for the required electronic documents.</span></span>

    ![Wybór typu dokumentu, aby wyświetlić dzienniki przedłożenia](media/e-Invoicing-services-get-started-MEX-Select-document-type-for-viewing-submission-log.png)

3. <span data-ttu-id="4188c-260">W okienku akcji wybierz **Zapytania \> Szczegóły przesyłania**, aby wyświetlić szczegóły dzienników wykonywania przesyłania.</span><span class="sxs-lookup"><span data-stu-id="4188c-260">On the Action Pane, select **Inquiries \> Submission details** to view the details of the submission execution logs.</span></span>

    ![Wyświetlanie szczegółów dziennika przesyłania](media/e-Invoicing-services-get-started-MEX-View-submission-log-details.png)

<span data-ttu-id="4188c-262">Informacje w dziennikach przesyłania dzielą się między trzy karty skrócone:</span><span class="sxs-lookup"><span data-stu-id="4188c-262">The information in the submission logs is divided among three FastTabs:</span></span>

- <span data-ttu-id="4188c-263">**Przetwarzanie akcji** – Ta skrócona karta przedstawia dziennik wykonywania działań skonfigurowanych w wersji funkcji skonfigurowanej w RCS.</span><span class="sxs-lookup"><span data-stu-id="4188c-263">**Processing actions** – This FastTab shows the execution log for the actions that are configured in the feature version that was set up in RCS.</span></span> <span data-ttu-id="4188c-264">Kolumna **Stan** wskazuje, czy akcja została pomyślnie uruchomiona.</span><span class="sxs-lookup"><span data-stu-id="4188c-264">The **Status** column shows whether the action was successfully run.</span></span>
- <span data-ttu-id="4188c-265">**Pliki akcji** – Ta skrócona karta przedstawia pliki pośrednie, które zostały wygenerowane podczas wykonywania działań.</span><span class="sxs-lookup"><span data-stu-id="4188c-265">**Action files** – This FastTab shows the intermediate files that were generated during execution of the actions.</span></span> <span data-ttu-id="4188c-266">Możesz wybrać **Widok**, aby pobrać plik i wyświetlić go.</span><span class="sxs-lookup"><span data-stu-id="4188c-266">You can select **View** to download and view the file.</span></span>
- <span data-ttu-id="4188c-267">**Dziennik akcji przetwarzania** – Ta skrócona karta przedstawia wyniki komunikacji między dodatkiem Fakturowanie elektroniczne a docelową usługą internetową.</span><span class="sxs-lookup"><span data-stu-id="4188c-267">**Processing action log** – This FastTab shows the results of the communication between the Electronic invoicing add-on and the target web service.</span></span> <span data-ttu-id="4188c-268">Pokazuje również, co zostało zwrócone podczas przetwarzania z usługi internetowej.</span><span class="sxs-lookup"><span data-stu-id="4188c-268">It also shows what was returned by the processing from the web service.</span></span> <span data-ttu-id="4188c-269">W kolumnie **Kod błędu** jest wyświetlany kod zwrotny zwrócony przez usługi autoryzacji sieci Web.</span><span class="sxs-lookup"><span data-stu-id="4188c-269">The **Error code** column shows the return code that was returned by the authorization web service.</span></span>

<span data-ttu-id="4188c-270">Po zatwierdzeniu przesłanej faktury CFDI jej stan jest aktualizowany do **Zatwierdzono**.</span><span class="sxs-lookup"><span data-stu-id="4188c-270">When the submitted CFDI invoice is authorized, its status is updated to **Approved**.</span></span>

#### <a name="view-submission-logs-from-cfdi-invoices"></a><span data-ttu-id="4188c-271">Wyświetl dzienniki przesyłania z faktur CFDI</span><span class="sxs-lookup"><span data-stu-id="4188c-271">View submission logs from CFDI invoices</span></span>

<span data-ttu-id="4188c-272">Po włączeniu funkcji **Konfigurowalna integracja z dodatkiem Faktur elektronicznych** można również przeglądać dzienniki przesyłania z faktur CFDI.</span><span class="sxs-lookup"><span data-stu-id="4188c-272">After you turn on the **ConfigurableElectronic invoicing add-on integration** feature, you can also view the submission logs from CFDI invoices.</span></span>

1. <span data-ttu-id="4188c-273">Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Zapytania i raporty \> CFDI (faktury elektroniczne)**.</span><span class="sxs-lookup"><span data-stu-id="4188c-273">Go to **Accounts receivable \> Inquiries and reports \> CFDI (electronic invoices)**.</span></span>
2. <span data-ttu-id="4188c-274">Wybierz fakturę CFDI, która została przesłana po włączeniu funkcji **Konfigurowalna integracja z dodatkiem Faktur elektronicznych**.</span><span class="sxs-lookup"><span data-stu-id="4188c-274">Select a CFDI invoice that was submitted after the **Configurable Electronic invoicing add-on integration** feature was turned on.</span></span>
3. <span data-ttu-id="4188c-275">W okienku akcji na karcie **Historia** wybierz opcję **Dziennik dokumentów elektronicznych**.</span><span class="sxs-lookup"><span data-stu-id="4188c-275">On the Action Pane, on the **History** tab, select **Electronic document log**.</span></span>

![Wyświetlanie dzienników przesyłania z faktur CFDI](media/e-Invoicing-services-get-started-MEX-View-submission-log-from-CFDI-invoice.png)

> [!NOTE]
> <span data-ttu-id="4188c-277">Dla faktur CFDI, które zostały przesłane przed włączeniem funkcji **Konfigurowalna integracja z dodatkiem Faktur elektronicznych**, przycisk **Historia** jest dostępny.</span><span class="sxs-lookup"><span data-stu-id="4188c-277">For CFDI invoices that were submitted before the **Configurable Electronic invoicing add-on integration** feature was turned on, the **History** button is available.</span></span> <span data-ttu-id="4188c-278">Przycisk **Historia** jest dostępny dla faktur CFDI, które zostały przesłane przed włączeniem funkcji **Konfigurowalna integracja z dodatkiem Faktur elektronicznych**.</span><span class="sxs-lookup"><span data-stu-id="4188c-278">The **History** button isn't available for CFDI invoices that were submitted after the **Configurable Electronic invoicing add-on integration** feature was turned on.</span></span>

### <a name="submit-cancellation-of-cfdi-invoices"></a><span data-ttu-id="4188c-279">Prześlij anulowanie faktur CFDI</span><span class="sxs-lookup"><span data-stu-id="4188c-279">Submit cancellation of CFDI invoices</span></span>

<span data-ttu-id="4188c-280">Po włączeniu funkcji **Konfigurowalna integracja z dodatkiem Faktur elektronicznych** nie można już używać starego procesu anulowania faktur CFDI.</span><span class="sxs-lookup"><span data-stu-id="4188c-280">After you turn on the **Configurable Electronic invoicing add-on integration** feature, the old process for canceling CFDI invoices can no longer be used.</span></span> <span data-ttu-id="4188c-281">Jest on zastępowany nowym procesem anulowania, który jest osadzony na stronie **Dziennik przsyłania dokumentów elektronicznych**.</span><span class="sxs-lookup"><span data-stu-id="4188c-281">It's replaced by a new cancellation process that is embedded on the **Electronic document submission log** page.</span></span>

1. <span data-ttu-id="4188c-282">Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Zapytania i raporty \> CFDI (faktury elektroniczne)**.</span><span class="sxs-lookup"><span data-stu-id="4188c-282">Go to **Accounts receivable \> Inquiries and reports \> CFDI (electronic invoices)**.</span></span>
2. <span data-ttu-id="4188c-283">Jeśli faktura CFDI ma stan **Zatwierdzono**, wybierz **Funkcje \> Anuluj CFDI**.</span><span class="sxs-lookup"><span data-stu-id="4188c-283">If the CFDI invoice has a status of **Approved**, select **Functions \> Cancel CFDI**.</span></span>
3. <span data-ttu-id="4188c-284">Przejdź do **Administrowanie organizacją \> Okresowe \> Dokumenty elektroniczne \> Dziennik przsyłania dokumentów elektronicznych**.</span><span class="sxs-lookup"><span data-stu-id="4188c-284">Go to **Organization administration \> Periodic \> Electronic documents \> Electronic document submission log**.</span></span>
4. <span data-ttu-id="4188c-285">Wybierz faktura CFDI, a następnie wybierz **Funkcje \> Wyślij powiązane zgłoszenia**.</span><span class="sxs-lookup"><span data-stu-id="4188c-285">Select the CFDI invoice, and then select **Functions \> Send related submissions**.</span></span>
5. <span data-ttu-id="4188c-286">Wprowadź opis powiązanego przesyłania, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="4188c-286">Enter a description for the related submission, and then select **OK**.</span></span>

#### <a name="view-cancellation-submission-logs"></a><span data-ttu-id="4188c-287">Wyświetlanie anulowania dzienników przesyłania</span><span class="sxs-lookup"><span data-stu-id="4188c-287">View cancellation submission logs</span></span>

1. <span data-ttu-id="4188c-288">Przejdź do **Administrowanie organizacją \> Okresowe \> Dokumenty elektroniczne \> Dziennik przsyłania dokumentów elektronicznych**.</span><span class="sxs-lookup"><span data-stu-id="4188c-288">Go to **Organization administration \> Periodic \> Electronic documents \> Electronic document submission log**.</span></span>
2. <span data-ttu-id="4188c-289">W polu **Typ dokumentu** wybierz opcję **Arkusz faktur dla odbiorcy**, aby filtrować tylko dokumenty dziennika faktur klienta.</span><span class="sxs-lookup"><span data-stu-id="4188c-289">In the **Document type** field, select **Customer invoice journal** to filter for customer invoice journal documents only.</span></span>
3. <span data-ttu-id="4188c-290">Wybierz fakturę CFDI, a następnie w okienku akcji wybierz **Zapytania \> Powiązane zgłoszenie**.</span><span class="sxs-lookup"><span data-stu-id="4188c-290">Select the CFDI invoice, and then, on the Action Pane, select **Inquiries \> Related submission**.</span></span>

    <span data-ttu-id="4188c-291">Strona **Powiązane dokumenty** przedstawia wszystkie powiązane wnioski i ich status dla danej faktury CFDI.</span><span class="sxs-lookup"><span data-stu-id="4188c-291">The **Related submissions** page shows all related submissions, and their submission status, for a given CFDI invoice.</span></span> <span data-ttu-id="4188c-292">Na poniższej ilustracji pierwszy wiersz przedstawia przesłanie, które zażądało zatwierdzenia faktury CFDI.</span><span class="sxs-lookup"><span data-stu-id="4188c-292">In the following illustration, the first line represents the submission that requested approval of the CFDI invoice.</span></span> <span data-ttu-id="4188c-293">Drugi wiersz przedstawia zgłoszenie, które anulowało fakturę CFDI.</span><span class="sxs-lookup"><span data-stu-id="4188c-293">The second line represents the submission that canceled that CFDI invoice.</span></span>

    ![Wyświetlanie anulowania dzienników przesyłania](media/e-Invoicing-services-get-started-MEX-View-cancellation-submission-log.png)

4. <span data-ttu-id="4188c-295">W okienku akcji wybierz **Zapytania \> Szczegóły przesyłania**, aby wyświetlić szczegóły dzienników wykonywania przesyłania.</span><span class="sxs-lookup"><span data-stu-id="4188c-295">On the Action Pane, select **Inquiries \> Submission details** to view the details of the submission execution logs.</span></span>

    ![Wyświetlanie anulowania dziennika przesyłania](media/e-Invoicing-services-get-started-MEX-View-cancellation-submission-log-details.png)

## <a name="privacy-notice"></a><span data-ttu-id="4188c-297">Klauzula prywatności</span><span class="sxs-lookup"><span data-stu-id="4188c-297">Privacy notice</span></span>
<span data-ttu-id="4188c-298">Włączenie funkcji MX-00010 i MX-00016 (faktura CFDI i anulowanie CFDI) może wymagać przesłania ograniczonych danych, w tym numeru identyfikacji podatkowej organizacji.</span><span class="sxs-lookup"><span data-stu-id="4188c-298">Enabling the MX-00010 and MX-00016 (CFDI Invoice and CFDI Cancellation) features may require sending limited data, which includes the organization tax registration ID.</span></span> <span data-ttu-id="4188c-299">Zostanie to przekazane agencjom zewnętrznym upoważnionym przez organ podatkowy w celu wysyłania faktur elektronicznych do tego organu podatkowego w predefiniowanym formacie wymaganym do integracji z rządową usługą internetową.</span><span class="sxs-lookup"><span data-stu-id="4188c-299">This will be transmitted to third-party agencies authorized by the tax authority for purposes of sending electronic invoices to this tax authority in the predefined format required for integration with the government’s web service.</span></span> <span data-ttu-id="4188c-300">Administrator może włączać i wyłączać funkcje MX-00010 i MX-00016 (faktura CFDI i anulowanie CFDI) przechodząc do **Administrowanie organizacją \> Konfiguracja \> Parametry dokumentu elektronicznego**.</span><span class="sxs-lookup"><span data-stu-id="4188c-300">An administrator can enable and disable the MX-00010 and MX-00016 (CFDI Invoice and CFDI Cancellation) features by navigating to **Organization administration \> Setup \> Electronic document parameters**.</span></span> <span data-ttu-id="4188c-301">Wybierz kartę **Funkcje**, wybierz wiersze zawierające funkcje MX-00010 i MX-00016, a następnie dokonaj odpowiedniego wyboru.</span><span class="sxs-lookup"><span data-stu-id="4188c-301">Select the **Features** tab, select the rows containing the MX-00010 and MX-00016 features, and then make the appropriate selection.</span></span> <span data-ttu-id="4188c-302">Dane importowane z tych zewnętrznych systemów do tej usługi online Dynamics 365 podlegają naszym [oświadczeniom o ochronie prywatności](https://go.microsoft.com/fwlink/?LinkId=512132).</span><span class="sxs-lookup"><span data-stu-id="4188c-302">Data imported from these external systems into this Dynamics 365 online service are subject to our [privacy statement](https://go.microsoft.com/fwlink/?LinkId=512132).</span></span> <span data-ttu-id="4188c-303">Aby uzyskać więcej informacji, zapoznaj się z sekcjami Uwagi dotyczące prywatności w dokumentacji funkcji dla danego kraju.</span><span class="sxs-lookup"><span data-stu-id="4188c-303">Consult the Privacy notice sections in country-specific feature documentation for more information.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4188c-304">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="4188c-304">Additional resources</span></span>

- [<span data-ttu-id="4188c-305">Omówienie dodatku Faktur elektronicznych</span><span class="sxs-lookup"><span data-stu-id="4188c-305">Electronic invoicing add-on overview</span></span>](e-invoicing-service-overview.md)
- [<span data-ttu-id="4188c-306">Rozpocznij pracę z dodatkiem Faktury elektroniczne</span><span class="sxs-lookup"><span data-stu-id="4188c-306">Get started with the Electronic invoicing add-on</span></span>](e-invoicing-get-started.md)
- [<span data-ttu-id="4188c-307">Skonfiguruj dodatek Faktury elektroniczne</span><span class="sxs-lookup"><span data-stu-id="4188c-307">Set up the Electronic invoicing add-on</span></span>](e-invoicing-setup.md)
