---
title: "Księgowanie za pomocą ksiąg pochodnych"
description: "W tym artykule opisano sposób korzystania z ksiąg pochodnych."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetBookTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 3421
ms.assetid: f5187c21-eec5-4148-b178-b8a5feff7f23
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 94eb82936da2a51a25105b26723088fb7dee9ae5
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="post-with-derived-books"></a><span data-ttu-id="30f1e-103">Księgowanie za pomocą ksiąg pochodnych</span><span class="sxs-lookup"><span data-stu-id="30f1e-103">Post with derived books</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="30f1e-104">W tym artykule opisano sposób korzystania z ksiąg pochodnych.</span><span class="sxs-lookup"><span data-stu-id="30f1e-104">This article describes how to use derived books.</span></span>

<span data-ttu-id="30f1e-105">W przypadku księgowania transakcji w księdze, która zawiera księgi pochodne, transakcje w księgach pochodnych są księgowane automatycznie z arkuszy, zamówień zakupu i faktur niezależnych.</span><span class="sxs-lookup"><span data-stu-id="30f1e-105">When you post transactions for a book that contains derived books, the derived book transactions are posted automatically in journals, purchase orders, or free text invoices.</span></span> <span data-ttu-id="30f1e-106">Jeżeli jednak przygotowujesz transakcje dla księgi podstawowej w arkuszu Środki trwałe, możliwe będzie wyświetlanie i modyfikowanie kwot transakcji pochodnych przed ich zaksięgowaniem.</span><span class="sxs-lookup"><span data-stu-id="30f1e-106">However, if you prepare the primary book transactions in the Fixed assets journal, you can view and modify the amounts of the derived transactions before you post them.</span></span>
-   <span data-ttu-id="30f1e-107">Pewne konta, takie jak konto podatkowe, konto odbiorcy lub konto dostawcy, są aktualizowane tylko raz poprzez księgowanie w księdze podstawowej.</span><span class="sxs-lookup"><span data-stu-id="30f1e-107">Certain accounts, such as sales tax and customer or vendor accounts, are updated only once by postings of the primary book.</span></span> <span data-ttu-id="30f1e-108">Transakcje księgi pochodnej są księgowane na kontach zdefiniowanych dla księgi pochodnej na stronie Profile księgowania środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="30f1e-108">The derived book transactions are posted to the accounts that have been defined for the derived book in the Fixed asset posting profiles page.</span></span>
-   <span data-ttu-id="30f1e-109">Dla ksiąg pochodnych jako typ transakcji jest zwykle używana opcja Nabycie.</span><span class="sxs-lookup"><span data-stu-id="30f1e-109">Acquisition is often used as the transaction type for the derived books.</span></span> <span data-ttu-id="30f1e-110">Z tej opcji można korzystać, jeżeli księga i księga pochodna mają być stosowane dla środków trwałych od momentu ich nabycia.</span><span class="sxs-lookup"><span data-stu-id="30f1e-110">You use this when the book and the derived book should be applied to the fixed asset from the time of the acquisition of the fixed asset.</span></span>
-   <span data-ttu-id="30f1e-111">Możliwe jest także stosowanie innych wartości dla opcji typu transakcji.</span><span class="sxs-lookup"><span data-stu-id="30f1e-111">Other values for the transaction type can also apply.</span></span> <span data-ttu-id="30f1e-112">Na przykład jeżeli w księgach podstawowej i pochodnych są te same okresy dotyczące sprzedaży lub likwidacji, wszystkie typy transakcji na środkach trwałych są dostępne podczas konfigurowania księgi pochodnej.</span><span class="sxs-lookup"><span data-stu-id="30f1e-112">For example, if the primary book and the derived books have the same intervals regarding sale or disposal, all fixed asset transaction types are available for the setup of a derived book.</span></span>

> [!WARNING]
> <span data-ttu-id="30f1e-113">Amortyzacja zaksięgowana w księdze pochodnej będzie na tę samą kwotą, co kwota zaksięgowana w księdze podstawowej.</span><span class="sxs-lookup"><span data-stu-id="30f1e-113">Depreciation posted in the derived book will be the same amount as was posted for the primary book.</span></span> <span data-ttu-id="30f1e-114">Jeżeli metody amortyzacji są różne w obu rodzajach ksiąg, nie należy generować transakcji amortyzacji za pomocą procesu ksiąg pochodnych.</span><span class="sxs-lookup"><span data-stu-id="30f1e-114">If the depreciation methods are different between the books, you should not generate depreciation transactions using the derived process.</span></span> |

## <a name="example"></a><span data-ttu-id="30f1e-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="30f1e-115">Example</span></span> 
<span data-ttu-id="30f1e-116">Na podstawie poniższych informacji prześledźmy sposób konfigurowania transakcji nabycia przy użyciu funkcji ksiąg pochodnych.</span><span class="sxs-lookup"><span data-stu-id="30f1e-116">The following information describes how to set up acquisition transactions with the derived book functionality.</span></span>

1.  <span data-ttu-id="30f1e-117">Utwórz księgi na stronie Księgi.</span><span class="sxs-lookup"><span data-stu-id="30f1e-117">Create the books on the Books page.</span></span>
    -   <span data-ttu-id="30f1e-118">Księga do celów księgowych: VM 1, warstwa księgowania Bieżący</span><span class="sxs-lookup"><span data-stu-id="30f1e-118">The book for accounting: VM 1, Current posting layer</span></span>
    -   <span data-ttu-id="30f1e-119">Księga do celów podatkowych: VM 2, warstwa księgowania Podatek</span><span class="sxs-lookup"><span data-stu-id="30f1e-119">The book for tax purposes: VM 2, Tax posting layer</span></span>

2.  <span data-ttu-id="30f1e-120">W obszarze VM 1 kliknij kartę Księgi pochodne. Wybierz opcję VM 2 w polu Księga i opcję Nabycie w polu Typ transakcji.</span><span class="sxs-lookup"><span data-stu-id="30f1e-120">On VM 1, click the Derived books tab. Select VM 2 in the Book field, and Acquisition in the Transaction type field.</span></span>

<span data-ttu-id="30f1e-121">Księgi można dołączać do określonych środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="30f1e-121">The books then can be attached to specific fixed assets.</span></span> 

<span data-ttu-id="30f1e-122">Jeżeli nabycie środka trwałego zostanie zaksięgowane w księdze VM 1, nie zostanie zaksięgowane tylko w księdze VM 1, ale również w księdze pochodnej VM 2.</span><span class="sxs-lookup"><span data-stu-id="30f1e-122">When an acquisition is posted for a fixed asset with book VM 1, the acquisition is posted not only on VM 1, but also on the derived book VM 2.</span></span> <span data-ttu-id="30f1e-123">Stan obu ksiąg środków trwałych zmieni się na Otwarty.</span><span class="sxs-lookup"><span data-stu-id="30f1e-123">The status of both fixed asset books is updated to Open.</span></span>

> [!NOTE]                                                                                                         
> <span data-ttu-id="30f1e-124">Jeżeli nie jest używana funkcja ksiąg pochodnych, należy zaksięgować nabycie środka trwałego osobno w księgach VM 1 i VM 2.</span><span class="sxs-lookup"><span data-stu-id="30f1e-124">If you do not use derived books, you must post the acquisition of the fixed asset both for book VM 1 and book VM 2.</span></span>

<span data-ttu-id="30f1e-125">Aby uzyskać więcej informacji, zobacz [Księgi pochodne](derived-books.md)</span><span class="sxs-lookup"><span data-stu-id="30f1e-125">For more information, see [Derived books](derived-books.md)</span></span>




