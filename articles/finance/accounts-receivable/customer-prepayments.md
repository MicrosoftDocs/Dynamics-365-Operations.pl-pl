---
title: Przedpłaty klienta
description: W tym temacie wyjaśniono, jak tworzyć i przetwarzać przedpłaty odbiorcy (zwane także wpłatami klientów).
author: roschlom
ms.date: 04/30/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, LedgerJournalTransCustPaym, CustParameters
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: ''
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c3314803b994aed40e5b04d8546a45bd305d48b6
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019427"
---
# <a name="customer-prepayments"></a><span data-ttu-id="83a4d-103">Przedpłaty klienta</span><span class="sxs-lookup"><span data-stu-id="83a4d-103">Customer prepayments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="83a4d-104">Przedpłaty odbiorcy są używane, gdy użytkownik otrzymuje płatność od odbiorcy, ale nie ma faktury, z która można rozliczyć płatność.</span><span class="sxs-lookup"><span data-stu-id="83a4d-104">Customer prepayments are used when you receive a payment from a customer, but there is no invoice that the payment can be settled against.</span></span> <span data-ttu-id="83a4d-105">Te typy płatności są nazywane również wpłatami klientów.</span><span class="sxs-lookup"><span data-stu-id="83a4d-105">These types of payments are also referred to as customer deposits.</span></span>

<span data-ttu-id="83a4d-106">Proces konfigurowania przedpłat odbiorcy i pracy z nim składa się z następujących podstawowych kroków.</span><span class="sxs-lookup"><span data-stu-id="83a4d-106">The process of setting up and working with customer prepayments consists of the following basic steps.</span></span>

1. <span data-ttu-id="83a4d-107">Tworzenie profilu księgowania odbiorcy dla przedpłat.</span><span class="sxs-lookup"><span data-stu-id="83a4d-107">Create a customer posting profile for prepayments.</span></span>
2. <span data-ttu-id="83a4d-108">Ustaw parametr **Profil księgowania z użyciem załącznika arkusza zaliczki**.</span><span class="sxs-lookup"><span data-stu-id="83a4d-108">Set the **Posting profile with prepayment journal voucher** parameter.</span></span>
3. <span data-ttu-id="83a4d-109">Utwórz arkusz płatności odbiorcy i zaznacz pole wyboru **Załącznik arkusza przedpłat** w każdym wierszu.</span><span class="sxs-lookup"><span data-stu-id="83a4d-109">Create a customer payment journal, and select the **Prepayment journal voucher** check box on each line.</span></span>
4. <span data-ttu-id="83a4d-110">Księgowanie arkusza płatności odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="83a4d-110">Post the customer payment journal.</span></span>
5. <span data-ttu-id="83a4d-111">Po wygenerowaniu faktury rozlicz przedpłatę przy użyciu strony **Rozlicz otwarte transakcje**.</span><span class="sxs-lookup"><span data-stu-id="83a4d-111">After an invoice is generated, settle the prepayment with it by using the **Settle open transactions** page.</span></span>

## <a name="create-a-customer-posting-profile-for-prepayments"></a><span data-ttu-id="83a4d-112">Tworzenie profilu księgowania odbiorcy dla przedpłat</span><span class="sxs-lookup"><span data-stu-id="83a4d-112">Create a customer posting profile for prepayments</span></span>

<span data-ttu-id="83a4d-113">Zazwyczaj w przypadku akceptowania przedpłat lub depozytów od odbiorców przed dostarczonem towarem lub usługą lub przed dodaniem faktury w systemie użytkownik chce zarejestrować gotówkę jako pasywa, a nie środek w plan kont.</span><span class="sxs-lookup"><span data-stu-id="83a4d-113">Typically, when you accept prepayments or deposits from your customers before goods or services are delivered, or before an invoice exists in your system, you will want to record the cash as a liability instead of an asset in your chart of accounts.</span></span> <span data-ttu-id="83a4d-114">Jednak wymagania dotyczące rejestrowania tych kwot w księdze głównej mogą się różnić w zależności od kraju lub regionu.</span><span class="sxs-lookup"><span data-stu-id="83a4d-114">However, the requirements for recording these amounts in your general ledger might differ, depending on your country or region.</span></span> <span data-ttu-id="83a4d-115">Dlatego należy skonsultować się z księgowymi w sprawie wszystkich obowiązujących lokalnych przepisów.</span><span class="sxs-lookup"><span data-stu-id="83a4d-115">Therefore, be sure to consult your accountants about any local regulations that apply.</span></span>

<span data-ttu-id="83a4d-116">Na ogół proces tworzenia profilu księgowania, który może być używany dla przedpłat, jest taki sam jak proces tworzenia innych profilów księgowania.</span><span class="sxs-lookup"><span data-stu-id="83a4d-116">In general, the process for creating a posting profile that can be used for prepayments is the same as the process for creating other posting profiles.</span></span> <span data-ttu-id="83a4d-117">Główną różnicą jest konto główne wybrane w polu **Konto podsumowujące**.</span><span class="sxs-lookup"><span data-stu-id="83a4d-117">The primary difference is the main account that you select in the **Summary account** field.</span></span> <span data-ttu-id="83a4d-118">Aby uzyskać więcej informacji, zobacz [Profile księgowania odbiorców](customer-posting-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="83a4d-118">For more information, see [Customer posting profiles](customer-posting-profiles.md).</span></span>

## <a name="define-parameters-for-customer-prepayments"></a><span data-ttu-id="83a4d-119">Definiuj parametry przedpłat odbiorcy</span><span class="sxs-lookup"><span data-stu-id="83a4d-119">Define parameters for customer prepayments</span></span>

<span data-ttu-id="83a4d-120">Istnieją dwa główne parametry rozrachunków z odbiorcami, które należy uwzględnić podczas konfigurowania systemu dla przedpłat odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="83a4d-120">There are two main Accounts receivable parameters that you must consider when you configure the system for customer prepayments.</span></span> <span data-ttu-id="83a4d-121">Wykonaj poniższe czynności, aby skonfigurować parametry.</span><span class="sxs-lookup"><span data-stu-id="83a4d-121">Follow these steps to configure the parameters.</span></span>

1. <span data-ttu-id="83a4d-122">Wybierz kolejno pozycje **Rozrachunki z odbiorcami \> Ustawienia \> Parametry modułu rozrachunków z odbiorcami**.</span><span class="sxs-lookup"><span data-stu-id="83a4d-122">Go to **Accounts receivable \> Setup \> Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="83a4d-123">Opcjonalnie: na karcie **Księga i podatek** na skróconej karcie **Płatność** ustaw dla opcji **Załącznik arkusza zaliczki** wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="83a4d-123">Optional: On the **Ledger and sales tax** tab, on the **Payment** FastTab, set the **Sales tax on prepayment journal voucher** option to **Yes**.</span></span>
3. <span data-ttu-id="83a4d-124">W polu **Profil księgowania załącznik arkusza zaliczki** wybierz profil księgowania odbiorcy do zastosowania podczas księgowania przedpłat odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="83a4d-124">In the **Posting profile with prepayment journal voucher** field, select the customer posting profile to use when customer prepayments are posted.</span></span>
4. <span data-ttu-id="83a4d-125">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="83a4d-125">Close the page.</span></span>

## <a name="create-customer-prepayment-vouchers"></a><span data-ttu-id="83a4d-126">Tworzenie załączników przedpłat odbiorcy</span><span class="sxs-lookup"><span data-stu-id="83a4d-126">Create customer prepayment vouchers</span></span>

<span data-ttu-id="83a4d-127">Podczas tworzenia arkusza płatności odbiorcy dla każdej przedpłaty trzeba ustawić opcję **Załącznik arkusza przedpłat** **Tak** na stronie **Arkusz płatności odbiorcy**.</span><span class="sxs-lookup"><span data-stu-id="83a4d-127">When you create the customer payment journal, for every prepayment, you must set the **Prepayment journal voucher** option to **Yes** on the **Customer payment journal** page.</span></span> <span data-ttu-id="83a4d-128">Wykonaj poniższe czynności, aby utworzyć przedpłatę klienta.</span><span class="sxs-lookup"><span data-stu-id="83a4d-128">Follow these steps to create a customer prepayment.</span></span>

1. <span data-ttu-id="83a4d-129">Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Płatności \> Arkusz płatności klienta**.</span><span class="sxs-lookup"><span data-stu-id="83a4d-129">Go to **Accounts receivable \> Payments \> Customer payment journal**.</span></span>
2. <span data-ttu-id="83a4d-130">Wybierz **Nowa**, aby utworzyć arkusz.</span><span class="sxs-lookup"><span data-stu-id="83a4d-130">Select **New** to create a journal.</span></span>
3. <span data-ttu-id="83a4d-131">W polu **Nazwa** wybierz nazwę arkusza, która ma być używana.</span><span class="sxs-lookup"><span data-stu-id="83a4d-131">In the **Name** field, select the journal name to use.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="83a4d-132">W przypadku ustawienia dla opcji **Podatek załącznik arkusza zaliczki** opcji **Tak** w poprzedniej procedurze należy wybrać nazwę arkusza, w której zaznaczono parametr **Kwota zawiera podatek**.</span><span class="sxs-lookup"><span data-stu-id="83a4d-132">If you set the **Sales tax on prepayment journal voucher** option to **Yes** in the previous procedure, you must select a journal name where the **Amount includes sales tax** parameter is selected.</span></span> 

4. <span data-ttu-id="83a4d-133">Opcjonalnie: W polu **opis** wprowadź szczegółowy opis.</span><span class="sxs-lookup"><span data-stu-id="83a4d-133">Optional: In the **Description** field, enter a detailed description.</span></span>
5. <span data-ttu-id="83a4d-134">Wybierz **Linie**.</span><span class="sxs-lookup"><span data-stu-id="83a4d-134">Select **Lines**.</span></span>
6. <span data-ttu-id="83a4d-135">Jeśli pusty wiersz nie istnieje, wybierz przycisk **Nowy**, aby utworzyć wiersz.</span><span class="sxs-lookup"><span data-stu-id="83a4d-135">If a blank line doesn't exist, select **New** to create a line.</span></span>
7. <span data-ttu-id="83a4d-136">W polu **Data** należy wpisać datę zaksięgowania przedpłaty.</span><span class="sxs-lookup"><span data-stu-id="83a4d-136">In the **Date** field, enter the date when the prepayment should be posted.</span></span>
8. <span data-ttu-id="83a4d-137">W polu **Konto** wybierz odbiorcę przedpłaty.</span><span class="sxs-lookup"><span data-stu-id="83a4d-137">In the **Account** field, select the customer for the prepayment.</span></span>
9. <span data-ttu-id="83a4d-138">Opcjonalnie: W polu **opis** wprowadź szczegółowy opis transakcji.</span><span class="sxs-lookup"><span data-stu-id="83a4d-138">Optional: In the **Description** field, enter a detailed description of the transaction.</span></span>
10. <span data-ttu-id="83a4d-139">W polu **Kredyt** wprowadź kwotę przedpłaty.</span><span class="sxs-lookup"><span data-stu-id="83a4d-139">In the **Credit** field, enter the amount of the prepayment.</span></span>
11. <span data-ttu-id="83a4d-140">W polu **Typ konta przeciwstawnego** wybierz konto, na które chcesz przeliczyć płatność.</span><span class="sxs-lookup"><span data-stu-id="83a4d-140">In the **Offset account** field, select the account to offset the payment to.</span></span> <span data-ttu-id="83a4d-141">Na przykład wybierz konto bankowe lub główne, w których ma być zaksięgowana płatność.</span><span class="sxs-lookup"><span data-stu-id="83a4d-141">For example, select the bank or main account to post the payment to.</span></span>
12. <span data-ttu-id="83a4d-142">W polu **Metody płatności** wybierz sposób płatności klienta.</span><span class="sxs-lookup"><span data-stu-id="83a4d-142">In the **Method of payment** field, select the customer's method of payment.</span></span>
13. <span data-ttu-id="83a4d-143">Na karcie **Płatność** ustaw opcję **Załącznik arkusza przedpłat** o wartości **Tak**.</span><span class="sxs-lookup"><span data-stu-id="83a4d-143">On the **Payment** tab, set the **Prepayment journal voucher** option to **Yes**.</span></span>
14. <span data-ttu-id="83a4d-144">Powtórz kroki od 7 do 13 dla każdej dodatkowej zaliczki, która musi zostać zaksięgowana.</span><span class="sxs-lookup"><span data-stu-id="83a4d-144">Repeat steps 7 through 13 for each additional prepayment that must be posted.</span></span>
15. <span data-ttu-id="83a4d-145">Wybierz **Publikowanie**, aby sfinalizować dziennik.</span><span class="sxs-lookup"><span data-stu-id="83a4d-145">Select **Post** to finalize the journal.</span></span>

## <a name="settle-prepayments-with-invoices"></a><span data-ttu-id="83a4d-146">Rozlicz przedpłaty za pomocą faktur</span><span class="sxs-lookup"><span data-stu-id="83a4d-146">Settle prepayments with invoices</span></span>

<span data-ttu-id="83a4d-147">Obszar roboczy **Płatności odbiorcy** umożliwia łatwe znajdowanie i rozliczanie płatności, które nie zostały w pełni rozliczone.</span><span class="sxs-lookup"><span data-stu-id="83a4d-147">You can use the **Customer payments** workspace to easily find and settle payments that haven't been fully settled.</span></span>

1. <span data-ttu-id="83a4d-148">Na **głównym** pulpicie nawigacyjnym wybierz kafelek **płatności odbiorcy**.</span><span class="sxs-lookup"><span data-stu-id="83a4d-148">On the **Home** dashboard, select the **Customer payments** tile.</span></span>
2. <span data-ttu-id="83a4d-149">W sekcji **Transakcje odbiorcy** na karcie **Płatności nie rozliczone** wyszukaj i wybierz płatność do rozliczenia.</span><span class="sxs-lookup"><span data-stu-id="83a4d-149">In the **Customer transactions** section, on the **Payments not settled** tab, search for and select the payment to settle.</span></span>
3. <span data-ttu-id="83a4d-150">Wybierz **Rozlicz transakcje**.</span><span class="sxs-lookup"><span data-stu-id="83a4d-150">Select **Settle transactions**.</span></span>
4. <span data-ttu-id="83a4d-151">Zaznacz pole wyboru **Zaznacz** dla faktury i płatność, która zostanie rozliczona.</span><span class="sxs-lookup"><span data-stu-id="83a4d-151">Select the **Mark** check box for the invoice and the payment that will be settled.</span></span>
5. <span data-ttu-id="83a4d-152">Wybierz opcję **Zaksięguj**.</span><span class="sxs-lookup"><span data-stu-id="83a4d-152">Select **Post**.</span></span>

<span data-ttu-id="83a4d-153">Aby uzyskać więcej informacji o rozliczaniu otwartych transakcji, zobacz [Przegląd rozliczania](/cash-bank-management/settlement-overview.md).</span><span class="sxs-lookup"><span data-stu-id="83a4d-153">For more information about how to settle open transactions, see [Settlement overview](/cash-bank-management/settlement-overview.md).</span></span>
