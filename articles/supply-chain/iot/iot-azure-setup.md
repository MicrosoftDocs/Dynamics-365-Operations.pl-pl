---
title: Konfigurowanie zasobów platformy Azure dla analizy Internetu rzeczy (IoT)
description: W tym temacie opisano sposób tworzenia i konfigurowania zasobów platformy Microsoft Azure potrzebnych do przeprowadzania analizy Internetu rzeczy (IoT).
author: robinarh
manager: tfehr
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: ''
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: cd06410dd6260e6a371b0044546be7f8c9957c80
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4989828"
---
# <a name="set-up-azure-resources-for-iot-intelligence"></a><span data-ttu-id="bbfec-103">Konfigurowanie zasobów platformy Azure dla analizy Internetu rzeczy (IoT)</span><span class="sxs-lookup"><span data-stu-id="bbfec-103">Set up Azure resources for IoT Intelligence</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bbfec-104">W tym temacie opisano sposób tworzenia i konfigurowania zasobów platformy Microsoft Azure potrzebnych do przeprowadzania analizy Internetu rzeczy (IoT).</span><span class="sxs-lookup"><span data-stu-id="bbfec-104">This topic explains how to create and configure the Microsoft Azure resources that you require for IoT Intelligence.</span></span>

## <a name="create-azure-resources"></a><span data-ttu-id="bbfec-105">Tworzenie zasobów platformy Azure</span><span class="sxs-lookup"><span data-stu-id="bbfec-105">Create Azure resources</span></span>

<span data-ttu-id="bbfec-106">Aby utworzyć centrum IoT, pamięć podręczną Redis i magazyn kluczy, do których można uzyskać dostęp z poziomu aplikacji Microsoft Dynamics 365 Supply Chain Management, wykonaj poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="bbfec-106">Follow these steps to create an IoT hub, a Redis cache, and a key vault that can be accessed by Microsoft Dynamics 365 Supply Chain Management.</span></span>

### <a name="verify-that-the-microsoft-dynamics-erp-microservices-first-party-app-id-is-in-your-tenant"></a><span data-ttu-id="bbfec-107">Sprawdź, czy identyfikator naszej aplikacji mikrousług Microsoft Dynamics ERP znajduje się w Twojej dzierżawie</span><span class="sxs-lookup"><span data-stu-id="bbfec-107">Verify that the Microsoft Dynamics ERP Microservices first-party app ID is in your tenant</span></span>

<span data-ttu-id="bbfec-108">Aby sprawdzić, czy identyfikator naszej aplikacji mikrousług Microsoft Dynamics ERP znajduje się w Twojej dzierżawie, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="bbfec-108">To verify that the app ID for the Microsoft Dynamics ERP Microservices first-party app is in your tenant, follow these steps.</span></span>

1. <span data-ttu-id="bbfec-109">Zaloguj się do portalu Azure pod adresem <https://portal.azure.com>.</span><span class="sxs-lookup"><span data-stu-id="bbfec-109">Sign in to the Azure portal at <https://portal.azure.com>.</span></span>
2. <span data-ttu-id="bbfec-110">Przejdź do **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-110">Go to **Azure Active Directory**.</span></span>
3. <span data-ttu-id="bbfec-111">Przejdź do obszaru **Aplikacje dla przedsiębiorstw**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-111">Go to **Enterprise applications**.</span></span>
4. <span data-ttu-id="bbfec-112">W polu **Typ aplikacji** wybierz pozycję **Aplikacje firmy Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-112">In the **Application type** field, select **Microsoft applications**.</span></span>
5. <span data-ttu-id="bbfec-113">W polu wyszukiwania wprowadź **Mikrousługi Microsoft Dynamics ERP**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-113">In the search field, enter **Microsoft Dynamics ERP Microservices**.</span></span>
6. <span data-ttu-id="bbfec-114">Sprawdź, czy pozycja **Mikrousługi Microsoft Dynamics ERP** znajduje się na liście.</span><span class="sxs-lookup"><span data-stu-id="bbfec-114">Verify that **Microsoft Dynamics ERP Microservices** is in the list.</span></span> <span data-ttu-id="bbfec-115">Inne aplikacje mają podobne nazwy.</span><span class="sxs-lookup"><span data-stu-id="bbfec-115">Other applications have similar names.</span></span> <span data-ttu-id="bbfec-116">Dlatego upewnij się, że znaleziona aplikacja jest prawidłowa.</span><span class="sxs-lookup"><span data-stu-id="bbfec-116">Therefore, make sure that you find the correct application.</span></span> <span data-ttu-id="bbfec-117">Identyfikator aplikacji to **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-117">The app ID is **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span>

    <span data-ttu-id="bbfec-118">Jeśli aplikacji nie ma na liście, musisz ją dodać do dzierżawy:</span><span class="sxs-lookup"><span data-stu-id="bbfec-118">If the application isn't in the list, you must add it to your tenant:</span></span>

    1. <span data-ttu-id="bbfec-119">W witrynie Azure Portal kliknij na pasku narzędzi przycisk, aby otworzyć usługę Azure Cloud Shell.</span><span class="sxs-lookup"><span data-stu-id="bbfec-119">In the Azure portal, on the toolbar, select the button to open Azure Cloud Shell.</span></span>
    2. <span data-ttu-id="bbfec-120">Uruchom polecenie **Install-Module AzureAD**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-120">Run the command **Install-Module AzureAD**.</span></span> <span data-ttu-id="bbfec-121">Wprowadź wartość **Y**, aby zainstalować moduł.</span><span class="sxs-lookup"><span data-stu-id="bbfec-121">Enter **Y** to install the module.</span></span>
    3. <span data-ttu-id="bbfec-122">Uruchom polecenie **Get-InstalledModule -Name "AzureAD"**, aby sprawdzić, czy moduł został zainstalowany.</span><span class="sxs-lookup"><span data-stu-id="bbfec-122">Run the command **Get-InstalledModule -Name "AzureAD"** to verify that the module is installed.</span></span>
    4. <span data-ttu-id="bbfec-123">Uruchom polecenie **Connect-AzureAD -Confirm**, aby uruchomić uwierzytelnianie.</span><span class="sxs-lookup"><span data-stu-id="bbfec-123">Run the command **Connect-AzureAD -Confirm** to run the authentication.</span></span>
    5. <span data-ttu-id="bbfec-124">Uruchom polecenie **New-AzureADServicePrincipal -AppId 0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-124">Run the command **New-AzureADServicePrincipal -AppId 0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span>

    <span data-ttu-id="bbfec-125">Teraz możesz powtórzyć kroki od 1 do 6, aby sprawdzić, czy identyfikator aplikacji znajduje się w dzierżawie.</span><span class="sxs-lookup"><span data-stu-id="bbfec-125">You can now repeat steps 1 through 6 to verify that the app ID is in your tenant.</span></span>

### <a name="create-a-key-vault-resource"></a><span data-ttu-id="bbfec-126">Tworzenie zasobu magazynu kluczy</span><span class="sxs-lookup"><span data-stu-id="bbfec-126">Create a key vault resource</span></span>

<span data-ttu-id="bbfec-127">Aby utworzyć zasób magazynu kluczy, wykonaj poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="bbfec-127">To create a key vault resource, follow these steps.</span></span>

1. <span data-ttu-id="bbfec-128">W witrynie Azure Portal utwórz grupę zasobów lub przejdź do niej.</span><span class="sxs-lookup"><span data-stu-id="bbfec-128">In the Azure portal, create or go to a resource group.</span></span>
2. <span data-ttu-id="bbfec-129">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-129">Select **Add**.</span></span>
3. <span data-ttu-id="bbfec-130">Na stronie **Nowy** w polu wyszukiwania wprowadź ciąg **Magazyn kluczy**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-130">On the **New** page, in the search field, enter **Key vault**.</span></span> <span data-ttu-id="bbfec-131">Następnie wybierz opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-131">Then select **Create**.</span></span>
4. <span data-ttu-id="bbfec-132">Na stronie **Tworzenie magazynu kluczy** w polu **Nazwa magazynu kluczy** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="bbfec-132">On the **Create key vault** page, in the **Key vault name** field, enter a name.</span></span>
5. <span data-ttu-id="bbfec-133">Przejrzyj wartości domyślne, a następnie wybierz pozycję **Przegląd + tworzenie**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-133">Review the default values, and then select **Review + create**.</span></span>
6. <span data-ttu-id="bbfec-134">Wybierz opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-134">Select **Create**.</span></span>

<span data-ttu-id="bbfec-135">Magazyn kluczy jest tworzony w tle.</span><span class="sxs-lookup"><span data-stu-id="bbfec-135">The key vault is created in the background.</span></span>

### <a name="create-an-iot-hub-resource"></a><span data-ttu-id="bbfec-136">Tworzenie zasobu centrum IoT</span><span class="sxs-lookup"><span data-stu-id="bbfec-136">Create an IoT hub resource</span></span>

<span data-ttu-id="bbfec-137">Aby utworzyć zasób centrum IoT, wykonaj poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="bbfec-137">To create an IoT hub resource, follow these steps.</span></span>

1. <span data-ttu-id="bbfec-138">Wybierz grupę zasobów lub przejdź do niej.</span><span class="sxs-lookup"><span data-stu-id="bbfec-138">Create or go to a resource group.</span></span>
2. <span data-ttu-id="bbfec-139">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-139">Select **Add**.</span></span>
3. <span data-ttu-id="bbfec-140">Na stronie **Nowy** w polu wyszukiwania wprowadź ciąg **Centrum IoT**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-140">On the **New** page, in the search field, enter **Iot Hub**.</span></span> <span data-ttu-id="bbfec-141">Następnie wybierz opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-141">Then select **Create**.</span></span>
4. <span data-ttu-id="bbfec-142">W polu **Nazwa centrum IoT** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="bbfec-142">In the **IoT hub name** field, enter a name.</span></span>
5. <span data-ttu-id="bbfec-143">Przejrzyj wartości domyślne, a następnie wybierz pozycję **Przegląd + tworzenie**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-143">Review the default values, and then select **Review + create**.</span></span>
6. <span data-ttu-id="bbfec-144">Wybierz opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-144">Select **Create**.</span></span>

<span data-ttu-id="bbfec-145">Centrum IoT jest tworzone w tle.</span><span class="sxs-lookup"><span data-stu-id="bbfec-145">The IoT hub is created in the background.</span></span>

> [!NOTE]
> <span data-ttu-id="bbfec-146">Zalecamy, aby dla każdego środowiska utworzyć tylko jeden zasób typu centrum IoT.</span><span class="sxs-lookup"><span data-stu-id="bbfec-146">We recommend that you create only one IoT hub resource per environment.</span></span>

### <a name="create-a-redis-cache-resource"></a><span data-ttu-id="bbfec-147">Tworzenie zasobu pamięci podręcznej Redis</span><span class="sxs-lookup"><span data-stu-id="bbfec-147">Create a Redis cache resource</span></span>

<span data-ttu-id="bbfec-148">Aby utworzyć zasób pamięci podręcznej Redis, wykonaj poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="bbfec-148">To create a Redis cache resource, follow these steps.</span></span>

1. <span data-ttu-id="bbfec-149">Wybierz grupę zasobów lub przejdź do niej.</span><span class="sxs-lookup"><span data-stu-id="bbfec-149">Create or go to a resource group.</span></span>
2. <span data-ttu-id="bbfec-150">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-150">Select **Add**.</span></span>
3. <span data-ttu-id="bbfec-151">Na stronie **Nowy** w polu wyszukiwania wprowadź ciąg **Azure Cache for Redis**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-151">On the **New** page, in the search field, enter **Azure Cache for Redis**.</span></span> <span data-ttu-id="bbfec-152">Następnie wybierz opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-152">Then select **Create**.</span></span>
4. <span data-ttu-id="bbfec-153">W polu **Nazwa DNS** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="bbfec-153">In the **DNS name** field, enter a name.</span></span>
5. <span data-ttu-id="bbfec-154">Przejrzyj wartości domyślne, a następnie wybierz pozycję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-154">Review the default values, and then select **Create**.</span></span>

<span data-ttu-id="bbfec-155">Pamięć podręczna Redis jest tworzona w tle.</span><span class="sxs-lookup"><span data-stu-id="bbfec-155">The Redis cache is created in the background.</span></span>

> [!NOTE]
> <span data-ttu-id="bbfec-156">Zalecamy, aby dla każdego środowiska utworzyć tylko jedną pamięć podręczną Redis.</span><span class="sxs-lookup"><span data-stu-id="bbfec-156">We recommend that you create only one Redis cache per environment.</span></span>

<span data-ttu-id="bbfec-157">Wszystkie zasoby zostały teraz utworzone.</span><span class="sxs-lookup"><span data-stu-id="bbfec-157">All the resources have now been created.</span></span>

## <a name="configure-the-azure-resources"></a><span data-ttu-id="bbfec-158">Konfigurowanie zasobów platformy Azure</span><span class="sxs-lookup"><span data-stu-id="bbfec-158">Configure the Azure resources</span></span>

### <a name="configure-the-iot-hub"></a><span data-ttu-id="bbfec-159">Konfigurowanie centrum IoT</span><span class="sxs-lookup"><span data-stu-id="bbfec-159">Configure the IoT hub</span></span>

<span data-ttu-id="bbfec-160">Aby skonfigurować centrum IoT, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="bbfec-160">To configure the IoT hub, follow these steps.</span></span>

1. <span data-ttu-id="bbfec-161">W obszarze zasobów wybierz zasób Centrum IoT.</span><span class="sxs-lookup"><span data-stu-id="bbfec-161">In your resources, select the IoT hub resource.</span></span>
2. <span data-ttu-id="bbfec-162">W lewym okienku nawigacji wybierz pozycję **Wbudowane punkty końcowe**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-162">In the left navigation pane, select **Built-in endpoints**.</span></span>
3. <span data-ttu-id="bbfec-163">W obszarze **Grupy konsumentów** wklej następujące grupy konsumentów:</span><span class="sxs-lookup"><span data-stu-id="bbfec-163">Under **Consumer groups**, paste the following consumer groups.</span></span> <span data-ttu-id="bbfec-164">Te grupy odbiorców odpowiadają gotowym scenariuszom.</span><span class="sxs-lookup"><span data-stu-id="bbfec-164">These consumer groups correspond to the out-of-box scenarios.</span></span>

    + <span data-ttu-id="bbfec-165">microsoft.dynamics.iotintelligence-1</span><span class="sxs-lookup"><span data-stu-id="bbfec-165">microsoft.dynamics.iotintelligence-1</span></span>
    + <span data-ttu-id="bbfec-166">microsoft.dynamics.iotintelligence-2</span><span class="sxs-lookup"><span data-stu-id="bbfec-166">microsoft.dynamics.iotintelligence-2</span></span>
    + <span data-ttu-id="bbfec-167">microsoft.dynamics.iotintelligence-3</span><span class="sxs-lookup"><span data-stu-id="bbfec-167">microsoft.dynamics.iotintelligence-3</span></span>

### <a name="configure-the-key-vault"></a><span data-ttu-id="bbfec-168">Konfigurowanie magazynu kluczy</span><span class="sxs-lookup"><span data-stu-id="bbfec-168">Configure the key vault</span></span>

<span data-ttu-id="bbfec-169">Aby skonfigurować magazyn kluczy, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="bbfec-169">To configure the key vault, follow these steps.</span></span>

1. <span data-ttu-id="bbfec-170">W obszarze zasobów wybierz zasób Magazyn kluczy.</span><span class="sxs-lookup"><span data-stu-id="bbfec-170">In your resources, select the key vault resource.</span></span>
2. <span data-ttu-id="bbfec-171">W okienku nawigacji po lewej stronie wybierz pozycję **Zasady dostępu**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-171">In the left navigation pane, select **Access policies**.</span></span>
3. <span data-ttu-id="bbfec-172">Wybierz pozycję **Dodaj zasady dostępu**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-172">Select **Add an access policy**.</span></span>
4. <span data-ttu-id="bbfec-173">Na stronie **Dodawanie zasad dostępu** w polu **Uprawnienia klucza tajnego** wybierz pozycję **Pobieranie** i **Tworzenie listy**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-173">On the **Add access policy** page, in the **Secret permissions** field, select **Get** and **List**.</span></span>
5. <span data-ttu-id="bbfec-174">Kliknij w obszarze **Wybierz podmiot zabezpieczeń**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-174">Click in the **Select principal**.</span></span>
6. <span data-ttu-id="bbfec-175">W oknie dialogowym **Podmiot zabezpieczeń** wyszukaj i wybierz pozycję **Mikrousługi Microsoft Dynamics ERP**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-175">In the **Principal** dialog box, search for and select **Microsoft Dynamics ERP Microservices**.</span></span> <span data-ttu-id="bbfec-176">Następnie wybierz pozycję **Wybierz**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-176">Then select **Select**.</span></span>
7. <span data-ttu-id="bbfec-177">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-177">Select **Add**.</span></span>
8. <span data-ttu-id="bbfec-178">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-178">Select **Save**.</span></span>

<span data-ttu-id="bbfec-179">Aplikacja ma teraz dostęp do kluczy tajnych w magazynie kluczy.</span><span class="sxs-lookup"><span data-stu-id="bbfec-179">The app now has access to the secrets in the key vault.</span></span>

### <a name="save-the-iot-hub-connection-string-secret"></a><span data-ttu-id="bbfec-180">Zapisywanie klucza tajnego parametrów połączenia centrum IoT</span><span class="sxs-lookup"><span data-stu-id="bbfec-180">Save the IoT hub connection string secret</span></span>

<span data-ttu-id="bbfec-181">Aby zapisać klucz tajny dla parametrów połączenia centrum IoT, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="bbfec-181">To save the secret for the IoT hub connection string, follow these steps.</span></span>

1. <span data-ttu-id="bbfec-182">W obszarze zasobów wybierz zasób Centrum IoT.</span><span class="sxs-lookup"><span data-stu-id="bbfec-182">In your resources, select the IoT hub resource.</span></span>
2. <span data-ttu-id="bbfec-183">W lewym okienku nawigacji wybierz pozycję **Wbudowane punkty końcowe**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-183">In the left navigation pane, select **Built-in endpoints**.</span></span>
3. <span data-ttu-id="bbfec-184">Skopiuj wartość w polu **Punkt końcowy zgodny z centrum zdarzeń**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-184">Copy the value in the **Event Hub-compatible endpoint** field.</span></span>
4. <span data-ttu-id="bbfec-185">Przejdź do zasobu magazynu kluczy.</span><span class="sxs-lookup"><span data-stu-id="bbfec-185">Go to the key vault resource.</span></span>
5. <span data-ttu-id="bbfec-186">W okienku nawigacji po lewej stronie wybierz pozycję **Wpisy tajne**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-186">In the left navigation pane, select **Secrets**.</span></span>
6. <span data-ttu-id="bbfec-187">Wybierz pozycję **Generuj/importuj**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-187">Select **Generate/Import**.</span></span>
7. <span data-ttu-id="bbfec-188">W polu **Nazwa** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="bbfec-188">In the **Name** field, enter a name.</span></span>
8. <span data-ttu-id="bbfec-189">W polu **Wartość** wklej wcześniej skopiowaną wartość punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="bbfec-189">In the **Value** field, paste the endpoint value that you copied earlier.</span></span>
9. <span data-ttu-id="bbfec-190">Wybierz opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-190">Select **Create**.</span></span>

### <a name="save-the-redis-cache-connection-string-secret"></a><span data-ttu-id="bbfec-191">Zapisywanie klucza tajnego parametrów połączenia pamięci podręcznej Redis</span><span class="sxs-lookup"><span data-stu-id="bbfec-191">Save the Redis cache connection string secret</span></span>

<span data-ttu-id="bbfec-192">Aby zapisać klucz tajny dla parametrów połączenia pamięci podręcznej Redis, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="bbfec-192">To save the secret for the Redis cache connection string, follow these steps.</span></span>

1. <span data-ttu-id="bbfec-193">W obszarze zasobów wybierz zasób pamięci podręcznej Redis.</span><span class="sxs-lookup"><span data-stu-id="bbfec-193">In your resources, select the Redis cache resource.</span></span>
2. <span data-ttu-id="bbfec-194">Wybierz pozycję **Klucze dostępu**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-194">Select **Access keys**.</span></span>
3. <span data-ttu-id="bbfec-195">Skopiuj wartość w polu **Podstawowe parametry połączenia**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-195">Copy the value in the **Primary connection string** field.</span></span>
4. <span data-ttu-id="bbfec-196">Przejdź do zasobu magazynu kluczy.</span><span class="sxs-lookup"><span data-stu-id="bbfec-196">Go to the key vault resource.</span></span>
5. <span data-ttu-id="bbfec-197">W okienku nawigacji po lewej stronie wybierz pozycję **Wpisy tajne**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-197">In the left navigation pane, select **Secrets**.</span></span>
6. <span data-ttu-id="bbfec-198">Wybierz pozycję **Generuj/importuj**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-198">Select **Generate/Import**.</span></span>
7. <span data-ttu-id="bbfec-199">W polu **Nazwa** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="bbfec-199">In the **Name** field, enter a name.</span></span>
8. <span data-ttu-id="bbfec-200">W polu **Wartość** wklej wcześniej skopiowane parametry połączenia.</span><span class="sxs-lookup"><span data-stu-id="bbfec-200">In the **Value** field, paste the connection string that you copied earlier.</span></span>
9. <span data-ttu-id="bbfec-201">Wybierz opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="bbfec-201">Select **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="bbfec-202">Za każdym razem, gdy parametry połączenia są aktualizowane, musisz również zaktualizować wartości kluczy tajnych.</span><span class="sxs-lookup"><span data-stu-id="bbfec-202">Whenever you update one of the connection strings, you must also update the secret values.</span></span>

<span data-ttu-id="bbfec-203">Aprowizowanie wymaganych zasobów platformy Azure zostało zakończone.</span><span class="sxs-lookup"><span data-stu-id="bbfec-203">You've now finished provisioning the required Azure resources.</span></span> <span data-ttu-id="bbfec-204">Następny krok to [zainstalowanie dodatku analizy Internetu rzeczy (IoT) w usługach Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="bbfec-204">The next step is to [install the IoT Intelligence add-in in Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md).</span></span>
