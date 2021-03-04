---
title: Raportowanie finansowe — często zadawane pytania
description: W tym temacie omówiono pytania związane z raportowaniem finansowym zgłoszone przez innych użytkowników.
author: jiwo
manager: tfehr
ms.date: 01/13/2021
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 3f9381f5b656d0cc0b46c8828b2ef9d024e296b0
ms.sourcegitcommit: 14785208d84b2c1efd30f140c52df35a2ccd1577
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/27/2021
ms.locfileid: "5070224"
---
# <a name="financial-reporting-faq"></a><span data-ttu-id="75032-103">Raportowanie finansowe — często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="75032-103">Financial reporting FAQ</span></span> 

<span data-ttu-id="75032-104">W tym temacie omówiono pytania związane z raportowaniem finansowym zgłoszone przez innych użytkowników.</span><span class="sxs-lookup"><span data-stu-id="75032-104">This topic lists questions related to financial reporting that other users have had.</span></span> 


## <a name="how-do-i-restrict-access-to-a-report-using-tree-security"></a><span data-ttu-id="75032-105">Jak ograniczyć dostęp do raportu przy użyciu drzewa zabezpieczeń?</span><span class="sxs-lookup"><span data-stu-id="75032-105">How do I restrict access to a report using Tree security?</span></span>

<span data-ttu-id="75032-106">Scenariusz: firma demonstracyjna USMF opracowała raport bilansowy, do którego chce ograniczyć dostęp w taki sposób, by nie wszyscy użytkownicy funkcji Financial Reporting mieli w niego wgląd w rozwiązaniu D365.</span><span class="sxs-lookup"><span data-stu-id="75032-106">Scenario: The USMF demo company has a Balance sheet report that it doesn’t want all Financial reporting users to be able to view in D365.</span></span> <span data-ttu-id="75032-107">Rozwiązanie: w celu ograniczenia dostępu do jednego raportu można użyć drzewa zabezpieczeń — dzięki temu dostęp do raportu będą mieć tylko wybrani użytkownicy.</span><span class="sxs-lookup"><span data-stu-id="75032-107">Solution: You can utilize Tree security to restrict access to a single report so that only certain users can access the report.</span></span> 

1.  <span data-ttu-id="75032-108">Zaloguj się do Projektanta raportów modułu Financial Reporter.</span><span class="sxs-lookup"><span data-stu-id="75032-108">Log into Financial Reporter Report Designer</span></span>

2.  <span data-ttu-id="75032-109">Utwórz nową definicję drzewa (Plik | Nowy | Definicja drzewa). a.</span><span class="sxs-lookup"><span data-stu-id="75032-109">Create a new Tree Definition (File | New | Tree Definition) a.</span></span>    <span data-ttu-id="75032-110">Kliknij dwukrotnie wiersz **Podsumowanie** w kolumnie **Zabezpieczenia jednostki**.</span><span class="sxs-lookup"><span data-stu-id="75032-110">Double-click the **Summary** line in the **Unit Security** column.</span></span>
  <span data-ttu-id="75032-111">i.</span><span class="sxs-lookup"><span data-stu-id="75032-111">i.</span></span>    <span data-ttu-id="75032-112">Kliknij pozycję Użytkownicy i grupy.</span><span class="sxs-lookup"><span data-stu-id="75032-112">Click Users and Groups.</span></span>  
          <span data-ttu-id="75032-113">1. Wybierz użytkowników lub grupę do przyznania dostępu do tego raportu.</span><span class="sxs-lookup"><span data-stu-id="75032-113">1.    Select the User(s) or Group that would like to access this report.</span></span> 
          
<span data-ttu-id="75032-114">[![ekran użytkownika](./media/FR-FAQ_users.png)](./media/FR-FAQ_users.png)</span><span class="sxs-lookup"><span data-stu-id="75032-114">[![user screen](./media/FR-FAQ_users.png)](./media/FR-FAQ_users.png)</span></span>

<span data-ttu-id="75032-115">[![ekran zabezpieczeń](./media/FR-FAQ_security.jpg)](./media/FR-FAQ_security.jpg)</span><span class="sxs-lookup"><span data-stu-id="75032-115">[![security screen](./media/FR-FAQ_security.jpg)](./media/FR-FAQ_security.jpg)</span></span>

  <span data-ttu-id="75032-116">b.</span><span class="sxs-lookup"><span data-stu-id="75032-116">b.</span></span>    <span data-ttu-id="75032-117">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="75032-117">Click **Save**.</span></span>
  
<span data-ttu-id="75032-118">[![przycisk Zapisz](./media/FR-FAQ_save.png)](./media/FR-FAQ_save.png)</span><span class="sxs-lookup"><span data-stu-id="75032-118">[![save button](./media/FR-FAQ_save.png)](./media/FR-FAQ_save.png)</span></span>

3.  <span data-ttu-id="75032-119">W definicji raportu dodaj nową definicję drzewa.</span><span class="sxs-lookup"><span data-stu-id="75032-119">In your Report Definition add your new Tree Definition</span></span>

<span data-ttu-id="75032-120">[![formularz definicji drzewa](./media/FR-FAQ_tree-definition.jpg)](./media/FR-FAQ_tree-definition.jpg)</span><span class="sxs-lookup"><span data-stu-id="75032-120">[![tree definition form](./media/FR-FAQ_tree-definition.jpg)](./media/FR-FAQ_tree-definition.jpg)</span></span>

<span data-ttu-id="75032-121">A.</span><span class="sxs-lookup"><span data-stu-id="75032-121">A.</span></span>  <span data-ttu-id="75032-122">W obszarze definicji drzewa kliknij pozycję Ustawienie i w obszarze „Wybór jednostki raportowania” zaznacz opcję „Uwzględnij wszystkie jednostki”.</span><span class="sxs-lookup"><span data-stu-id="75032-122">While in the Tree Definition click on Setting and under “Reporting unit selection” check “Include all units”</span></span>

<span data-ttu-id="75032-123">[![formularz wyboru jednostki raportowania](./media/FR-FAQ_reporting-unit-selection.jpg)](./media/FR-FAQ_reporting-unit-selection.jpg)</span><span class="sxs-lookup"><span data-stu-id="75032-123">[![reporting unit selection form](./media/FR-FAQ_reporting-unit-selection.jpg)](./media/FR-FAQ_reporting-unit-selection.jpg)</span></span>

<span data-ttu-id="75032-124">**Przed:** [![zrzut ekranu przed](./media/FR-FAQ_before.png)](./media/FR-FAQ_before.png)</span><span class="sxs-lookup"><span data-stu-id="75032-124">**Before:** [![before screenshot](./media/FR-FAQ_before.png)](./media/FR-FAQ_before.png)</span></span>

<span data-ttu-id="75032-125">**Po:** [![zrzut ekranu po](./media/FR-FAQ_after.png)](./media/FR-FAQ_after.png)</span><span class="sxs-lookup"><span data-stu-id="75032-125">**After:** [![after screenshot](./media/FR-FAQ_after.png)](./media/FR-FAQ_after.png)</span></span>

<span data-ttu-id="75032-126">Uwaga: powodem wyświetlenia powyższej wiadomości jest fakt, że użytkownik nie ma dostępu do tego raportu po zastosowaniu zabezpieczeń jednostki.</span><span class="sxs-lookup"><span data-stu-id="75032-126">Note: Reason for the above message is my user does not have access to that report after applying Unit Security</span></span>



## <a name="how-do-i-determine-which-accounts-do-not-matching-my-balances-in-d365"></a><span data-ttu-id="75032-127">Jak ustalić, które konta nie są zgodne z moimi saldami w D365?</span><span class="sxs-lookup"><span data-stu-id="75032-127">How do I determine which account(s) do not matching my balances in D365?</span></span>

<span data-ttu-id="75032-128">Jeśli masz raport, który zawiera inne dane niż te, których można by się spodziewać w usłudze D365, wykonaj kilka kroków w celu zidentyfikowania tych kont oraz odchyleń.</span><span class="sxs-lookup"><span data-stu-id="75032-128">When you have a report that doesn't match what you would expect in D365, here are some steps you could take to identify those accounts and the variances.</span></span> 

### <a name="in-financial-reporter-report-designer"></a><span data-ttu-id="75032-129">W Projektancie raportów modułu Financial Reporter</span><span class="sxs-lookup"><span data-stu-id="75032-129">In Financial Reporter Report Designer</span></span>

1.  <span data-ttu-id="75032-130">Utwórz nową definicję wiersza. a.</span><span class="sxs-lookup"><span data-stu-id="75032-130">Create a new Row Definition a.</span></span>    <span data-ttu-id="75032-131">Kliknij kolejno Edycja | Wstaw wiersze z wymiarów. i.</span><span class="sxs-lookup"><span data-stu-id="75032-131">Click Edit | Insert Rows from Dimensions i.</span></span>  <span data-ttu-id="75032-132">Wybierz pozycję MainAccount [![Wybierz ekran główny](./media/FR-FAQ_selectmain_.png)](./media/FR-FAQ_selectmain_.png)</span><span class="sxs-lookup"><span data-stu-id="75032-132">Select MainAccount [![Select Main screen_](./media/FR-FAQ_selectmain_.png)](./media/FR-FAQ_selectmain_.png)</span></span>
    
    <span data-ttu-id="75032-133">ii.</span><span class="sxs-lookup"><span data-stu-id="75032-133">ii.</span></span> <span data-ttu-id="75032-134">Kliknij przycisk OK. b.</span><span class="sxs-lookup"><span data-stu-id="75032-134">Click Ok b.</span></span>    <span data-ttu-id="75032-135">Zapisz definicję wiersza.</span><span class="sxs-lookup"><span data-stu-id="75032-135">Save the Row Definition</span></span>

2.  <span data-ttu-id="75032-136">Utwórz nową definicję kolumny [![Utwórz nową definicję kolumny](./media/FR-FAQ_column.png)](./media/FR-FAQ_column.png)</span><span class="sxs-lookup"><span data-stu-id="75032-136">Create a new Column Definition     [![Create a new column definition](./media/FR-FAQ_column.png)](./media/FR-FAQ_column.png)</span></span>

3.  <span data-ttu-id="75032-137">Utwórz nową definicję raportu. a.</span><span class="sxs-lookup"><span data-stu-id="75032-137">Create a new Report Definition a.</span></span>    <span data-ttu-id="75032-138">Kliknij przycisk Ustawienia i usuń zaznaczenie [![formularza Ustawienia](./media/FR-FAQ_settings.png)](./media/FR-FAQ_settings.png)</span><span class="sxs-lookup"><span data-stu-id="75032-138">Click Settings and uncheck [![Settings form](./media/FR-FAQ_settings.png)](./media/FR-FAQ_settings.png)</span></span>
   
4.  <span data-ttu-id="75032-139">Wygeneruj raport.</span><span class="sxs-lookup"><span data-stu-id="75032-139">Generate the Report.</span></span> 

5.  <span data-ttu-id="75032-140">Wyeksportuj raport do programu Excel.</span><span class="sxs-lookup"><span data-stu-id="75032-140">Export the Report to Excel.</span></span>

### <a name="in-d365"></a><span data-ttu-id="75032-141">W usłudze D365:</span><span class="sxs-lookup"><span data-stu-id="75032-141">In D365:</span></span> 
1.  <span data-ttu-id="75032-142">Kliknij pozycję Księga główna | Zapytania i raporty | Bilans próbny. a.</span><span class="sxs-lookup"><span data-stu-id="75032-142">Click General Ledger | Inquiries and Reports | Trial Balance a.</span></span>    <span data-ttu-id="75032-143">Parametry i.</span><span class="sxs-lookup"><span data-stu-id="75032-143">Parameters i.</span></span>  <span data-ttu-id="75032-144">Data początkowa: początek roku obrachunkowego. ii.</span><span class="sxs-lookup"><span data-stu-id="75032-144">From Date: Start of Fiscal Year ii.</span></span> <span data-ttu-id="75032-145">Data końcowa: data wygenerowania raportu iii.</span><span class="sxs-lookup"><span data-stu-id="75032-145">To Date: Date you generated the report for iii.</span></span>    <span data-ttu-id="75032-146">Zestawów wymiarów finansowych „Zestaw konta głównego” [![Formularz konta głównego](./media/FR-FAQ_mainacct.png)](./media/FR-FAQ_mainacct.png)</span><span class="sxs-lookup"><span data-stu-id="75032-146">Financial Dimension Set “Main Account set” [![Main Account Form](./media/FR-FAQ_mainacct.png)](./media/FR-FAQ_mainacct.png)</span></span>
      
  <span data-ttu-id="75032-147">b.</span><span class="sxs-lookup"><span data-stu-id="75032-147">b.</span></span>    <span data-ttu-id="75032-148">Kliknij przycisk Oblicz.</span><span class="sxs-lookup"><span data-stu-id="75032-148">Click Calculate</span></span>

2.  <span data-ttu-id="75032-149">Wyeksportuj raport do programu Excel.</span><span class="sxs-lookup"><span data-stu-id="75032-149">Export the report to Excel</span></span>

<span data-ttu-id="75032-150">Teraz powinno być możliwe skopiowanie danych z raportu rozwiązania Financial Reporting w programie Excel do raportu bilansu próbnego D365 oraz porównanie kolumn „Saldo zamknięcia”.</span><span class="sxs-lookup"><span data-stu-id="75032-150">You should now be able to copy the data from the FR Excel Report and to the D365 Trial Balance report and compare the “Closing Balance” columns.</span></span>
