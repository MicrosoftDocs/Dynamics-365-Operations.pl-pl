---
title: Typy problemów w niezgodnościach
description: W tym temacie opisano sposób tworzenia i używania typów problemów w niezgodnościach.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventProblemType, InventProblemTypeSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 742edec8570610efe41a2c627efd1df586e0733e
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022163"
---
# <a name="problem-types-for-nonconformances"></a><span data-ttu-id="8d15b-103">Typy problemów w niezgodnościach</span><span class="sxs-lookup"><span data-stu-id="8d15b-103">Problem types for nonconformances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8d15b-104">W tym temacie opisano sposób tworzenia i używania typów problemów w niezgodnościach.</span><span class="sxs-lookup"><span data-stu-id="8d15b-104">This topic describes how to create and use problem types for nonconformances.</span></span>

<span data-ttu-id="8d15b-105">Strona **Typ problemu** służy do definiowania klasyfikacji problemów z jakością, które mogą występować w różnych typach niezgodności.</span><span class="sxs-lookup"><span data-stu-id="8d15b-105">You use the **Problem types** page to define a classification of the quality problems that might occur for the various nonconformance types.</span></span> <span data-ttu-id="8d15b-106">Dla każdego tworzonego problemu należy określić typy niezgodności, z którymi będzie on używany.</span><span class="sxs-lookup"><span data-stu-id="8d15b-106">For each problem type that you create, you must specify the types of nonconformances that the problem type can be used with.</span></span> <span data-ttu-id="8d15b-107">Możliwe jest skonfigurowanie następujących typów niezgodności:</span><span class="sxs-lookup"><span data-stu-id="8d15b-107">You can set up the following nonconformance types:</span></span>

- <span data-ttu-id="8d15b-108">**Wewnętrzne** — niezgodności tego typu są związane z dostępnymi zapasami (na przykład zleceniami kontroli jakości lub zleceniami kwarantanny).</span><span class="sxs-lookup"><span data-stu-id="8d15b-108">**Internal** – Nonconformances of this type are related to on-hand inventory (for example, quality orders or quarantine orders).</span></span>
- <span data-ttu-id="8d15b-109">**Odbiorca** — niezgodności tego typu są związane z zamówieniami sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="8d15b-109">**Customer** – Nonconformances of this type are related to sales orders.</span></span>
- <span data-ttu-id="8d15b-110">**Dostawca** — niezgodności tego typu są związane z zamówieniami zakupu.</span><span class="sxs-lookup"><span data-stu-id="8d15b-110">**Vendor** – Nonconformances of this type are related to purchase orders.</span></span>
- <span data-ttu-id="8d15b-111">**Zlecenie usługi** — niezgodności tego typu są związane ze zleceniami serwisowymi.</span><span class="sxs-lookup"><span data-stu-id="8d15b-111">**Service request** – Nonconformances of this type are related to service orders.</span></span>
- <span data-ttu-id="8d15b-112">**Produkcja** — Niezgodności tego typu są związane z zamówieniami partii lub zleceniami produkcyjnymi.</span><span class="sxs-lookup"><span data-stu-id="8d15b-112">**Production** – Nonconformances of this type are related to batch orders or production orders.</span></span>
- <span data-ttu-id="8d15b-113">**Wytwarzanie produktu towarzyszącego** — Niezgodności tego typu są związane z zamówieniami partii na produkty towarzyszące.</span><span class="sxs-lookup"><span data-stu-id="8d15b-113">**Co-product production** – Nonconformances of this type are related to batch orders for co-products.</span></span>

<span data-ttu-id="8d15b-114">Podczas tworzenia nowego typu problemu w okienku akcji wybierz opcję **Typy niezgodności**, aby utworzyć listę co najmniej jednego typu niezgodności autoryzowanych dla tego typu problemu.</span><span class="sxs-lookup"><span data-stu-id="8d15b-114">When you create a new problem type, select **Non conformance types** on the Action Pane to create a list of one or more nonconformance types that are authorized for the problem type.</span></span> <span data-ttu-id="8d15b-115">Dzięki temu typ problemu, który jest związany z wadliwym kodem, może być stosowany do wszystkich typów niezgodności.</span><span class="sxs-lookup"><span data-stu-id="8d15b-115">For example, a problem type that is related to a defect code might apply to all nonconformance types.</span></span> <span data-ttu-id="8d15b-116">Jednak typ problemu związany ze skargami klientów może dotyczyć tylko typów niezgodności **Odbiorca** i **Zlecenie usługi**.</span><span class="sxs-lookup"><span data-stu-id="8d15b-116">However, a problem type that is related to customer complaints might apply only to the **Customer** and **Service request** nonconformance types.</span></span>

## <a name="examples-of-problem-types"></a><span data-ttu-id="8d15b-117">Przykłady typów problemu</span><span class="sxs-lookup"><span data-stu-id="8d15b-117">Examples of problem types</span></span>

<span data-ttu-id="8d15b-118">Oto kilka przykładów scenariuszy typów problemów, których można używać z różnymi typami niezgodności:</span><span class="sxs-lookup"><span data-stu-id="8d15b-118">Here are some examples of scenarios for problem types that can be used with the different nonconformance types:</span></span>

- <span data-ttu-id="8d15b-119">**Odbiorca:** złożenie reklamacji przez odbiorcę, wykonanie zwrotu przez odbiorcę lub niespełnienie specyfikacji jakościowych.</span><span class="sxs-lookup"><span data-stu-id="8d15b-119">**Customer:** A customer filed a complaint, a customer made a return, or quality specifications weren't met.</span></span>
- <span data-ttu-id="8d15b-120">**Dostawca:** produkt został uszkodzony, specyfikacje jakości nie zostały spełnione lub odebrano niewłaściwy produkt.</span><span class="sxs-lookup"><span data-stu-id="8d15b-120">**Vendor:** The product was damaged, quality specifications weren't met, or the wrong product was received.</span></span>
- <span data-ttu-id="8d15b-121">**Zlecenie usługi:** niespełnienie specyfikacji jakościowych, złożenie reklamacji przez odbiorcę lub wymagana konserwacja maszyny.</span><span class="sxs-lookup"><span data-stu-id="8d15b-121">**Service request:** Quality specifications weren't met, a customer filed a complaint, or machine maintenance is required.</span></span>
- <span data-ttu-id="8d15b-122">**Produkcja:** specyfikacje jakości nie zostały spełnione, konserwacja maszyny jest wymagana lub produkt został uszkodzony.</span><span class="sxs-lookup"><span data-stu-id="8d15b-122">**Production:** Quality specifications weren't met, machine maintenance is required, or the product was damaged.</span></span>
- <span data-ttu-id="8d15b-123">**Wytwarzanie produktu towarzyszącego:** specyfikacje jakości nie zostały spełnione, konserwacja maszyny jest wymagana lub produkt został uszkodzony.</span><span class="sxs-lookup"><span data-stu-id="8d15b-123">**Co-product production:** Quality specifications weren't met, machine maintenance is required, or the product was damaged.</span></span>

## <a name="create-a-problem-type-and-assign-it-to-nonconformance-types"></a><span data-ttu-id="8d15b-124">Tworzenie typu problemu i przypisywanie go do typów niezgodności</span><span class="sxs-lookup"><span data-stu-id="8d15b-124">Create a problem type and assign it to nonconformance types</span></span>

1. <span data-ttu-id="8d15b-125">Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Zarządzanie jakością \> Typy problemów**.</span><span class="sxs-lookup"><span data-stu-id="8d15b-125">Go to **Inventory management \> Setup \> Quality management \> Problem types**.</span></span>
1. <span data-ttu-id="8d15b-126">W okienku akcji wybierz opcję **Nowy**, aby dodać nowy wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="8d15b-126">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="8d15b-127">Następnie ustaw następujące pola dla nowego wiersza:</span><span class="sxs-lookup"><span data-stu-id="8d15b-127">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="8d15b-128">**Typ problemu** — służy do wprowadzania unikatowego identyfikatora lub nazwy typu problemu.</span><span class="sxs-lookup"><span data-stu-id="8d15b-128">**Problem type** – Enter a unique ID or name for the problem type.</span></span>
    - <span data-ttu-id="8d15b-129">**Opis** – wprowadź szczegółowy opis typu problemu.</span><span class="sxs-lookup"><span data-stu-id="8d15b-129">**Description** – Enter a detailed description of the problem type.</span></span>

1. <span data-ttu-id="8d15b-130">Gdy nowy wiersz jest nadal zaznaczony, wybierz opcję **Typy niezgodności** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="8d15b-130">While the new row is still selected, select **Non conformance types** on the Action Pane.</span></span>
1. <span data-ttu-id="8d15b-131">W okienku akcji wybierz opcję **Nowy**, aby dodać nowy wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="8d15b-131">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="8d15b-132">Następnie dla nowego wiersza ustaw w polu **Typ niezgodności** typ niezgodności, który ma być dozwolony dla tego typu problemu.</span><span class="sxs-lookup"><span data-stu-id="8d15b-132">Then, for the new row, set the **Non conformance type** field to the nonconformance type that you want to allow for the problem type.</span></span>
1. <span data-ttu-id="8d15b-133">Powtórz poprzedni krok dla każdego dodatkowego typu niezgodności, który chcesz autoryzować dla tego typu problemu.</span><span class="sxs-lookup"><span data-stu-id="8d15b-133">Repeat the previous step for each additional nonconformance type that you want to authorize for the problem type.</span></span>
1. <span data-ttu-id="8d15b-134">Zamknij strony.</span><span class="sxs-lookup"><span data-stu-id="8d15b-134">Close the pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8d15b-135">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="8d15b-135">Additional resources</span></span>

- [<span data-ttu-id="8d15b-136">Omówienie zarządzanie jakością</span><span class="sxs-lookup"><span data-stu-id="8d15b-136">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="8d15b-137">Włączanie zarządzania kontrolą jakości i niezgodnością</span><span class="sxs-lookup"><span data-stu-id="8d15b-137">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="8d15b-138">Pracownicy odpowiedzialni za zatwierdzanie niezgodności</span><span class="sxs-lookup"><span data-stu-id="8d15b-138">Workers responsible for approving nonconformances</span></span>](quality-responsible-workers.md)
- [<span data-ttu-id="8d15b-139">Strefy kwarantanny niezgodności</span><span class="sxs-lookup"><span data-stu-id="8d15b-139">Quarantine zones for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="8d15b-140">Typy diagnostyki niezgodności</span><span class="sxs-lookup"><span data-stu-id="8d15b-140">Diagnostic types for nonconformances</span></span>](quality-diagnostic-types.md)
- [<span data-ttu-id="8d15b-141">Opłaty związane z kontrolą jakości dla niezgodności</span><span class="sxs-lookup"><span data-stu-id="8d15b-141">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="8d15b-142">Operacje dotyczące niezgodności</span><span class="sxs-lookup"><span data-stu-id="8d15b-142">Operations for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="8d15b-143">Zarządzanie jakością dla procesów magazynowych</span><span class="sxs-lookup"><span data-stu-id="8d15b-143">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
