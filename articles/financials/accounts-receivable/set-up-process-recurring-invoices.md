---
title: Konfigurowanie i przetwarzania faktur cyklicznych
description: W tym artykule wyjaśniono, jak konfigurować i przetwarzać faktury cykliczne. Faktur cyklicznych można używać, jeśli regularnie trzeba fakturować odbiorców na tę samą kwotę.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustInvoiceTemplate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 14011
ms.assetid: 9cc37003-adf1-413d-b2b2-2badcf512e3b
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ac9e836b0baa24c40554844ea4f3288b80e0c654
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "350212"
---
# <a name="set-up-and-process-recurring-invoices"></a><span data-ttu-id="b6cab-104">Konfigurowanie i przetwarzania faktur cyklicznych</span><span class="sxs-lookup"><span data-stu-id="b6cab-104">Set up and process recurring invoices</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b6cab-105">W tym artykule wyjaśniono, jak konfigurować i przetwarzać faktury cykliczne.</span><span class="sxs-lookup"><span data-stu-id="b6cab-105">This article explains how to set up and process recurring invoices.</span></span> <span data-ttu-id="b6cab-106">Faktur cyklicznych można używać, jeśli regularnie trzeba fakturować odbiorców na tę samą kwotę.</span><span class="sxs-lookup"><span data-stu-id="b6cab-106">You can use recurring invoices if you must invoice customers for the same amount on a regular basis.</span></span>

<a name="create-a-recurring-free-text-invoice-template"></a><span data-ttu-id="b6cab-107">Tworzenie szablonu cyklicznej faktury niezależnej</span><span class="sxs-lookup"><span data-stu-id="b6cab-107">Create a recurring free text invoice template</span></span>
---------------------------------------------

<span data-ttu-id="b6cab-108">Aby wystawiać faktury dla odbiorców za te same usługi w regularnych odstępach czasu, trzeba zdefiniować szablon faktury niezależnej, który może być używany wielokrotnie do tworzenia faktur.</span><span class="sxs-lookup"><span data-stu-id="b6cab-108">To invoice customers for the same services on a regular basis, you must define a free text invoice template that can be reused to create the invoices.</span></span> <span data-ttu-id="b6cab-109">Szablon zawiera następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="b6cab-109">This template contains the following information:</span></span>

-   <span data-ttu-id="b6cab-110">Informacje nagłówka, takie jak grupy podatków, warunki płatności i metody płatności</span><span class="sxs-lookup"><span data-stu-id="b6cab-110">Header information, such as tax groups, terms of payment, and the method of payment</span></span>
-   <span data-ttu-id="b6cab-111">Informacje wiersza, takie jak opis usługi, konta przychodów, cena jednostkowa i kwota faktury</span><span class="sxs-lookup"><span data-stu-id="b6cab-111">Line information, such as the service description, revenue accounts, unit price, and invoice amount</span></span>
-   <span data-ttu-id="b6cab-112">Opłaty za wysyłkę lub obsługę</span><span class="sxs-lookup"><span data-stu-id="b6cab-112">Charges for shipping or handling</span></span>
-   <span data-ttu-id="b6cab-113">Zasady podziału księgowań łącznie z informacjami o wymiarach finansowych, takie jak centra kosztów i jednostki biznesowe</span><span class="sxs-lookup"><span data-stu-id="b6cab-113">Accounting distributions together with financial dimension information, such as cost centers and business units</span></span>

<span data-ttu-id="b6cab-114">W efekcie tworzysz całą fakturę i zapisujesz ją jako szablon.</span><span class="sxs-lookup"><span data-stu-id="b6cab-114">In effect, you're creating an entire invoice and saving it as a template.</span></span> <span data-ttu-id="b6cab-115">Szablony konfiguruje się za pomocą strony **Faktury cykliczne**.</span><span class="sxs-lookup"><span data-stu-id="b6cab-115">You can set up the templates using the **Recurring invoices** page.</span></span>

## <a name="assign-a-free-text-invoice-template-to-a-customer-and-enter-recurrence-details"></a><span data-ttu-id="b6cab-116">Przypisywanie szablonu faktury niezależnej do odbiorcy i wpisywanie szczegółów cyklu</span><span class="sxs-lookup"><span data-stu-id="b6cab-116">Assign a free text invoice template to a customer and enter recurrence details</span></span>
<span data-ttu-id="b6cab-117">Po utworzeniu szablonu trzeba przypisać szablon do odbiorców, którym chcesz wystawić fakturę.</span><span class="sxs-lookup"><span data-stu-id="b6cab-117">After the template is created, you must assign the template to the customers that you want to invoice.</span></span> <span data-ttu-id="b6cab-118">Oprócz tego trzeba określić, kiedy i jak często faktura ma być używana.</span><span class="sxs-lookup"><span data-stu-id="b6cab-118">Additionally, you must specify when and how often the invoice will be used.</span></span> <span data-ttu-id="b6cab-119">Szablony można przypisywać na karcie **Faktura** na stronie **Odbiorcy**.</span><span class="sxs-lookup"><span data-stu-id="b6cab-119">You can assign the templates on the **Invoice** tab of the **Customers** page.</span></span> <span data-ttu-id="b6cab-120">Dodaj szablon do listy i zaktualizuj następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="b6cab-120">Add the template to the list, and update the following information:</span></span>

-   <span data-ttu-id="b6cab-121">Data rozpoczęcia i, opcjonalnie, data zakończenia cyklu fakturowania</span><span class="sxs-lookup"><span data-stu-id="b6cab-121">The start date and, optionally, the end date for the recurring billing</span></span>
-   <span data-ttu-id="b6cab-122">Częstotliwość cyklu fakturowania (na przykład codziennie lub raz na miesiąc)</span><span class="sxs-lookup"><span data-stu-id="b6cab-122">The frequency of the recurring billing (for example, every day or once a month)</span></span>
-   <span data-ttu-id="b6cab-123">Maksymalna kwota fakturowania (jeśli ta informacja jest wymagana)</span><span class="sxs-lookup"><span data-stu-id="b6cab-123">The maximum billing amount (if this information is required)</span></span>

<span data-ttu-id="b6cab-124">Odbiorca może mieć wiele szablonów z różnymi częstotliwościami.</span><span class="sxs-lookup"><span data-stu-id="b6cab-124">A customer can have multiple templates that have different frequencies.</span></span>

## <a name="generate-the-recurring-invoices"></a><span data-ttu-id="b6cab-125">Generowane faktur cyklicznych</span><span class="sxs-lookup"><span data-stu-id="b6cab-125">Generate the recurring invoices</span></span>
<span data-ttu-id="b6cab-126">Na stronie **Faktury cykliczne** jest zadanie do przetwarzania szablonów faktur cyklicznych.</span><span class="sxs-lookup"><span data-stu-id="b6cab-126">On the **Recurring invoices** page, there is a task that processes recurring invoice templates.</span></span> <span data-ttu-id="b6cab-127">Określasz datę faktury i szablon do generowania faktur.</span><span class="sxs-lookup"><span data-stu-id="b6cab-127">You specify the invoice date and the template to generate the invoices from.</span></span> <span data-ttu-id="b6cab-128">Faktury będą generowane i przypisywane do jednego cyklicznego identyfikatora dla każdej przetwarzanej grupy faktur.</span><span class="sxs-lookup"><span data-stu-id="b6cab-128">Invoices will be generated and assigned a single recurrence ID number for each group of invoices that is processed.</span></span>

<a name="post-recurring-free-text-invoices"></a><span data-ttu-id="b6cab-129">Księgowanie cyklicznych faktur niezależnych</span><span class="sxs-lookup"><span data-stu-id="b6cab-129">Post recurring free text invoices</span></span>
---------------------------------

<span data-ttu-id="b6cab-130">Po wygenerowaniu faktur cyklicznych w zadaniu księgowania w zadaniu pojawiają się identyfikatory cyklu faktur na stronie **Faktury cykliczne**.</span><span class="sxs-lookup"><span data-stu-id="b6cab-130">After recurring invoices are generated, the invoice recurrence IDs appear in a posting task on the **Recurring invoices** page.</span></span> <span data-ttu-id="b6cab-131">Można wyświetlić wszystkie faktury dla identyfikatora cyklu, klikając łącze.</span><span class="sxs-lookup"><span data-stu-id="b6cab-131">You can view all of the invoices for a recurrence ID by clicking the link.</span></span> <span data-ttu-id="b6cab-132">Podczas przeglądu faktur dla identyfikatora cyklu można usunąć indywidualne faktury.</span><span class="sxs-lookup"><span data-stu-id="b6cab-132">During your review of the invoices for the recurrence ID, you can delete individual invoices.</span></span> <span data-ttu-id="b6cab-133">Ustawienia cyklu odbiorcy zostaną zresetowane dla tego szablonu, tak aby można było go wygenerować ponownie później.</span><span class="sxs-lookup"><span data-stu-id="b6cab-133">The customer's recurrence settings will be reset for that template, so that it can be regenerated later.</span></span> <span data-ttu-id="b6cab-134">Można księgować jedną, wiele lub wszystkie faktury dla identyfikatora cyklu.</span><span class="sxs-lookup"><span data-stu-id="b6cab-134">You can post one, many, or all of the invoices for a recurrence ID.</span></span> <span data-ttu-id="b6cab-135">Jeśli przepływy pracy są włączone, należy kliknąć opcję **Prześlij** przed zaksięgowaniem faktury.</span><span class="sxs-lookup"><span data-stu-id="b6cab-135">If workflows are enabled, you must click **Submit** before you can post the invoices.</span></span>

<a name="print-recurring-free-text-invoices"></a><span data-ttu-id="b6cab-136">Drukowanie cyklicznych faktur niezależnych</span><span class="sxs-lookup"><span data-stu-id="b6cab-136">Print recurring free text invoices</span></span>
----------------------------------

<span data-ttu-id="b6cab-137">Po zaksięgowaniu faktur cyklicznych można je drukować ze strony listy faktur niezależnych.</span><span class="sxs-lookup"><span data-stu-id="b6cab-137">After recurring invoices are posted, you can print the invoices from the free text invoice list page.</span></span> <span data-ttu-id="b6cab-138">Można drukować faktury, które są wybrane, lub można wybrać zakres faktur do wydrukowania.</span><span class="sxs-lookup"><span data-stu-id="b6cab-138">You can print the invoices that are selected, or you can select a range of invoices to print.</span></span>



