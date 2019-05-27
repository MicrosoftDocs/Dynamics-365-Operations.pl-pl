---
title: Przeszacowanie w walucie obcej dla kont bankowych
description: Ten temat zawiera informacje o przeszacowywaniu w walucie obcej dla kont bankowych.
author: ShylaThompson
manager: AnnBe
ms.date: 03/28/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 11464
ms.search.region: Czech Republic, Estonia, Latvia, Lithuania, Poland
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 584fc17addca1e967af2be0b8272808e2f3e1c4f
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "1538252"
---
# <a name="currency-revaluation-for-bank-account-transactions"></a><span data-ttu-id="e2317-103">Przeszacowanie w walucie dla transakcji na kontach bankowych</span><span class="sxs-lookup"><span data-stu-id="e2317-103">Currency revaluation for bank account transactions</span></span>

[!include [banner](../includes/banner.md)]

## <a name="revalue-foreign-currency-amounts-for-bank-account-transactions"></a><span data-ttu-id="e2317-104">Zmiana wartości kwoty w walucie obcej dla transakcji na kontach bankowych</span><span class="sxs-lookup"><span data-stu-id="e2317-104">Revalue foreign currency amounts for bank account transactions</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e2317-105">Ta sekcja dotyczy tylko firm, które mają podstawowy adres w Polsce.</span><span class="sxs-lookup"><span data-stu-id="e2317-105">This section applies only to legal entities that have a primary address in Poland.</span></span>

<span data-ttu-id="e2317-106">Można zmienić wartości kwoty w walucie obcej dla transakcji bankowych.</span><span class="sxs-lookup"><span data-stu-id="e2317-106">You can revalue foreign currency amounts for bank transactions.</span></span> <span data-ttu-id="e2317-107">Następnie można utworzyć raport o transakcjach bankowych z korektami przeszacowań w walucie obcej.</span><span class="sxs-lookup"><span data-stu-id="e2317-107">You can then create a report to view the bank transactions that have adjustments for foreign currency revaluations.</span></span>

1. <span data-ttu-id="e2317-108">Wybierz kolejno opcje **Zarządzanie gotówką i bankami** &gt; **Zadania okresowe** &gt; **Bank — różnica kursowa (FIFO/LIFO)**.</span><span class="sxs-lookup"><span data-stu-id="e2317-108">Select **Cash and bank management** &gt; **Periodic tasks** &gt; **Bank - Exchange adjustment (FIFO/LIFO)**.</span></span>
2. <span data-ttu-id="e2317-109">W polu **W dniu** wprowadź datę końcową dotyczącą przeszacowania.</span><span class="sxs-lookup"><span data-stu-id="e2317-109">In the **On date** field, enter an end date for the revaluation.</span></span> <span data-ttu-id="e2317-110">W obliczaniu są uwzględnione tylko transakcje z datami wcześniejszymi od wskazanej daty.</span><span class="sxs-lookup"><span data-stu-id="e2317-110">The calculation includes only transactions that have a date that is before the specified date.</span></span>
3. <span data-ttu-id="e2317-111">Wybierz kolejno opcje **Rekordy do uwzględnienia** &gt; **Filtr** &gt; **Dodaj**, aby dodać konto bankowe.</span><span class="sxs-lookup"><span data-stu-id="e2317-111">Select **Records to include** &gt; **Filter** &gt; **Add** to add a bank account.</span></span> <span data-ttu-id="e2317-112">Jeśli nie określisz konta bankowego, zostaną przeszacowane kwoty dla wszystkich kont bankowych.</span><span class="sxs-lookup"><span data-stu-id="e2317-112">If you don't specify a bank account, amounts are revalued for all bank accounts.</span></span>
4. <span data-ttu-id="e2317-113">Kliknij przycisk **OK**, aby zamknąć stronę zapytania.</span><span class="sxs-lookup"><span data-stu-id="e2317-113">Select **OK** to close the query page.</span></span>
5. <span data-ttu-id="e2317-114">Na stronie **Przeszacowanie w walucie obcej** zaznacz pole wyboru **Ponowne obliczanie**, aby przeszacować kwoty w walucie obcej dla wszystkich otwartych okresów.</span><span class="sxs-lookup"><span data-stu-id="e2317-114">On the **Foreign currency revaluation** page, select the **Recalculation** check box to revalue foreign currency amounts for all open periods.</span></span>

## <a name="create-a-report-to-view-bank-transactions-that-have-adjustments-for-foreign-currency-revaluations"></a><span data-ttu-id="e2317-115">Tworzenie raportu o transakcjach bankowych z korektami przeszacowań w walucie obcej</span><span class="sxs-lookup"><span data-stu-id="e2317-115">Create a report to view bank transactions that have adjustments for foreign currency revaluations</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e2317-116">Ta sekcja dotyczy tylko firm, które mają podstawowy adres w Polsce.</span><span class="sxs-lookup"><span data-stu-id="e2317-116">This section applies only to legal entities that have a primary address in Poland.</span></span>

1. <span data-ttu-id="e2317-117">Wybierz kolejno opcje **Zarządzanie gotówką i bankami** &gt; **Zapytania i raporty** &gt; **Bank — raport korekt kursu wymiany**.</span><span class="sxs-lookup"><span data-stu-id="e2317-117">Select **Cash and bank management** &gt; **Inquiries and reports** &gt; **Bank - Exchange adjustment report**.</span></span>
2. <span data-ttu-id="e2317-118">Wybierz kolejno opcje **Rekordy do uwzględnienia** &gt; **Filtr**, aby znaleźć jedno lub więcej kont bankowych, o których chcesz wyświetlić informacje.</span><span class="sxs-lookup"><span data-stu-id="e2317-118">Select **Records to include** &gt; **Filter** to find one or more bank accounts to view information for.</span></span>
3. <span data-ttu-id="e2317-119">Opcjonalnie: W polu **Konto bankowe** wybierz konto bankowe.</span><span class="sxs-lookup"><span data-stu-id="e2317-119">Optional: In the **Bank account** field, select a bank account.</span></span> <span data-ttu-id="e2317-120">Jeśli zostawisz to pole puste, raport będzie zawierał szczegóły transakcji bankowej dla wszystkich kont bankowych.</span><span class="sxs-lookup"><span data-stu-id="e2317-120">If you leave this field blank, the report includes bank transaction details for all bank accounts.</span></span>
4. <span data-ttu-id="e2317-121">Kliknij przycisk **OK**. Raport zostanie wygenerowany.</span><span class="sxs-lookup"><span data-stu-id="e2317-121">Select **OK** to generate the report.</span></span> 

## <a name="calculate-exchange-rate-adjustments-for-bank-account-transactions"></a><span data-ttu-id="e2317-122">Obliczanie korekt kursu wymiany dla transakcji konta bankowego</span><span class="sxs-lookup"><span data-stu-id="e2317-122">Calculate exchange rate adjustments for bank account transactions</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e2317-123">Ta sekcja dotyczy tylko firm, które mają podstawowy adres w Czechach, Estonii, na Litwie lub na Łotwie.</span><span class="sxs-lookup"><span data-stu-id="e2317-123">This section applies only to legal entities that have a primary address in the Czech Republic, Estonia, Lithuania, or Latvia.</span></span>

<span data-ttu-id="e2317-124">Musisz przeszacować i dostosować konta bankowe, jeśli istnieje różnica kursów wymiany między walutą rozliczeniową i walutą raportowania.</span><span class="sxs-lookup"><span data-stu-id="e2317-124">You must revalue and adjust bank accounts if there is a difference in the exchange rate between the accounting currency and the reporting currency.</span></span> <span data-ttu-id="e2317-125">To zadanie ułatwia obliczenie odpowiedniego salda w walucie rozliczeniowej i walucie raportowania dla kont bankowych.</span><span class="sxs-lookup"><span data-stu-id="e2317-125">This task helps you calculate the correct balance in both the accounting currency and the reporting currency for the bank accounts.</span></span>

1. <span data-ttu-id="e2317-126">Wybierz kolejno opcje **Zarządzanie gotówką i bankami** &gt; **Ustawienia** &gt; **Parametry modułu Zarządzanie gotówką i bankami**.</span><span class="sxs-lookup"><span data-stu-id="e2317-126">Select **Cash and bank management** &gt; **Setup** &gt; **Cash and bank management parameters**.</span></span>
2. <span data-ttu-id="e2317-127">Na karcie **Sekwencje numerów** w polu **Odwołanie** wybierz numerację dla odwołania **Bank — różnice kursowe**.</span><span class="sxs-lookup"><span data-stu-id="e2317-127">On the **Number sequences** tab, in the **Reference** field, select a number sequence for the **Bank - Exchange adjustment** reference.</span></span>
3. <span data-ttu-id="e2317-128">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e2317-128">Close the page.</span></span>
4. <span data-ttu-id="e2317-129">Wybierz kolejno opcje **Księga główna** &gt; **Ustawienia** &gt; **Waluta** &gt; **Kursy wymiany waluty**.</span><span class="sxs-lookup"><span data-stu-id="e2317-129">Select **General ledger** &gt; **Setup** &gt; **Currency** &gt; **Currency exchange rates**.</span></span> <span data-ttu-id="e2317-130">Na stronie **Kursy wymiany waluty** można definiować kurs wymiany między dwiema walutami lub dla pary walut.</span><span class="sxs-lookup"><span data-stu-id="e2317-130">On the **Currency exchange rates** page, you can define the exchange rate between two currencies or a currency pair.</span></span>
5. <span data-ttu-id="e2317-131">Po zakończeniu zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e2317-131">When you've finished, close the page.</span></span>
6. <span data-ttu-id="e2317-132">Wybierz kolejno opcje **Księga główna** &gt; **Ustawienia** &gt; **Księga**.</span><span class="sxs-lookup"><span data-stu-id="e2317-132">Select **General ledger** &gt; **Setup** &gt; **Ledger**.</span></span> <span data-ttu-id="e2317-133">W polach **Niezrealizowana dodatnia różnica kursowa** i **Niezrealizowana ujemna różnica kursowa** wybierz konto główne, dla którego są księgowane kursy wymiany.</span><span class="sxs-lookup"><span data-stu-id="e2317-133">In the **Unrealized gain** and **Unrealized loss** fields, select the main account that the exchange rates are posted for.</span></span>
7. <span data-ttu-id="e2317-134">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e2317-134">Close the page.</span></span>
8. <span data-ttu-id="e2317-135">Wybierz kolejno opcje **Zarządzanie gotówką i bankami** &gt; **Zadania okresowe** &gt; **Przeszacowanie w walucie obcej**.</span><span class="sxs-lookup"><span data-stu-id="e2317-135">Select **Cash and bank management** &gt; **Periodic tasks** &gt; **Foreign currency revaluation**.</span></span>
9. <span data-ttu-id="e2317-136">W polu **W dniu** wybierz datę przeszacowanie lub korekty.</span><span class="sxs-lookup"><span data-stu-id="e2317-136">In the **On date** field, select the revaluation date or adjustment date.</span></span>
10. <span data-ttu-id="e2317-137">W polu **Z waluty** wybierz kod bieżącej waluty.</span><span class="sxs-lookup"><span data-stu-id="e2317-137">In the **From currency** field, select the current currency code.</span></span> <span data-ttu-id="e2317-138">W polu **Na walutę** wybierz walutę, na którą należy dokonać korekty.</span><span class="sxs-lookup"><span data-stu-id="e2317-138">In the **To currency** field, select the currency that the adjustment should be made to.</span></span>
11. <span data-ttu-id="e2317-139">Wybierz kolejno opcje **Rekordy do uwzględnienia** &gt; **Filtr**, aby znaleźć konto bankowe, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="e2317-139">Select **Records to include** &gt; **Filter** to find the bank account, and then select **OK**.</span></span>
12. <span data-ttu-id="e2317-140">Na stronie **Przeszacowanie w walucie obcej** kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="e2317-140">On the **Foreign currency revaluation** page, select **OK**.</span></span> <span data-ttu-id="e2317-141">Zostanie obliczona korekta transakcji kont bankowych dla wybranej daty.</span><span class="sxs-lookup"><span data-stu-id="e2317-141">The adjustment for the bank account transactions on the selected date is calculated.</span></span>

> [!NOTE]
> <span data-ttu-id="e2317-142">W księdze głównej są wyświetlane dwie oddzielne transakcje: jedna w walucie rozliczeniowej i jedna w walucie raportowania.</span><span class="sxs-lookup"><span data-stu-id="e2317-142">In the general ledger, you can view two separate transactions: one for the accounting currency and one for the reporting currency.</span></span>
