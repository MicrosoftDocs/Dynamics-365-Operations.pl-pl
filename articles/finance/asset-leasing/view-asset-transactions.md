---
title: Wyświetlanie zobowiązania, składnika majątku i transakcji wydatków
description: W tym temacie opisano sposób wyświetlania transakcji dla wynajętego składnika majątku. Transakcje te obejmują transakcje zobowiązań z tytułu wynajmu i transakcje wydatków wykonawczych, które zostały zaksięgowane.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 7008891d194dc990d13a9f56db155c6990aae0c0
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2020
ms.locfileid: "4447012"
---
# <a name="view-liability-asset-and-expense-transactions"></a><span data-ttu-id="50343-104">Wyświetlanie zobowiązania, składnika majątku i transakcji wydatków</span><span class="sxs-lookup"><span data-stu-id="50343-104">View liability, asset, and expense transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="50343-105">W tym temacie opisano sposób wyświetlania transakcji dla wynajętego składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="50343-105">This topic explains how to view transactions for a leased asset.</span></span> <span data-ttu-id="50343-106">Transakcje te obejmują transakcje zobowiązań z tytułu wynajmu i transakcje wydatków wykonawczych, które zostały zaksięgowane.</span><span class="sxs-lookup"><span data-stu-id="50343-106">These transactions include lease liability transactions and executory expense transactions that have been posted.</span></span> <span data-ttu-id="50343-107">Wartości bilansowe zobowiązania i składnika majątku z prawem do użytkowania (PDU) są wykorzystywane w kilku raportach.</span><span class="sxs-lookup"><span data-stu-id="50343-107">The carrying values of the liability and right-of-use (ROU) asset are used on several reports.</span></span> <span data-ttu-id="50343-108">Służą one również do obliczania wartości korekt.</span><span class="sxs-lookup"><span data-stu-id="50343-108">They are also used to calculate adjustment values.</span></span>

## <a name="liability-transactions"></a><span data-ttu-id="50343-109">Transakcje zobowiązań</span><span class="sxs-lookup"><span data-stu-id="50343-109">Liability transactions</span></span>

<span data-ttu-id="50343-110">Aby wyświetlić transakcje zobowiązań z tytułu wynajmu, wybierz umowę wynajmu na stronie **Podsumowanie wynajmu**, a następnie wybierz opcję **Księgi**, aby otworzyć księgi dołączone do rekordu wynajmu.</span><span class="sxs-lookup"><span data-stu-id="50343-110">To view the lease liability transactions, select a lease on the **Lease summary** page, and then select **Books** to open the books that are attached to the lease record.</span></span> <span data-ttu-id="50343-111">Po zaksięgowaniu początkowego ujęcia, faktury lub arkusza odsetek wybierz opcję **Transakcje zobowiązań**.</span><span class="sxs-lookup"><span data-stu-id="50343-111">After an initial recognition, an invoice, or an interest journal has been posted, select **Liability transactions**.</span></span>

<span data-ttu-id="50343-112">Na stronie **Transakcje zobowiązań** są wyświetlane transakcje zwiększające lub zmniejszające zobowiązanie z tytułu wynajmu.</span><span class="sxs-lookup"><span data-stu-id="50343-112">The **Liability transactions** page shows the transactions that either increase or decrease the lease liability.</span></span> <span data-ttu-id="50343-113">Kwoty ujemne na tej stronie reprezentują transakcje uznaniowe w standardowej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="50343-113">Negative amounts on this page represent credit transactions in the standard application.</span></span> <span data-ttu-id="50343-114">Wszelkie naliczenia odsetek są pokazywane jako wartości ujemne i zwiększają łączne zobowiązanie z tytułu wynajmu.</span><span class="sxs-lookup"><span data-stu-id="50343-114">Any interest accruals are shown as negative values and increase the total lease liability.</span></span> <span data-ttu-id="50343-115">Wszelkie korekty wynajmu są wyświetlane jako wartości dodatnie lub ujemne, w zależności od charakteru i wpływu księgi wynajmu.</span><span class="sxs-lookup"><span data-stu-id="50343-115">Any lease adjustments are shown as positive or negative values, depending on the nature and impact of the lease book.</span></span> <span data-ttu-id="50343-116">Bieżące całkowite saldo netto zobowiązania z tytułu wynajmu dla wybranej umowy wynajmu jest wyświetlane w lewej dolnej części strony.</span><span class="sxs-lookup"><span data-stu-id="50343-116">The current net total balance of the lease liability for the selected lease is shown at the bottom left of the page.</span></span>

## <a name="asset-transactions"></a><span data-ttu-id="50343-117">Transakcje składnika majątku</span><span class="sxs-lookup"><span data-stu-id="50343-117">Asset transactions</span></span>

<span data-ttu-id="50343-118">Aby wyświetlić transakcje należności z tytułu wynajmu, wybierz umowę wynajmu na stronie **Podsumowanie wynajmu**, a następnie wybierz opcję **Księgi**, aby otworzyć księgi wynajmu dołączone do rekordu wynajmu.</span><span class="sxs-lookup"><span data-stu-id="50343-118">To view the lease asset transactions, select a lease on the **Lease summary** page, and then select **Books** to open the lease books that are attached to the lease record.</span></span> <span data-ttu-id="50343-119">Następnie wybierz opcję **Transakcje składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="50343-119">Then select **Asset transactions**.</span></span>

<span data-ttu-id="50343-120">Na stronie **Transakcja składnika majątku** są wyświetlane transakcje, które powodują zwiększenie lub zmniejszenie należności z tytułu wynajmu i wartości na kontach umorzenia.</span><span class="sxs-lookup"><span data-stu-id="50343-120">The **Asset transaction** page shows the transactions that either increase or decrease the lease asset and accumulated depreciation accounts.</span></span> <span data-ttu-id="50343-121">Obciążenia są pokazywane jako wartości dodatnie, a uznania jako wartości ujemne, podobnie jak na stronie **Transakcje zobowiązań**.</span><span class="sxs-lookup"><span data-stu-id="50343-121">Debits are shown as positive values, and credits are shown as negative values, as on the **Liability transactions** page.</span></span> <span data-ttu-id="50343-122">Zaksięgowane początkowe ujęcie i późniejsze umorzenie są wyświetlane w dolnej lewej części strony jako saldo środka składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="50343-122">The posted initial recognition and the next of accumulated depreciation are shown at the bottom left of the page as the asset balance.</span></span> 

## <a name="expenses-transactions"></a><span data-ttu-id="50343-123">Transakcje wydatkowe</span><span class="sxs-lookup"><span data-stu-id="50343-123">Expenses transactions</span></span>

<span data-ttu-id="50343-124">Aby wyświetlić transakcje wydatków z tytułu wynajmu, wybierz umowę wynajmu na stronie **Podsumowanie wynajmu**, a następnie wybierz opcję **Księgi**, aby otworzyć księgi wynajmu dołączone do rekordu wynajmu.</span><span class="sxs-lookup"><span data-stu-id="50343-124">To view the lease expense transactions, select a lease on the **Lease summary** page, and then select **Books** to open the lease books that are attached to the lease record.</span></span> <span data-ttu-id="50343-125">Następnie wybierz opcję **Transakcje wydatkowe**.</span><span class="sxs-lookup"><span data-stu-id="50343-125">Then select **Expense transactions**.</span></span>

<span data-ttu-id="50343-126">Na stronie **Transakcje wydatkowe** są wyświetlane wszystkie wydatki, które zostały zaksięgowane dla wynajmu, takie jak koszty odsetek, wydatki amortyzacji i wszelkie koszty wykonawcze.</span><span class="sxs-lookup"><span data-stu-id="50343-126">The **Expense transactions** page shows all the expenses that have been posted against the lease, such as interest expenses, depreciation expenses, and any executory costs.</span></span>
