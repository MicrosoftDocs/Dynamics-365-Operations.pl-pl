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
ms.openlocfilehash: fb690769a33f88e63ab8f54cec69a5e927fd324c
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179469"
---
# <a name="key-invoice-data-into-accounts-payable-using-an-approval-journal"></a><span data-ttu-id="95cd4-103">Wprowadzanie najważniejszych danych faktury do modułu rozrachunków z dostawcami za pomocą arkusza zatwierdzania</span><span class="sxs-lookup"><span data-stu-id="95cd4-103">Key invoice data into accounts payable using an approval journal</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="95cd4-104">W tym przewodniku pokazano sposób używania rejestru faktur do tworzenia faktur, a następnie używania arkusza zatwierdzania do aktualizowania kont wydatków.</span><span class="sxs-lookup"><span data-stu-id="95cd4-104">This topic explains how to use the invoice register to create invoices and then use the approval journal to update the expense accounts.</span></span>

## <a name="create-and-post-and-invoice"></a><span data-ttu-id="95cd4-105">Tworzenie i księgowanie faktury</span><span class="sxs-lookup"><span data-stu-id="95cd4-105">Create and post and invoice</span></span>
1. <span data-ttu-id="95cd4-106">W okienku nawigacji przejdź do **Moduły > Rozrachunki z dostawcami > Faktury > Rejestr faktur**.</span><span class="sxs-lookup"><span data-stu-id="95cd4-106">In the navigation pan, go to **Modules > Accounts payable > Invoices > Invoice register**.</span></span>
2. <span data-ttu-id="95cd4-107">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="95cd4-107">Select **New**.</span></span>
3. <span data-ttu-id="95cd4-108">Wybierz nazwę rejestru faktur, którego chcesz używać.</span><span class="sxs-lookup"><span data-stu-id="95cd4-108">Select the name of the invoice register that you want to use.</span></span>
4. <span data-ttu-id="95cd4-109">Kliknij przycisk **Wiersze**, aby otworzyć rejestr i wprowadzić wiersze wydatków.</span><span class="sxs-lookup"><span data-stu-id="95cd4-109">Select **Lines** to open the register and enter expense lines.</span></span>
5. <span data-ttu-id="95cd4-110">Wybierz dostawcę.</span><span class="sxs-lookup"><span data-stu-id="95cd4-110">Select a vendor.</span></span> <span data-ttu-id="95cd4-111">Na przykład wprowadź lub wybierz dostawcę `US-104`.</span><span class="sxs-lookup"><span data-stu-id="95cd4-111">For example, enter or select `US-104`.</span></span>
6. <span data-ttu-id="95cd4-112">W polu **Faktura** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="95cd4-112">In the **Invoice** field, type a value.</span></span>
7. <span data-ttu-id="95cd4-113">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="95cd4-113">In the **Description** field, type a value.</span></span>
8. <span data-ttu-id="95cd4-114">W polu **Kredyt** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="95cd4-114">In the **Credit** field, enter a number.</span></span>
9. <span data-ttu-id="95cd4-115">W polu **Zatwierdzone przez** wybierz osobę zatwierdzającą z menu rozwijanego.</span><span class="sxs-lookup"><span data-stu-id="95cd4-115">In the **Approved by** field, select an approver from the drop-down menu.</span></span>
10. <span data-ttu-id="95cd4-116">Wybierz opcję **Zaksięguj**.</span><span class="sxs-lookup"><span data-stu-id="95cd4-116">Select **Post**.</span></span>

## <a name="approve-an-invoice"></a><span data-ttu-id="95cd4-117">Zatwierdzanie faktury</span><span class="sxs-lookup"><span data-stu-id="95cd4-117">Approve an invoice</span></span>
1. <span data-ttu-id="95cd4-118">W okienku nawigacji przejdź do **Moduły > Rozrachunki z dostawcami > Faktury > Zatwierdzenie faktury**.</span><span class="sxs-lookup"><span data-stu-id="95cd4-118">In the navigation pane, go to **Modules > Accounts payable > Invoices > Invoice approval**.</span></span>
2. <span data-ttu-id="95cd4-119">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="95cd4-119">Select **New**.</span></span>
3. <span data-ttu-id="95cd4-120">Wybierz nazwę arkusza zatwierdzania faktur, którego chcesz używać.</span><span class="sxs-lookup"><span data-stu-id="95cd4-120">Select the name of the invoice approval journal that you want to use.</span></span>
4. <span data-ttu-id="95cd4-121">Wybierz **Wiersze**, a zostanie wyświetlona strona, gdzie będzie można wybrać faktury do zatwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="95cd4-121">Select **Lines** to display a page where you will be able to select the invoices that you want to approve.</span></span>
5. <span data-ttu-id="95cd4-122">Kliknij przycisk **Znajdź załączniki**, aby wyświetlić wszystkie faktury gotowe do zatwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="95cd4-122">Select **Find Vouchers** to display all of the invoices that are ready for approval.</span></span>
6. <span data-ttu-id="95cd4-123">Zaznacz utworzoną fakturę, a następnie kliknij przycisk **Wybierz**.</span><span class="sxs-lookup"><span data-stu-id="95cd4-123">Mark the invoice that you created, then click **Select**.</span></span> <span data-ttu-id="95cd4-124">Załączniki wybrane powyżej zostaną po zaznaczeniu przeniesione do tej listy.</span><span class="sxs-lookup"><span data-stu-id="95cd4-124">The vouchers that you selected above are moved to this list after you select them.</span></span>  
7. <span data-ttu-id="95cd4-125">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="95cd4-125">Select **OK**.</span></span>
8. <span data-ttu-id="95cd4-126">Wybierz **Numer konta**, aby dodać konto wydatków do faktury.</span><span class="sxs-lookup"><span data-stu-id="95cd4-126">Select the **account number** field to add an expense account to the invoice.</span></span>
9. <span data-ttu-id="95cd4-127">Wprowadź numer konta i opuść to pole.</span><span class="sxs-lookup"><span data-stu-id="95cd4-127">Enter an account number and tab off of the field.</span></span> <span data-ttu-id="95cd4-128">Na przykład wpisz `600120`.</span><span class="sxs-lookup"><span data-stu-id="95cd4-128">For example, enter `600120`.</span></span>
10. <span data-ttu-id="95cd4-129">Wybierz opcję **Zaksięguj**.</span><span class="sxs-lookup"><span data-stu-id="95cd4-129">Select **Post**.</span></span>
11. <span data-ttu-id="95cd4-130">Wybierz **Załącznik**, aby wyświetlić zapisy, które zostały zaksięgowane.</span><span class="sxs-lookup"><span data-stu-id="95cd4-130">Select **Voucher** to view the entries that were posted.</span></span> <span data-ttu-id="95cd4-131">Konto faktur oczekujących na zatwierdzenie zostanie wycofane i zastąpione kontem wydatków rzeczywistych.</span><span class="sxs-lookup"><span data-stu-id="95cd4-131">The Invoice Pending Approval account is reversed and replaced with the actual expense account.</span></span>  

