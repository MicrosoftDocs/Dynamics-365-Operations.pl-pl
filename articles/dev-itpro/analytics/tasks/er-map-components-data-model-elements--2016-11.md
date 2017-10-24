--- 
title: "Mapowanie składników utworzonego formatu na elementy modelu danych na potrzeby raportowania elektronicznego (ER)"
description: "W poniższej procedurze pokazano, jak użytkownik posiadający rolę Administrator systemu lub Deweloper raportowania elektronicznego może mapować elementy modelu danych na składniki utworzonej konfiguracji raportowania elektronicznego (ER), która definiuje format dokumentu elektronicznego dla domeny biznesowej płatności."
author: NickSelin
manager: AnnBe
ms.date: 02/27/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 1c81a1268a56164e0d4465359a0f9ec425ee7c31
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="map-components-of-the-created-format-to-data-model-elements-for-electronic-reporting-er"></a><span data-ttu-id="2b342-103">Mapowanie składników utworzonego formatu na elementy modelu danych na potrzeby raportowania elektronicznego (ER)</span><span class="sxs-lookup"><span data-stu-id="2b342-103">Map components of the created format to data model elements for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2b342-104">W poniższej procedurze pokazano, jak użytkownik posiadający rolę Administrator systemu lub Deweloper raportowania elektronicznego może mapować elementy modelu danych na składniki utworzonej konfiguracji raportowania elektronicznego (ER), która definiuje format dokumentu elektronicznego dla domeny biznesowej płatności.</span><span class="sxs-lookup"><span data-stu-id="2b342-104">The following procedure shows how a user in either the System administrator or Electronic reporting developer role can map data model elements to components of the created Electronic reporting (ER) configuration, which defines an electronic document format for the payments business domain.</span></span> <span data-ttu-id="2b342-105">Ten format będzie używany później do generowania dokumentów elektronicznych przeznaczonych do przetwarzania płatności.</span><span class="sxs-lookup"><span data-stu-id="2b342-105">This format will be used later to generate electronic documents for processing payments.</span></span> <span data-ttu-id="2b342-106">W tym przykładzie utworzysz konfigurację formatu dla przykładowej firmy „Litware, Inc.”.</span><span class="sxs-lookup"><span data-stu-id="2b342-106">In this example, you will create a format configuration for the sample company, ‘Litware, Inc.’.</span></span> <span data-ttu-id="2b342-107">Podane kroki można wykonać w dowolnej firmie, ponieważ konfiguracje ER są współużytkowane przez wszystkie firmy.</span><span class="sxs-lookup"><span data-stu-id="2b342-107">These steps can be performed in any company as ER configurations are shared for all companies.</span></span> <span data-ttu-id="2b342-108">Aby wykonać te kroki, należy najpierw wykonać kroki przewodnika po zadaniu „Tworzenie konfiguracji formatu”.</span><span class="sxs-lookup"><span data-stu-id="2b342-108">To complete these steps, you must first complete the steps in the “Create a format configuration” task guide.</span></span>


## <a name="select-a-format-configuration"></a><span data-ttu-id="2b342-109">Wybieranie konfiguracji formatu</span><span class="sxs-lookup"><span data-stu-id="2b342-109">Select a format configuration</span></span>
1. <span data-ttu-id="2b342-110">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="2b342-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="2b342-111">Kliknij opcję Konfiguracje raportowania.</span><span class="sxs-lookup"><span data-stu-id="2b342-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="2b342-112">W drzewie rozwiń węzeł „Płatności (model uproszczony)”.</span><span class="sxs-lookup"><span data-stu-id="2b342-112">In the tree, expand 'Payments (simplified model)'.</span></span>
4. <span data-ttu-id="2b342-113">W drzewie zaznacz element „Płatności (model uproszczony)\BACS (fikcyjny brytyjski)”.</span><span class="sxs-lookup"><span data-stu-id="2b342-113">In the tree, select 'Payments (simplified model)\BACS (UK fictitious)'.</span></span>
5. <span data-ttu-id="2b342-114">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="2b342-114">Click Designer.</span></span>

## <a name="map-format-components-to-data-model-elements"></a><span data-ttu-id="2b342-115">Zmapuj składniki formatu na elementy modelu danych.</span><span class="sxs-lookup"><span data-stu-id="2b342-115">Map format components to data model elements</span></span>
1. <span data-ttu-id="2b342-116">Kliknij przycisk Rozwiń/zwiń.</span><span class="sxs-lookup"><span data-stu-id="2b342-116">Click Expand/collapse.</span></span>
2. <span data-ttu-id="2b342-117">Kliknij kartę Mapowanie.</span><span class="sxs-lookup"><span data-stu-id="2b342-117">Click the Mapping tab.</span></span>
3. <span data-ttu-id="2b342-118">W drzewie rozwiń model„”</span><span class="sxs-lookup"><span data-stu-id="2b342-118">In the tree, expand 'model'.</span></span>
4. <span data-ttu-id="2b342-119">W drzewie zaznacz element „Xml\Komunikat\ProcessingDate\DateTime”.</span><span class="sxs-lookup"><span data-stu-id="2b342-119">In the tree, select 'Xml\Message\ProcessingDate\DateTime'.</span></span>
5. <span data-ttu-id="2b342-120">W drzewie zaznacz element „model\ProcessingDateTime”.</span><span class="sxs-lookup"><span data-stu-id="2b342-120">In the tree, select 'model\ProcessingDateTime'.</span></span>
6. <span data-ttu-id="2b342-121">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="2b342-121">Click Bind.</span></span>
7. <span data-ttu-id="2b342-122">W drzewie zaznacz element „Xml\Komunikat\MessageId\Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="2b342-122">In the tree, select 'Xml\Message\MessageId\String'.</span></span>
8. <span data-ttu-id="2b342-123">W drzewie zaznacz element „model\MessageIdentification”.</span><span class="sxs-lookup"><span data-stu-id="2b342-123">In the tree, select 'model\MessageIdentification'.</span></span>
9. <span data-ttu-id="2b342-124">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="2b342-124">Click Bind.</span></span>
10. <span data-ttu-id="2b342-125">W drzewie rozwiń węzeł „model\Płatności”.</span><span class="sxs-lookup"><span data-stu-id="2b342-125">In the tree, expand 'model\Payments'.</span></span>
11. <span data-ttu-id="2b342-126">W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Kwota\Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="2b342-126">In the tree, select 'Xml\Message\Payments\Item\Amount\String'.</span></span>
12. <span data-ttu-id="2b342-127">W drzewie zaznacz element „model\Płatności\InstructedAmount”.</span><span class="sxs-lookup"><span data-stu-id="2b342-127">In the tree, select 'model\Payments\InstructedAmount'.</span></span>
13. <span data-ttu-id="2b342-128">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="2b342-128">Click Bind.</span></span>
14. <span data-ttu-id="2b342-129">W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\TransDate\DateTime”.</span><span class="sxs-lookup"><span data-stu-id="2b342-129">In the tree, select 'Xml\Message\Payments\Item\TransDate\DateTime'.</span></span>
15. <span data-ttu-id="2b342-130">W drzewie zaznacz element „model\Płatności\TransactionDate”.</span><span class="sxs-lookup"><span data-stu-id="2b342-130">In the tree, select 'model\Payments\TransactionDate'.</span></span>
16. <span data-ttu-id="2b342-131">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="2b342-131">Click Bind.</span></span>
17. <span data-ttu-id="2b342-132">W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Opis\Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="2b342-132">In the tree, select 'Xml\Message\Payments\Item\Description\String'.</span></span>
18. <span data-ttu-id="2b342-133">W drzewie zaznacz element „model\Płatności\Opis”.</span><span class="sxs-lookup"><span data-stu-id="2b342-133">In the tree, select 'model\Payments\Description'.</span></span>
19. <span data-ttu-id="2b342-134">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="2b342-134">Click Bind.</span></span>
20. <span data-ttu-id="2b342-135">W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Waluta\Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="2b342-135">In the tree, select 'Xml\Message\Payments\Item\Currency\String'.</span></span>
21. <span data-ttu-id="2b342-136">W drzewie zaznacz element „model\Płatności\Waluta”.</span><span class="sxs-lookup"><span data-stu-id="2b342-136">In the tree, select 'model\Payments\Currency'.</span></span>
22. <span data-ttu-id="2b342-137">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="2b342-137">Click Bind.</span></span>
23. <span data-ttu-id="2b342-138">W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Identyfikator”.</span><span class="sxs-lookup"><span data-stu-id="2b342-138">In the tree, select 'Xml\Message\Payments\Item\Id'.</span></span>
24. <span data-ttu-id="2b342-139">W drzewie zaznacz element „model\Płatności\End2EndID”.</span><span class="sxs-lookup"><span data-stu-id="2b342-139">In the tree, select 'model\Payments\End2EndID'.</span></span>
25. <span data-ttu-id="2b342-140">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="2b342-140">Click Bind.</span></span>
26. <span data-ttu-id="2b342-141">W drzewie rozwiń węzeł „model\Płatności\Wierzyciel”.</span><span class="sxs-lookup"><span data-stu-id="2b342-141">In the tree, expand 'model\Payments\Creditor'.</span></span>
27. <span data-ttu-id="2b342-142">W drzewie rozwiń „model\Płatności\Konto wierzyciela".</span><span class="sxs-lookup"><span data-stu-id="2b342-142">In the tree, expand 'model\Payments\Creditor\Account'.</span></span>
28. <span data-ttu-id="2b342-143">W drzewie rozwiń „model\Płatności\Wierzyciel\Agent".</span><span class="sxs-lookup"><span data-stu-id="2b342-143">In the tree, expand 'model\Payments\Creditor\Agent'.</span></span>
29. <span data-ttu-id="2b342-144">W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Dostawca\Nazwa\Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="2b342-144">In the tree, select 'Xml\Message\Payments\Item\Vendor\Name\String'.</span></span>
30. <span data-ttu-id="2b342-145">W drzewie zaznacz element „model\Płatności\Wierzyciel\Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="2b342-145">In the tree, select 'model\Payments\Creditor\Name'.</span></span>
31. <span data-ttu-id="2b342-146">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="2b342-146">Click Bind.</span></span>
32. <span data-ttu-id="2b342-147">W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Dostawca\Bank\RoutingNumber\Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="2b342-147">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber\String'.</span></span>
33. <span data-ttu-id="2b342-148">W drzewie zaznacz element „model\Płatności\Wierzyciel\Agent\RoutingNumber”.</span><span class="sxs-lookup"><span data-stu-id="2b342-148">In the tree, select 'model\Payments\Creditor\Agent\RoutingNumber'.</span></span>
34. <span data-ttu-id="2b342-149">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="2b342-149">Click Bind.</span></span>
35. <span data-ttu-id="2b342-150">W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Dostawca\Bank\AccountNumber\Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="2b342-150">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\AccountNumber\String'.</span></span>
36. <span data-ttu-id="2b342-151">W drzewie zaznacz element „model\Płatności\Wierzyciel\Konto\Numer”.</span><span class="sxs-lookup"><span data-stu-id="2b342-151">In the tree, select 'model\Payments\Creditor\Account\Number'.</span></span>
37. <span data-ttu-id="2b342-152">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="2b342-152">Click Bind.</span></span>
38. <span data-ttu-id="2b342-153">W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Płatnik\Nazwa\Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="2b342-153">In the tree, select 'Xml\Message\Payments\Item\Payer\Name\String'.</span></span>
39. <span data-ttu-id="2b342-154">W drzewie rozwiń węzeł „model\Płatności\Dłużnik”.</span><span class="sxs-lookup"><span data-stu-id="2b342-154">In the tree, expand 'model\Payments\Debtor'.</span></span>
40. <span data-ttu-id="2b342-155">W drzewie rozwiń „model\Płatności\Dłużnik\Konto".</span><span class="sxs-lookup"><span data-stu-id="2b342-155">In the tree, expand 'model\Payments\Debtor\Account'.</span></span>
41. <span data-ttu-id="2b342-156">W drzewie rozwiń „model\Płatności\Dłużnik\Agent".</span><span class="sxs-lookup"><span data-stu-id="2b342-156">In the tree, expand 'model\Payments\Debtor\Agent'.</span></span>
42. <span data-ttu-id="2b342-157">W drzewie zaznacz element „model\Płatności\Dłużnik\Nazwa”.</span><span class="sxs-lookup"><span data-stu-id="2b342-157">In the tree, select 'model\Payments\Debtor\Name'.</span></span>
43. <span data-ttu-id="2b342-158">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="2b342-158">Click Bind.</span></span>
44. <span data-ttu-id="2b342-159">W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Płatnik\Bank\RoutingNumber\Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="2b342-159">In the tree, select 'Xml\Message\Payments\Item\Payer\Bank\RoutingNumber\String'.</span></span>
45. <span data-ttu-id="2b342-160">W drzewie zaznacz element „model\Płatności\Dłużnik\Agent\RoutingNumber”.</span><span class="sxs-lookup"><span data-stu-id="2b342-160">In the tree, select 'model\Payments\Debtor\Agent\RoutingNumber'.</span></span>
46. <span data-ttu-id="2b342-161">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="2b342-161">Click Bind.</span></span>
47. <span data-ttu-id="2b342-162">W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Płatnik\Bank\AccountNumber\Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="2b342-162">In the tree, select 'Xml\Message\Payments\Item\Payer\Bank\AccountNumber\String'.</span></span>
48. <span data-ttu-id="2b342-163">W drzewie zaznacz element „model\Płatności\Dłużnik\Konto\Numer”.</span><span class="sxs-lookup"><span data-stu-id="2b342-163">In the tree, select 'model\Payments\Debtor\Account\Number'.</span></span>
49. <span data-ttu-id="2b342-164">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="2b342-164">Click Bind.</span></span>
50. <span data-ttu-id="2b342-165">W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar”.</span><span class="sxs-lookup"><span data-stu-id="2b342-165">In the tree, select 'Xml\Message\Payments\Item'.</span></span>
51. <span data-ttu-id="2b342-166">W drzewie zaznacz element „model\Płatności”.</span><span class="sxs-lookup"><span data-stu-id="2b342-166">In the tree, select 'model\Payments'.</span></span>
52. <span data-ttu-id="2b342-167">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="2b342-167">Click Bind.</span></span>
53. <span data-ttu-id="2b342-168">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="2b342-168">Click Save.</span></span>

## <a name="validate-format-mapping"></a><span data-ttu-id="2b342-169">Sprawdzanie poprawności mapowania formatu.</span><span class="sxs-lookup"><span data-stu-id="2b342-169">Validate format mapping</span></span>
1. <span data-ttu-id="2b342-170">Kliknij przycisk Sprawdź poprawność.</span><span class="sxs-lookup"><span data-stu-id="2b342-170">Click Validate.</span></span>
    * <span data-ttu-id="2b342-171">Sprawdź poprawność nowego mapowania, aby się upewnić, że wszystkie powiązania są w porządku.</span><span class="sxs-lookup"><span data-stu-id="2b342-171">Validate the new mapping to ensure that all bindings are okay.</span></span>  
2. <span data-ttu-id="2b342-172">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2b342-172">Close the page.</span></span>

## <a name="change-status-of-the-current-version-of-format-configuration"></a><span data-ttu-id="2b342-173">Zmień stan bieżącej wersji konfiguracji formatu.</span><span class="sxs-lookup"><span data-stu-id="2b342-173">Change status of the current version of format configuration</span></span>
    * <span data-ttu-id="2b342-174">W następnych krokach zmienisz stan konfiguracji formatu z Wersja robocza na Zakończony, aby udostępnić go dla operacji generowania dokumentu płatniczego.</span><span class="sxs-lookup"><span data-stu-id="2b342-174">In the next steps, you’ll change the status of the format configuration from Draft to Completed to make it available for payment document generation.</span></span>  
1. <span data-ttu-id="2b342-175">Kliknij przycisk Zmień stan.</span><span class="sxs-lookup"><span data-stu-id="2b342-175">Click Change status.</span></span>
2. <span data-ttu-id="2b342-176">Kliknij przycisk Wykonaj.</span><span class="sxs-lookup"><span data-stu-id="2b342-176">Click Complete.</span></span>
3. <span data-ttu-id="2b342-177">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="2b342-177">In the Description field, type a value.</span></span>
    * <span data-ttu-id="2b342-178">Na przykład „wersja 1”.</span><span class="sxs-lookup"><span data-stu-id="2b342-178">For example, 'version 1'.</span></span>  
4. <span data-ttu-id="2b342-179">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="2b342-179">Click OK.</span></span>
5. <span data-ttu-id="2b342-180">Wybierz ukończoną wersję bieżącej konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="2b342-180">Select completed version of the current configuration.</span></span>
    * <span data-ttu-id="2b342-181">Należy zauważyć, że konfiguracja została zapisana jako ukończona wersja 1.1. To jest wersja 1 formatu, który jest oparty na wersji 1 modelu danych.</span><span class="sxs-lookup"><span data-stu-id="2b342-181">Note that the configuration is saved as completed version 1.1: version 1 of the format based on the version 1 of the data model.</span></span>  

## <a name="define-effective-date-for-completed-version-of-format"></a><span data-ttu-id="2b342-182">Określ datę wejścia w życie ukończonej wersji formatu.</span><span class="sxs-lookup"><span data-stu-id="2b342-182">Define effective date for completed version of format</span></span>
    * <span data-ttu-id="2b342-183">Każdą wersję formatu można skonfigurować jako dostępną do użycia począwszy od określonej daty.</span><span class="sxs-lookup"><span data-stu-id="2b342-183">Each format version can be configured as available for usage starting from a certain date.</span></span> <span data-ttu-id="2b342-184">Kiedy więcej niż jedna wersja formatu jest aktywna w określonym dniu, do użycia zostanie wybrany najnowszy forma (na podstawie numeru wersji).</span><span class="sxs-lookup"><span data-stu-id="2b342-184">When more than one format version is active on a certain date, the latest format (based on version number) will be selected for usage.</span></span> <span data-ttu-id="2b342-185">Do wyboru odpowiedniej wersji jest używana wartość daty sesji.</span><span class="sxs-lookup"><span data-stu-id="2b342-185">The session date value is used for proper version selection.</span></span>  

## <a name="restrict-access-to-created-format-from-companies"></a><span data-ttu-id="2b342-186">Ograniczanie dostępu do utworzonego formatu z firm</span><span class="sxs-lookup"><span data-stu-id="2b342-186">Restrict access to created format from companies</span></span>
1. <span data-ttu-id="2b342-187">Rozwiń sekcję Kody ISO krajów/regionów.</span><span class="sxs-lookup"><span data-stu-id="2b342-187">Expand the ISO Country/region codes section.</span></span>
    * <span data-ttu-id="2b342-188">Można ograniczyć dostęp do każdego formatu, identyfikując określone kraje/regiony, w których format się stosuje.</span><span class="sxs-lookup"><span data-stu-id="2b342-188">Each format access can be restricted by identifying particular countries/regions in which a format is applicable.</span></span> <span data-ttu-id="2b342-189">Gdy lista krajów/regionów dla określonego formatu jest pusta, tego formatu można używać dla dowolnej firmy.</span><span class="sxs-lookup"><span data-stu-id="2b342-189">When the list of countries/regions for particular format is empty, this format can be used in any company.</span></span> <span data-ttu-id="2b342-190">Jeśli do listy krajów/regionów zostaną wstawione jakieś kody ISO krajów/regionów, formatu można używać tylko w firmach, których adres podstawowy mieści się w danym kraju/regionie.</span><span class="sxs-lookup"><span data-stu-id="2b342-190">When some ISO country/region codes are inserted in the list of countries/regions, the format can only be use in companies if the primary address is in the country/region.</span></span>  


