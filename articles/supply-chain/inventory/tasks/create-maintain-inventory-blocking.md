---
title: Tworzenie i obsługa blokowania zapasów
description: W tym temacie opisano sposób korzystania z funkcji blokowania zapasów, aby zapobiec rezerwowaniu fizycznie dostępnych zapasów przez inne dokumenty źródłowe.
author: perlynne
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventBlocking, InventItemIdLookupSimple, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e9aa38ca52da577fff258bb330922ad7f4044330
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956165"
---
# <a name="create-and-maintain-an-inventory-blocking"></a><span data-ttu-id="db8d1-103">Tworzenie i obsługa blokowania zapasów</span><span class="sxs-lookup"><span data-stu-id="db8d1-103">Create and maintain an inventory blocking</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="db8d1-104">W tym temacie opisano sposób korzystania z funkcji blokowania zapasów, aby zapobiec rezerwowaniu fizycznie dostępnych zapasów przez inne dokumenty źródłowe.</span><span class="sxs-lookup"><span data-stu-id="db8d1-104">This topic describes how to use an inventory blocking to prevent physical on-hand inventory from being reserved by other outbound source documents.</span></span> <span data-ttu-id="db8d1-105">Przed rozpoczęciem procedury opisanych w tym temacie musisz mieć fizycznie dostępne zapasy towaru.</span><span class="sxs-lookup"><span data-stu-id="db8d1-105">Before you start the procedures in this topic, you must have an item that physical on-hand inventory is available for.</span></span>

## <a name="block-inventory"></a><span data-ttu-id="db8d1-106">Blokuj zapasy</span><span class="sxs-lookup"><span data-stu-id="db8d1-106">Block inventory</span></span>

<span data-ttu-id="db8d1-107">Aby utworzyć rekord blokowania zapasów w celu zablokowania zapasów, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="db8d1-107">To create an inventory blocking record so that inventory is blocked, follow these steps.</span></span>

1. <span data-ttu-id="db8d1-108">Kliknij kolejno opcje **Zarządzanie zapasami \> Zadania okresowe \> Blokowanie zapasów**.</span><span class="sxs-lookup"><span data-stu-id="db8d1-108">Go to **Inventory management \> Periodic tasks \> Inventory blocking**.</span></span>
1. <span data-ttu-id="db8d1-109">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="db8d1-109">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="db8d1-110">W nagłówku nowego rekordu blokowania ustaw w polu **Kod towaru** towar, który chcesz zablokować, i wprowadź opis.</span><span class="sxs-lookup"><span data-stu-id="db8d1-110">On the header of the new blocking record, set the **Item number** field to the item that you want to block, and enter a description.</span></span>
1. <span data-ttu-id="db8d1-111">Na skróconej karcie **Ogólne** w polu **Ilość** wpisz liczbę towarów do zablokowania.</span><span class="sxs-lookup"><span data-stu-id="db8d1-111">On the **General** FastTab, in the **Quantity** field, enter the number of items to block.</span></span>
1. <span data-ttu-id="db8d1-112">Na skróconej karcie **Wymiary magazynowe** określ lokalizację i magazyn, w którym znajdują się zablokowane towary.</span><span class="sxs-lookup"><span data-stu-id="db8d1-112">On the **Inventory dimensions** FastTab, specify the site and warehouse where the items that you want to block are currently located.</span></span>
1. <span data-ttu-id="db8d1-113">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="db8d1-113">On the Action Pane, select **Save**.</span></span>

## <a name="update-the-conditions-of-the-inventory-blocking"></a><span data-ttu-id="db8d1-114">Aktualizowanie warunków blokowania zapasów</span><span class="sxs-lookup"><span data-stu-id="db8d1-114">Update the conditions of the inventory blocking</span></span>

<span data-ttu-id="db8d1-115">Aby zaktualizować rekord blokowania zapasów, wykonaj następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="db8d1-115">To update an inventory blocking record, follow these steps.</span></span>

1. <span data-ttu-id="db8d1-116">Kliknij kolejno opcje **Zarządzanie zapasami \> Zadania okresowe \> Blokowanie zapasów**.</span><span class="sxs-lookup"><span data-stu-id="db8d1-116">Go to **Inventory management \> Periodic tasks \> Inventory blocking**.</span></span>
1. <span data-ttu-id="db8d1-117">W okienku listy wybierz odpowiedni rekord blokowania.</span><span class="sxs-lookup"><span data-stu-id="db8d1-117">In the list pane, select the relevant blocking record.</span></span>
1. <span data-ttu-id="db8d1-118">Edytuj rekord stosownie do potrzeb.</span><span class="sxs-lookup"><span data-stu-id="db8d1-118">Edit the record as required.</span></span> <span data-ttu-id="db8d1-119">Możesz na przykład zmienić wartość pola **Oczekiwana data**, aby wskazać, kiedy zablokowane zapasy powinny stać się dostępne do rezerwacji.</span><span class="sxs-lookup"><span data-stu-id="db8d1-119">For example, you might change the value of the **Expected date** field to indicate when the blocked inventory is expected to become available for reservation.</span></span> <span data-ttu-id="db8d1-120">Jeśli jest wybrana opcja **Oczekiwane przyjęcia**, data będzie wyświetlana w oczekiwanej transakcji.</span><span class="sxs-lookup"><span data-stu-id="db8d1-120">If the **Expected receipts** option is selected, the date will appear on the expected transaction.</span></span> <span data-ttu-id="db8d1-121">(Opcja **Oczekiwane przyjęcia** jest domyślnie wybrana, gdy ręcznie tworzysz rekord blokowania).</span><span class="sxs-lookup"><span data-stu-id="db8d1-121">(The **Expected receipts** option is selected by default when you manually create a blocking record.)</span></span>
1. <span data-ttu-id="db8d1-122">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="db8d1-122">On the Action Pane, select **Save**.</span></span>

## <a name="unblock-inventory"></a><span data-ttu-id="db8d1-123">Odblokowywanie zapasów</span><span class="sxs-lookup"><span data-stu-id="db8d1-123">Unblock inventory</span></span>

<span data-ttu-id="db8d1-124">Aby usunąć rekord blokowania zapasów w celu odblokowania zapasów, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="db8d1-124">To remove an inventory blocking record so that inventory is unblocked, follow these steps.</span></span>

1. <span data-ttu-id="db8d1-125">Kliknij kolejno opcje **Zarządzanie zapasami \> Zadania okresowe \> Blokowanie zapasów**.</span><span class="sxs-lookup"><span data-stu-id="db8d1-125">Go to **Inventory management \> Periodic tasks \> Inventory blocking**.</span></span>
1. <span data-ttu-id="db8d1-126">W okienku listy wybierz odpowiedni rekord blokowania.</span><span class="sxs-lookup"><span data-stu-id="db8d1-126">In the list pane, select the relevant blocking record.</span></span>
1. <span data-ttu-id="db8d1-127">W okienku akcji wybierz opcję **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="db8d1-127">On the Action Pane, select **Delete**.</span></span>
1. <span data-ttu-id="db8d1-128">Zostanie wyświetlony monit o potwierdzenie operacji.</span><span class="sxs-lookup"><span data-stu-id="db8d1-128">You're prompted to confirm the operation.</span></span> <span data-ttu-id="db8d1-129">Wybierz przycisk **Tak**, aby kontynuować.</span><span class="sxs-lookup"><span data-stu-id="db8d1-129">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="db8d1-130">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="db8d1-130">Close the page.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
