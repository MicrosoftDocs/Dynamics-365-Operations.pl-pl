---
title: Ustaw Mapowanie pól stanu zamówienia sprzedaży
description: W tym temacie opisano sposób konfigurowania pól stanu zamówienia sprzedaży na potrzeby podwójnego zapisywania.
author: dasani-madipalli
manager: tonyafehr
ms.date: 06/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: damadipa
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-06-25
ms.openlocfilehash: 5855581100606003c1faf6b88a0ab234ae378893
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997681"
---
# <a name="set-up-the-mapping-for-the-sales-order-status-fields"></a><span data-ttu-id="8cc25-103">Ustaw Mapowanie pól stanu zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="8cc25-103">Set up the mapping for the sales order status fields</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8cc25-104">Pola wskazujące stan zamówienia sprzedaży mają różne wartości wyliczenia w Microsoft Dynamics 365 Supply Chain Management i Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="8cc25-104">The fields that indicate sales order status have different enumeration values in Microsoft Dynamics 365 Supply Chain Management and Dynamics 365 Sales.</span></span> <span data-ttu-id="8cc25-105">Dodatkowe ustawienia są wymagane do mapowania tych pól w trybie podwójnego zapisu.</span><span class="sxs-lookup"><span data-stu-id="8cc25-105">Additional setup is required to map these fields in dual-write.</span></span>

## <a name="fields-in-supply-chain-management"></a><span data-ttu-id="8cc25-106">Pola w Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="8cc25-106">Fields in Supply Chain Management</span></span>

<span data-ttu-id="8cc25-107">W Supply Chain Management dwa pola odzwierciedlają stan zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="8cc25-107">In Supply Chain Management, two fields reflect the status of the sales order.</span></span> <span data-ttu-id="8cc25-108">Pola, które muszą być zmapowane, to **Stan** i **Stan dokumentu**.</span><span class="sxs-lookup"><span data-stu-id="8cc25-108">The fields that you must map are **Status** and **Document Status**.</span></span>

<span data-ttu-id="8cc25-109">Wyliczenie **Stan** określa ogólny stan zamówienia.</span><span class="sxs-lookup"><span data-stu-id="8cc25-109">The **Status** enumeration specifies the overall status of the order.</span></span> <span data-ttu-id="8cc25-110">Ten stan jest wyświetlany w nagłówku zamówienia.</span><span class="sxs-lookup"><span data-stu-id="8cc25-110">This status is shown on the order header.</span></span>

<span data-ttu-id="8cc25-111">Wyliczenie **Stan** oferuje następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="8cc25-111">The **Status** enumeration has the following values:</span></span>

- <span data-ttu-id="8cc25-112">Otwarte zamówienie</span><span class="sxs-lookup"><span data-stu-id="8cc25-112">Open Order</span></span>
- <span data-ttu-id="8cc25-113">Dostarczone</span><span class="sxs-lookup"><span data-stu-id="8cc25-113">Delivered</span></span>
- <span data-ttu-id="8cc25-114">Zafakturowane</span><span class="sxs-lookup"><span data-stu-id="8cc25-114">Invoiced</span></span>
- <span data-ttu-id="8cc25-115">Anulowane</span><span class="sxs-lookup"><span data-stu-id="8cc25-115">Cancelled</span></span>

<span data-ttu-id="8cc25-116">Wyliczenie **Stanu dokumentu** określa najnowszy dokument, który został wygenerowany dla zamówienia.</span><span class="sxs-lookup"><span data-stu-id="8cc25-116">The **Document Status** enumeration specifies the most recent document that was generated for the order.</span></span> <span data-ttu-id="8cc25-117">Jeśli na przykład zamówienie zostało potwierdzone, dokument jest potwierdzeniem zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="8cc25-117">For example, if the order is confirmed, this document is a sales order confirmation.</span></span> <span data-ttu-id="8cc25-118">Jeśli zamówienie sprzedaży jest częściowo zafakturowane, a pozostały wiersz zostanie potwierdzony, stan dokumentu pozostanie na **Fakturze** , ponieważ faktura jest generowana w późniejszym etapie procesu.</span><span class="sxs-lookup"><span data-stu-id="8cc25-118">If a sales order is partially invoiced, and then the remaining line is confirmed, the document status remains **Invoice** , because the invoice is generated later in the process.</span></span>

<span data-ttu-id="8cc25-119">Wyliczenie **Stan dokumentu** oferuje następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="8cc25-119">The **Document Status** enumeration has the following values:</span></span>

- <span data-ttu-id="8cc25-120">Potwierdzenie</span><span class="sxs-lookup"><span data-stu-id="8cc25-120">Confirmation</span></span>
- <span data-ttu-id="8cc25-121">Lista pobrania</span><span class="sxs-lookup"><span data-stu-id="8cc25-121">Picking List</span></span>
- <span data-ttu-id="8cc25-122">Dokument dostawy</span><span class="sxs-lookup"><span data-stu-id="8cc25-122">Packing Slip</span></span>
- <span data-ttu-id="8cc25-123">Faktura VAT</span><span class="sxs-lookup"><span data-stu-id="8cc25-123">Invoice</span></span>

## <a name="fields-in-sales"></a><span data-ttu-id="8cc25-124">Pola w Sales</span><span class="sxs-lookup"><span data-stu-id="8cc25-124">Fields in Sales</span></span>

<span data-ttu-id="8cc25-125">W Sales dwa pola odzwierciedlają stan zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="8cc25-125">In Sales, two fields indicate the status of the order.</span></span> <span data-ttu-id="8cc25-126">Pola, które muszą być zmapowane, to **Stan** i **Przetwarzanie dokumentu**.</span><span class="sxs-lookup"><span data-stu-id="8cc25-126">The fields that you must map are **Status** and **Processing Status**.</span></span>

<span data-ttu-id="8cc25-127">Wyliczenie **Stan** określa ogólny stan zamówienia.</span><span class="sxs-lookup"><span data-stu-id="8cc25-127">The **Status** enumeration specifies the overall status of the order.</span></span> <span data-ttu-id="8cc25-128">Ma następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="8cc25-128">It has the following values:</span></span>

- <span data-ttu-id="8cc25-129">Aktywni</span><span class="sxs-lookup"><span data-stu-id="8cc25-129">Active</span></span>
- <span data-ttu-id="8cc25-130">Przesłany</span><span class="sxs-lookup"><span data-stu-id="8cc25-130">Submitted</span></span>
- <span data-ttu-id="8cc25-131">Realizacja</span><span class="sxs-lookup"><span data-stu-id="8cc25-131">Fulfilled</span></span>
- <span data-ttu-id="8cc25-132">Zafakturowane</span><span class="sxs-lookup"><span data-stu-id="8cc25-132">Invoiced</span></span>
- <span data-ttu-id="8cc25-133">Anulowane</span><span class="sxs-lookup"><span data-stu-id="8cc25-133">Cancelled</span></span>

<span data-ttu-id="8cc25-134">Wyliczenie **Stanu przetwarzania** zostało wprowadzone w taki sposób, aby można było dokładniej zamapować stan z Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="8cc25-134">The **Processing Status** enumeration was introduced so that the status can be mapped more accurately with Supply Chain Management.</span></span>

<span data-ttu-id="8cc25-135">W poniższej tabeli przedstawiono mapowanie **Stanu przetwarzania** w Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="8cc25-135">The following table shows the mapping of **Processing Status** in Supply Chain Management.</span></span>

| <span data-ttu-id="8cc25-136">Stan przetwarzania</span><span class="sxs-lookup"><span data-stu-id="8cc25-136">Processing Status</span></span>   | <span data-ttu-id="8cc25-137">Stan w Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="8cc25-137">Status in Supply Chain Management</span></span> | <span data-ttu-id="8cc25-138">Stan dokumentu w Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="8cc25-138">Document Status in Supply Chain Management</span></span> |
|---------------------|-----------------------------------|--------------------------------------------|
| <span data-ttu-id="8cc25-139">Aktywni</span><span class="sxs-lookup"><span data-stu-id="8cc25-139">Active</span></span>              | <span data-ttu-id="8cc25-140">Otwarte zamówienie</span><span class="sxs-lookup"><span data-stu-id="8cc25-140">Open Order</span></span>                        | <span data-ttu-id="8cc25-141">None</span><span class="sxs-lookup"><span data-stu-id="8cc25-141">None</span></span>                                       |
| <span data-ttu-id="8cc25-142">Potwierdzone</span><span class="sxs-lookup"><span data-stu-id="8cc25-142">Confirmed</span></span>           | <span data-ttu-id="8cc25-143">Otwarte zamówienie</span><span class="sxs-lookup"><span data-stu-id="8cc25-143">Open Order</span></span>                        | <span data-ttu-id="8cc25-144">Potwierdzenie</span><span class="sxs-lookup"><span data-stu-id="8cc25-144">Confirmation</span></span>                               |
| <span data-ttu-id="8cc25-145">Pobrane</span><span class="sxs-lookup"><span data-stu-id="8cc25-145">Picked</span></span>              | <span data-ttu-id="8cc25-146">Otwarte zamówienie</span><span class="sxs-lookup"><span data-stu-id="8cc25-146">Open Order</span></span>                        | <span data-ttu-id="8cc25-147">Lista pobrania</span><span class="sxs-lookup"><span data-stu-id="8cc25-147">Picking List</span></span>                               |
| <span data-ttu-id="8cc25-148">Częściowo dostarczone</span><span class="sxs-lookup"><span data-stu-id="8cc25-148">Partially Delivered</span></span> | <span data-ttu-id="8cc25-149">Otwarte zamówienie</span><span class="sxs-lookup"><span data-stu-id="8cc25-149">Open Order</span></span>                        | <span data-ttu-id="8cc25-150">Dokument dostawy</span><span class="sxs-lookup"><span data-stu-id="8cc25-150">Packing Slip</span></span>                               |
| <span data-ttu-id="8cc25-151">Dostarczone</span><span class="sxs-lookup"><span data-stu-id="8cc25-151">Delivered</span></span>           | <span data-ttu-id="8cc25-152">Dostarczone</span><span class="sxs-lookup"><span data-stu-id="8cc25-152">Delivered</span></span>                         | <span data-ttu-id="8cc25-153">Dokument dostawy</span><span class="sxs-lookup"><span data-stu-id="8cc25-153">Packing Slip</span></span>                               |
| <span data-ttu-id="8cc25-154">Częściowo zafakturowane</span><span class="sxs-lookup"><span data-stu-id="8cc25-154">Partially Invoiced</span></span>  | <span data-ttu-id="8cc25-155">Dostarczone</span><span class="sxs-lookup"><span data-stu-id="8cc25-155">Delivered</span></span>                         | <span data-ttu-id="8cc25-156">Faktura VAT</span><span class="sxs-lookup"><span data-stu-id="8cc25-156">Invoice</span></span>                                    |
| <span data-ttu-id="8cc25-157">Zafakturowane</span><span class="sxs-lookup"><span data-stu-id="8cc25-157">Invoiced</span></span>            | <span data-ttu-id="8cc25-158">Zafakturowane</span><span class="sxs-lookup"><span data-stu-id="8cc25-158">Invoiced</span></span>                          | <span data-ttu-id="8cc25-159">Faktura VAT</span><span class="sxs-lookup"><span data-stu-id="8cc25-159">Invoice</span></span>                                    |
| <span data-ttu-id="8cc25-160">Anulowane</span><span class="sxs-lookup"><span data-stu-id="8cc25-160">Cancelled</span></span>           | <span data-ttu-id="8cc25-161">Anulowane</span><span class="sxs-lookup"><span data-stu-id="8cc25-161">Cancelled</span></span>                         | <span data-ttu-id="8cc25-162">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="8cc25-162">Not applicable</span></span>                             |

<span data-ttu-id="8cc25-163">W poniższej tabeli przedstawiono mapowanie **Stanu przetwarzania** między Sales a Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="8cc25-163">The following table shows the mapping of **Processing Status** between Sales and Supply Chain Management.</span></span>

| <span data-ttu-id="8cc25-164">Stan przetwarzania</span><span class="sxs-lookup"><span data-stu-id="8cc25-164">Processing Status</span></span>   | <span data-ttu-id="8cc25-165">Stany w Sales</span><span class="sxs-lookup"><span data-stu-id="8cc25-165">Status in Sales</span></span> | <span data-ttu-id="8cc25-166">Stan w Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="8cc25-166">Status in Supply Chain Management</span></span> |
|---------------------|-----------------|-----------------------------------|
| <span data-ttu-id="8cc25-167">Aktywni</span><span class="sxs-lookup"><span data-stu-id="8cc25-167">Active</span></span>              | <span data-ttu-id="8cc25-168">Aktywni</span><span class="sxs-lookup"><span data-stu-id="8cc25-168">Active</span></span>          | <span data-ttu-id="8cc25-169">Otwarte zamówienie</span><span class="sxs-lookup"><span data-stu-id="8cc25-169">Open Order</span></span>                        |
| <span data-ttu-id="8cc25-170">Potwierdzone</span><span class="sxs-lookup"><span data-stu-id="8cc25-170">Confirmed</span></span>           | <span data-ttu-id="8cc25-171">Przesłany</span><span class="sxs-lookup"><span data-stu-id="8cc25-171">Submitted</span></span>       | <span data-ttu-id="8cc25-172">Otwarte zamówienie</span><span class="sxs-lookup"><span data-stu-id="8cc25-172">Open Order</span></span>                        |
| <span data-ttu-id="8cc25-173">Pobrane</span><span class="sxs-lookup"><span data-stu-id="8cc25-173">Picked</span></span>              | <span data-ttu-id="8cc25-174">Przesłany</span><span class="sxs-lookup"><span data-stu-id="8cc25-174">Submitted</span></span>       | <span data-ttu-id="8cc25-175">Otwarte zamówienie</span><span class="sxs-lookup"><span data-stu-id="8cc25-175">Open Order</span></span>                        |
| <span data-ttu-id="8cc25-176">Częściowo dostarczone</span><span class="sxs-lookup"><span data-stu-id="8cc25-176">Partially Delivered</span></span> | <span data-ttu-id="8cc25-177">Aktywni</span><span class="sxs-lookup"><span data-stu-id="8cc25-177">Active</span></span>          | <span data-ttu-id="8cc25-178">Otwarte zamówienie</span><span class="sxs-lookup"><span data-stu-id="8cc25-178">Open Order</span></span>                        |
| <span data-ttu-id="8cc25-179">Częściowo zafakturowane</span><span class="sxs-lookup"><span data-stu-id="8cc25-179">Partially Invoiced</span></span>  | <span data-ttu-id="8cc25-180">Aktywni</span><span class="sxs-lookup"><span data-stu-id="8cc25-180">Active</span></span>          | <span data-ttu-id="8cc25-181">Otwarte zamówienie</span><span class="sxs-lookup"><span data-stu-id="8cc25-181">Open Order</span></span>                        |
| <span data-ttu-id="8cc25-182">Częściowo zafakturowane</span><span class="sxs-lookup"><span data-stu-id="8cc25-182">Partially Invoiced</span></span>  | <span data-ttu-id="8cc25-183">Realizacja</span><span class="sxs-lookup"><span data-stu-id="8cc25-183">Fulfilled</span></span>       | <span data-ttu-id="8cc25-184">Dostarczone</span><span class="sxs-lookup"><span data-stu-id="8cc25-184">Delivered</span></span>                         |
| <span data-ttu-id="8cc25-185">Zafakturowane</span><span class="sxs-lookup"><span data-stu-id="8cc25-185">Invoiced</span></span>            | <span data-ttu-id="8cc25-186">Zafakturowane</span><span class="sxs-lookup"><span data-stu-id="8cc25-186">Invoiced</span></span>        | <span data-ttu-id="8cc25-187">Zafakturowane</span><span class="sxs-lookup"><span data-stu-id="8cc25-187">Invoiced</span></span>                          |
| <span data-ttu-id="8cc25-188">Anulowane</span><span class="sxs-lookup"><span data-stu-id="8cc25-188">Cancelled</span></span>           | <span data-ttu-id="8cc25-189">Anulowane</span><span class="sxs-lookup"><span data-stu-id="8cc25-189">Cancelled</span></span>       | <span data-ttu-id="8cc25-190">Anulowane</span><span class="sxs-lookup"><span data-stu-id="8cc25-190">Cancelled</span></span>                         |

## <a name="setup"></a><span data-ttu-id="8cc25-191">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="8cc25-191">Setup</span></span>

<span data-ttu-id="8cc25-192">Aby skonfigurować mapowanie dla pól stanu zamówienia sprzedaży, należy włączyć atrybuty **IsSOPIntegrationEnabled** i **isIntegrationUser**.</span><span class="sxs-lookup"><span data-stu-id="8cc25-192">To set up the mapping for the sales order status fields, you must enable the **IsSOPIntegrationEnabled** and **isIntegrationUser** attributes.</span></span>

<span data-ttu-id="8cc25-193">Aby włączyć atrybut **IsSOPIntegrationEnabled** , wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="8cc25-193">To enable the **IsSOPIntegrationEnabled** attribute, follow these steps.</span></span>

1. <span data-ttu-id="8cc25-194">W przeglądarce przejdź do strony `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations`.</span><span class="sxs-lookup"><span data-stu-id="8cc25-194">In a browser, go to `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations`.</span></span> <span data-ttu-id="8cc25-195">Zastąp **\<test-name\>** łączem firmy w Sales.</span><span class="sxs-lookup"><span data-stu-id="8cc25-195">Replace **\<test-name\>** with your company's link to Sales.</span></span>
2. <span data-ttu-id="8cc25-196">Na otwartej stronie znajdź **organizationid** i zanotuj wartość.</span><span class="sxs-lookup"><span data-stu-id="8cc25-196">On the page that is opened, find **organizationid** , and make a note of the value.</span></span>

    ![Znajdowanie organizationid](media/sales-map-orgid.png)

3. <span data-ttu-id="8cc25-198">W Sales otwórz konsolę przeglądarki i uruchom następujący skrypt.</span><span class="sxs-lookup"><span data-stu-id="8cc25-198">In Sales, open the browser console, and run following script.</span></span> <span data-ttu-id="8cc25-199">Należy zastosować wartość **organizationid** z kroku 2.</span><span class="sxs-lookup"><span data-stu-id="8cc25-199">Use the **organizationid** value from step 2.</span></span>

    ```javascript
    Xrm.WebApi.updateRecord("organization",
    "d9a7c5f7-acbf-4aa9-86e8-a891c43f748c", {"issopintegrationenabled" :
    true}).then(
        function success(result) {
            console.log("Account updated");
            // perform operations on record update
        },
        function (error) {
            console.log(error.message);
            // handle error conditions
        }
    );
    ```

    ![Kod JavaScript w konsoli przeglądarki](media/sales-map-script.png)

4. <span data-ttu-id="8cc25-201">Upewnij się, że **IsSOPIntegrationEnabled** ma ustawioną wartość **true**.</span><span class="sxs-lookup"><span data-stu-id="8cc25-201">Verify that **IsSOPIntegrationEnabled** is set to **true**.</span></span> <span data-ttu-id="8cc25-202">Użyj adresu URL z kroku 1, aby sprawdzić wartość.</span><span class="sxs-lookup"><span data-stu-id="8cc25-202">Use the URL from step 1 to check the value.</span></span>

    ![IsSOPIntegrationEnabled ma ustawioną wartość true](media/sales-map-integration-enabled.png)

<span data-ttu-id="8cc25-204">Aby włączyć atrybut **isIntegrationUser** , wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="8cc25-204">To enable the **isIntegrationUser** attribute, follow these steps.</span></span>

1. <span data-ttu-id="8cc25-205">W Sales przejdź do **Ustawienia \> Dostosowania \> Dostosuj system** , wybierz pozycję **Jednostka użytkownika** , a następnie otwórz **Formularz \> Użytkownik**.</span><span class="sxs-lookup"><span data-stu-id="8cc25-205">In Sales, go to **Setting \> Customization \> Customize the System** , select **User entity** , and then open **Form \> User**.</span></span>

    ![Otwieranie formularza użytkownika](media/sales-map-user.png)

2. <span data-ttu-id="8cc25-207">W Eksploratorze pól znajdź **Tryb użytkownika integracyjnego** i kliknij go dwukrotnie, aby dodać go do formularza.</span><span class="sxs-lookup"><span data-stu-id="8cc25-207">In Field Explorer, find **Integration user mode** , and double-click it to add it to the form.</span></span> <span data-ttu-id="8cc25-208">Zapisz zmiany.</span><span class="sxs-lookup"><span data-stu-id="8cc25-208">Save your change.</span></span>

    ![Dodanie pola tryb użytkownika integracyjnego do formularza](media/sales-map-field-explorer.png)

3. <span data-ttu-id="8cc25-210">W module Sprzedaż należy posłużyć do **Ustawienia \> Zabezpieczenia \> Użytkownicy** i zmień widok z **Włączeni użytkownicy** na **Uzytkownicy aplikacji**.</span><span class="sxs-lookup"><span data-stu-id="8cc25-210">In Sales, go to **Setting \> Security \> Users** , and change the view from **Enabled Users** to **Application Users**.</span></span>

    ![Zmienianie widoku z Włączonych użytkowników na Użytkowników aplikacji](media/sales-map-enabled-users.png)

4. <span data-ttu-id="8cc25-212">Wybierz dwa wpisy dla **DualWrite IntegrationUser**.</span><span class="sxs-lookup"><span data-stu-id="8cc25-212">Select the two entries for **DualWrite IntegrationUser**.</span></span>

    ![Lista użytkowników aplikacji](media/sales-map-user-mode.png)

5. <span data-ttu-id="8cc25-214">Zmień wartość w polu **Tryb użytkownika integracyjnego** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="8cc25-214">Change the value of the **Integration user mode** field to **Yes**.</span></span>

    ![Zmiana wartości pola Tryb użytkownika integracji](media/sales-map-user-mode-yes.png)

<span data-ttu-id="8cc25-216">Twoje zamówienia sprzedaży są teraz zamapowane.</span><span class="sxs-lookup"><span data-stu-id="8cc25-216">Your sales orders are now mapped.</span></span>
