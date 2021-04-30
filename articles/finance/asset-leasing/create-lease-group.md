---
title: Tworzenie grupy wynajmu
description: W tym temacie opisano sposób konfigurowania grup wynajmu. Grupy wynajmu są wymagane do tworzenia nowych wynajmów.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseGroupTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 88a49e4db868078fd05875df33ca5727363aaa18
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881235"
---
# <a name="create-a-lease-group"></a><span data-ttu-id="f95b9-104">Tworzenie grupy wynajmu</span><span class="sxs-lookup"><span data-stu-id="f95b9-104">Create a lease group</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f95b9-105">W tym temacie opisano sposób konfigurowania grup wynajmu.</span><span class="sxs-lookup"><span data-stu-id="f95b9-105">This topic explains how to set up lease groups.</span></span> <span data-ttu-id="f95b9-106">Grupy wynajmu są wymagane do tworzenia nowych wynajmów.</span><span class="sxs-lookup"><span data-stu-id="f95b9-106">Lease groups are required to create new leases.</span></span> <span data-ttu-id="f95b9-107">Księgi wynajmu są skojarzone z każdą grupą wynajmu.</span><span class="sxs-lookup"><span data-stu-id="f95b9-107">Lease books are associated with each lease group.</span></span> <span data-ttu-id="f95b9-108">Księgi wynajmu decydują o domyślnych księgach, które muszą zostać utworzone dla każdego wynajmu.</span><span class="sxs-lookup"><span data-stu-id="f95b9-108">Lease books determine the default books that must be created for each lease.</span></span> <span data-ttu-id="f95b9-109">Określone konta można przypisać do grupy wynajmu na stronie **Parametry księgowania wynajmu**.</span><span class="sxs-lookup"><span data-stu-id="f95b9-109">You can assign specific accounts to a lease group on the **Lease posting parameters** page.</span></span>

## <a name="create-a-lease-book-and-add-a-lease-group"></a><span data-ttu-id="f95b9-110">Tworzenie książki wynajmu i dodawanie grupy wynajmu</span><span class="sxs-lookup"><span data-stu-id="f95b9-110">Create a lease book and add a lease group</span></span>

1. <span data-ttu-id="f95b9-111">Przejdź do **Wynajem składnika majątku \> Ustawienia \> Grupy wynajmu**.</span><span class="sxs-lookup"><span data-stu-id="f95b9-111">Go to **Asset leasing \> Setup \> Lease groups**.</span></span>
2. <span data-ttu-id="f95b9-112">W okienku akcji wybierz opcję **Nowe**, aby dodać grupę wynajmu.</span><span class="sxs-lookup"><span data-stu-id="f95b9-112">On the Action Pane, select **New** to add a lease group.</span></span> <span data-ttu-id="f95b9-113">Wiersz zostanie dodany do siatki.</span><span class="sxs-lookup"><span data-stu-id="f95b9-113">A line is added to the grid.</span></span>
3. <span data-ttu-id="f95b9-114">W nowym wierszu w polu **Grupa wynajmu** wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="f95b9-114">On the new line, in the **Lease group** field, enter a value.</span></span>
4. <span data-ttu-id="f95b9-115">W polu **Opis** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f95b9-115">In the **Description** field, enter a value.</span></span>

<span data-ttu-id="f95b9-116">Wprowadzone informacje zostaną dodane do pola **Grupa wynajmu** na stronie **Dodaj wynajem**.</span><span class="sxs-lookup"><span data-stu-id="f95b9-116">The information that you just entered is added to the **Lease group** field on the **Add lease** page.</span></span>

## <a name="associate-a-book-with-a-lease-group"></a><span data-ttu-id="f95b9-117">Kojarzenie księgi z grupą wynajmu</span><span class="sxs-lookup"><span data-stu-id="f95b9-117">Associate a book with a lease group</span></span>

<span data-ttu-id="f95b9-118">Po utworzeniu grup wynajmu można przypisać księgi do każdej grupy.</span><span class="sxs-lookup"><span data-stu-id="f95b9-118">After you create lease groups, you can assign books to each group.</span></span> <span data-ttu-id="f95b9-119">Podczas tworzenia wynajmu i przypisywania jej do grupy wynajmu system tworzy zestaw harmonogramów dla każdej księgi skojarzonej z daną grupą wynajmu.</span><span class="sxs-lookup"><span data-stu-id="f95b9-119">When you create a lease and assign it to a lease group, the system creates a set of schedules for each book that is associated with that lease group.</span></span>

> [!NOTE]
> <span data-ttu-id="f95b9-120">Aby można było przypisać księgi do grupy wynajmu, należy je skonfigurować.</span><span class="sxs-lookup"><span data-stu-id="f95b9-120">Books must be set up before they can be assigned to a lease group.</span></span>

1. <span data-ttu-id="f95b9-121">Przejdź do **Wynajem składnika majątku \> Ustawienia \> Grupa wynajmu**.</span><span class="sxs-lookup"><span data-stu-id="f95b9-121">Go to **Asset leasing \> Setup \> Lease group**.</span></span>
2. <span data-ttu-id="f95b9-122">Wybierz grupę wynajmu, a następnie wybierz opcję **Księgi**.</span><span class="sxs-lookup"><span data-stu-id="f95b9-122">Select a lease group, and then select **Books**.</span></span>
3. <span data-ttu-id="f95b9-123">Wybierz opcję **Nowy**, a następnie w polu **Typ księgi** wybierz księgę, która ma zostać przypisana do grupy wynajmu.</span><span class="sxs-lookup"><span data-stu-id="f95b9-123">Select **New**, and then, in the **Book type** field, select the book to assign to the lease group.</span></span> <span data-ttu-id="f95b9-124">Można przypisać wiele ksiąg do grupy wynajmu, jeśli wynajem musi być księgowany na różne sposoby.</span><span class="sxs-lookup"><span data-stu-id="f95b9-124">You can assign multiple books to a lease group if a lease must be accounted for in different ways.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
