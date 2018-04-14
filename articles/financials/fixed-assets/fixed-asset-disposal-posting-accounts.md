---
title: "Konta księgowania likwidacji środków trwałych"
description: "W tym temacie wyjaśniono, jak w księdze głównej skonfigurować konta księgowania operacji likwidacji środków trwałych."
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
ms.search.scope: Core, Operations
ms.custom: 3461
ms.assetid: dfdc0730-e030-48cc-8d93-15bdc7b23776
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 20bb2a046eba54cf59d6029d4278ffd7a1d4736f
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---

# <a name="fixed-asset-disposal-posting-accounts"></a><span data-ttu-id="5e549-103">Konta księgowania likwidacji środków trwałych</span><span class="sxs-lookup"><span data-stu-id="5e549-103">Fixed asset disposal posting accounts</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="5e549-104">W tym temacie wyjaśniono, jak w księdze głównej skonfigurować konta księgowania operacji likwidacji środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="5e549-104">This topic explains how to set up general ledger posting accounts for disposing of assets.</span></span>

<span data-ttu-id="5e549-105">Na stronie Profile księgowania środków trwałych na skróconej karcie Konta księgowe wybierz Likwidacja — sprzedaż i Likwidacja — odpadki, aby ustawić księgowanie do księgi.</span><span class="sxs-lookup"><span data-stu-id="5e549-105">In the Fixed asset posting profiles page, on the Ledger accounts FastTab, select Disposal - sale and Disposal - scrap to set up postings to the ledger.</span></span>

<span data-ttu-id="5e549-106">Dla obu typów transakcji na konto księgowe wpływa wartość likwidacji środka trwałego.</span><span class="sxs-lookup"><span data-stu-id="5e549-106">For both transaction types, the ledger account is credited for the disposal value of the fixed asset.</span></span> <span data-ttu-id="5e549-107">Księgowanie po stronie debetowej obciąży konto przeciwstawne, którym może być na przykład konto bankowe.</span><span class="sxs-lookup"><span data-stu-id="5e549-107">The debit is posted to an offset account, which might be, for example, a bank account.</span></span> <span data-ttu-id="5e549-108">Jeśli środek trwały zostanie sprzedany odbiorcy, zamiast konta przeciwstawnego użyte zostanie konto odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="5e549-108">If a fixed asset is sold to a customer, the customer account is used instead of the offset account.</span></span>

<span data-ttu-id="5e549-109">Kliknij Likwidacja, następnie kliknij Sprzedaż lub Odpadki, a następnie skonfiguruj szczegóły kont, aby wycofać wartość księgową netto środka trwałego.</span><span class="sxs-lookup"><span data-stu-id="5e549-109">Click Disposal and then click Sale or Scrap, and then set up detailed accounts to reverse the net book value of the fixed asset.</span></span> <span data-ttu-id="5e549-110">Można również wprowadzić informacje w polach Księguj wartość i Typ wartości sprzedaży na stronie Parametry likwidacji.</span><span class="sxs-lookup"><span data-stu-id="5e549-110">You can also enter information in the Post value and Sales value type fields in the Disposal parameters page.</span></span> 

<span data-ttu-id="5e549-111">Transakcja likwidacji środka trwałego w puli środków trwałych o niskiej wartości zmniejsza wartość księgową netto tej puli tylko o kwotę danej likwidacji.</span><span class="sxs-lookup"><span data-stu-id="5e549-111">The disposal transaction for an asset in a low-value pool reduces the net book value of the low-value pool by the disposed amount only.</span></span> <span data-ttu-id="5e549-112">Jeśli jednak wartość sprzedaży takiego środka trwałego przekracza wartość księgową netto wspomnianej puli, wartość księgowa netto zostanie zmniejszona do zera.</span><span class="sxs-lookup"><span data-stu-id="5e549-112">However, when the sale of an asset exceeds the net book value of the low-value pool, the net book value is reduced to zero.</span></span>






