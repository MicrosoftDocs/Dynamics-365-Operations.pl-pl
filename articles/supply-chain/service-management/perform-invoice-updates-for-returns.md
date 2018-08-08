---
title: "Aktualizowanie faktur w związku ze zwrotami"
description: "Ta funkcjonalność obsługuje również procesy biznesowe w organizacjach, które określą, że zamówienia zwrotu i zamówienia sprzedaży mają być fakturowane w tym samym czasie i przez tę samą osobę."
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 2f962641f7fdae18a360567d6f37348fabbfc302
ms.contentlocale: pl-pl
ms.lasthandoff: 08/07/2018

---


# <a name="perform-invoice-updates-for-returns"></a><span data-ttu-id="1dc08-103">Aktualizowanie faktur w związku ze zwrotami</span><span class="sxs-lookup"><span data-stu-id="1dc08-103">Perform invoice updates for returns</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="1dc08-104">Zamówienie zwrotu to rodzaj zamówienia sprzedaży, które jest oznaczone jako zwrot towaru.</span><span class="sxs-lookup"><span data-stu-id="1dc08-104">A return order is a type of sales order that is marked as a returned order.</span></span> <span data-ttu-id="1dc08-105">Z tego względu do generowania faktur dla zamówień zwrotu jest używana strona listy **Wszystkie zamówienia sprzedaży**, a nie formularz **Zamówienia zwrotu**.</span><span class="sxs-lookup"><span data-stu-id="1dc08-105">Therefore, the **All sales orders** list page is used to generate invoices for return orders instead of the **Return orders** form.</span></span> <span data-ttu-id="1dc08-106">Ta funkcjonalność obsługuje również procesy biznesowe w organizacjach, które określą, że zamówienia zwrotu i zamówienia sprzedaży mają być fakturowane w tym samym czasie i przez tę samą osobę.</span><span class="sxs-lookup"><span data-stu-id="1dc08-106">This functionality supports the business processes of organizations that choose to have return orders and sales orders invoiced at the same time and by the same person.</span></span>

<span data-ttu-id="1dc08-107">Ponieważ faktura dla zwróconego towaru jest na kwotę ujemną, jest nazywana fakturą korygującą.</span><span class="sxs-lookup"><span data-stu-id="1dc08-107">Because the invoice for a returned item is for a negative amount, it is called a credit note.</span></span>

<span data-ttu-id="1dc08-108">W przypadku skonfigurowania wsadowego przetwarzania aktualizacji faktur zamówienie sprzedaży typu **Zwrot towaru** musi zawierać wiersz zwrotu o stanie **Otrzymano**, co oznacza, że dokument dostawy zamówienia został zaktualizowany.</span><span class="sxs-lookup"><span data-stu-id="1dc08-108">When you set up the invoice update for batch processing, the sales order of type **Returned order** must have a return line status of **Received**, which indicates that the order's packing slip has been updated.</span></span>

## <a name="post-an-invoice-for-a-return-order"></a><span data-ttu-id="1dc08-109">Księgowanie faktury dla zamówienia zwrotu</span><span class="sxs-lookup"><span data-stu-id="1dc08-109">Post an invoice for a return order</span></span>

1.  <span data-ttu-id="1dc08-110">Kliknij kolejno opcje **Rozrachunki z odbiorcami** \> **Wspólne** \> **Zamówienia sprzedaży** \> **Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="1dc08-110">Click **Accounts receivable** \> **Common** \> **Sales orders** \> **All sales orders**.</span></span>

2.  <span data-ttu-id="1dc08-111">Zaznacz zamówienie sprzedaży, dla którego w polu **Typ zamówienia** jest wyświetlana wartość **Zamówienie zwrotu**.</span><span class="sxs-lookup"><span data-stu-id="1dc08-111">Select a sales order for which **Returned order** is displayed in the **Order type** field.</span></span>

3.  <span data-ttu-id="1dc08-112">W okienku akcji na karcie **Faktura** w grupie **Generuj** kliknij opcję **Faktura**.</span><span class="sxs-lookup"><span data-stu-id="1dc08-112">On the Action Pane, on the **Invoice** tab, in the **Generate** group, click **Invoice**.</span></span>

4.  <span data-ttu-id="1dc08-113">Na karcie **Parametry** zaznacz pole wyboru **Księgowanie**.</span><span class="sxs-lookup"><span data-stu-id="1dc08-113">On the **Parameters** tab, select the **Posting** check box.</span></span>

5.  <span data-ttu-id="1dc08-114">Przejrzyj informacje w formularzu i wprowadź niezbędne zmiany.</span><span class="sxs-lookup"><span data-stu-id="1dc08-114">Review information in the form and make any changes that are needed.</span></span>

6.  <span data-ttu-id="1dc08-115">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="1dc08-115">Click **OK**.</span></span> <span data-ttu-id="1dc08-116">Faktura korygująca zostanie zaksięgowana.</span><span class="sxs-lookup"><span data-stu-id="1dc08-116">The credit note is posted.</span></span>

## <a name="see-also"></a><span data-ttu-id="1dc08-117">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="1dc08-117">See also</span></span>

[<span data-ttu-id="1dc08-118">Aktualizowanie dokumentów dostawy w związku ze zwrotami</span><span class="sxs-lookup"><span data-stu-id="1dc08-118">Packing slip updates for returns</span></span>](packing-slip-updates-returns.md)

  



