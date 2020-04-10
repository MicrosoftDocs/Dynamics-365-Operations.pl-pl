---
title: Wprowadzanie najważniejszych danych faktury do modułu rozrachunków z dostawcami za pomocą arkusza zatwierdzania
description: W tym przewodniku pokazano sposób używania rejestru faktur do tworzenia faktur, a następnie używania arkusza zatwierdzania do aktualizowania kont wydatków.
author: abruer
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransInvoiceRegister, HcmWorkerLookUp, LedgerJournalTransApprove, LedgerJournalTransApproveFetchVouchers, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 788397b5c9a3f42e373f7cdad256c1ee3d058e57
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143773"
---
# <a name="key-invoice-data-into-accounts-payable-using-an-approval-journal"></a><span data-ttu-id="c41e8-103">Wprowadzanie najważniejszych danych faktury do modułu rozrachunków z dostawcami za pomocą arkusza zatwierdzania</span><span class="sxs-lookup"><span data-stu-id="c41e8-103">Key invoice data into accounts payable using an approval journal</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c41e8-104">W tym przewodniku pokazano sposób używania rejestru faktur do tworzenia faktur, a następnie używania arkusza zatwierdzania do aktualizowania kont wydatków.</span><span class="sxs-lookup"><span data-stu-id="c41e8-104">This topic explains how to use the invoice register to create invoices and then use the approval journal to update the expense accounts.</span></span>

## <a name="create-and-post-and-invoice"></a><span data-ttu-id="c41e8-105">Tworzenie i księgowanie faktury</span><span class="sxs-lookup"><span data-stu-id="c41e8-105">Create and post and invoice</span></span>
1. <span data-ttu-id="c41e8-106">W okienku nawigacji przejdź do **Moduły > Rozrachunki z dostawcami > Faktury > Rejestr faktur**.</span><span class="sxs-lookup"><span data-stu-id="c41e8-106">In the navigation pan, go to **Modules > Accounts payable > Invoices > Invoice register**.</span></span>
2. <span data-ttu-id="c41e8-107">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="c41e8-107">Select **New**.</span></span>
3. <span data-ttu-id="c41e8-108">Wybierz nazwę rejestru faktur, którego chcesz używać.</span><span class="sxs-lookup"><span data-stu-id="c41e8-108">Select the name of the invoice register that you want to use.</span></span>
4. <span data-ttu-id="c41e8-109">Kliknij przycisk **Wiersze**, aby otworzyć rejestr i wprowadzić wiersze wydatków.</span><span class="sxs-lookup"><span data-stu-id="c41e8-109">Select **Lines** to open the register and enter expense lines.</span></span>
5. <span data-ttu-id="c41e8-110">Wybierz dostawcę.</span><span class="sxs-lookup"><span data-stu-id="c41e8-110">Select a vendor.</span></span> <span data-ttu-id="c41e8-111">Na przykład wprowadź lub wybierz dostawcę `US-104`.</span><span class="sxs-lookup"><span data-stu-id="c41e8-111">For example, enter or select `US-104`.</span></span>
6. <span data-ttu-id="c41e8-112">W polu **Faktura** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c41e8-112">In the **Invoice** field, type a value.</span></span>
7. <span data-ttu-id="c41e8-113">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c41e8-113">In the **Description** field, type a value.</span></span>
8. <span data-ttu-id="c41e8-114">W polu **Kredyt** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="c41e8-114">In the **Credit** field, enter a number.</span></span>
9. <span data-ttu-id="c41e8-115">W polu **Zatwierdzone przez** wybierz osobę zatwierdzającą z menu rozwijanego.</span><span class="sxs-lookup"><span data-stu-id="c41e8-115">In the **Approved by** field, select an approver from the drop-down menu.</span></span>
10. <span data-ttu-id="c41e8-116">Wybierz opcję **Zaksięguj**.</span><span class="sxs-lookup"><span data-stu-id="c41e8-116">Select **Post**.</span></span>

## <a name="approve-an-invoice"></a><span data-ttu-id="c41e8-117">Zatwierdzanie faktury</span><span class="sxs-lookup"><span data-stu-id="c41e8-117">Approve an invoice</span></span>
1. <span data-ttu-id="c41e8-118">W okienku nawigacji przejdź do **Moduły > Rozrachunki z dostawcami > Faktury > Zatwierdzenie faktury**.</span><span class="sxs-lookup"><span data-stu-id="c41e8-118">In the navigation pane, go to **Modules > Accounts payable > Invoices > Invoice approval**.</span></span>
2. <span data-ttu-id="c41e8-119">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="c41e8-119">Select **New**.</span></span>
3. <span data-ttu-id="c41e8-120">Wybierz nazwę arkusza zatwierdzania faktur, którego chcesz używać.</span><span class="sxs-lookup"><span data-stu-id="c41e8-120">Select the name of the invoice approval journal that you want to use.</span></span>
4. <span data-ttu-id="c41e8-121">Wybierz **Wiersze**, a zostanie wyświetlona strona, gdzie będzie można wybrać faktury do zatwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="c41e8-121">Select **Lines** to display a page where you will be able to select the invoices that you want to approve.</span></span>
5. <span data-ttu-id="c41e8-122">Kliknij przycisk **Znajdź załączniki**, aby wyświetlić wszystkie faktury gotowe do zatwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="c41e8-122">Select **Find Vouchers** to display all of the invoices that are ready for approval.</span></span>
6. <span data-ttu-id="c41e8-123">Zaznacz utworzoną fakturę, a następnie kliknij przycisk **Wybierz**.</span><span class="sxs-lookup"><span data-stu-id="c41e8-123">Mark the invoice that you created, then click **Select**.</span></span> <span data-ttu-id="c41e8-124">Załączniki wybrane powyżej zostaną po zaznaczeniu przeniesione do tej listy.</span><span class="sxs-lookup"><span data-stu-id="c41e8-124">The vouchers that you selected above are moved to this list after you select them.</span></span>  
7. <span data-ttu-id="c41e8-125">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="c41e8-125">Select **OK**.</span></span>
8. <span data-ttu-id="c41e8-126">Wybierz **Numer konta**, aby dodać konto wydatków do faktury.</span><span class="sxs-lookup"><span data-stu-id="c41e8-126">Select the **account number** field to add an expense account to the invoice.</span></span>
9. <span data-ttu-id="c41e8-127">Wprowadź numer konta i opuść to pole.</span><span class="sxs-lookup"><span data-stu-id="c41e8-127">Enter an account number and tab off of the field.</span></span> <span data-ttu-id="c41e8-128">Na przykład wpisz `600120`.</span><span class="sxs-lookup"><span data-stu-id="c41e8-128">For example, enter `600120`.</span></span>
10. <span data-ttu-id="c41e8-129">Wybierz opcję **Zaksięguj**.</span><span class="sxs-lookup"><span data-stu-id="c41e8-129">Select **Post**.</span></span>
11. <span data-ttu-id="c41e8-130">Wybierz **Załącznik**, aby wyświetlić zapisy, które zostały zaksięgowane.</span><span class="sxs-lookup"><span data-stu-id="c41e8-130">Select **Voucher** to view the entries that were posted.</span></span> <span data-ttu-id="c41e8-131">Konto faktur oczekujących na zatwierdzenie zostanie wycofane i zastąpione kontem wydatków rzeczywistych.</span><span class="sxs-lookup"><span data-stu-id="c41e8-131">The Invoice Pending Approval account is reversed and replaced with the actual expense account.</span></span>  

