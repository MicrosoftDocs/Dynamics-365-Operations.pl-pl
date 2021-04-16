---
title: Ustawianie mapowania kolumn stanu zamówienia sprzedaży
description: W tym temacie opisano sposób konfigurowania kolumn stanu zamówienia sprzedaży na potrzeby podwójnego zapisywania.
author: dasani-madipalli
ms.date: 06/25/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 9afa64df73aa17e7a15a0ee4f4529ac74bcd3c67
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750721"
---
# <a name="set-up-the-mapping-for-the-sales-order-status-columns"></a><span data-ttu-id="eaeb6-103">Ustawianie mapowania kolumn stanu zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="eaeb6-103">Set up the mapping for the sales order status columns</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="eaeb6-104">Kolumny wskazujące stan zamówienia sprzedaży mają różne wartości wyliczenia w Microsoft Dynamics 365 Supply Chain Management i Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="eaeb6-104">The columns that indicate sales order status have different enumeration values in Microsoft Dynamics 365 Supply Chain Management and Dynamics 365 Sales.</span></span> <span data-ttu-id="eaeb6-105">Dodatkowe ustawienia są wymagane do mapowania tych kolumn w trybie podwójnego zapisu.</span><span class="sxs-lookup"><span data-stu-id="eaeb6-105">Additional setup is required to map these columns in dual-write.</span></span>

## <a name="columns-in-supply-chain-management"></a><span data-ttu-id="eaeb6-106">Kolumny w Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="eaeb6-106">columns in Supply Chain Management</span></span>

<span data-ttu-id="eaeb6-107">W Supply Chain Management dwie kolumny odzwierciedlają stan zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="eaeb6-107">In Supply Chain Management, two columns reflect the status of the sales order.</span></span> <span data-ttu-id="eaeb6-108">Kolumny, które muszą być zmapowane, to **Stan** i **Stan dokumentu**.</span><span class="sxs-lookup"><span data-stu-id="eaeb6-108">The columns that you must map are **Status** and **Document Status**.</span></span>

<span data-ttu-id="eaeb6-109">Wyliczenie **Stan** określa ogólny stan zamówienia.</span><span class="sxs-lookup"><span data-stu-id="eaeb6-109">The **Status** enumeration specifies the overall status of the order.</span></span> <span data-ttu-id="eaeb6-110">Ten stan jest wyświetlany w nagłówku zamówienia.</span><span class="sxs-lookup"><span data-stu-id="eaeb6-110">This status is shown on the order header.</span></span>

<span data-ttu-id="eaeb6-111">Wyliczenie **Stan** oferuje następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="eaeb6-111">The **Status** enumeration has the following values:</span></span>

- <span data-ttu-id="eaeb6-112">Otwarte zamówienie</span><span class="sxs-lookup"><span data-stu-id="eaeb6-112">Open Order</span></span>
- <span data-ttu-id="eaeb6-113">Dostarczone</span><span class="sxs-lookup"><span data-stu-id="eaeb6-113">Delivered</span></span>
- <span data-ttu-id="eaeb6-114">Zafakturowane</span><span class="sxs-lookup"><span data-stu-id="eaeb6-114">Invoiced</span></span>
- <span data-ttu-id="eaeb6-115">Anulowane</span><span class="sxs-lookup"><span data-stu-id="eaeb6-115">Cancelled</span></span>

<span data-ttu-id="eaeb6-116">Wyliczenie **Stanu dokumentu** określa najnowszy dokument, który został wygenerowany dla zamówienia.</span><span class="sxs-lookup"><span data-stu-id="eaeb6-116">The **Document Status** enumeration specifies the most recent document that was generated for the order.</span></span> <span data-ttu-id="eaeb6-117">Jeśli na przykład zamówienie zostało potwierdzone, dokument jest potwierdzeniem zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="eaeb6-117">For example, if the order is confirmed, this document is a sales order confirmation.</span></span> <span data-ttu-id="eaeb6-118">Jeśli zamówienie sprzedaży jest częściowo zafakturowane, a pozostały wiersz zostanie potwierdzony, stan dokumentu pozostanie na **Fakturze**, ponieważ faktura jest generowana w późniejszym etapie procesu.</span><span class="sxs-lookup"><span data-stu-id="eaeb6-118">If a sales order is partially invoiced, and then the remaining line is confirmed, the document status remains **Invoice**, because the invoice is generated later in the process.</span></span>

<span data-ttu-id="eaeb6-119">Wyliczenie **Stan dokumentu** oferuje następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="eaeb6-119">The **Document Status** enumeration has the following values:</span></span>

- <span data-ttu-id="eaeb6-120">Potwierdzenie</span><span class="sxs-lookup"><span data-stu-id="eaeb6-120">Confirmation</span></span>
- <span data-ttu-id="eaeb6-121">Lista pobrania</span><span class="sxs-lookup"><span data-stu-id="eaeb6-121">Picking List</span></span>
- <span data-ttu-id="eaeb6-122">Dokument dostawy</span><span class="sxs-lookup"><span data-stu-id="eaeb6-122">Packing Slip</span></span>
- <span data-ttu-id="eaeb6-123">Faktura VAT</span><span class="sxs-lookup"><span data-stu-id="eaeb6-123">Invoice</span></span>

## <a name="columns-in-sales"></a><span data-ttu-id="eaeb6-124">Kolumny w aplikacji Sales</span><span class="sxs-lookup"><span data-stu-id="eaeb6-124">columns in Sales</span></span>

<span data-ttu-id="eaeb6-125">W aplikacji Sales dwie kolumny odzwierciedlają stan zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="eaeb6-125">In Sales, two columns indicate the status of the order.</span></span> <span data-ttu-id="eaeb6-126">Kolumny, które muszą być zmapowane, to **Stan** i **Przetwarzanie dokumentu**.</span><span class="sxs-lookup"><span data-stu-id="eaeb6-126">The columns that you must map are **Status** and **Processing Status**.</span></span>

<span data-ttu-id="eaeb6-127">Wyliczenie **Stan** określa ogólny stan zamówienia.</span><span class="sxs-lookup"><span data-stu-id="eaeb6-127">The **Status** enumeration specifies the overall status of the order.</span></span> <span data-ttu-id="eaeb6-128">Ma następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="eaeb6-128">It has the following values:</span></span>

- <span data-ttu-id="eaeb6-129">Aktywni</span><span class="sxs-lookup"><span data-stu-id="eaeb6-129">Active</span></span>
- <span data-ttu-id="eaeb6-130">Przesłany</span><span class="sxs-lookup"><span data-stu-id="eaeb6-130">Submitted</span></span>
- <span data-ttu-id="eaeb6-131">Realizacja</span><span class="sxs-lookup"><span data-stu-id="eaeb6-131">Fulfilled</span></span>
- <span data-ttu-id="eaeb6-132">Zafakturowane</span><span class="sxs-lookup"><span data-stu-id="eaeb6-132">Invoiced</span></span>
- <span data-ttu-id="eaeb6-133">Anulowane</span><span class="sxs-lookup"><span data-stu-id="eaeb6-133">Cancelled</span></span>

<span data-ttu-id="eaeb6-134">Wyliczenie **Stanu przetwarzania** zostało wprowadzone w taki sposób, aby można było dokładniej zamapować stan z Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="eaeb6-134">The **Processing Status** enumeration was introduced so that the status can be mapped more accurately with Supply Chain Management.</span></span>

<span data-ttu-id="eaeb6-135">W poniższej tabeli przedstawiono mapowanie **Stanu przetwarzania** w Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="eaeb6-135">The following table shows the mapping of **Processing Status** in Supply Chain Management.</span></span>

| <span data-ttu-id="eaeb6-136">Stan przetwarzania</span><span class="sxs-lookup"><span data-stu-id="eaeb6-136">Processing Status</span></span>   | <span data-ttu-id="eaeb6-137">Stan w Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="eaeb6-137">Status in Supply Chain Management</span></span> | <span data-ttu-id="eaeb6-138">Stan dokumentu w Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="eaeb6-138">Document Status in Supply Chain Management</span></span> |
|---------------------|-----------------------------------|--------------------------------------------|
| <span data-ttu-id="eaeb6-139">Aktywni</span><span class="sxs-lookup"><span data-stu-id="eaeb6-139">Active</span></span>              | <span data-ttu-id="eaeb6-140">Otwarte zamówienie</span><span class="sxs-lookup"><span data-stu-id="eaeb6-140">Open Order</span></span>                        | <span data-ttu-id="eaeb6-141">None</span><span class="sxs-lookup"><span data-stu-id="eaeb6-141">None</span></span>                                       |
| <span data-ttu-id="eaeb6-142">Potwierdzone</span><span class="sxs-lookup"><span data-stu-id="eaeb6-142">Confirmed</span></span>           | <span data-ttu-id="eaeb6-143">Otwarte zamówienie</span><span class="sxs-lookup"><span data-stu-id="eaeb6-143">Open Order</span></span>                        | <span data-ttu-id="eaeb6-144">Potwierdzenie</span><span class="sxs-lookup"><span data-stu-id="eaeb6-144">Confirmation</span></span>                               |
| <span data-ttu-id="eaeb6-145">Pobrane</span><span class="sxs-lookup"><span data-stu-id="eaeb6-145">Picked</span></span>              | <span data-ttu-id="eaeb6-146">Otwarte zamówienie</span><span class="sxs-lookup"><span data-stu-id="eaeb6-146">Open Order</span></span>                        | <span data-ttu-id="eaeb6-147">Lista pobrania</span><span class="sxs-lookup"><span data-stu-id="eaeb6-147">Picking List</span></span>                               |
| <span data-ttu-id="eaeb6-148">Częściowo dostarczone</span><span class="sxs-lookup"><span data-stu-id="eaeb6-148">Partially Delivered</span></span> | <span data-ttu-id="eaeb6-149">Otwarte zamówienie</span><span class="sxs-lookup"><span data-stu-id="eaeb6-149">Open Order</span></span>                        | <span data-ttu-id="eaeb6-150">Dokument dostawy</span><span class="sxs-lookup"><span data-stu-id="eaeb6-150">Packing Slip</span></span>                               |
| <span data-ttu-id="eaeb6-151">Dostarczone</span><span class="sxs-lookup"><span data-stu-id="eaeb6-151">Delivered</span></span>           | <span data-ttu-id="eaeb6-152">Dostarczone</span><span class="sxs-lookup"><span data-stu-id="eaeb6-152">Delivered</span></span>                         | <span data-ttu-id="eaeb6-153">Dokument dostawy</span><span class="sxs-lookup"><span data-stu-id="eaeb6-153">Packing Slip</span></span>                               |
| <span data-ttu-id="eaeb6-154">Częściowo zafakturowane</span><span class="sxs-lookup"><span data-stu-id="eaeb6-154">Partially Invoiced</span></span>  | <span data-ttu-id="eaeb6-155">Dostarczone</span><span class="sxs-lookup"><span data-stu-id="eaeb6-155">Delivered</span></span>                         | <span data-ttu-id="eaeb6-156">Faktura VAT</span><span class="sxs-lookup"><span data-stu-id="eaeb6-156">Invoice</span></span>                                    |
| <span data-ttu-id="eaeb6-157">Zafakturowane</span><span class="sxs-lookup"><span data-stu-id="eaeb6-157">Invoiced</span></span>            | <span data-ttu-id="eaeb6-158">Zafakturowane</span><span class="sxs-lookup"><span data-stu-id="eaeb6-158">Invoiced</span></span>                          | <span data-ttu-id="eaeb6-159">Faktura VAT</span><span class="sxs-lookup"><span data-stu-id="eaeb6-159">Invoice</span></span>                                    |
| <span data-ttu-id="eaeb6-160">Anulowane</span><span class="sxs-lookup"><span data-stu-id="eaeb6-160">Cancelled</span></span>           | <span data-ttu-id="eaeb6-161">Anulowane</span><span class="sxs-lookup"><span data-stu-id="eaeb6-161">Cancelled</span></span>                         | <span data-ttu-id="eaeb6-162">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="eaeb6-162">Not applicable</span></span>                             |

<span data-ttu-id="eaeb6-163">W poniższej tabeli przedstawiono mapowanie **Stanu przetwarzania** między Sales a Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="eaeb6-163">The following table shows the mapping of **Processing Status** between Sales and Supply Chain Management.</span></span>

| <span data-ttu-id="eaeb6-164">Stan przetwarzania</span><span class="sxs-lookup"><span data-stu-id="eaeb6-164">Processing Status</span></span>   | <span data-ttu-id="eaeb6-165">Stany w Sales</span><span class="sxs-lookup"><span data-stu-id="eaeb6-165">Status in Sales</span></span> | <span data-ttu-id="eaeb6-166">Stan w Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="eaeb6-166">Status in Supply Chain Management</span></span> |
|---------------------|-----------------|-----------------------------------|
| <span data-ttu-id="eaeb6-167">Aktywni</span><span class="sxs-lookup"><span data-stu-id="eaeb6-167">Active</span></span>              | <span data-ttu-id="eaeb6-168">Aktywni</span><span class="sxs-lookup"><span data-stu-id="eaeb6-168">Active</span></span>          | <span data-ttu-id="eaeb6-169">Otwarte zamówienie</span><span class="sxs-lookup"><span data-stu-id="eaeb6-169">Open Order</span></span>                        |
| <span data-ttu-id="eaeb6-170">Potwierdzone</span><span class="sxs-lookup"><span data-stu-id="eaeb6-170">Confirmed</span></span>           | <span data-ttu-id="eaeb6-171">Przesłany</span><span class="sxs-lookup"><span data-stu-id="eaeb6-171">Submitted</span></span>       | <span data-ttu-id="eaeb6-172">Otwarte zamówienie</span><span class="sxs-lookup"><span data-stu-id="eaeb6-172">Open Order</span></span>                        |
| <span data-ttu-id="eaeb6-173">Pobrane</span><span class="sxs-lookup"><span data-stu-id="eaeb6-173">Picked</span></span>              | <span data-ttu-id="eaeb6-174">Przesłany</span><span class="sxs-lookup"><span data-stu-id="eaeb6-174">Submitted</span></span>       | <span data-ttu-id="eaeb6-175">Otwarte zamówienie</span><span class="sxs-lookup"><span data-stu-id="eaeb6-175">Open Order</span></span>                        |
| <span data-ttu-id="eaeb6-176">Częściowo dostarczone</span><span class="sxs-lookup"><span data-stu-id="eaeb6-176">Partially Delivered</span></span> | <span data-ttu-id="eaeb6-177">Aktywni</span><span class="sxs-lookup"><span data-stu-id="eaeb6-177">Active</span></span>          | <span data-ttu-id="eaeb6-178">Otwarte zamówienie</span><span class="sxs-lookup"><span data-stu-id="eaeb6-178">Open Order</span></span>                        |
| <span data-ttu-id="eaeb6-179">Częściowo zafakturowane</span><span class="sxs-lookup"><span data-stu-id="eaeb6-179">Partially Invoiced</span></span>  | <span data-ttu-id="eaeb6-180">Aktywni</span><span class="sxs-lookup"><span data-stu-id="eaeb6-180">Active</span></span>          | <span data-ttu-id="eaeb6-181">Otwarte zamówienie</span><span class="sxs-lookup"><span data-stu-id="eaeb6-181">Open Order</span></span>                        |
| <span data-ttu-id="eaeb6-182">Częściowo zafakturowane</span><span class="sxs-lookup"><span data-stu-id="eaeb6-182">Partially Invoiced</span></span>  | <span data-ttu-id="eaeb6-183">Realizacja</span><span class="sxs-lookup"><span data-stu-id="eaeb6-183">Fulfilled</span></span>       | <span data-ttu-id="eaeb6-184">Dostarczone</span><span class="sxs-lookup"><span data-stu-id="eaeb6-184">Delivered</span></span>                         |
| <span data-ttu-id="eaeb6-185">Zafakturowane</span><span class="sxs-lookup"><span data-stu-id="eaeb6-185">Invoiced</span></span>            | <span data-ttu-id="eaeb6-186">Zafakturowane</span><span class="sxs-lookup"><span data-stu-id="eaeb6-186">Invoiced</span></span>        | <span data-ttu-id="eaeb6-187">Zafakturowane</span><span class="sxs-lookup"><span data-stu-id="eaeb6-187">Invoiced</span></span>                          |
| <span data-ttu-id="eaeb6-188">Anulowane</span><span class="sxs-lookup"><span data-stu-id="eaeb6-188">Cancelled</span></span>           | <span data-ttu-id="eaeb6-189">Anulowane</span><span class="sxs-lookup"><span data-stu-id="eaeb6-189">Cancelled</span></span>       | <span data-ttu-id="eaeb6-190">Anulowane</span><span class="sxs-lookup"><span data-stu-id="eaeb6-190">Cancelled</span></span>                         |

## <a name="setup"></a><span data-ttu-id="eaeb6-191">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="eaeb6-191">Setup</span></span>

<span data-ttu-id="eaeb6-192">Aby skonfigurować mapowanie dla kolumn stanu zamówienia sprzedaży, należy włączyć atrybuty **IsSOPIntegrationEnabled** i **isIntegrationUser**.</span><span class="sxs-lookup"><span data-stu-id="eaeb6-192">To set up the mapping for the sales order status columns, you must enable the **IsSOPIntegrationEnabled** and **isIntegrationUser** attributes.</span></span>

<span data-ttu-id="eaeb6-193">Aby włączyć atrybut **IsSOPIntegrationEnabled**, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="eaeb6-193">To enable the **IsSOPIntegrationEnabled** attribute, follow these steps.</span></span>

1. <span data-ttu-id="eaeb6-194">W przeglądarce przejdź do strony `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations`.</span><span class="sxs-lookup"><span data-stu-id="eaeb6-194">In a browser, go to `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations`.</span></span> <span data-ttu-id="eaeb6-195">Zastąp **\<test-name\>** łączem firmy w Sales.</span><span class="sxs-lookup"><span data-stu-id="eaeb6-195">Replace **\<test-name\>** with your company's link to Sales.</span></span>
2. <span data-ttu-id="eaeb6-196">Na otwartej stronie znajdź **organizationid** i zanotuj wartość.</span><span class="sxs-lookup"><span data-stu-id="eaeb6-196">On the page that is opened, find **organizationid**, and make a note of the value.</span></span>

    ![Znajdowanie organizationid](media/sales-map-orgid.png)

3. <span data-ttu-id="eaeb6-198">W Sales otwórz konsolę przeglądarki i uruchom następujący skrypt.</span><span class="sxs-lookup"><span data-stu-id="eaeb6-198">In Sales, open the browser console, and run following script.</span></span> <span data-ttu-id="eaeb6-199">Należy zastosować wartość **organizationid** z kroku 2.</span><span class="sxs-lookup"><span data-stu-id="eaeb6-199">Use the **organizationid** value from step 2.</span></span>

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

4. <span data-ttu-id="eaeb6-201">Upewnij się, że **IsSOPIntegrationEnabled** ma ustawioną wartość **true**.</span><span class="sxs-lookup"><span data-stu-id="eaeb6-201">Verify that **IsSOPIntegrationEnabled** is set to **true**.</span></span> <span data-ttu-id="eaeb6-202">Użyj adresu URL z kroku 1, aby sprawdzić wartość.</span><span class="sxs-lookup"><span data-stu-id="eaeb6-202">Use the URL from step 1 to check the value.</span></span>

    ![IsSOPIntegrationEnabled ma ustawioną wartość true](media/sales-map-integration-enabled.png)

<span data-ttu-id="eaeb6-204">Aby włączyć atrybut **isIntegrationUser**, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="eaeb6-204">To enable the **isIntegrationUser** attribute, follow these steps.</span></span>

1. <span data-ttu-id="eaeb6-205">W Sales przejdź do **Ustawienia \> Dostosowania \> Dostosuj system**, wybierz pozycję **Tabela użytkownika**, a następnie otwórz **Formularz \> Użytkownik**.</span><span class="sxs-lookup"><span data-stu-id="eaeb6-205">In Sales, go to **Setting \> Customization \> Customize the System**, select **User table**, and then open **Form \> User**.</span></span>

    ![Otwieranie formularza użytkownika](media/sales-map-user.png)

2. <span data-ttu-id="eaeb6-207">W Eksploratorze pól znajdź **Tryb użytkownika integracyjnego** i kliknij go dwukrotnie, aby dodać go do formularza.</span><span class="sxs-lookup"><span data-stu-id="eaeb6-207">In Field Explorer, find **Integration user mode**, and double-click it to add it to the form.</span></span> <span data-ttu-id="eaeb6-208">Zapisz zmiany.</span><span class="sxs-lookup"><span data-stu-id="eaeb6-208">Save your change.</span></span>

    ![Dodanie kolumny trybu użytkownika integracyjnego do formularza](media/sales-map-field-explorer.png)

3. <span data-ttu-id="eaeb6-210">W module Sprzedaż należy posłużyć do **Ustawienia \> Zabezpieczenia \> Użytkownicy** i zmień widok z **Włączeni użytkownicy** na **Uzytkownicy aplikacji**.</span><span class="sxs-lookup"><span data-stu-id="eaeb6-210">In Sales, go to **Setting \> Security \> Users**, and change the view from **Enabled Users** to **Application Users**.</span></span>

    ![Zmienianie widoku z Włączonych użytkowników na Użytkowników aplikacji](media/sales-map-enabled-users.png)

4. <span data-ttu-id="eaeb6-212">Wybierz dwa wpisy dla **DualWrite IntegrationUser**.</span><span class="sxs-lookup"><span data-stu-id="eaeb6-212">Select the two entries for **DualWrite IntegrationUser**.</span></span>

    ![Lista użytkowników aplikacji](media/sales-map-user-mode.png)

5. <span data-ttu-id="eaeb6-214">Zmień wartość w kolumnie **Tryb użytkownika integracyjnego** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="eaeb6-214">Change the value of the **Integration user mode** column to **Yes**.</span></span>

    ![Zmiana wartości kolumny Tryb użytkownika integracji](media/sales-map-user-mode-yes.png)

<span data-ttu-id="eaeb6-216">Twoje zamówienia sprzedaży są teraz zamapowane.</span><span class="sxs-lookup"><span data-stu-id="eaeb6-216">Your sales orders are now mapped.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]