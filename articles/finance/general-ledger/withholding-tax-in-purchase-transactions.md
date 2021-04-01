---
title: Zaliczka na podatek w transakcjach zakupu
description: W przypadku dostawców, którzy są objęci potrąconą zaliczką na podatek w płatnościach na rzecz użytkownika, można przypisać **Domyślną grupę potrąconej zaliczki na podatek** na stronie **Wszyscy dostawcy**.
author: roschlom
manager: AnnBe
ms.date: 01/12/2021
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
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: 06c18e6b0779539a6da7ae7afbe000c4cfc78d9e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5256674"
---
# <a name="withholding-tax-in-purchase-transactions"></a><span data-ttu-id="2314f-103">Zaliczka na podatek w transakcjach zakupu</span><span class="sxs-lookup"><span data-stu-id="2314f-103">Withholding tax in purchase transactions</span></span>

<span data-ttu-id="2314f-104">W przypadku dostawców, którzy są objęci potrąconą zaliczką na podatek w płatnościach na rzecz użytkownika, można przypisać **Domyślną grupę potrąconej zaliczki na podatek** na stronie **Wszyscy dostawcy**.</span><span class="sxs-lookup"><span data-stu-id="2314f-104">For vendors who are liable to withholding tax, you can assign the default **Withholding tax group** on the **All vendors** page.</span></span>

1. <span data-ttu-id="2314f-105">Przejdź do **Okienko nawigacij > Moduły > Rozrachunki z dostawcami > Dostawcy > Wszyscy dostawcy**.</span><span class="sxs-lookup"><span data-stu-id="2314f-105">Go to **Navigation pane > Modules > Accounts payable > Vendors > All vendors**.</span></span>

2. <span data-ttu-id="2314f-106">Kliknij odpowiednie konto dostawcy i kliknij przycisk **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="2314f-106">Click the respective Vendor account, click **Edit**.</span></span>

3. <span data-ttu-id="2314f-107">Na karcie **Faktura i dostawa** w polu **Oblicz potrącanie zaliczki na podatek** ustaw wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="2314f-107">In **Invoice and delivery** tab, set the **Calculate withholding tax** field to **Yes**.</span></span>

   > [!NOTE] 
   > <span data-ttu-id="2314f-108">Podatek u źródła nie zostanie obliczony, jeśli **Obliczanie zaliczki na podatek** nie jest włączone dla tego dostawców w danych.</span><span class="sxs-lookup"><span data-stu-id="2314f-108">Withholding tax will not be calculated if **Calculate withholding tax** is not switched on for this vendor in the data.</span></span>

4. <span data-ttu-id="2314f-109">Wybierz grupę Potrącona zaliczka na podatek na liście **Grupa potrąconej zaliczki na podatek**.</span><span class="sxs-lookup"><span data-stu-id="2314f-109">Select a withholding tax group in **Withholding tax group**.</span></span>

5. <span data-ttu-id="2314f-110">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="2314f-110">Click **Save**.</span></span>

<span data-ttu-id="2314f-111">W przypadku towarów / usług, które podlegają potrąceniu u źródła, można przypisać domyślną **Grupę podatku potrącanego u źródła** w obszarze **Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="2314f-111">For items/services which are liable to withholding tax, you can assign the default **Item withholding tax group** in **Released Products**.</span></span>

1. <span data-ttu-id="2314f-112">Otwórz **Okienko nawigacji > Moduły > Informacje o zarządzaniu produktem > Produkty > Wydane produkty**.</span><span class="sxs-lookup"><span data-stu-id="2314f-112">Go to **Navigation pane > Modules > Product information management > Products > Released products**.</span></span>

2. <span data-ttu-id="2314f-113">Kliknij odpowiedni numer pozycji i kliknij przycisk **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="2314f-113">Click the respective Item number, click **Edit**.</span></span>

3. <span data-ttu-id="2314f-114">Na karcie **Zakup** kliknij przycisk **Oblicz potrącenie zaliczki na podatek**.</span><span class="sxs-lookup"><span data-stu-id="2314f-114">In **Purchase** tab, click **Calculate withholding tax**.</span></span>

   > [!NOTE] 
   > <span data-ttu-id="2314f-115">Potrącona zaliczka na podatek nie zostanie obliczona, jeśli ustawienie **Oblicz potrąconej zaliczki na podatek** nie ma wartości **Tak** dla tej pozycji na karcie **Zakup** na stronie **Zwolniony produkt**.</span><span class="sxs-lookup"><span data-stu-id="2314f-115">Withholding tax will not be calculated if **Calculate withholding tax** isn't set to **Yes** for this Item in the **Purchase** tab on the **Released product** page.</span></span>

4. <span data-ttu-id="2314f-116">Wybierz grupę Potrącona zaliczka na podatek od pozycji na liście **Grupa potrąconej zaliczki na podatek od pozycji**.</span><span class="sxs-lookup"><span data-stu-id="2314f-116">Select an item withholding tax group in **Item withholding tax group** list.</span></span>

5. <span data-ttu-id="2314f-117">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="2314f-117">Click **Save**.</span></span>

<span data-ttu-id="2314f-118">Można przypisać grupy potrąconych zaliczek na podatek i grupy potrąconych zaliczek na podatek od pozycji na stronach:</span><span class="sxs-lookup"><span data-stu-id="2314f-118">Withholding tax groups and Item withholding tax groups can be assigned in pages:</span></span> 

- <span data-ttu-id="2314f-119">**Zamówienie zakupu**</span><span class="sxs-lookup"><span data-stu-id="2314f-119">**Purchase order**</span></span>
- <span data-ttu-id="2314f-120">**Faktura dostawcy**</span><span class="sxs-lookup"><span data-stu-id="2314f-120">**Vendor invoice**</span></span>
- <span data-ttu-id="2314f-121">**Arkusz faktur**</span><span class="sxs-lookup"><span data-stu-id="2314f-121">**Invoice journal**</span></span>

<span data-ttu-id="2314f-122">Domyślna grupa potrąconej zaliczki na podatek i grupa potrąconej zaliczki na podatek od pozycji zostaną włączone do wierszy podczas tworzenia **Zamówień zakupu** i/lub **Faktur oczekujących dostawców**.</span><span class="sxs-lookup"><span data-stu-id="2314f-122">The default Withholding tax group and Item withholding tax group will be carried into the lines when creating **Purchase orders** and/or **Pending Vendor invoices**.</span></span> <span data-ttu-id="2314f-123">Dla **Arkusz faktur od dostawców** można włączyć **Oblicz potrącenie zaliczki na podatek** i wybrać **Grupa potrąconej zaliczki na podatek od pozycji** na karcie **Ogólne** w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="2314f-123">For **Vendor invoice journal**, you can switch on **Calculate withholding tax** and select **Item withholding tax group** in the **General** tab in the journal.</span></span>

<span data-ttu-id="2314f-124">Tymczasowa kwota potrąconej zaliczki na podatek jest dostępna w polu **Skorygowana potrącona zaliczka na podatek** na karcie **Sumy** na stronie **Zamówienie zakupu**.</span><span class="sxs-lookup"><span data-stu-id="2314f-124">The temporary amount of withholding tax is available in the field **Adjusted withholding tax** of the **Totals** tab on the **Purchase order** page.</span></span>

![Potrącona zaliczka na podatek jest uwzględniona w zamówieniu zakupu](media/withholding-tax-adjusted.png)

<span data-ttu-id="2314f-126">Potrącona zaliczka na podatek jest obliczana na podstawie **Arkusz płatności dostawców**.</span><span class="sxs-lookup"><span data-stu-id="2314f-126">Withholding tax is calculated on **Vendor payment journal**.</span></span> <span data-ttu-id="2314f-127">Można ręcznie skorygować stosowane kody potrąconej zaliczki na podatek oraz rzeczywistą kwoty potrąconej zaliczki na podatek na karcie **Potrącona zaliczka na podatek** na stronie **Rozlicz transakcje**.</span><span class="sxs-lookup"><span data-stu-id="2314f-127">You can manually adjust the applicable withholding tax codes as well as the actual withholding tax amounts in the **Withholding tax** tab on the **Settle transactions** page.</span></span>

![Potrącenie można ręcznie skorygować na stronie Rozlicz transakcje](media/withholding-tax-vendor-payment-tab.png)

<span data-ttu-id="2314f-129">Uzyskana kwota podatku potrąconego u źródła zostanie odjęta od płatności dostawcy i zaksięgowana na koncie **Potrąconej zaliczki na podatek** w powiązanym załączniku.</span><span class="sxs-lookup"><span data-stu-id="2314f-129">The derived withholding tax amount will be deducted from the vendor payment and posted to the **Withholding tax account** in a related voucher.</span></span>

![Konto potrąconej zaliczki na podatek pokazujące powiązany załącznik](media/withholding-tax-adjusted.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]