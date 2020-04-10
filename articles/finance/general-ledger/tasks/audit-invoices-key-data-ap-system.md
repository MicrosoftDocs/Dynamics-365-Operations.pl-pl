---
title: Wykonywanie audytu faktur i najważniejszych danych w systemie rozrachunków z dostawcami
description: Po otrzymaniu od dostawcy faktury za towary lub usługi na zamówieniu zakupu w procesach biznesowych firmy może być wymagane, aby towary lub usługi zostały dostarczone przed zatwierdzeniem płatności za fakturę.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, PurchEditLines, VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog,  VendJournalMatch_PackingSlip, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6e1af0dac107be6009eb3ca576c49ac5abbd9848
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3139951"
---
# <a name="audit-invoices-and-key-data-in-ap-system"></a><span data-ttu-id="db6a6-103">Wykonywanie audytu faktur i najważniejszych danych w systemie rozrachunków z dostawcami</span><span class="sxs-lookup"><span data-stu-id="db6a6-103">Audit invoices and key data in AP system</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="db6a6-104">Po otrzymaniu od dostawcy faktury za towary lub usługi na zamówieniu zakupu w procesach biznesowych firmy może być wymagane, aby towary lub usługi zostały dostarczone przed zatwierdzeniem płatności za fakturę.</span><span class="sxs-lookup"><span data-stu-id="db6a6-104">When you receive an invoice from a vendor for goods or services on a purchase order, the business processes might require that the goods or services be received before the invoice can be approved for payment.</span></span> <span data-ttu-id="db6a6-105">Zanim rozpoczniesz, upewnij się, że wybrano klucz konfiguracji Uzgadnianie faktur.</span><span class="sxs-lookup"><span data-stu-id="db6a6-105">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span> 

<span data-ttu-id="db6a6-106">Na stronie Parametry modułu rozrachunków z dostawcami upewnij się, że zaznaczono opcję Włącz weryfikację uzgadniania faktur, w polu Księguj fakturę z rozbieżnościami zaznaczono opcję Wymagaj zatwierdzania, a pole Zasady uzgadniania wierszy ma wartość Uzgadnianie trzyelementowe.</span><span class="sxs-lookup"><span data-stu-id="db6a6-106">In the Accounts payable parameters page, ensure that the Enable invoice matching validation option is selected, the Post invoice with discrepancies field is set to Require approval, and the Line matching policy field is set to Three-way matching.</span></span>

<span data-ttu-id="db6a6-107">Ta procedura wykorzystuje firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="db6a6-107">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="db6a6-108">Czynności te wykonuje menedżer ds. rozrachunków z dostawcami lub menedżer księgowości.</span><span class="sxs-lookup"><span data-stu-id="db6a6-108">The accounts payable manager or accounting manager role would perform these steps.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="db6a6-109">Tworzenie zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="db6a6-109">Create a purchase order</span></span>
1. <span data-ttu-id="db6a6-110">Przejdź do okna **Wszystkie zamówienia zakupu.**</span><span class="sxs-lookup"><span data-stu-id="db6a6-110">Go to **All purchase orders**.</span></span>
2. <span data-ttu-id="db6a6-111">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="db6a6-111">Click **New**.</span></span>
3. <span data-ttu-id="db6a6-112">W polu **Konto dostawcy** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="db6a6-112">In the **Vendor account** field, type a value.</span></span>
4. <span data-ttu-id="db6a6-113">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="db6a6-113">Click **OK**.</span></span>
5. <span data-ttu-id="db6a6-114">Kliknij przycisk **Dodaj wiersz.**</span><span class="sxs-lookup"><span data-stu-id="db6a6-114">Click **Add line**.</span></span>
6. <span data-ttu-id="db6a6-115">W polu **Numer towaru** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="db6a6-115">In the **Item number** field, type a value.</span></span>
7. <span data-ttu-id="db6a6-116">W okienku akcji kliknij pozycję **Zakup.**</span><span class="sxs-lookup"><span data-stu-id="db6a6-116">On the Action Pane, click **Purchase**.</span></span>
8. <span data-ttu-id="db6a6-117">Kliknij przycisk **Potwierdź**.</span><span class="sxs-lookup"><span data-stu-id="db6a6-117">Click **Confirm**.</span></span>

## <a name="post-a-product-receipt"></a><span data-ttu-id="db6a6-118">Księgowanie dokumentu przyjęcia produktów</span><span class="sxs-lookup"><span data-stu-id="db6a6-118">Post a product receipt</span></span>
1. <span data-ttu-id="db6a6-119">W okienku akcji kliknij pozycję **Odbierz.**</span><span class="sxs-lookup"><span data-stu-id="db6a6-119">On the Action Pane, click **Receive**.</span></span>
2. <span data-ttu-id="db6a6-120">Kliknij opcję **Dokument przyjęcia produktów.**</span><span class="sxs-lookup"><span data-stu-id="db6a6-120">Click **Product receipt**.</span></span>
3. <span data-ttu-id="db6a6-121">W polu **Dokument przyjęcia produktów** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="db6a6-121">In the **Product receipt** field, type a value.</span></span>
4. <span data-ttu-id="db6a6-122">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="db6a6-122">Click **OK**.</span></span>

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a><span data-ttu-id="db6a6-123">Rejestrowanie i uzgadnianie faktury od dostawcy z dokumentem przyjęcia produktów</span><span class="sxs-lookup"><span data-stu-id="db6a6-123">Record and match a vendor invoice to a product receipt</span></span>
1. <span data-ttu-id="db6a6-124">W okienku akcji kliknij pozycję **Faktura > Faktura**.</span><span class="sxs-lookup"><span data-stu-id="db6a6-124">On the Action Pane, click **Invoice > Invoice**.</span></span>
2. <span data-ttu-id="db6a6-125">W polu **Numer** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="db6a6-125">In the **Number** field, type a value.</span></span>
3. <span data-ttu-id="db6a6-126">Na liście **Domyślnie z zaznacz opcję Zamówiona ilość**, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="db6a6-126">Click **Default from: Ordered quantity** to open the drop dialog.</span></span>
4. <span data-ttu-id="db6a6-127">W polu **Domyślna ilość dla wierszy** zaznacz opcję.</span><span class="sxs-lookup"><span data-stu-id="db6a6-127">In the **Default quantity for lines** field, select an option.</span></span>
5. <span data-ttu-id="db6a6-128">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="db6a6-128">Click **OK**.</span></span>
6. <span data-ttu-id="db6a6-129">Kliknij przycisk **Tak**.</span><span class="sxs-lookup"><span data-stu-id="db6a6-129">Click **Yes**.</span></span>
7. <span data-ttu-id="db6a6-130">Kliknij opcję **Dopasuj dokumenty przyjęcia produktów**.</span><span class="sxs-lookup"><span data-stu-id="db6a6-130">Click **Match product receipts**.</span></span>
8. <span data-ttu-id="db6a6-131">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="db6a6-131">Click **OK**.</span></span>
9. <span data-ttu-id="db6a6-132">W okienku akcji kliknij pozycję **Przegląd**.</span><span class="sxs-lookup"><span data-stu-id="db6a6-132">On the Action Pane, click **Review**.</span></span>
10. <span data-ttu-id="db6a6-133">Kliknij przycisk **Szczegóły uzgadniania**.</span><span class="sxs-lookup"><span data-stu-id="db6a6-133">Click **Matching details**.</span></span>

