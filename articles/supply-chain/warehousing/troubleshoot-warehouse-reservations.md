---
title: Rozwiązywanie problemów z rezerwacjami w module zarządzania magazynem
description: W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pracy z rezerwacjami w magazynie w Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: d0d73396772ed9e8397797d6685fb550d911303b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828113"
---
# <a name="troubleshoot-reservations-in-warehouse-management"></a><span data-ttu-id="40432-103">Rozwiązywanie problemów z rezerwacjami w module zarządzania magazynem</span><span class="sxs-lookup"><span data-stu-id="40432-103">Troubleshoot reservations in warehouse management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="40432-104">W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pracy z rezerwacjami w magazynie w Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="40432-104">This topic describes how to fix common issues that you might encounter while you work with warehouse reservations in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="40432-105">Aby uzyskać tematy związane z rejestracją numerów partii i numerów seryjnych, zobacz [Rozwiązywanie problemów z hierarchiami rezerwacji partii i numerów seryjnych w magazynie](troubleshoot-warehouse-batch-and-serial-reservation-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="40432-105">For topics that are related to batch and serial number registrations, see [Troubleshoot warehouse batch and serial reservation hierarchies](troubleshoot-warehouse-batch-and-serial-reservation-hierarchies.md).</span></span>

## <a name="i-receive-the-following-error-message-reservations-cannot-be-removed-because-there-is-work-created-which-relies-on-the-reservations"></a><span data-ttu-id="40432-106">Otrzymuje następujący komunikat o błędzie: „Nie można usunąć rezerwacji, ponieważ utworzono pracę, która opiera się na rezerwacjach”.</span><span class="sxs-lookup"><span data-stu-id="40432-106">I receive the following error message: "Reservations cannot be removed because there is work created which relies on the reservations."</span></span>

### <a name="issue-description"></a><span data-ttu-id="40432-107">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="40432-107">Issue description</span></span>

<span data-ttu-id="40432-108">Nie można usunąć rezerwacji zapasów w wierszu sprzedaży, ponieważ w wierszu istnieje otwarta praca.</span><span class="sxs-lookup"><span data-stu-id="40432-108">You can't unreserve inventory on a sales line, because there is open work against the line.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="40432-109">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="40432-109">Issue resolution</span></span>

<span data-ttu-id="40432-110">Sprawdź, czy istnieje otwarta grupa załadunkowa, aby przenieść pozycję z stacji pakowania do innej lokalizacji (np. *Brama dokowa*).</span><span class="sxs-lookup"><span data-stu-id="40432-110">Investigate whether open packing group work exists to bring the item from a packing station to another location (such as *Baydoor*).</span></span> <span data-ttu-id="40432-111">Przejrzyj rekordy w **Dzienniku historii tworzenia pracy** i **Szczegóły pracy**, aby określić, co fizycznie rezerwuje zapasy, a następnie ukończyć lub usunąć pracę, aby zwolnić rezerwację.</span><span class="sxs-lookup"><span data-stu-id="40432-111">Review the records on the **Work creation history log** and **Work details** pages to determine what is physically reserving the inventory, and then complete or delete the work to free up the reservation.</span></span>

## <a name="i-receive-the-following-error-message-inventory-quantity--1-could-not-be-updated-due-to-insufficient-inventory-transactions-for-item-2"></a><span data-ttu-id="40432-112">Zgłaszany jest następujący komunikat o błędzie: „Ilość zapasów -%1 nie zostać zaktualizowane z powodu niewystarczających transakcji magazynowych dla pozycji %2”...</span><span class="sxs-lookup"><span data-stu-id="40432-112">I receive the following error message: "Inventory quantity -%1 could not be updated due to insufficient inventory transactions for item %2...."</span></span>

### <a name="issue-description"></a><span data-ttu-id="40432-113">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="40432-113">Issue description</span></span>

<span data-ttu-id="40432-114">Ten problem może wystąpić, jeśli system nie może zaktualizować ilości zapasów, ponieważ nie ma wystarczającej liczby transakcji magazynowych o określonych wymiarach.</span><span class="sxs-lookup"><span data-stu-id="40432-114">This issue can occur if the system can't update an inventory quantity because there aren't enough inventory transactions that have the specified dimensions.</span></span> <span data-ttu-id="40432-115">Oto pełen tekst całego komunikatu o błędzie:</span><span class="sxs-lookup"><span data-stu-id="40432-115">Here is the full text of the full error message:</span></span>

> <span data-ttu-id="40432-116">Ilość zapasów -%1 nie zostać zaktualizowane z powodu niewystarczających transakcji magazynowych dla pozycji %2 o wymiarze Wymiar=%3, Kolor=%4, Dodatki=%5, Oddział=%6, Magazyn=%7, Lokalizacja=%8, Stan zapasów=dostępny, Numer identyfikacyjny=%9, Numer partii=%10 dla identyfikatora odwołania %11 w identyfikatorze partii %12.</span><span class="sxs-lookup"><span data-stu-id="40432-116">Inventory quantity -%1 could not be updated due to insufficient inventory transactions for item %2 with dimensions Size=%3, Color=%4, Additions=%5, Site=%6, Warehouse=%7, Location=%8, Inventory status=Available, License plate=%9, Batch number=%10 for reference ID %11 on Lot ID %12.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="40432-117">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="40432-117">Issue resolution</span></span>

<span data-ttu-id="40432-118">Upewnij się, że żadne transakcje magazynowe nie rezerwują ilości fizycznie.</span><span class="sxs-lookup"><span data-stu-id="40432-118">Make sure that no inventory transactions are physically reserving the quantity.</span></span> <span data-ttu-id="40432-119">Na przykład te transakcje mogą otwierać zlecenia kontroli jakości, rekordy blokowania zapasów lub zamówienia wyjścia.</span><span class="sxs-lookup"><span data-stu-id="40432-119">For example, these transactions might open quality orders, inventory blocking records, or output orders.</span></span>

## <a name="i-receive-the-following-error-message-physical-on-handcannot-be-reserved-because-only-000-are-available-in-the-inventory"></a><span data-ttu-id="40432-120">Zgłaszany jest następujący komunikat o błędzie: „Fizycznie dostępne zapasy... nie mogą być zarezerwowane, ponieważ w magazynie jest dostępnych tylko 0,00”.</span><span class="sxs-lookup"><span data-stu-id="40432-120">I receive the following error message: "Physical on-hand...cannot be reserved because only 0.00 are available in the inventory."</span></span>

### <a name="issue-description"></a><span data-ttu-id="40432-121">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="40432-121">Issue description</span></span>

<span data-ttu-id="40432-122">Ten problem może wystąpić, jeśli system nie może zaktualizować ilości zapasów, ponieważ nie ma wystarczającej liczby transakcji magazynowych o określonych wymiarach.</span><span class="sxs-lookup"><span data-stu-id="40432-122">This issue can occur if the system can't update an inventory quantity because there aren't enough inventory transactions that have the specified dimensions.</span></span> <span data-ttu-id="40432-123">Oto pełen tekst całego komunikatu o błędzie:</span><span class="sxs-lookup"><span data-stu-id="40432-123">Here is the full text of the full error message:</span></span>

> <span data-ttu-id="40432-124">Fizycznie dostępne w oddziale=%1, Magazyn=%2, Stan zapasów=dostępne, Numer partii=%3, Właściciel=%4: %5 nie może zostać zarezerwowane, ponieważ w magazynie jest dostępnych tylko 0,00.</span><span class="sxs-lookup"><span data-stu-id="40432-124">Physical on-hand Site=%1, Warehouse=%2, Inventory status=Available, Batch number=%3, Owner=%4: %5 cannot be reserved because only 0.00 are available in the inventory.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="40432-125">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="40432-125">Issue resolution</span></span>

<span data-ttu-id="40432-126">Ten problem jest prawdopodobnie spowodowany otwarta pracą.</span><span class="sxs-lookup"><span data-stu-id="40432-126">This issue is probably caused by open work.</span></span> <span data-ttu-id="40432-127">Ukończ pracę lub odbierz bez tworzenia pracy.</span><span class="sxs-lookup"><span data-stu-id="40432-127">Either complete the work or receive without work creation.</span></span> <span data-ttu-id="40432-128">Upewnij się, że żadne transakcje magazynowe nie rezerwują ilości fizycznie.</span><span class="sxs-lookup"><span data-stu-id="40432-128">Make sure that no inventory transactions are physically reserving the quantity.</span></span> <span data-ttu-id="40432-129">Na przykład tymi transakcjami mogą być otwarte zlecenia kontroli jakości, rekordy blokowania zapasów lub zamówienia wyjścia.</span><span class="sxs-lookup"><span data-stu-id="40432-129">For example, these transactions might be open quality orders, inventory blocking records, or output orders.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
