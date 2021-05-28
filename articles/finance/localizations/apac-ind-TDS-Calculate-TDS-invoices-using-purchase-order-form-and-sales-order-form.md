---
title: Obliczanie faktur TDS przy użyciu formularza zamówienia zakupu i formularza zamówienia sprzedaży
description: W tym temacie wymieniono kroki obliczania podatku potrąconego w źródle (TDS) dla różnych typów faktur.
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
ms.openlocfilehash: e7925206f3c060c6332de9d4972c8a7fb0066be2
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023498"
---
# <a name="calculate-tds-invoices-using-purchase-order-form-and-sales-order-form"></a><span data-ttu-id="fa709-103">Obliczanie faktur TDS przy użyciu formularza zamówienia zakupu i formularza zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="fa709-103">Calculate TDS invoices using purchase order form and sales order form</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fa709-104">W tym temacie wymieniono kroki obliczania podatku potrąconego w źródle (TDS) na różnych typach faktur przy użyciu stron **Zamówienie zakupu**, **Arkusz zakupów**, **Zamówienie zbiorcze** i **Zamówienie sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="fa709-104">This topic lists the steps for calculating Tax Deducted at Source (TDS) on various types of invoices using the **Purchase order**, **Purchase journal**, **Blanket order**, and **Sales order** pages.</span></span>

1. <span data-ttu-id="fa709-105">Strona ta umożliwia tworzenie zamówienia zakupu, arkusza zakupu, zbiorczego zamówienia zakupu lub zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="fa709-105">Create a purchase order, purchase journal, purchase blanket order, or a sales order using the page listed.</span></span> <span data-ttu-id="fa709-106">Wprowadź wymagane informacje.</span><span class="sxs-lookup"><span data-stu-id="fa709-106">Enter the required details.</span></span>

2. <span data-ttu-id="fa709-107">Wybierz **kartę Ustawienia**, aby wyświetlić charakter oceny dostawcy lub odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="fa709-107">Select the **Setup** tab to view the nature of the assessee of the vendor or customer.</span></span> <span data-ttu-id="fa709-108">Te informacje są wymienione w polu **Charakter oceny** w grupie pól **Grupa potrąconej zaliczki na podatek**.</span><span class="sxs-lookup"><span data-stu-id="fa709-108">This information is listed in the **Nature of assessee** field, under the **Withholding tax group** field group.</span></span>

3. <span data-ttu-id="fa709-109">W polu **Grupa TDS** wyświetl lub zmodyfikuj domyślną grupę TDS zdefiniowaną dla dostawcy lub odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="fa709-109">In the **TDS group** field, view or modify the default TDS group defined for the vendor or customer.</span></span>

   > [!NOTE]
   > <span data-ttu-id="fa709-110">Pole **grupa TCS** nie jest dostępne po wybraniu grupy TDS w polu **grupa TCS**.</span><span class="sxs-lookup"><span data-stu-id="fa709-110">The **TCS group** field isn't available when you select a TDS group in the **TDS group** field.</span></span> <span data-ttu-id="fa709-111">TDS jest obliczany tylko wtedy, gdy pole wyboru **Oblicz zaliczkę na podatek** jest zaznaczone dla dostawcy lub odbiorcy na stronie **Wszyscy dostawcy** lub **Wszyscy odbiorcy**.</span><span class="sxs-lookup"><span data-stu-id="fa709-111">TDS is calculated only if the **Calculate withholding tax** check box is selected for the vendor or customer on the **All vendors** or **All customers** page.</span></span>  

4. <span data-ttu-id="fa709-112">Na karcie **Wiersze faktury** utwórz pozycje pozycji w dniu i wprowadź wymagane szczegóły.</span><span class="sxs-lookup"><span data-stu-id="fa709-112">Create item lines on the **Lines** tab and enter the required details.</span></span>

5. <span data-ttu-id="fa709-113">Wybierz **kartę Ustawienia** (poziom wiersza), aby wyświetlić lub zmienić grupę TDS zdefiniowaną na poziomie nagłówka.</span><span class="sxs-lookup"><span data-stu-id="fa709-113">Select the **Setup** tab (line-level) to view or change the TDS group defined at the header-level.</span></span> <span data-ttu-id="fa709-114">Grupa TDS jest wyświetlana w polu **Grupa TDS**, które znajduje się w grupie pól **Grupa potrąconej zaliczki na podatek**.</span><span class="sxs-lookup"><span data-stu-id="fa709-114">The TDS group is displayed in the **TDS group** field, which is under the **Withholding tax group** field group.</span></span>

6. <span data-ttu-id="fa709-115">Wybierz kartę **Informacje podatkowe** i wybierz adresy alternatywne ustawione dla nazwy firmy wyświetlanej w tym polu.</span><span class="sxs-lookup"><span data-stu-id="fa709-115">Select the **Tax information** tab and select alternate addresses that are set up for the company name that's displayed in this field.</span></span> <span data-ttu-id="fa709-116">Nazwa firmy jest wyświetlana w polu **Nazwa**, które znajduje się w grupie **pól Informacje o firmie**.</span><span class="sxs-lookup"><span data-stu-id="fa709-116">The company name is displayed in the **Name** field, which is under the **Company information** field group.</span></span> 

   <span data-ttu-id="fa709-117">Numer IDENTYFIKACYJNY wybranej nazwy firmy jest wyświetlany w polu **Numer konta podatkowego (**TAN**)** w grupie pól **Potrącona zaliczka na podatek**.</span><span class="sxs-lookup"><span data-stu-id="fa709-117">The TAN of the selected company name is displayed in the **Tax Account Number** (**TAN**) field, under the **Withholding tax** field group.</span></span> 

7. <span data-ttu-id="fa709-118">Wybierz przycisk **Potrącona zaliczka na podatek**, aby otworzyć stronę **Tymczasowe transakcje potrącenia zaliczki na podatek**.</span><span class="sxs-lookup"><span data-stu-id="fa709-118">Select **Withholding tax** to open the **Temporary withholding tax transactions** page.</span></span> <span data-ttu-id="fa709-119">Wyświetl następujące pola w górnym okienku strony **Tymczasowe transakcje potrącenia zaliczki na podatek**.</span><span class="sxs-lookup"><span data-stu-id="fa709-119">View the following fields on the upper pane of the **Temporary withholding tax transactions** page.</span></span>

   - <span data-ttu-id="fa709-120">**Łączna** **kwota** **potrąconej** **zaliczki** **na podatek** — łączna kwota TDS obliczona dla transakcji dla grupy TDS.</span><span class="sxs-lookup"><span data-stu-id="fa709-120">**Withholding** **tax** **amount** **in** **total** - The total TDS calculated for the transaction for the TDS group.</span></span>

   - <span data-ttu-id="fa709-121">**Wartość** - łączna wartość procentowa użyta do obliczenia TDS dla transakcji.</span><span class="sxs-lookup"><span data-stu-id="fa709-121">**Value** - The total percentage used to calculate TDS for the transaction.</span></span> <span data-ttu-id="fa709-122">Łączny procent jest oparty na formule zdefiniowanej dla kodów podatków TDS i dołączonej do grupy TDS.</span><span class="sxs-lookup"><span data-stu-id="fa709-122">The total percentage is based on the formula that is defined for TDS tax codes attached to the TDS group.</span></span>

   - <span data-ttu-id="fa709-123">**Skorygowana łączna kwota potrąconej zaliczki na podatek** - łączna skorygowana kwota TDS dla wszystkich kodów podatków w grupie TDS.</span><span class="sxs-lookup"><span data-stu-id="fa709-123">**Adjusted withholding tax amount in total** - The total adjusted TDS amount for all tax codes in the TDS group.</span></span>

   - <span data-ttu-id="fa709-124">**TDS** — jeśli ta opcja jest zaznaczona, do transakcji jest dołączona grupa TDS.</span><span class="sxs-lookup"><span data-stu-id="fa709-124">**TDS** - If selected, a TDS group is attached to the transaction.</span></span>

<span data-ttu-id="fa709-125">Pola na kartach **Przegląd**, **Ogólne** i **Korekta** na stronie **Tymczasowe transakcje potrącenia zaliczki na podatek** pokazują obliczoną kwotę TDS oraz szczegóły skorygowanej kwoty TDS dla każdego kodu podatku TDS dołączonego do grupy TDS.</span><span class="sxs-lookup"><span data-stu-id="fa709-125">The fields on the **Overview**, **General**, and **Adjustment** tabs on the **Temporary withholding tax transactions** page display the calculated TDS amount and adjusted TDS amount details for each TDS tax code attached to the TDS group.</span></span>

8. <span data-ttu-id="fa709-126">Wybierz **pozycję Próg**, aby otworzyć stronę **Próg**.</span><span class="sxs-lookup"><span data-stu-id="fa709-126">Select **Threshold** to open the **Threshold** page.</span></span> <span data-ttu-id="fa709-127">Umożliwia wyświetlenie na tej stronie limitu progowego zdefiniowanego dla składnika podatku TDS dołączonego do określonego kodu podatku TDS.</span><span class="sxs-lookup"><span data-stu-id="fa709-127">View the threshold limit defined for the TDS tax component attached to a specific TDS tax code on this page.</span></span>

9. <span data-ttu-id="fa709-128">Wybierz opcję **Projektant formuł**, aby otworzyć stronę **Projektant formuł**.</span><span class="sxs-lookup"><span data-stu-id="fa709-128">Select **Formula designer** to open the **Formula designer** page.</span></span> <span data-ttu-id="fa709-129">Na tej stronie można wyświetlić formułę zdefiniowaną dla określonego kodu podatku TDS.</span><span class="sxs-lookup"><span data-stu-id="fa709-129">View the formula that is defined for a specific TDS tax code on this page.</span></span> 

10. <span data-ttu-id="fa709-130">Zaksięguj fakturę.</span><span class="sxs-lookup"><span data-stu-id="fa709-130">Post the invoice.</span></span> <span data-ttu-id="fa709-131">Kwota TDS obliczona na fakturach zakupu jest księgowana na koncie zobowiązań, a kwota TDS obliczona na fakturach sprzedaży jest księgowana na koncie należności określonym dla każdego kodu podatku TDS w grupie TDS.</span><span class="sxs-lookup"><span data-stu-id="fa709-131">The TDS amount calculated on purchase invoices is posted to the payable account and the TDS amount calculated on sales invoices is posted to the receivable account that is defined for each TDS tax code in the TDS group.</span></span> <span data-ttu-id="fa709-132">Konta rozrachunków lub należności dla kodów podatku TDS są definiowane na stronie **Kody potrąconych zaliczek na podatek**.</span><span class="sxs-lookup"><span data-stu-id="fa709-132">The payable accounts or receivable accounts for TDS tax codes are defined on the **Withholding tax codes** page.</span></span>

11. <span data-ttu-id="fa709-133">Wybierz przycisk **Zapytanie** **> Faktura > Zaksięgowana potrącona zaliczka na podatek**, aby otworzyć stronę **Transakcje potrącenia zaliczki**.</span><span class="sxs-lookup"><span data-stu-id="fa709-133">Select **Inquiry** button **> Invoice > Posted withholding tax** button to open the **Withholding tax transactions** page.</span></span> <span data-ttu-id="fa709-134">Pole **Wartość** pokazuje łączną wartość procentowa użyta do obliczenia TDS dla transakcji.</span><span class="sxs-lookup"><span data-stu-id="fa709-134">You can view the total percentage used to calculate TDS for the transaction in the **Value** field.</span></span>

<span data-ttu-id="fa709-135">W polach na kartach **Przegląd**, **Ogólne** i **Kwota** na stronie **Transakcje potrącenia zaliczki na podatek** są wyświetlane informacje o identyfikatorze TDS obliczonym dla transakcji.</span><span class="sxs-lookup"><span data-stu-id="fa709-135">The fields on the **Overview**, **General**, and **Amount** tabs on the **Withholding tax transactions** page display the information of TDS calculated for the transaction.</span></span> <span data-ttu-id="fa709-136">Zobacz informacje o obliczaniu TDS dla każdego kodu podatku TDS dołączonego do grupy TDS.</span><span class="sxs-lookup"><span data-stu-id="fa709-136">View the TDS calculation information for each TDS tax code attached to the TDS group.</span></span>
