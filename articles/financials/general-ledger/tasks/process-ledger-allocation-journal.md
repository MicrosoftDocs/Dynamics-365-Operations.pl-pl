---
title: Przetwarzanie arkusza alokacji księgi
description: Na stronie Przetwarzanie żądania alokacji można utworzyć arkusz alokacji, który może być przeglądany i zatwierdzany przed księgowaniem w księdze głównej lub bezpośrednio księgowany w księdze głównej.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAllocationRequest, LedgerJournalTable, LedgerJournalTransAllocation
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d2046e25719c9023bee99736488a4ee6f22723fe
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "335653"
---
# <a name="process-ledger-allocation-journal"></a><span data-ttu-id="83686-103">Przetwarzanie arkusza alokacji księgi</span><span class="sxs-lookup"><span data-stu-id="83686-103">Process ledger allocation journal</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="83686-104">Na stronie Przetwarzanie żądania alokacji można utworzyć arkusz alokacji, który może być przeglądany i zatwierdzany przed księgowaniem w księdze głównej lub bezpośrednio księgowany w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="83686-104">Use the Process allocation request page to create an allocation journal that can be reviewed and approved before posting to General ledger, or posted directly to General ledger.</span></span> <span data-ttu-id="83686-105">Przed utworzeniem arkusza alokacji musi istnieć co najmniej jedna aktywna reguła alokacji księgi.</span><span class="sxs-lookup"><span data-stu-id="83686-105">Before you can create an allocations journal, there must be least one active Ledger allocation rule.</span></span> <span data-ttu-id="83686-106">W zadaniu wykorzystano firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="83686-106">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="83686-107">Wybierz kolejno opcje Księga główna > Alokacje > Przetwarzanie żądania alokacji.</span><span class="sxs-lookup"><span data-stu-id="83686-107">Go to General ledger > Allocations > Process allocation request.</span></span>
2. <span data-ttu-id="83686-108">W polu Reguła kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="83686-108">In the Rule field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="83686-109">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="83686-109">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="83686-110">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="83686-110">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="83686-111">W polu Na dzień wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="83686-111">In the As of date field, enter a date.</span></span>
    * <span data-ttu-id="83686-112">Wartość Na dzień jest bardzo ważna, jeżeli jest źródłem danych reguły jest księga.</span><span class="sxs-lookup"><span data-stu-id="83686-112">The As of Date is very important when the Ledger is the Data source for the rule.</span></span> <span data-ttu-id="83686-113">Ta data określa, które salda księgi mają być uwzględnione w alokacji.</span><span class="sxs-lookup"><span data-stu-id="83686-113">This date controls which ledger balances to include for allocation.</span></span>     <span data-ttu-id="83686-114">W polu Źródło zerowe wybierz opcję Zatrzymaj.</span><span class="sxs-lookup"><span data-stu-id="83686-114">In the Zero source field select Stop.</span></span> <span data-ttu-id="83686-115">Spowoduje to zatrzymanie procesu alokacji i wyświetlenie komunikatu o wybraniu kwoty źródłowej równej 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="83686-115">This will  Stop the allocation process and display a message that states that a zero source amount is selected.</span></span>  
6. <span data-ttu-id="83686-116">W polu Opcje propozycji wybierz opcję "Tylko propozycja".</span><span class="sxs-lookup"><span data-stu-id="83686-116">In the Proposal options field, select 'Proposal only'.</span></span>
    * <span data-ttu-id="83686-117">Wybierz opcję Tylko propozycja, aby przejrzeć i opcjonalnie zatwierdzić wynik w arkuszach alokacji przed księgowaniem alokacji w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="83686-117">Select Proposal only to review and optionally approve the result in Allocation journals prior to posting the allocation to General ledger.</span></span>  
7. <span data-ttu-id="83686-118">W polu Data księgowania w księdze głównej wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="83686-118">In the GL posting date field, enter a date.</span></span>
8. <span data-ttu-id="83686-119">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="83686-119">Click OK.</span></span>
9. <span data-ttu-id="83686-120">Wybierz kolejno opcje Księga główna > Alokacje > Arkusze alokacji.</span><span class="sxs-lookup"><span data-stu-id="83686-120">Go to General ledger > Allocations > Allocation journals.</span></span>
10. <span data-ttu-id="83686-121">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="83686-121">Click Lines.</span></span>
11. <span data-ttu-id="83686-122">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="83686-122">Click Post.</span></span>
12. <span data-ttu-id="83686-123">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="83686-123">Click Post.</span></span>

