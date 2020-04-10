---
title: Przetwarzanie arkusza alokacji księgi
description: W tym temacie wyjaśniono, jak przetwarzać żądania alokacji Dynamics 365 Finance.
author: aprilolson
manager: AnnBe
ms.date: 07/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAllocationRequest, LedgerJournalTable, LedgerJournalTransAllocation
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 33e989d3641ae1eaa28a55398fcf51674ac1ed72
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144966"
---
# <a name="process-ledger-allocation-journal"></a><span data-ttu-id="c8a07-103">Przetwarzanie arkusza alokacji księgi</span><span class="sxs-lookup"><span data-stu-id="c8a07-103">Process ledger allocation journal</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c8a07-104">W tym temacie wyjaśniono, jak przetwarzać żądania alokacji.</span><span class="sxs-lookup"><span data-stu-id="c8a07-104">This topic explains how to process an allocation request.</span></span> <span data-ttu-id="c8a07-105">Na stronie Przetwarzanie żądania alokacji można utworzyć arkusz alokacji, który może być przeglądany i zatwierdzany przed księgowaniem w księdze głównej lub bezpośrednio księgowany w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="c8a07-105">Use the Process allocation request page to create an allocation journal that can be reviewed and approved before posting to General ledger, or posted directly to General ledger.</span></span> <span data-ttu-id="c8a07-106">Przed utworzeniem arkusza alokacji musi istnieć co najmniej jedna aktywna reguła alokacji księgi.</span><span class="sxs-lookup"><span data-stu-id="c8a07-106">Before you can create an allocations journal, there must be least one active Ledger allocation rule.</span></span> <span data-ttu-id="c8a07-107">W zadaniu wykorzystano firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="c8a07-107">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="c8a07-108">W okienku nawigacji przejdź do **Moduły > Księga główna > Alokacja > Przetwarzanie żądania alokacji**.</span><span class="sxs-lookup"><span data-stu-id="c8a07-108">In the navigation pane, go to **Modules > General ledger > Allocations > Process allocation request**.</span></span>
2. <span data-ttu-id="c8a07-109">W polu **Reguła** wybierz odpowiedni rekord z menu rozwijanego.</span><span class="sxs-lookup"><span data-stu-id="c8a07-109">In the **Rule** field, select the desired record in the drop-down menu.</span></span>
3. <span data-ttu-id="c8a07-110">W polu **Na dzień** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="c8a07-110">In the **As of date** field, enter a date.</span></span>

    - <span data-ttu-id="c8a07-111">Wartość **Na dzień** jest bardzo ważna, jeżeli źródłem danych reguły jest księga.</span><span class="sxs-lookup"><span data-stu-id="c8a07-111">The **As of Date** is very important when the Ledger is the Data source for the rule.</span></span> <span data-ttu-id="c8a07-112">Ta data określa, które salda księgi mają być uwzględnione w alokacji.</span><span class="sxs-lookup"><span data-stu-id="c8a07-112">This date controls which ledger balances to include for allocation.</span></span>  
    - <span data-ttu-id="c8a07-113">W polu **Źródło zerowe** wybierz opcję **Zatrzymaj**.</span><span class="sxs-lookup"><span data-stu-id="c8a07-113">In the **Zero source** field select **Stop**.</span></span> <span data-ttu-id="c8a07-114">Spowoduje to zatrzymanie procesu alokacji i wyświetlenie komunikatu o wybraniu kwoty źródłowej równej zero.</span><span class="sxs-lookup"><span data-stu-id="c8a07-114">This will stop the allocation process and display a message that states that a zero source amount is selected.</span></span>  

4. <span data-ttu-id="c8a07-115">W polu **Opcje propozycji** wybierz opcję **Tylko propozycja**.</span><span class="sxs-lookup"><span data-stu-id="c8a07-115">In the **Proposal options** field, select **Proposal only**.</span></span> <span data-ttu-id="c8a07-116">Wybierz opcję **Tylko propozycja**, aby przejrzeć i opcjonalnie zatwierdzić wynik w arkuszach alokacji przed księgowaniem alokacji w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="c8a07-116">Select **Proposal only** to review and optionally approve the result in Allocation journals prior to posting the allocation to General ledger.</span></span>  
5. <span data-ttu-id="c8a07-117">W polu Data księgowania w księdze głównej wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="c8a07-117">In the GL posting date field, enter a date.</span></span>
6. <span data-ttu-id="c8a07-118">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="c8a07-118">Select **OK**.</span></span>
7. <span data-ttu-id="c8a07-119">W okienku nawigacji przejdź do **Moduły > Księga główna > Alokacja > Arkusze alokacji**.</span><span class="sxs-lookup"><span data-stu-id="c8a07-119">In the navigation pane, go to **Modules > General ledger > Allocations > Allocation journals**.</span></span>
8. <span data-ttu-id="c8a07-120">Wybierz **Linie**.</span><span class="sxs-lookup"><span data-stu-id="c8a07-120">Select **Lines**.</span></span>
9. <span data-ttu-id="c8a07-121">Wybierz opcję **Zaksięguj**.</span><span class="sxs-lookup"><span data-stu-id="c8a07-121">Select **Post**.</span></span>
10. <span data-ttu-id="c8a07-122">Wybierz opcję **Zaksięguj**.</span><span class="sxs-lookup"><span data-stu-id="c8a07-122">Select **Post**.</span></span>

