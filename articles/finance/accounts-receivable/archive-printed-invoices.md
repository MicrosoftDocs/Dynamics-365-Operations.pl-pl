---
title: Archiwizowanie wydrukowanych faktur dla odbiorcy z numerami skrótów
description: W tym temacie wyjaśniono, jak włączyć archiwizację w celu przechowywania wydrukowanych faktur dla odbiorcy z numerami skrótów.
author: ilyako
ms.date: 03/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-05
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 5b0305381ee709ce52b18d171a1ea274e2126cce
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5827705"
---
# <a name="archive-printed-customer-invoices-with-hash-numbers"></a><span data-ttu-id="8b644-103">Archiwizowanie wydrukowanych faktur dla odbiorcy z numerami skrótów</span><span class="sxs-lookup"><span data-stu-id="8b644-103">Archive printed customer invoices with hash numbers</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="8b644-104">W niektórych krajach istnieje prawny wymóg przechowywania obliczonych skrótów numerów skrótów w systemie wraz z wydrukami niektórych dokumentów.</span><span class="sxs-lookup"><span data-stu-id="8b644-104">In some countries, there is a legal requirement to store calculated hash numbers in the system together with printouts of some documents.</span></span> <span data-ttu-id="8b644-105">Wartości skrótów mogą być używane w raportach dla urzędów i podczas inspekcji.</span><span class="sxs-lookup"><span data-stu-id="8b644-105">Hash numbers can be used for reporting to authorities and during audits.</span></span>

<span data-ttu-id="8b644-106">W tym temacie wyjaśniono, jak skonfigurować archiwizację w celu przechowywania wydrukowanych faktur dla odbiorcy z numerami skrótów.</span><span class="sxs-lookup"><span data-stu-id="8b644-106">This topic explains how to configure archiving in order to store printed customer invoices with hash numbers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8b644-107">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="8b644-107">Prerequisites</span></span>

- <span data-ttu-id="8b644-108">W obszarze roboczym **Zarządzanie funkcjami** włącz tę funkcję, aby **Zarchiwizować wydrukowane faktury dla odbiorcy za pomocą wartości skrótów**.</span><span class="sxs-lookup"><span data-stu-id="8b644-108">In the **Feature management** workspace, turn on the feature, **Archive printed customer invoices with hash numbers**.</span></span> <span data-ttu-id="8b644-109">Aby uzyskać więcej informacji, zapoznaj się z tematem [Zarządzanie funkcjami — omówienie](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8b644-109">For more information, see [Feature management overview](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>
- <span data-ttu-id="8b644-110">Skonfiguruj formaty do wydrukowania wymaganych dokumentów w **Zarządzanie drukowaniem**.</span><span class="sxs-lookup"><span data-stu-id="8b644-110">Configure the printable formats of required documents in **Print management**.</span></span>

<span data-ttu-id="8b644-111">Ta funkcja ma zastosowanie do następujących dokumentów.</span><span class="sxs-lookup"><span data-stu-id="8b644-111">This functionality is applicable to the following documents.</span></span>

<span data-ttu-id="8b644-112">**Rozrachunki z odbiorcami**</span><span class="sxs-lookup"><span data-stu-id="8b644-112">**Accounts receivable**</span></span>
- <span data-ttu-id="8b644-113">Faktura dla odbiorcy</span><span class="sxs-lookup"><span data-stu-id="8b644-113">Customer invoice</span></span>
- <span data-ttu-id="8b644-114">Odbiorca faktury korygującej</span><span class="sxs-lookup"><span data-stu-id="8b644-114">Customer credit note</span></span>
- <span data-ttu-id="8b644-115">Faktura niezależna</span><span class="sxs-lookup"><span data-stu-id="8b644-115">Free text invoice</span></span>
- <span data-ttu-id="8b644-116">Niezależna faktura korygująca</span><span class="sxs-lookup"><span data-stu-id="8b644-116">Free text credit note</span></span>

<span data-ttu-id="8b644-117">**Zarządzanie projektami i ich księgowanie**</span><span class="sxs-lookup"><span data-stu-id="8b644-117">**Project management and accounting**</span></span>
- <span data-ttu-id="8b644-118">Faktura projektu</span><span class="sxs-lookup"><span data-stu-id="8b644-118">Project invoice</span></span>
- <span data-ttu-id="8b644-119">Projektowanie faktury korygującej</span><span class="sxs-lookup"><span data-stu-id="8b644-119">Project credit note</span></span>

## <a name="configure-customer-master-data"></a><span data-ttu-id="8b644-120">Konfigurowanie danych głównych odbiorców</span><span class="sxs-lookup"><span data-stu-id="8b644-120">Configure customer master data</span></span>
<span data-ttu-id="8b644-121">Aby skonfigurować dane odbiorcy, wykonaj poniższe kroki, a następnie włącz możliwość automatycznego zapisywania drukowanych faktur jako załączników.</span><span class="sxs-lookup"><span data-stu-id="8b644-121">Complete the following steps to configure customer data and turn on the ability to automatically save printed invoices as attachments.</span></span>

1. <span data-ttu-id="8b644-122">Wybierz kolejno opcje **Rozrachunki z odbiorcami** > **Wszyscy odbiorcy**.</span><span class="sxs-lookup"><span data-stu-id="8b644-122">Go to **Accounts receivable** > **All customers**.</span></span> 
2. <span data-ttu-id="8b644-123">Wybierz odbiorcy, a na skróconej karcie **Faktura i dostawa** w sekcji **E-INVOCE** w polu **załącznika do faktury elektronicznej** wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="8b644-123">Select a customer, and on the **Invoice and delivery** FastTab, in the **E-INVOCE** section, in the **eInvoice attachment** field, select **Yes**.</span></span>

## <a name="print-invoices"></a><span data-ttu-id="8b644-124">Drukowanie faktur</span><span class="sxs-lookup"><span data-stu-id="8b644-124">Print invoices</span></span>
<span data-ttu-id="8b644-125">Można księgć i drukować dowolny tekst dowolny, fakturę odbiorcy i fakturę korygową projektu dla odbiorcy skonfigurowanego w poprzedniej procedurze.</span><span class="sxs-lookup"><span data-stu-id="8b644-125">You can post and print any free text, customer, and project invoice or credit note for the customer configured in the previous procedure.</span></span>

<span data-ttu-id="8b644-126">Otwórz stronę **Załączniki** dla wydrukowanej faktury.</span><span class="sxs-lookup"><span data-stu-id="8b644-126">Open the **Attachments** page for the printed invoice.</span></span> <span data-ttu-id="8b644-127">Na skróconej karcie **Załączniki**, w grupie pól **Dodatkowe szczegóły**, w polu **Numer skrótu dokumentu** znajdź przechowywany numer skrótu obliczony dla wydrukowanej faktury.</span><span class="sxs-lookup"><span data-stu-id="8b644-127">On the **Attachment** FastTab, in the **Additional details** field group, in **Document hash number** field, find the stored hash number calculated for the printed invoice.</span></span>

![Numer skrótu załącznika](media/attach-hash-num.jpg)

