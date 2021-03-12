---
title: Ustawianie mapowania kolumn stanu zamówienia sprzedaży
description: W tym temacie opisano sposób konfigurowania kolumn stanu zamówienia sprzedaży na potrzeby podwójnego zapisywania.
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
ms.openlocfilehash: cc70501d231390ea15104d508a36300a1b2cd44c
ms.sourcegitcommit: 7e1be696894731e1c58074d9b5e9c5b3acf7e52a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/17/2020
ms.locfileid: "4744306"
---
# <a name="set-up-the-mapping-for-the-sales-order-status-columns"></a><span data-ttu-id="65345-103">Ustawianie mapowania kolumn stanu zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="65345-103">Set up the mapping for the sales order status columns</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="65345-104">Kolumny wskazujące stan zamówienia sprzedaży mają różne wartości wyliczenia w Microsoft Dynamics 365 Supply Chain Management i Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="65345-104">The columns that indicate sales order status have different enumeration values in Microsoft Dynamics 365 Supply Chain Management and Dynamics 365 Sales.</span></span> <span data-ttu-id="65345-105">Dodatkowe ustawienia są wymagane do mapowania tych kolumn w trybie podwójnego zapisu.</span><span class="sxs-lookup"><span data-stu-id="65345-105">Additional setup is required to map these columns in dual-write.</span></span>

## <a name="columns-in-supply-chain-management"></a><span data-ttu-id="65345-106">Kolumny w Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="65345-106">columns in Supply Chain Management</span></span>

<span data-ttu-id="65345-107">W Supply Chain Management dwie kolumny odzwierciedlają stan zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="65345-107">In Supply Chain Management, two columns reflect the status of the sales order.</span></span> <span data-ttu-id="65345-108">Kolumny, które muszą być zmapowane, to **Stan** i **Stan dokumentu**.</span><span class="sxs-lookup"><span data-stu-id="65345-108">The columns that you must map are **Status** and **Document Status**.</span></span>

<span data-ttu-id="65345-109">Wyliczenie **Stan** określa ogólny stan zamówienia.</span><span class="sxs-lookup"><span data-stu-id="65345-109">The **Status** enumeration specifies the overall status of the order.</span></span> <span data-ttu-id="65345-110">Ten stan jest wyświetlany w nagłówku zamówienia.</span><span class="sxs-lookup"><span data-stu-id="65345-110">This status is shown on the order header.</span></span>

<span data-ttu-id="65345-111">Wyliczenie **Stan** oferuje następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="65345-111">The **Status** enumeration has the following values:</span></span>

- <span data-ttu-id="65345-112">Otwarte zamówienie</span><span class="sxs-lookup"><span data-stu-id="65345-112">Open Order</span></span>
- <span data-ttu-id="65345-113">Dostarczone</span><span class="sxs-lookup"><span data-stu-id="65345-113">Delivered</span></span>
- <span data-ttu-id="65345-114">Zafakturowane</span><span class="sxs-lookup"><span data-stu-id="65345-114">Invoiced</span></span>
- <span data-ttu-id="65345-115">Anulowane</span><span class="sxs-lookup"><span data-stu-id="65345-115">Cancelled</span></span>

<span data-ttu-id="65345-116">Wyliczenie **Stanu dokumentu** określa najnowszy dokument, który został wygenerowany dla zamówienia.</span><span class="sxs-lookup"><span data-stu-id="65345-116">The **Document Status** enumeration specifies the most recent document that was generated for the order.</span></span> <span data-ttu-id="65345-117">Jeśli na przykład zamówienie zostało potwierdzone, dokument jest potwierdzeniem zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="65345-117">For example, if the order is confirmed, this document is a sales order confirmation.</span></span> <span data-ttu-id="65345-118">Jeśli zamówienie sprzedaży jest częściowo zafakturowane, a pozostały wiersz zostanie potwierdzony, stan dokumentu pozostanie na **Fakturze**, ponieważ faktura jest generowana w późniejszym etapie procesu.</span><span class="sxs-lookup"><span data-stu-id="65345-118">If a sales order is partially invoiced, and then the remaining line is confirmed, the document status remains **Invoice**, because the invoice is generated later in the process.</span></span>

<span data-ttu-id="65345-119">Wyliczenie **Stan dokumentu** oferuje następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="65345-119">The **Document Status** enumeration has the following values:</span></span>

- <span data-ttu-id="65345-120">Potwierdzenie</span><span class="sxs-lookup"><span data-stu-id="65345-120">Confirmation</span></span>
- <span data-ttu-id="65345-121">Lista pobrania</span><span class="sxs-lookup"><span data-stu-id="65345-121">Picking List</span></span>
- <span data-ttu-id="65345-122">Dokument dostawy</span><span class="sxs-lookup"><span data-stu-id="65345-122">Packing Slip</span></span>
- <span data-ttu-id="65345-123">Faktura VAT</span><span class="sxs-lookup"><span data-stu-id="65345-123">Invoice</span></span>

## <a name="columns-in-sales"></a><span data-ttu-id="65345-124">Kolumny w aplikacji Sales</span><span class="sxs-lookup"><span data-stu-id="65345-124">columns in Sales</span></span>

<span data-ttu-id="65345-125">W aplikacji Sales dwie kolumny odzwierciedlają stan zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="65345-125">In Sales, two columns indicate the status of the order.</span></span> <span data-ttu-id="65345-126">Kolumny, które muszą być zmapowane, to **Stan** i **Przetwarzanie dokumentu**.</span><span class="sxs-lookup"><span data-stu-id="65345-126">The columns that you must map are **Status** and **Processing Status**.</span></span>

<span data-ttu-id="65345-127">Wyliczenie **Stan** określa ogólny stan zamówienia.</span><span class="sxs-lookup"><span data-stu-id="65345-127">The **Status** enumeration specifies the overall status of the order.</span></span> <span data-ttu-id="65345-128">Ma następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="65345-128">It has the following values:</span></span>

- <span data-ttu-id="65345-129">Aktywni</span><span class="sxs-lookup"><span data-stu-id="65345-129">Active</span></span>
- <span data-ttu-id="65345-130">Przesłany</span><span class="sxs-lookup"><span data-stu-id="65345-130">Submitted</span></span>
- <span data-ttu-id="65345-131">Realizacja</span><span class="sxs-lookup"><span data-stu-id="65345-131">Fulfilled</span></span>
- <span data-ttu-id="65345-132">Zafakturowane</span><span class="sxs-lookup"><span data-stu-id="65345-132">Invoiced</span></span>
- <span data-ttu-id="65345-133">Anulowane</span><span class="sxs-lookup"><span data-stu-id="65345-133">Cancelled</span></span>

<span data-ttu-id="65345-134">Wyliczenie **Stanu przetwarzania** zostało wprowadzone w taki sposób, aby można było dokładniej zamapować stan z Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="65345-134">The **Processing Status** enumeration was introduced so that the status can be mapped more accurately with Supply Chain Management.</span></span>

<span data-ttu-id="65345-135">W poniższej tabeli przedstawiono mapowanie **Stanu przetwarzania** w Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="65345-135">The following table shows the mapping of **Processing Status** in Supply Chain Management.</span></span>

| <span data-ttu-id="65345-136">Stan przetwarzania</span><span class="sxs-lookup"><span data-stu-id="65345-136">Processing Status</span></span>   | <span data-ttu-id="65345-137">Stan w Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="65345-137">Status in Supply Chain Management</span></span> | <span data-ttu-id="65345-138">Stan dokumentu w Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="65345-138">Document Status in Supply Chain Management</span></span> |
|---------------------|-----------------------------------|--------------------------------------------|
| <span data-ttu-id="65345-139">Aktywni</span><span class="sxs-lookup"><span data-stu-id="65345-139">Active</span></span>              | <span data-ttu-id="65345-140">Otwarte zamówienie</span><span class="sxs-lookup"><span data-stu-id="65345-140">Open Order</span></span>                        | <span data-ttu-id="65345-141">None</span><span class="sxs-lookup"><span data-stu-id="65345-141">None</span></span>                                       |
| <span data-ttu-id="65345-142">Potwierdzone</span><span class="sxs-lookup"><span data-stu-id="65345-142">Confirmed</span></span>           | <span data-ttu-id="65345-143">Otwarte zamówienie</span><span class="sxs-lookup"><span data-stu-id="65345-143">Open Order</span></span>                        | <span data-ttu-id="65345-144">Potwierdzenie</span><span class="sxs-lookup"><span data-stu-id="65345-144">Confirmation</span></span>                               |
| <span data-ttu-id="65345-145">Pobrane</span><span class="sxs-lookup"><span data-stu-id="65345-145">Picked</span></span>              | <span data-ttu-id="65345-146">Otwarte zamówienie</span><span class="sxs-lookup"><span data-stu-id="65345-146">Open Order</span></span>                        | <span data-ttu-id="65345-147">Lista pobrania</span><span class="sxs-lookup"><span data-stu-id="65345-147">Picking List</span></span>                               |
| <span data-ttu-id="65345-148">Częściowo dostarczone</span><span class="sxs-lookup"><span data-stu-id="65345-148">Partially Delivered</span></span> | <span data-ttu-id="65345-149">Otwarte zamówienie</span><span class="sxs-lookup"><span data-stu-id="65345-149">Open Order</span></span>                        | <span data-ttu-id="65345-150">Dokument dostawy</span><span class="sxs-lookup"><span data-stu-id="65345-150">Packing Slip</span></span>                               |
| <span data-ttu-id="65345-151">Dostarczone</span><span class="sxs-lookup"><span data-stu-id="65345-151">Delivered</span></span>           | <span data-ttu-id="65345-152">Dostarczone</span><span class="sxs-lookup"><span data-stu-id="65345-152">Delivered</span></span>                         | <span data-ttu-id="65345-153">Dokument dostawy</span><span class="sxs-lookup"><span data-stu-id="65345-153">Packing Slip</span></span>                               |
| <span data-ttu-id="65345-154">Częściowo zafakturowane</span><span class="sxs-lookup"><span data-stu-id="65345-154">Partially Invoiced</span></span>  | <span data-ttu-id="65345-155">Dostarczone</span><span class="sxs-lookup"><span data-stu-id="65345-155">Delivered</span></span>                         | <span data-ttu-id="65345-156">Faktura VAT</span><span class="sxs-lookup"><span data-stu-id="65345-156">Invoice</span></span>                                    |
| <span data-ttu-id="65345-157">Zafakturowane</span><span class="sxs-lookup"><span data-stu-id="65345-157">Invoiced</span></span>            | <span data-ttu-id="65345-158">Zafakturowane</span><span class="sxs-lookup"><span data-stu-id="65345-158">Invoiced</span></span>                          | <span data-ttu-id="65345-159">Faktura VAT</span><span class="sxs-lookup"><span data-stu-id="65345-159">Invoice</span></span>                                    |
| <span data-ttu-id="65345-160">Anulowane</span><span class="sxs-lookup"><span data-stu-id="65345-160">Cancelled</span></span>           | <span data-ttu-id="65345-161">Anulowane</span><span class="sxs-lookup"><span data-stu-id="65345-161">Cancelled</span></span>                         | <span data-ttu-id="65345-162">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="65345-162">Not applicable</span></span>                             |

<span data-ttu-id="65345-163">W poniższej tabeli przedstawiono mapowanie **Stanu przetwarzania** między Sales a Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="65345-163">The following table shows the mapping of **Processing Status** between Sales and Supply Chain Management.</span></span>

| <span data-ttu-id="65345-164">Stan przetwarzania</span><span class="sxs-lookup"><span data-stu-id="65345-164">Processing Status</span></span>   | <span data-ttu-id="65345-165">Stany w Sales</span><span class="sxs-lookup"><span data-stu-id="65345-165">Status in Sales</span></span> | <span data-ttu-id="65345-166">Stan w Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="65345-166">Status in Supply Chain Management</span></span> |
|---------------------|-----------------|-----------------------------------|
| <span data-ttu-id="65345-167">Aktywni</span><span class="sxs-lookup"><span data-stu-id="65345-167">Active</span></span>              | <span data-ttu-id="65345-168">Aktywni</span><span class="sxs-lookup"><span data-stu-id="65345-168">Active</span></span>          | <span data-ttu-id="65345-169">Otwarte zamówienie</span><span class="sxs-lookup"><span data-stu-id="65345-169">Open Order</span></span>                        |
| <span data-ttu-id="65345-170">Potwierdzone</span><span class="sxs-lookup"><span data-stu-id="65345-170">Confirmed</span></span>           | <span data-ttu-id="65345-171">Przesłany</span><span class="sxs-lookup"><span data-stu-id="65345-171">Submitted</span></span>       | <span data-ttu-id="65345-172">Otwarte zamówienie</span><span class="sxs-lookup"><span data-stu-id="65345-172">Open Order</span></span>                        |
| <span data-ttu-id="65345-173">Pobrane</span><span class="sxs-lookup"><span data-stu-id="65345-173">Picked</span></span>              | <span data-ttu-id="65345-174">Przesłany</span><span class="sxs-lookup"><span data-stu-id="65345-174">Submitted</span></span>       | <span data-ttu-id="65345-175">Otwarte zamówienie</span><span class="sxs-lookup"><span data-stu-id="65345-175">Open Order</span></span>                        |
| <span data-ttu-id="65345-176">Częściowo dostarczone</span><span class="sxs-lookup"><span data-stu-id="65345-176">Partially Delivered</span></span> | <span data-ttu-id="65345-177">Aktywni</span><span class="sxs-lookup"><span data-stu-id="65345-177">Active</span></span>          | <span data-ttu-id="65345-178">Otwarte zamówienie</span><span class="sxs-lookup"><span data-stu-id="65345-178">Open Order</span></span>                        |
| <span data-ttu-id="65345-179">Częściowo zafakturowane</span><span class="sxs-lookup"><span data-stu-id="65345-179">Partially Invoiced</span></span>  | <span data-ttu-id="65345-180">Aktywni</span><span class="sxs-lookup"><span data-stu-id="65345-180">Active</span></span>          | <span data-ttu-id="65345-181">Otwarte zamówienie</span><span class="sxs-lookup"><span data-stu-id="65345-181">Open Order</span></span>                        |
| <span data-ttu-id="65345-182">Częściowo zafakturowane</span><span class="sxs-lookup"><span data-stu-id="65345-182">Partially Invoiced</span></span>  | <span data-ttu-id="65345-183">Realizacja</span><span class="sxs-lookup"><span data-stu-id="65345-183">Fulfilled</span></span>       | <span data-ttu-id="65345-184">Dostarczone</span><span class="sxs-lookup"><span data-stu-id="65345-184">Delivered</span></span>                         |
| <span data-ttu-id="65345-185">Zafakturowane</span><span class="sxs-lookup"><span data-stu-id="65345-185">Invoiced</span></span>            | <span data-ttu-id="65345-186">Zafakturowane</span><span class="sxs-lookup"><span data-stu-id="65345-186">Invoiced</span></span>        | <span data-ttu-id="65345-187">Zafakturowane</span><span class="sxs-lookup"><span data-stu-id="65345-187">Invoiced</span></span>                          |
| <span data-ttu-id="65345-188">Anulowane</span><span class="sxs-lookup"><span data-stu-id="65345-188">Cancelled</span></span>           | <span data-ttu-id="65345-189">Anulowane</span><span class="sxs-lookup"><span data-stu-id="65345-189">Cancelled</span></span>       | <span data-ttu-id="65345-190">Anulowane</span><span class="sxs-lookup"><span data-stu-id="65345-190">Cancelled</span></span>                         |

## <a name="setup"></a><span data-ttu-id="65345-191">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="65345-191">Setup</span></span>

<span data-ttu-id="65345-192">Aby skonfigurować mapowanie dla kolumn stanu zamówienia sprzedaży, należy włączyć atrybuty **IsSOPIntegrationEnabled** i **isIntegrationUser**.</span><span class="sxs-lookup"><span data-stu-id="65345-192">To set up the mapping for the sales order status columns, you must enable the **IsSOPIntegrationEnabled** and **isIntegrationUser** attributes.</span></span>

<span data-ttu-id="65345-193">Aby włączyć atrybut **IsSOPIntegrationEnabled**, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="65345-193">To enable the **IsSOPIntegrationEnabled** attribute, follow these steps.</span></span>

1. <span data-ttu-id="65345-194">W przeglądarce przejdź do strony `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations`.</span><span class="sxs-lookup"><span data-stu-id="65345-194">In a browser, go to `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations`.</span></span> <span data-ttu-id="65345-195">Zastąp **\<test-name\>** łączem firmy w Sales.</span><span class="sxs-lookup"><span data-stu-id="65345-195">Replace **\<test-name\>** with your company's link to Sales.</span></span>
2. <span data-ttu-id="65345-196">Na otwartej stronie znajdź **organizationid** i zanotuj wartość.</span><span class="sxs-lookup"><span data-stu-id="65345-196">On the page that is opened, find **organizationid**, and make a note of the value.</span></span>

    ![Znajdowanie organizationid](media/sales-map-orgid.png)

3. <span data-ttu-id="65345-198">W Sales otwórz konsolę przeglądarki i uruchom następujący skrypt.</span><span class="sxs-lookup"><span data-stu-id="65345-198">In Sales, open the browser console, and run following script.</span></span> <span data-ttu-id="65345-199">Należy zastosować wartość **organizationid** z kroku 2.</span><span class="sxs-lookup"><span data-stu-id="65345-199">Use the **organizationid** value from step 2.</span></span>

    ```javascript
    Xrm.WebApi.updateRecord("organization",
    "d9a7c5f7-acbf-4aa9-86e8-a891c43f748c", {"issopintegrationenabled" :
    true}).then(
        function success(result) {
            console.log("Account updated");
            // perform operations on row update
        },
        function (error) {
            console.log(error.message);
            // handle error conditions
        }
    );
    ```

    ![Kod JavaScript w konsoli przeglądarki](media/sales-map-script.png)

4. <span data-ttu-id="65345-201">Upewnij się, że **IsSOPIntegrationEnabled** ma ustawioną wartość **true**.</span><span class="sxs-lookup"><span data-stu-id="65345-201">Verify that **IsSOPIntegrationEnabled** is set to **true**.</span></span> <span data-ttu-id="65345-202">Użyj adresu URL z kroku 1, aby sprawdzić wartość.</span><span class="sxs-lookup"><span data-stu-id="65345-202">Use the URL from step 1 to check the value.</span></span>

    ![IsSOPIntegrationEnabled ma ustawioną wartość true](media/sales-map-integration-enabled.png)

<span data-ttu-id="65345-204">Aby włączyć atrybut **isIntegrationUser**, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="65345-204">To enable the **isIntegrationUser** attribute, follow these steps.</span></span>

1. <span data-ttu-id="65345-205">W Sales przejdź do **Ustawienia \> Dostosowania \> Dostosuj system**, wybierz pozycję **Tabela użytkownika**, a następnie otwórz **Formularz \> Użytkownik**.</span><span class="sxs-lookup"><span data-stu-id="65345-205">In Sales, go to **Setting \> Customization \> Customize the System**, select **User table**, and then open **Form \> User**.</span></span>

    ![Otwieranie formularza użytkownika](media/sales-map-user.png)

2. <span data-ttu-id="65345-207">W Eksploratorze pól znajdź **Tryb użytkownika integracyjnego** i kliknij go dwukrotnie, aby dodać go do formularza.</span><span class="sxs-lookup"><span data-stu-id="65345-207">In Field Explorer, find **Integration user mode**, and double-click it to add it to the form.</span></span> <span data-ttu-id="65345-208">Zapisz zmiany.</span><span class="sxs-lookup"><span data-stu-id="65345-208">Save your change.</span></span>

    ![Dodanie kolumny trybu użytkownika integracyjnego do formularza](media/sales-map-field-explorer.png)

3. <span data-ttu-id="65345-210">W module Sprzedaż należy posłużyć do **Ustawienia \> Zabezpieczenia \> Użytkownicy** i zmień widok z **Włączeni użytkownicy** na **Uzytkownicy aplikacji**.</span><span class="sxs-lookup"><span data-stu-id="65345-210">In Sales, go to **Setting \> Security \> Users**, and change the view from **Enabled Users** to **Application Users**.</span></span>

    ![Zmienianie widoku z Włączonych użytkowników na Użytkowników aplikacji](media/sales-map-enabled-users.png)

4. <span data-ttu-id="65345-212">Wybierz dwa wpisy dla **DualWrite IntegrationUser**.</span><span class="sxs-lookup"><span data-stu-id="65345-212">Select the two entries for **DualWrite IntegrationUser**.</span></span>

    ![Lista użytkowników aplikacji](media/sales-map-user-mode.png)

5. <span data-ttu-id="65345-214">Zmień wartość w kolumnie **Tryb użytkownika integracyjnego** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="65345-214">Change the value of the **Integration user mode** column to **Yes**.</span></span>

    ![Zmiana wartości kolumny Tryb użytkownika integracji](media/sales-map-user-mode-yes.png)

<span data-ttu-id="65345-216">Twoje zamówienia sprzedaży są teraz zamapowane.</span><span class="sxs-lookup"><span data-stu-id="65345-216">Your sales orders are now mapped.</span></span>
