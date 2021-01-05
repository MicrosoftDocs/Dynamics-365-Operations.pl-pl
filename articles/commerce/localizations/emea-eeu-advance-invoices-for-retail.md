---
title: Faktury zaliczkowe w rozwiązaniu Commerce dla Europy Wschodniej
description: W tym temacie opisano, jak skonfigurować faktury zaliczkowe w aplikacji Commerce dla Europy Wschodniej.
author: epopov
manager: annbe
ms.date: 10/23/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Retail, Operations
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.search.industry: Retail
ms.author: v-kikozl
ms.search.validFrom: 2018-10-01
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: fc2af93880b634e6cec0015a2469fb8e4e56a7d7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4408364"
---
# <a name="advance-invoices-for-commerce-for-eastern-europe"></a><span data-ttu-id="d208a-103">Faktury zaliczkowe w rozwiązaniu Commerce dla Europy Wschodniej</span><span class="sxs-lookup"><span data-stu-id="d208a-103">Advance invoices for Commerce for Eastern Europe</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d208a-104">Informacje zawarte w tym temacie mają zastosowanie do lokalizacji dla Europy Wschodniej i są specyficzne dla branży handlowej.</span><span class="sxs-lookup"><span data-stu-id="d208a-104">The information in this topic applies to the Eastern European localization and is specific to the commerce industry.</span></span>

<span data-ttu-id="d208a-105">W Polsce, na Węgrzech i w Czechach po otrzymaniu od klienta przedpłaty za pośrednictwem aplikacji punktu sprzedaży (POS) przedpłatę należy zarejestrować do celów podatkowych, a także należy wygenerować i wydrukować dokument faktury zaliczkowej zawierający kwotę przedpłaty.</span><span class="sxs-lookup"><span data-stu-id="d208a-105">For Poland, Hungary, and Czech Republic, when a prepayment is received from a customer via Point of Sale (POS), the prepayment must be registered for tax purposes, and it's required to generate and print an advance invoice document that includes the prepayment amount.</span></span> <span data-ttu-id="d208a-106">Ponadto w Polsce transakcje faktur zaliczkowych muszą być księgowane w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="d208a-106">Additionally, for Poland, advance invoice transactions must be posted in the general ledger.</span></span>

<span data-ttu-id="d208a-107">Gdy faktura za zamówienie sprzedaży jest finalnie księgowana, ostateczny dokument powinien uwzględniać dane faktury zaliczkowej z oznaczeniem wszelkich przedpłat.</span><span class="sxs-lookup"><span data-stu-id="d208a-107">When the invoice for the sales order is finally posted, the final document should include the advance invoice, and any prepayments should be indicated.</span></span>

<span data-ttu-id="d208a-108">Jeśli generujesz zamówienia sprzedaży z modułu Rozrachunki z odbiorcami, należy ręcznie wygenerować faktury zaliczkowe przy użyciu procedury opisanej w temacie [Faktury zaliczkowe dla Europy Wschodniej](https://docs.microsoft.com/dynamics365/unified-operations/financials/localizations/emea-advance-invoice).</span><span class="sxs-lookup"><span data-stu-id="d208a-108">If you generate sales orders from Accounts receivable, you must manually generate advance invoices by using the procedure in [Advance invoices for Eastern Europe](https://docs.microsoft.com/dynamics365/unified-operations/financials/localizations/emea-advance-invoice).</span></span> <span data-ttu-id="d208a-109">Jeśli generujesz zamówienia sprzedaży z aplikacji POS, system automatycznie wygeneruje i zaksięguje faktury zaliczkowe.</span><span class="sxs-lookup"><span data-stu-id="d208a-109">If you generate sales orders via POS, the system generates and posts the advance invoices for you.</span></span>

## <a name="supported-scenarios"></a><span data-ttu-id="d208a-110">Obsługiwane scenariusze</span><span class="sxs-lookup"><span data-stu-id="d208a-110">Supported scenarios</span></span>

<span data-ttu-id="d208a-111">Obsługiwane są następujące scenariusze:</span><span class="sxs-lookup"><span data-stu-id="d208a-111">The following scenarios are supported:</span></span>

- <span data-ttu-id="d208a-112">Tworzenie i księgowanie faktury zaliczkowej.</span><span class="sxs-lookup"><span data-stu-id="d208a-112">Create and post an advance invoice.</span></span>
- <span data-ttu-id="d208a-113">Modyfikowanie kwoty wpłaty.</span><span class="sxs-lookup"><span data-stu-id="d208a-113">Modify a deposit amount.</span></span> <span data-ttu-id="d208a-114">Jeżeli odbiorca postanowi zwiększyć kwotę wpłaty, zostanie wystawiona dodatkowa faktura zaliczkowa.</span><span class="sxs-lookup"><span data-stu-id="d208a-114">If a customer decides to increase the amount of a deposit, an additional advance invoice is issued.</span></span> <span data-ttu-id="d208a-115">W przypadku wszystkich innych zmian kwoty wpłaty (na przykład w przypadku modyfikacji zamówienia odbiorcy) zostanie utworzona faktura korygująca do wygenerowanej wcześniej faktury zaliczkowej, a następnie zostanie utworzona i zaksięgowana nowa faktura zaliczkowa na skorygowaną kwotę.</span><span class="sxs-lookup"><span data-stu-id="d208a-115">For all other changes to the deposit amount (for example, if a customer order is edited), a credit note is created for the advance invoice that was previously generated, and a new advance invoice is generated and posted for the corrected amount.</span></span>
- <span data-ttu-id="d208a-116">Anulowanie zamówienia sprzedaży mającego połączone faktury zaliczkowe.</span><span class="sxs-lookup"><span data-stu-id="d208a-116">Cancel a sales order that has linked advance invoices.</span></span> <span data-ttu-id="d208a-117">W takim przypadku jest tworzona faktura korygująca do faktury zaliczkowej.</span><span class="sxs-lookup"><span data-stu-id="d208a-117">In this case, a credit note is created for the advance invoice.</span></span>
- <span data-ttu-id="d208a-118">Zaksięgowanie faktury za zamówienie sprzedaży mającej połączone faktury zaliczkowe.</span><span class="sxs-lookup"><span data-stu-id="d208a-118">Post a sales order invoice that has linked advance invoices.</span></span> <span data-ttu-id="d208a-119">Faktura zaliczkowa połączona z zamówieniem sprzedaży jest stornowana na kwotę faktury sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="d208a-119">The advance invoice that is linked to a sales order is reversed for the amount of the sales invoice.</span></span> <span data-ttu-id="d208a-120">Transakcje faktur zaliczkowych są rozliczane za pomocą transakcji wycofania faktur zaliczkowych.</span><span class="sxs-lookup"><span data-stu-id="d208a-120">The advance invoice transactions are settled with advance invoice reversal transactions.</span></span>

## <a name="set-up-advance-invoices"></a><span data-ttu-id="d208a-121">Konfigurowanie faktur zaliczkowych</span><span class="sxs-lookup"><span data-stu-id="d208a-121">Set up advance invoices</span></span>

### <a name="turn-on-the-functionality-for-creating-advance-invoices"></a><span data-ttu-id="d208a-122">Włączanie funkcjonalności tworzenia faktur zaliczkowych</span><span class="sxs-lookup"><span data-stu-id="d208a-122">Turn on the functionality for creating advance invoices</span></span>

1. <span data-ttu-id="d208a-123">Wybierz kolejno opcje **Commerce \> Ustawienia central \> Parametry \> Parametry Commerce**.</span><span class="sxs-lookup"><span data-stu-id="d208a-123">Go to **Retail and Commerce \> Headquarters setup \> Parameters \> Commerce parameters**.</span></span>
2. <span data-ttu-id="d208a-124">Na karcie **Zamówienia odbiorców** na skróconej karcie **Zamówienie** ustaw opcję **Utwórz fakturę zaliczkową dla wpłaty** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="d208a-124">On the **Customer orders** tab, on the **Order** FastTab, set the **Create advance invoice for deposit** option to **Yes**.</span></span>

### <a name="define-the-parameters-for-posting-advance-invoices"></a><span data-ttu-id="d208a-125">Definiowanie parametrów księgowania faktur zaliczkowych</span><span class="sxs-lookup"><span data-stu-id="d208a-125">Define the parameters for posting advance invoices</span></span>

1. <span data-ttu-id="d208a-126">Wybierz kolejno pozycje **Rozrachunki z odbiorcami \> Ustawienia \> Parametry modułu rozrachunków z odbiorcami**.</span><span class="sxs-lookup"><span data-stu-id="d208a-126">Go to **Accounts receivable \> Setup \> Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="d208a-127">Na karcie **Aktualizacje** na skróconej karcie **Faktura zaliczkowa** ustaw wartości w polach **Profil księgowania**, **Grupa podatków** i **Grupa podatków dla pozycji**.</span><span class="sxs-lookup"><span data-stu-id="d208a-127">On the **Updates** tab, on the **Advance invoice** FastTab, set the **Posting profile**, **Sales tax group**, and **Item sales tax group** fields.</span></span> <span data-ttu-id="d208a-128">Jeśli te pola są ustawione poprawnie, faktura zaliczkowa zostanie zaksięgowana.</span><span class="sxs-lookup"><span data-stu-id="d208a-128">If these fields are set correctly, the advance invoice will be posted.</span></span> <span data-ttu-id="d208a-129">Jeśli te pola nie są ustawione, faktury zaliczkowe nie będą księgowane.</span><span class="sxs-lookup"><span data-stu-id="d208a-129">If these fields aren't set, advance invoices won't be posted.</span></span>

### <a name="turn-off-posting-of-the-sales-tax-on-prepayment-journal-voucher"></a><span data-ttu-id="d208a-130">Wyłączanie księgowania podatku z załącznika arkusza zaliczki</span><span class="sxs-lookup"><span data-stu-id="d208a-130">Turn off posting of the Sales tax on prepayment journal voucher</span></span>

<span data-ttu-id="d208a-131">Podatek figurujący w załączniku arkusza zaliczki nie może być księgowany, jeśli jest włączona funkcja księgowania faktur zaliczkowych.</span><span class="sxs-lookup"><span data-stu-id="d208a-131">The Sales tax on prepayment journal voucher must not be posted if advance invoice posting is turned on.</span></span> <span data-ttu-id="d208a-132">Aby sprawdzić, czy ten wymóg jest spełniony, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="d208a-132">To verify that this requirement is met, follow these steps.</span></span>

1. <span data-ttu-id="d208a-133">Wybierz kolejno pozycje **Rozrachunki z odbiorcami \> Ustawienia \> Parametry modułu rozrachunków z odbiorcami**.</span><span class="sxs-lookup"><span data-stu-id="d208a-133">Go to **Accounts receivable \> Setup \> Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="d208a-134">Na karcie **Księga i podatek** na skróconej karcie **Płatność** upewnij się, że następujące pola są puste lub zawierają wartość **Nie**:</span><span class="sxs-lookup"><span data-stu-id="d208a-134">On the **Ledger and sales tax** tab, on the **Payment** FastTab, make sure that the following fields are blank or set to **No**:</span></span>

    - <span data-ttu-id="d208a-135">Podatek w załączniku arkusza zaliczki</span><span class="sxs-lookup"><span data-stu-id="d208a-135">Sales tax on prepayment journal voucher</span></span>
    - <span data-ttu-id="d208a-136">Profil księgowania z użyciem załącznika arkusza zaliczki</span><span class="sxs-lookup"><span data-stu-id="d208a-136">Posting profile with prepayment journal voucher</span></span>
    - <span data-ttu-id="d208a-137">Grupa podatku zaliczki</span><span class="sxs-lookup"><span data-stu-id="d208a-137">Tax group for prepayment</span></span>
    - <span data-ttu-id="d208a-138">Grupa podatków dla pozycji</span><span class="sxs-lookup"><span data-stu-id="d208a-138">Item Sales tax group</span></span>

## <a name="print-advance-invoices"></a><span data-ttu-id="d208a-139">Drukowanie faktur zaliczkowych</span><span class="sxs-lookup"><span data-stu-id="d208a-139">Print advance invoices</span></span>

<span data-ttu-id="d208a-140">Faktury zaliczkowe można drukować z aplikacji POS na drukarce systemu Microsoft Windows podłączonej do stacji sprzętowej.</span><span class="sxs-lookup"><span data-stu-id="d208a-140">You can print advance invoices from POS on a Microsoft Windows printer that is connected to the hardware station.</span></span> <span data-ttu-id="d208a-141">Dostępne są dwie opcje drukowania faktury zaliczkowej z aplikacji POS:</span><span class="sxs-lookup"><span data-stu-id="d208a-141">There are two options for printing an advance invoice from POS:</span></span>

- <span data-ttu-id="d208a-142">**Drukowanie faktury zaliczkowej po zawarciu transakcji w aplikacji POS.**</span><span class="sxs-lookup"><span data-stu-id="d208a-142">**Print an advance invoice after a transaction is concluded in POS.**</span></span> <span data-ttu-id="d208a-143">Ta opcja jest uruchamiana automatycznie, jeśli faktura zaliczkowa została wygenerowana, a drukarka systemu Windows jest poprawnie skonfigurowana.</span><span class="sxs-lookup"><span data-stu-id="d208a-143">This option occurs automatically if an advance invoice was generated and a Windows printer was correctly set up.</span></span> <span data-ttu-id="d208a-144">W takim przypadku zostanie wydrukowana tylko ostatnia faktura zaliczkowa połączona z zamówieniem klienta.</span><span class="sxs-lookup"><span data-stu-id="d208a-144">In this case, only the last advance invoice that is linked to the customer order is printed.</span></span>
- <span data-ttu-id="d208a-145">**Ponowne wydrukowanie faktury zaliczkowej z arkusza transakcji.**</span><span class="sxs-lookup"><span data-stu-id="d208a-145">**Reprint an advance invoice from the transaction journal.**</span></span> <span data-ttu-id="d208a-146">Wybierz opcję **Pokaż arkusz**, aby otworzyć arkusz transakcji, znajdź zamówienie odbiorcy, a następnie wybierz opcję **Drukuj fakturę zaliczkową**.</span><span class="sxs-lookup"><span data-stu-id="d208a-146">Select **Show journal** to open the transactions journal, find the customer order, and then select **Print Advance invoice**.</span></span> <span data-ttu-id="d208a-147">W takim przypadku zostaną wydrukowane wszystkie faktury zaliczkowe połączone z zamówieniem klienta.</span><span class="sxs-lookup"><span data-stu-id="d208a-147">In this case, all advance invoices that are linked to the customer order are printed.</span></span>

### <a name="set-up-a-windows-printer"></a><span data-ttu-id="d208a-148">Konfigurowanie drukarki systemu Windows</span><span class="sxs-lookup"><span data-stu-id="d208a-148">Set up a Windows printer</span></span>

<span data-ttu-id="d208a-149">Wykonaj następujące kroki, aby umożliwić drukowanie dokumentów z aplikacji POS na drukarce systemu Windows podłączonej do stacji sprzętowej.</span><span class="sxs-lookup"><span data-stu-id="d208a-149">Follow these steps to enable documents to be printed from POS on a Windows printer that is connected to the hardware station.</span></span>

1. <span data-ttu-id="d208a-150">Wybierz kolejno opcje **Handel detaliczny i inny \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Profile punktów sprzedaży \> Profile sprzętu**.</span><span class="sxs-lookup"><span data-stu-id="d208a-150">Go to **Retail and Commerce \> Channel setup \> POS setup \> POS profiles \> Hardware profiles**.</span></span>
2. <span data-ttu-id="d208a-151">Wybierz profil sprzętowy powiązany ze sklepem, w których jest używana drukarka.</span><span class="sxs-lookup"><span data-stu-id="d208a-151">Select a hardware profile that is related to the store where the printer is used.</span></span>
3. <span data-ttu-id="d208a-152">W sekcji **Drukarka** lub **Drukarka 2** zaktualizuj ustawienia:</span><span class="sxs-lookup"><span data-stu-id="d208a-152">In either the **Printer** section or the **Printer 2** section, update the settings:</span></span>

    - <span data-ttu-id="d208a-153">W polu **Drukarki** zaznacz opcję **Sterownik w systemie Windows**.</span><span class="sxs-lookup"><span data-stu-id="d208a-153">In the **Printer** field, select **Windows driver**.</span></span>
    - <span data-ttu-id="d208a-154">W polu **Nazwa urządzenia** nadaj drukarce nazwę.</span><span class="sxs-lookup"><span data-stu-id="d208a-154">In the **Device name** field, enter the name of the printer.</span></span>

4. <span data-ttu-id="d208a-155">Wybierz kolejno opcje **Retail i Commerce \> Retail i Commerce IT \> Harmonogram dystrybucji**.</span><span class="sxs-lookup"><span data-stu-id="d208a-155">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
5. <span data-ttu-id="d208a-156">Wybierz zadanie **1090**, a następnie kliknij przycisk **Uruchom teraz**.</span><span class="sxs-lookup"><span data-stu-id="d208a-156">Select job **1090**, and then select **Run now**.</span></span>
