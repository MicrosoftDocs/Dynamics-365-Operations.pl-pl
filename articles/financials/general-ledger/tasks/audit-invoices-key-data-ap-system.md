--- 
title: "Wykonywanie audytu faktur i najważniejszych danych w module rozrachunków z dostawcami"
description: "Po otrzymaniu od dostawcy faktury za towary lub usługi na zamówieniu zakupu w procesach biznesowych firmy może być wymagane, aby towary lub usługi zostały dostarczone przed zatwierdzeniem płatności za fakturę."
author: saraschi2
manager: AnnBe
ms.date: 02/16/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: c928edee086835479ab6d150b1dd86df1824226f
ms.contentlocale: pl-pl
ms.lasthandoff: 08/07/2018

---
# <a name="audit-invoices-and-key-data-in-accounts-payable"></a><span data-ttu-id="36afc-103">Wykonywanie audytu faktur i najważniejszych danych w module rozrachunków z dostawcami</span><span class="sxs-lookup"><span data-stu-id="36afc-103">Audit invoices and key data in accounts payable</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="36afc-104">Po otrzymaniu od dostawcy faktury za towary lub usługi na zamówieniu zakupu w procesach biznesowych firmy może być wymagane, aby towary lub usługi zostały dostarczone przed zatwierdzeniem płatności za fakturę.</span><span class="sxs-lookup"><span data-stu-id="36afc-104">When you receive an invoice from a vendor for goods or services on a purchase order, the business processes might require that the goods or services be received before the invoice can be approved for payment.</span></span> <span data-ttu-id="36afc-105">Zanim rozpoczniesz, upewnij się, że wybrano klucz konfiguracji Uzgadnianie faktur.</span><span class="sxs-lookup"><span data-stu-id="36afc-105">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span> 

<span data-ttu-id="36afc-106">Na stronie Parametry modułu rozrachunków z dostawcami upewnij się, że zaznaczono opcję Włącz weryfikację uzgadniania faktur, w polu Księguj fakturę z rozbieżnościami zaznaczono opcję Wymagaj zatwierdzania, a pole Zasady uzgadniania wierszy ma wartość Uzgadnianie trzyelementowe.</span><span class="sxs-lookup"><span data-stu-id="36afc-106">In the Accounts payable parameters page, ensure that the Enable invoice matching validation option is selected, the Post invoice with discrepancies field is set to Require approval, and the Line matching policy field is set to Three-way matching.</span></span>

<span data-ttu-id="36afc-107">Ta procedura wykorzystuje firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="36afc-107">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="36afc-108">Czynności te wykonuje menedżer ds. rozrachunków z dostawcami lub menedżer księgowości.</span><span class="sxs-lookup"><span data-stu-id="36afc-108">The accounts payable manager or accounting manager role would perform these steps.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="36afc-109">Tworzenie zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="36afc-109">Create a purchase order</span></span>
1. <span data-ttu-id="36afc-110">Przejdź do okna Wszystkie zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="36afc-110">Go to All purchase orders.</span></span>
2. <span data-ttu-id="36afc-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="36afc-111">Click New.</span></span>
3. <span data-ttu-id="36afc-112">W polu Konto dostawcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="36afc-112">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="36afc-113">W polu Konto dostawcy wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="36afc-113">In the Vendor account field, type a value.</span></span>
5. <span data-ttu-id="36afc-114">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="36afc-114">Click OK.</span></span>
6. <span data-ttu-id="36afc-115">Kliknij przycisk Dodaj wiersz.</span><span class="sxs-lookup"><span data-stu-id="36afc-115">Click Add line.</span></span>
7. <span data-ttu-id="36afc-116">W polu Numer towaru wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="36afc-116">In the Item number field, type a value.</span></span>
8. <span data-ttu-id="36afc-117">W okienku akcji kliknij pozycję Zakup.</span><span class="sxs-lookup"><span data-stu-id="36afc-117">On the Action Pane, click Purchase.</span></span>
9. <span data-ttu-id="36afc-118">Kliknij przycisk Potwierdź.</span><span class="sxs-lookup"><span data-stu-id="36afc-118">Click Confirm.</span></span>

## <a name="post-a-product-receipt"></a><span data-ttu-id="36afc-119">Księgowanie dokumentu przyjęcia produktów</span><span class="sxs-lookup"><span data-stu-id="36afc-119">Post a product receipt</span></span>
1. <span data-ttu-id="36afc-120">W okienku akcji kliknij pozycję Odbierz.</span><span class="sxs-lookup"><span data-stu-id="36afc-120">On the Action Pane, click Receive.</span></span>
2. <span data-ttu-id="36afc-121">Kliknij opcję Dokument przyjęcia produktów.</span><span class="sxs-lookup"><span data-stu-id="36afc-121">Click Product receipt.</span></span>
3. <span data-ttu-id="36afc-122">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="36afc-122">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="36afc-123">W polu Dokument przyjęcia produktów wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="36afc-123">In the Product receipt field, type a value.</span></span>
5. <span data-ttu-id="36afc-124">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="36afc-124">Click OK.</span></span>

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a><span data-ttu-id="36afc-125">Rejestrowanie i uzgadnianie faktury od dostawcy z dokumentem przyjęcia produktów</span><span class="sxs-lookup"><span data-stu-id="36afc-125">Record and match a vendor invoice to a product receipt</span></span>
1. <span data-ttu-id="36afc-126">W okienku akcji kliknij pozycję Faktura.</span><span class="sxs-lookup"><span data-stu-id="36afc-126">On the Action Pane, click Invoice.</span></span>
2. <span data-ttu-id="36afc-127">Kliknij opcję Faktura.</span><span class="sxs-lookup"><span data-stu-id="36afc-127">Click Invoice.</span></span>
3. <span data-ttu-id="36afc-128">W polu Numer wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="36afc-128">In the Number field, type a value.</span></span>
4. <span data-ttu-id="36afc-129">Na liście Domyślnie z zaznacz opcję Zamówiona ilość, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="36afc-129">Click Default from: Ordered quantity to open the drop dialog.</span></span>
5. <span data-ttu-id="36afc-130">W polu Domyślna ilość dla wierszy zaznacz opcję.</span><span class="sxs-lookup"><span data-stu-id="36afc-130">In the Default quantity for lines field, select an option.</span></span>
6. <span data-ttu-id="36afc-131">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="36afc-131">Click OK.</span></span>
7. <span data-ttu-id="36afc-132">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="36afc-132">Click Yes.</span></span>
8. <span data-ttu-id="36afc-133">Kliknij opcję Dopasuj dokumenty przyjęcia produktów.</span><span class="sxs-lookup"><span data-stu-id="36afc-133">Click Match product receipts.</span></span>
9. <span data-ttu-id="36afc-134">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="36afc-134">Click OK.</span></span>
10. <span data-ttu-id="36afc-135">W okienku akcji kliknij pozycję Przegląd.</span><span class="sxs-lookup"><span data-stu-id="36afc-135">On the Action Pane, click Review.</span></span>
11. <span data-ttu-id="36afc-136">Kliknij przycisk Szczegóły uzgadniania.</span><span class="sxs-lookup"><span data-stu-id="36afc-136">Click Matching details.</span></span>


