---
title: Skonfiguruj opłaty za płatności z urzędu podatku potrącanego u źródła
description: W tym temacie opisano sposób skonfigurowania opłat pobieranych z podatku potrącanego z płatności urzędu źródłowego (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: b52331bb1c7a1bc2c764008112f3df9cc0385995
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023523"
---
# <a name="set-up-payment-fees-for-tds-authority-payments"></a><span data-ttu-id="924b6-103">Skonfiguruj opłaty za płatności z urzędu podatku potrącanego u źródła</span><span class="sxs-lookup"><span data-stu-id="924b6-103">Set up payment fees for TDS authority payments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="924b6-104">W tym temacie opisano sposób skonfigurowania opłat pobieranych z podatku potrącanego z płatności urzędu źródłowego (TDS).</span><span class="sxs-lookup"><span data-stu-id="924b6-104">This topic explains how to set up payment fees that are charged for Tax Deducted at Source (TDS) authority payments.</span></span>

1. <span data-ttu-id="924b6-105">Wybierz kolejno opcje **Rozrachunki z dostawcami \> Ustawienia płatności \> Opłata**.</span><span class="sxs-lookup"><span data-stu-id="924b6-105">Go to **Accounts payable \> Payment setup \> Payment fee**.</span></span>

    <span data-ttu-id="924b6-106">[![Strona Opłata](./media/apac-ind-TDS-28.png)](./media/apac-ind-TDS-28.png)</span><span class="sxs-lookup"><span data-stu-id="924b6-106">[![Payment fee page](./media/apac-ind-TDS-28.png)](./media/apac-ind-TDS-28.png)</span></span>

2. <span data-ttu-id="924b6-107">Wybierz **Nowy**, aby utworzyć opłatę za płatność i wprowadź wymagane szczegóły.</span><span class="sxs-lookup"><span data-stu-id="924b6-107">Select **New** to create a payment fee, and enter the required details.</span></span>
3. <span data-ttu-id="924b6-108">W polu **Typ opłaty** wybierz typ opłaty.</span><span class="sxs-lookup"><span data-stu-id="924b6-108">In the **Fee type** field, select the type of payment fee:</span></span>

    - <span data-ttu-id="924b6-109">**None**</span><span class="sxs-lookup"><span data-stu-id="924b6-109">**None**</span></span>
    - <span data-ttu-id="924b6-110">**Odsetki** — odsetki obciążają opóźnione płatności dokonywane na rzecz dostawcy urzędu TDS.</span><span class="sxs-lookup"><span data-stu-id="924b6-110">**Interest** – Interest is charged on late payments that are made to the TDS authority vendor.</span></span>
    - <span data-ttu-id="924b6-111">**Inne** — Inne opłaty są naliczane za zwłokę w płatnościach na rzecz dostawcy urzędu podatku potrącanego u źródła.</span><span class="sxs-lookup"><span data-stu-id="924b6-111">**Others** – Other charges are charged on late payments that are made to the TDS authority vendor.</span></span>

    <span data-ttu-id="924b6-112">W przypadku wybrania opcji **Odsetki** lub **Inne** pole **Opłata** jest automatycznie ustawiane na **Księga**.</span><span class="sxs-lookup"><span data-stu-id="924b6-112">If you select **Interest** or **Others**, the **Charge** field is automatically set to **Ledger**.</span></span>

4. <span data-ttu-id="924b6-113">Jeśli wybrano opcję **Odsetki** lub **Inne** w polu **Typ pola** , w polu **Konto główne** wybierz konto księgowe, na które mają być księgowane odsetki lub inne opłaty.</span><span class="sxs-lookup"><span data-stu-id="924b6-113">If you selected **Interest** or **Others** in the **Field type** field, in the **Main account** field, select the ledger account to post the interest or other charges to.</span></span>
5. <span data-ttu-id="924b6-114">Wprowadź wymagane dane.</span><span class="sxs-lookup"><span data-stu-id="924b6-114">Enter the other required details.</span></span>
6. <span data-ttu-id="924b6-115">W okienku akcji wybierz **ustawienia opłat płatności**, aby otworzyć stronę **Ustawienia opłat od płatności**, na której można skonfigurować opłaty dla różnych kombinacji banków, metod płatności, specyfikacji płatności, walut i interwałów dat.</span><span class="sxs-lookup"><span data-stu-id="924b6-115">On the Action Pane, select **Payment fee setup** to open the **Payment fee setup** page, where you can set up payment fees for various combinations of banks, methods of payment, payment specifications, currencies, and date intervals.</span></span>

    <span data-ttu-id="924b6-116">[![Strona konfiguracji opłaty za płatność](./media/apac-ind-TDS-21.png)](./media/apac-ind-TDS-21.png)</span><span class="sxs-lookup"><span data-stu-id="924b6-116">[![Payment fee setup page](./media/apac-ind-TDS-21.png)](./media/apac-ind-TDS-21.png)</span></span>

7. <span data-ttu-id="924b6-117">Na karcie **Przegląd** w polu **Grupowanie** określ, dla których banków ma być ustawiana opłata za:</span><span class="sxs-lookup"><span data-stu-id="924b6-117">On the **Overview** tab, in the **Groupings** field, specify which banks you're setting up the payment fee for:</span></span>

    - <span data-ttu-id="924b6-118">**Tabela** — opłata obowiązuje w przypadku określonego konta bankowego.</span><span class="sxs-lookup"><span data-stu-id="924b6-118">**Table** – The fee is valid for a specific bank account.</span></span>
    - <span data-ttu-id="924b6-119">**Grupa** — Opłata obowiązuje dla określonej grupy banków.</span><span class="sxs-lookup"><span data-stu-id="924b6-119">**Group** – The fee is valid for a specific bank group.</span></span>
    - <span data-ttu-id="924b6-120">**Wszystkie** — opłata obowiązuje w przypadku wszystkich kont bankowych.</span><span class="sxs-lookup"><span data-stu-id="924b6-120">**All** – The fee is valid for all the bank accounts.</span></span>

8. <span data-ttu-id="924b6-121">Jeśli wybrano opcję **Tabela** lub **Grupa** w polu **Grupowanie**, w polu **Relacja bankowa** wybierz określone konto bankowe lub grupę bankową, dla których chcesz skonfigurować opłatę za płatność.</span><span class="sxs-lookup"><span data-stu-id="924b6-121">If you selected **Table** or **Group** in the **Groupings** field, in the **Bank relation** field, select the specific bank account or bank group that you're setting up the payment fee for.</span></span>
9. <span data-ttu-id="924b6-122">W polu **Metoda płatności** wybierz sposób uiszczenia opłat.</span><span class="sxs-lookup"><span data-stu-id="924b6-122">In the **Method of payment** field, select the method of payment for the payment of fees.</span></span>
10. <span data-ttu-id="924b6-123">W polu **Specyfikacja płatności** wybierz lub wprowadź kod specyfikacji płatności wygenerowany na stronie **Specyfikacja płatności**.</span><span class="sxs-lookup"><span data-stu-id="924b6-123">In the **Payment specification** field, select or enter the payment specification code that was generated on the **Payment specification** page.</span></span>
    - <span data-ttu-id="924b6-124">Specyfikacja płatności jest używana do płatności za pomocą przelewów elektronicznych.</span><span class="sxs-lookup"><span data-stu-id="924b6-124">The Payment specification is used with electronic fund transfer methods of payment.</span></span>
12. <span data-ttu-id="924b6-125">W polu **Waluta płatności** wybierz walutę, która aktywuje opłatę.</span><span class="sxs-lookup"><span data-stu-id="924b6-125">In the **Payment currency** field, select the currency that activates the fee.</span></span> <span data-ttu-id="924b6-126">Tylko transakcje, w których jest aktywna wybrana waluta, mogą uaktywnić opłatę.</span><span class="sxs-lookup"><span data-stu-id="924b6-126">Only transactions that use the selected currency can activate the fee.</span></span> <span data-ttu-id="924b6-127">Jeśli to pole jest puste, opłaty są aktywowane przez wszystkie waluty.</span><span class="sxs-lookup"><span data-stu-id="924b6-127">If you leave this field blank, all currencies activate the fee.</span></span>
13. <span data-ttu-id="924b6-128">W polu **Procent/Kwota** wybierz metodę obliczania.</span><span class="sxs-lookup"><span data-stu-id="924b6-128">In the **Percentage/Amount** field, select the calculation method.</span></span> <span data-ttu-id="924b6-129">Dostępne opcje to **Kwota**, **Procent** i **Interwał**.</span><span class="sxs-lookup"><span data-stu-id="924b6-129">The options are **Amount**, **Percent**, and **Interval**.</span></span>
14. <span data-ttu-id="924b6-130">W polu **Kwota opłaty** określ kwotę opłaty jako procent płatności lub kwotę jednej płatności.</span><span class="sxs-lookup"><span data-stu-id="924b6-130">In the **Fee amount** field, specify the fee amount as either a percentage of the payment or the amount for one payment.</span></span>
15. <span data-ttu-id="924b6-131">W polu **Waluta opłaty** określ kod waluty opłaty.</span><span class="sxs-lookup"><span data-stu-id="924b6-131">In the **Fee currency** field, specify the currency code for the fee.</span></span>
16. <span data-ttu-id="924b6-132">Wybierz kartę **Ogólne**, aby wyświetlić lub zmodyfikować szczegóły wybranego konta bankowego.</span><span class="sxs-lookup"><span data-stu-id="924b6-132">Select the **General** tab to view or modify the details for the selected bank account.</span></span>

    <span data-ttu-id="924b6-133">[![Karta Ogólne](./media/apac-ind-TDS-22.png)](./media/apac-ind-TDS-22.png)</span><span class="sxs-lookup"><span data-stu-id="924b6-133">[![General tab](./media/apac-ind-TDS-22.png)](./media/apac-ind-TDS-22.png)</span></span>

16. <span data-ttu-id="924b6-134">W polu **Minimum** wprowadź minimalną kwotę transakcji, która aktywuje opłatę.</span><span class="sxs-lookup"><span data-stu-id="924b6-134">In the **Minimum** field, enter the minimum transaction amount that activates the fee.</span></span>
17. <span data-ttu-id="924b6-135">W polu **Maksimum** wprowadź maksymalną kwotę transakcji, która aktywuje opłatę.</span><span class="sxs-lookup"><span data-stu-id="924b6-135">In the **Maximum** field, enter the maximum transaction amount that activates the fee.</span></span>
18. <span data-ttu-id="924b6-136">W polach **Od dnia** i **Do dnia** zdefiniuj zakres dat naliczania opłat.</span><span class="sxs-lookup"><span data-stu-id="924b6-136">In the **From date** and **To date** fields, define a date range for calculating fees.</span></span>
19. <span data-ttu-id="924b6-137">W polu **Opłata minimalna** określ kwotę opłaty jako procent płatności lub kwotę jednej płatności.</span><span class="sxs-lookup"><span data-stu-id="924b6-137">In the **Minimum fee** field, specify the amount of the fee as either a percentage of the payment or the amount for one payment.</span></span>
20. <span data-ttu-id="924b6-138">W polu **Grupa podatków** wybierz grupę podatków, która ma być obliczana dla kwoty opłaty.</span><span class="sxs-lookup"><span data-stu-id="924b6-138">In the **Sales tax group** field, select the sales tax group to use to calculate the sales tax for the fee amount.</span></span>
21. <span data-ttu-id="924b6-139">W polu **Grupa podatku od sprzedaży towaru** wybierz grupę podatków dla towaru, która ma być użyta do obliczenia podatku od sprzedaży towaru dla kwoty opłaty.</span><span class="sxs-lookup"><span data-stu-id="924b6-139">In the **Item sales tax group** field, select the item sales tax group to use to calculate the item sales tax for the fee amount.</span></span>
22. <span data-ttu-id="924b6-140">Wybierz kartę **Interwał**.</span><span class="sxs-lookup"><span data-stu-id="924b6-140">Select the **Interval** tab.</span></span> 

    <span data-ttu-id="924b6-141">[![Karta Interwał](./media/apac-ind-TDS-23.png)](./media/apac-ind-TDS-23.png)</span><span class="sxs-lookup"><span data-stu-id="924b6-141">[![Interval tab](./media/apac-ind-TDS-23.png)](./media/apac-ind-TDS-23.png)</span></span>

23. <span data-ttu-id="924b6-142">W polu **Dni** należy wpisać liczbę dni pomiędzy datą księgowania (datą dyskonta) przekazu a datą płatności skryptu dłużnego.</span><span class="sxs-lookup"><span data-stu-id="924b6-142">In the **Days** field, enter the number of days between the posting date (discounting date) of the payment and the due date of the promissory note.</span></span>
24. <span data-ttu-id="924b6-143">W polu **Procent/Kwota** określ, czy specyfikacja jest wartością procentową czy kwotą zestawu.</span><span class="sxs-lookup"><span data-stu-id="924b6-143">In the **Percentage/Amount** field, select whether the specification is a percentage or a set amount.</span></span>
25. <span data-ttu-id="924b6-144">W polu **Kwota opłaty** określ kwotę opłaty jako procent płatności lub kwotę jednej płatności.</span><span class="sxs-lookup"><span data-stu-id="924b6-144">In the **Fee amount** field, enter the amount of the fee as either a percentage of the payment or the amount for one payment.</span></span>
26. <span data-ttu-id="924b6-145">Zamknij stronę **Ustawienia opłaty** od płatności.</span><span class="sxs-lookup"><span data-stu-id="924b6-145">Close the **Payment fee setup** page.</span></span>
27. <span data-ttu-id="924b6-146">Zamknij stronę **Ustawienia opłaty** od płatności.</span><span class="sxs-lookup"><span data-stu-id="924b6-146">Close the **Payment fee** page.</span></span>
