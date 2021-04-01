---
title: Konfigurowanie typów wydatków
description: W tym temacie wyjaśniono, jak konfigurować typy wydatków w module Wynajem składnika majątku.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2019-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 1538826f140393eec59be9ff4df5242d5ced9d8f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5249756"
---
# <a name="set-up-expense-types"></a><span data-ttu-id="5c27e-103">Konfigurowanie typów wydatków</span><span class="sxs-lookup"><span data-stu-id="5c27e-103">Set up expense types</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5c27e-104">W tym temacie wyjaśniono, jak konfigurować typy wydatków w module Wynajem składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="5c27e-104">This topic explains how to set up expense types in Asset leasing.</span></span> <span data-ttu-id="5c27e-105">Koszty, które nie są reprezentowane w harmonogramie płatności, są nazywane *kosztami wydatków*.</span><span class="sxs-lookup"><span data-stu-id="5c27e-105">Costs that aren't represented by the payment schedule are known as *expense costs*.</span></span> <span data-ttu-id="5c27e-106">Przykładami tych kosztów są podatki od nieruchomości, wspólne koszty utrzymania obszaru oraz koszty ubezpieczenia.</span><span class="sxs-lookup"><span data-stu-id="5c27e-106">Examples of these costs include property taxes, common area maintenance costs, and insurance expenses.</span></span>

## <a name="add-an-administrative-expense-type"></a><span data-ttu-id="5c27e-107">Dodawanie typu wydatku administracyjnego</span><span class="sxs-lookup"><span data-stu-id="5c27e-107">Add an administrative expense type</span></span>

1. <span data-ttu-id="5c27e-108">Przejdź do **Wynajem składnika majątku \> Ustawienia \> Typy wydatków**.</span><span class="sxs-lookup"><span data-stu-id="5c27e-108">Go to **Asset leasing \> Setup \> Expense types**.</span></span>
2. <span data-ttu-id="5c27e-109">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="5c27e-109">Select **New**.</span></span>
3. <span data-ttu-id="5c27e-110">W odpowiednich polach wprowadź nowy typ wydatku oraz jego opis.</span><span class="sxs-lookup"><span data-stu-id="5c27e-110">In the appropriate fields, enter the new expense type and a description.</span></span>

## <a name="assign-accounts-to-administrative-costs"></a><span data-ttu-id="5c27e-111">Przypisywanie kont do kosztów administracyjnych</span><span class="sxs-lookup"><span data-stu-id="5c27e-111">Assign accounts to administrative costs</span></span>

<span data-ttu-id="5c27e-112">Następnie należy skojarzyć konta z typami wydatków.</span><span class="sxs-lookup"><span data-stu-id="5c27e-112">Next, you should associate accounts with the expense types.</span></span> <span data-ttu-id="5c27e-113">Te konta będą obciążane podczas księgowania wpisów harmonogramu wydatków.</span><span class="sxs-lookup"><span data-stu-id="5c27e-113">These accounts will be debited when expense schedule entries are posted.</span></span> <span data-ttu-id="5c27e-114">Konto przeciwstawne jest określane w wierszach sekcji **Harmonogram płatności kosztów wykonawczych** dla każdej umowy wynajmu.</span><span class="sxs-lookup"><span data-stu-id="5c27e-114">The offset account is specified on the **Executory costs payment schedule** lines on each lease.</span></span>

1. <span data-ttu-id="5c27e-115">Przejdź do **Wynajem składnika majątku \> Ustawienia \> Parametry wynajmu składników majątku**.</span><span class="sxs-lookup"><span data-stu-id="5c27e-115">Go to **Asset leasing \> Setup \> Asset leasing parameters**.</span></span>
2. <span data-ttu-id="5c27e-116">Na karcie **Konta** na skróconej karcie **Koszty wykonawcze** w polu **Typ wydatku** zaznacz typ wydatku.</span><span class="sxs-lookup"><span data-stu-id="5c27e-116">On the **Accounts** tab, on the **Executory costs** FastTab, in the **Expense type** field, select the expense type.</span></span>
3. <span data-ttu-id="5c27e-117">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="5c27e-117">Select **Add**.</span></span>
4. <span data-ttu-id="5c27e-118">W polu **Typ księgi** wybierz typ księgi, który ma zostać połączony z kosztami administracyjnymi.</span><span class="sxs-lookup"><span data-stu-id="5c27e-118">In the **Book type** field, select the book type to link to the administrative costs.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5c27e-119">Z tym samym kontem wydatków można łączyć wiele typów ksiąg.</span><span class="sxs-lookup"><span data-stu-id="5c27e-119">Multiple book types can be linked to the same expense account.</span></span>

5. <span data-ttu-id="5c27e-120">W polu **Kod konta** określ, do których umów wynajmu ma być stosowana księga:</span><span class="sxs-lookup"><span data-stu-id="5c27e-120">In the **Account code** field, specify which leases the book should be applied to:</span></span>

    - <span data-ttu-id="5c27e-121">**Wszystkie** – księga ma zastosowanie do wszystkich umów wynajmu.</span><span class="sxs-lookup"><span data-stu-id="5c27e-121">**All** – Apply the book to all leases.</span></span>
    - <span data-ttu-id="5c27e-122">**Grupa** — zastosowanie księgi do wybranej grupy umów wynajmu.</span><span class="sxs-lookup"><span data-stu-id="5c27e-122">**Group** – Apply the book to a specific group of leases.</span></span>
    - <span data-ttu-id="5c27e-123">**tabela** – księga ma zastosowanie do wybranych umów wynajmu.</span><span class="sxs-lookup"><span data-stu-id="5c27e-123">**Table** – Apply the book to specific leases.</span></span>

6. <span data-ttu-id="5c27e-124">Jeśli w polu **Kod konta** wybrano opcję **Grupa** lub **Tabela**, wybierz numer konta lub numer grupy w polu **Numer konta/grupy**.</span><span class="sxs-lookup"><span data-stu-id="5c27e-124">If you selected **Group** or **Table** in the **Account code** field, select an account number or group number in the **Account/Group number** field.</span></span>
7. <span data-ttu-id="5c27e-125">W odpowiednich polach wybierz konto główne leasingu finansowego i konto główne leasingu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="5c27e-125">In the appropriate fields, select the finance lease main account and the operating lease main account.</span></span>

<span data-ttu-id="5c27e-126">Po wykonaniu tych kroków można dodawać wydatki za pomocą wierszy w sekcji **Harmonogram płatności kosztów wykonawczych** na stronie **Szczegóły wynajmu** dla wybranej umowy wynajmu.</span><span class="sxs-lookup"><span data-stu-id="5c27e-126">When you've completed these steps, you can add expenses through the **Executory costs payment schedule** lines on the **Lease details** page of a selected lease.</span></span> <span data-ttu-id="5c27e-127">Wydatki można dodawać również podczas tworzenia nowej umowy wynajmu.</span><span class="sxs-lookup"><span data-stu-id="5c27e-127">Alternatively, you can add expenses when you create a new lease.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]