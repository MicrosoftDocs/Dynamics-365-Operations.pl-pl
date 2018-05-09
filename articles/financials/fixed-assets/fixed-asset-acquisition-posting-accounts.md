---
title: "Konta księgowania nabycia środków trwałych"
description: "W tym artykule wyjaśniono, jak w księdze głównej skonfigurować konta księgowania operacji nabycia środków trwałych."
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
ms.custom: 23021
ms.assetid: d7e86f72-95db-4423-9b04-761e9536a959
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: ec23f6a70200aeac50d47a0b0c2f985d9d29c35c
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---

# <a name="fixed-asset-acquisition-posting-accounts"></a><span data-ttu-id="4fab1-103">Konta księgowania nabycia środków trwałych</span><span class="sxs-lookup"><span data-stu-id="4fab1-103">Fixed asset acquisition posting accounts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4fab1-104">W tym artykule wyjaśniono, jak w księdze głównej skonfigurować konta księgowania operacji nabycia środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="4fab1-104">This article explains how to set up general ledger posting accounts for acquiring assets.</span></span>

<span data-ttu-id="4fab1-105">Konta używane do księgowani nabycia środków trwałych mogą się od siebie różnić w zależności od metody używanej do pozyskiwania składników aktywów.</span><span class="sxs-lookup"><span data-stu-id="4fab1-105">Accounts used for posting fixed asset acquisitions may vary depending upon the method used to acquire the asset.</span></span> <span data-ttu-id="4fab1-106">Na stronie Profile księgowania środków trwałych na karcie Konta księgowe należy wybrać opcje Nabycie i Korekta wartości początkowej, aby skonfigurować księgowanie kont środków trwałych do księgi.</span><span class="sxs-lookup"><span data-stu-id="4fab1-106">On the Fixed asset posting profiles page, on the Ledger accounts tab, select Acquisition and Acquisition adjustment to set up fixed asset accounts to post to the ledger.</span></span> 

<span data-ttu-id="4fab1-107">W arkuszach i w zamówieniach zakupu Konto księgowe jest zwykle kontem bilansowym, na którym wartość nabycia nowego środka trwałego księgowana jest po stronie debetowej.</span><span class="sxs-lookup"><span data-stu-id="4fab1-107">In journals and on purchase orders, Ledger account is typically the balance sheet account, where the acquisition value of the new fixed asset is debited.</span></span> <span data-ttu-id="4fab1-108">To konto nie jest wyświetlane w arkuszu i nie może zostać zastąpione w transakcjach.</span><span class="sxs-lookup"><span data-stu-id="4fab1-108">This account is not displayed in the journal and cannot be replaced in transactions.</span></span> 

<span data-ttu-id="4fab1-109">Konto przeciwstawne jest również kontem bilansowym.</span><span class="sxs-lookup"><span data-stu-id="4fab1-109">Offset account is also a balance sheet account.</span></span> <span data-ttu-id="4fab1-110">W arkuszu finansowym i w arkuszu środków trwałych to konto będzie często kontem bankowym używanym do dokonywania płatności za nabycie środka trwałego.</span><span class="sxs-lookup"><span data-stu-id="4fab1-110">In the general journal and in the fixed assets journal, this account often will be the bank account that is used to pay for the acquisition of the asset.</span></span> <span data-ttu-id="4fab1-111">Konto przeciwstawne jest domyślnym kontem, które jest zalecane w arkuszach.</span><span class="sxs-lookup"><span data-stu-id="4fab1-111">The offset account is a default account, which is suggested in the journals.</span></span> <span data-ttu-id="4fab1-112">Można je zmienić w arkuszu na dowolne inne konto z planu kont lub na konto dostawcy, jeśli od niego został zakupiony środek trwały.</span><span class="sxs-lookup"><span data-stu-id="4fab1-112">It can be changed in the journal to any other account from the chart of accounts or to a vendor account, if the fixed asset was purchase from a vendor.</span></span> 

<span data-ttu-id="4fab1-113">Jeśli opcje Arkusz faktur lub Zamówienia zakupu w formularzu Rozrachunki z dostawcami są używane do nabywania środków trwałych, konto przeciwstawne dla transakcji środków trwałych zostanie zastąpione kontem dostawcy wybranym dla transakcji.</span><span class="sxs-lookup"><span data-stu-id="4fab1-113">When Invoice journal or Purchase orders in Accounts payable are used for fixed asset acquisitions, the offset account for the fixed asset transaction is replaced by the vendor account that is selected for the transaction.</span></span>

<span data-ttu-id="4fab1-114">Dla transakcji nabycia zaksięgowanych przy użyciu arkusza Zapasy do środków trwałych w Księdze głównej środki trwałe nie są kupowane z zewnętrznych źródeł, a przenoszone z własnych zapasów firmy.</span><span class="sxs-lookup"><span data-stu-id="4fab1-114">For acquisitions posted using the Inventory to fixed assets journal in General ledger, the fixed asset is not bought from external sources, but transferred from the company's own inventory.</span></span> <span data-ttu-id="4fab1-115">Dlatego też konto przeciwstawne jest kontem wydań z magazynu dla towarów magazynowych w opcji Zarządzanie zapasami.</span><span class="sxs-lookup"><span data-stu-id="4fab1-115">Therefore, the offset account is an inventory issue account for the inventory item in Inventory management.</span></span>

<span data-ttu-id="4fab1-116">Aby uzyskać więcej informacji, zobacz [Nabywanie środków trwałych za pomocą zaopatrzenia](acquire-assets-procurement.md).</span><span class="sxs-lookup"><span data-stu-id="4fab1-116">For more information, see [Acquire assets through procurement](acquire-assets-procurement.md).</span></span>




