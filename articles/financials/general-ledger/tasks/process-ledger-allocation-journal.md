--- 
title: "Przetwarzanie arkusza alokacji księgi"
description: "Na stronie Przetwarzanie żądania alokacji można utworzyć arkusz alokacji, który może być przeglądany i zatwierdzany przed księgowaniem w księdze głównej lub bezpośrednio księgowany w księdze głównej."
author: aprilolson
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerAllocationRequest, LedgerJournalTable, LedgerJournalTransAllocation
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: d9caebc6004d0a513ab2c3947300d7dd6e283750
ms.contentlocale: pl-pl
ms.lasthandoff: 09/11/2018

---
# <a name="process-ledger-allocation-journal"></a><span data-ttu-id="b312f-103">Przetwarzanie arkusza alokacji księgi</span><span class="sxs-lookup"><span data-stu-id="b312f-103">Process ledger allocation journal</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b312f-104">Na stronie Przetwarzanie żądania alokacji można utworzyć arkusz alokacji, który może być przeglądany i zatwierdzany przed księgowaniem w księdze głównej lub bezpośrednio księgowany w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="b312f-104">Use the Process allocation request page to create an allocation journal that can be reviewed and approved before posting to General ledger, or posted directly to General ledger.</span></span> <span data-ttu-id="b312f-105">Przed utworzeniem arkusza alokacji musi istnieć co najmniej jedna aktywna reguła alokacji księgi.</span><span class="sxs-lookup"><span data-stu-id="b312f-105">Before you can create an allocations journal, there must be least one active Ledger allocation rule.</span></span> <span data-ttu-id="b312f-106">W zadaniu wykorzystano firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="b312f-106">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="b312f-107">Wybierz kolejno opcje Księga główna > Alokacje > Przetwarzanie żądania alokacji.</span><span class="sxs-lookup"><span data-stu-id="b312f-107">Go to General ledger > Allocations > Process allocation request.</span></span>
2. <span data-ttu-id="b312f-108">W polu Reguła kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="b312f-108">In the Rule field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="b312f-109">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="b312f-109">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="b312f-110">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="b312f-110">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="b312f-111">W polu Na dzień wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="b312f-111">In the As of date field, enter a date.</span></span>
    * <span data-ttu-id="b312f-112">Wartość Na dzień jest bardzo ważna, jeżeli jest źródłem danych reguły jest księga.</span><span class="sxs-lookup"><span data-stu-id="b312f-112">The As of Date is very important when the Ledger is the Data source for the rule.</span></span> <span data-ttu-id="b312f-113">Ta data określa, które salda księgi mają być uwzględnione w alokacji.</span><span class="sxs-lookup"><span data-stu-id="b312f-113">This date controls which ledger balances to include for allocation.</span></span>     <span data-ttu-id="b312f-114">W polu Źródło zerowe wybierz opcję Zatrzymaj.</span><span class="sxs-lookup"><span data-stu-id="b312f-114">In the Zero source field select Stop.</span></span> <span data-ttu-id="b312f-115">Spowoduje to zatrzymanie procesu alokacji i wyświetlenie komunikatu o wybraniu kwoty źródłowej równej 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="b312f-115">This will  Stop the allocation process and display a message that states that a zero source amount is selected.</span></span>  
6. <span data-ttu-id="b312f-116">W polu Opcje propozycji wybierz opcję "Tylko propozycja".</span><span class="sxs-lookup"><span data-stu-id="b312f-116">In the Proposal options field, select 'Proposal only'.</span></span>
    * <span data-ttu-id="b312f-117">Wybierz opcję Tylko propozycja, aby przejrzeć i opcjonalnie zatwierdzić wynik w arkuszach alokacji przed księgowaniem alokacji w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="b312f-117">Select Proposal only to review and optionally approve the result in Allocation journals prior to posting the allocation to General ledger.</span></span>  
7. <span data-ttu-id="b312f-118">W polu Data księgowania w księdze głównej wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="b312f-118">In the GL posting date field, enter a date.</span></span>
8. <span data-ttu-id="b312f-119">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="b312f-119">Click OK.</span></span>
9. <span data-ttu-id="b312f-120">Wybierz kolejno opcje Księga główna > Alokacje > Arkusze alokacji.</span><span class="sxs-lookup"><span data-stu-id="b312f-120">Go to General ledger > Allocations > Allocation journals.</span></span>
10. <span data-ttu-id="b312f-121">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="b312f-121">Click Lines.</span></span>
11. <span data-ttu-id="b312f-122">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="b312f-122">Click Post.</span></span>
12. <span data-ttu-id="b312f-123">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="b312f-123">Click Post.</span></span>


