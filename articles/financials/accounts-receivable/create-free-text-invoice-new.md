---
title: Tworzenie faktur niezależnych
description: W tym temacie opisano sposób tworzenia faktur niezależnych.
author: mikefalkner
manager: AnnBe
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: f6ee6fda0b52b8af7c253b7d22e470345a8a421f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "332249"
---
# <a name="create-free-text-invoices"></a><span data-ttu-id="e15cd-103">Tworzenie faktur niezależnych</span><span class="sxs-lookup"><span data-stu-id="e15cd-103">Create free text invoices</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e15cd-104">W tym temacie opisano sposób tworzenia faktur niezależnych.</span><span class="sxs-lookup"><span data-stu-id="e15cd-104">This topic explains how to create free text invoices.</span></span> <span data-ttu-id="e15cd-105">Ta procedura wykorzystuje firmę demonstracyjną **USMF**.</span><span class="sxs-lookup"><span data-stu-id="e15cd-105">For the procedure, use the **USMF** demo company.</span></span>

## <a name="create-a-free-text-invoice"></a><span data-ttu-id="e15cd-106">Tworzenie faktury niezależnej</span><span class="sxs-lookup"><span data-stu-id="e15cd-106">Create a free text invoice</span></span>

1. <span data-ttu-id="e15cd-107">Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Faktury \> Wszystkie faktury niezależne**.</span><span class="sxs-lookup"><span data-stu-id="e15cd-107">Go to **Accounts receivable \> Invoices \> All free text invoices**.</span></span>
2. <span data-ttu-id="e15cd-108">Wybierz **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="e15cd-108">Select **New**.</span></span>
3. <span data-ttu-id="e15cd-109">W polu **Konto odbiorcy** wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e15cd-109">In the **Customer account** field, select a value.</span></span>

    * <span data-ttu-id="e15cd-110">Domyślnie kontem faktury będzie konto wybrane jako konto odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="e15cd-110">By default, the account that is selected as the customer account is used as the invoice account.</span></span>
    * <span data-ttu-id="e15cd-111">Jeśli faktura nie jest zaksięgowana, stan księgowania zaczyna się od stanu **W trakcie przetwarzania**.</span><span class="sxs-lookup"><span data-stu-id="e15cd-111">If the invoice isn't posted, the accounting status starts with **In process**.</span></span>
    * <span data-ttu-id="e15cd-112">Identyfikator faktury zostanie przypisany podczas księgowania faktury.</span><span class="sxs-lookup"><span data-stu-id="e15cd-112">The invoice number will be assigned when the invoice is posted.</span></span>
    * <span data-ttu-id="e15cd-113">Jeśli używasz upoważnień bankowych SEPA (Jednolitego Obszaru Płatniczego w Euro), zgoda na polecenie zapłaty będzie automatycznie wprowadzana po wybraniu konta odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="e15cd-113">If you're using Single Euro Payments Area (SEPA) mandates, the direct debit mandate is automatically entered when you select the customer account.</span></span>

4. <span data-ttu-id="e15cd-114">W polu **Opis** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e15cd-114">In the **Description** field, enter a value.</span></span>
5. <span data-ttu-id="e15cd-115">W polu **Konto główne** określ numer konta, które nie ma wymiarów.</span><span class="sxs-lookup"><span data-stu-id="e15cd-115">In the **Main account** field, specify an account number that doesn't have dimensions.</span></span> <span data-ttu-id="e15cd-116">Wymiary zostaną wprowadzone w dalszej części tego tematu.</span><span class="sxs-lookup"><span data-stu-id="e15cd-116">You will enter dimensions later in this topic.</span></span>

    <span data-ttu-id="e15cd-117">Można również wpisać jeden lub więcej znaków konta głównego, a następnie za pomocą funkcji wyszukiwania znaleźć konto.</span><span class="sxs-lookup"><span data-stu-id="e15cd-117">You can also enter one or more characters for the main account, and use the lookup to find the account.</span></span>

6. <span data-ttu-id="e15cd-118">Kliknij skróconą kartę **Szczegóły wiersza**, aby dodać wymiary do konta głównego.</span><span class="sxs-lookup"><span data-stu-id="e15cd-118">Select the **Line details** FastTab to add dimensions to the main account.</span></span>
7. <span data-ttu-id="e15cd-119">Kliknij kartę **Wiersz wymiarów finansowych**.</span><span class="sxs-lookup"><span data-stu-id="e15cd-119">Select the **Financial dimensions line** tab.</span></span>

    * <span data-ttu-id="e15cd-120">Wymiary dotyczą tylko wybranego wiersza.</span><span class="sxs-lookup"><span data-stu-id="e15cd-120">The dimensions are for the selected line only.</span></span>
    * <span data-ttu-id="e15cd-121">Grupa podatków jest wypełniania domyślnie na podstawie odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="e15cd-121">The sales tax group is filled in from the customer.</span></span> <span data-ttu-id="e15cd-122">Jeśli odbiorca nie ma zdefiniowanej grupy podatków, jest używana grupa podatków z konta głównego.</span><span class="sxs-lookup"><span data-stu-id="e15cd-122">If the customer doesn't have a sales tax group, the sales tax group from the main account is used.</span></span>
    * <span data-ttu-id="e15cd-123">Grupa podatków dla pozycji jest wypełniana na podstawie konta głównego.</span><span class="sxs-lookup"><span data-stu-id="e15cd-123">The items sales tax group is filled in from the main account.</span></span> <span data-ttu-id="e15cd-124">Jeśli konto główne nie ma zdefiniowanej grupy podatków dla pozycji, jest używana grupa podatków dla pozycji określona w parametrach podatków w Księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="e15cd-124">If the main account doesn't have an item sales tax group, the item sales tax group that is specified in the sales tax parameters in General ledger is used.</span></span>

8. <span data-ttu-id="e15cd-125">Opcjonalnie: wprowadź liczbę w polu **Ilość**.</span><span class="sxs-lookup"><span data-stu-id="e15cd-125">Optional: In the **Quantity** field, enter a number.</span></span>
9. <span data-ttu-id="e15cd-126">Opcjonalnie: w polu **Cena jednostkowa** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="e15cd-126">Optional: In the **Unit price** field, enter a number.</span></span>

    <span data-ttu-id="e15cd-127">Kwota jest obliczana jako ilość pomnożona przez cenę jednostkową.</span><span class="sxs-lookup"><span data-stu-id="e15cd-127">The amount is calculated as the quantity times the unit price.</span></span> <span data-ttu-id="e15cd-128">Można jednak zastąpić wynik tego obliczenia poprzez samodzielne wprowadzenie kwoty.</span><span class="sxs-lookup"><span data-stu-id="e15cd-128">However, you can override that calculation by entering an amount.</span></span>

10. <span data-ttu-id="e15cd-129">Kliknij opcję **Podatek**, aby wyświetlić podatek obliczony dla faktury.</span><span class="sxs-lookup"><span data-stu-id="e15cd-129">Select **Sales tax** to view the sales tax that is calculated for the invoice.</span></span>

    <span data-ttu-id="e15cd-130">Można wyświetlić kwoty podatków na tej stronie albo zastąpić kwoty na karcie **Korekta**.</span><span class="sxs-lookup"><span data-stu-id="e15cd-130">You can view the sales tax amounts on this page, or you can override the amounts on the **Adjustment** tab.</span></span>

11. <span data-ttu-id="e15cd-131">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="e15cd-131">Select **OK**.</span></span>
12. <span data-ttu-id="e15cd-132">Kliknij opcję **Opłaty**, aby dodać opłatę do faktury.</span><span class="sxs-lookup"><span data-stu-id="e15cd-132">Select **Charges** to add a charge to the invoice.</span></span>
13. <span data-ttu-id="e15cd-133">W polu **Kod opłat** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e15cd-133">In the **Charges code** field, enter a value.</span></span>
14. <span data-ttu-id="e15cd-134">W polu **Wartość opłat** wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="e15cd-134">In the **Charges value** field, enter a number.</span></span>
15. <span data-ttu-id="e15cd-135">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e15cd-135">Close the page.</span></span>
16. <span data-ttu-id="e15cd-136">Kliknij opcję **Sumy**, aby wyświetlić szczegóły i sumy faktury zbiorczej.</span><span class="sxs-lookup"><span data-stu-id="e15cd-136">Select **Totals** to view a summary of the invoice details and totals.</span></span>
17. <span data-ttu-id="e15cd-137">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="e15cd-137">Select **Close**.</span></span>
18. <span data-ttu-id="e15cd-138">Wybierz opcję **Księguj**, aby zaksięgować fakturę.</span><span class="sxs-lookup"><span data-stu-id="e15cd-138">Select **Post** to post the invoice.</span></span> <span data-ttu-id="e15cd-139">Nadal będziesz mieć możliwość anulowania operacji przed rzeczywistym zaksięgowaniem.</span><span class="sxs-lookup"><span data-stu-id="e15cd-139">You will still have an opportunity to cancel before you actually post.</span></span>

    * <span data-ttu-id="e15cd-140">Możesz zmienić harmonogram drukowania faktur.</span><span class="sxs-lookup"><span data-stu-id="e15cd-140">You can change the timing of invoice printing.</span></span> <span data-ttu-id="e15cd-141">Zaznacz opcję **Bieżąca**, aby drukować każdą fakturę po jej aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="e15cd-141">Select **Current** to print each invoice as it's updated.</span></span> <span data-ttu-id="e15cd-142">Zaznacz opcję **Po**, aby drukować po zaktualizowaniu wszystkich faktur.</span><span class="sxs-lookup"><span data-stu-id="e15cd-142">Select **After** to print after all invoices have been updated.</span></span>
    * <span data-ttu-id="e15cd-143">Aby zmienić sposób weryfikowania limitu kredytowego odbiorcy przed zaksięgowaniem faktury, zmień wartość w pola **Typ limitu kredytu**.</span><span class="sxs-lookup"><span data-stu-id="e15cd-143">To change how the customer's credit limit is verified before the invoice is posted, change the value in the **Credit limit type** field.</span></span>
    * <span data-ttu-id="e15cd-144">Aby wydrukować fakturę, zaznacz w tej opcji wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="e15cd-144">To print the invoice, set the option to **Yes**.</span></span>
    * <span data-ttu-id="e15cd-145">Aby zaksięgować fakturę, zaznacz w tej opcji wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="e15cd-145">To post the invoice, set the option to **Yes**.</span></span> <span data-ttu-id="e15cd-146">Fakturę można wydrukować bez księgowania.</span><span class="sxs-lookup"><span data-stu-id="e15cd-146">You can print the invoice without posting it.</span></span>

19. <span data-ttu-id="e15cd-147">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="e15cd-147">Select **OK**.</span></span>

## <a name="copy-lines"></a><span data-ttu-id="e15cd-148">Kopiuj wiersze</span><span class="sxs-lookup"><span data-stu-id="e15cd-148">Copy lines</span></span>
<span data-ttu-id="e15cd-149">Aby skopiować wiersze faktury niezależnej, zaznacz jeden lub więcej wierszy, a następnie kliknij przycisk **Kopiuj zaznaczone wiersze**.</span><span class="sxs-lookup"><span data-stu-id="e15cd-149">To copy lines on a free text invoice, select one or more lines, and then select **Copy selected lines**.</span></span> <span data-ttu-id="e15cd-150">Można określić liczbę kopii, jaka ma zostać wykonana, oraz skopiować notatki i załączniki.</span><span class="sxs-lookup"><span data-stu-id="e15cd-150">You can specify the number of copies to make, and you can also copy notes and attachments.</span></span> <span data-ttu-id="e15cd-151">Można skopiować dystrybucje lub pozwolić na ich ponowne tworzenie podczas księgowania.</span><span class="sxs-lookup"><span data-stu-id="e15cd-151">You can either copy the distributions or let them be re-created when you post.</span></span>

<span data-ttu-id="e15cd-152">Po skopiowaniu wierszy można edytować informacje zgodnie z potrzebami.</span><span class="sxs-lookup"><span data-stu-id="e15cd-152">After you copy lines, you can edit the information as you require.</span></span>

## <a name="create-a-free-text-invoice-from-a-template"></a><span data-ttu-id="e15cd-153">Tworzenie faktury niezależnej z szablonu</span><span class="sxs-lookup"><span data-stu-id="e15cd-153">Create a free text invoice from a template</span></span>
<span data-ttu-id="e15cd-154">Fakturę niezależną można utworzyć na podstawie szablonu.</span><span class="sxs-lookup"><span data-stu-id="e15cd-154">You can create a free text invoice from a template.</span></span> <span data-ttu-id="e15cd-155">Gdy na karcie **Faktura** wybierzesz opcję **Nowe z szablonu**, można wybrać nazwę szablonu i konto odbiorcy dla nowej faktury niezależnej.</span><span class="sxs-lookup"><span data-stu-id="e15cd-155">When you select **New from template** on the **Invoice** tab, you can select a template name and the customer account for the new free text invoice.</span></span> <span data-ttu-id="e15cd-156">Wartości domyślne, takie jak warunki płatności i metoda płatności, mogą być automatycznie wprowadzane na podstawie danych odbiorcy lub też można użyć wartości zapisanych w szablonie.</span><span class="sxs-lookup"><span data-stu-id="e15cd-156">Default values, such as the terms of payment and method of payment, can be automatically filled in from the customer, or you can use the values that were saved in the template.</span></span>

<span data-ttu-id="e15cd-157">Zostanie utworzona nowa faktura niezależna i można w niej edytować wartości zgodnie z potrzebami.</span><span class="sxs-lookup"><span data-stu-id="e15cd-157">A new free text invoice is created, and you can edit the values as you require.</span></span>
