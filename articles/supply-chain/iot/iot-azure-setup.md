---
title: Konfigurowanie zasobów platformy Azure dla analizy Internetu rzeczy (IoT)
description: W tym temacie opisano sposób tworzenia i konfigurowania zasobów platformy Microsoft Azure potrzebnych do przeprowadzania analizy Internetu rzeczy (IoT).
author: ''
manager: tfehr
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: ''
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ea1083a65efb25699b9237c72c081f50e1fb476c
ms.sourcegitcommit: 5bb36b74935ffe140367fd6ecf956b4857ad12e5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/14/2020
ms.locfileid: "3802780"
---
# <a name="set-up-azure-resources-for-iot-intelligence"></a><span data-ttu-id="fd5cf-103">Konfigurowanie zasobów platformy Azure dla analizy Internetu rzeczy (IoT)</span><span class="sxs-lookup"><span data-stu-id="fd5cf-103">Set up Azure resources for IoT Intelligence</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fd5cf-104">W tym temacie opisano sposób tworzenia i konfigurowania zasobów platformy Microsoft Azure potrzebnych do przeprowadzania analizy Internetu rzeczy (IoT).</span><span class="sxs-lookup"><span data-stu-id="fd5cf-104">This topic explains how to create and configure the Microsoft Azure resources that you require for IoT Intelligence.</span></span>

## <a name="create-azure-resources"></a><span data-ttu-id="fd5cf-105">Tworzenie zasobów platformy Azure</span><span class="sxs-lookup"><span data-stu-id="fd5cf-105">Create Azure resources</span></span>

<span data-ttu-id="fd5cf-106">Aby utworzyć centrum IoT, pamięć podręczną Redis i magazyn kluczy, do których można uzyskać dostęp z poziomu aplikacji Microsoft Dynamics 365 Supply Chain Management, wykonaj poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-106">Follow these steps to create an IoT hub, a Redis cache, and a key vault that can be accessed by Microsoft Dynamics 365 Supply Chain Management.</span></span>

### <a name="verify-that-the-microsoft-dynamics-erp-microservices-first-party-app-id-is-in-your-tenant"></a><span data-ttu-id="fd5cf-107">Sprawdź, czy identyfikator naszej aplikacji mikrousług Microsoft Dynamics ERP znajduje się w Twojej dzierżawie</span><span class="sxs-lookup"><span data-stu-id="fd5cf-107">Verify that the Microsoft Dynamics ERP Microservices first-party app ID is in your tenant</span></span>

<span data-ttu-id="fd5cf-108">Aby sprawdzić, czy identyfikator naszej aplikacji mikrousług Microsoft Dynamics ERP znajduje się w Twojej dzierżawie, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-108">To verify that the app ID for the Microsoft Dynamics ERP Microservices first-party app is in your tenant, follow these steps.</span></span>

1. <span data-ttu-id="fd5cf-109">Zaloguj się do portalu Azure pod adresem <https://portal.azure.com>.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-109">Sign in to the Azure portal at <https://portal.azure.com>.</span></span>
2. <span data-ttu-id="fd5cf-110">Przejdź do **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-110">Go to **Azure Active Directory**.</span></span>
3. <span data-ttu-id="fd5cf-111">Przejdź do obszaru **Aplikacje dla przedsiębiorstw**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-111">Go to **Enterprise applications**.</span></span>
4. <span data-ttu-id="fd5cf-112">W polu **Typ aplikacji** wybierz pozycję **Aplikacje firmy Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-112">In the **Application type** field, select **Microsoft applications**.</span></span>
5. <span data-ttu-id="fd5cf-113">W polu wyszukiwania wprowadź **Mikrousługi Microsoft Dynamics ERP**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-113">In the search field, enter **Microsoft Dynamics ERP Microservices**.</span></span>
6. <span data-ttu-id="fd5cf-114">Sprawdź, czy pozycja **Mikrousługi Microsoft Dynamics ERP** znajduje się na liście.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-114">Verify that **Microsoft Dynamics ERP Microservices** is in the list.</span></span> <span data-ttu-id="fd5cf-115">Inne aplikacje mają podobne nazwy.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-115">Other applications have similar names.</span></span> <span data-ttu-id="fd5cf-116">Dlatego upewnij się, że znaleziona aplikacja jest prawidłowa.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-116">Therefore, make sure that you find the correct application.</span></span> <span data-ttu-id="fd5cf-117">Identyfikator aplikacji to **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-117">The app ID is **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span>

    <span data-ttu-id="fd5cf-118">Jeśli aplikacji nie ma na liście, musisz ją dodać do dzierżawy:</span><span class="sxs-lookup"><span data-stu-id="fd5cf-118">If the application isn't in the list, you must add it to your tenant:</span></span>

    1. <span data-ttu-id="fd5cf-119">W witrynie Azure Portal kliknij na pasku narzędzi przycisk, aby otworzyć usługę Azure Cloud Shell.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-119">In the Azure portal, on the toolbar, select the button to open Azure Cloud Shell.</span></span>
    2. <span data-ttu-id="fd5cf-120">Uruchom polecenie **Install-Module AzureAD**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-120">Run the command **Install-Module AzureAD**.</span></span> <span data-ttu-id="fd5cf-121">Wprowadź wartość **Y**, aby zainstalować moduł.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-121">Enter **Y** to install the module.</span></span>
    3. <span data-ttu-id="fd5cf-122">Uruchom polecenie **Get-InstalledModule -Name "AzureAD"**, aby sprawdzić, czy moduł został zainstalowany.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-122">Run the command **Get-InstalledModule -Name "AzureAD"** to verify that the module is installed.</span></span>
    4. <span data-ttu-id="fd5cf-123">Uruchom polecenie **Connect-AzureAD -Confirm**, aby uruchomić uwierzytelnianie.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-123">Run the command **Connect-AzureAD -Confirm** to run the authentication.</span></span>
    5. <span data-ttu-id="fd5cf-124">Uruchom polecenie **New-AzureADServicePrincipal -AppId 0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-124">Run the command **New-AzureADServicePrincipal -AppId 0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span>

    <span data-ttu-id="fd5cf-125">Teraz możesz powtórzyć kroki od 1 do 6, aby sprawdzić, czy identyfikator aplikacji znajduje się w dzierżawie.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-125">You can now repeat steps 1 through 6 to verify that the app ID is in your tenant.</span></span>

### <a name="create-a-key-vault-resource"></a><span data-ttu-id="fd5cf-126">Tworzenie zasobu magazynu kluczy</span><span class="sxs-lookup"><span data-stu-id="fd5cf-126">Create a key vault resource</span></span>

<span data-ttu-id="fd5cf-127">Aby utworzyć zasób magazynu kluczy, wykonaj poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-127">To create a key vault resource, follow these steps.</span></span>

1. <span data-ttu-id="fd5cf-128">W witrynie Azure Portal utwórz grupę zasobów lub przejdź do niej.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-128">In the Azure portal, create or go to a resource group.</span></span>
2. <span data-ttu-id="fd5cf-129">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-129">Select **Add**.</span></span>
3. <span data-ttu-id="fd5cf-130">Na stronie **Nowy** w polu wyszukiwania wprowadź ciąg **Magazyn kluczy**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-130">On the **New** page, in the search field, enter **Key vault**.</span></span> <span data-ttu-id="fd5cf-131">Następnie wybierz opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-131">Then select **Create**.</span></span>
4. <span data-ttu-id="fd5cf-132">Na stronie **Tworzenie magazynu kluczy** w polu **Nazwa magazynu kluczy** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-132">On the **Create key vault** page, in the **Key vault name** field, enter a name.</span></span>
5. <span data-ttu-id="fd5cf-133">Przejrzyj wartości domyślne, a następnie wybierz pozycję **Przegląd + tworzenie**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-133">Review the default values, and then select **Review + create**.</span></span>
6. <span data-ttu-id="fd5cf-134">Wybierz opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-134">Select **Create**.</span></span>

<span data-ttu-id="fd5cf-135">Magazyn kluczy jest tworzony w tle.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-135">The key vault is created in the background.</span></span>

### <a name="create-an-iot-hub-resource"></a><span data-ttu-id="fd5cf-136">Tworzenie zasobu centrum IoT</span><span class="sxs-lookup"><span data-stu-id="fd5cf-136">Create an IoT hub resource</span></span>

<span data-ttu-id="fd5cf-137">Aby utworzyć zasób centrum IoT, wykonaj poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-137">To create an IoT hub resource, follow these steps.</span></span>

1. <span data-ttu-id="fd5cf-138">Wybierz grupę zasobów lub przejdź do niej.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-138">Create or go to a resource group.</span></span>
2. <span data-ttu-id="fd5cf-139">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-139">Select **Add**.</span></span>
3. <span data-ttu-id="fd5cf-140">Na stronie **Nowy** w polu wyszukiwania wprowadź ciąg **Centrum IoT**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-140">On the **New** page, in the search field, enter **Iot Hub**.</span></span> <span data-ttu-id="fd5cf-141">Następnie wybierz opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-141">Then select **Create**.</span></span>
4. <span data-ttu-id="fd5cf-142">W polu **Nazwa centrum IoT** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-142">In the **IoT hub name** field, enter a name.</span></span>
5. <span data-ttu-id="fd5cf-143">Przejrzyj wartości domyślne, a następnie wybierz pozycję **Przegląd + tworzenie**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-143">Review the default values, and then select **Review + create**.</span></span>
6. <span data-ttu-id="fd5cf-144">Wybierz opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-144">Select **Create**.</span></span>

<span data-ttu-id="fd5cf-145">Centrum IoT jest tworzone w tle.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-145">The IoT hub is created in the background.</span></span>

> [!NOTE]
> <span data-ttu-id="fd5cf-146">Zalecamy, aby dla każdego środowiska utworzyć tylko jeden zasób typu centrum IoT.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-146">We recommend that you create only one IoT hub resource per environment.</span></span>

### <a name="create-a-redis-cache-resource"></a><span data-ttu-id="fd5cf-147">Tworzenie zasobu pamięci podręcznej Redis</span><span class="sxs-lookup"><span data-stu-id="fd5cf-147">Create a Redis cache resource</span></span>

<span data-ttu-id="fd5cf-148">Aby utworzyć zasób pamięci podręcznej Redis, wykonaj poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-148">To create a Redis cache resource, follow these steps.</span></span>

1. <span data-ttu-id="fd5cf-149">Wybierz grupę zasobów lub przejdź do niej.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-149">Create or go to a resource group.</span></span>
2. <span data-ttu-id="fd5cf-150">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-150">Select **Add**.</span></span>
3. <span data-ttu-id="fd5cf-151">Na stronie **Nowy** w polu wyszukiwania wprowadź ciąg **Azure Cache for Redis**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-151">On the **New** page, in the search field, enter **Azure Cache for Redis**.</span></span> <span data-ttu-id="fd5cf-152">Następnie wybierz opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-152">Then select **Create**.</span></span>
4. <span data-ttu-id="fd5cf-153">W polu **Nazwa DNS** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-153">In the **DNS name** field, enter a name.</span></span>
5. <span data-ttu-id="fd5cf-154">Przejrzyj wartości domyślne, a następnie wybierz pozycję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-154">Review the default values, and then select **Create**.</span></span>

<span data-ttu-id="fd5cf-155">Pamięć podręczna Redis jest tworzona w tle.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-155">The Redis cache is created in the background.</span></span>

> [!NOTE]
> <span data-ttu-id="fd5cf-156">Zalecamy, aby dla każdego środowiska utworzyć tylko jedną pamięć podręczną Redis.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-156">We recommend that you create only one Redis cache per environment.</span></span>

<span data-ttu-id="fd5cf-157">Wszystkie zasoby zostały teraz utworzone.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-157">All the resources have now been created.</span></span>

## <a name="configure-the-azure-resources"></a><span data-ttu-id="fd5cf-158">Konfigurowanie zasobów platformy Azure</span><span class="sxs-lookup"><span data-stu-id="fd5cf-158">Configure the Azure resources</span></span>

### <a name="configure-the-iot-hub"></a><span data-ttu-id="fd5cf-159">Konfigurowanie centrum IoT</span><span class="sxs-lookup"><span data-stu-id="fd5cf-159">Configure the IoT hub</span></span>

<span data-ttu-id="fd5cf-160">Aby skonfigurować centrum IoT, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-160">To configure the IoT hub, follow these steps.</span></span>

1. <span data-ttu-id="fd5cf-161">W obszarze zasobów wybierz zasób Centrum IoT.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-161">In your resources, select the IoT hub resource.</span></span>
2. <span data-ttu-id="fd5cf-162">W lewym okienku nawigacji wybierz pozycję **Wbudowane punkty końcowe**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-162">In the left navigation pane, select **Built-in endpoints**.</span></span>
3. <span data-ttu-id="fd5cf-163">W obszarze **Grupy konsumentów** wklej następujące grupy konsumentów:</span><span class="sxs-lookup"><span data-stu-id="fd5cf-163">Under **Consumer groups**, paste the following consumer groups.</span></span> <span data-ttu-id="fd5cf-164">Te grupy odbiorców odpowiadają gotowym scenariuszom.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-164">These consumer groups correspond to the out-of-box scenarios.</span></span>

    + <span data-ttu-id="fd5cf-165">microsoft.dynamics.iotintelligence-1</span><span class="sxs-lookup"><span data-stu-id="fd5cf-165">microsoft.dynamics.iotintelligence-1</span></span>
    + <span data-ttu-id="fd5cf-166">microsoft.dynamics.iotintelligence-2</span><span class="sxs-lookup"><span data-stu-id="fd5cf-166">microsoft.dynamics.iotintelligence-2</span></span>
    + <span data-ttu-id="fd5cf-167">microsoft.dynamics.iotintelligence-3</span><span class="sxs-lookup"><span data-stu-id="fd5cf-167">microsoft.dynamics.iotintelligence-3</span></span>

### <a name="configure-the-key-vault"></a><span data-ttu-id="fd5cf-168">Konfigurowanie magazynu kluczy</span><span class="sxs-lookup"><span data-stu-id="fd5cf-168">Configure the key vault</span></span>

<span data-ttu-id="fd5cf-169">Aby skonfigurować magazyn kluczy, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-169">To configure the key vault, follow these steps.</span></span>

1. <span data-ttu-id="fd5cf-170">W obszarze zasobów wybierz zasób Magazyn kluczy.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-170">In your resources, select the key vault resource.</span></span>
2. <span data-ttu-id="fd5cf-171">W okienku nawigacji po lewej stronie wybierz pozycję **Zasady dostępu**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-171">In the left navigation pane, select **Access policies**.</span></span>
3. <span data-ttu-id="fd5cf-172">Wybierz pozycję **Dodaj zasady dostępu**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-172">Select **Add an access policy**.</span></span>
4. <span data-ttu-id="fd5cf-173">Na stronie **Dodawanie zasad dostępu** w polu **Uprawnienia klucza tajnego** wybierz pozycję **Pobieranie** i **Tworzenie listy**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-173">On the **Add access policy** page, in the **Secret permissions** field, select **Get** and **List**.</span></span>
5. <span data-ttu-id="fd5cf-174">Kliknij w obszarze **Wybierz podmiot zabezpieczeń**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-174">Click in the **Select principal**.</span></span>
6. <span data-ttu-id="fd5cf-175">W oknie dialogowym **Podmiot zabezpieczeń** wyszukaj i wybierz pozycję **Mikrousługi Microsoft Dynamics ERP**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-175">In the **Principal** dialog box, search for and select **Microsoft Dynamics ERP Microservices**.</span></span> <span data-ttu-id="fd5cf-176">Następnie wybierz pozycję **Wybierz**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-176">Then select **Select**.</span></span>
7. <span data-ttu-id="fd5cf-177">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-177">Select **Add**.</span></span>
8. <span data-ttu-id="fd5cf-178">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-178">Select **Save**.</span></span>

<span data-ttu-id="fd5cf-179">Aplikacja ma teraz dostęp do kluczy tajnych w magazynie kluczy.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-179">The app now has access to the secrets in the key vault.</span></span>

### <a name="save-the-iot-hub-connection-string-secret"></a><span data-ttu-id="fd5cf-180">Zapisywanie klucza tajnego parametrów połączenia centrum IoT</span><span class="sxs-lookup"><span data-stu-id="fd5cf-180">Save the IoT hub connection string secret</span></span>

<span data-ttu-id="fd5cf-181">Aby zapisać klucz tajny dla parametrów połączenia centrum IoT, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-181">To save the secret for the IoT hub connection string, follow these steps.</span></span>

1. <span data-ttu-id="fd5cf-182">W obszarze zasobów wybierz zasób Centrum IoT.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-182">In your resources, select the IoT hub resource.</span></span>
2. <span data-ttu-id="fd5cf-183">W lewym okienku nawigacji wybierz pozycję **Wbudowane punkty końcowe**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-183">In the left navigation pane, select **Built-in endpoints**.</span></span>
3. <span data-ttu-id="fd5cf-184">Skopiuj wartość w polu **Punkt końcowy zgodny z centrum zdarzeń**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-184">Copy the value in the **Event Hub-compatible endpoint** field.</span></span>
4. <span data-ttu-id="fd5cf-185">Przejdź do zasobu magazynu kluczy.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-185">Go to the key vault resource.</span></span>
5. <span data-ttu-id="fd5cf-186">W okienku nawigacji po lewej stronie wybierz pozycję **Wpisy tajne**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-186">In the left navigation pane, select **Secrets**.</span></span>
6. <span data-ttu-id="fd5cf-187">Wybierz pozycję **Generuj/importuj**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-187">Select **Generate/Import**.</span></span>
7. <span data-ttu-id="fd5cf-188">W polu **Nazwa** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-188">In the **Name** field, enter a name.</span></span>
8. <span data-ttu-id="fd5cf-189">W polu **Wartość** wklej wcześniej skopiowaną wartość punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-189">In the **Value** field, paste the endpoint value that you copied earlier.</span></span>
9. <span data-ttu-id="fd5cf-190">Wybierz opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-190">Select **Create**.</span></span>

### <a name="save-the-redis-cache-connection-string-secret"></a><span data-ttu-id="fd5cf-191">Zapisywanie klucza tajnego parametrów połączenia pamięci podręcznej Redis</span><span class="sxs-lookup"><span data-stu-id="fd5cf-191">Save the Redis cache connection string secret</span></span>

<span data-ttu-id="fd5cf-192">Aby zapisać klucz tajny dla parametrów połączenia pamięci podręcznej Redis, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-192">To save the secret for the Redis cache connection string, follow these steps.</span></span>

1. <span data-ttu-id="fd5cf-193">W obszarze zasobów wybierz zasób pamięci podręcznej Redis.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-193">In your resources, select the Redis cache resource.</span></span>
2. <span data-ttu-id="fd5cf-194">Wybierz pozycję **Klucze dostępu**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-194">Select **Access keys**.</span></span>
3. <span data-ttu-id="fd5cf-195">Skopiuj wartość w polu **Podstawowe parametry połączenia**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-195">Copy the value in the **Primary connection string** field.</span></span>
4. <span data-ttu-id="fd5cf-196">Przejdź do zasobu magazynu kluczy.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-196">Go to the key vault resource.</span></span>
5. <span data-ttu-id="fd5cf-197">W okienku nawigacji po lewej stronie wybierz pozycję **Wpisy tajne**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-197">In the left navigation pane, select **Secrets**.</span></span>
6. <span data-ttu-id="fd5cf-198">Wybierz pozycję **Generuj/importuj**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-198">Select **Generate/Import**.</span></span>
7. <span data-ttu-id="fd5cf-199">W polu **Nazwa** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-199">In the **Name** field, enter a name.</span></span>
8. <span data-ttu-id="fd5cf-200">W polu **Wartość** wklej wcześniej skopiowane parametry połączenia.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-200">In the **Value** field, paste the connection string that you copied earlier.</span></span>
9. <span data-ttu-id="fd5cf-201">Wybierz opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-201">Select **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="fd5cf-202">Za każdym razem, gdy parametry połączenia są aktualizowane, musisz również zaktualizować wartości kluczy tajnych.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-202">Whenever you update one of the connection strings, you must also update the secret values.</span></span>

<span data-ttu-id="fd5cf-203">Aprowizowanie wymaganych zasobów platformy Azure zostało zakończone.</span><span class="sxs-lookup"><span data-stu-id="fd5cf-203">You've now finished provisioning the required Azure resources.</span></span> <span data-ttu-id="fd5cf-204">Następny krok to [zainstalowanie dodatku analizy Internetu rzeczy (IoT) w usługach Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="fd5cf-204">The next step is to [install the IoT Intelligence add-in in Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md).</span></span>
