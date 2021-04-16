---
title: Rozpoczynanie pracy z fakturowaniem elektronicznym — administrowanie usługami
description: W tym temacie opisano sposób rozpoczęcia pracy z funkcją Faktur elektronicznych.
author: gionoder
ms.date: 03/29/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: ec431cb4a3620459d905f64a80fd820a2113290f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840155"
---
# <a name="get-started-with-electronic-invoicing-service-administration"></a><span data-ttu-id="dd87a-103">Rozpoczynanie pracy z fakturowaniem elektronicznym — administrowanie usługami</span><span class="sxs-lookup"><span data-stu-id="dd87a-103">Get started with Electronic invoicing service administration</span></span>

[!include [banner](../includes/banner.md)]

## <a name="prerequisites"></a><span data-ttu-id="dd87a-104">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="dd87a-104">Prerequisites</span></span>

<span data-ttu-id="dd87a-105">Przed wykonaniem procedur opisanych w tym temacie muszą być spełnione następujące wymagania wstępne:</span><span class="sxs-lookup"><span data-stu-id="dd87a-105">Before you complete the procedures in this topic, the following prerequisites must be in place:</span></span>

- <span data-ttu-id="dd87a-106">Musisz mieć dostęp do konta Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="dd87a-106">You must have access to your Microsoft Dynamics Lifecycle Services (LCS) account.</span></span>
- <span data-ttu-id="dd87a-107">Musisz mieć projekt usługi LCS z wersją 10.0.17 lub nowszą firmy Microsoft Dynamics 365 Finance i Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="dd87a-107">You must have an LCS project that includes version 10.0.17 or later of Microsoft Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="dd87a-108">Ponadto te aplikacje muszą zostać wdrożone w jednej z następujących lokalizacji geograficznych platformy Azure:</span><span class="sxs-lookup"><span data-stu-id="dd87a-108">Additionally, these apps must be deployed in one of the following Azure geographies:</span></span>

    - <span data-ttu-id="dd87a-109">Wschodnie stany USA</span><span class="sxs-lookup"><span data-stu-id="dd87a-109">East US</span></span>
    - <span data-ttu-id="dd87a-110">Zachodnie stany USA</span><span class="sxs-lookup"><span data-stu-id="dd87a-110">West US</span></span>
    - <span data-ttu-id="dd87a-111">Europa Północna</span><span class="sxs-lookup"><span data-stu-id="dd87a-111">North EU</span></span>
    - <span data-ttu-id="dd87a-112">Europa Zachodnia</span><span class="sxs-lookup"><span data-stu-id="dd87a-112">West EU</span></span>

- <span data-ttu-id="dd87a-113">Musisz mieć dostęp do swojego konta Dynamics 365 Regulatory Configuration Services (RCS).</span><span class="sxs-lookup"><span data-stu-id="dd87a-113">You must have access to your Dynamics 365 Regulatory Configuration Services (RCS) account.</span></span>
- <span data-ttu-id="dd87a-114">Musisz aktywować funkcję globalizacji dla swojego konta RCS w zarządzaniu funkcjami.</span><span class="sxs-lookup"><span data-stu-id="dd87a-114">You must activate the Globalization feature for your RCS account in Feature management.</span></span> <span data-ttu-id="dd87a-115">Aby uzyskać więcej informacji, zobacz [Regulatory Configuration Services (RCS) – funkcje globalizacji](rcs-globalization-feature.md).</span><span class="sxs-lookup"><span data-stu-id="dd87a-115">For more information, see [Regulatory Configuration Services (RCS) - Globalization features](rcs-globalization-feature.md).</span></span>
- <span data-ttu-id="dd87a-116">Musisz utworzyć magazyn kluczy i konto magazynu na platformie Azure.</span><span class="sxs-lookup"><span data-stu-id="dd87a-116">You must create a key vault and a storage account in Azure.</span></span> <span data-ttu-id="dd87a-117">Aby uzyskać więcej informacji, przejrzyj temat [Utwórz konto magazynu Azure i magazyn kluczy](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="dd87a-117">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>

## <a name="install-the-add-in-for-microservices-in-lifecycle-services"></a><span data-ttu-id="dd87a-118">Zainstaluj dodatek dla mikrousług w Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="dd87a-118">Install the add-in for microservices in Lifecycle Services</span></span>

1. <span data-ttu-id="dd87a-119">Zaloguj się do swojego konta LCS.</span><span class="sxs-lookup"><span data-stu-id="dd87a-119">Sign in to your LCS account.</span></span>
2. <span data-ttu-id="dd87a-120">Wybierz kafelek **Zarządzanie funkcjami w wersji zapoznawczej**.</span><span class="sxs-lookup"><span data-stu-id="dd87a-120">Select the **Preview feature management** tile.</span></span>
3. <span data-ttu-id="dd87a-121">W sekcji **Funkcje w publicznych wersjach zapoznawczych** wybierz **usługę fakturowania elektronicznego**.</span><span class="sxs-lookup"><span data-stu-id="dd87a-121">In the **Public Preview Features** section, select **e-Invoicing service**.</span></span>
4. <span data-ttu-id="dd87a-122">Sprawdź, czy w opcji **Funkcja wersji zapoznawczej włączona** jest ustawiona wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="dd87a-122">Make sure that the **Preview feature enabled** option is set to **Yes**.</span></span>
5. <span data-ttu-id="dd87a-123">Na pulpicie nawigacyjnym usługi LCS wybierz projekt wdrożenia usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="dd87a-123">On your LCS dashboard, select your LCS deployment project.</span></span> <span data-ttu-id="dd87a-124">Projekt usługi LCS musi być uruchomiony.</span><span class="sxs-lookup"><span data-stu-id="dd87a-124">The LCS project must be running.</span></span>
7. <span data-ttu-id="dd87a-125">Na karcie **Dodatki środowiska** wybierz opcję **Zainstaluj nowy dodatek**.</span><span class="sxs-lookup"><span data-stu-id="dd87a-125">On the **Environment add-ins** tab, select **Install a new add-in**.</span></span>
8. <span data-ttu-id="dd87a-126">Wybierz **usługi fakturowania elektronicznego**.</span><span class="sxs-lookup"><span data-stu-id="dd87a-126">Select **e-invoicing Services**.</span></span>
9. <span data-ttu-id="dd87a-127">W polu **Identyfikator aplikacji AAD** wprowadź nazwę **091c98b0-a1c9-4b02-b62c-7753395ccabe**.</span><span class="sxs-lookup"><span data-stu-id="dd87a-127">In the **AAD application ID** field, enter **091c98b0-a1c9-4b02-b62c-7753395ccabe**.</span></span> <span data-ttu-id="dd87a-128">Ta wartość jest stałą wartością.</span><span class="sxs-lookup"><span data-stu-id="dd87a-128">This is a fixed value.</span></span>
10. <span data-ttu-id="dd87a-129">W polu **Identyfikator dzierżawy usługi AAD** wprowadź identyfikator dzierżawy konta subskrypcji systemu Azure.</span><span class="sxs-lookup"><span data-stu-id="dd87a-129">In the **AAD tenant ID** field, enter the tenant ID of your Azure subscription account.</span></span>
11. <span data-ttu-id="dd87a-130">Przejrzyj warunki, a następnie zaznacz pole wyboru.</span><span class="sxs-lookup"><span data-stu-id="dd87a-130">Review the terms and conditions, and then select the check box.</span></span>
12. <span data-ttu-id="dd87a-131">Wybierz **Zainstaluj**.</span><span class="sxs-lookup"><span data-stu-id="dd87a-131">Select **Install**.</span></span>


## <a name="set-up-the-parameters-for-rcs-integration-with-electronic-invoicing"></a><span data-ttu-id="dd87a-132">Skonfiguruj parametry RCS z Faktury elektroniczne</span><span class="sxs-lookup"><span data-stu-id="dd87a-132">Set up the parameters for RCS integration with Electronic invoicing</span></span>

1. <span data-ttu-id="dd87a-133">Zaloguj się do swojego konta RCS.</span><span class="sxs-lookup"><span data-stu-id="dd87a-133">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="dd87a-134">W module **Powiązane odnośniki**, w obszarze roboczym **Raportowanie elektroniczne** wybierz opcję **Parametry raportowania elektronicznego**.</span><span class="sxs-lookup"><span data-stu-id="dd87a-134">In the **Electronic reporting** workspace, in the **Related links** section, select **Electronic reporting parameters**.</span></span>
3. <span data-ttu-id="dd87a-135">Na karcie **Usługa fakturowania elektronicznego** w polu **Identyfikator URI punktu końcowego usługi** wprowadź odpowiedni punkt końcowy usługi dla geografii systemu Azure, tak jak pokazano w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="dd87a-135">On the **e-Invoicing service** tab, in the **Service endpoint URI** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="dd87a-136">Geografia platformy Datacenter Azure</span><span class="sxs-lookup"><span data-stu-id="dd87a-136">Datacenter Azure geography</span></span> | <span data-ttu-id="dd87a-137">Adres URI punktu końcowego usługi</span><span class="sxs-lookup"><span data-stu-id="dd87a-137">Service endpoint URI</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="dd87a-138">Wschodnie stany USA</span><span class="sxs-lookup"><span data-stu-id="dd87a-138">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="dd87a-139">Zachodnie stany USA</span><span class="sxs-lookup"><span data-stu-id="dd87a-139">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="dd87a-140">Europa Północna</span><span class="sxs-lookup"><span data-stu-id="dd87a-140">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="dd87a-141">Europa Zachodnia</span><span class="sxs-lookup"><span data-stu-id="dd87a-141">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

4. <span data-ttu-id="dd87a-142">Upewnij się, że pole **Identyfikator aplikacji** ma ustawioną wartość **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span><span class="sxs-lookup"><span data-stu-id="dd87a-142">Verify that the **Application Id** field is set to **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span> <span data-ttu-id="dd87a-143">Ta wartość jest stałą wartością.</span><span class="sxs-lookup"><span data-stu-id="dd87a-143">This value is a fixed value.</span></span>
5. <span data-ttu-id="dd87a-144">W polu **Identyfikator środowiska usługi LCS** wprowadź identyfikator środowiska LCS.</span><span class="sxs-lookup"><span data-stu-id="dd87a-144">In the **LCS Environment Id** field, enter the ID of your LCS environment.</span></span>
6. <span data-ttu-id="dd87a-145">Wybierz przycisk **Zapisz** i zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="dd87a-145">Select **Save**, and then close the page.</span></span>

## <a name="create-key-vault-references"></a><span data-ttu-id="dd87a-146">Tworzenie zasobu magazynu kluczy</span><span class="sxs-lookup"><span data-stu-id="dd87a-146">Create Key Vault references</span></span>

1. <span data-ttu-id="dd87a-147">Zaloguj się do swojego konta RCS.</span><span class="sxs-lookup"><span data-stu-id="dd87a-147">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="dd87a-148">Otwórz nowy obszar roboczy **Funkcje globalizacji**, a następnie w obszarze **Środowiska** wybierz kafelek **Faktury elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="dd87a-148">In the **Globalization feature** workspace, in the **Environment** section, select the **Electronic invoicing** tile.</span></span>
3. <span data-ttu-id="dd87a-149">Na stronie **Ustawienia środowiska**, w okienku akcji wybierz **Środowisko serwisu**, a następnie wybierz opcję **Parametry Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="dd87a-149">On the **Environment setups** page, on the action Pane, select **Service environment**, and then select **Key Vault parameters**.</span></span>
4. <span data-ttu-id="dd87a-150">Wybierz opcję **Nowy**, aby utworzyć klucz tajny referencji.</span><span class="sxs-lookup"><span data-stu-id="dd87a-150">Select **New** to create a key vault reference.</span></span>
5. <span data-ttu-id="dd87a-151">W polu **Nazwa** wprowadź nazwę wpisu tajnego magazynu kluczy referencji.</span><span class="sxs-lookup"><span data-stu-id="dd87a-151">In the **Name** field, enter the name of the key vault reference.</span></span> <span data-ttu-id="dd87a-152">W polu **Opis wprowadź** opis.</span><span class="sxs-lookup"><span data-stu-id="dd87a-152">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="dd87a-153">W polu **URI magazynu kluczy** wklej klucz tajny z Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="dd87a-153">In the **Key Vault URI** field, paste the key vault secret from Azure Key Vault.</span></span> <span data-ttu-id="dd87a-154">Aby uzyskać więcej informacji, przejrzyj temat [Utwórz konto magazynu Azure i magazyn kluczy](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="dd87a-154">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>
7. <span data-ttu-id="dd87a-155">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="dd87a-155">Select **Save**.</span></span>

## <a name="create-storage-account-secret"></a><span data-ttu-id="dd87a-156">Utwórz klucz tajny konta magazynu</span><span class="sxs-lookup"><span data-stu-id="dd87a-156">Create Storage account secret</span></span>

1. <span data-ttu-id="dd87a-157">Na stronie **Ustawienia środowiska**, w okienku akcji wybierz **Środowisko usługi** > **Parametry Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="dd87a-157">On the **Environment setups** page, on the Action Pane, select **Service environment** > **Key Vault parameters**.</span></span>
2. <span data-ttu-id="dd87a-158">Wybierz **Referencje wpisu tajnego** i w sekcji **Certyfikaty** wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="dd87a-158">Select a **Key Vault reference** and in the **Certificates** section, select **Add**.</span></span>
3. <span data-ttu-id="dd87a-159">W polu **Nazwa** wprowadź ten nazwę klucza tajnyego konta magazynu.</span><span class="sxs-lookup"><span data-stu-id="dd87a-159">In the **Name** field, enter the name of the storage account secret.</span></span> <span data-ttu-id="dd87a-160">Aby uzyskać więcej informacji, przejrzyj temat [Utwórz konto magazynu Azure i magazyn kluczy](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="dd87a-160">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>
4. <span data-ttu-id="dd87a-161">W polu **Opis wprowadź** opis.</span><span class="sxs-lookup"><span data-stu-id="dd87a-161">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="dd87a-162">W polu **Typ** wybierz **Wpis tajny**.</span><span class="sxs-lookup"><span data-stu-id="dd87a-162">In the **Type** field, select **Secret**.</span></span>
6. <span data-ttu-id="dd87a-163">Wybierz przycisk **Zapisz** i zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="dd87a-163">Select **Save**, and then close the page.</span></span>

## <a name="create-a-digital-certificate-secret"></a><span data-ttu-id="dd87a-164">Utwórz tajny kod certyfikatu cyfrowego</span><span class="sxs-lookup"><span data-stu-id="dd87a-164">Create a digital certificate secret</span></span>

1. <span data-ttu-id="dd87a-165">Na stronie **Ustawienia środowiska**, w okienku akcji wybierz **Środowisko serwisu**, a następnie wybierz opcję **Parametry Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="dd87a-165">On the **Environment setups** page, on the action Pane, select **Service environment** and then select **Key Vault parameters**.</span></span>
2. <span data-ttu-id="dd87a-166">Wybierz **Referencje wpisu tajnego** i w sekcji **Certyfikaty** wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="dd87a-166">Select a **Key Vault reference** and then in the **Certificates** section, select **Add**.</span></span>
3. <span data-ttu-id="dd87a-167">W polu **Nazwa** wprowadź ten nazwę klucza tajnego cyfrowego certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="dd87a-167">In the **Name** field, enter the name of the digital certificate secret.</span></span> <span data-ttu-id="dd87a-168">Aby uzyskać więcej informacji, przejrzyj temat [Utwórz konto magazynu Azure i magazyn kluczy](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="dd87a-168">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>
4. <span data-ttu-id="dd87a-169">W polu **Opis wprowadź** opis.</span><span class="sxs-lookup"><span data-stu-id="dd87a-169">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="dd87a-170">W polu **Typ** zaznacz opcję **Certyfikat**.</span><span class="sxs-lookup"><span data-stu-id="dd87a-170">In the **Type** field, select **Certificate**.</span></span>
6. <span data-ttu-id="dd87a-171">Wybierz przycisk **Zapisz** i zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="dd87a-171">Select **Save**, and then close the page.</span></span>

## <a name="create-a-service-environment"></a><span data-ttu-id="dd87a-172">Tworzenie środowiska usługi</span><span class="sxs-lookup"><span data-stu-id="dd87a-172">Create a service environment</span></span>

1. <span data-ttu-id="dd87a-173">Zaloguj się do swojego konta RCS.</span><span class="sxs-lookup"><span data-stu-id="dd87a-173">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="dd87a-174">Otwórz nowy obszar roboczy **Funkcje globalizacji**, a następnie w obszarze **Środowiska** wybierz kafelek **Faktury elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="dd87a-174">In the **Globalization feature** workspace, in the **Environment** section, select the **Electronic invoicing** tile.</span></span>
3. <span data-ttu-id="dd87a-175">Na stronie **Ustawienia środowiska** w okienku akcji wybierz pozycję **Środowisko usługi**.</span><span class="sxs-lookup"><span data-stu-id="dd87a-175">On the **Environment setups** page, on the Action Pane, select **Service environment**.</span></span>
4. <span data-ttu-id="dd87a-176">Wybierz pozycję **Nowy**, aby utworzyć nowe środowisko usługi.</span><span class="sxs-lookup"><span data-stu-id="dd87a-176">Select **New** to create a new service environment.</span></span>
5. <span data-ttu-id="dd87a-177">W polu **Nazwa** wprowadź nazwę środowiska e-fakturowania.</span><span class="sxs-lookup"><span data-stu-id="dd87a-177">In the **Name** field, enter the name of the e-Invoicing environment.</span></span> <span data-ttu-id="dd87a-178">W polu **Opis wprowadź** opis.</span><span class="sxs-lookup"><span data-stu-id="dd87a-178">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="dd87a-179">W polu **Tajny klucz tokenu sygnatury dostępu Współdzielonego magazynu** wybierz nazwę klucza tajnego konta magazynu, który musi być używany do uwierzytelniania dostępu do konta magazynu.</span><span class="sxs-lookup"><span data-stu-id="dd87a-179">In the **Storage SAS token secret** field, select the name of the storage account secret that must be used to authenticate access to the storage account.</span></span>
7. <span data-ttu-id="dd87a-180">W sekcji **Użytkownicy** wybierz opcję **Dodaj**, aby dodać użytkownika, który może przesyłać faktury elektroniczne za pośrednictwem środowiska, a także połączyć się z kontem magazynu.</span><span class="sxs-lookup"><span data-stu-id="dd87a-180">In the **Users** section, select **Add** to add a user who is allowed to submit electronic invoices through the environment and also connect to the storage account.</span></span>
8. <span data-ttu-id="dd87a-181">W polu **Identyfikator użytkownika** wprowadź alias użytkownika.</span><span class="sxs-lookup"><span data-stu-id="dd87a-181">In the **User ID** field, enter the alias of the user.</span></span> <span data-ttu-id="dd87a-182">W polu **Adres e-mail** wprowadź adres e-mail dla użytkownika.</span><span class="sxs-lookup"><span data-stu-id="dd87a-182">In the **Email** field, enter the user's email address.</span></span>
9. <span data-ttu-id="dd87a-183">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="dd87a-183">Select **Save**.</span></span>
10. <span data-ttu-id="dd87a-184">Jeśli faktury dotyczące Twojego kraju / regionu wymagają łańcucha certyfikatów do stosowania podpisów cyfrowych, w okienku Akcja wybierz **Parametry Key Vault**, a następnie wybierz **Łańcuch certyfikatów** i wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="dd87a-184">If your country/region-specific invoices require a chain of certificates to apply digital signatures, on the Action pane, select **Key Vault parameters**, then select **Chain of certificates**, and follow these steps:</span></span>
    1. <span data-ttu-id="dd87a-185">Wybierz pozycję **Nowy**, aby utworzyć łańcuch certyfikatów.</span><span class="sxs-lookup"><span data-stu-id="dd87a-185">Select **New** to create a chain of certificates.</span></span>
    2. <span data-ttu-id="dd87a-186">W polu **Nazwa** wprowadź nazwę łańcucha certyfikatów.</span><span class="sxs-lookup"><span data-stu-id="dd87a-186">In the **Name** field, enter the name of the chain of certificate.</span></span> <span data-ttu-id="dd87a-187">W polu **Opis wprowadź** opis.</span><span class="sxs-lookup"><span data-stu-id="dd87a-187">In the **Description** field, enter a description.</span></span>
    3. <span data-ttu-id="dd87a-188">W sekcji **Certyfikaty** wybierz pozycję **Dodaj**, aby dodać certyfikat do łańcucha.</span><span class="sxs-lookup"><span data-stu-id="dd87a-188">In the **Certificates** section, select **Add** to add a certificate to the chain.</span></span>
    4. <span data-ttu-id="dd87a-189">Przycisk **W górę** lub **W dół** umożliwia zmianę pozycji certyfikatu w łańcuchu.</span><span class="sxs-lookup"><span data-stu-id="dd87a-189">Use the **Up** or **Down** button to change the position of the certificate in the chain.</span></span>
    5. <span data-ttu-id="dd87a-190">Wybierz przycisk **Zapisz** i zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="dd87a-190">Select **Save**, and then close the page.</span></span>
    6. <span data-ttu-id="dd87a-191">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="dd87a-191">Close the page.</span></span>
11. <span data-ttu-id="dd87a-192">Na stronie **Środowisko usługi** w okienku akcji wybierz opcję **Publikuj**, aby opublikować środowisko w chmurze.</span><span class="sxs-lookup"><span data-stu-id="dd87a-192">On **Service environment** page, on the Action Pane, select **Publish** to publish the environment to the cloud.</span></span> <span data-ttu-id="dd87a-193">Wartość pola **Stan** jest zmieniana na **Opublikowana**.</span><span class="sxs-lookup"><span data-stu-id="dd87a-193">The value of the **Status** field is changed to **Published**.</span></span>

## <a name="create-a-connected-application"></a><span data-ttu-id="dd87a-194">Utwórz połączoną aplikację</span><span class="sxs-lookup"><span data-stu-id="dd87a-194">Create a connected application</span></span>

1. <span data-ttu-id="dd87a-195">Na stronie **Ustawienia środowiska** w okienku akcji wybierz pozycję **Połączone aplikacje**.</span><span class="sxs-lookup"><span data-stu-id="dd87a-195">On the **Environment setups** page, on the action Pane, select **Connected applications**.</span></span>
2. <span data-ttu-id="dd87a-196">Wybierz pozycję **Nowy**, aby utworzyć połączoną aplikację.</span><span class="sxs-lookup"><span data-stu-id="dd87a-196">Select **New** to create a connected application.</span></span>
3. <span data-ttu-id="dd87a-197">W polu **Nazwa** wprowadź nazwę aplikacji do połączenia.</span><span class="sxs-lookup"><span data-stu-id="dd87a-197">In the **Name** field, enter the name of the application to connect.</span></span>
4. <span data-ttu-id="dd87a-198">W polu **Aplikacja** wprowadź adres URL środowiska Finance and Supply Chain Management, aby nawiązać połączenie.</span><span class="sxs-lookup"><span data-stu-id="dd87a-198">In the **Application** field, enter the URL of the Finance and Supply Chain Management environment to connect.</span></span>
4. <span data-ttu-id="dd87a-199">W polu **Dzierżawca** wprowadź dzierżawcę Finance and Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="dd87a-199">In the **Tenant** field, enter the tenant of the Finance and Supply Chain Management environment.</span></span>
5. <span data-ttu-id="dd87a-200">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="dd87a-200">Select **Save**.</span></span>
6. <span data-ttu-id="dd87a-201">W okienku akcji wybierz opcję **Sprawdź połączenie**, aby przetestować połączenie ze środowiskiem.</span><span class="sxs-lookup"><span data-stu-id="dd87a-201">On the Action Pane, select **Check connection** to test the connection with the environment.</span></span> <span data-ttu-id="dd87a-202">Następnie zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="dd87a-202">Then close the page.</span></span>

## <a name="link-connected-applications-to-environments"></a><span data-ttu-id="dd87a-203">Połącz połączone aplikacje ze środowiskami</span><span class="sxs-lookup"><span data-stu-id="dd87a-203">Link connected applications to environments</span></span>

1. <span data-ttu-id="dd87a-204">Na stronie **Ustawienia środowiska** wybierz pozycję **Nowy**, aby przypisać połączoną aplikację do środowiska.</span><span class="sxs-lookup"><span data-stu-id="dd87a-204">On the **Environment setups** page, select **New** to assign a connected application to an environment.</span></span>
2. <span data-ttu-id="dd87a-205">W polu **Połączona aplikacja** wybierz połączoną aplikację.</span><span class="sxs-lookup"><span data-stu-id="dd87a-205">In the **Connected application** field, select a connected application.</span></span>
3. <span data-ttu-id="dd87a-206">W polu **Środowisko usługi** wybierz środowisko usługi.</span><span class="sxs-lookup"><span data-stu-id="dd87a-206">In the **Service environment** field, select a service environment.</span></span>
4. <span data-ttu-id="dd87a-207">Wybierz przycisk **Zapisz** i zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="dd87a-207">Select **Save**, and then close the page.</span></span>

## <a name="set-up-electronic-invoicing-integration-in-finance-and-supply-chain-management"></a><span data-ttu-id="dd87a-208">Skonfiguruj integrację Faktur elektronicznych w rozwiązaniach Finance lub Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="dd87a-208">Set up Electronic invoicing integration in Finance and Supply Chain Management</span></span>

### <a name="turn-on-the-electronic-invoicing-integration-feature"></a><span data-ttu-id="dd87a-209">Funkcja integracji faktur elektronicznych jest włączana za pośrednictwem terminów wyświetlania</span><span class="sxs-lookup"><span data-stu-id="dd87a-209">Turn on the Electronic invoicing integration feature</span></span>

1. <span data-ttu-id="dd87a-210">Zaloguj się do wystąpienia Finance lub Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="dd87a-210">Sign in to your Finance or Supply Chain Management instance.</span></span>
2. <span data-ttu-id="dd87a-211">W obszarze roboczym **Zarządzanie funkcjami** wyszukaj funkcję **Integracja elektronicznego fakturowania**.</span><span class="sxs-lookup"><span data-stu-id="dd87a-211">In the **Feature management** workspace, search for the **Electronic invoicing integration** feature.</span></span> <span data-ttu-id="dd87a-212">Jeśli ta funkcja nie jest wyświetlana na stronie, wybierz pozycję **Sprawdź, czy nie są aktualizacje**.</span><span class="sxs-lookup"><span data-stu-id="dd87a-212">If this feature doesn't appear on the page, select **Check for updates**.</span></span>
3. <span data-ttu-id="dd87a-213">Wybierz funkcję, a następnie wybierz **Wyłącz teraz**.</span><span class="sxs-lookup"><span data-stu-id="dd87a-213">Select the feature, and then select **Enable now**.</span></span>

### <a name="set-up-the-service-endpoint-url"></a><span data-ttu-id="dd87a-214">Konfigurowanie adresu URL punktu końcowego usługi</span><span class="sxs-lookup"><span data-stu-id="dd87a-214">Set up the service endpoint URL</span></span>

1. <span data-ttu-id="dd87a-215">Przejdź do **Administrowanie organizacją \> Konfiguracja \> Parametry dokumentu elektronicznego**.</span><span class="sxs-lookup"><span data-stu-id="dd87a-215">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="dd87a-216">Na karcie **Usługa przesyłania** w polu **Identyfikator URL punktu końcowego usługi** wprowadź odpowiedni punkt końcowy usługi dla geografii systemu Azure, tak jak pokazano w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="dd87a-216">On the **Submission service** tab, in the **Service endpoint URL** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="dd87a-217">Geografia platformy Datacenter Azure</span><span class="sxs-lookup"><span data-stu-id="dd87a-217">Datacenter Azure geography</span></span> | <span data-ttu-id="dd87a-218">Adres URL punktu końcowego usługi</span><span class="sxs-lookup"><span data-stu-id="dd87a-218">Service endpoint URL</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="dd87a-219">Wschodnie stany USA</span><span class="sxs-lookup"><span data-stu-id="dd87a-219">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="dd87a-220">Zachodnie stany USA</span><span class="sxs-lookup"><span data-stu-id="dd87a-220">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="dd87a-221">Europa Północna</span><span class="sxs-lookup"><span data-stu-id="dd87a-221">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="dd87a-222">Europa Zachodnia</span><span class="sxs-lookup"><span data-stu-id="dd87a-222">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

3. <span data-ttu-id="dd87a-223">W polu **Środowisko** wprowadź nazwę środowiska usługowego opublikowaną w Fakturowaniu elektronicznym.</span><span class="sxs-lookup"><span data-stu-id="dd87a-223">In the **Environment** field, enter the name of the service environment published in Electronic invoicing.</span></span>
4. <span data-ttu-id="dd87a-224">Wybierz przycisk **Zapisz** i zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="dd87a-224">Select **Save**, and then close the page.</span></span>

### <a name="enable-flighting-keys"></a><span data-ttu-id="dd87a-225">Włącz klucze lotów</span><span class="sxs-lookup"><span data-stu-id="dd87a-225">Enable Flighting keys</span></span>

<span data-ttu-id="dd87a-226">Włącz klucze lotów dla rozwiązania Microsoft Dynamics 365 Finance lub Microsoft Dynamics 365 Supply Chain Management w wersji 10.0.17 lub wcześniejszych.</span><span class="sxs-lookup"><span data-stu-id="dd87a-226">Enable Flight keys for  Microsoft Dynamics 365 Finance or  Microsoft Dynamics 365 Supply Chain Management versions 10.0.17 or earlier.</span></span> 
1. <span data-ttu-id="dd87a-227">Wykonaj następujące polecenie SQL:</span><span class="sxs-lookup"><span data-stu-id="dd87a-227">Execute the following SQL command:</span></span>

    <span data-ttu-id="dd87a-228">INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BusinessDocumentSubmissionServiceEnabled', 1)</span><span class="sxs-lookup"><span data-stu-id="dd87a-228">INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BusinessDocumentSubmissionServiceEnabled', 1)</span></span>
    
    <span data-ttu-id="dd87a-229">INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('ElectronicInvoicingServiceIntegrationFeature', 1)</span><span class="sxs-lookup"><span data-stu-id="dd87a-229">INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('ElectronicInvoicingServiceIntegrationFeature', 1)</span></span>

2. <span data-ttu-id="dd87a-230">Wykonaj polecenie IISreset dla wszystkich AOS.</span><span class="sxs-lookup"><span data-stu-id="dd87a-230">Perform an IISreset command for all AOS's.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
