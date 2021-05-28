---
title: Nie jest generowany załącznik
description: Ten temat zawiera informacje na temat rozwiązywania problemów, które mogą pomóc w przypadku niewygenerowania załącznika, który powinien być generowany.
author: qire
ms.date: 04/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: ba23b597b1d7d283b99638fb7d5d91da00afb09c
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018764"
---
# <a name="voucher-isnt-generated"></a><span data-ttu-id="36ed2-103">Nie jest generowany załącznik</span><span class="sxs-lookup"><span data-stu-id="36ed2-103">Voucher isn't generated</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="36ed2-104">Jeśli załącznik powinien być generowany, ale na stronie **Transakcje na załączniku** nie są wyświetlane żadne załączniki, w celu rozwiązania tego problemu wykonaj kroki opisane w poniższych sekcjach.</span><span class="sxs-lookup"><span data-stu-id="36ed2-104">If a voucher should be generated, but the **Voucher transactions** page doesn't show any vouchers, follow the steps in the following sections as required to troubleshoot this issue.</span></span>

<span data-ttu-id="36ed2-105">[![Na stronie Transakcje na załączniku nie ma załączników](./media/voucher-not-generated-Picture1.png)](./media/voucher-not-generated-Picture1.png)</span><span class="sxs-lookup"><span data-stu-id="36ed2-105">[![Voucher transactions page that has no vouchers](./media/voucher-not-generated-Picture1.png)](./media/voucher-not-generated-Picture1.png)</span></span>

## <a name="check-the-tax-applicability"></a><span data-ttu-id="36ed2-106">Sprawdzanie, czy podlega opodatkowaniu</span><span class="sxs-lookup"><span data-stu-id="36ed2-106">Check the tax applicability</span></span>

1. <span data-ttu-id="36ed2-107">Przejdź do lokalizacji **Podatek** \> **Zadania okresowe** \> **Zapisy w arkuszu księgi podrzędnej nie są jeszcze przeniesione**.</span><span class="sxs-lookup"><span data-stu-id="36ed2-107">Go to **Tax** \> **Periodic tasks** \> **Subledger journal entries not yet transferred**.</span></span>
2. <span data-ttu-id="36ed2-108">Jeśli istnieje rekord arkusza, zaznacz go, a następnie wybierz opcję **Przenieś teraz**.</span><span class="sxs-lookup"><span data-stu-id="36ed2-108">If there is a journal record, select it, and then select **Transfer now**.</span></span>

    <span data-ttu-id="36ed2-109">[![Przycisk Przenieś teraz na stronie Zapisy w arkuszu księgi podrzędnej nie zostały jeszcze przeniesione](./media/voucher-not-generated-Picture2.png)](./media/voucher-not-generated-Picture2.png)</span><span class="sxs-lookup"><span data-stu-id="36ed2-109">[![Transfer now button on the Subledger journal entries not yet transferred page](./media/voucher-not-generated-Picture2.png)](./media/voucher-not-generated-Picture2.png)</span></span>

3. <span data-ttu-id="36ed2-110">Otwórz ponownie stronę **Transakcje na załączniku**, aby sprawdzić, czy załącznik został wygenerowany.</span><span class="sxs-lookup"><span data-stu-id="36ed2-110">Open the **Voucher transactions** page again to see whether the voucher was generated.</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="36ed2-111">Określanie, czy dostosowanie istnieje</span><span class="sxs-lookup"><span data-stu-id="36ed2-111">Determine whether customization exists</span></span>

<span data-ttu-id="36ed2-112">Jeśli zostały wykonane kroki w poprzedniej sekcji, ale nie znaleziono problemu, określ, czy istnieje dostosowanie.</span><span class="sxs-lookup"><span data-stu-id="36ed2-112">If you've completed the steps in the previous section but have found no issue, determine whether customization exists.</span></span> <span data-ttu-id="36ed2-113">Jeśli nie istnieją żadne dostosowania, utwórz żądanie obsługi do firmy Microsoft, aby uzyskać dalszą pomoc techniczną.</span><span class="sxs-lookup"><span data-stu-id="36ed2-113">If no customization exists, create a Microsoft service request for further support.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
