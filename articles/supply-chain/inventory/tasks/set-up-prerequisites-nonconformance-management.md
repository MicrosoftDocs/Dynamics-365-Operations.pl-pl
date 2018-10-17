--- 
title: "Konfigurowanie warunków wstępnych zarządzania brakiem zgodności"
description: "Ta procedura umożliwia aktywowanie procesów zarządzania brakiem zgodności."
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventParameters, InventTestReportSetup, SysUserManagement, SysUserSetup, InventTestDiagnosticType, InventTestMiscCharges, InventTestOperation, InventProblemType, InventProblemTypeSetup, InventQuarantineZone
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 0a4062acc91e024e3a0a41c0b3cb35ff5ffe2a4a
ms.contentlocale: pl-pl
ms.lasthandoff: 09/14/2018

---
# <a name="set-up-prerequisites-for-nonconformance-management"></a><span data-ttu-id="2ce2e-103">Konfigurowanie warunków wstępnych zarządzania brakiem zgodności</span><span class="sxs-lookup"><span data-stu-id="2ce2e-103">Set up prerequisites for nonconformance management</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2ce2e-104">Ta procedura umożliwia aktywowanie procesów zarządzania brakiem zgodności.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-104">Use this procedure to enable nonconformance management processes.</span></span> <span data-ttu-id="2ce2e-105">Brak zgodności opisuje procedurę lub towar, który ma problem z jakością, gdzie opisowe informacje zawierają źródło i typ problemu.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-105">A nonconformance describes a procedure or item that has a quality problem, where the descriptive information includes the source and type of problem.</span></span> <span data-ttu-id="2ce2e-106">Procedura wykorzystuje dane firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-106">This procedure uses the USMF demo data company.</span></span> <span data-ttu-id="2ce2e-107">Ta procedura jest zwykle wykonywana przez kierownika ds. jakości.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-107">This procedure is typically performed by a quality manager.</span></span>


## <a name="enable-quality-management-processes-within-the-company"></a><span data-ttu-id="2ce2e-108">Włączanie procesów zarządzania jakością w firmie</span><span class="sxs-lookup"><span data-stu-id="2ce2e-108">Enable quality management processes within the company</span></span>
1. <span data-ttu-id="2ce2e-109">Wybierz kolejno opcje Zarządzanie zapasami > Ustawienia > Parametry modułu Zarządzanie zapasami i magazynem.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-109">Go to Inventory management > Setup > Inventory and warehouse management parameters.</span></span>
2. <span data-ttu-id="2ce2e-110">Kliknij kartę Zarządzanie jakością.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-110">Click the Quality management tab.</span></span>
3. <span data-ttu-id="2ce2e-111">W polu Korzystaj z funkcji zarządzania jakością zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-111">Select Yes in the Use quality management field.</span></span>
    * <span data-ttu-id="2ce2e-112">Zaznacz ten parametr, aby umożliwić procesy zarządzania jakością w firmie.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-112">Select this parameter to enable quality management processes for the company.</span></span>  
4. <span data-ttu-id="2ce2e-113">W polu Stawka godzinowa wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-113">In the Hourly rate field, enter a number.</span></span>
    * <span data-ttu-id="2ce2e-114">W polu Stawka godzinowa wpisz stawkę godzinową za pracę w walucie lokalnej.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-114">Use the Hourly rate field to enter an hourly labor rate in the local currency.</span></span> <span data-ttu-id="2ce2e-115">Stawka godzinowa używana jest do obliczania kosztów operacji związanych z niezgodnością.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-115">The hourly rate is used for calculating costs for operations that are related to a nonconformance.</span></span> <span data-ttu-id="2ce2e-116">Stawka godzinowa i obliczone koszty stanowią odnośnikowe informacje o niezgodności i nie mają styczności z innymi funkcjami.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-116">The hourly rate and calculated costs provide reference information for a nonconformance, and they do not interact with other functionality.</span></span>  
5. <span data-ttu-id="2ce2e-117">Kliknij opcję Konfiguracja raportu.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-117">Click Report setup.</span></span>
    * <span data-ttu-id="2ce2e-118">Na tej stronie można określić typy uwag do raportów z kontroli jakości, które będą używane w różnych rodzajach raportów o zarządzaniu jakością.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-118">This page allows you define the quality report note types that will be used on different kinds of quality management reports.</span></span>  
6. <span data-ttu-id="2ce2e-119">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-119">Close the page.</span></span>
7. <span data-ttu-id="2ce2e-120">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-120">Close the page.</span></span>

## <a name="enable-user-for-nonconformance-processing"></a><span data-ttu-id="2ce2e-121">Włączanie użytkownika dla przetwarzania braku zgodności</span><span class="sxs-lookup"><span data-stu-id="2ce2e-121">Enable user for nonconformance processing</span></span>
1. <span data-ttu-id="2ce2e-122">Wybierz kolejno opcje Administrowanie systemem > Użytkownicy > Użytkownicy.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-122">Go to System administration > Users > Users.</span></span>
    * <span data-ttu-id="2ce2e-123">Aby wykonać zatwierdzenie braku zgodności, użytkownik, który zatwierdza lub odrzuca brak zgodności, musi mieć przypisaną wartość „Nazwa” na stronie Użytkownicy.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-123">To process the approval of a nonconformance the user who  approves or rejects nonconformances must have a “Name” value assigned on the Users page.</span></span> <span data-ttu-id="2ce2e-124">Aby korzystać z notatek do dokumentu, użytkownik musi mieć również włączoną funkcję Obsługa dokumentu w opcjach użytkownika.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-124">To use the document notes, the user must also have Document handling activated in the user options.</span></span>  
2. <span data-ttu-id="2ce2e-125">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-125">Use the Quick Filter to find records.</span></span> <span data-ttu-id="2ce2e-126">Na przykład wyfiltruj według pola Nazwa z wartością „Ricardo”.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-126">For example, filter on the Name field with a value of 'Ricardo'.</span></span>
    * <span data-ttu-id="2ce2e-127">Użyj filtru, aby znaleźć użytkownika, który będzie zatwierdzał lub odrzucał rekordy braku zgodności.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-127">Use the filter to find the user who will be approving or rejecting the nonconformance records.</span></span>  
3. <span data-ttu-id="2ce2e-128">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-128">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="2ce2e-129">Aby wykonać zatwierdzenie braku zgodności, upewnij się, że użytkownik, który zatwierdza lub odrzuca niezgodności, ma przypisaną wartość „Nazwa” na stronie Użytkownicy.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-129">To process the approval of a nonconformance, make sure the user who approves or rejects nonconformances has a “Name” value assigned on the Users page.</span></span>  
4. <span data-ttu-id="2ce2e-130">Kliknij opcję Opcje użytkownika.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-130">Click User options.</span></span>
5. <span data-ttu-id="2ce2e-131">Kliknij kartę Preferencje.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-131">Click the Preferences tab.</span></span>
6. <span data-ttu-id="2ce2e-132">W polu Włącz obsługę dokumentów zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-132">Select Yes in the Enable document handling field.</span></span>
    * <span data-ttu-id="2ce2e-133">Aby korzystać z notatek do dokumentu, użytkownik musi mieć również włączoną funkcję Obsługa dokumentu w opcjach użytkownika.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-133">To use the document notes, the user must also have Document handling activated in the user options.</span></span>  
7. <span data-ttu-id="2ce2e-134">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-134">Close the page.</span></span>
8. <span data-ttu-id="2ce2e-135">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-135">Close the page.</span></span>
9. <span data-ttu-id="2ce2e-136">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-136">Close the page.</span></span>

## <a name="define-diagnostic-types-for-nonconformance-processing"></a><span data-ttu-id="2ce2e-137">Definiowanie typów diagnostyki dla przetwarzania braku zgodności</span><span class="sxs-lookup"><span data-stu-id="2ce2e-137">Define diagnostic types for nonconformance processing</span></span>
1. <span data-ttu-id="2ce2e-138">Wybierz kolejno opcje Zarządzanie zapasami > Ustawienia > Zarządzanie jakością > Typy diagnostyki.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-138">Go to Inventory management > Setup > Quality management > Diagnostic types.</span></span>
    * <span data-ttu-id="2ce2e-139">Na stronie Typy diagnostyki zdefiniuj klasyfikację akcji diagnostycznych.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-139">Use the Diagnostic types page to define a classification of diagnostic actions.</span></span> <span data-ttu-id="2ce2e-140">Korekta określa typ akcji diagnostycznej, którą należy wykonać dla zatwierdzonej niezgodności, osobę mającą wykonać tę akcję oraz żądaną i planowaną datę wykonania.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-140">A correction identifies what type of diagnostic action should be taken on an approved nonconformance, who should perform it, and the requested and planned completion date.</span></span>  
2. <span data-ttu-id="2ce2e-141">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-141">Click New.</span></span>
3. <span data-ttu-id="2ce2e-142">W polu Diagnostyka wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-142">In the Diagnostic field, type a value.</span></span>
4. <span data-ttu-id="2ce2e-143">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-143">In the Description field, type a value.</span></span>
5. <span data-ttu-id="2ce2e-144">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-144">Close the page.</span></span>

## <a name="define-quality-charges-for-nonconformance-processing"></a><span data-ttu-id="2ce2e-145">Definiowanie opłat związanych z kontrolą jakości dla przetwarzania braku zgodności</span><span class="sxs-lookup"><span data-stu-id="2ce2e-145">Define quality charges for nonconformance processing</span></span>
1. <span data-ttu-id="2ce2e-146">Wybierz kolejno opcje Zarządzanie zapasami > ustawienia > Zarządzanie jakością > Opłaty związane z kontrolą jakości.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-146">Go to Inventory management > Setup > Quality management > Quality charges.</span></span>
    * <span data-ttu-id="2ce2e-147">Strona Opłaty związane z kontrolą jakości służy do definiowania klasyfikacji opłat, które będą używane w operacjach związanych z brakiem zgodności.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-147">Use the Quality charges page to define a classification of charges that will used in operations related to nonconformances.</span></span>  
2. <span data-ttu-id="2ce2e-148">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-148">Click New.</span></span>
3. <span data-ttu-id="2ce2e-149">W polu Kod opłat wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-149">In the Charges code field, type a value.</span></span>
4. <span data-ttu-id="2ce2e-150">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-150">In the Description field, type a value.</span></span>
5. <span data-ttu-id="2ce2e-151">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-151">Close the page.</span></span>

## <a name="define-the-operations-for-nonconformance-processing"></a><span data-ttu-id="2ce2e-152">Definiowanie operacji przetwarzania braku zgodności</span><span class="sxs-lookup"><span data-stu-id="2ce2e-152">Define the operations for nonconformance processing</span></span>
1. <span data-ttu-id="2ce2e-153">Wybierz kolejno opcje Zarządzanie zapasami > Ustawienia > Zarządzanie jakością > Operacje.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-153">Go to Inventory management > Setup > Quality management > Operations.</span></span>
    * <span data-ttu-id="2ce2e-154">Za pomocą strony Operacje zdefiniuj klasyfikację pracy, którą można wykonać dla zatwierdzonego braku zgodności.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-154">Use the Operations page to define a classification of the work that may be performed for an approved nonconformance.</span></span> <span data-ttu-id="2ce2e-155">Podczas kojarzenia operacji z brakiem zgodności można zdefiniować szczegółowe informacje o powiązanych materiałach, godzinach robocizny i opłatach dodatkowych wymaganych do wykonania operacji.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-155">When you relate an operation to a nonconformance, you can define information about the associated material, labor hours, and miscellaneous charges that are required to perform the operation.</span></span> <span data-ttu-id="2ce2e-156">Te informacje stanowią podstawę do obliczenia szacowanego kosztu wykonania operacji.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-156">This information provides the basis for calculating an estimated cost for performing the operation.</span></span>  
2. <span data-ttu-id="2ce2e-157">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-157">Click New.</span></span>
3. <span data-ttu-id="2ce2e-158">W polu Operacje wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-158">In the Operation field, type a value.</span></span>
4. <span data-ttu-id="2ce2e-159">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-159">In the Description field, type a value.</span></span>
5. <span data-ttu-id="2ce2e-160">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-160">Close the page.</span></span>

## <a name="define-problem-types-for-nonconformance-processing"></a><span data-ttu-id="2ce2e-161">Definiowanie typów problemów dla przetwarzania braku zgodności</span><span class="sxs-lookup"><span data-stu-id="2ce2e-161">Define problem types for nonconformance processing</span></span>
1. <span data-ttu-id="2ce2e-162">Wybierz kolejno opcje Zarządzanie zapasami > Ustawienia > Zarządzanie jakością > Typy problemów.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-162">Go to Inventory management > Setup > Quality management > Problem types.</span></span>
    * <span data-ttu-id="2ce2e-163">Użyj strony Typ problemu do zdefiniowania klasyfikacji problemów z jakością, które występują w różnych typach braku zgodności.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-163">Use the Problem types page to define a classification of quality problems that are encountered in the various nonconformance types.</span></span> <span data-ttu-id="2ce2e-164">Istnieją następujące typy braku zgodności: Wewnętrzny, Odbiorca, Dostawca, Żądanie usługi, Produkcja i Wytwarzanie produktu towarzyszącego.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-164">The nonconformance types include Internal, Customer, Vendor, Service request, Production, and Co-product production.</span></span> <span data-ttu-id="2ce2e-165">Jeden typ problemu można skojarzyć z wieloma typami braku zgodności.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-165">A single problem type can be associated with multiple nonconformance types.</span></span>  
2. <span data-ttu-id="2ce2e-166">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-166">Click New.</span></span>
3. <span data-ttu-id="2ce2e-167">W polu Typ problemu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-167">In the Problem type field, type a value.</span></span>
4. <span data-ttu-id="2ce2e-168">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-168">In the Description field, type a value.</span></span>
5. <span data-ttu-id="2ce2e-169">Kliknij opcję Typy niezgodności.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-169">Click Non conformance types.</span></span>
    * <span data-ttu-id="2ce2e-170">Użyj strony Typy niezgodności w celu autoryzowania użycia typu problemu dla jednego lub więcej typów braku zgodności.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-170">Use the Non conformance types page to authorize the use of a problem type for one or more of the nonconformance types.</span></span> <span data-ttu-id="2ce2e-171">Na przykład typ problemu związany z kodem wady może dotyczyć wszystkich typów niezgodności, podczas gdy typ problemu związany ze skargami odbiorców może dotyczyć tylko niezgodności typu odbiorca i zlecenie serwisowe.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-171">For example, a problem type regarding a defect code could apply to all nonconformance types, whereas a problem type about customer complaints may only apply to the customer and service request nonconformance types.</span></span>  
6. <span data-ttu-id="2ce2e-172">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-172">Click New.</span></span>
7. <span data-ttu-id="2ce2e-173">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-173">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="2ce2e-174">W polu Typ niezgodności wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-174">In the Non conformance type field, select an option.</span></span>
9. <span data-ttu-id="2ce2e-175">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-175">Close the page.</span></span>
10. <span data-ttu-id="2ce2e-176">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-176">Close the page.</span></span>

## <a name="define-quarantine-zones-for-nonconformance-processing"></a><span data-ttu-id="2ce2e-177">Definiowanie stref kwarantanny dla przetwarzania braku zgodności</span><span class="sxs-lookup"><span data-stu-id="2ce2e-177">Define quarantine zones for nonconformance processing</span></span>
1. <span data-ttu-id="2ce2e-178">Wybierz kolejno opcje Zarządzanie zapasami > Ustawienia > Zarządzanie jakością > Strefy kwarantanny.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-178">Go to Inventory management > Setup > Quality management > Quarantine zones.</span></span>
2. <span data-ttu-id="2ce2e-179">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-179">Click New.</span></span>
3. <span data-ttu-id="2ce2e-180">W polu Strefa kwarantanny wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-180">In the Quarantine zone field, type a value.</span></span>
4. <span data-ttu-id="2ce2e-181">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-181">In the Description field, type a value.</span></span>
5. <span data-ttu-id="2ce2e-182">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2ce2e-182">Close the page.</span></span>


