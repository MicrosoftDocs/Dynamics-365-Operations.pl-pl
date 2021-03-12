---
title: Rejestrowanie faktury od dostawcy w arkuszu faktur
description: W tym przewodniku po zadaniach pokazano sposób rejestrowania faktur dostawców, które nie są powiązane z zamówieniami zakupu.
author: abruer
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendInvoiceWorkspace, LedgerJournalTable, LedgerJournalTransVendInvoice
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 18d8b74bd8783c23e548a3185414d1461bc1d869
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971835"
---
# <a name="record-a-vendor-invoice-in-the-invoice-journal"></a><span data-ttu-id="3eb46-103">Rejestrowanie faktury od dostawcy w arkuszu faktur</span><span class="sxs-lookup"><span data-stu-id="3eb46-103">Record a vendor invoice in the invoice journal</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3eb46-104">W tym przewodniku po zadaniach pokazano sposób rejestrowania faktur dostawców, które nie są powiązane z zamówieniami zakupu.</span><span class="sxs-lookup"><span data-stu-id="3eb46-104">This task guide will show how to record vendor invoices that are not associated with purchase orders.</span></span> <span data-ttu-id="3eb46-105">Przykładami tego rodzaju faktur są faktury za wydatki na materiały eksploatacyjne lub usługi.</span><span class="sxs-lookup"><span data-stu-id="3eb46-105">Examples of this type of invoice include expenses for supplies or services.</span></span>  <span data-ttu-id="3eb46-106">To nagranie wykorzystuje firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="3eb46-106">This recording uses the USMF demo company.</span></span>

1. <span data-ttu-id="3eb46-107">Przejdź do **Okienko nawigacji > Moduły > Rozrachunki z dostawcami > Obszary robocze > Wprowadzanie faktur od dostawcy**.</span><span class="sxs-lookup"><span data-stu-id="3eb46-107">Go to **Navigation pane > Modules > Accounts payable > Workspaces > Vendor invoice entry**.</span></span>
2. <span data-ttu-id="3eb46-108">W **Okienku akcji** kliknij **Nowy arkusz faktur**.</span><span class="sxs-lookup"><span data-stu-id="3eb46-108">On the **Action pane**, click **New invoice journal**.</span></span>
3. <span data-ttu-id="3eb46-109">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="3eb46-109">Click **New**.</span></span>
4. <span data-ttu-id="3eb46-110">W polu **Nazwa** nadaj arkuszowi nazwę lub kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="3eb46-110">In the **Name** field, enter the journal name or click the drop down button to open the lookup.</span></span>
5. <span data-ttu-id="3eb46-111">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3eb46-111">In the **Description** field, type a value.</span></span>
6. <span data-ttu-id="3eb46-112">W **okienku akcji** kliknij pozycję **Wiersze**.</span><span class="sxs-lookup"><span data-stu-id="3eb46-112">On the **Action pane**, click **Lines**.</span></span> <span data-ttu-id="3eb46-113">W polu **Data** wprowadź datę księgowania, która spowoduje aktualizację Księgi głównej.</span><span class="sxs-lookup"><span data-stu-id="3eb46-113">In the **Date** field, enter the posting date that will update General Ledger.</span></span>  
7. <span data-ttu-id="3eb46-114">W polu **Konto** określ **konto dostawcy**.</span><span class="sxs-lookup"><span data-stu-id="3eb46-114">In the **Account** field, specify the **Vendor account**.</span></span>
8. <span data-ttu-id="3eb46-115">W polu **Faktura** wprowadź numer faktury.</span><span class="sxs-lookup"><span data-stu-id="3eb46-115">In the **Invoice** field, enter the invoice number.</span></span>
9. <span data-ttu-id="3eb46-116">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3eb46-116">In the **Description** field, type a value.</span></span>
10. <span data-ttu-id="3eb46-117">W polu **Kredyt** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="3eb46-117">In the **Credit** field, enter a number.</span></span>
11. <span data-ttu-id="3eb46-118">W polu **Konto przeciwstawne** wpisz numer konta lub kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="3eb46-118">In the **Offset account** field, enter the account number or click the drop down button to open the lookup</span></span>
    * <span data-ttu-id="3eb46-119">Wartość pola **Grupa podatków** zostanie pobrana domyślnie z ustawień konta dostawcy.</span><span class="sxs-lookup"><span data-stu-id="3eb46-119">The **Sales tax group** will be default from the vendor account.</span></span>  
    * <span data-ttu-id="3eb46-120">Wartość pola **Grupa podatków** dla towaru jest pobierana z ustawień konta głównego określonego w polu **Konto przeciwstawne**.</span><span class="sxs-lookup"><span data-stu-id="3eb46-120">The **Item sales tax group** will be default from the main account specified in the **Offset account** field.</span></span>  
    * <span data-ttu-id="3eb46-121">**Termin płatności** zostanie obliczony na podstawie warunków płatności.</span><span class="sxs-lookup"><span data-stu-id="3eb46-121">The **Due date** will be calculated based on the Terms of payment.</span></span>  
    * <span data-ttu-id="3eb46-122">Wartość pola **Rabat gotówkowy** zostanie pobrana domyślnie z ustawień konta dostawcy.</span><span class="sxs-lookup"><span data-stu-id="3eb46-122">The **Cash discount** will default from the Vendor account.</span></span>
12. <span data-ttu-id="3eb46-123">Jeśli włączono przepływ pracy Arkusz faktur od dostawców, kliknij kolejno opcje **Przepływ pracy > Prześlij**.</span><span class="sxs-lookup"><span data-stu-id="3eb46-123">If you have enabled Vendor invoice journal workflow, click **Workflow > Submit**.</span></span>
    * <span data-ttu-id="3eb46-124">Po zatwierdzeniu przesłanych informacji data zostanie przeniesiona do pierwszego dnia następnego otwartego okresu, jeśli data księgowania transakcji przypada w okresie wstrzymania lub zamknięcia księgowania w księdze.</span><span class="sxs-lookup"><span data-stu-id="3eb46-124">When your submission is approved, the date will be advanced to the first day of the next open period, if the transaction posting date falls within a period that is On hold or Closed for ledger posting.</span></span>
12. <span data-ttu-id="3eb46-125">Kliknij przycisk **Księguj**.</span><span class="sxs-lookup"><span data-stu-id="3eb46-125">Click **Post**.</span></span>
13. <span data-ttu-id="3eb46-126">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3eb46-126">Close the page.</span></span>

