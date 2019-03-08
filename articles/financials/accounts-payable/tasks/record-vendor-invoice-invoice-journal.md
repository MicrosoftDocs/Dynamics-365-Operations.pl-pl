---
title: Rejestrowanie faktury od dostawcy w arkuszu faktur
description: W tym przewodniku po zadaniach pokazano sposób rejestrowania faktur dostawców, które nie są powiązane z zamówieniami zakupu.
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendInvoiceWorkspace, LedgerJournalTable, LedgerJournalTransVendInvoice
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 775f3764d34cecbfc071ff7420d32c7832b42308
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "348947"
---
# <a name="record-a-vendor-invoice-in-the-invoice-journal"></a><span data-ttu-id="c02b2-103">Rejestrowanie faktury od dostawcy w arkuszu faktur</span><span class="sxs-lookup"><span data-stu-id="c02b2-103">Record a vendor invoice in the invoice journal</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c02b2-104">W tym przewodniku po zadaniach pokazano sposób rejestrowania faktur dostawców, które nie są powiązane z zamówieniami zakupu.</span><span class="sxs-lookup"><span data-stu-id="c02b2-104">This task guide will show how to record vendor invoices that are not associated with purchase orders.</span></span> <span data-ttu-id="c02b2-105">Przykładami tego rodzaju faktur są faktury za wydatki na materiały eksploatacyjne lub usługi.</span><span class="sxs-lookup"><span data-stu-id="c02b2-105">Examples of this type of invoice include expenses for supplies or services.</span></span>  <span data-ttu-id="c02b2-106">To nagranie wykorzystuje firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="c02b2-106">This recording uses the USMF demo company.</span></span>

1. <span data-ttu-id="c02b2-107">Wybierz kolejno opcje Rozrachunki z dostawcami > Obszary robocze > Wprowadzanie faktur od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="c02b2-107">Go to Accounts payable > Workspaces > Vendor invoice entry.</span></span>
2. <span data-ttu-id="c02b2-108">Kliknij opcję Nowy arkusz faktur.</span><span class="sxs-lookup"><span data-stu-id="c02b2-108">Click New invoice journal.</span></span>
3. <span data-ttu-id="c02b2-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="c02b2-109">Click New.</span></span>
4. <span data-ttu-id="c02b2-110">W polu Nazwa nadaj arkuszowi nazwę lub kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="c02b2-110">In the Name field, enter the journal name or click the drop down button to open the lookup.</span></span>
5. <span data-ttu-id="c02b2-111">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="c02b2-111">In the Description field, type a value.</span></span>
6. <span data-ttu-id="c02b2-112">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="c02b2-112">Click Lines.</span></span>
    * <span data-ttu-id="c02b2-113">W polu Data wprowadź datę księgowania, która spowoduje aktualizację Księgi głównej.</span><span class="sxs-lookup"><span data-stu-id="c02b2-113">In the Date field, enter the posting date that will update General Ledger.</span></span>  
7. <span data-ttu-id="c02b2-114">W polu Konto podaj konto dostawcy.</span><span class="sxs-lookup"><span data-stu-id="c02b2-114">In the Account field, specify the Vendor account.</span></span>
8. <span data-ttu-id="c02b2-115">W polu Faktura wprowadź numer faktury.</span><span class="sxs-lookup"><span data-stu-id="c02b2-115">In the Invoice field, enter the invoice number.</span></span>
9. <span data-ttu-id="c02b2-116">W polu Opis wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c02b2-116">In the Description field, type a value.</span></span>
10. <span data-ttu-id="c02b2-117">W polu Kredyt wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="c02b2-117">In the Credit field, enter a number.</span></span>
11. <span data-ttu-id="c02b2-118">W polu Konto przeciwstawne wpisz numer konta lub kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="c02b2-118">In the Offset account field, enter the account number or click the drop down button to open the lookup</span></span>
    * <span data-ttu-id="c02b2-119">Wartość pola Grupa podatków zostanie pobrana domyślnie z ustawień konta dostawcy.</span><span class="sxs-lookup"><span data-stu-id="c02b2-119">The Sales tax group will default from the vendor account.</span></span>  
    * <span data-ttu-id="c02b2-120">Wartość pola Grupa podatków dla towaru jest pobierana z ustawień konta głównego określonego w polu Konto przeciwstawne.</span><span class="sxs-lookup"><span data-stu-id="c02b2-120">The Item sales tax group will default from the main account specified in the Offset account field.</span></span>  
    * <span data-ttu-id="c02b2-121">Termin płatności zostanie obliczony na podstawie warunków płatności.</span><span class="sxs-lookup"><span data-stu-id="c02b2-121">The Due date will be calculated based on the Terms of payment.</span></span>  
    * <span data-ttu-id="c02b2-122">Wartość pola Rabat gotówkowy zostanie pobrana domyślnie z ustawień konta dostawcy.</span><span class="sxs-lookup"><span data-stu-id="c02b2-122">The Cash discount will default from the Vendor account.</span></span>  
12. <span data-ttu-id="c02b2-123">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="c02b2-123">Click Post.</span></span>
13. <span data-ttu-id="c02b2-124">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c02b2-124">Close the page.</span></span>

