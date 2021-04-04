---
title: Zacznij od administrowania usługą dodatkową dotyczącą fakturowania elektronicznego
description: W tym temacie opisano sposób rozpoczęcia pracy z dodatkiem Faktur elektronicznych.
author: gionoder
manager: AnnBe
ms.date: 03/12/2021
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
ms.openlocfilehash: 05b00380cec7511adad2467d3f252799a4aaee5c
ms.sourcegitcommit: 543772ee97efe215cf6f2ec6e092cc1568919f20
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/13/2021
ms.locfileid: "5592533"
---
# <a name="get-started-with-electronic-invoicing-add-on-service-administration"></a><span data-ttu-id="6d411-103">Zacznij od administrowania usługą dodatkową dotyczącą fakturowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="6d411-103">Get started with Electronic invoicing add-on service administration</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

## <a name="prerequisites"></a><span data-ttu-id="6d411-104">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="6d411-104">Prerequisites</span></span>

<span data-ttu-id="6d411-105">Przed wykonaniem procedur opisanych w tym temacie muszą być spełnione następujące wymagania wstępne:</span><span class="sxs-lookup"><span data-stu-id="6d411-105">Before you complete the procedures in this topic, the following prerequisites must be in place:</span></span>

- <span data-ttu-id="6d411-106">Musisz mieć dostęp do konta Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="6d411-106">You must have access to your Microsoft Dynamics Lifecycle Services (LCS) account.</span></span>
- <span data-ttu-id="6d411-107">Musisz mieć projekt usługi LCS z wersją 10.0.17 lub nowszą firmy Microsoft Dynamics 365 Finance i Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="6d411-107">You must have an LCS project that includes version 10.0.17 or later of Microsoft Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="6d411-108">Ponadto te aplikacje muszą zostać wdrożone w jednej z następujących lokalizacji geograficznych platformy Azure:</span><span class="sxs-lookup"><span data-stu-id="6d411-108">Additionally, these apps must be deployed in one of the following Azure geographies:</span></span>

    - <span data-ttu-id="6d411-109">Wschodnie stany USA</span><span class="sxs-lookup"><span data-stu-id="6d411-109">East US</span></span>
    - <span data-ttu-id="6d411-110">Zachodnie stany USA</span><span class="sxs-lookup"><span data-stu-id="6d411-110">West US</span></span>
    - <span data-ttu-id="6d411-111">Europa Północna</span><span class="sxs-lookup"><span data-stu-id="6d411-111">North EU</span></span>
    - <span data-ttu-id="6d411-112">Europa Zachodnia</span><span class="sxs-lookup"><span data-stu-id="6d411-112">West EU</span></span>

- <span data-ttu-id="6d411-113">Musisz mieć dostęp do swojego konta Dynamics 365 Regulatory Configuration Services (RCS).</span><span class="sxs-lookup"><span data-stu-id="6d411-113">You must have access to your Dynamics 365 Regulatory Configuration Services (RCS) account.</span></span>
- <span data-ttu-id="6d411-114">Musisz aktywować funkcję globalizacji dla swojego konta RCS w zarządzaniu funkcjami.</span><span class="sxs-lookup"><span data-stu-id="6d411-114">You must activate the Globalization feature for your RCS account in Feature management.</span></span> <span data-ttu-id="6d411-115">Aby uzyskać więcej informacji, zobacz [Regulatory Configuration Services (RCS) – funkcje globalizacji](rcs-globalization-feature.md).</span><span class="sxs-lookup"><span data-stu-id="6d411-115">For more information, see [Regulatory Configuration Services (RCS) - Globalization features](rcs-globalization-feature.md).</span></span>
- <span data-ttu-id="6d411-116">Musisz utworzyć magazyn kluczy i konto magazynu na platformie Azure.</span><span class="sxs-lookup"><span data-stu-id="6d411-116">You must create a key vault and a storage account in Azure.</span></span> <span data-ttu-id="6d411-117">Aby uzyskać więcej informacji, przejrzyj temat [Utwórz konto magazynu Azure i magazyn kluczy](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="6d411-117">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>

## <a name="install-the-add-on-for-microservices-in-lifecycle-services"></a><span data-ttu-id="6d411-118">Zainstaluj dodatek dla mikrousług w Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="6d411-118">Install the add-on for microservices in Lifecycle Services</span></span>

1. <span data-ttu-id="6d411-119">Zaloguj się do swojego konta LCS.</span><span class="sxs-lookup"><span data-stu-id="6d411-119">Sign in to your LCS account.</span></span>
2. <span data-ttu-id="6d411-120">Wybierz kafelek **Zarządzanie funkcjami w wersji zapoznawczej**.</span><span class="sxs-lookup"><span data-stu-id="6d411-120">Select the **Preview feature management** tile.</span></span>
3. <span data-ttu-id="6d411-121">W sekcji **Funkcje w publicznych wersjach zapoznawczych** wybierz **usługę fakturowania elektronicznego**.</span><span class="sxs-lookup"><span data-stu-id="6d411-121">In the **Public Preview Features** section, select **e-Invoicing service**.</span></span>
4. <span data-ttu-id="6d411-122">Sprawdź, czy w opcji **Funkcja wersji zapoznawczej włączona** jest ustawiona wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="6d411-122">Make sure that the **Preview feature enabled** option is set to **Yes**.</span></span>
5. <span data-ttu-id="6d411-123">Na pulpicie nawigacyjnym usługi LCS wybierz projekt wdrożenia usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="6d411-123">On your LCS dashboard, select your LCS deployment project.</span></span> <span data-ttu-id="6d411-124">Projekt usługi LCS musi być uruchomiony.</span><span class="sxs-lookup"><span data-stu-id="6d411-124">The LCS project must be running.</span></span>
7. <span data-ttu-id="6d411-125">Na karcie **Dodatki środowiska** wybierz opcję **Zainstaluj nowy dodatek**.</span><span class="sxs-lookup"><span data-stu-id="6d411-125">On the **Environment add-ins** tab, select **Install a new add-in**.</span></span>
8. <span data-ttu-id="6d411-126">Wybierz **usługi fakturowania elektronicznego** i w polu Identyfikator aplikacji usługi **AAD** wprowadź wartość **091c98b0-a1c9-4b02-b62c-7753395ccabe**.</span><span class="sxs-lookup"><span data-stu-id="6d411-126">Select **e-invoicing Services** and in the **AAD application ID** field, enter **091c98b0-a1c9-4b02-b62c-7753395ccabe**.</span></span> <span data-ttu-id="6d411-127">Ta wartość jest stałą wartością.</span><span class="sxs-lookup"><span data-stu-id="6d411-127">This is a fixed value.</span></span>
10. <span data-ttu-id="6d411-128">W polu **Identyfikator dzierżawy usługi AAD** wprowadź identyfikator dzierżawy konta subskrypcji systemu Azure.</span><span class="sxs-lookup"><span data-stu-id="6d411-128">In the **AAD tenant ID** field, enter the tenant ID of your Azure subscription account.</span></span>
11. <span data-ttu-id="6d411-129">Przejrzyj warunki, a następnie zaznacz pole wyboru.</span><span class="sxs-lookup"><span data-stu-id="6d411-129">Review the terms and conditions, and then select the check box.</span></span>
12. <span data-ttu-id="6d411-130">Wybierz **Zainstaluj**.</span><span class="sxs-lookup"><span data-stu-id="6d411-130">Select **Install**.</span></span>


## <a name="set-up-the-parameters-for-rcs-integration-with-the-electronic-invoicing-add-on"></a><span data-ttu-id="6d411-131">Skonfiguruj parametry RCS z dodatkiem Faktury elektroniczne</span><span class="sxs-lookup"><span data-stu-id="6d411-131">Set up the parameters for RCS integration with the Electronic invoicing add-on</span></span>

1. <span data-ttu-id="6d411-132">Zaloguj się do swojego konta RCS.</span><span class="sxs-lookup"><span data-stu-id="6d411-132">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="6d411-133">W module **Powiązane odnośniki**, w obszarze roboczym **Raportowanie elektroniczne** wybierz opcję **Parametry raportowania elektronicznego**.</span><span class="sxs-lookup"><span data-stu-id="6d411-133">In the **Electronic reporting** workspace, in the **Related links** section, select **Electronic reporting parameters**.</span></span>
3. <span data-ttu-id="6d411-134">Na karcie **Usługa fakturowania elektronicznego** w polu **Identyfikator URI punktu końcowego usługi** wprowadź odpowiedni punkt końcowy usługi dla geografii systemu Azure, tak jak pokazano w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="6d411-134">On the **e-Invoicing service** tab, in the **Service endpoint URI** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="6d411-135">Geografia platformy Datacenter Azure</span><span class="sxs-lookup"><span data-stu-id="6d411-135">Datacenter Azure geography</span></span> | <span data-ttu-id="6d411-136">Adres URI punktu końcowego usługi</span><span class="sxs-lookup"><span data-stu-id="6d411-136">Service endpoint URI</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="6d411-137">Wschodnie stany USA</span><span class="sxs-lookup"><span data-stu-id="6d411-137">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="6d411-138">Zachodnie stany USA</span><span class="sxs-lookup"><span data-stu-id="6d411-138">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="6d411-139">Europa Północna</span><span class="sxs-lookup"><span data-stu-id="6d411-139">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="6d411-140">Europa Zachodnia</span><span class="sxs-lookup"><span data-stu-id="6d411-140">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

4. <span data-ttu-id="6d411-141">Upewnij się, że pole **Identyfikator aplikacji** ma ustawioną wartość **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span><span class="sxs-lookup"><span data-stu-id="6d411-141">Verify that the **Application Id** field is set to **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span> <span data-ttu-id="6d411-142">Ta wartość jest stałą wartością.</span><span class="sxs-lookup"><span data-stu-id="6d411-142">This value is a fixed value.</span></span>
5. <span data-ttu-id="6d411-143">W polu **Identyfikator środowiska usługi LCS** wprowadź identyfikator konta subskrypcji LCS.</span><span class="sxs-lookup"><span data-stu-id="6d411-143">In the **LCS Environment Id** field, enter the ID of your LCS subscription account.</span></span>
6. <span data-ttu-id="6d411-144">Wybierz przycisk **Zapisz** i zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="6d411-144">Select **Save**, and then close the page.</span></span>

## <a name="create-key-vault-secret"></a><span data-ttu-id="6d411-145">Utwórz wpis tajny magazynu kluczy</span><span class="sxs-lookup"><span data-stu-id="6d411-145">Create Key Vault secret</span></span>

1. <span data-ttu-id="6d411-146">Zaloguj się do swojego konta RCS.</span><span class="sxs-lookup"><span data-stu-id="6d411-146">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="6d411-147">Otwórz nowy obszar roboczy **Funkcje globalizacji**, a następnie w obszarze **Środowiska** wybierz kafelek **Dodatek Faktury elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="6d411-147">In the **Globalization feature** workspace, in the **Environment** section, select the **Electronic invoicing add-on** tile.</span></span>
3. <span data-ttu-id="6d411-148">Na stronie **Ustawienia środowiska**, w okienku akcji wybierz **Środowisko serwisu**, a następnie wybierz opcję **Parametry Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="6d411-148">On the **Environment setups** page, on the action Pane, select **Service environment**, and then select **Key Vault parameters**.</span></span>
4. <span data-ttu-id="6d411-149">Wybierz opcję **Nowy**, aby utworzyć klucz tajny.</span><span class="sxs-lookup"><span data-stu-id="6d411-149">Select **New** to create a key vault secret.</span></span>
5. <span data-ttu-id="6d411-150">W polu **Nazwa** wprowadź nazwę wpisu tajnego magazynu kluczy.</span><span class="sxs-lookup"><span data-stu-id="6d411-150">In the **Name** field, enter the name of the key vault secret.</span></span> <span data-ttu-id="6d411-151">W polu **Opis wprowadź** opis.</span><span class="sxs-lookup"><span data-stu-id="6d411-151">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="6d411-152">W polu **URI magazynu kluczy** wklej klucz tajny z Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="6d411-152">In the **Key Vault URI** field, paste the secret from Azure Key Vault.</span></span>
7. <span data-ttu-id="6d411-153">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="6d411-153">Select **Save**.</span></span>

## <a name="create-storage-account-secret"></a><span data-ttu-id="6d411-154">Utwórz klucz tajny konta magazynu</span><span class="sxs-lookup"><span data-stu-id="6d411-154">Create Storage account secret</span></span>

1. <span data-ttu-id="6d411-155">Przejdź do **Administrowanie systemem** > **Ustawienia** > **Parametry Key Vault** i wybierz klucz tajny klucz.</span><span class="sxs-lookup"><span data-stu-id="6d411-155">Go to **System administration** > **Setup** > **Key Vault parameters**, and select a Key vault secret.</span></span>
2. <span data-ttu-id="6d411-156">W sekcji **Certyfikaty** wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="6d411-156">In the **Certificates** section, select **Add**.</span></span>
3. <span data-ttu-id="6d411-157">W polu **Nazwa** wprowadź nazwę tajnych kont magazynowania, a w polu **Opis** wprowadź opis.</span><span class="sxs-lookup"><span data-stu-id="6d411-157">In the **Name** field, enter the name of the storage account secret and in the **Description** field, enter a description.</span></span>
4. <span data-ttu-id="6d411-158">W polu **Typ** zaznacz opcję **Certyfikat**.</span><span class="sxs-lookup"><span data-stu-id="6d411-158">In the **Type** field, select **Certificate**.</span></span>
5. <span data-ttu-id="6d411-159">Wybierz przycisk **Zapisz** i zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="6d411-159">Select **Save**, and then close the page.</span></span>

## <a name="create-a-digital-certificate-secret"></a><span data-ttu-id="6d411-160">Utwórz tajny kod certyfikatu cyfrowego</span><span class="sxs-lookup"><span data-stu-id="6d411-160">Create a digital certificate secret</span></span>

1. <span data-ttu-id="6d411-161">Przejdź do **Administrowanie systemem** > **Ustawienia** > **Parametry Key Vault** i wybierz klucz tajny klucz.</span><span class="sxs-lookup"><span data-stu-id="6d411-161">Go to **System administration** > **Setup** > **Key Vault parameters**, and select a Key vault secret.</span></span>
2. <span data-ttu-id="6d411-162">W sekcji **Certyfikaty** wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="6d411-162">In the **Certificates** section, select **Add**.</span></span>
3. <span data-ttu-id="6d411-163">W polu **Nazwa** wprowadź nazwę tajnych certyfikatów wirtualnych, a w polu **Opis** wprowadź opis.</span><span class="sxs-lookup"><span data-stu-id="6d411-163">In the **Name** field, enter the name of the digital certificate secret and in the **Description** field, enter a description.</span></span>
4. <span data-ttu-id="6d411-164">W polu **Typ** zaznacz opcję **Certyfikat**.</span><span class="sxs-lookup"><span data-stu-id="6d411-164">In the **Type** field, select **Certificate**.</span></span>
5. <span data-ttu-id="6d411-165">Wybierz przycisk **Zapisz** i zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="6d411-165">Select **Save**, and then close the page.</span></span>

## <a name="create-an-electronic-invoicing-add-on-environment"></a><span data-ttu-id="6d411-166">Tworzenie środowiska dodatku Faktur elektronicznych</span><span class="sxs-lookup"><span data-stu-id="6d411-166">Create an Electronic invoicing add-on environment</span></span>

1. <span data-ttu-id="6d411-167">Zaloguj się do swojego konta RCS.</span><span class="sxs-lookup"><span data-stu-id="6d411-167">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="6d411-168">Otwórz nowy obszar roboczy **Funkcje globalizacji**, a następnie w obszarze **Środowiska** wybierz kafelek **Dodatek Faktury elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="6d411-168">In the **Globalization feature** workspace, in the **Environment** section, select the **Electronic invoicing add-on** tile.</span></span>

## <a name="create-a-service-environment"></a><span data-ttu-id="6d411-169">Tworzenie środowiska usługi</span><span class="sxs-lookup"><span data-stu-id="6d411-169">Create a service environment</span></span>

1. <span data-ttu-id="6d411-170">Na stronie **Ustawienia środowiska** w okienku akcji wybierz pozycję **Środowisko usługi**.</span><span class="sxs-lookup"><span data-stu-id="6d411-170">On the **Environment setups** page, on the Action Pane, select **Service environment**.</span></span>
2. <span data-ttu-id="6d411-171">Wybierz pozycję **Nowy**, aby utworzyć nowe środowisko usługi.</span><span class="sxs-lookup"><span data-stu-id="6d411-171">Select **New** to create a new service environment.</span></span>
3. <span data-ttu-id="6d411-172">W polu **Nazwa** wprowadź nazwę środowiska e-fakturowania.</span><span class="sxs-lookup"><span data-stu-id="6d411-172">In the **Name** field, enter the name of the e-Invoicing environment.</span></span> <span data-ttu-id="6d411-173">W polu **Opis wprowadź** opis.</span><span class="sxs-lookup"><span data-stu-id="6d411-173">In the **Description** field, enter a description.</span></span>
4. <span data-ttu-id="6d411-174">W polu **Tajny klucz tokenu sygnatury dostępu Współdzielonego magazynu** wybierz nazwę klucza tajnego konta magazynu, który musi być używany do uwierzytelniania dostępu do konta magazynu.</span><span class="sxs-lookup"><span data-stu-id="6d411-174">In the **Storage SAS token secret** field, select the name of the storage account secret that must be used to authenticate access to the storage account.</span></span>
5. <span data-ttu-id="6d411-175">W sekcji **Użytkownicy** wybierz opcję **Dodaj**, aby dodać użytkownika, który może przesyłać faktury elektroniczne za pośrednictwem środowiska, a także połączyć się z kontem magazynu.</span><span class="sxs-lookup"><span data-stu-id="6d411-175">In the **Users** section, select **Add** to add a user who is allowed to submit electronic invoices through the environment and also connect to the storage account.</span></span>
6. <span data-ttu-id="6d411-176">W polu **Identyfikator użytkownika** wprowadź alias użytkownika.</span><span class="sxs-lookup"><span data-stu-id="6d411-176">In the **User ID** field, enter the alias of the user.</span></span> <span data-ttu-id="6d411-177">W polu **Adres e-mail** wprowadź adres e-mail dla użytkownika.</span><span class="sxs-lookup"><span data-stu-id="6d411-177">In the **Email** field, enter the user's email address.</span></span>
7. <span data-ttu-id="6d411-178">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="6d411-178">Select **Save**.</span></span>
8. <span data-ttu-id="6d411-179">Jeśli faktury dotyczące Twojego kraju / regionu wymagają łańcucha certyfikatów do stosowania podpisów cyfrowych, w okienku Akcja wybierz **Parametry Key Vault**, a następnie wybierz **Łańcuch certyfikatów** i wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="6d411-179">If your country/region-specific invoices require a chain of certificates to apply digital signatures, on the Action pane, select **Key Vault parameters**, then select **Chain of certificates**, and follow these steps:</span></span>

    1. <span data-ttu-id="6d411-180">Wybierz pozycję **Nowy**, aby utworzyć łańcuch certyfikatów.</span><span class="sxs-lookup"><span data-stu-id="6d411-180">Select **New** to create a chain of certificates.</span></span>
    2. <span data-ttu-id="6d411-181">W polu **Nazwa** wprowadź nazwę łańcucha certyfikatów.</span><span class="sxs-lookup"><span data-stu-id="6d411-181">In the **Name** field, enter the name of the chain of certificate.</span></span> <span data-ttu-id="6d411-182">W polu **Opis wprowadź** opis.</span><span class="sxs-lookup"><span data-stu-id="6d411-182">In the **Description** field, enter a description.</span></span>
    3. <span data-ttu-id="6d411-183">W sekcji **Certyfikaty** wybierz pozycję **Dodaj**, aby dodać certyfikat do łańcucha.</span><span class="sxs-lookup"><span data-stu-id="6d411-183">In the **Certificates** section, select **Add** to add a certificate to the chain.</span></span>
    4. <span data-ttu-id="6d411-184">Przycisk **W górę** lub **W dół** umożliwia zmianę pozycji certyfikatu w łańcuchu.</span><span class="sxs-lookup"><span data-stu-id="6d411-184">Use the **Up** or **Down** button to change the position of the certificate in the chain.</span></span>
    5. <span data-ttu-id="6d411-185">Wybierz przycisk **Zapisz** i zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="6d411-185">Select **Save**, and then close the page.</span></span>
    6. <span data-ttu-id="6d411-186">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="6d411-186">Close the page.</span></span>
9. <span data-ttu-id="6d411-187">Na stronie **Środowisko usługi** w okienku akcji wybierz opcję **Publikuj**, aby opublikować środowisko w chmurze.</span><span class="sxs-lookup"><span data-stu-id="6d411-187">On **Service environment** page, on the Action Pane, select **Publish** to publish the environment to the cloud.</span></span> <span data-ttu-id="6d411-188">Wartość pola **Stan** jest zmieniana na **Opublikowana**.</span><span class="sxs-lookup"><span data-stu-id="6d411-188">The value of the **Status** field is changed to **Published**.</span></span>

## <a name="create-a-connected-application"></a><span data-ttu-id="6d411-189">Utwórz połączoną aplikację</span><span class="sxs-lookup"><span data-stu-id="6d411-189">Create a connected application</span></span>

1. <span data-ttu-id="6d411-190">Na stronie **Ustawienia środowiska** w okienku akcji wybierz pozycję **Połączone aplikacje**.</span><span class="sxs-lookup"><span data-stu-id="6d411-190">On the **Environment setups** page, on the action Pane, select **Connected applications**.</span></span>
2. <span data-ttu-id="6d411-191">Wybierz pozycję **Nowy**, aby utworzyć połączoną aplikację.</span><span class="sxs-lookup"><span data-stu-id="6d411-191">Select **New** to create a connected application.</span></span>
3. <span data-ttu-id="6d411-192">W polu **Nazwa** wprowadź nazwę aplikacji do połączenia.</span><span class="sxs-lookup"><span data-stu-id="6d411-192">In the **Name** field, enter the name of the application to connect.</span></span>
4. <span data-ttu-id="6d411-193">W polu **Aplikacja** wprowadź adres URL środowiska Finance and Supply Chain Management, aby nawiązać połączenie.</span><span class="sxs-lookup"><span data-stu-id="6d411-193">In the **Application** field, enter the URL of the Finance and Supply Chain Management environment to connect.</span></span>
4. <span data-ttu-id="6d411-194">W polu **Dzierżawca** wprowadź dzierżawcę Finance and Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="6d411-194">In the **Tenant** field, enter the tenant of the Finance and Supply Chain Management environment.</span></span>
5. <span data-ttu-id="6d411-195">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="6d411-195">Select **Save**.</span></span>
6. <span data-ttu-id="6d411-196">W okienku akcji wybierz opcję **Sprawdź połączenie**, aby przetestować połączenie ze środowiskiem.</span><span class="sxs-lookup"><span data-stu-id="6d411-196">On the Action Pane, select **Check connection** to test the connection with the environment.</span></span> <span data-ttu-id="6d411-197">Następnie zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="6d411-197">Then close the page.</span></span>

## <a name="link-connected-applications-to-environments"></a><span data-ttu-id="6d411-198">Połącz połączone aplikacje ze środowiskami</span><span class="sxs-lookup"><span data-stu-id="6d411-198">Link connected applications to environments</span></span>

1. <span data-ttu-id="6d411-199">Na stronie **Ustawienia środowiska** wybierz pozycję **Nowy**, aby przypisać połączoną aplikację do środowiska.</span><span class="sxs-lookup"><span data-stu-id="6d411-199">On the **Environment setups** page, select **New** to assign a connected application to an environment.</span></span>
2. <span data-ttu-id="6d411-200">W polu **Połączona aplikacja** wybierz połączoną aplikację.</span><span class="sxs-lookup"><span data-stu-id="6d411-200">In the **Connected application** field, select a connected application.</span></span>
3. <span data-ttu-id="6d411-201">W polu **Środowisko usługi** wybierz środowisko usługi.</span><span class="sxs-lookup"><span data-stu-id="6d411-201">In the **Service environment** field, select a service environment.</span></span>
4. <span data-ttu-id="6d411-202">Wybierz przycisk **Zapisz** i zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="6d411-202">Select **Save**, and then close the page.</span></span>

## <a name="set-up-the-electronic-invoicing-add-on-integration-in-finance-and-supply-chain-management"></a><span data-ttu-id="6d411-203">Skonfiguruj integrację dodatku Faktur elektronicznych w rozwiązaniach Finance i Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="6d411-203">Set up the Electronic invoicing add-on integration in Finance and Supply Chain Management</span></span>

### <a name="turn-on-the-electronic-invoicing-add-on-integration-feature"></a><span data-ttu-id="6d411-204">Funkcja integracji faktur elektronicznych jest włączana za pośrednictwem terminów wyświetlania</span><span class="sxs-lookup"><span data-stu-id="6d411-204">Turn on the Electronic invoicing add-on integration feature</span></span>

1. <span data-ttu-id="6d411-205">Zaloguj się do wystąpienia Finance lub Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="6d411-205">Sign in to your Finance or Supply Chain Management instance.</span></span>
2. <span data-ttu-id="6d411-206">W obszarze roboczym **Zarządzanie funkcjami** wyszukaj funkcję **Integracja dodatku do elektronicznego fakturowania**.</span><span class="sxs-lookup"><span data-stu-id="6d411-206">In the **Feature management** workspace, search for the **Electronic invoicing add-on integration** feature.</span></span> <span data-ttu-id="6d411-207">Jeśli ta funkcja nie jest wyświetlana na stronie, wybierz pozycję **Sprawdź, czy nie są aktualizacje**.</span><span class="sxs-lookup"><span data-stu-id="6d411-207">If this feature doesn't appear on the page, select **Check for updates**.</span></span>
3. <span data-ttu-id="6d411-208">Wybierz funkcję, a następnie wybierz **Wyłącz teraz**.</span><span class="sxs-lookup"><span data-stu-id="6d411-208">Select the feature, and then select **Enable now**.</span></span>

### <a name="set-up-the-service-endpoint-url"></a><span data-ttu-id="6d411-209">Konfigurowanie adresu URL punktu końcowego usługi</span><span class="sxs-lookup"><span data-stu-id="6d411-209">Set up the service endpoint URL</span></span>

1. <span data-ttu-id="6d411-210">Przejdź do **Administrowanie organizacją \> Konfiguracja \> Parametry dokumentu elektronicznego**.</span><span class="sxs-lookup"><span data-stu-id="6d411-210">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="6d411-211">Na karcie **Usługa przesyłania** w polu **Identyfikator URL punktu końcowego usługi** wprowadź odpowiedni punkt końcowy usługi dla geografii systemu Azure, tak jak pokazano w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="6d411-211">On the **Submission service** tab, in the **Service endpoint URL** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="6d411-212">Geografia platformy Datacenter Azure</span><span class="sxs-lookup"><span data-stu-id="6d411-212">Datacenter Azure geography</span></span> | <span data-ttu-id="6d411-213">Adres URL punktu końcowego usługi</span><span class="sxs-lookup"><span data-stu-id="6d411-213">Service endpoint URL</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="6d411-214">Wschodnie stany USA</span><span class="sxs-lookup"><span data-stu-id="6d411-214">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="6d411-215">Zachodnie stany USA</span><span class="sxs-lookup"><span data-stu-id="6d411-215">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="6d411-216">Europa Północna</span><span class="sxs-lookup"><span data-stu-id="6d411-216">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="6d411-217">Europa Zachodnia</span><span class="sxs-lookup"><span data-stu-id="6d411-217">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

3. <span data-ttu-id="6d411-218">W polu **Środowisko** wprowadź nazwę środowiska dodatkowego fakturowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="6d411-218">In the **Environment** field, enter the name of the Electronic invoicing add-on environment.</span></span>
4. <span data-ttu-id="6d411-219">Wybierz przycisk **Zapisz** i zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="6d411-219">Select **Save**, and then close the page.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
