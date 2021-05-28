---
title: Obliczanie TDS na fakturach ze strony Faktura niezależna
description: W tym temacie wyjaśniono, jak obliczyć podatek odliczany u źródła (TDS) na fakturach przy użyciu strony Faktura niezależna.
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
ms.openlocfilehash: 7d551a8ba6ba9ca282fd9de3fa7d7c7303e394ed
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023514"
---
# <a name="tds-calculation-on-invoices-from-the-free-text-invoice-page"></a><span data-ttu-id="92c40-103">Obliczanie TDS na fakturach ze strony Faktura niezależna</span><span class="sxs-lookup"><span data-stu-id="92c40-103">TDS calculation on invoices from the Free text invoice page</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="92c40-104">W tym temacie wyjaśniono, jak obliczyć podatek odliczany u źródła (TDS) na fakturach przy użyciu strony **Faktura niezależna**.</span><span class="sxs-lookup"><span data-stu-id="92c40-104">This topic explains how to calculate Tax Deducted at Source (TDS) on invoices by using the **Free text invoice** page.</span></span>

1. <span data-ttu-id="92c40-105">Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Faktury \> Wszystkie faktury niezależne**.</span><span class="sxs-lookup"><span data-stu-id="92c40-105">Go to **Accounts receivable \> Invoices \> All free text invoices**.</span></span>

    <span data-ttu-id="92c40-106">[![Strona faktury niezależnej](./media/apac-ind-TDS-57-1.png)](./media/apac-ind-TDS-57-1.png)</span><span class="sxs-lookup"><span data-stu-id="92c40-106">[![Free text invoice page](./media/apac-ind-TDS-57-1.png)](./media/apac-ind-TDS-57-1.png)</span></span>

2. <span data-ttu-id="92c40-107">Wybierz **Nowy**, aby utworzyć fakturę niezależną i wprowadź wymagane szczegóły.</span><span class="sxs-lookup"><span data-stu-id="92c40-107">Select **New** to create a free text invoice, and enter the required details.</span></span>
3. <span data-ttu-id="92c40-108">Na karcie **Faktura** w sekcji **Grupa potrąconej zaliczki na podatek** pole **Charakter grupy oszacowań** pokazuje charakter kategorii produktów ocenianych dostawcy lub odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="92c40-108">Select the **Invoice** tab. In the **Withholding tax group** section, the **Nature of assessee** field shows the nature of assessee category of the customer.</span></span>
4. <span data-ttu-id="92c40-109">W polu **Grupa TDS** przejrzyj lub zmień domyślną grupę TDS zdefiniowaną dla odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="92c40-109">In the **TDS group** field, review or change the default TDS group that is defined for the customer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="92c40-110">Po wybraniu wartości w polu **grupy TDS** pole **grupy TCS** staje się niedostępne.</span><span class="sxs-lookup"><span data-stu-id="92c40-110">When you select a value in the **TDS group** field, the **TCS group** field becomes unavailable.</span></span> <span data-ttu-id="92c40-111">Identyfikator TDS jest obliczany tylko wtedy, gdy opcja **Oblicz potrącanie zaliczki** na podatek ma wartość **Tak** dla odbiorcy na stronie **Wszyscy odbiorcy**.</span><span class="sxs-lookup"><span data-stu-id="92c40-111">TDS is calculated only if the **Calculate withholding tax** option is set to **Yes** for the customer on the **All customers** page.</span></span>

5. <span data-ttu-id="92c40-112">Na karcie **Informacje podatkowe**, w sekcji **Informacje o firmie**, w polu **Nazwa** wybierz nazwę firmy dla alternatywnego adresu, który został skonfigurowany dla firmy.</span><span class="sxs-lookup"><span data-stu-id="92c40-112">On the **Tax information** tab, in the **Company information** section, in the **Name** field, select the company name for an alternate address that has been set up for the company.</span></span>

    <span data-ttu-id="92c40-113">W sekcji **Potrącona zaliczka na podatek** w polu **Numer konta podatkowego (TAN)** jest uwzględniany numer konta podatkowego (TAN) wybranej firmy.</span><span class="sxs-lookup"><span data-stu-id="92c40-113">In the **Withholding tax** section, the **Tax Account Number (TAN)** field shows the tax account number (TAN) for the selected company.</span></span>

6. <span data-ttu-id="92c40-114">Na karcie **Wiersze faktury** utwórz wiersze faktury i wprowadź wymagane szczegóły.</span><span class="sxs-lookup"><span data-stu-id="92c40-114">On the **Invoice lines** tab, create invoice lines, and enter the required details.</span></span>

    <span data-ttu-id="92c40-115">W sekcji **Grupa potrąconej zaliczki** na podatek pole  **Numer konta podatkowego (TAN)** zawiera kod TAN, a pole **Grupa TDS** zawiera grupę TDS.</span><span class="sxs-lookup"><span data-stu-id="92c40-115">In the **Withholding tax group** section, the **Tax Account Number (TAN)** field shows the TAN, and the **TDS group** field shows the TDS group.</span></span>

7. <span data-ttu-id="92c40-116">Wybierz przycisk **Potrącona zaliczka na podatek**, aby otworzyć stronę **Tymczasowe transakcje potrącenia zaliczki na podatek**.</span><span class="sxs-lookup"><span data-stu-id="92c40-116">Select **Withholding tax** to open the **Temporary withholding tax transactions** page.</span></span> <span data-ttu-id="92c40-117">W górnej części tej strony są następujące pola:</span><span class="sxs-lookup"><span data-stu-id="92c40-117">The upper part of this page has the following fields:</span></span>

    - <span data-ttu-id="92c40-118">**Łączna kwota potrąconej zaliczki na podatek** — łączna kwota TDS obliczona dla transakcji dla grupy TDS.</span><span class="sxs-lookup"><span data-stu-id="92c40-118">**Withholding tax amount in total** – The total TDS that was calculated for the transaction for the TDS group.</span></span>
    - <span data-ttu-id="92c40-119">**Wartość** — łączna wartość procentowa użyta do obliczenia TDS dla transakcji.</span><span class="sxs-lookup"><span data-stu-id="92c40-119">**Value** – The total percentage that was used to calculate TDS for the transaction.</span></span> <span data-ttu-id="92c40-120">Łączny procent jest oparty na formule zdefiniowanej dla kodów podatków TDS i dołączonej do grupy TDS.</span><span class="sxs-lookup"><span data-stu-id="92c40-120">The total percentage is based on the formula that is defined for the TDS tax codes and attached to the TDS group.</span></span>
    - <span data-ttu-id="92c40-121">**Skorygowana łączna kwota potrąconej zaliczki na podatek** — łączna skorygowana kwota TDS dla wszystkich kodów podatków w grupie TDS.</span><span class="sxs-lookup"><span data-stu-id="92c40-121">**Adjusted withholding tax amount in total** – The total adjusted TDS amount for all tax codes in the TDS group.</span></span>
    - <span data-ttu-id="92c40-122">**TDS** — zaznaczone pole wyboru wskazuje, że grupa TDS jest dołączona do transakcji.</span><span class="sxs-lookup"><span data-stu-id="92c40-122">**TDS** – A selected checkbox indicates that a TDS group is attached to the transaction.</span></span>

    <span data-ttu-id="92c40-123">Pola na kartach **Przegląd**, **Ogólne** i **Korekta** pokazują obliczoną kwotę TDS oraz szczegóły skorygowanej kwoty TDS dla każdego kodu podatku TDS dołączonego do grupy TDS.</span><span class="sxs-lookup"><span data-stu-id="92c40-123">The fields on the **Overview**, **General**, and **Adjustment** tabs show the calculated TDS amount and details of the adjusted TDS amount for each TDS tax code that is attached to the TDS group.</span></span>

8. <span data-ttu-id="92c40-124">Wybierz opcję **Próg**, aby otworzyć stronę **Progu**, na której możesz przejrzeć limit progowy zdefiniowany dla składnika podatku TDS dołączonego do określonego kodu podatku TDS.</span><span class="sxs-lookup"><span data-stu-id="92c40-124">Select **Threshold** to open the **Threshold** page, where you can review the threshold limit that is defined for the TDS tax component that is attached to a specific TDS tax code.</span></span>
9. <span data-ttu-id="92c40-125">Po wybraniu opcji **Projektant formuł** zostanie otwarta strona **Projektant formuł**, na której można przejrzeć formułę zdefiniowaną dla określonego kodu podatku TDS.</span><span class="sxs-lookup"><span data-stu-id="92c40-125">Select **Formula designer** to open the **Formula designer** page, where you can review the formula that is defined for a specific TDS tax code.</span></span>
10. <span data-ttu-id="92c40-126">Księguj fakturę niezależną.</span><span class="sxs-lookup"><span data-stu-id="92c40-126">Post the free text invoice.</span></span> <span data-ttu-id="92c40-127">Kwota TDS obliczona dla faktury niezależnej jest księgowana na koncie należności zdefiniowanym dla każdego kodu podatku potrącanego u źródła w grupie TDS.</span><span class="sxs-lookup"><span data-stu-id="92c40-127">The TDS amount that is calculated for the free text invoice is posted to the receivable account that is defined for each TDS tax code in the TDS group.</span></span> <span data-ttu-id="92c40-128">Konta należności dla kodów podatku TDS są definiowane na stronie **Kody potrąconych zaliczek na podatek**.</span><span class="sxs-lookup"><span data-stu-id="92c40-128">The receivable accounts for TDS tax codes are defined on the **Withholding tax codes** page.</span></span>
11. <span data-ttu-id="92c40-129">Wybierz przycisk **Zaksięgowana potrącona zaliczka na podatek**, aby otworzyć stronę **transakcje potrącenia zaliczki**.</span><span class="sxs-lookup"><span data-stu-id="92c40-129">Select **Posted withholding tax** to open the **Withholding tax transactions** page.</span></span> <span data-ttu-id="92c40-130">**Wartość** pokazuje łączną wartość procentowa użyta do obliczenia TDS dla transakcji.</span><span class="sxs-lookup"><span data-stu-id="92c40-130">The **Value** field shows the total percentage that was used to calculate TDS for the transaction.</span></span>

    <span data-ttu-id="92c40-131">W polach na kartach **Przegląd**, **Ogólne** i **Kwota** są wyświetlane kwoty TDS, które zostały obliczone w wierszach faktury.</span><span class="sxs-lookup"><span data-stu-id="92c40-131">The fields on the **Overview**, **General**, and **Amount** tabs show the TDS amounts that were calculated on the invoice lines.</span></span>

12. <span data-ttu-id="92c40-132">Przejrzyj informacje o obliczaniu TDS dla każdego kodu podatku TDS dołączonego do grupy TDS.</span><span class="sxs-lookup"><span data-stu-id="92c40-132">Review the TDS calculation information for each TDS tax code that is attached to the TDS group.</span></span>
