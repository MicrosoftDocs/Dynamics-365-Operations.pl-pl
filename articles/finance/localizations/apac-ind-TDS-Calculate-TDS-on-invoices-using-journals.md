---
title: Obliczanie TDS dla faktur przy użyciu arkuszy
description: W tym temacie wymieniono kroki obliczania podatku potrąconego w źródle (TDS) dla arkuszy.
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
ms.openlocfilehash: d68e1b3a4dc31823ec56a525149f16bdc23c0883
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023522"
---
# <a name="calculate-tds-on-invoices-using-journals"></a><span data-ttu-id="df242-103">Obliczanie TDS dla faktur przy użyciu arkuszy</span><span class="sxs-lookup"><span data-stu-id="df242-103">Calculate TDS on invoices using journals</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="df242-104">W tym temacie wymieniono kroki obliczania podatku potrąconego w źródle (TDS) dla arkuszy.</span><span class="sxs-lookup"><span data-stu-id="df242-104">This topic lists the steps for calculating Tax Deducted at Source (TDS) on journals.</span></span>

<span data-ttu-id="df242-105">Otwórz **Księga główna** (**Księga główna > Wpisy w arkuszu > Arkusze finansowe**).</span><span class="sxs-lookup"><span data-stu-id="df242-105">Begin by opening the **General journals** page (**General ledger > Journal entries > General journals**).</span></span>

<span data-ttu-id="df242-106">[![Arkusze finansowe](./media/apac-ind-TDS-57.png)](./media/apac-ind-TDS-57.png)</span><span class="sxs-lookup"><span data-stu-id="df242-106">[![General journals](./media/apac-ind-TDS-57.png)](./media/apac-ind-TDS-57.png)</span></span>

1. <span data-ttu-id="df242-107">Umożliwia tworzenie wierszy arkusza przy użyciu formularzy arkusza wymienionych w tabeli.</span><span class="sxs-lookup"><span data-stu-id="df242-107">Create journal lines using the journal forms that are listed in the table.</span></span> <span data-ttu-id="df242-108">Wybierz typ konta i typ konta przeciwstawowego oraz wprowadź kwotę transakcji.</span><span class="sxs-lookup"><span data-stu-id="df242-108">Select the account type and offset account type and enter the amount for the transaction.</span></span> 

   > [!NOTE]
   > <span data-ttu-id="df242-109">Na stronie **Arkusz zatwierdzania faktur** wybierz pozycję **Znajdź załączniki i wybierz faktury**, dla których mają być obliczana wartość TDS.</span><span class="sxs-lookup"><span data-stu-id="df242-109">On the **Invoice approval journal** page, select **Find vouchers** and select invoices to calculate TDS on.</span></span> <span data-ttu-id="df242-110">Wyświetlanie faktur utworzonych na stronie **Rejestr faktur** lub na stronie **Znajdowanie załączników**.</span><span class="sxs-lookup"><span data-stu-id="df242-110">View the invoices created in the **Invoice register** page or the **Find vouchers** page.</span></span>  

2. <span data-ttu-id="df242-111">Na karcie **Ogólne**, na stronie **Załącznik arkusza** w polu **Grupy TDS** przejrzyj lub zmień domyślną grupę TDS zdefiniowaną dla dostawcy lub odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="df242-111">On the **General** tab of the **Journal voucher** page, view or modify the default TDS group defined for the vendor or customer, in the **TDS group** field.</span></span> <span data-ttu-id="df242-112">Kwota podatku potrącanego u źródła, która jest obliczana w wierszach arkusza, jest oparta na formule zdefiniowanej dla kodów podatku potrąconego podatku u źródła wymienionych w polu **Grupa potrącenia podatku u źródła**.</span><span class="sxs-lookup"><span data-stu-id="df242-112">The TDS amount that's calculated on journal lines is based on the formula defined for the TDS tax codes listed in the **TDS group** field.</span></span> 

   > [!NOTE]
   > <span data-ttu-id="df242-113">Pole **Grupa podatku u źródła** i pole **Grupa TCS** stają się niedostępne po wybraniu grupy podatku u źródła w polu **Grupa podatku u źródła**.</span><span class="sxs-lookup"><span data-stu-id="df242-113">The **Withholding tax group**  field and the **TCS group** field become unavailable when you select a TDS group in the **TDS group** field.</span></span> <span data-ttu-id="df242-114">Pole **Grupa potrąconej zaliczki na podatek** jest dostępne tylko na **stronie arkusza ogólnego**.</span><span class="sxs-lookup"><span data-stu-id="df242-114">The **Withholding tax group** field is available only on the **General journal** page.</span></span> <span data-ttu-id="df242-115">TDS jest obliczany tylko wtedy, gdy pole wyboru **Oblicz zaliczkę na podatek** jest zaznaczone dla dostawcy lub odbiorcy na stronie **Wszyscy dostawcy** lub **Wszyscy odbiorcy**.</span><span class="sxs-lookup"><span data-stu-id="df242-115">TDS is calculated only if the **Calculate withholding tax** check box is selected for the vendor or customer on the **All vendors** or **All customers** pages.</span></span>   

3. <span data-ttu-id="df242-116">Wybierz kartę **Informacje podatkowe**. W razie potrzeby wybierz w tym polu alternatywne adresy firmy, która została skonfigurowana dla firmy.</span><span class="sxs-lookup"><span data-stu-id="df242-116">Select the **Tax information** tab. Select the alternate addresses of a company that's set up for the company in this field, if required.</span></span> <span data-ttu-id="df242-117">Nazwa firmy jest wyświetlana w polu **Nazwa**, które znajduje się w grupie **pól Informacje o firmie**.</span><span class="sxs-lookup"><span data-stu-id="df242-117">You can view the company name in the **Name** field, which is under the **Company information** field group.</span></span> 

4. <span data-ttu-id="df242-118">Wyświetl rodzaj kategorii osoby oceniającej dostawcy lub klienta w polu **Rodzaj osoby oceniającej**, które znajduje się w grupie pól **Podatek u źródła**.</span><span class="sxs-lookup"><span data-stu-id="df242-118">View the nature of assessee category of the vendor or customer in the **Nature of assessee** field, which is under the **Withholding tax** field group.</span></span> <span data-ttu-id="df242-119">W polu **Numer konta podatkowego** (**TAN**) jest wyświetlany numer TAN wybranej nazwy firmy.</span><span class="sxs-lookup"><span data-stu-id="df242-119">In the **Tax Account Number** (**TAN**) field, view the TAN of the selected company name that's displayed.</span></span>  

5. <span data-ttu-id="df242-120">Wybierz przycisk **Potrącona zaliczka na podatek** w meny **Potrącona zaliczka na podatek**, aby otworzyć stronę **Tymczasowe transakcje potrącenia zaliczki na podatek**.</span><span class="sxs-lookup"><span data-stu-id="df242-120">Select **Withholding tax** in **Withholding tax** menu to open the **Temporary withholding tax transactions** page.</span></span> <span data-ttu-id="df242-121">Wyświetl następujące pola w górnym okienku strony **Tymczasowe transakcje potrącenia zaliczki na podatek**.</span><span class="sxs-lookup"><span data-stu-id="df242-121">The following fields are displayed on the upper pane of the **Temporary withholding tax transactions** page.</span></span>

   - <span data-ttu-id="df242-122">**Łączna kwota potrąconej zaliczki na podatek** — łączna kwota TDS obliczona dla transakcji dla grupy TDS.</span><span class="sxs-lookup"><span data-stu-id="df242-122">**Withholding tax amount in total** - The total TDS calculated for the transaction for the TDS group.</span></span>

   - <span data-ttu-id="df242-123">**Wartość** - łączna wartość procentowa użyta do obliczenia TDS dla transakcji.</span><span class="sxs-lookup"><span data-stu-id="df242-123">**Value** - The total percentage used to calculate TDS for the transaction.</span></span> <span data-ttu-id="df242-124">Łączny procent jest oparty na formule zdefiniowanej dla kodów podatków TDS i dołączonej do grupy TDS.</span><span class="sxs-lookup"><span data-stu-id="df242-124">The total percentage is based on the formula that is defined for TDS tax codes attached to the TDS group.</span></span>

   - <span data-ttu-id="df242-125">**Skorygowana łączna kwota potrąconej zaliczki na podatek** - łączna skorygowana kwota TDS dla wszystkich kodów podatków w grupie TDS.</span><span class="sxs-lookup"><span data-stu-id="df242-125">**Adjusted withholding tax amount in total** - The total adjusted TDS amount for all tax codes in the TDS group.</span></span>

   - <span data-ttu-id="df242-126">**TDS** — jeśli ta opcja jest zaznaczona, do transakcji jest dołączona grupa TDS.</span><span class="sxs-lookup"><span data-stu-id="df242-126">**TDS** - If selected, a TDS group is attached to the transaction.</span></span>

  <span data-ttu-id="df242-127">Pola na kartach **Przegląd**, **Ogólne** i **Korekta** na stronie **Tymczasowe transakcje potrącenia zaliczki na podatek** pokazują obliczoną kwotę TDS oraz szczegóły skorygowanej kwoty TDS dla każdego kodu podatku TDS dołączonego do grupy TDS.</span><span class="sxs-lookup"><span data-stu-id="df242-127">The fields on the **Overview**, **General**, and **Adjustment** tabs on the **Temporary withholding tax transactions** page display the calculated TDS amount and adjusted TDS amount details for each TDS tax code attached to the TDS group.</span></span>

6. <span data-ttu-id="df242-128">Wybierz **pozycję Próg**, aby otworzyć stronę **Próg**.</span><span class="sxs-lookup"><span data-stu-id="df242-128">Select **Threshold** to open the **Threshold** page.</span></span> <span data-ttu-id="df242-129">Umożliwia wyświetlenie na tej stronie limitu progowego zdefiniowanego dla składnika podatku TDS dołączonego do określonego kodu podatku TDS.</span><span class="sxs-lookup"><span data-stu-id="df242-129">View the threshold limit and exception threshold limit defined for the TDS tax component attached to a specific TDS tax code on this page.</span></span>

   <span data-ttu-id="df242-130">Wybierz opcję **Projektant formuł**, aby otworzyć formularz **Projektant formuł**.</span><span class="sxs-lookup"><span data-stu-id="df242-130">Select **Formula designer** to open the **Formula designer** form.</span></span> <span data-ttu-id="df242-131">Na tej stronie można wyświetlić formułę zdefiniowaną dla określonego kodu podatku TDS.</span><span class="sxs-lookup"><span data-stu-id="df242-131">View the formula defined for a specific TDS tax code in this page.</span></span> <span data-ttu-id="df242-132">Zamknij strony **Konstruktor formuł** i **Tymczasowe transakcje potrącenia zaliczki na podatek**, aby powrócić do **strony załącznika arkusza**.</span><span class="sxs-lookup"><span data-stu-id="df242-132">Close the **Formula designer** and **Temporary withholding tax transactions** pages to return to the **Journal voucher** page.</span></span>

8. <span data-ttu-id="df242-133">Wprowadź wymagane dane.</span><span class="sxs-lookup"><span data-stu-id="df242-133">Enter the other required details.</span></span> <span data-ttu-id="df242-134">Sprawdź poprawność arkusza i zaksięguj go.</span><span class="sxs-lookup"><span data-stu-id="df242-134">Validate and post the journal.</span></span> <span data-ttu-id="df242-135">Kwota TDS obliczona na fakturach zakupu jest księgowana na koncie rozrachunków z dostawcami.</span><span class="sxs-lookup"><span data-stu-id="df242-135">The TDS amount that's calculated on purchase invoices is posted to the payable account.</span></span> <span data-ttu-id="df242-136">Kwota podatku potrącanego u źródła obliczona na fakturach sprzedaży jest księgowana na koncie należności zdefiniowanym dla każdego kodu podatku potrącanego u źródła w grupie podatku potrąconego u źródła.</span><span class="sxs-lookup"><span data-stu-id="df242-136">The TDS amount that's calculated on sales invoices is posted to the receivable account that is defined for each TDS tax code in the TDS group.</span></span> <span data-ttu-id="df242-137">Konta rozrachunków lub należności dla kodów podatku TDS są definiowane na stronie **Kody potrąconych zaliczek na podatek**.</span><span class="sxs-lookup"><span data-stu-id="df242-137">The payable accounts or receivable accounts for TDS tax codes are defined on the **Withholding tax codes** page.</span></span>

9. <span data-ttu-id="df242-138">Wybierz przycisk **Zaksięgowana potrącona zaliczka na podatek**, aby otworzyć stronę **transakcje** **potrącenia** **zaliczki**.</span><span class="sxs-lookup"><span data-stu-id="df242-138">Select **Posted withholding tax** to open the **Withholding** **tax** **transactions** page.</span></span> <span data-ttu-id="df242-139">**Wartość** pokazuje łączną wartość procentowa użyta do obliczenia TDS dla transakcji.</span><span class="sxs-lookup"><span data-stu-id="df242-139">In the **Value** field, the total percentage used to calculate TDS for the transaction is displayed.</span></span>

   <span data-ttu-id="df242-140">Pola na kartach **Przegląd**, **Ogólne** i **Kwota** na stronie Tymczasowe transakcje potrącenia zaliczki na podatek pokazują obliczoną kwotę TDS oraz szczegóły skorygowanej kwoty TDS dla każdego kodu podatku TDS dołączonego do grupy TDS.</span><span class="sxs-lookup"><span data-stu-id="df242-140">The fields on the **Overview**, **General**, and **Amount** tabs in the Withholding tax transactions page display the calculated TDS amount and adjusted TDS amount details for each TDS tax code attached to the TDS group.</span></span>
