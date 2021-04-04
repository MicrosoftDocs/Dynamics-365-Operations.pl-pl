---
title: Ustawienia stanu podróży
description: W tym temacie opisano sposób ustanawiania wartości stanu, które użytkownicy mogą przypisywać do podróży.
author: sherry-zheng
manager: tfehr
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMStatusTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: b7180cc9ab2d13f2260635d717adb7aab2177ab9
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500893"
---
# <a name="voyage-status-setup"></a><span data-ttu-id="c6588-103">Ustawienia stanu podróży</span><span class="sxs-lookup"><span data-stu-id="c6588-103">Voyage status setup</span></span>

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="c6588-104">Na stronie **Stany podróży** ustal zestaw wartości stanów, które użytkownicy mogą przypisywać do podróży.</span><span class="sxs-lookup"><span data-stu-id="c6588-104">On the **Voyage statuses** page, you establish the set of status values that users can assign to voyages.</span></span> <span data-ttu-id="c6588-105">Użytkownicy mogą przypisywać wartości statusu podróży do wszystkich poziomów podróży: rejsu, kontenera wysyłkowego, folio, zamówienia zakupu i pozycji (linie zakupu i zamówienia przeniesienia).</span><span class="sxs-lookup"><span data-stu-id="c6588-105">Users can assign voyage status values to all levels of a voyage: voyage, shipping container, folio, purchase order, and item (purchase lines and transfer order lines).</span></span> <span data-ttu-id="c6588-106">Są one używane do dwóch celów:</span><span class="sxs-lookup"><span data-stu-id="c6588-106">They are used for two purposes:</span></span>

- <span data-ttu-id="c6588-107">Poinformuj użytkownika o statusie podróży, kontenerze wysyłkowym, folio, zamówieniu zakupu lub pozycji (wiersze zakupu i wiersze zamówienia przeniesienia).</span><span class="sxs-lookup"><span data-stu-id="c6588-107">Inform the user about the status of the voyage, shipping container, folio, purchase order, or item (purchase lines and transfer order lines).</span></span>
- <span data-ttu-id="c6588-108">Ograniczenie użycia obszaru kosztów przez zapobieganie modyfikacji lub usunięciu.</span><span class="sxs-lookup"><span data-stu-id="c6588-108">Limit the use of the cost area by preventing modification or deletion.</span></span>

<span data-ttu-id="c6588-109">Aby skonfigurować stany podróży, przejdź do **Koszt dostawy \> Konfiguracja \> Stany podróży**.</span><span class="sxs-lookup"><span data-stu-id="c6588-109">To set up your voyage statuses, go to **Landed cost \> Setup \> Voyage statuses**.</span></span> <span data-ttu-id="c6588-110">Można tam dodawać, usuwać i edytować stany za pomocą przycisków w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="c6588-110">There, you can add, remove, and edit statuses by using the buttons on the Action Pane.</span></span>

<span data-ttu-id="c6588-111">Dla każdego obszaru kosztów jest ustawiony własny zestaw oraz hierarchia stanów podróży.</span><span class="sxs-lookup"><span data-stu-id="c6588-111">Each cost area has its own set and hierarchy of voyage statuses.</span></span> <span data-ttu-id="c6588-112">Dlatego na stronie **Stany podróży**, w polu **Obszar kosztów**, należy najpierw wybrać obszar kosztów, dla którego chcesz wyświetlić lub utworzyć stany podróży.</span><span class="sxs-lookup"><span data-stu-id="c6588-112">Therefore, on the **Voyage statuses** page, in the **Cost area** field, you must first select the cost area that you want to view or create voyage statuses for.</span></span> <span data-ttu-id="c6588-113">Następnie, w razie potrzeby, dla każdego stanu podróży należy ustawić pola opisane w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="c6588-113">Then, for each voyage status, set the fields that are described in the following table, as required.</span></span> <span data-ttu-id="c6588-114">Zwróć uwagę, że status podróży może być również automatycznie zmieniany przez zdarzenia systemowe, takie jak reguły, które zostały ustanowione przy użyciu centrum kontroli śledzenia.</span><span class="sxs-lookup"><span data-stu-id="c6588-114">Note that the status of a voyage can also be automatically changed by system events, such as rules that have been established by using the tracking control center.</span></span>

| <span data-ttu-id="c6588-115">Pole</span><span class="sxs-lookup"><span data-stu-id="c6588-115">Field</span></span> | <span data-ttu-id="c6588-116">opis</span><span class="sxs-lookup"><span data-stu-id="c6588-116">Description</span></span> |
|---|---|
| <span data-ttu-id="c6588-117">Stan podróży</span><span class="sxs-lookup"><span data-stu-id="c6588-117">Voyage status</span></span> | <span data-ttu-id="c6588-118">Wprowadź nazwę statusu podróży.</span><span class="sxs-lookup"><span data-stu-id="c6588-118">Enter the name of the voyage status.</span></span> |
| <span data-ttu-id="c6588-119">opis</span><span class="sxs-lookup"><span data-stu-id="c6588-119">Description</span></span> | <span data-ttu-id="c6588-120">Wprowadź opis wybranego stanu podróży.</span><span class="sxs-lookup"><span data-stu-id="c6588-120">Enter a description of the voyage status.</span></span> |
| <span data-ttu-id="c6588-121">Modyfikuj</span><span class="sxs-lookup"><span data-stu-id="c6588-121">Modify</span></span> | <span data-ttu-id="c6588-122">To pole wyboru należy zaznaczyć, jeśli użytkownicy mogą modyfikować podróże o tym stanie.</span><span class="sxs-lookup"><span data-stu-id="c6588-122">Select this check box if users are allowed to modify voyages that have this status.</span></span> |
| <span data-ttu-id="c6588-123">Usuwanie</span><span class="sxs-lookup"><span data-stu-id="c6588-123">Delete</span></span> | <span data-ttu-id="c6588-124">Zaznacz to pole wyboru, jeśli użytkownicy mogą usuwać podróże o tym statusie.</span><span class="sxs-lookup"><span data-stu-id="c6588-124">Select this check box if users are allowed to delete voyages that have this status.</span></span> |
| <span data-ttu-id="c6588-125">Wymagany</span><span class="sxs-lookup"><span data-stu-id="c6588-125">Mandatory</span></span> | <span data-ttu-id="c6588-126">Zaznacz to pole wyboru, aby status podróży był obowiązkowy i nie można go było pominąć.</span><span class="sxs-lookup"><span data-stu-id="c6588-126">Select this check box to make the voyage status mandatory, so that it can't be skipped.</span></span> |
| <span data-ttu-id="c6588-127">Nadrzędne</span><span class="sxs-lookup"><span data-stu-id="c6588-127">Parent</span></span> | <span data-ttu-id="c6588-128">To pole pozwala ustanowić hierarchię między wartościami stanu.</span><span class="sxs-lookup"><span data-stu-id="c6588-128">Use this field to establish a hierarchy among the status values.</span></span> <span data-ttu-id="c6588-129">Stany podróży można zmieniać (ręcznie lub automatycznie) tylko w dół hierarchii, z stanu nadrzędnego na jeden z jego stanów podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="c6588-129">Voyage statuses can be changed (either manually or automatically) only downward in the hierarchy, from a parent status to one of its child statuses.</span></span>

> [!NOTE]
> <span data-ttu-id="c6588-130">Należy skonfigurować tylko określone stany podróży używane przez organizację.</span><span class="sxs-lookup"><span data-stu-id="c6588-130">You have to set up only the specific voyage statuses that your organization uses.</span></span> <span data-ttu-id="c6588-131">Do typowych stanów podróży należą: *Potwierdzone*, *Towary w transporcie*, *Odebrane*, *Gotowe do wyceny* i *Wycenone*.</span><span class="sxs-lookup"><span data-stu-id="c6588-131">Typical voyage statuses include *Confirmed*, *Goods in transit*, *Received*, *Ready for costing*, and *Costed*.</span></span> <span data-ttu-id="c6588-132">Mogą jednak wystąpić inne stany.</span><span class="sxs-lookup"><span data-stu-id="c6588-132">However, other statuses might be present.</span></span>
