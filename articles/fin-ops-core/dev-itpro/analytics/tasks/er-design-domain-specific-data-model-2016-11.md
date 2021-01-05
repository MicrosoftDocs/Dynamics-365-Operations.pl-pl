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
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 268f661079b80551b36ad2e1877615d878350051
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681956"
---
# <a name="er-design-domain-specific-data-model"></a><span data-ttu-id="36c05-103">ER Projektowanie modelu danych dla konkretnej domeny</span><span class="sxs-lookup"><span data-stu-id="36c05-103">ER Design domain specific data model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="36c05-104">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli Administrator systemu lub Deweloper raportowania elektronicznego może utworzyć nową konfigurację raportowania elektronicznego (ER) zawierającą dane dokumentów płatności elektronicznych.</span><span class="sxs-lookup"><span data-stu-id="36c05-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="36c05-105">Ten model danych będzie później używany jako źródło danych podczas tworzenia formatu dokumentów płatności.</span><span class="sxs-lookup"><span data-stu-id="36c05-105">This data model will later be used as a data source when you create the format of the payment documents.</span></span>

<span data-ttu-id="36c05-106">W tym przykładzie utworzysz konfigurację dla przykładowej firmy Litware, Inc. Podane kroki można wykonać w dowolnej firmie, ponieważ konfiguracje ER są współużytkowane przez wszystkie firmy.</span><span class="sxs-lookup"><span data-stu-id="36c05-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in any company as ER configurations are shared among companies.</span></span> <span data-ttu-id="36c05-107">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.</span><span class="sxs-lookup"><span data-stu-id="36c05-107">To complete these steps, you must first complete the steps in the "Create a configuration provider and mark it as active" procedure.</span></span>

1. <span data-ttu-id="36c05-108">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="36c05-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>

    <span data-ttu-id="36c05-109">Wybierz dostawcę konfiguracji przykładowej firmy „Litware, Inc.”.</span><span class="sxs-lookup"><span data-stu-id="36c05-109">Select the configuration provider for sample company, 'Litware, Inc.'</span></span> <span data-ttu-id="36c05-110">Jeśli ten dostawca konfiguracji nie jest widoczny, należy najpierw wykonać procedurę „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.</span><span class="sxs-lookup"><span data-stu-id="36c05-110">If you don't see this configuration provider, you must first complete the steps in the "Create a configuration provider and mark it as active" procedure.</span></span>  
    
2. <span data-ttu-id="36c05-111">Kliknij opcję Konfiguracje raportowania.</span><span class="sxs-lookup"><span data-stu-id="36c05-111">Click Reporting configurations.</span></span>

    <span data-ttu-id="36c05-112">Utworzysz konfigurację, która zawiera model danych dla dokumentów płatności elektronicznych.</span><span class="sxs-lookup"><span data-stu-id="36c05-112">You will create a configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="36c05-113">Ten model danych będzie później używany jako źródło danych podczas tworzenia formatu dokumentów płatności.</span><span class="sxs-lookup"><span data-stu-id="36c05-113">This data model will be used later as a data source when you create the format for the payment documents.</span></span>  

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="36c05-114">Tworzenie nowej konfiguracji modelu danych</span><span class="sxs-lookup"><span data-stu-id="36c05-114">Create a new data model configuration</span></span>
1. <span data-ttu-id="36c05-115">Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="36c05-115">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="36c05-116">W polu Nazwa wpisz „Płatności (model uproszczony)”.</span><span class="sxs-lookup"><span data-stu-id="36c05-116">In the Name field, type 'Payments (simplified model)'.</span></span>
3. <span data-ttu-id="36c05-117">W polu Opis wpisz „Konfiguracja modelu płatności”.</span><span class="sxs-lookup"><span data-stu-id="36c05-117">In the Description field, type 'Payment model configuration'.</span></span>

    <span data-ttu-id="36c05-118">Aktywny dostawca konfiguracji jest automatycznie umieszczany w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="36c05-118">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="36c05-119">Ten dostawca będzie mógł obsługiwać tę konfigurację.</span><span class="sxs-lookup"><span data-stu-id="36c05-119">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="36c05-120">Inni dostawcy mogą używać tej konfiguracji, ale nie będą mogli nią zarządzać.</span><span class="sxs-lookup"><span data-stu-id="36c05-120">Other providers can use this configuration, but will not be able to maintain it.</span></span>  

4. <span data-ttu-id="36c05-121">Kliknij przycisk „Utwórz konfigurację”, aby dokończyć zadanie tworzenia konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="36c05-121">Click 'Create configuration' button to complete the configuration creation task</span></span>

## <a name="create-a-data-model"></a><span data-ttu-id="36c05-122">Tworzenie modelu danych</span><span class="sxs-lookup"><span data-stu-id="36c05-122">Create a data model</span></span>
<span data-ttu-id="36c05-123">Tworzysz nowy model danych dla wybranej konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="36c05-123">You're creating a new data model for the selected configuration.</span></span> <span data-ttu-id="36c05-124">Ta wersja konfiguracji będzie miała stan Wersja robocza.</span><span class="sxs-lookup"><span data-stu-id="36c05-124">This configuration version will have a status of Draft.</span></span>  
1. <span data-ttu-id="36c05-125">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="36c05-125">Click Designer.</span></span>

## <a name="define-the-structure-of-a-party-participating-in-a-payment-process"></a><span data-ttu-id="36c05-126">Definiowanie struktury strony uczestniczącej w procesie płatności</span><span class="sxs-lookup"><span data-stu-id="36c05-126">Define the structure of a party participating in a payment process</span></span>
1. <span data-ttu-id="36c05-127">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="36c05-127">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="36c05-128">W polu Nazwa wpisz „Strona”.</span><span class="sxs-lookup"><span data-stu-id="36c05-128">In the Name field, type 'Party'.</span></span>
3. <span data-ttu-id="36c05-129">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="36c05-129">Click Add.</span></span>
4. <span data-ttu-id="36c05-130">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="36c05-130">Click New to open the drop dialog.</span></span>
5. <span data-ttu-id="36c05-131">W polu Nazwa wpisz „Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="36c05-131">In the Name field, type 'Name'.</span></span>
6. <span data-ttu-id="36c05-132">W polu Typ elementu wybierz opcję „Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="36c05-132">In the Item type field, select 'String'.</span></span>
7. <span data-ttu-id="36c05-133">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="36c05-133">Click Add.</span></span>
8. <span data-ttu-id="36c05-134">W polu Znajdź wpisz „Strona”.</span><span class="sxs-lookup"><span data-stu-id="36c05-134">In the Find field, type 'Party'.</span></span>
9. <span data-ttu-id="36c05-135">Kliknij opcję Znajdź poprzednie.</span><span class="sxs-lookup"><span data-stu-id="36c05-135">Click Find previous.</span></span>

## <a name="define-the-bank-structure-for-this-model"></a><span data-ttu-id="36c05-136">Definiowanie struktury banku dla tego modelu</span><span class="sxs-lookup"><span data-stu-id="36c05-136">Define the bank structure for this model</span></span>
1. <span data-ttu-id="36c05-137">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="36c05-137">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="36c05-138">W polu Nazwa wpisz „Agent”.</span><span class="sxs-lookup"><span data-stu-id="36c05-138">In the Name field, type 'Agent'.</span></span>
3. <span data-ttu-id="36c05-139">W polu Typ elementu wybierz opcję „Rekord”.</span><span class="sxs-lookup"><span data-stu-id="36c05-139">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="36c05-140">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="36c05-140">Click Add.</span></span>
5. <span data-ttu-id="36c05-141">W polu Opis wpisz „Instytucja finansowa (np. bank) obsługująca konto strony (dłużnika/wierzyciela).”.</span><span class="sxs-lookup"><span data-stu-id="36c05-141">In the Description field, enter 'Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).'.</span></span>

    <span data-ttu-id="36c05-142">Instytucja finansowa (np. bank) obsługująca konto strony (dłużnika/wierzyciela).</span><span class="sxs-lookup"><span data-stu-id="36c05-142">Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).</span></span>  

6. <span data-ttu-id="36c05-143">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="36c05-143">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="36c05-144">W polu Nazwa wpisz „Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="36c05-144">In the Name field, type 'Name'.</span></span> 
8. <span data-ttu-id="36c05-145">W polu Typ elementu wybierz opcję „Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="36c05-145">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="36c05-146">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="36c05-146">Click Add.</span></span>
10. <span data-ttu-id="36c05-147">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="36c05-147">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="36c05-148">W polu Nazwa wpisz „SWIFT”.</span><span class="sxs-lookup"><span data-stu-id="36c05-148">In the Name field, type 'SWIFT'.</span></span>
12. <span data-ttu-id="36c05-149">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="36c05-149">Click Add.</span></span>
13. <span data-ttu-id="36c05-150">W polu Opis wpisz „Kod identyfikacyjny banku”.</span><span class="sxs-lookup"><span data-stu-id="36c05-150">In the Description field, enter 'Bank identification code'.</span></span> 
14. <span data-ttu-id="36c05-151">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="36c05-151">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="36c05-152">W polu Nazwa wpisz „RoutingNumber”.</span><span class="sxs-lookup"><span data-stu-id="36c05-152">In the Name field, type 'RoutingNumber'.</span></span>
16. <span data-ttu-id="36c05-153">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="36c05-153">Click Add.</span></span>
17. <span data-ttu-id="36c05-154">W polu Opis wpisz „Kod banku”.</span><span class="sxs-lookup"><span data-stu-id="36c05-154">In the Description field, enter 'Routing number'.</span></span>
18. <span data-ttu-id="36c05-155">Kliknij opcję Znajdź poprzednie.</span><span class="sxs-lookup"><span data-stu-id="36c05-155">Click Find previous.</span></span>

## <a name="define-the-bank-account-structure-for-this-model"></a><span data-ttu-id="36c05-156">Definiowanie struktury konta banku dla tego modelu</span><span class="sxs-lookup"><span data-stu-id="36c05-156">Define the bank account structure for this model</span></span>
1. <span data-ttu-id="36c05-157">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="36c05-157">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="36c05-158">W polu Nazwa wpisz „Konto”.</span><span class="sxs-lookup"><span data-stu-id="36c05-158">In the Name field, type 'Account'.</span></span> 
3. <span data-ttu-id="36c05-159">W polu Typ elementu wybierz opcję „Rekord”.</span><span class="sxs-lookup"><span data-stu-id="36c05-159">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="36c05-160">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="36c05-160">Click Add.</span></span>
5. <span data-ttu-id="36c05-161">W polu Opis wpisz „Identyfikator konta strony w instytucji finansowej (na przykład w banku).”.</span><span class="sxs-lookup"><span data-stu-id="36c05-161">In the Description field, enter 'Identification of an account of a party in a financial institution (for instance, a bank).'.</span></span>

    <span data-ttu-id="36c05-162">Identyfikator konta strony w instytucji finansowej (na przykład w banku).</span><span class="sxs-lookup"><span data-stu-id="36c05-162">Identification of an account of a party in a financial institution (for instance, a bank).</span></span>  

6. <span data-ttu-id="36c05-163">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="36c05-163">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="36c05-164">W polu Nazwa wpisz „Waluta”.</span><span class="sxs-lookup"><span data-stu-id="36c05-164">In the Name field, type 'Currency'.</span></span> 
8. <span data-ttu-id="36c05-165">W polu Typ elementu wybierz opcję „Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="36c05-165">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="36c05-166">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="36c05-166">Click Add.</span></span>
10. <span data-ttu-id="36c05-167">W polu Opis wpisz „Kod waluty”.</span><span class="sxs-lookup"><span data-stu-id="36c05-167">In the Description field, enter 'Currency code'.</span></span>
11. <span data-ttu-id="36c05-168">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="36c05-168">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="36c05-169">W polu Nazwa wpisz „Numer”.</span><span class="sxs-lookup"><span data-stu-id="36c05-169">In the Name field, type 'Number'.</span></span> 
13. <span data-ttu-id="36c05-170">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="36c05-170">Click Add.</span></span>
14. <span data-ttu-id="36c05-171">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="36c05-171">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="36c05-172">W polu Nazwa wpisz „IBAN”.</span><span class="sxs-lookup"><span data-stu-id="36c05-172">In the Name field, type 'IBAN'.</span></span> 
16. <span data-ttu-id="36c05-173">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="36c05-173">Click Add.</span></span>
17. <span data-ttu-id="36c05-174">W polu Opis wpisz „Międzynarodowy numer konta bankowego”.</span><span class="sxs-lookup"><span data-stu-id="36c05-174">In the Description field, enter 'International bank account number'.</span></span>

## <a name="define-the-payment-message-structure-for-credit-transfer-payment-type"></a><span data-ttu-id="36c05-175">Definiowanie struktury komunikatu płatności dla płatności poleceniem przelewu</span><span class="sxs-lookup"><span data-stu-id="36c05-175">Define the payment message structure for credit transfer payment type</span></span>
1. <span data-ttu-id="36c05-176">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="36c05-176">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="36c05-177">W polu Nowy węzeł jako wpisz „Element główny modelu”.</span><span class="sxs-lookup"><span data-stu-id="36c05-177">In the New node as a field, enter 'Model root'.</span></span>
3. <span data-ttu-id="36c05-178">W polu Nazwa wpisz „CustomerCreditTransferInitiation”.</span><span class="sxs-lookup"><span data-stu-id="36c05-178">In the Name field, type 'CustomerCreditTransferInitiation'.</span></span>
4. <span data-ttu-id="36c05-179">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="36c05-179">Click Add.</span></span>
5. <span data-ttu-id="36c05-180">W polu Znajdź wpisz „CustomerCreditTransferInitiation”.</span><span class="sxs-lookup"><span data-stu-id="36c05-180">In the Find field, type 'CustomerCreditTransferInitiation'.</span></span> 
6. <span data-ttu-id="36c05-181">Kliknij opcję Znajdź poprzednie.</span><span class="sxs-lookup"><span data-stu-id="36c05-181">Click Find previous.</span></span>
7. <span data-ttu-id="36c05-182">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="36c05-182">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="36c05-183">W polu Nazwa wpisz „MessageIdentification”.</span><span class="sxs-lookup"><span data-stu-id="36c05-183">In the Name field, type 'MessageIdentification'.</span></span> 
9. <span data-ttu-id="36c05-184">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="36c05-184">Click Add.</span></span>
10. <span data-ttu-id="36c05-185">W polu Opis wpisz „Odwołanie bezpośrednie przypisane przez stronę zlecającą (i wysłane do następnej strony) w celu identyfikacji komunikatu.”.</span><span class="sxs-lookup"><span data-stu-id="36c05-185">In the Description field, enter 'The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.'.</span></span>

    <span data-ttu-id="36c05-186">Odwołanie bezpośrednie przypisane przez stronę zlecającą (i wysłane do następnej strony) w celu identyfikacji komunikatu.</span><span class="sxs-lookup"><span data-stu-id="36c05-186">The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.</span></span>  

11. <span data-ttu-id="36c05-187">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="36c05-187">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="36c05-188">W polu Nazwa wpisz „ProcessingDateTime”.</span><span class="sxs-lookup"><span data-stu-id="36c05-188">In the Name field, type 'ProcessingDateTime'.</span></span>
13. <span data-ttu-id="36c05-189">W polu Typ elementu wybierz opcję „DateTime”.</span><span class="sxs-lookup"><span data-stu-id="36c05-189">In the Item type field, select 'DateTime'.</span></span>
14. <span data-ttu-id="36c05-190">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="36c05-190">Click Add.</span></span>
15. <span data-ttu-id="36c05-191">W polu Opis wpisz „Data i godzina utworzenia komunikatu płatności.”.</span><span class="sxs-lookup"><span data-stu-id="36c05-191">In the Description field, enter 'Date and time at which the payment message was created.'.</span></span> 
16. <span data-ttu-id="36c05-192">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="36c05-192">Click New to open the drop dialog.</span></span>

    <span data-ttu-id="36c05-193">Definiowanie struktury transakcji płatności dla tego modelu.</span><span class="sxs-lookup"><span data-stu-id="36c05-193">Define the payment transaction structure for this model.</span></span>  

17. <span data-ttu-id="36c05-194">W polu Nazwa wpisz „Płatności”.</span><span class="sxs-lookup"><span data-stu-id="36c05-194">In the Name field, type 'Payments'.</span></span>
18. <span data-ttu-id="36c05-195">W polu Typ elementu wybierz opcję „Lista rekordów”.</span><span class="sxs-lookup"><span data-stu-id="36c05-195">In the Item type field, select 'Record list'.</span></span>
19. <span data-ttu-id="36c05-196">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="36c05-196">Click Add.</span></span>
20. <span data-ttu-id="36c05-197">W polu Opis wpisz „Wiersze płatności w bieżącym komunikacie”.</span><span class="sxs-lookup"><span data-stu-id="36c05-197">In the Description field, enter 'Payment lines of the current message'.</span></span>
21. <span data-ttu-id="36c05-198">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="36c05-198">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="36c05-199">W polu Nazwa wpisz „Wierzyciel”.</span><span class="sxs-lookup"><span data-stu-id="36c05-199">In the Name field, type 'Creditor'.</span></span> 
23. <span data-ttu-id="36c05-200">W polu Typ elementu wybierz opcję „Rekord”.</span><span class="sxs-lookup"><span data-stu-id="36c05-200">In the Item type field, select 'Record'.</span></span>
24. <span data-ttu-id="36c05-201">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="36c05-201">Click Add.</span></span>
25. <span data-ttu-id="36c05-202">W polu Opis wpisz „Strona, do której należy przesłać kwotę pieniężną.”.</span><span class="sxs-lookup"><span data-stu-id="36c05-202">In the Description field, enter 'Party to which an amount of money is due.'.</span></span> 
26. <span data-ttu-id="36c05-203">Kliknij opcję Przełącz odwołanie do elementu.</span><span class="sxs-lookup"><span data-stu-id="36c05-203">Click Switch item reference.</span></span>
27. <span data-ttu-id="36c05-204">W polu Znajdź wpisz „Strona”.</span><span class="sxs-lookup"><span data-stu-id="36c05-204">In the Find field, type 'Party'.</span></span>
28. <span data-ttu-id="36c05-205">Kliknij przycisk Znajdź następny.</span><span class="sxs-lookup"><span data-stu-id="36c05-205">Click Find next.</span></span>
29. <span data-ttu-id="36c05-206">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="36c05-206">Click OK.</span></span>
30. <span data-ttu-id="36c05-207">W polu Znajdź wpisz „Płatności”.</span><span class="sxs-lookup"><span data-stu-id="36c05-207">In the Find field, type 'Payments'.</span></span>
31. <span data-ttu-id="36c05-208">Kliknij przycisk Znajdź następny.</span><span class="sxs-lookup"><span data-stu-id="36c05-208">Click Find next.</span></span>
32. <span data-ttu-id="36c05-209">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="36c05-209">Click New to open the drop dialog.</span></span>
33. <span data-ttu-id="36c05-210">W polu Nazwa wpisz „Dłużnik”.</span><span class="sxs-lookup"><span data-stu-id="36c05-210">In the Name field, type 'Debtor'.</span></span> 
34. <span data-ttu-id="36c05-211">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="36c05-211">Click Add.</span></span>
35. <span data-ttu-id="36c05-212">W polu Opis wpisz „Strona będąca dłużna kwotę pieniężną (ostatecznemu) wierzycielowi.”.</span><span class="sxs-lookup"><span data-stu-id="36c05-212">In the Description field, enter 'Party that owes an amount of money to the (ultimate) creditor.'.</span></span>
36. <span data-ttu-id="36c05-213">Kliknij opcję Przełącz odwołanie do elementu.</span><span class="sxs-lookup"><span data-stu-id="36c05-213">Click Switch item reference.</span></span>
37. <span data-ttu-id="36c05-214">W polu Znajdź wpisz „Strona”.</span><span class="sxs-lookup"><span data-stu-id="36c05-214">In the Find field, type 'Party'.</span></span>
38. <span data-ttu-id="36c05-215">Kliknij przycisk Znajdź następny.</span><span class="sxs-lookup"><span data-stu-id="36c05-215">Click Find next.</span></span>
39. <span data-ttu-id="36c05-216">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="36c05-216">Click OK.</span></span>
40. <span data-ttu-id="36c05-217">Kliknij przycisk Znajdź następny.</span><span class="sxs-lookup"><span data-stu-id="36c05-217">Click Find next.</span></span>
41. <span data-ttu-id="36c05-218">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="36c05-218">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="36c05-219">W polu Nazwa wpisz „Opis”.</span><span class="sxs-lookup"><span data-stu-id="36c05-219">In the Name field, type 'Description'.</span></span>
43. <span data-ttu-id="36c05-220">W polu Typ elementu wybierz opcję „Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="36c05-220">In the Item type field, select 'String'.</span></span>
44. <span data-ttu-id="36c05-221">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="36c05-221">Click Add.</span></span>
45. <span data-ttu-id="36c05-222">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="36c05-222">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="36c05-223">W polu Nazwa wpisz „Waluta”.</span><span class="sxs-lookup"><span data-stu-id="36c05-223">In the Name field, type 'Currency'.</span></span>
47. <span data-ttu-id="36c05-224">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="36c05-224">Click Add.</span></span>
48. <span data-ttu-id="36c05-225">W polu Opis wpisz „Kod waluty”.</span><span class="sxs-lookup"><span data-stu-id="36c05-225">In the Description field, enter 'Currency code'.</span></span>
49. <span data-ttu-id="36c05-226">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="36c05-226">Click New to open the drop dialog.</span></span>
50. <span data-ttu-id="36c05-227">W polu Nazwa wpisz „TransactionDate”.</span><span class="sxs-lookup"><span data-stu-id="36c05-227">In the Name field, type 'TransactionDate'.</span></span> 
51. <span data-ttu-id="36c05-228">W polu Typ elementu wybierz opcję „Data”.</span><span class="sxs-lookup"><span data-stu-id="36c05-228">In the Item type field, select 'Date'.</span></span>
52. <span data-ttu-id="36c05-229">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="36c05-229">Click Add.</span></span>
53. <span data-ttu-id="36c05-230">W polu Opis wpisz „Data transakcji”.</span><span class="sxs-lookup"><span data-stu-id="36c05-230">In the Description field, enter 'Transaction date'.</span></span> 
54. <span data-ttu-id="36c05-231">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="36c05-231">Click New to open the drop dialog.</span></span>
55. <span data-ttu-id="36c05-232">W polu Nazwa wpisz „InstructedAmount”.</span><span class="sxs-lookup"><span data-stu-id="36c05-232">In the Name field, type 'InstructedAmount'.</span></span>  
56. <span data-ttu-id="36c05-233">W polu Typ elementu wybierz opcję „Liczba rzeczywista”.</span><span class="sxs-lookup"><span data-stu-id="36c05-233">In the Item type field, select 'Real'.</span></span>
57. <span data-ttu-id="36c05-234">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="36c05-234">Click Add.</span></span>
58. <span data-ttu-id="36c05-235">W polu Opis wpisz „Kwota pieniężna do przekazania między dłużnikiem a wierzycielem przed potrąceniem opłat.</span><span class="sxs-lookup"><span data-stu-id="36c05-235">In the Description field, enter 'The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="36c05-236">Kwota powinna być wyrażona w walucie podanej przez stronę inicjującą.”.</span><span class="sxs-lookup"><span data-stu-id="36c05-236">The amount should be expressed in the currency as ordered by the initiating party.'.</span></span>

    <span data-ttu-id="36c05-237">Kwota pieniężna do przekazania między dłużnikiem a wierzycielem przed potrąceniem opłat.</span><span class="sxs-lookup"><span data-stu-id="36c05-237">The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="36c05-238">Kwota powinna być wyrażona w walucie podanej przez stronę inicjującą.</span><span class="sxs-lookup"><span data-stu-id="36c05-238">The amount should be expressed in the currency as ordered by the initiating party.</span></span>  

59. <span data-ttu-id="36c05-239">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="36c05-239">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="36c05-240">W polu Nazwa wpisz „End2EndID”.</span><span class="sxs-lookup"><span data-stu-id="36c05-240">In the Name field, type 'End2EndID'.</span></span> 
61. <span data-ttu-id="36c05-241">W polu Typ elementu wybierz opcję „Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="36c05-241">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="36c05-242">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="36c05-242">Click Add.</span></span>
63. <span data-ttu-id="36c05-243">W polu Opis wpisz „Unikatowy identyfikator przypisywany przez stronę inicjującą.</span><span class="sxs-lookup"><span data-stu-id="36c05-243">In the Description field, enter 'The unique identification assigned by the initiating party.</span></span> <span data-ttu-id="36c05-244">Identyfikator jest przekazywany bez zmian w całym łańcuchu operacji.”.</span><span class="sxs-lookup"><span data-stu-id="36c05-244">This identification is passed on, unchanged, throughout the entire end-to-end chain.'.</span></span> 
64. <span data-ttu-id="36c05-245">W polu Nazwa wpisz „PaymentModel”.</span><span class="sxs-lookup"><span data-stu-id="36c05-245">In the Name field, type 'PaymentModel'.</span></span>

    <span data-ttu-id="36c05-246">Nazwa PaymentModel jest dopasowana do wstępnie zdefiniowanych interfejsów formularzy płatności.</span><span class="sxs-lookup"><span data-stu-id="36c05-246">The PaymentModel name aligns with predefined interfaces of payment forms.</span></span>  

65. <span data-ttu-id="36c05-247">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="36c05-247">Click Save.</span></span>
66. <span data-ttu-id="36c05-248">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="36c05-248">Close the page.</span></span>

