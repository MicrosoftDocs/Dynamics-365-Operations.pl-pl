---
title: Raportowanie finansowe — często zadawane pytania
description: W tym temacie omówiono pytania związane z raportowaniem finansowym zgłoszone przez innych użytkowników.
author: jiwo
ms.date: 01/13/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 023354b0e2973f63411bf81cbeb0344333c49112
ms.sourcegitcommit: d63e7e0593084a61362a6cad3937b1fd956c384f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/21/2021
ms.locfileid: "5923032"
---
# <a name="financial-reporting-faq"></a><span data-ttu-id="4a591-103">Raportowanie finansowe — często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="4a591-103">Financial reporting FAQ</span></span> 

<span data-ttu-id="4a591-104">Ten temat zawiera odpowiedzi na często zadawane pytania dotyczące raportowania finansowego.</span><span class="sxs-lookup"><span data-stu-id="4a591-104">This topic provides answers to frequently asked questions about financial reporting.</span></span> 

## <a name="how-do-i-restrict-access-to-a-report-using-tree-security"></a><span data-ttu-id="4a591-105">Jak ograniczyć dostęp do raportu przy użyciu zabezpieczeń drzewa?</span><span class="sxs-lookup"><span data-stu-id="4a591-105">How do I restrict access to a report using tree security?</span></span>

<span data-ttu-id="4a591-106">Na poniższym przykładzie pokazano, jak ograniczyć dostęp do raportu przy użyciu zabezpieczeń drzewa.</span><span class="sxs-lookup"><span data-stu-id="4a591-106">The following example shows how to restrict access to a report using tree security.</span></span>

<span data-ttu-id="4a591-107">Firma demonstracyjna USMF ma raport bilansowy, do którego nie wszyscy użytkownicy raportowania finansowego powinni mieć dostęp.</span><span class="sxs-lookup"><span data-stu-id="4a591-107">The USMF demo company has a Balance sheet report that not all Financial reporting users should have access to.</span></span> <span data-ttu-id="4a591-108">W celu ograniczenia dostępu do jednego raportu można użyć zabezpieczenia drzewa, dzięki któremu dostęp do raportu będą mieć tylko wybrani użytkownicy.</span><span class="sxs-lookup"><span data-stu-id="4a591-108">To restrict access, you can use tree security to restrict access to a single report so that only certain users can access the report.</span></span> <span data-ttu-id="4a591-109">Aby ograniczyć dostęp, należy wykonać następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="4a591-109">Follow these steps to restrict access:</span></span> 

1. <span data-ttu-id="4a591-110">Zaloguj się do projektanta Financial Reporter Report Designer.</span><span class="sxs-lookup"><span data-stu-id="4a591-110">Sign in to Financial Reporter Report Designer.</span></span>
2. <span data-ttu-id="4a591-111">Utwórz nową definicję drzewa.</span><span class="sxs-lookup"><span data-stu-id="4a591-111">Create a new tree definition.</span></span> <span data-ttu-id="4a591-112">Przejdź do opcji **Plik > Nowy > Definicja drzewa**.</span><span class="sxs-lookup"><span data-stu-id="4a591-112">Go to **File > New > Tree Definition**.</span></span>
3. <span data-ttu-id="4a591-113">Kliknij dwukrotnie wiersz **Podsumowanie** w kolumnie **Zabezpieczenia jednostki**.</span><span class="sxs-lookup"><span data-stu-id="4a591-113">Double-click the **Summary** line in the **Unit Security** column.</span></span>
4. <span data-ttu-id="4a591-114">Wybierz opcję **Użytkownicy i grupy**.</span><span class="sxs-lookup"><span data-stu-id="4a591-114">Select **Users and Groups**.</span></span>  
5. <span data-ttu-id="4a591-115">Wybierz użytkowników lub grupy, które wymagają dostępu do tego raportu.</span><span class="sxs-lookup"><span data-stu-id="4a591-115">Select the users or groups that need access to this report.</span></span> 
6. <span data-ttu-id="4a591-116">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="4a591-116">Select **Save**.</span></span>
7. <span data-ttu-id="4a591-117">W definicji raportu dodaj nową definicję drzewa.</span><span class="sxs-lookup"><span data-stu-id="4a591-117">In the report definition, add your new tree definition.</span></span>
8. <span data-ttu-id="4a591-118">W definicji drzewa wybierz opcję **Ustawienie**.</span><span class="sxs-lookup"><span data-stu-id="4a591-118">In the tree definition, select **Setting**.</span></span> <span data-ttu-id="4a591-119">W obszarze **Wybór jednostki raportowania** wybierz opcję **Uwzględnij wszystkie jednostki**.</span><span class="sxs-lookup"><span data-stu-id="4a591-119">Under **Reporting unit selection**, select **Include all units**.</span></span>

## <a name="how-do-i-identify-which-accounts-do-not-match-my-balances"></a><span data-ttu-id="4a591-120">Jak określić, które konta nie pasują do moich sald?</span><span class="sxs-lookup"><span data-stu-id="4a591-120">How do I identify which accounts do not match my balances?</span></span>

<span data-ttu-id="4a591-121">Jeśli masz raport, który nie zawiera pasujących sald, wykonaj kilka kroków w celu zidentyfikowania każdego z tych kont oraz odchyleń.</span><span class="sxs-lookup"><span data-stu-id="4a591-121">If you have a report that doesn't have matching balances, here are some steps you can take to identify each of the accounts and variances.</span></span> 

<span data-ttu-id="4a591-122">**Financial Reporter Report Designer**</span><span class="sxs-lookup"><span data-stu-id="4a591-122">**Financial Reporter Report Designer**</span></span>
1. <span data-ttu-id="4a591-123">W projektancie Financial Reporter Report Designer utwórz nową definicję wiersza.</span><span class="sxs-lookup"><span data-stu-id="4a591-123">In Financial Reporter Report Designer, create a new row definition.</span></span> 
2. <span data-ttu-id="4a591-124">Kliknij opcję **Edycja > Wstaw wiersze z wymiarów**.</span><span class="sxs-lookup"><span data-stu-id="4a591-124">Select **Edit > Insert Rows from Dimensions**.</span></span>
3. <span data-ttu-id="4a591-125">Wybierz opcję **Konto główne**.</span><span class="sxs-lookup"><span data-stu-id="4a591-125">Select **MainAccount**.</span></span>  
4. <span data-ttu-id="4a591-126">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a591-126">Select **OK**.</span></span>
5. <span data-ttu-id="4a591-127">Zapisz definicję wiersza.</span><span class="sxs-lookup"><span data-stu-id="4a591-127">Save the row definition.</span></span>
6. <span data-ttu-id="4a591-128">Utwórz nową definicję kolumny</span><span class="sxs-lookup"><span data-stu-id="4a591-128">Create a new column definition</span></span>
7. <span data-ttu-id="4a591-129">Utwórz nową definicję raportu.</span><span class="sxs-lookup"><span data-stu-id="4a591-129">Create a new report definition.</span></span>
8. <span data-ttu-id="4a591-130">Wybierz opcję **Ustawienia** i usuń jej zaznaczenie.</span><span class="sxs-lookup"><span data-stu-id="4a591-130">Select **Settings** and unmark this option.</span></span>  
9. <span data-ttu-id="4a591-131">Wygeneruj raport.</span><span class="sxs-lookup"><span data-stu-id="4a591-131">Generate the report.</span></span> 
10. <span data-ttu-id="4a591-132">Wyeksportuj raport do programu Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="4a591-132">Export the report to Microsoft Excel.</span></span>

<span data-ttu-id="4a591-133">**Dynamics 365 Finance**</span><span class="sxs-lookup"><span data-stu-id="4a591-133">**Dynamics 365 Finance**</span></span> 
1. <span data-ttu-id="4a591-134">W rozwiązaniu Dynamics 365 Finance przejdź do opcji **Księga główna > Zapytania i raporty > Bilans próbny**.</span><span class="sxs-lookup"><span data-stu-id="4a591-134">In Dynamics 365 Finance, go to **General Ledger > Inquiries and Reports > Trial Balance**.</span></span>
2. <span data-ttu-id="4a591-135">Ustaw następujące parametry:</span><span class="sxs-lookup"><span data-stu-id="4a591-135">Set the following parameters:</span></span>
   - <span data-ttu-id="4a591-136">**Data początkowa** — wprowadź początek roku obrachunkowego.</span><span class="sxs-lookup"><span data-stu-id="4a591-136">**From Date** - Enter the start of the fiscal year.</span></span>
   - <span data-ttu-id="4a591-137">**Data końcowa** — wprowadź datę generowania raportu.</span><span class="sxs-lookup"><span data-stu-id="4a591-137">**To Date** - Enter the date you are generating the report for.</span></span>
   - <span data-ttu-id="4a591-138">**Wymiar finansowy** — ustaw wartość tego pola na **Ustawione konto główne**.</span><span class="sxs-lookup"><span data-stu-id="4a591-138">**Financial Dimension** - Set this field to **Main Account set**.</span></span>
 3. <span data-ttu-id="4a591-139">Wybierz pozycję **Oblicz**.</span><span class="sxs-lookup"><span data-stu-id="4a591-139">Select **Calculate**.</span></span>
 4. <span data-ttu-id="4a591-140">Wyeksportuj raport do programu Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="4a591-140">Export the report to Microsoft Excel.</span></span>

<span data-ttu-id="4a591-141">Teraz powinno być możliwe skopiowanie danych z raportu raportowania finansowego w programie Excel do raportu bilansu próbnego, by można było porównać kolumny **Saldo zamknięcia**.</span><span class="sxs-lookup"><span data-stu-id="4a591-141">You should now be able to copy the data from the Financial Reporter Excel report to the Trial Balance report, so you can compare the **Closing Balance** columns.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]