---
title: ER Projektowanie modelu danych dla konkretnej domeny
description: W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli Administrator systemu lub Deweloper raportowania elektronicznego może utworzyć nową konfigurację raportowania elektronicznego (ER) zawierającą dane dokumentów płatności elektronicznych.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERDataContainerDescriptorReferenceSwitchDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3fe08b30977b8515ffd8d0acc1fd8f4b3085de93
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2020
ms.locfileid: "3026093"
---
# <a name="er-design-domain-specific-data-model"></a><span data-ttu-id="26d07-103">ER Projektowanie modelu danych dla konkretnej domeny</span><span class="sxs-lookup"><span data-stu-id="26d07-103">ER Design domain specific data model</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="26d07-104">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli Administrator systemu lub Deweloper raportowania elektronicznego może utworzyć nową konfigurację raportowania elektronicznego (ER) zawierającą dane dokumentów płatności elektronicznych.</span><span class="sxs-lookup"><span data-stu-id="26d07-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="26d07-105">Ten model danych będzie później używany jako źródło danych podczas tworzenia formatu dokumentów płatności.</span><span class="sxs-lookup"><span data-stu-id="26d07-105">This data model will later be used as a data source when you create the format of the payment documents.</span></span>



<span data-ttu-id="26d07-106">W tym przykładzie utworzysz konfigurację dla przykładowej firmy Litware, Inc. Podane kroki można wykonać w dowolnej firmie, ponieważ konfiguracje ER są współużytkowane przez wszystkie firmy.</span><span class="sxs-lookup"><span data-stu-id="26d07-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in any company as ER configurations are shared among companies.</span></span> <span data-ttu-id="26d07-107">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.</span><span class="sxs-lookup"><span data-stu-id="26d07-107">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>

1. <span data-ttu-id="26d07-108">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="26d07-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="26d07-109">Wybierz dostawcę konfiguracji przykładowej firmy „Litware, Inc.”.</span><span class="sxs-lookup"><span data-stu-id="26d07-109">Select the configuration provider for sample company, ‘Litware, Inc.’</span></span> <span data-ttu-id="26d07-110">Jeśli ten dostawca konfiguracji nie jest widoczny, należy najpierw wykonać procedurę „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.</span><span class="sxs-lookup"><span data-stu-id="26d07-110">If you don’t see this configuration provider, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>  
2. <span data-ttu-id="26d07-111">Kliknij opcję Konfiguracje raportowania.</span><span class="sxs-lookup"><span data-stu-id="26d07-111">Click Reporting configurations.</span></span>
    * <span data-ttu-id="26d07-112">Utworzysz konfigurację, która zawiera model danych dla dokumentów płatności elektronicznych.</span><span class="sxs-lookup"><span data-stu-id="26d07-112">You will create a configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="26d07-113">Ten model danych będzie później używany jako źródło danych podczas tworzenia formatu dokumentów płatności.</span><span class="sxs-lookup"><span data-stu-id="26d07-113">This data model will be used later as a data source when you create the format for the payment documents.</span></span>  

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="26d07-114">Tworzenie nowej konfiguracji modelu danych</span><span class="sxs-lookup"><span data-stu-id="26d07-114">Create a new data model configuration</span></span>
1. <span data-ttu-id="26d07-115">Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="26d07-115">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="26d07-116">W polu Nazwa wpisz „Płatności (model uproszczony)”.</span><span class="sxs-lookup"><span data-stu-id="26d07-116">In the Name field, type 'Payments (simplified model)'.</span></span>
    * <span data-ttu-id="26d07-117">Płatności (model uproszczony)</span><span class="sxs-lookup"><span data-stu-id="26d07-117">Payments (simplified model)</span></span>  
3. <span data-ttu-id="26d07-118">W polu Opis wpisz „Konfiguracja modelu płatności”.</span><span class="sxs-lookup"><span data-stu-id="26d07-118">In the Description field, type 'Payment model configuration'.</span></span>
    * <span data-ttu-id="26d07-119">Konfiguracja modelu płatności</span><span class="sxs-lookup"><span data-stu-id="26d07-119">Payment model configuration</span></span>  
    * <span data-ttu-id="26d07-120">Aktywny dostawca konfiguracji jest automatycznie umieszczany w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="26d07-120">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="26d07-121">Ten dostawca będzie mógł obsługiwać tę konfigurację.</span><span class="sxs-lookup"><span data-stu-id="26d07-121">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="26d07-122">Inni dostawcy mogą używać tej konfiguracji, ale nie będą mogli nią zarządzać.</span><span class="sxs-lookup"><span data-stu-id="26d07-122">Other providers can use this configuration, but will not be able to maintain it.</span></span>  
4. <span data-ttu-id="26d07-123">Kliknij przycisk „Utwórz konfigurację”, aby dokończyć zadanie tworzenia konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="26d07-123">Click ‘Create configuration’ button to complete the configuration creation task</span></span>

## <a name="create-a-data-model"></a><span data-ttu-id="26d07-124">Tworzenie modelu danych</span><span class="sxs-lookup"><span data-stu-id="26d07-124">Create a data model</span></span>
<span data-ttu-id="26d07-125">Tworzysz nowy model danych dla wybranej konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="26d07-125">You're creating a new data model for the selected configuration.</span></span> <span data-ttu-id="26d07-126">Ta wersja konfiguracji będzie miała stan Wersja robocza.</span><span class="sxs-lookup"><span data-stu-id="26d07-126">This configuration version will have a status of Draft.</span></span>  
1. <span data-ttu-id="26d07-127">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="26d07-127">Click Designer.</span></span>

## <a name="define-the-structure-of-a-party-participating-in-a-payment-process"></a><span data-ttu-id="26d07-128">Definiowanie struktury strony uczestniczącej w procesie płatności</span><span class="sxs-lookup"><span data-stu-id="26d07-128">Define the structure of a party participating in a payment process</span></span>
1. <span data-ttu-id="26d07-129">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="26d07-129">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="26d07-130">W polu Nazwa wpisz „Strona”.</span><span class="sxs-lookup"><span data-stu-id="26d07-130">In the Name field, type 'Party'.</span></span>
    * <span data-ttu-id="26d07-131">Jednostka</span><span class="sxs-lookup"><span data-stu-id="26d07-131">Party</span></span>  
3. <span data-ttu-id="26d07-132">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="26d07-132">Click Add.</span></span>
4. <span data-ttu-id="26d07-133">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="26d07-133">Click New to open the drop dialog.</span></span>
5. <span data-ttu-id="26d07-134">W polu Nazwa wpisz „Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="26d07-134">In the Name field, type 'Name'.</span></span>
    * <span data-ttu-id="26d07-135">Nazwisko</span><span class="sxs-lookup"><span data-stu-id="26d07-135">Name</span></span>  
6. <span data-ttu-id="26d07-136">W polu Typ elementu wybierz opcję „Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="26d07-136">In the Item type field, select 'String'.</span></span>
7. <span data-ttu-id="26d07-137">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="26d07-137">Click Add.</span></span>
8. <span data-ttu-id="26d07-138">W polu Znajdź wpisz „Strona”.</span><span class="sxs-lookup"><span data-stu-id="26d07-138">In the Find field, type 'Party'.</span></span>
    * <span data-ttu-id="26d07-139">Jednostka</span><span class="sxs-lookup"><span data-stu-id="26d07-139">Party</span></span>  
9. <span data-ttu-id="26d07-140">Kliknij opcję Znajdź poprzednie.</span><span class="sxs-lookup"><span data-stu-id="26d07-140">Click Find previous.</span></span>

## <a name="define-the-bank-structure-for-this-model"></a><span data-ttu-id="26d07-141">Definiowanie struktury banku dla tego modelu</span><span class="sxs-lookup"><span data-stu-id="26d07-141">Define the bank structure for this model</span></span>
1. <span data-ttu-id="26d07-142">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="26d07-142">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="26d07-143">W polu Nazwa wpisz „Agent”.</span><span class="sxs-lookup"><span data-stu-id="26d07-143">In the Name field, type 'Agent'.</span></span>
    * <span data-ttu-id="26d07-144">Agent</span><span class="sxs-lookup"><span data-stu-id="26d07-144">Agent</span></span>  
3. <span data-ttu-id="26d07-145">W polu Typ elementu wybierz opcję „Rekord”.</span><span class="sxs-lookup"><span data-stu-id="26d07-145">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="26d07-146">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="26d07-146">Click Add.</span></span>
5. <span data-ttu-id="26d07-147">W polu Opis wpisz „Instytucja finansowa (np. bank) obsługująca konto strony (dłużnika/wierzyciela).”.</span><span class="sxs-lookup"><span data-stu-id="26d07-147">In the Description field, enter 'Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).'.</span></span>
    * <span data-ttu-id="26d07-148">Instytucja finansowa (np. bank) obsługująca konto strony (dłużnika/wierzyciela).</span><span class="sxs-lookup"><span data-stu-id="26d07-148">Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).</span></span>  
6. <span data-ttu-id="26d07-149">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="26d07-149">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="26d07-150">W polu Nazwa wpisz „Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="26d07-150">In the Name field, type 'Name'.</span></span>
    * <span data-ttu-id="26d07-151">Nazwisko</span><span class="sxs-lookup"><span data-stu-id="26d07-151">Name</span></span>  
8. <span data-ttu-id="26d07-152">W polu Typ elementu wybierz opcję „Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="26d07-152">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="26d07-153">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="26d07-153">Click Add.</span></span>
10. <span data-ttu-id="26d07-154">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="26d07-154">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="26d07-155">W polu Nazwa wpisz „SWIFT”.</span><span class="sxs-lookup"><span data-stu-id="26d07-155">In the Name field, type 'SWIFT'.</span></span>
    * <span data-ttu-id="26d07-156">SWIFT</span><span class="sxs-lookup"><span data-stu-id="26d07-156">SWIFT</span></span>  
12. <span data-ttu-id="26d07-157">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="26d07-157">Click Add.</span></span>
13. <span data-ttu-id="26d07-158">W polu Opis wpisz „Kod identyfikacyjny banku”.</span><span class="sxs-lookup"><span data-stu-id="26d07-158">In the Description field, enter 'Bank identification code'.</span></span>
    * <span data-ttu-id="26d07-159">Kod identyfikacyjny banku.</span><span class="sxs-lookup"><span data-stu-id="26d07-159">Bank identification code</span></span>  
14. <span data-ttu-id="26d07-160">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="26d07-160">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="26d07-161">W polu Nazwa wpisz „RoutingNumber”.</span><span class="sxs-lookup"><span data-stu-id="26d07-161">In the Name field, type 'RoutingNumber'.</span></span>
    * <span data-ttu-id="26d07-162">RoutingNumber</span><span class="sxs-lookup"><span data-stu-id="26d07-162">RoutingNumber</span></span>  
16. <span data-ttu-id="26d07-163">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="26d07-163">Click Add.</span></span>
17. <span data-ttu-id="26d07-164">W polu Opis wpisz „Kod banku”.</span><span class="sxs-lookup"><span data-stu-id="26d07-164">In the Description field, enter 'Routing number'.</span></span>
    * <span data-ttu-id="26d07-165">REGON</span><span class="sxs-lookup"><span data-stu-id="26d07-165">Routing number</span></span>  
18. <span data-ttu-id="26d07-166">Kliknij opcję Znajdź poprzednie.</span><span class="sxs-lookup"><span data-stu-id="26d07-166">Click Find previous.</span></span>

## <a name="define-the-bank-account-structure-for-this-model"></a><span data-ttu-id="26d07-167">Definiowanie struktury konta banku dla tego modelu</span><span class="sxs-lookup"><span data-stu-id="26d07-167">Define the bank account structure for this model</span></span>
1. <span data-ttu-id="26d07-168">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="26d07-168">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="26d07-169">W polu Nazwa wpisz „Konto”.</span><span class="sxs-lookup"><span data-stu-id="26d07-169">In the Name field, type 'Account'.</span></span>
    * <span data-ttu-id="26d07-170">Konto</span><span class="sxs-lookup"><span data-stu-id="26d07-170">Account</span></span>  
3. <span data-ttu-id="26d07-171">W polu Typ elementu wybierz opcję „Rekord”.</span><span class="sxs-lookup"><span data-stu-id="26d07-171">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="26d07-172">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="26d07-172">Click Add.</span></span>
5. <span data-ttu-id="26d07-173">W polu Opis wpisz „Identyfikator konta strony w instytucji finansowej (na przykład w banku).”.</span><span class="sxs-lookup"><span data-stu-id="26d07-173">In the Description field, enter 'Identification of an account of a party in a financial institution (for instance, a bank).'.</span></span>
    * <span data-ttu-id="26d07-174">Identyfikator konta strony w instytucji finansowej (na przykład w banku).</span><span class="sxs-lookup"><span data-stu-id="26d07-174">Identification of an account of a party in a financial institution (for instance, a bank).</span></span>  
6. <span data-ttu-id="26d07-175">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="26d07-175">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="26d07-176">W polu Nazwa wpisz „Waluta”.</span><span class="sxs-lookup"><span data-stu-id="26d07-176">In the Name field, type 'Currency'.</span></span>
    * <span data-ttu-id="26d07-177">Waluta</span><span class="sxs-lookup"><span data-stu-id="26d07-177">Currency</span></span>  
8. <span data-ttu-id="26d07-178">W polu Typ elementu wybierz opcję „Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="26d07-178">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="26d07-179">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="26d07-179">Click Add.</span></span>
10. <span data-ttu-id="26d07-180">W polu Opis wpisz „Kod waluty”.</span><span class="sxs-lookup"><span data-stu-id="26d07-180">In the Description field, enter 'Currency code'.</span></span>
    * <span data-ttu-id="26d07-181">Kod waluty</span><span class="sxs-lookup"><span data-stu-id="26d07-181">Currency code</span></span>  
11. <span data-ttu-id="26d07-182">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="26d07-182">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="26d07-183">W polu Nazwa wpisz „Numer”.</span><span class="sxs-lookup"><span data-stu-id="26d07-183">In the Name field, type 'Number'.</span></span>
    * <span data-ttu-id="26d07-184">Identyfikator</span><span class="sxs-lookup"><span data-stu-id="26d07-184">Number</span></span>  
13. <span data-ttu-id="26d07-185">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="26d07-185">Click Add.</span></span>
14. <span data-ttu-id="26d07-186">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="26d07-186">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="26d07-187">W polu Nazwa wpisz „IBAN”.</span><span class="sxs-lookup"><span data-stu-id="26d07-187">In the Name field, type 'IBAN'.</span></span>
    * <span data-ttu-id="26d07-188">Numer IBAN</span><span class="sxs-lookup"><span data-stu-id="26d07-188">IBAN</span></span>  
16. <span data-ttu-id="26d07-189">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="26d07-189">Click Add.</span></span>
17. <span data-ttu-id="26d07-190">W polu Opis wpisz „Międzynarodowy numer konta bankowego”.</span><span class="sxs-lookup"><span data-stu-id="26d07-190">In the Description field, enter 'International bank account number'.</span></span>
    * <span data-ttu-id="26d07-191">Międzynarodowy numer konta bankowego</span><span class="sxs-lookup"><span data-stu-id="26d07-191">International bank account number</span></span>  

## <a name="define-the-payment-message-structure-for-credit-transfer-payment-type"></a><span data-ttu-id="26d07-192">Definiowanie struktury komunikatu płatności dla płatności poleceniem przelewu</span><span class="sxs-lookup"><span data-stu-id="26d07-192">Define the payment message structure for credit transfer payment type</span></span>
1. <span data-ttu-id="26d07-193">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="26d07-193">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="26d07-194">W polu Nowy węzeł jako wpisz „Element główny modelu”.</span><span class="sxs-lookup"><span data-stu-id="26d07-194">In the New node as a field, enter 'Model root'.</span></span>
3. <span data-ttu-id="26d07-195">W polu Nazwa wpisz „CustomerCreditTransferInitiation”.</span><span class="sxs-lookup"><span data-stu-id="26d07-195">In the Name field, type 'CustomerCreditTransferInitiation'.</span></span>
    * <span data-ttu-id="26d07-196">CustomerCreditTransferInitiation</span><span class="sxs-lookup"><span data-stu-id="26d07-196">CustomerCreditTransferInitiation</span></span>  
4. <span data-ttu-id="26d07-197">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="26d07-197">Click Add.</span></span>
5. <span data-ttu-id="26d07-198">W polu Znajdź wpisz „CustomerCreditTransferInitiation”.</span><span class="sxs-lookup"><span data-stu-id="26d07-198">In the Find field, type 'CustomerCreditTransferInitiation'.</span></span>
    * <span data-ttu-id="26d07-199">CustomerCreditTransferInitiation</span><span class="sxs-lookup"><span data-stu-id="26d07-199">CustomerCreditTransferInitiation</span></span>  
6. <span data-ttu-id="26d07-200">Kliknij opcję Znajdź poprzednie.</span><span class="sxs-lookup"><span data-stu-id="26d07-200">Click Find previous.</span></span>
7. <span data-ttu-id="26d07-201">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="26d07-201">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="26d07-202">W polu Nazwa wpisz „MessageIdentification”.</span><span class="sxs-lookup"><span data-stu-id="26d07-202">In the Name field, type 'MessageIdentification'.</span></span>
    * <span data-ttu-id="26d07-203">MessageIdentification</span><span class="sxs-lookup"><span data-stu-id="26d07-203">MessageIdentification</span></span>  
9. <span data-ttu-id="26d07-204">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="26d07-204">Click Add.</span></span>
10. <span data-ttu-id="26d07-205">W polu Opis wpisz „Odwołanie bezpośrednie przypisane przez stronę zlecającą (i wysłane do następnej strony) w celu identyfikacji komunikatu.”.</span><span class="sxs-lookup"><span data-stu-id="26d07-205">In the Description field, enter 'The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.'.</span></span>
    * <span data-ttu-id="26d07-206">Odwołanie bezpośrednie przypisane przez stronę zlecającą (i wysłane do następnej strony) w celu identyfikacji komunikatu.</span><span class="sxs-lookup"><span data-stu-id="26d07-206">The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.</span></span>  
11. <span data-ttu-id="26d07-207">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="26d07-207">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="26d07-208">W polu Nazwa wpisz „ProcessingDateTime”.</span><span class="sxs-lookup"><span data-stu-id="26d07-208">In the Name field, type 'ProcessingDateTime'.</span></span>
    * <span data-ttu-id="26d07-209">ProcessingDateTime</span><span class="sxs-lookup"><span data-stu-id="26d07-209">ProcessingDateTime</span></span>  
13. <span data-ttu-id="26d07-210">W polu Typ elementu wybierz opcję „DateTime”.</span><span class="sxs-lookup"><span data-stu-id="26d07-210">In the Item type field, select 'DateTime'.</span></span>
14. <span data-ttu-id="26d07-211">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="26d07-211">Click Add.</span></span>
15. <span data-ttu-id="26d07-212">W polu Opis wpisz „Data i godzina utworzenia komunikatu płatności.”.</span><span class="sxs-lookup"><span data-stu-id="26d07-212">In the Description field, enter 'Date and time at which the payment message was created.'.</span></span>
    * <span data-ttu-id="26d07-213">Data i godzina utworzenia komunikatu płatności.</span><span class="sxs-lookup"><span data-stu-id="26d07-213">Date and time at which the payment message was created.</span></span>  
16. <span data-ttu-id="26d07-214">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="26d07-214">Click New to open the drop dialog.</span></span>
    * <span data-ttu-id="26d07-215">Definiowanie struktury transakcji płatności dla tego modelu.</span><span class="sxs-lookup"><span data-stu-id="26d07-215">Define the payment transaction structure for this model.</span></span>  
17. <span data-ttu-id="26d07-216">W polu Nazwa wpisz „Płatności”.</span><span class="sxs-lookup"><span data-stu-id="26d07-216">In the Name field, type 'Payments'.</span></span>
    * <span data-ttu-id="26d07-217">Płatności</span><span class="sxs-lookup"><span data-stu-id="26d07-217">Payments</span></span>  
18. <span data-ttu-id="26d07-218">W polu Typ elementu wybierz opcję „Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="26d07-218">In the Item type field, select 'Record list'.</span></span>
19. <span data-ttu-id="26d07-219">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="26d07-219">Click Add.</span></span>
20. <span data-ttu-id="26d07-220">W polu Opis wpisz „Wiersze płatności w bieżącym komunikacie”.</span><span class="sxs-lookup"><span data-stu-id="26d07-220">In the Description field, enter 'Payment lines of the current message'.</span></span>
    * <span data-ttu-id="26d07-221">Wiersze płatności w bieżącym komunikacie</span><span class="sxs-lookup"><span data-stu-id="26d07-221">Payment lines of the current message</span></span>  
21. <span data-ttu-id="26d07-222">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="26d07-222">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="26d07-223">W polu Nazwa wpisz „Wierzyciel”.</span><span class="sxs-lookup"><span data-stu-id="26d07-223">In the Name field, type 'Creditor'.</span></span>
    * <span data-ttu-id="26d07-224">Dostawca</span><span class="sxs-lookup"><span data-stu-id="26d07-224">Creditor</span></span>  
23. <span data-ttu-id="26d07-225">W polu Typ elementu wybierz opcję „Rekord”.</span><span class="sxs-lookup"><span data-stu-id="26d07-225">In the Item type field, select 'Record'.</span></span>
24. <span data-ttu-id="26d07-226">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="26d07-226">Click Add.</span></span>
25. <span data-ttu-id="26d07-227">W polu Opis wpisz „Strona, do której należy przesłać kwotę pieniężną.”.</span><span class="sxs-lookup"><span data-stu-id="26d07-227">In the Description field, enter 'Party to which an amount of money is due.'.</span></span>
    * <span data-ttu-id="26d07-228">Strona, do której należy przesłać kwotę pieniężną.</span><span class="sxs-lookup"><span data-stu-id="26d07-228">Party to which an amount of money is due.</span></span>  
26. <span data-ttu-id="26d07-229">Kliknij opcję Przełącz odwołanie do elementu.</span><span class="sxs-lookup"><span data-stu-id="26d07-229">Click Switch item reference.</span></span>
27. <span data-ttu-id="26d07-230">W polu Znajdź wpisz „Strona”.</span><span class="sxs-lookup"><span data-stu-id="26d07-230">In the Find field, type 'Party'.</span></span>
    * <span data-ttu-id="26d07-231">Jednostka</span><span class="sxs-lookup"><span data-stu-id="26d07-231">Party</span></span>  
28. <span data-ttu-id="26d07-232">Kliknij przycisk Znajdź następny.</span><span class="sxs-lookup"><span data-stu-id="26d07-232">Click Find next.</span></span>
29. <span data-ttu-id="26d07-233">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="26d07-233">Click OK.</span></span>
30. <span data-ttu-id="26d07-234">W polu Znajdź wpisz „Płatności”.</span><span class="sxs-lookup"><span data-stu-id="26d07-234">In the Find field, type 'Payments'.</span></span>
    * <span data-ttu-id="26d07-235">Płatności</span><span class="sxs-lookup"><span data-stu-id="26d07-235">Payments</span></span>  
31. <span data-ttu-id="26d07-236">Kliknij przycisk Znajdź następny.</span><span class="sxs-lookup"><span data-stu-id="26d07-236">Click Find next.</span></span>
32. <span data-ttu-id="26d07-237">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="26d07-237">Click New to open the drop dialog.</span></span>
33. <span data-ttu-id="26d07-238">W polu Nazwa wpisz „Dłużnik”.</span><span class="sxs-lookup"><span data-stu-id="26d07-238">In the Name field, type 'Debtor'.</span></span>
    * <span data-ttu-id="26d07-239">Dłużnik</span><span class="sxs-lookup"><span data-stu-id="26d07-239">Debtor</span></span>  
34. <span data-ttu-id="26d07-240">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="26d07-240">Click Add.</span></span>
35. <span data-ttu-id="26d07-241">W polu Opis wpisz „Strona będąca dłużna kwotę pieniężną (ostatecznemu) wierzycielowi.”.</span><span class="sxs-lookup"><span data-stu-id="26d07-241">In the Description field, enter 'Party that owes an amount of money to the (ultimate) creditor.'.</span></span>
    * <span data-ttu-id="26d07-242">Strona będąca dłużna kwotę pieniężną (ostatecznemu) wierzycielowi.</span><span class="sxs-lookup"><span data-stu-id="26d07-242">Party that owes an amount of money to the (ultimate) creditor.</span></span>  
36. <span data-ttu-id="26d07-243">Kliknij opcję Przełącz odwołanie do elementu.</span><span class="sxs-lookup"><span data-stu-id="26d07-243">Click Switch item reference.</span></span>
37. <span data-ttu-id="26d07-244">W polu Znajdź wpisz „Strona”.</span><span class="sxs-lookup"><span data-stu-id="26d07-244">In the Find field, type 'Party'.</span></span>
    * <span data-ttu-id="26d07-245">Jednostka</span><span class="sxs-lookup"><span data-stu-id="26d07-245">Party</span></span>  
38. <span data-ttu-id="26d07-246">Kliknij przycisk Znajdź następny.</span><span class="sxs-lookup"><span data-stu-id="26d07-246">Click Find next.</span></span>
39. <span data-ttu-id="26d07-247">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="26d07-247">Click OK.</span></span>
40. <span data-ttu-id="26d07-248">Kliknij przycisk Znajdź następny.</span><span class="sxs-lookup"><span data-stu-id="26d07-248">Click Find next.</span></span>
41. <span data-ttu-id="26d07-249">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="26d07-249">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="26d07-250">W polu Nazwa wpisz „Opis”.</span><span class="sxs-lookup"><span data-stu-id="26d07-250">In the Name field, type 'Description'.</span></span>
    * <span data-ttu-id="26d07-251">opis</span><span class="sxs-lookup"><span data-stu-id="26d07-251">Description</span></span>  
43. <span data-ttu-id="26d07-252">W polu Typ elementu wybierz opcję „Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="26d07-252">In the Item type field, select 'String'.</span></span>
44. <span data-ttu-id="26d07-253">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="26d07-253">Click Add.</span></span>
45. <span data-ttu-id="26d07-254">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="26d07-254">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="26d07-255">W polu Nazwa wpisz „Waluta”.</span><span class="sxs-lookup"><span data-stu-id="26d07-255">In the Name field, type 'Currency'.</span></span>
    * <span data-ttu-id="26d07-256">Waluta</span><span class="sxs-lookup"><span data-stu-id="26d07-256">Currency</span></span>  
47. <span data-ttu-id="26d07-257">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="26d07-257">Click Add.</span></span>
48. <span data-ttu-id="26d07-258">W polu Opis wpisz „Kod waluty”.</span><span class="sxs-lookup"><span data-stu-id="26d07-258">In the Description field, enter 'Currency code'.</span></span>
    * <span data-ttu-id="26d07-259">Kod waluty</span><span class="sxs-lookup"><span data-stu-id="26d07-259">Currency code</span></span>  
49. <span data-ttu-id="26d07-260">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="26d07-260">Click New to open the drop dialog.</span></span>
50. <span data-ttu-id="26d07-261">W polu Nazwa wpisz „TransactionDate”.</span><span class="sxs-lookup"><span data-stu-id="26d07-261">In the Name field, type 'TransactionDate'.</span></span>
    * <span data-ttu-id="26d07-262">TransactionDate</span><span class="sxs-lookup"><span data-stu-id="26d07-262">TransactionDate</span></span>  
51. <span data-ttu-id="26d07-263">W polu Typ elementu wybierz opcję „Data”.</span><span class="sxs-lookup"><span data-stu-id="26d07-263">In the Item type field, select 'Date'.</span></span>
52. <span data-ttu-id="26d07-264">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="26d07-264">Click Add.</span></span>
53. <span data-ttu-id="26d07-265">W polu Opis wpisz „Data transakcji”.</span><span class="sxs-lookup"><span data-stu-id="26d07-265">In the Description field, enter 'Transaction date'.</span></span>
    * <span data-ttu-id="26d07-266">Data transakcji</span><span class="sxs-lookup"><span data-stu-id="26d07-266">Transaction date</span></span>  
54. <span data-ttu-id="26d07-267">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="26d07-267">Click New to open the drop dialog.</span></span>
55. <span data-ttu-id="26d07-268">W polu Nazwa wpisz „InstructedAmount”.</span><span class="sxs-lookup"><span data-stu-id="26d07-268">In the Name field, type 'InstructedAmount'.</span></span>
    * <span data-ttu-id="26d07-269">InstructedAmount</span><span class="sxs-lookup"><span data-stu-id="26d07-269">InstructedAmount</span></span>  
56. <span data-ttu-id="26d07-270">W polu Typ elementu wybierz opcję „Liczba rzeczywista”.</span><span class="sxs-lookup"><span data-stu-id="26d07-270">In the Item type field, select 'Real'.</span></span>
57. <span data-ttu-id="26d07-271">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="26d07-271">Click Add.</span></span>
58. <span data-ttu-id="26d07-272">W polu Opis wpisz „Kwota pieniężna do przekazania między dłużnikiem a wierzycielem przed potrąceniem opłat.</span><span class="sxs-lookup"><span data-stu-id="26d07-272">In the Description field, enter 'The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="26d07-273">Kwota powinna być wyrażona w walucie podanej przez stronę inicjującą.”.</span><span class="sxs-lookup"><span data-stu-id="26d07-273">The amount should be expressed in the currency as ordered by the initiating party.'.</span></span>
    * <span data-ttu-id="26d07-274">Kwota pieniężna do przekazania między dłużnikiem a wierzycielem przed potrąceniem opłat.</span><span class="sxs-lookup"><span data-stu-id="26d07-274">The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="26d07-275">Kwota powinna być wyrażona w walucie podanej przez stronę inicjującą.</span><span class="sxs-lookup"><span data-stu-id="26d07-275">The amount should be expressed in the currency as ordered by the initiating party.</span></span>  
59. <span data-ttu-id="26d07-276">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="26d07-276">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="26d07-277">W polu Nazwa wpisz „End2EndID”.</span><span class="sxs-lookup"><span data-stu-id="26d07-277">In the Name field, type 'End2EndID'.</span></span>
    * <span data-ttu-id="26d07-278">End2EndID</span><span class="sxs-lookup"><span data-stu-id="26d07-278">End2EndID</span></span>  
61. <span data-ttu-id="26d07-279">W polu Typ elementu wybierz opcję „Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="26d07-279">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="26d07-280">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="26d07-280">Click Add.</span></span>
63. <span data-ttu-id="26d07-281">W polu Opis wpisz „Unikatowy identyfikator przypisywany przez stronę inicjującą.</span><span class="sxs-lookup"><span data-stu-id="26d07-281">In the Description field, enter 'The unique identification assigned by the initiating party.</span></span> <span data-ttu-id="26d07-282">Identyfikator jest przekazywany bez zmian w całym łańcuchu operacji.”.</span><span class="sxs-lookup"><span data-stu-id="26d07-282">This identification is passed on, unchanged, throughout the entire end-to-end chain.'.</span></span>
    * <span data-ttu-id="26d07-283">Unikatowy identyfikator przypisywany przez stronę inicjującą.</span><span class="sxs-lookup"><span data-stu-id="26d07-283">The unique identification assigned by the initiating party.</span></span> <span data-ttu-id="26d07-284">Identyfikator jest przekazywany bez zmian w całym łańcuchu operacji.</span><span class="sxs-lookup"><span data-stu-id="26d07-284">This identification is passed on, unchanged, throughout the entire end-to-end chain.</span></span>  
64. <span data-ttu-id="26d07-285">W polu Nazwa wpisz „PaymentModel”.</span><span class="sxs-lookup"><span data-stu-id="26d07-285">In the Name field, type 'PaymentModel'.</span></span>
    * <span data-ttu-id="26d07-286">Nazwa PaymentModel jest dopasowana do wstępnie zdefiniowanych interfejsów formularzy płatności.</span><span class="sxs-lookup"><span data-stu-id="26d07-286">The PaymentModel name aligns with predefined interfaces of payment forms.</span></span>  
65. <span data-ttu-id="26d07-287">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="26d07-287">Click Save.</span></span>
66. <span data-ttu-id="26d07-288">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="26d07-288">Close the page.</span></span>

