---
title: "Konta księgowania likwidacji środków trwałych"
description: "W tym artykule wyjaśniono, jak w księdze głównej skonfigurować konta księgowania operacji likwidacji środków trwałych."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3461
ms.assetid: dfdc0730-e030-48cc-8d93-15bdc7b23776
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 0129eae177d44100b09c2b7bce553dd5bde5ce0c
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="fixed-asset-disposal-posting-accounts"></a><span data-ttu-id="90670-103">Konta księgowania likwidacji środków trwałych</span><span class="sxs-lookup"><span data-stu-id="90670-103">Fixed asset disposal posting accounts</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="90670-104">W tym artykule wyjaśniono, jak w księdze głównej skonfigurować konta księgowania operacji likwidacji środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="90670-104">This article explains how to set up general ledger posting accounts for disposing of assets.</span></span>

<span data-ttu-id="90670-105">Na stronie Profile księgowania środków trwałych na skróconej karcie Konta księgowe wybierz Likwidacja — sprzedaż i Likwidacja — odpadki, aby ustawić księgowanie do księgi.</span><span class="sxs-lookup"><span data-stu-id="90670-105">In the Fixed asset posting profiles page, on the Ledger accounts FastTab, select Disposal - sale and Disposal - scrap to set up postings to the ledger.</span></span>

<span data-ttu-id="90670-106">Dla obu typów transakcji na konto księgowe wpływa wartość likwidacji środka trwałego.</span><span class="sxs-lookup"><span data-stu-id="90670-106">For both transaction types, the ledger account is credited for the disposal value of the fixed asset.</span></span> <span data-ttu-id="90670-107">Księgowanie po stronie debetowej obciąży konto przeciwstawne, którym może być na przykład konto bankowe.</span><span class="sxs-lookup"><span data-stu-id="90670-107">The debit is posted to an offset account, which might be, for example, a bank account.</span></span> <span data-ttu-id="90670-108">Jeśli środek trwały zostanie sprzedany odbiorcy, zamiast konta przeciwstawnego użyte zostanie konto odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="90670-108">If a fixed asset is sold to a customer, the customer account is used instead of the offset account.</span></span>

<span data-ttu-id="90670-109">Kliknij Likwidacja, następnie kliknij Sprzedaż lub Odpadki, a następnie skonfiguruj szczegóły kont, aby wycofać wartość księgową netto środka trwałego.</span><span class="sxs-lookup"><span data-stu-id="90670-109">Click Disposal and then click Sale or Scrap, and then set up detailed accounts to reverse the net book value of the fixed asset.</span></span> <span data-ttu-id="90670-110">Można również wprowadzić informacje w polach Księguj wartość i Typ wartości sprzedaży na stronie Parametry likwidacji.</span><span class="sxs-lookup"><span data-stu-id="90670-110">You can also enter information in the Post value and Sales value type fields in the Disposal parameters page.</span></span> 

<span data-ttu-id="90670-111">Transakcja likwidacji środka trwałego w puli środków trwałych o niskiej wartości zmniejsza wartość księgową netto tej puli tylko o kwotę danej likwidacji.</span><span class="sxs-lookup"><span data-stu-id="90670-111">The disposal transaction for an asset in a low-value pool reduces the net book value of the low-value pool by the disposed amount only.</span></span> <span data-ttu-id="90670-112">Jeśli jednak wartość sprzedaży takiego środka trwałego przekracza wartość księgową netto wspomnianej puli, wartość księgowa netto zostanie zmniejszona do zera.</span><span class="sxs-lookup"><span data-stu-id="90670-112">However, when the sale of an asset is exceeds the net book value of the low-value pool, the net book value is reduced to zero.</span></span>






