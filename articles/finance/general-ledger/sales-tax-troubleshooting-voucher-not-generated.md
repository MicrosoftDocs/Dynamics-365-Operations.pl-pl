---
title: Nie jest generowany załącznik
description: Ten temat zawiera informacje na temat rozwiązywania problemów, które mogą pomóc w przypadku niewygenerowania załącznika, który powinien być generowany.
author: qire
manager: beya
ms.date: 04/13/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: eafc9110ec58be5083569188d59b67a62e86c85d
ms.sourcegitcommit: 57668404d61359b33e0c0280f2f7c4eb829b1ed2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/27/2021
ms.locfileid: "5947694"
---
# <a name="voucher-isnt-generated"></a><span data-ttu-id="89ca5-103">Nie jest generowany załącznik</span><span class="sxs-lookup"><span data-stu-id="89ca5-103">Voucher isn't generated</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="89ca5-104">Jeśli załącznik powinien być generowany, ale na stronie **Transakcje na załączniku** nie są wyświetlane żadne załączniki, w celu rozwiązania tego problemu wykonaj kroki opisane w poniższych sekcjach.</span><span class="sxs-lookup"><span data-stu-id="89ca5-104">If a voucher should be generated, but the **Voucher transactions** page doesn't show any vouchers, follow the steps in the following sections as required to troubleshoot this issue.</span></span>

<span data-ttu-id="89ca5-105">[![Na stronie Transakcje na załączniku nie ma załączników](./media/voucher-not-generated-Picture1.png)](./media/voucher-not-generated-Picture1.png)</span><span class="sxs-lookup"><span data-stu-id="89ca5-105">[![Voucher transactions page that has no vouchers](./media/voucher-not-generated-Picture1.png)](./media/voucher-not-generated-Picture1.png)</span></span>

## <a name="check-the-tax-applicability"></a><span data-ttu-id="89ca5-106">Sprawdzanie, czy podlega opodatkowaniu</span><span class="sxs-lookup"><span data-stu-id="89ca5-106">Check the tax applicability</span></span>

1. <span data-ttu-id="89ca5-107">Przejdź do lokalizacji **Podatek** \> **Zadania okresowe** \> **Zapisy w arkuszu księgi podrzędnej nie są jeszcze przeniesione**.</span><span class="sxs-lookup"><span data-stu-id="89ca5-107">Go to **Tax** \> **Periodic tasks** \> **Subledger journal entries not yet transferred**.</span></span>
2. <span data-ttu-id="89ca5-108">Jeśli istnieje rekord arkusza, zaznacz go, a następnie wybierz opcję **Przenieś teraz**.</span><span class="sxs-lookup"><span data-stu-id="89ca5-108">If there is a journal record, select it, and then select **Transfer now**.</span></span>

    <span data-ttu-id="89ca5-109">[![Przycisk Przenieś teraz na stronie Zapisy w arkuszu księgi podrzędnej nie zostały jeszcze przeniesione](./media/voucher-not-generated-Picture2.png)](./media/voucher-not-generated-Picture2.png)</span><span class="sxs-lookup"><span data-stu-id="89ca5-109">[![Transfer now button on the Subledger journal entries not yet transferred page](./media/voucher-not-generated-Picture2.png)](./media/voucher-not-generated-Picture2.png)</span></span>

3. <span data-ttu-id="89ca5-110">Otwórz ponownie stronę **Transakcje na załączniku**, aby sprawdzić, czy załącznik został wygenerowany.</span><span class="sxs-lookup"><span data-stu-id="89ca5-110">Open the **Voucher transactions** page again to see whether the voucher was generated.</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="89ca5-111">Określanie, czy dostosowanie istnieje</span><span class="sxs-lookup"><span data-stu-id="89ca5-111">Determine whether customization exists</span></span>

<span data-ttu-id="89ca5-112">Jeśli zostały wykonane kroki w poprzedniej sekcji, ale nie znaleziono problemu, określ, czy istnieje dostosowanie.</span><span class="sxs-lookup"><span data-stu-id="89ca5-112">If you've completed the steps in the previous section but have found no issue, determine whether customization exists.</span></span> <span data-ttu-id="89ca5-113">Jeśli nie istnieją żadne dostosowania, utwórz żądanie obsługi do firmy Microsoft, aby uzyskać dalszą pomoc techniczną.</span><span class="sxs-lookup"><span data-stu-id="89ca5-113">If no customization exists, create a Microsoft service request for further support.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
