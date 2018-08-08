---
title: "Korekta faktury niezależnej"
description: "W tym artykule wyjaśniono, jak poprawić zaksięgowaną fakturę niezależną i wystawić ją ponownie jako skorygowaną fakturę."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: c8c1b90b7b2c02a53e53cc13d70445a237b126d4
ms.contentlocale: pl-pl
ms.lasthandoff: 08/07/2018

---

# <a name="correct-a-free-text-invoice"></a><span data-ttu-id="2cbab-103">Korekta faktury niezależnej</span><span class="sxs-lookup"><span data-stu-id="2cbab-103">Correct a free text invoice</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2cbab-104">W tym artykule wyjaśniono, jak poprawić zaksięgowaną fakturę niezależną i wystawić ją ponownie jako skorygowaną fakturę.</span><span class="sxs-lookup"><span data-stu-id="2cbab-104">This article explains how to correct a free text invoice that has been posted and reissue it as a corrected invoice.</span></span>

<span data-ttu-id="2cbab-105">Aby skorygować fakturę niezależną, która została zaksięgowana, otwórz ją.</span><span class="sxs-lookup"><span data-stu-id="2cbab-105">To correct a free text invoice that has already been posted, open the posted free text invoice.</span></span> <span data-ttu-id="2cbab-106">Na stronie **Faktura** wybierz opcję **Anuluj**, a następnie wybierz opcję **Poprawianie faktury**.</span><span class="sxs-lookup"><span data-stu-id="2cbab-106">On the **Invoice** page, select **Cancel**, and then select **Correct invoice**.</span></span> <span data-ttu-id="2cbab-107">Wybierz kod przyczyny, dodaj komentarz i wybierz datę dla nowej, poprawionej faktury.</span><span class="sxs-lookup"><span data-stu-id="2cbab-107">Select a reason code, add comments, and select the date for new corrected invoice.</span></span> <span data-ttu-id="2cbab-108">Możesz zmodyfikować skorygowaną fakturę i zaksięgować ją.</span><span class="sxs-lookup"><span data-stu-id="2cbab-108">You can modify the corrected invoice, and post it.</span></span> 

<span data-ttu-id="2cbab-109">Podczas księgowania skorygowanej faktury tworzona jest faktura anulująca dla kwoty po stronie kredytowej, która jest równa kwocie pierwotnej faktury.</span><span class="sxs-lookup"><span data-stu-id="2cbab-109">When you post the corrected invoice, a canceling invoice is created for a credit amount that equals the original invoice amount.</span></span> <span data-ttu-id="2cbab-110">W efekcie saldo połączone oryginalnej faktury i faktury anulującej wynosi 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="2cbab-110">Therefore, the combined balance of the original invoice and the canceling invoice is 0 (zero).</span></span> <span data-ttu-id="2cbab-111">Faktura anulująca jest księgowana względem oryginalne faktury.</span><span class="sxs-lookup"><span data-stu-id="2cbab-111">The canceling invoice is settled against the original invoice.</span></span> 

<span data-ttu-id="2cbab-112">Po zaksięgowaniu skorygowanej faktury, masz trzy faktury:</span><span class="sxs-lookup"><span data-stu-id="2cbab-112">After you post the corrected invoice, you will have three invoices:</span></span>

-   <span data-ttu-id="2cbab-113">**Oryginalna faktura** — faktura, która zawiera informacje, które korygujesz.</span><span class="sxs-lookup"><span data-stu-id="2cbab-113">**Original invoice** – The invoice that includes the information that you're correcting.</span></span>
-   <span data-ttu-id="2cbab-114">**Faktura anulująca** — wygenerowana przez system faktura kredytowa, utworzona w celu anulowania faktury, która jako ostatnia została skorygowana.</span><span class="sxs-lookup"><span data-stu-id="2cbab-114">**Canceling invoice** – The system-generated credit invoice that was created to cancel the invoice that was most recently corrected.</span></span>
-   <span data-ttu-id="2cbab-115">**Skorygowana faktura** — faktura, która zawiera informacje faktury skorygowanej.</span><span class="sxs-lookup"><span data-stu-id="2cbab-115">**Corrected invoice** – The invoice that contains the corrected invoice information.</span></span>

<span data-ttu-id="2cbab-116">Faktury anulujące i korygujące można określić na dwa sposoby:</span><span class="sxs-lookup"><span data-stu-id="2cbab-116">You can identify canceling and correcting invoices in two ways:</span></span>

-   <span data-ttu-id="2cbab-117">Strona **Wszystkie faktury niezależne** zawiera kolumnę **korekta**, na której widać, które faktury są fakturami anulującymi, a które są fakturami korygującymi.</span><span class="sxs-lookup"><span data-stu-id="2cbab-117">The **All free text invoices** page includes a **Correction** column, where you can see which invoices are canceling invoices and corrected invoices.</span></span>
-   <span data-ttu-id="2cbab-118">Nagłówek faktury niezależnej pokazuje stan **Anulowanie faktury „\[numer faktury\]”** lub **Skorygowana faktura „\[numer faktury\]”**.</span><span class="sxs-lookup"><span data-stu-id="2cbab-118">The header of the free text invoice shows a status of **Cancelling invoice '\[invoice number\]'** or **Corrected invoice '\[invoice number\]'**.</span></span>

> [!NOTE]
> <span data-ttu-id="2cbab-119">Ta funkcja jest dostępna tylko, jeśli wybrany jest klucz konfiguracji **Poprawianie faktury niezależnej**.</span><span class="sxs-lookup"><span data-stu-id="2cbab-119">This feature is available only if the **Free text invoice correction** configuration key is selected.</span></span>




