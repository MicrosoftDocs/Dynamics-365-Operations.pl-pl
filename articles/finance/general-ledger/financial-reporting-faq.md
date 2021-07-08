---
title: Raportowanie finansowe — często zadawane pytania
description: Ten temat zawiera odpowiedzi na niektóre często zadawane pytania dotyczące raportowania finansowego.
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
ms.openlocfilehash: e1b67f86446403933005008a9a1e2cc6739dc516
ms.sourcegitcommit: ecabf43282a3e55f1db40341aa3f3c7950b9e94c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/16/2021
ms.locfileid: "6266640"
---
# <a name="financial-reporting-faq"></a><span data-ttu-id="ea83c-103">Raportowanie finansowe — często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="ea83c-103">Financial reporting FAQ</span></span>

<span data-ttu-id="ea83c-104">Ten temat zawiera odpowiedzi na często zadawane pytania dotyczące raportowania finansowego.</span><span class="sxs-lookup"><span data-stu-id="ea83c-104">This topic provides answers to frequently asked questions about Financial reporting.</span></span>

## <a name="how-do-i-restrict-access-to-a-report-by-using-tree-security"></a><span data-ttu-id="ea83c-105">Jak ograniczyć dostęp do raportu przy użyciu zabezpieczeń drzewa?</span><span class="sxs-lookup"><span data-stu-id="ea83c-105">How do I restrict access to a report by using tree security?</span></span>

<span data-ttu-id="ea83c-106">Na poniższym przykładzie pokazano, jak ograniczyć dostęp do raportu przy użyciu zabezpieczeń drzewa.</span><span class="sxs-lookup"><span data-stu-id="ea83c-106">The following example shows how to restrict access to a report by using tree security.</span></span>

<span data-ttu-id="ea83c-107">Firma demonstracyjna USMF ma raport **bilansowy**, do którego nie wszyscy użytkownicy raportowania finansowego powinni mieć dostęp.</span><span class="sxs-lookup"><span data-stu-id="ea83c-107">The USMF demo company has a **Balance sheet** report that not all Financial reporting users should have access to.</span></span> <span data-ttu-id="ea83c-108">W celu ograniczenia dostępu do jednego raportu można użyć drzewa zabezpieczeń — dzięki temu dostęp do niego będą mieć tylko wybrani użytkownicy.</span><span class="sxs-lookup"><span data-stu-id="ea83c-108">You can use tree security to restrict access to a single report so that only specific users can access it.</span></span>

1. <span data-ttu-id="ea83c-109">Zaloguj się w rozwiązaniu Financial Reporter Report Designer.</span><span class="sxs-lookup"><span data-stu-id="ea83c-109">Sign in to Financial Reporter Report Designer.</span></span>
2. <span data-ttu-id="ea83c-110">W celu utworzenia nowej definicji drzewa wybierz **Plik \> Nowy \> Definicja drzewa**.</span><span class="sxs-lookup"><span data-stu-id="ea83c-110">Select **File \> New \> Tree Definition** to create a new tree definition.</span></span>
3. <span data-ttu-id="ea83c-111">Naciśnij (lub kliknij) dwukrotnie wiersz **Podsumowanie** w kolumnie **Zabezpieczenia jednostki**.</span><span class="sxs-lookup"><span data-stu-id="ea83c-111">Double-tap (or double-click) the **Summary** line in the **Unit Security** column.</span></span>
4. <span data-ttu-id="ea83c-112">Wybierz opcję **Użytkownicy i grupy**.</span><span class="sxs-lookup"><span data-stu-id="ea83c-112">Select **Users and Groups**.</span></span>
5. <span data-ttu-id="ea83c-113">Wybierz użytkowników lub grupy, które wymagają dostępu do raportu.</span><span class="sxs-lookup"><span data-stu-id="ea83c-113">Select the users or groups that require access to the report.</span></span>
6. <span data-ttu-id="ea83c-114">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="ea83c-114">Select **Save**.</span></span>
7. <span data-ttu-id="ea83c-115">W definicji raportu dodaj nową definicję drzewa.</span><span class="sxs-lookup"><span data-stu-id="ea83c-115">In the report definition, add your new tree definition.</span></span>
8. <span data-ttu-id="ea83c-116">W definicji drzewa wybierz opcję **Ustawienie**.</span><span class="sxs-lookup"><span data-stu-id="ea83c-116">In the tree definition, select **Setting**.</span></span> <span data-ttu-id="ea83c-117">Następnie w obszarze **Wybór jednostki raportowania** wybierz opcję **Uwzględnij wszystkie jednostki**.</span><span class="sxs-lookup"><span data-stu-id="ea83c-117">Then, under **Reporting unit selection**, select **Include all units**.</span></span>

## <a name="how-do-i-identify-which-accounts-dont-match-my-balances"></a><span data-ttu-id="ea83c-118">Jak określić, które konta nie pasują do moich sald?</span><span class="sxs-lookup"><span data-stu-id="ea83c-118">How do I identify which accounts don't match my balances?</span></span>

<span data-ttu-id="ea83c-119">Jeśli masz raport, który nie zawiera pasujących sald, zastosuj następujące procedury w celu zidentyfikowania każdego konta i odchylenia.</span><span class="sxs-lookup"><span data-stu-id="ea83c-119">If you have a report that doesn't have matching balances, use the following procedures to identify each account and variance.</span></span>

### <a name="in-financial-reporter-report-designer"></a><span data-ttu-id="ea83c-120">W Financial Reporter Report Designer</span><span class="sxs-lookup"><span data-stu-id="ea83c-120">In Financial Reporter Report Designer</span></span>

1. <span data-ttu-id="ea83c-121">Utwórz nową definicję wiersza.</span><span class="sxs-lookup"><span data-stu-id="ea83c-121">Create a new row definition.</span></span>
2. <span data-ttu-id="ea83c-122">Kliknij opcję **Edycja \> Wstaw wiersze z wymiarów**.</span><span class="sxs-lookup"><span data-stu-id="ea83c-122">Select **Edit \> Insert Rows from Dimensions**.</span></span>
3. <span data-ttu-id="ea83c-123">Wybierz opcję **MainAccount**.</span><span class="sxs-lookup"><span data-stu-id="ea83c-123">Select **MainAccount**.</span></span>
4. <span data-ttu-id="ea83c-124">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea83c-124">Select **OK**.</span></span>
5. <span data-ttu-id="ea83c-125">Zapisz definicję wiersza.</span><span class="sxs-lookup"><span data-stu-id="ea83c-125">Save the row definition.</span></span>
6. <span data-ttu-id="ea83c-126">Utwórz nową definicję kolumny.</span><span class="sxs-lookup"><span data-stu-id="ea83c-126">Create a new column definition.</span></span>
7. <span data-ttu-id="ea83c-127">Utwórz nową definicję raportu.</span><span class="sxs-lookup"><span data-stu-id="ea83c-127">Create a new report definition.</span></span>
8. <span data-ttu-id="ea83c-128">Wybierz opcję **Ustawienia** i usuń jej zaznaczenie.</span><span class="sxs-lookup"><span data-stu-id="ea83c-128">Select **Settings** and unmark this option.</span></span>
9. <span data-ttu-id="ea83c-129">Wygeneruj raport.</span><span class="sxs-lookup"><span data-stu-id="ea83c-129">Generate the report.</span></span> 
10. <span data-ttu-id="ea83c-130">Wyeksportuj raport do programu Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="ea83c-130">Export the report to Microsoft Excel.</span></span>

### <a name="in-dynamics-365-finance"></a><span data-ttu-id="ea83c-131">W Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="ea83c-131">In Dynamics 365 Finance</span></span>

1. <span data-ttu-id="ea83c-132">Przejdź do opcji **Księga główna \> Zapytania i raporty \> Bilans próbny**.</span><span class="sxs-lookup"><span data-stu-id="ea83c-132">Go to **General ledger \> Inquiries and reports \> Trial balance**.</span></span>
2. <span data-ttu-id="ea83c-133">Ustaw wartości w następujących polach:</span><span class="sxs-lookup"><span data-stu-id="ea83c-133">Set the following fields:</span></span>

    - <span data-ttu-id="ea83c-134">**Data początkowa** — wprowadź datę rozpoczęcia roku obrachunkowego.</span><span class="sxs-lookup"><span data-stu-id="ea83c-134">**From Date** – Enter the start date of the fiscal year.</span></span>
    - <span data-ttu-id="ea83c-135">**Data końcowa** — wprowadź datę, dla której generowany jest raport.</span><span class="sxs-lookup"><span data-stu-id="ea83c-135">**To Date** – Enter the date that you're generating the report for.</span></span>
    - <span data-ttu-id="ea83c-136">**Wymiar finansowy** — ustaw wartość tego pola na **Ustawione konto główne**.</span><span class="sxs-lookup"><span data-stu-id="ea83c-136">**Financial Dimension** – Set this field to **Main Account set**.</span></span>

3. <span data-ttu-id="ea83c-137">Wybierz pozycję **Oblicz**.</span><span class="sxs-lookup"><span data-stu-id="ea83c-137">Select **Calculate**.</span></span>
4. <span data-ttu-id="ea83c-138">Wyeksportuj raport do programu Excel.</span><span class="sxs-lookup"><span data-stu-id="ea83c-138">Export the report to Excel.</span></span>

<span data-ttu-id="ea83c-139">Teraz powinno być możliwe skopiowanie danych z raportu programu Financial Reporter w programie Excel do raportu **Bilans próbny**, by można było porównać kolumny **Saldo zamknięcia**.</span><span class="sxs-lookup"><span data-stu-id="ea83c-139">You should now be able to copy the data from the Financial Reporter Excel report to the **Trial Balance** report, so that you can compare the **Closing Balance** columns.</span></span>

## <a name="when-i-design-a-report-in-report-designer-or-when-i-generate-a-financial-report-i-received-the-following-message-the-operation-could-not-be-completed-due-to-a-problem-in-the-data-provider-framework-how-should-i-respond"></a><span data-ttu-id="ea83c-140">Podczas projektowania raportu w programie Report Designer lub podczas generowania raportu finansowego wyświetlany jest następujący komunikat: „Nie można zakończyć operacji z powodu problemu w strukturze dostawcy danych.”</span><span class="sxs-lookup"><span data-stu-id="ea83c-140">When I design a report in Report Designer, or when I generate a financial report, I received the following message: "The operation could not be completed due to a problem in the data provider framework."</span></span> <span data-ttu-id="ea83c-141">W jaki sposób należy zareagować?</span><span class="sxs-lookup"><span data-stu-id="ea83c-141">How should I respond?</span></span>

<span data-ttu-id="ea83c-142">Komunikat wskazuje, że wystąpił problem podczas próby pobrania przez system metadanych finansowych ze składnicy danych podczas korzystania z raportowania finansowego.</span><span class="sxs-lookup"><span data-stu-id="ea83c-142">The message indicates that an issue occurred when the system tried to retrieve financial metadata from the data mart while you were using Financial reporting.</span></span> <span data-ttu-id="ea83c-143">Istnieją dwa sposoby odpowiedzi na ten problem:</span><span class="sxs-lookup"><span data-stu-id="ea83c-143">There are two ways to respond to this issue:</span></span>

- <span data-ttu-id="ea83c-144">Aby sprawdzić stan integracji danych, należy w programie Report Designer przejść do opcji **Narzędzia \> Stan integracji**.</span><span class="sxs-lookup"><span data-stu-id="ea83c-144">Review the integration status of the data by going to **Tools \> Integration status** in Report Designer.</span></span> <span data-ttu-id="ea83c-145">Jeśli integracja jest niekompletna, poczekaj na jej zakończenie.</span><span class="sxs-lookup"><span data-stu-id="ea83c-145">If the integration is incomplete, wait for it to be completed.</span></span> <span data-ttu-id="ea83c-146">Po otrzymaniu komunikatu ponów próbę wykonania swojej czynności.</span><span class="sxs-lookup"><span data-stu-id="ea83c-146">Then retry what you were doing when you received the message.</span></span>
- <span data-ttu-id="ea83c-147">Skontaktuj się z pomocą techniczną, aby zidentyfikować i rozwiązać problem.</span><span class="sxs-lookup"><span data-stu-id="ea83c-147">Contact Support to identify and work through the issue.</span></span> <span data-ttu-id="ea83c-148">W systemie mogą być niespójne dane.</span><span class="sxs-lookup"><span data-stu-id="ea83c-148">There might be inconsistent data in the system.</span></span> <span data-ttu-id="ea83c-149">Inżynierowie pomocy technicznej mogą pomóc w zidentyfikowaniu tego problemu na serwerze i odnalezieniu określonych danych, które mogą wymagać aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="ea83c-149">Support engineers can help you identify that issue on the server and find the specific data that might require an update.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
