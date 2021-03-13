---
title: Zacznij od administrowania usługą dodatkową dotyczącą fakturowania elektronicznego
description: W tym temacie opisano sposób rozpoczęcia pracy z dodatkiem Faktur elektronicznych.
author: gionoder
manager: AnnBe
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 111ec65aa826795125d4a9ce835f72e1a0f41b7b
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104423"
---
# <a name="get-started-with-electronic-invoicing-add-on-service-administration"></a><span data-ttu-id="73df0-103">Zacznij od administrowania usługą dodatkową dotyczącą fakturowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="73df0-103">Get started with Electronic invoicing add-on service administration</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

## <a name="prerequisites"></a><span data-ttu-id="73df0-104">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="73df0-104">Prerequisites</span></span>

<span data-ttu-id="73df0-105">Przed wykonaniem procedur opisanych w tym temacie muszą być spełnione następujące wymagania wstępne:</span><span class="sxs-lookup"><span data-stu-id="73df0-105">Before you complete the procedures in this topic, the following prerequisites must be in place:</span></span>

- <span data-ttu-id="73df0-106">Musisz mieć dostęp do konta Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="73df0-106">You must have access to your Microsoft Dynamics Lifecycle Services (LCS) account.</span></span>
- <span data-ttu-id="73df0-107">Musisz mieć projekt usługi LCS z wersją 10.0.13 lub nowszą firmy Microsoft Dynamics 365 Finance i Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="73df0-107">You must have an LCS project that includes version 10.0.13 or later of Microsoft Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="73df0-108">Ponadto te aplikacje muszą zostać wdrożone w jednej z następujących lokalizacji geograficznych platformy Azure:</span><span class="sxs-lookup"><span data-stu-id="73df0-108">Additionally, these apps must be deployed in one of the following Azure geographies:</span></span>

    - <span data-ttu-id="73df0-109">Wschodnie stany USA</span><span class="sxs-lookup"><span data-stu-id="73df0-109">East US</span></span>
    - <span data-ttu-id="73df0-110">Zachodnie stany USA</span><span class="sxs-lookup"><span data-stu-id="73df0-110">West US</span></span>
    - <span data-ttu-id="73df0-111">Europa Północna</span><span class="sxs-lookup"><span data-stu-id="73df0-111">North EU</span></span>
    - <span data-ttu-id="73df0-112">Europa Zachodnia</span><span class="sxs-lookup"><span data-stu-id="73df0-112">West EU</span></span>

- <span data-ttu-id="73df0-113">Musisz mieć dostęp do swojego konta Dynamics 365 Regulatory Configuration Services (RCS).</span><span class="sxs-lookup"><span data-stu-id="73df0-113">You must have access to your Dynamics 365 Regulatory Configuration Services (RCS) account.</span></span>
- <span data-ttu-id="73df0-114">Musisz aktywować funkcję globalizacji dla swojego konta RCS w zarządzaniu funkcjami.</span><span class="sxs-lookup"><span data-stu-id="73df0-114">You must activate the Globalization feature for your RCS account in Feature management.</span></span> <span data-ttu-id="73df0-115">Aby uzyskać więcej informacji, zobacz [Regulatory Configuration Services (RCS) – funkcje globalizacji](rcs-globalization-feature.md).</span><span class="sxs-lookup"><span data-stu-id="73df0-115">For more information, see [Regulatory Configuration Services (RCS) - Globalization features](rcs-globalization-feature.md).</span></span>
- <span data-ttu-id="73df0-116">Musisz utworzyć magazyn kluczy i konto magazynu na platformie Azure.</span><span class="sxs-lookup"><span data-stu-id="73df0-116">You must create a key vault and a storage account in Azure.</span></span> <span data-ttu-id="73df0-117">Aby uzyskać więcej informacji, przejrzyj temat [Utwórz konto magazynu Azure i magazyn kluczy](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="73df0-117">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>

## <a name="install-the-add-on-for-microservices-in-lifecycle-services"></a><span data-ttu-id="73df0-118">Zainstaluj dodatek dla mikrousług w Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="73df0-118">Install the add-on for microservices in Lifecycle Services</span></span>

1. <span data-ttu-id="73df0-119">Zaloguj się do swojego konta LCS.</span><span class="sxs-lookup"><span data-stu-id="73df0-119">Sign in to your LCS account.</span></span>
2. <span data-ttu-id="73df0-120">Wybierz kafelek **Zarządzanie funkcjami w wersji zapoznawczej**.</span><span class="sxs-lookup"><span data-stu-id="73df0-120">Select the **Preview feature management** tile.</span></span>
3. <span data-ttu-id="73df0-121">W sekcji **Funkcje w publicznych wersjach zapoznawczych** wybierz **usługę fakturowania elektronicznego**.</span><span class="sxs-lookup"><span data-stu-id="73df0-121">In the **Public Preview Features** section, select **e-Invoicing service**.</span></span>
4. <span data-ttu-id="73df0-122">Sprawdź, czy w opcji **Funkcja wersji zapoznawczej włączona** jest ustawiona wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="73df0-122">Make sure that the **Preview feature enabled** option is set to **Yes**.</span></span>

## <a name="set-up-the-parameters-for-rcs-integration-with-the-electronic-invoicing-add-on"></a><span data-ttu-id="73df0-123">Skonfiguruj parametry RCS z dodatkiem Faktury elektroniczne</span><span class="sxs-lookup"><span data-stu-id="73df0-123">Set up the parameters for RCS integration with the Electronic invoicing add-on</span></span>

1. <span data-ttu-id="73df0-124">Zaloguj się do swojego konta RCS.</span><span class="sxs-lookup"><span data-stu-id="73df0-124">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="73df0-125">W module **Powiązane odnośniki**, w obszarze roboczym **Raportowanie elektroniczne** wybierz opcję **Parametry raportowania elektronicznego**.</span><span class="sxs-lookup"><span data-stu-id="73df0-125">In the **Electronic reporting** workspace, in the **Related links** section, select **Electronic reporting parameters**.</span></span>
3. <span data-ttu-id="73df0-126">Na karcie **Usługa fakturowania elektronicznego** w polu **Identyfikator URI punktu końcowego usługi** wprowadź odpowiedni punkt końcowy usługi dla geografii systemu Azure, tak jak pokazano w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="73df0-126">On the **e-Invoicing service** tab, in the **Service endpoint URI** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="73df0-127">Geografia platformy Datacenter Azure</span><span class="sxs-lookup"><span data-stu-id="73df0-127">Datacenter Azure geography</span></span> | <span data-ttu-id="73df0-128">Adres URI punktu końcowego usługi</span><span class="sxs-lookup"><span data-stu-id="73df0-128">Service endpoint URI</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="73df0-129">Wschodnie stany USA</span><span class="sxs-lookup"><span data-stu-id="73df0-129">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="73df0-130">Zachodnie stany USA</span><span class="sxs-lookup"><span data-stu-id="73df0-130">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="73df0-131">Europa Północna</span><span class="sxs-lookup"><span data-stu-id="73df0-131">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="73df0-132">Europa Zachodnia</span><span class="sxs-lookup"><span data-stu-id="73df0-132">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

4. <span data-ttu-id="73df0-133">Upewnij się, że pole **Identyfikator aplikacji** ma ustawioną wartość **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span><span class="sxs-lookup"><span data-stu-id="73df0-133">Verify that the **Application Id** field is set to **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span> <span data-ttu-id="73df0-134">Ta wartość jest stałą wartością.</span><span class="sxs-lookup"><span data-stu-id="73df0-134">This value is a fixed value.</span></span>
5. <span data-ttu-id="73df0-135">W polu **Identyfikator środowiska usługi LCS** wprowadź identyfikator konta subskrypcji LCS.</span><span class="sxs-lookup"><span data-stu-id="73df0-135">In the **LCS Environment Id** field, enter the ID of your LCS subscription account.</span></span>
6. <span data-ttu-id="73df0-136">Wybierz przycisk **Zapisz** i zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="73df0-136">Select **Save**, and then close the page.</span></span>

## <a name="create-key-vault-secret"></a><span data-ttu-id="73df0-137">Utwórz wpis tajny magazynu kluczy</span><span class="sxs-lookup"><span data-stu-id="73df0-137">Create Key Vault secret</span></span>

1. <span data-ttu-id="73df0-138">Zaloguj się do swojego konta RCS.</span><span class="sxs-lookup"><span data-stu-id="73df0-138">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="73df0-139">Otwórz nowy obszar roboczy **Funkcja globalizacji**, a następnie w obszarze **Środowisko** wybierz kafelek **Fakturowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="73df0-139">In the **Globalization feature** workspace, in the **Environment** section, select the **e-Invoicing** tile.</span></span>
3. <span data-ttu-id="73df0-140">Na stronie **Ustawienia środowiska**, w okienku akcji wybierz **Środowisko serwisu**, a następnie wybierz opcję **Parametry Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="73df0-140">On the **Environment setups** page, on the action Pane, select **Service environment**, and then select **Key Vault parameters**.</span></span>
4. <span data-ttu-id="73df0-141">Wybierz opcję **Nowy**, aby utworzyć klucz tajny.</span><span class="sxs-lookup"><span data-stu-id="73df0-141">Select **New** to create a key vault secret.</span></span>
5. <span data-ttu-id="73df0-142">W polu **Nazwa** wprowadź nazwę wpisu tajnego magazynu kluczy.</span><span class="sxs-lookup"><span data-stu-id="73df0-142">In the **Name** field, enter the name of the key vault secret.</span></span> <span data-ttu-id="73df0-143">W polu **Opis wprowadź** opis.</span><span class="sxs-lookup"><span data-stu-id="73df0-143">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="73df0-144">W polu **URI magazynu kluczy** wklej klucz tajny z Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="73df0-144">In the **Key Vault URI** field, paste the secret from Azure Key Vault.</span></span>
7. <span data-ttu-id="73df0-145">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="73df0-145">Select **Save**.</span></span>

## <a name="create-storage-account-secret"></a><span data-ttu-id="73df0-146">Utwórz klucz tajny konta magazynu</span><span class="sxs-lookup"><span data-stu-id="73df0-146">Create Storage account secret</span></span>

1. <span data-ttu-id="73df0-147">Na stronie **Kluczowe parametry**, w sekcji **Certyfikaty** wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="73df0-147">On **Key vault parameters** page, in the **Certificates** section, select **Add**.</span></span>
2. <span data-ttu-id="73df0-148">W polu **Nazwa** wprowadź ten sam klucz tajny konta magazynu.</span><span class="sxs-lookup"><span data-stu-id="73df0-148">In the **Name** field, enter the same of the storage account secret.</span></span> <span data-ttu-id="73df0-149">W polu **Opis wprowadź** opis.</span><span class="sxs-lookup"><span data-stu-id="73df0-149">In the **Description** field, enter a description.</span></span>
3. <span data-ttu-id="73df0-150">W polu **Typ** zaznacz opcję **Certyfikat**.</span><span class="sxs-lookup"><span data-stu-id="73df0-150">In the **Type** field, select **Certificate**.</span></span>
4. <span data-ttu-id="73df0-151">Wybierz przycisk **Zapisz** i zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="73df0-151">Select **Save**, and then close the page.</span></span>

## <a name="create-an-electronic-invoicing-add-on-environment"></a><span data-ttu-id="73df0-152">Tworzenie środowiska dodatku Faktur elektronicznych</span><span class="sxs-lookup"><span data-stu-id="73df0-152">Create an Electronic invoicing add-on environment</span></span>

1. <span data-ttu-id="73df0-153">Zaloguj się do swojego konta RCS.</span><span class="sxs-lookup"><span data-stu-id="73df0-153">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="73df0-154">Otwórz nowy obszar roboczy **Funkcja globalizacji**, a następnie w obszarze **Środowisko** wybierz kafelek **Fakturowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="73df0-154">In the **Globalization feature** workspace, in the **Environment** section, select the **e-Invoicing** tile.</span></span>

## <a name="create-a-service-environment"></a><span data-ttu-id="73df0-155">Tworzenie środowiska usługi</span><span class="sxs-lookup"><span data-stu-id="73df0-155">Create a service environment</span></span>

1. <span data-ttu-id="73df0-156">Na stronie **Ustawienia środowiska** w okienku akcji wybierz pozycję **Środowisko usługi**.</span><span class="sxs-lookup"><span data-stu-id="73df0-156">On the **Environment setups** page, on the action Pane, select **Service environment**.</span></span>
2. <span data-ttu-id="73df0-157">Wybierz pozycję **Nowy**, aby utworzyć nowe środowisko usługi.</span><span class="sxs-lookup"><span data-stu-id="73df0-157">Select **New** to create a new service environment.</span></span>
3. <span data-ttu-id="73df0-158">W polu **Nazwa** wprowadź nazwę środowiska e-fakturowania.</span><span class="sxs-lookup"><span data-stu-id="73df0-158">In the **Name** field, enter the name of the e-Invoicing environment.</span></span> <span data-ttu-id="73df0-159">W polu **Opis wprowadź** opis.</span><span class="sxs-lookup"><span data-stu-id="73df0-159">In the **Description** field, enter a description.</span></span>
4. <span data-ttu-id="73df0-160">W polu **Tajny klucz tokenu sygnatury dostępu Współdzielonego magazynu** wybierz nazwę certyfikatu, który musi być używany do uwierzytelnienia dostępu do konta magazynu.</span><span class="sxs-lookup"><span data-stu-id="73df0-160">In the **Storage SAS token secret** field, select the name of the certificate that must be used to authenticate access to the storage account.</span></span>
5. <span data-ttu-id="73df0-161">W sekcji **Użytkownicy** wybierz opcję **Dodaj**, aby dodać użytkownika, który może przesyłać faktury elektroniczne za pośrednictwem środowiska, a także połączyć się z kontem magazynu.</span><span class="sxs-lookup"><span data-stu-id="73df0-161">In the **Users** section, select **Add** to add a user who is allowed to submit electronic invoices through the environment and also connect to the storage account.</span></span>
6. <span data-ttu-id="73df0-162">W polu **Identyfikator użytkownika** wprowadź alias użytkownika.</span><span class="sxs-lookup"><span data-stu-id="73df0-162">In the **User ID** field, enter the alias of the user.</span></span> <span data-ttu-id="73df0-163">W polu **Adres e-mail** wprowadź adres e-mail dla użytkownika.</span><span class="sxs-lookup"><span data-stu-id="73df0-163">In the **Email** field, enter the user's email address.</span></span>
7. <span data-ttu-id="73df0-164">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="73df0-164">Select **Save**.</span></span>
8. <span data-ttu-id="73df0-165">Jeśli faktury dotyczące Twojego kraju / regionu wymagają łańcucha certyfikatów do stosowania podpisów cyfrowych, w okienku Akcja wybierz **Parametry Key Vault**, a następnie wybierz **Łańcuch certyfikatów** i wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="73df0-165">If your country/region-specific invoices require a chain of certificates to apply digital signatures, on the Action pane, select **Key Vault parameters**, then select **Chain of certificates**, and follow these steps:</span></span>

    1. <span data-ttu-id="73df0-166">Wybierz pozycję **Nowy**, aby utworzyć łańcuch certyfikatów.</span><span class="sxs-lookup"><span data-stu-id="73df0-166">Select **New** to create a chain of certificates.</span></span>
    2. <span data-ttu-id="73df0-167">W polu **Nazwa** wprowadź nazwę łańcucha certyfikatów.</span><span class="sxs-lookup"><span data-stu-id="73df0-167">In the **Name** field, enter the name of the chain of certificate.</span></span> <span data-ttu-id="73df0-168">W polu **Opis wprowadź** opis.</span><span class="sxs-lookup"><span data-stu-id="73df0-168">In the **Description** field, enter a description.</span></span>
    3. <span data-ttu-id="73df0-169">W sekcji **Certyfikaty** wybierz pozycję **Dodaj**, aby dodać certyfikat do łańcucha.</span><span class="sxs-lookup"><span data-stu-id="73df0-169">In the **Certificates** section, select **Add** to add a certificate to the chain.</span></span>
    4. <span data-ttu-id="73df0-170">Przycisk **W górę** lub **W dół** umożliwia zmianę pozycji certyfikatu w łańcuchu.</span><span class="sxs-lookup"><span data-stu-id="73df0-170">Use the **Up** or **Down** button to change the position of the certificate in the chain.</span></span>
    5. <span data-ttu-id="73df0-171">Wybierz przycisk **Zapisz** i zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="73df0-171">Select **Save**, and then close the page.</span></span>
    6. <span data-ttu-id="73df0-172">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="73df0-172">Close the page.</span></span>
9. <span data-ttu-id="73df0-173">Na stronie **Środowisko usługi** w okienku akcji wybierz opcję **Publikuj**, aby opublikować środowisko w chmurze.</span><span class="sxs-lookup"><span data-stu-id="73df0-173">On **Service environment** page, on the Action Pane, select **Publish** to publish the environment to the cloud.</span></span> <span data-ttu-id="73df0-174">Wartość pola **Stan** jest zmieniana na **Opublikowana**.</span><span class="sxs-lookup"><span data-stu-id="73df0-174">The value of the **Status** field is changed to **Published**.</span></span>

## <a name="create-a-connected-application"></a><span data-ttu-id="73df0-175">Utwórz połączoną aplikację</span><span class="sxs-lookup"><span data-stu-id="73df0-175">Create a connected application</span></span>

1. <span data-ttu-id="73df0-176">Na stronie **Ustawienia środowiska** w okienku akcji wybierz pozycję **Połączone aplikacje**.</span><span class="sxs-lookup"><span data-stu-id="73df0-176">On the **Environment setups** page, on the action Pane, select **Connected applications**.</span></span>
2. <span data-ttu-id="73df0-177">Wybierz pozycję **Nowy**, aby utworzyć połączoną aplikację.</span><span class="sxs-lookup"><span data-stu-id="73df0-177">Select **New** to create a connected application.</span></span>
3. <span data-ttu-id="73df0-178">W polu **Nazwa** wprowadź nazwę aplikacji do połączenia.</span><span class="sxs-lookup"><span data-stu-id="73df0-178">In the **Name** field, enter the name of the application to connect.</span></span>
4. <span data-ttu-id="73df0-179">W polu **Aplikacja** wprowadź adres URL środowiska Finance and Supply Chain Management, aby nawiązać połączenie.</span><span class="sxs-lookup"><span data-stu-id="73df0-179">In the **Application** field, enter the URL of the Finance and Supply Chain Management environment to connect.</span></span>
4. <span data-ttu-id="73df0-180">W polu **Dzierżawca** wprowadź dzierżawcę Finance and Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="73df0-180">In the **Tenant** field, enter the tenant of the Finance and Supply Chain Management environment.</span></span>
5. <span data-ttu-id="73df0-181">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="73df0-181">Select **Save**.</span></span>
6. <span data-ttu-id="73df0-182">W okienku akcji wybierz opcję **Sprawdź połączenie**, aby przetestować połączenie ze środowiskiem.</span><span class="sxs-lookup"><span data-stu-id="73df0-182">On the Action Pane, select **Check connection** to test the connection with the environment.</span></span> <span data-ttu-id="73df0-183">Następnie zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="73df0-183">Then close the page.</span></span>

## <a name="link-connected-applications-to-environments"></a><span data-ttu-id="73df0-184">Połącz połączone aplikacje ze środowiskami</span><span class="sxs-lookup"><span data-stu-id="73df0-184">Link connected applications to environments</span></span>

1. <span data-ttu-id="73df0-185">Na stronie **Ustawienia środowiska** wybierz pozycję **Nowy**, aby przypisać połączoną aplikację do środowiska.</span><span class="sxs-lookup"><span data-stu-id="73df0-185">On the **Environment setups** page, select **New** to assign a connected application to an environment.</span></span>
2. <span data-ttu-id="73df0-186">W polu **Połączona aplikacja** wybierz połączoną aplikację.</span><span class="sxs-lookup"><span data-stu-id="73df0-186">In the **Connected application** field, select a connected application.</span></span>
3. <span data-ttu-id="73df0-187">W polu **Środowisko usługi** wybierz środowisko usługi.</span><span class="sxs-lookup"><span data-stu-id="73df0-187">In the **Service environment** field, select a service environment.</span></span>
4. <span data-ttu-id="73df0-188">Wybierz przycisk **Zapisz** i zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="73df0-188">Select **Save**, and then close the page.</span></span>

## <a name="set-up-the-electronic-invoicing-add-on-integration-in-finance-and-supply-chain-management"></a><span data-ttu-id="73df0-189">Skonfiguruj integrację dodatku Faktur elektronicznych w rozwiązaniach Finance i Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="73df0-189">Set up the Electronic invoicing add-on integration in Finance and Supply Chain Management</span></span>

### <a name="turn-on-the-electronic-invoicing-add-on-integration-feature"></a><span data-ttu-id="73df0-190">Funkcja integracji faktur elektronicznych jest włączana za pośrednictwem terminów wyświetlania</span><span class="sxs-lookup"><span data-stu-id="73df0-190">Turn on the Electronic invoicing add-on integration feature</span></span>

1. <span data-ttu-id="73df0-191">Zaloguj się do wystąpienia Finance lub Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="73df0-191">Sign in to your Finance or Supply Chain Management instance.</span></span>
2. <span data-ttu-id="73df0-192">W obszarze roboczym **Zarządzanie funkcjami** wyszukaj funkcję **Integracja dodatku do elektronicznego fakturowania**.</span><span class="sxs-lookup"><span data-stu-id="73df0-192">In the **Feature management** workspace, search for the **Electronic invoicing add-on integration** feature.</span></span> <span data-ttu-id="73df0-193">Jeśli ta funkcja nie jest wyświetlana na stronie, wybierz pozycję **Sprawdź, czy nie są aktualizacje**.</span><span class="sxs-lookup"><span data-stu-id="73df0-193">If this feature doesn't appear on the page, select **Check for updates**.</span></span>
3. <span data-ttu-id="73df0-194">Wybierz funkcję, a następnie wybierz **Wyłącz teraz**.</span><span class="sxs-lookup"><span data-stu-id="73df0-194">Select the feature, and then select **Enable now**.</span></span>

### <a name="set-up-the-service-endpoint-url"></a><span data-ttu-id="73df0-195">Konfigurowanie adresu URL punktu końcowego usługi</span><span class="sxs-lookup"><span data-stu-id="73df0-195">Set up the service endpoint URL</span></span>

1. <span data-ttu-id="73df0-196">Przejdź do **Administrowanie organizacją \> Konfiguracja \> Parametry dokumentu elektronicznego**.</span><span class="sxs-lookup"><span data-stu-id="73df0-196">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="73df0-197">Na karcie **Usługa przesyłania** w polu **Identyfikator URL punktu końcowego usługi** wprowadź odpowiedni punkt końcowy usługi dla geografii systemu Azure, tak jak pokazano w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="73df0-197">On the **Submission service** tab, in the **Service endpoint URL** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="73df0-198">Geografia platformy Datacenter Azure</span><span class="sxs-lookup"><span data-stu-id="73df0-198">Datacenter Azure geography</span></span> | <span data-ttu-id="73df0-199">Adres URL punktu końcowego usługi</span><span class="sxs-lookup"><span data-stu-id="73df0-199">Service endpoint URL</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="73df0-200">Wschodnie stany USA</span><span class="sxs-lookup"><span data-stu-id="73df0-200">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="73df0-201">Zachodnie stany USA</span><span class="sxs-lookup"><span data-stu-id="73df0-201">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="73df0-202">Europa Północna</span><span class="sxs-lookup"><span data-stu-id="73df0-202">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="73df0-203">Europa Zachodnia</span><span class="sxs-lookup"><span data-stu-id="73df0-203">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

3. <span data-ttu-id="73df0-204">W polu **Środowisko** wprowadź nazwę środowiska dodatkowego fakturowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="73df0-204">In the **Environment** field, enter the name of the Electronic invoicing add-on environment.</span></span>
4. <span data-ttu-id="73df0-205">Wybierz przycisk **Zapisz** i zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="73df0-205">Select **Save**, and then close the page.</span></span>
