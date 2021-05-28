---
title: Zapisz możliwe do odzyskania numery certyfikatów TDS
description: W tym temacie wyjaśniono, jak używać strony Certyfikaty podlegające zwrotowi do rejestracji numerów certyfikatów i dat dla certyfikatów potrącanych z podatku w źródle (TDS), które są odbierane dla określonego dostawcy, odbiorcy lub księgi.
author: kailiang
mms.date: 02/12/2021
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
ms.openlocfilehash: b501c331cccc6d030f36d0a13ba0a6a13c08c733
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023494"
---
# <a name="record-tds-recoverable-certificate-numbers"></a><span data-ttu-id="c4b96-103">Zapisz możliwe do odzyskania numery certyfikatów TDS</span><span class="sxs-lookup"><span data-stu-id="c4b96-103">Record TDS recoverable certificate numbers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c4b96-104">W tym temacie wyjaśniono, jak używać strony **Certyfikaty podlegające zwrotowi** do rejestracji numerów certyfikatów i dat dla certyfikatów potrącanych z podatku w źródle (TDS), które są odbierane dla określonego dostawcy, odbiorcy lub księgi.</span><span class="sxs-lookup"><span data-stu-id="c4b96-104">This topic explains how to use the **Recoverable certificates** page to record the certificate numbers and dates for Tax Deducted at Source (TDS) certificates that are received for a specific vendor, customer, or ledger.</span></span> <span data-ttu-id="c4b96-105">Aby zaktualizować numery i daty certyfikatów TDS zarejestrowane dla transakcji TDS na tej stronie, użyj strony **Aktualizuj certyfikat** (**Księga główna \> Okres \> Potrącona zaliczka na podatek \> Aktualizuj certyfikaty**).</span><span class="sxs-lookup"><span data-stu-id="c4b96-105">To update the TDS certificate numbers and dates that are recorded for TDS transactions on this page, use the **Update certificate** page (**General ledger \> Periodic \> Withholding tax \> Update certificate**).</span></span> <span data-ttu-id="c4b96-106">Po zakończeniu aktualizowania numerów certyfikatów TDS należy je zamknąć.</span><span class="sxs-lookup"><span data-stu-id="c4b96-106">After you've finished updating TDS certificate numbers, close them.</span></span>

<span data-ttu-id="c4b96-107">Aby zarejestrować numery i daty certyfikatów TDS, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="c4b96-107">Follow these steps to record the TDS certificate numbers and dates.</span></span>

1. <span data-ttu-id="c4b96-108">Wybierz kolejno opcje **Podatek \> Podatki pośrednie \> Potrącona zaliczka na podatek \> Certyfikaty podlegające zwrotowi**.</span><span class="sxs-lookup"><span data-stu-id="c4b96-108">Go to **Tax \> Indirect tax \> Withholding tax \> Recoverable certificates**.</span></span>

    <span data-ttu-id="c4b96-109">[![Strona certyfikatów zwrotnych](./media/apac-ind-TDS-49.png)](./media/apac-ind-TDS-49.png)</span><span class="sxs-lookup"><span data-stu-id="c4b96-109">[![Recoverable certificates page](./media/apac-ind-TDS-49.png)](./media/apac-ind-TDS-49.png)</span></span> 

2. <span data-ttu-id="c4b96-110">Na stronie **Certyfikaty objętych zwrotem** w polu **Typ podatku** wybierz pozycję **TDS**.</span><span class="sxs-lookup"><span data-stu-id="c4b96-110">On the **Recoverable certificates** page, in the **Tax type** field, select **TDS**.</span></span>
3. <span data-ttu-id="c4b96-111">Wybierz **Nowy**, aby utworzyć rekord.</span><span class="sxs-lookup"><span data-stu-id="c4b96-111">Select **New** to create a record.</span></span>
4. <span data-ttu-id="c4b96-112">W polu **Numer certyfikacji** wprowadź numer certyfikatu koncesji TDS.</span><span class="sxs-lookup"><span data-stu-id="c4b96-112">In the **Certificate number** field, enter the TDS certificate number.</span></span>
5. <span data-ttu-id="c4b96-113">W polu **Typ konta** wybierz typ konta, dla których otrzymano certyfikat TDS: **Dostawca**, **Odbiorca** lub **Księga**.</span><span class="sxs-lookup"><span data-stu-id="c4b96-113">In the **Account type** field, select the type of account that the TDS certificate is received for: **Vendor**, **Customer**, or **Ledger**.</span></span>
6. <span data-ttu-id="c4b96-114">W polu **Konto** wybierz dostawcę, konto odbiorcy lub numer konta księgowego, w zależności od wybranego typu konta.</span><span class="sxs-lookup"><span data-stu-id="c4b96-114">In the **Account** field, select the vendor, customer, or ledger account number, depending on the account type that you selected.</span></span> <span data-ttu-id="c4b96-115">Pole **Nazwa** zawiera nazwę dostawcy, odbiorcy lub konta księgowego.</span><span class="sxs-lookup"><span data-stu-id="c4b96-115">The **Name** field shows the name of the vendor, customer, or ledger account.</span></span>
7. <span data-ttu-id="c4b96-116">W polu **Kwota certyfikacji** wprowadź kwotę certyfikatu TDS.</span><span class="sxs-lookup"><span data-stu-id="c4b96-116">In the **Certificate amount** field, enter the amount of the TDS certificate.</span></span>
8. <span data-ttu-id="c4b96-117">W polu **Data** wprowadź datę dla numeru certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="c4b96-117">In the **Date** field, enter the certificate date for the certificate number.</span></span>
9. <span data-ttu-id="c4b96-118">Wybierz opcję **Informacje**, aby otworzyć stronę **Transakcje certyfikatu**, na której możesz przejrzeć transakcje TDS, dla których zaktualizowano numer i datę certyfikatu TDS.</span><span class="sxs-lookup"><span data-stu-id="c4b96-118">Select **Inquiries** to open the **Certificate transactions** page, where you can view the TDS transactions that the TDS certificate number and date are updated for.</span></span> <span data-ttu-id="c4b96-119">Te informacje można zaktualizować na stronie **Aktualizuj certyfikat** (**Podatek \> Deklaracje \> Potrącona zaliczka na podatek \> Aktualizuj certyfikaty**).</span><span class="sxs-lookup"><span data-stu-id="c4b96-119">This information can be updated on the **Update certificate** page (**Tax \> Declarations \> Withholding tax \> Update certificate**).</span></span>

    <span data-ttu-id="c4b96-120">Na stronie **Aktualizuj certyfikaty** są podane następujące informacje dotyczące każdej otwartej transakcji TDS:</span><span class="sxs-lookup"><span data-stu-id="c4b96-120">The **Update certificate** page shows the following information for each TDS transaction:</span></span>

    - <span data-ttu-id="c4b96-121">**Data** – Data księgowania transakcji TDS.</span><span class="sxs-lookup"><span data-stu-id="c4b96-121">**Date** – The posting date of the TDS transaction.</span></span>
    - <span data-ttu-id="c4b96-122">**Załącznik** – Umożliwia wyświetlenie numeru załącznika TDS.</span><span class="sxs-lookup"><span data-stu-id="c4b96-122">**Voucher** – The voucher number of the TDS transaction.</span></span>
    - <span data-ttu-id="c4b96-123">**Źródło** — moduł, w których jest utworzona transakcja TDS.</span><span class="sxs-lookup"><span data-stu-id="c4b96-123">**Source** – The module that the TDS transaction was created in.</span></span>
    - <span data-ttu-id="c4b96-124">**Konto** — numer dostawcy, odbiorcy lub konta księgowego, dla których została utworzona transakcja TDS.</span><span class="sxs-lookup"><span data-stu-id="c4b96-124">**Account** – The vendor, customer, or ledger account number that the TDS transaction was created for.</span></span>
    - <span data-ttu-id="c4b96-125">**Nazwa** — Nazwa dostawcy, odbiorcy lub konta księgowego, dla którego utworzono transakcję TDS.</span><span class="sxs-lookup"><span data-stu-id="c4b96-125">**Name** – The name of the vendor, customer, or ledger account that the TDS transaction was created for.</span></span>
    - <span data-ttu-id="c4b96-126">**Kwota** – Kwota faktury, na podstawie której obliczono TDS.</span><span class="sxs-lookup"><span data-stu-id="c4b96-126">**Amount** – The invoice amount that the TDS was calculated on.</span></span>
    - <span data-ttu-id="c4b96-127">**Kwota podatku** — kwota podatku TDS obliczona dla transakcji.</span><span class="sxs-lookup"><span data-stu-id="c4b96-127">**Tax amount** – The TDS tax amount that was calculated for the transaction.</span></span>
    - <span data-ttu-id="c4b96-128">**Data certyfikatu** — data certyfikatu TDS zaktualizowana dla transakcji TDS.</span><span class="sxs-lookup"><span data-stu-id="c4b96-128">**Certificate date** – The TDS certificate date that was updated for the TDS transaction.</span></span>
    - <span data-ttu-id="c4b96-129">**Numer certyfikatu** — numer certyfikatu TDS zaktualizowana dla transakcji TDS.</span><span class="sxs-lookup"><span data-stu-id="c4b96-129">**Certificate number** – TDS certificate number that was updated for the TDS transaction.</span></span>

10. <span data-ttu-id="c4b96-130">Na stronie **Certyfikaty możliwe do zwrotu** zaznacz pole wyboru **Zamknięte**, aby zamknąć numer certyfikatu TDS po zakończeniu aktualizowania go dla transakcji TDS na stronie **Aktualizacja certyfikatu**.</span><span class="sxs-lookup"><span data-stu-id="c4b96-130">On the **Recoverable certificates** page, select the **Closed** check box to close the TDS certificate number after you've finished updating it for TDS transactions on the **Update certificate** page.</span></span>

    <span data-ttu-id="c4b96-131">Aby zaznaczyć pole wyboru **Zamknięte** dla wszystkich rekordów na stronie, zaznacz opcję **Zaznacz wszystko**.</span><span class="sxs-lookup"><span data-stu-id="c4b96-131">To select the **Closed** check box for all records on the page, select **Mark all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c4b96-132">Numery certyfikatów TDS, dla których zaznaczono pole wyboru **Zamknięte**, nie są dostępne na stronie **Aktualizacja certyfikatu**.</span><span class="sxs-lookup"><span data-stu-id="c4b96-132">TDS certificate numbers that the **Closed** check box is selected for aren't available on the **Update certificate** page.</span></span>
