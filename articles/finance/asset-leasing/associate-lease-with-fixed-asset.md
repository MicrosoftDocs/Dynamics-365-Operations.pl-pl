---
title: Kojarzenie środków trwałych z wynajmami
description: W tym temacie opisano sposób kojarzenia istniejącego środka trwałego z nowym wynajmem.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseDetail
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 02a17b8c995e8aa97384d8b855afb688324017d6
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881355"
---
# <a name="associate-fixed-assets-with-leases"></a><span data-ttu-id="d0ecb-103">Kojarzenie środków trwałych z wynajmami</span><span class="sxs-lookup"><span data-stu-id="d0ecb-103">Associate fixed assets with leases</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d0ecb-104">W tym temacie opisano sposób kojarzenia istniejącego środka trwałego z nowym wynajmem.</span><span class="sxs-lookup"><span data-stu-id="d0ecb-104">The topic explains how to associate an existing fixed asset with a new lease.</span></span> <span data-ttu-id="d0ecb-105">Po skojarzeniu środka trwałego z wynajmem wartość środka trwałego (ROU) w momencie początkowego uznania będzie kosztem nabycia środka trwałego.</span><span class="sxs-lookup"><span data-stu-id="d0ecb-105">When you associate a fixed asset with a lease, the right-of-use (ROU) asset value at initial recognition will be the acquisition cost of the fixed asset.</span></span>

<span data-ttu-id="d0ecb-106">Aby można było skojarzyć środek trwały z wynajmem, należy utworzyć rekord dla środka trwałego w module Środki trwałe.</span><span class="sxs-lookup"><span data-stu-id="d0ecb-106">Before you can associate a fixed asset with a lease, you must create a record for the fixed asset in Fixed assets.</span></span> <span data-ttu-id="d0ecb-107">Następnie na stronie **Podsumowanie wynajmu** należy utworzyć wynajem i powiązać środek trwały z tym wynajmem.</span><span class="sxs-lookup"><span data-stu-id="d0ecb-107">Then, on the **Lease summary** page, you must create a lease and link the asset to that lease.</span></span>

1. <span data-ttu-id="d0ecb-108">Dodaj wynajem, wykonując kroki w obszarze [Dodaj lub kopiuj wynajmy](add-lease.md).</span><span class="sxs-lookup"><span data-stu-id="d0ecb-108">Add a lease by following the steps in [Add or copy leases](add-lease.md).</span></span> <span data-ttu-id="d0ecb-109">Na stronie **Dodawanie wynajmu** w polu **Numer środka trwałego** wybierz środek trwały, który nie został jeszcze nabyty.</span><span class="sxs-lookup"><span data-stu-id="d0ecb-109">On the **Add lease** page, in the **Fixed asset number** field, select the asset that hasn't yet been acquired.</span></span>
2. <span data-ttu-id="d0ecb-110">Wybierz opcję **Księgi** i potwierdź harmonogram płatności.</span><span class="sxs-lookup"><span data-stu-id="d0ecb-110">Select **Books**, and confirm the payment schedule.</span></span>
3. <span data-ttu-id="d0ecb-111">Wybierz **Początkowe uznanie**.</span><span class="sxs-lookup"><span data-stu-id="d0ecb-111">Select **Initial recognition**.</span></span>
4. <span data-ttu-id="d0ecb-112">Wybierz **Arkusz wynajmu składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="d0ecb-112">Select **Asset leasing journal**.</span></span>

    <span data-ttu-id="d0ecb-113">Początkowy wpis w arkuszu uznania dla wynajmu obciąża środek trwały na kwotę, która zwykle jest księgowana po stronie debetowej konta składnika majątku z PDU.</span><span class="sxs-lookup"><span data-stu-id="d0ecb-113">The initial recognition journal entry for the lease debits the fixed asset for the amount that is usually debited to the ROU asset account.</span></span>

    <span data-ttu-id="d0ecb-114">Teraz można wyświetlić typ transakcji i księgę dla środka trwałego.</span><span class="sxs-lookup"><span data-stu-id="d0ecb-114">You can now view the transaction type and book for the fixed asset.</span></span>

5. <span data-ttu-id="d0ecb-115">Wybierz **Szczegóły arkusza**.</span><span class="sxs-lookup"><span data-stu-id="d0ecb-115">Select **Journal details**.</span></span>
6. <span data-ttu-id="d0ecb-116">Wybierz opcję **Wiersze**, aby wyświetlić poszczególne wiersze danego wpisu w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="d0ecb-116">Select **Lines** to view the individual lines for the journal entry.</span></span>
7. <span data-ttu-id="d0ecb-117">Wybierz wiersz arkusza zawierający środek trwały, a następnie wybierz kartę **Środki trwałe**.</span><span class="sxs-lookup"><span data-stu-id="d0ecb-117">Select the journal line that contains the asset, and then select the **Fixed Assets** tab.</span></span>

    <span data-ttu-id="d0ecb-118">Na karcie **Środki trwałe** wyświetlany jest typ transakcji oraz księga.</span><span class="sxs-lookup"><span data-stu-id="d0ecb-118">The **Fixed assets** tab shows the transaction type and the book.</span></span> <span data-ttu-id="d0ecb-119">Domyślnie pole **Typ transakcji** jest ustawione na **Nabycie**, a pole **Księga** ma ustawioną bieżącą księgę dla środka trwałego.</span><span class="sxs-lookup"><span data-stu-id="d0ecb-119">By default, the **Transaction type** field is set to **Acquisition**, and the **Book** field is set to the current book for the fixed asset.</span></span>

<span data-ttu-id="d0ecb-120">Po zaksięgowaniu wpisu w arkuszu początkowego uznania transakcja jest wyświetlana jako transakcja nabycia dla środka trwałego.</span><span class="sxs-lookup"><span data-stu-id="d0ecb-120">After you post the initial recognition journal entry, the transaction appears as an acquisition transaction for the fixed asset.</span></span> <span data-ttu-id="d0ecb-121">Aby wyświetlić tabelę transakcji, należy przejść do **Środki trwałe \> Środki trwałe \> Środki trwałe**, wybrać odpowiedni środek trwały i wybrać pozycję **Wyceny**.</span><span class="sxs-lookup"><span data-stu-id="d0ecb-121">To view the transaction table, go to **Fixed assets \> Fixed assets \> Fixed assets**, select the appropriate asset, and then select **Valuations**.</span></span> <span data-ttu-id="d0ecb-122">Powinno być widoczne, że początkowe uznanie wpisu w arkuszu utworzyło transakcję nabycia dla danego środka trwałego.</span><span class="sxs-lookup"><span data-stu-id="d0ecb-122">You should see that the initial recognition journal entry has created an acquisition transaction for the specified fixed asset.</span></span>

<span data-ttu-id="d0ecb-123">Środek trwały może teraz zostać zamortyzowany przy użyciu standardowych funkcji amortyzacji w module Środki trwałe.</span><span class="sxs-lookup"><span data-stu-id="d0ecb-123">The fixed asset can now be depreciated by using the standard depreciation functionality in Fixed assets.</span></span> <span data-ttu-id="d0ecb-124">Aby uzyskać więcej informacji na temat amortyzacji, zobacz [Metody i konwencje amortyzacji środka trwałego](../fixed-assets/depreciation-methods-conventions.md).</span><span class="sxs-lookup"><span data-stu-id="d0ecb-124">For more information about depreciation, see [Depreciation methods and conventions](../fixed-assets/depreciation-methods-conventions.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d0ecb-125">Jeśli użytkownik skojarzy środek trwały z wynajmem, przyciski **Amortyzacja środka trwałego** i **Utrata wartości wynajmu** są wyłączone w module Wynajem składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="d0ecb-125">If you associate a fixed asset with a lease, the **Asset depreciation** and **Lease impairment** buttons are disabled in Asset leasing.</span></span> <span data-ttu-id="d0ecb-126">Transakcje amortyzacji składnika majątku i utraty wartości wynajmu można wyświetlić w module Środki trwałe.</span><span class="sxs-lookup"><span data-stu-id="d0ecb-126">You can view asset depreciation and lease impairment transactions from Fixed assets.</span></span> <span data-ttu-id="d0ecb-127">Przycisk **Transakcje składnika majątku**, który powoduje otwarcie formularza kwerendy, również jest wyłączony.</span><span class="sxs-lookup"><span data-stu-id="d0ecb-127">The **Asset transactions** button, which opens an inquiry form is also disabled.</span></span> <span data-ttu-id="d0ecb-128">Formularz kwerendy **Transakcje składnika majątku** można również otworzyć w module Środki trwałe.</span><span class="sxs-lookup"><span data-stu-id="d0ecb-128">You can also open the **Asset transactions** inquiry form in Fixed assets.</span></span>  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
