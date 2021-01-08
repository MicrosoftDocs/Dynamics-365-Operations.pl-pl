---
title: Naliczanie subskrypcji
description: W przypadku subskrypcji serwisu należy ręcznie naliczać przychód w okresach następujących po dacie zafakturowania transakcji opłaty.
author: ShylaThompson
manager: tfehr
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMASubscriptionGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ebd65655db56ee1169f24dbc79fbfb5130f06a5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435177"
---
# <a name="accruing-subscriptions"></a><span data-ttu-id="e7dfe-103">Naliczanie subskrypcji</span><span class="sxs-lookup"><span data-stu-id="e7dfe-103">Accruing subscriptions</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="e7dfe-104">W przypadku subskrypcji serwisu należy ręcznie naliczać przychód w okresach następujących po dacie zafakturowania transakcji opłaty.</span><span class="sxs-lookup"><span data-stu-id="e7dfe-104">With service subscriptions, you manually accrue revenue in the periods following the date when you invoiced a fee transaction.</span></span>

<span data-ttu-id="e7dfe-105">Okresy naliczania są tworzone dla okresu fakturowania skonfigurowanego dla opłaty subskrypcji i są oparte na kodzie okresu subskrypcji.</span><span class="sxs-lookup"><span data-stu-id="e7dfe-105">Accrual periods are created for the invoice period that you set up for the subscription fee, and the accrual periods are based on the period code of the subscription.</span></span>

<span data-ttu-id="e7dfe-106">Można naliczyć przychód i można też wycofać naliczony przychód.</span><span class="sxs-lookup"><span data-stu-id="e7dfe-106">You can accrue and reverse accrued revenue.</span></span>

## <a name="reverse-accruals-of-credit-amounts"></a><span data-ttu-id="e7dfe-107">Stornowanie naliczeń kwot uznań</span><span class="sxs-lookup"><span data-stu-id="e7dfe-107">Reverse accruals of credit amounts</span></span>

<span data-ttu-id="e7dfe-108">Jeśli zapiszesz zafakturowane kwoty subskrypcji po stronie kredytowej (uznasz je), można użyć dwóch metod do wycofania naliczonych kwot:</span><span class="sxs-lookup"><span data-stu-id="e7dfe-108">If you credit invoiced subscription amounts, you can use two methods to reverse the accrual amounts:</span></span>

  - <span data-ttu-id="e7dfe-109">Każdą transakcję naliczenia przychodu można wycofać indywidualnie przed utworzeniem propozycji faktury korygującej dla transakcji.</span><span class="sxs-lookup"><span data-stu-id="e7dfe-109">You can reverse each accrued revenue transaction individually before you create the credit note proposal for the transaction.</span></span> <span data-ttu-id="e7dfe-110">To jest metoda ręczna.</span><span class="sxs-lookup"><span data-stu-id="e7dfe-110">This is the manual method.</span></span> <span data-ttu-id="e7dfe-111">(ręcznie)</span><span class="sxs-lookup"><span data-stu-id="e7dfe-111">(manual)</span></span>

  - <span data-ttu-id="e7dfe-112">Naliczone kwoty można wycofać na dzień zaksięgowania faktury korygującej lub na pierwotny dzień zaksięgowania naliczenia.</span><span class="sxs-lookup"><span data-stu-id="e7dfe-112">You can have the accrued amounts reversed on the date where the credit note is posted or on the original posting date of the accrual.</span></span>

<span data-ttu-id="e7dfe-113">Aby uzyskać więcej informacji, zobacz temat [Parametry subskrypcji (formularz)](https://technet.microsoft.com/library/aa619615.aspx).</span><span class="sxs-lookup"><span data-stu-id="e7dfe-113">For more information, see [Subscription parameters (form)](https://technet.microsoft.com/library/aa619615.aspx).</span></span>

## <a name="setup-requirements"></a><span data-ttu-id="e7dfe-114">Skonfiguruj wymagania</span><span class="sxs-lookup"><span data-stu-id="e7dfe-114">Setup requirements</span></span>

<span data-ttu-id="e7dfe-115">Aby można było naliczać przychód, muszą być spełnione następujące wymagania dotyczące danych:</span><span class="sxs-lookup"><span data-stu-id="e7dfe-115">To accrue revenue, make sure that the following data requirements are met:</span></span>

## <a name="account-setup"></a><span data-ttu-id="e7dfe-116">Konfiguracja kont</span><span class="sxs-lookup"><span data-stu-id="e7dfe-116">Account setup</span></span>

<span data-ttu-id="e7dfe-117">Konta **PWT — subskrypcja** i **Naliczony przychód — subskrypcja** muszą być skonfigurowane w module **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="e7dfe-117">The **WIP - subscription** and the **Accrued revenue - subscription** accounts must be set up in the **Project** module.</span></span>

<span data-ttu-id="e7dfe-118">Podczas księgowania naliczonego przychodu naliczona kwota jest księgowana po stronie debetowej konta **PWT — subskrypcja** i po stronie kredytowej konta **Naliczony przychód — subskrypcja**.</span><span class="sxs-lookup"><span data-stu-id="e7dfe-118">When you post accrued revenue, the **WIP - subscription** account is debited with the accrual amount, and the **Accrued revenue - subscription** account is credited with the accrual amount.</span></span>

## <a name="set-up-accounts-for-accrual-of-subscription-revenue"></a><span data-ttu-id="e7dfe-119">Konfigurowanie kont służących do naliczania przychodu subskrypcji</span><span class="sxs-lookup"><span data-stu-id="e7dfe-119">Set up accounts for accrual of subscription revenue</span></span>

1.  <span data-ttu-id="e7dfe-120">Kliknij kolejno opcje **Zarządzanie projektami i ich księgowanie** \> **Ustawienia** \> **Księgowanie** \> **Konfiguracja księgowania**.</span><span class="sxs-lookup"><span data-stu-id="e7dfe-120">Click **Project management and accounting** \> **Setup** \> **Posting** \> **Ledger posting setup**.</span></span>

2.  <span data-ttu-id="e7dfe-121">Kliknij kartę **Konta przychodów**, a następnie wybierz opcję **PWT — subskrypcja** lub **Naliczony przychód — subskrypcja** i skonfiguruj konta.</span><span class="sxs-lookup"><span data-stu-id="e7dfe-121">Click the **Revenue accounts** tab, and select **WIP - subscription** or **Accrued revenue - subscription** to set up the accounts.</span></span>

## <a name="subscription-group-setup"></a><span data-ttu-id="e7dfe-122">Konfiguracja grupy subskrypcji</span><span class="sxs-lookup"><span data-stu-id="e7dfe-122">Subscription group setup</span></span>

<span data-ttu-id="e7dfe-123">Aby można było naliczać przychody z subskrypcji, musi być zaznaczone pole wyboru **Nalicz przychód**.</span><span class="sxs-lookup"><span data-stu-id="e7dfe-123">To be able to accrue revenue for subscriptions, the **Accrue revenue** check box must be selected.</span></span> <span data-ttu-id="e7dfe-124">Znajduje się ono w formularzu **Grupy subskrypcji** dla grupy dołączonej do subskrypcji.</span><span class="sxs-lookup"><span data-stu-id="e7dfe-124">This is found on the **Subscription groups** form for the group that is attached to the subscription.</span></span> <span data-ttu-id="e7dfe-125">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Ustawienia** \> **Subskrypcje serwisowe** \> **Grupy subskrypcji**.</span><span class="sxs-lookup"><span data-stu-id="e7dfe-125">Click **Service management** \> **Setup** \> **Service subscriptions** \> **Subscription groups**.</span></span>

## <a name="enable-revenue-accrual-on-a-subscription-group"></a><span data-ttu-id="e7dfe-126">Włączanie naliczania przychodu w grupie subskrypcji</span><span class="sxs-lookup"><span data-stu-id="e7dfe-126">Enable revenue accrual on a subscription group</span></span>

1.  <span data-ttu-id="e7dfe-127">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Ustawienia** \> **Subskrypcje serwisowe** \> **Grupy subskrypcji**.</span><span class="sxs-lookup"><span data-stu-id="e7dfe-127">Click **Service management** \> **Setup** \> **Service subscriptions** \> **Subscription groups**.</span></span>

## <a name="periods"></a><span data-ttu-id="e7dfe-128">Okresy</span><span class="sxs-lookup"><span data-stu-id="e7dfe-128">Periods</span></span>

<span data-ttu-id="e7dfe-129">Trzeba skonfigurować kod okresu fakturowania.</span><span class="sxs-lookup"><span data-stu-id="e7dfe-129">You must set up an invoicing period code.</span></span> <span data-ttu-id="e7dfe-130">Należy również skonfigurować okres naliczania, chyba że przychód ma być naliczany w tych samych przedziałach czasowych, jak używane dla fakturowania.</span><span class="sxs-lookup"><span data-stu-id="e7dfe-130">Unless you want to accrue revenue in the same time intervals as you use for invoicing, you must also set up an accrual period.</span></span>

<span data-ttu-id="e7dfe-131">W następującej tabeli pokazano, które okresy naliczania można skonfigurować w poszczególnych okresach fakturowania:</span><span class="sxs-lookup"><span data-stu-id="e7dfe-131">The following table provides an overview of which accrual periods can be set up for each invoicing period:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="e7dfe-132">Okres fakturowania</span><span class="sxs-lookup"><span data-stu-id="e7dfe-132">Invoicing period</span></span></p></th>
<th><p><span data-ttu-id="e7dfe-133">Okres naliczania</span><span class="sxs-lookup"><span data-stu-id="e7dfe-133">Accrual period</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e7dfe-134"><strong>Lata</strong></span><span class="sxs-lookup"><span data-stu-id="e7dfe-134"><strong>Years</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e7dfe-135"><strong>Lata</strong></span><span class="sxs-lookup"><span data-stu-id="e7dfe-135"><strong>Years</strong></span></span></p></li>
<li><p><span data-ttu-id="e7dfe-136"><strong>Kwartał</strong></span><span class="sxs-lookup"><span data-stu-id="e7dfe-136"><strong>Quarter</strong></span></span></p></li>
<li><p><span data-ttu-id="e7dfe-137"><strong>Miesiąc</strong></span><span class="sxs-lookup"><span data-stu-id="e7dfe-137"><strong>Month</strong></span></span></p></li>
<li><p><span data-ttu-id="e7dfe-138"><strong>Dzień</strong></span><span class="sxs-lookup"><span data-stu-id="e7dfe-138"><strong>Day</strong></span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7dfe-139"><strong>Kwartał</strong></span><span class="sxs-lookup"><span data-stu-id="e7dfe-139"><strong>Quarter</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e7dfe-140"><strong>Kwartał</strong></span><span class="sxs-lookup"><span data-stu-id="e7dfe-140"><strong>Quarter</strong></span></span></p></li>
<li><p><span data-ttu-id="e7dfe-141"><strong>Miesiąc</strong></span><span class="sxs-lookup"><span data-stu-id="e7dfe-141"><strong>Month</strong></span></span></p></li>
<li><p><span data-ttu-id="e7dfe-142"><strong>Dzień</strong></span><span class="sxs-lookup"><span data-stu-id="e7dfe-142"><strong>Day</strong></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7dfe-143"><strong>Miesiąc</strong></span><span class="sxs-lookup"><span data-stu-id="e7dfe-143"><strong>Month</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e7dfe-144"><strong>Miesiąc</strong></span><span class="sxs-lookup"><span data-stu-id="e7dfe-144"><strong>Month</strong></span></span></p></li>
<li><p><span data-ttu-id="e7dfe-145"><strong>Dzień</strong></span><span class="sxs-lookup"><span data-stu-id="e7dfe-145"><strong>Day</strong></span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7dfe-146"><strong>Tydzień</strong></span><span class="sxs-lookup"><span data-stu-id="e7dfe-146"><strong>Week</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e7dfe-147"><strong>Dzień</strong></span><span class="sxs-lookup"><span data-stu-id="e7dfe-147"><strong>Day</strong></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7dfe-148"><strong>Dzień</strong></span><span class="sxs-lookup"><span data-stu-id="e7dfe-148"><strong>Day</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e7dfe-149"><strong>Dzień</strong></span><span class="sxs-lookup"><span data-stu-id="e7dfe-149"><strong>Day</strong></span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e7dfe-150">Skonfigurowanie okresu fakturowania jest obowiązkowym elementem całościowej konfiguracji grupy subskrypcji.</span><span class="sxs-lookup"><span data-stu-id="e7dfe-150">Setting up the invoicing period is a mandatory part of the overall subscription group setup.</span></span> <span data-ttu-id="e7dfe-151">Można zdecydować, czy chcesz również ustawić okres naliczania dla grupy subskrypcji.</span><span class="sxs-lookup"><span data-stu-id="e7dfe-151">You can decide whether to also set up an accrual period for the subscription group.</span></span> <span data-ttu-id="e7dfe-152">W przypadku skonfigurowania okresu naliczania dla grupy subskrypcji okres ten będzie sugerowany w polu **Kod okresu**.</span><span class="sxs-lookup"><span data-stu-id="e7dfe-152">If you set up an accrual period for the subscription group, this period is suggested in the **Period code** field.</span></span> <span data-ttu-id="e7dfe-153">To pole znajduje się w formularzu **Naliczanie przychodu z subskrypcji** podczas naliczania przychodu z subskrypcji.</span><span class="sxs-lookup"><span data-stu-id="e7dfe-153">This field is found in the **Accrue subscription revenue** form, when you accrue subscription revenue.</span></span> <span data-ttu-id="e7dfe-154">Jednak okres naliczania jest opcjonalnym ustawieniem konfiguracji dla grupy subskrypcji.</span><span class="sxs-lookup"><span data-stu-id="e7dfe-154">However, the accrual period is optional information about the subscription group.</span></span>


> [!NOTE]
> <P><span data-ttu-id="e7dfe-155">Aby otworzyć formularz <STRONG>Naliczanie przychodu z subskrypcji</STRONG>, użyj następującej ścieżki.</span><span class="sxs-lookup"><span data-stu-id="e7dfe-155">Use the following path to open the <STRONG>Accrue subscription revenue</STRONG> form.</span></span> <span data-ttu-id="e7dfe-156">Kliknij kolejno opcje <STRONG>Zarządzanie serwisem</STRONG> &gt; <STRONG>Okresowe</STRONG> &gt; <STRONG>Subskrypcje serwisowe</STRONG> &gt; <STRONG>Naliczanie przychodu z subskrypcji</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="e7dfe-156">Click <STRONG>Service management</STRONG> &gt; <STRONG>Periodic</STRONG> &gt; <STRONG>Service subscriptions</STRONG> &gt; <STRONG>Accrue subscription revenue</STRONG>.</span></span></P>


## <a name="transactions"></a><span data-ttu-id="e7dfe-157">Transakcje</span><span class="sxs-lookup"><span data-stu-id="e7dfe-157">Transactions</span></span>

<span data-ttu-id="e7dfe-158">Można określić liczbę transakcji finansowych, które będą tworzone podczas księgowania naliczonego przychodu.</span><span class="sxs-lookup"><span data-stu-id="e7dfe-158">You can control the number of ledger transactions that are created when you post accrued revenue.</span></span> <span data-ttu-id="e7dfe-159">W subskrypcjach określ, czy transakcje finansowe mają tworzone jako sumy czy dla poszczególnych wierszy.</span><span class="sxs-lookup"><span data-stu-id="e7dfe-159">On subscriptions, define if the ledger transactions should be created as a total or per line.</span></span>

## <a name="specify-the-level-of-posting-details-to-display-for-accrued-transactions"></a><span data-ttu-id="e7dfe-160">Określanie poziomu szczegółów dotyczących księgowania, które mają być wyświetlane dla naliczonych transakcji</span><span class="sxs-lookup"><span data-stu-id="e7dfe-160">Specify the level of posting details to display for accrued transactions</span></span>

1.  <span data-ttu-id="e7dfe-161">Kliknij kolejno opcje **Zarządzanie projektami i ich księgowanie** \> **Ustawienia** \> **Parametry modułu Zarządzanie projektami i ich księgowanie**.</span><span class="sxs-lookup"><span data-stu-id="e7dfe-161">Click **Project management and accounting** \> **Setup** \> **Project management and accounting parameters**.</span></span>

2.  <span data-ttu-id="e7dfe-162">Na karcie **Finanse** w polu **Faktura** zaznacz opcję **Suma** lub **Wiersz**.</span><span class="sxs-lookup"><span data-stu-id="e7dfe-162">On the **Financial** tab, in the **Invoice** field, select **Total** or **Line**.</span></span>


## <a name="see-also"></a><span data-ttu-id="e7dfe-163">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="e7dfe-163">See also</span></span>

[<span data-ttu-id="e7dfe-164">Nalicz przychód subskrypcji</span><span class="sxs-lookup"><span data-stu-id="e7dfe-164">Accrue subscription revenue</span></span>](accrue-subscription-revenue.md)

  


