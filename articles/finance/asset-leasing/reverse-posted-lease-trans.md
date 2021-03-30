---
title: Wycofywanie zaksięgowanych transakcji wynajmu
description: W tym temacie wyjaśniono, jak wycofać zaksięgowaną transakcję wynajmu. Każdą transakcję utworzoną za pośrednictwem modułu Wynajem składnika majątku można wycofać.
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
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 22d8eee22221efaf5e7a715c8b95dff261bee62f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5249732"
---
# <a name="reverse-posted-lease-transactions"></a><span data-ttu-id="43a06-104">Wycofywanie zaksięgowanych transakcji wynajmu</span><span class="sxs-lookup"><span data-stu-id="43a06-104">Reverse posted lease transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="43a06-105">Każdą transakcję utworzoną za pośrednictwem modułu Wynajem składnika majątku można wycofać.</span><span class="sxs-lookup"><span data-stu-id="43a06-105">Any transaction that is created through Asset leasing can be reversed.</span></span> <span data-ttu-id="43a06-106">Transakcje wycofane za pośrednictwem modułu Wynajem składnika majątku powodują aktualizację danych wynajmu.</span><span class="sxs-lookup"><span data-stu-id="43a06-106">Transactions that are reversed through Asset leasing update your lease data.</span></span> <span data-ttu-id="43a06-107">W związku z tym aktualizują także wartości bilansowe zobowiązania z tytułu wynajmu i składnika majątku z prawem do użytkowania (PDU).</span><span class="sxs-lookup"><span data-stu-id="43a06-107">Therefore, they also update the carrying values of the lease liability and right-of-use (ROU) asset.</span></span>

<span data-ttu-id="43a06-108">Aby utworzyć transakcję stornującą dla dzierżawy, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="43a06-108">To create a reversing transaction for a lease, follow these steps.</span></span>

1. <span data-ttu-id="43a06-109">Na stronie **Transakcje składnika majątku** lub **Transakcje zobowiązań** wybierz transakcję, a następnie wybierz pozycję **Wycofaj transakcję**.</span><span class="sxs-lookup"><span data-stu-id="43a06-109">On either the **Asset transactions** page or the **Liability transactions** page, select the transaction, and then select **Reverse transaction**.</span></span>
2. <span data-ttu-id="43a06-110">W wyświetlonym oknie dialogowym można edytować datę, z którą ma zostać zaksięgowany wpis stornujący.</span><span class="sxs-lookup"><span data-stu-id="43a06-110">In the dialog box that appears, you can edit the date when the reversing entry will be posted.</span></span> <span data-ttu-id="43a06-111">Domyślnie w polu **Data** jest ustawiana data księgowania wybranej transakcji.</span><span class="sxs-lookup"><span data-stu-id="43a06-111">By default, the **Date** field is set to the transaction posting date of the transaction that you selected.</span></span> <span data-ttu-id="43a06-112">Wpis stornujący nie może zostać zaksięgowany wcześniej niż w pierwotnym dniu księgowania wybranej transakcji.</span><span class="sxs-lookup"><span data-stu-id="43a06-112">The reversing entry can't be posted earlier than the original posting date of the selected transaction.</span></span>
3. <span data-ttu-id="43a06-113">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="43a06-113">Select **OK**.</span></span> <span data-ttu-id="43a06-114">Jest księgowany wpis w arkuszu, który powoduje wycofanie wybranego wpisu.</span><span class="sxs-lookup"><span data-stu-id="43a06-114">A journal entry is posted that reverses the entry that you selected.</span></span> <span data-ttu-id="43a06-115">Wycofanie jest wyświetlane na stronie **Transakcje składnika majątku** lub **Transakcje zobowiązań**, a suma netto bieżącego salda wyświetlana na stronie jest aktualizowana.</span><span class="sxs-lookup"><span data-stu-id="43a06-115">The reversal is shown on the **Asset transactions** or **Liability transactions** page, and the net total of the current balance that is shown on the page is updated.</span></span>

<span data-ttu-id="43a06-116">Po wybraniu opcji **Śledzenie wycofania** zostanie wyświetlone okno dialogowe, w którym są wyświetlane zarówno oryginalne transakcje, jak i transakcje wycofane, wraz z połączoną liczbą nazywaną *numerem śledzenia*.</span><span class="sxs-lookup"><span data-stu-id="43a06-116">When you select **Reverse tracing**, a dialog box appears that shows both the original transactions and the reversed transactions, together with a linked number that is known as a *trace number*.</span></span> <span data-ttu-id="43a06-117">Aby wycofania były bardziej zrozumiałe i przejrzyste, można je również śledzić, korzystając z harmonogramów wynajmu.</span><span class="sxs-lookup"><span data-stu-id="43a06-117">To make the reversals easier to understand and to improve visibility, you can also track reversals by using the lease schedules.</span></span>

<span data-ttu-id="43a06-118">W polu **Najnowszy numer arkusza** na stronie **Harmonogram** są wyświetlane numery arkuszy transakcji.</span><span class="sxs-lookup"><span data-stu-id="43a06-118">The **Latest journal number** field on the **Schedule** page shows the journal numbers of transactions.</span></span> <span data-ttu-id="43a06-119">Po wycofaniu transakcji to pole jest aktualizowane numerem arkusza transakcji stornującej.</span><span class="sxs-lookup"><span data-stu-id="43a06-119">When a transaction is reversed, this field is updated with the journal number of a reversing transaction.</span></span> <span data-ttu-id="43a06-120">Ponadto jest zaznaczane pole wyboru **Wycofane**, aby wskazać, że transakcja została wycofana, oraz jest zaznaczane pole **Zaksięgowano**.</span><span class="sxs-lookup"><span data-stu-id="43a06-120">Additionally, the **Reversed** check box is selected to indicate that the transaction is reversed, and the **Posted** field is selected.</span></span>

## <a name="revoke-a-reversed-transaction"></a><span data-ttu-id="43a06-121">Anulowanie wycofanej transakcji</span><span class="sxs-lookup"><span data-stu-id="43a06-121">Revoke a reversed transaction</span></span>

<span data-ttu-id="43a06-122">Aby anulować wycofaną transakcję, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="43a06-122">To revoke a reversed transaction, follow these steps.</span></span>

1. <span data-ttu-id="43a06-123">Na stronie **Harmonogram** lub **Transakcje** wybierz oryginalną transakcję.</span><span class="sxs-lookup"><span data-stu-id="43a06-123">On either the **Schedule** page or the **Transactions** page, select the original transaction.</span></span>
2. <span data-ttu-id="43a06-124">Wykonaj jeden z następujących kroków:</span><span class="sxs-lookup"><span data-stu-id="43a06-124">Follow one of these steps:</span></span>

    - <span data-ttu-id="43a06-125">Jeśli wybrano transakcję na stronie **Harmonogram**, należy wykonać kroki tworzenia arkusza podane w temacie [Tworzenie miesięcznych wpisów w arkuszu w partii](create-monthly-journals-batch.md).</span><span class="sxs-lookup"><span data-stu-id="43a06-125">If you selected the transaction on the **Schedule** page, follow the steps for creating a journal in [Create monthly journal entries in a batch](create-monthly-journals-batch.md).</span></span> <span data-ttu-id="43a06-126">Należy ręcznie zaksięgować arkusz.</span><span class="sxs-lookup"><span data-stu-id="43a06-126">You must manually post the journal.</span></span>
    - <span data-ttu-id="43a06-127">Jeśli wybrano transakcję na stronie **Transakcje**, należy wybrać opcję **Wycofaj transakcję**.</span><span class="sxs-lookup"><span data-stu-id="43a06-127">If you selected the transaction on the **Transactions** page, select **Reverse transaction**.</span></span> <span data-ttu-id="43a06-128">Zostanie wyświetlony komunikat z informacją, że anulowanie jest anulowaniem wcześniejszego wycofania i można edytować datę księgowania tego anulowania.</span><span class="sxs-lookup"><span data-stu-id="43a06-128">You receive a message that states that this revocation is a revocation of an earlier reversal, and that you can edit the posting date for this revocation.</span></span> <span data-ttu-id="43a06-129">Jednak daty, które można wprowadzić w polu **Data**, zależą od ogólnych weryfikacji biznesowych dokonywanych w organizacji.</span><span class="sxs-lookup"><span data-stu-id="43a06-129">However, general business validations affect the dates that can be entered in the **Date** field.</span></span> 

3. <span data-ttu-id="43a06-130">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="43a06-130">Select **OK**.</span></span> <span data-ttu-id="43a06-131">Jest księgowany wpis w arkuszu, który powoduje wycofanie wybranego wpisu.</span><span class="sxs-lookup"><span data-stu-id="43a06-131">A journal entry is posted that reverses the entry that you selected.</span></span> <span data-ttu-id="43a06-132">Wycofanie jest wyświetlane na stronie **Transakcje**, a suma netto bieżącego salda jest przywracana do wartości sprzed pierwszego wycofania.</span><span class="sxs-lookup"><span data-stu-id="43a06-132">The reversal is shown on the **Transactions** page, and the net total current balance is restored to what it was before the first reversal.</span></span> <span data-ttu-id="43a06-133">W związku z tym wpływ wycofania na salda jest niwelowany.</span><span class="sxs-lookup"><span data-stu-id="43a06-133">Therefore, the impact that the reversal had on the balances is negated.</span></span>

<span data-ttu-id="43a06-134">Po wybraniu opcji **Śledzenie wycofania** zostanie wyświetlone okno dialogowe, w którym są wyświetlane zarówno oryginalne transakcje, jak i transakcje wycofane, wraz z połączonym numerem śledzenia.</span><span class="sxs-lookup"><span data-stu-id="43a06-134">When you select **Reverse tracing**, a dialog box appears that shows both the original transactions and the reversed transactions, together with a linked trace number.</span></span>

<span data-ttu-id="43a06-135">Odwołania można również śledzić na odpowiedniej stronie **Harmonogramy**.</span><span class="sxs-lookup"><span data-stu-id="43a06-135">You can also track revocations by using the appropriate **Schedules** page.</span></span> <span data-ttu-id="43a06-136">Pole **Wycofaj** jest czyszczone, podczas gdy pole **Arkusz zaksięgowany** jest zaznaczane.</span><span class="sxs-lookup"><span data-stu-id="43a06-136">The **Reverse** field is cleared, whereas the **Journal posted** field is selected.</span></span> <span data-ttu-id="43a06-137">Ponadto pole **Najnowszy numer arkusza** jest aktualizowana o numer arkusza transakcji anulowania, a pole **Numer arkusza** jest aktualizowane numerem arkusza wycofywania.</span><span class="sxs-lookup"><span data-stu-id="43a06-137">Additionally, the **Latest journal number** field is updated with the journal number of the revocation transaction, and the **Journal number** field is updated with the reversal journal number.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]