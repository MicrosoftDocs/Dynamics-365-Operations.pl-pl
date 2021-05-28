---
title: Opłaty za operacje dotyczące niezgodności
description: W tym temacie opisano sposób tworzenia opłat związanych z kontrolą jakości, które mogą być naliczane za operacje dotyczące niezgodności.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestMiscCharges
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 382890232bff47a885840af1eb7e91d27bb46cae
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022307"
---
# <a name="charges-for-nonconformance-operations"></a><span data-ttu-id="827d3-103">Opłaty za operacje dotyczące niezgodności</span><span class="sxs-lookup"><span data-stu-id="827d3-103">Charges for nonconformance operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="827d3-104">W tym temacie opisano sposób tworzenia opłat związanych z kontrolą jakości, które mogą być naliczane za operacje dotyczące niezgodności.</span><span class="sxs-lookup"><span data-stu-id="827d3-104">This topic describes how to create quality charges that can be used with operations for a nonconformance.</span></span>

<span data-ttu-id="827d3-105">Strona **Opłaty związane z kontrolą jakości** służy do definiowania typów opłat, które można dodawać do operacji dotyczących niezgodności.</span><span class="sxs-lookup"><span data-stu-id="827d3-105">You use the **Quality charges** page to define the types of charges that can be added to operations for a nonconformance.</span></span> <span data-ttu-id="827d3-106">Opłaty umożliwiają śledzenie szczegółów dotyczących obciążeń lub opłat, które są należne odbiorcy za niezgodne produkty lub należne od dostawcy za otrzymane niezgodne produkty.</span><span class="sxs-lookup"><span data-stu-id="827d3-106">Charges let you track details about fees or charges that you owe to a customer for nonconforming products, or that a vendor owes to you for nonconforming products that you received.</span></span> <span data-ttu-id="827d3-107">Opłat można również użyć do śledzenia kosztów, które są wymagane dla zewnętrznych dostawców lub usług w celu wykonania operacji.</span><span class="sxs-lookup"><span data-stu-id="827d3-107">You might also use charges to track costs that are required for external vendors or services to perform an operation.</span></span>

## <a name="examples-of-quality-charges"></a><span data-ttu-id="827d3-108">Przykłady opłat związanych z kontrolą jakości</span><span class="sxs-lookup"><span data-stu-id="827d3-108">Examples of quality charges</span></span>

<span data-ttu-id="827d3-109">Pracujesz dla firmy produkcyjnej.</span><span class="sxs-lookup"><span data-stu-id="827d3-109">You work for a manufacturing company.</span></span> <span data-ttu-id="827d3-110">Twoja firma ma kontrakty z kilkoma dostawcami.</span><span class="sxs-lookup"><span data-stu-id="827d3-110">Your company has contracts with several vendors.</span></span> <span data-ttu-id="827d3-111">W tych umowach są określone standardy wysyłki na czas, uszkodzeń i jakości produktów dla towarów.</span><span class="sxs-lookup"><span data-stu-id="827d3-111">Those contracts outline standards for on-time shipment, damages, and product quality for items.</span></span> <span data-ttu-id="827d3-112">Analogicznie, masz zawarte z kilkoma odbiorcami umowy dotyczące zwrotów, uszkodzeń i jakości produktów.</span><span class="sxs-lookup"><span data-stu-id="827d3-112">Likewise, several of your customers have agreements with your company about returns, damages, and product quality.</span></span>

<span data-ttu-id="827d3-113">Struktura opłat jest definiowana dla każdej okoliczności i określona w umowie.</span><span class="sxs-lookup"><span data-stu-id="827d3-113">A fee structure is defined for each circumstance and specified in the contract.</span></span> <span data-ttu-id="827d3-114">Opłaty związane z kontrolą jakości można konfigurować jako kontur różnych typów opłat, takich jak *Uszkodzenia*, *Opóźnienie wysyłki* czy *Jakość*.</span><span class="sxs-lookup"><span data-stu-id="827d3-114">You can configure quality charges to outline the various types of charges, such as *Damages*, *Late shipment*, and *Quality*.</span></span> <span data-ttu-id="827d3-115">Następnie podczas tworzenia niezgodności dodajesz jedną lub więcej operacji.</span><span class="sxs-lookup"><span data-stu-id="827d3-115">Then, when you create a nonconformance, you add one or more operations.</span></span> <span data-ttu-id="827d3-116">Dla każdej operacji należy wybrać opcję **Opłaty**, aby zdefiniować szczegóły dotyczące opłat.</span><span class="sxs-lookup"><span data-stu-id="827d3-116">For each operation, you select **Charges** to define the details about the fees.</span></span>

## <a name="create-a-quality-charge"></a><span data-ttu-id="827d3-117">Tworzenie opłaty związanej z kontrolą jakości</span><span class="sxs-lookup"><span data-stu-id="827d3-117">Create a quality charge</span></span>

1. <span data-ttu-id="827d3-118">Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Zarządzanie jakością \> Opłaty związane z kontrolą jakości**.</span><span class="sxs-lookup"><span data-stu-id="827d3-118">Go to **Inventory management \> Setup \> Quality management \> Quality charges**.</span></span>
1. <span data-ttu-id="827d3-119">W okienku akcji wybierz opcję **Nowy**, aby dodać nowy wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="827d3-119">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="827d3-120">Następnie ustaw następujące pola dla nowego wiersza:</span><span class="sxs-lookup"><span data-stu-id="827d3-120">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="827d3-121">**Kod opłaty** — służy do wprowadzania unikatowego identyfikatora lub nazwy opłaty związanej z kontrolą jakości.</span><span class="sxs-lookup"><span data-stu-id="827d3-121">**Charges code** – Enter a unique ID or name for the quality charge.</span></span>
    - <span data-ttu-id="827d3-122">**Opis** – wprowadź szczegółowy opis opłaty związanej z kontrolą jakości.</span><span class="sxs-lookup"><span data-stu-id="827d3-122">**Description** – Enter a detailed description of the quality charge.</span></span>

1. <span data-ttu-id="827d3-123">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="827d3-123">Close the page.</span></span>

## <a name="add-a-quality-charge-to-an-operation-for-a-nonconformance"></a><span data-ttu-id="827d3-124">Dodawanie opłaty związanej z kontrolą jakości do operacji dotyczącej niezgodności</span><span class="sxs-lookup"><span data-stu-id="827d3-124">Add a quality charge to an operation for a nonconformance</span></span>

<span data-ttu-id="827d3-125">Aby uzyskać szczegółowe informacje dotyczące dodawania operacji do niezgodności i stosowania za nią opłat, zobacz temat [Operacje dotyczące niezgodności](quality-operations.md).</span><span class="sxs-lookup"><span data-stu-id="827d3-125">For details about how to add operations to a nonconformance and apply charges to them, see [Operations for nonconformances](quality-operations.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="827d3-126">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="827d3-126">Additional resources</span></span>

- [<span data-ttu-id="827d3-127">Omówienie zarządzanie jakością</span><span class="sxs-lookup"><span data-stu-id="827d3-127">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="827d3-128">Włączanie zarządzania kontrolą jakości i niezgodnością</span><span class="sxs-lookup"><span data-stu-id="827d3-128">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="827d3-129">Pracownicy odpowiedzialni za zatwierdzanie niezgodności</span><span class="sxs-lookup"><span data-stu-id="827d3-129">Workers responsible for approving nonconformances</span></span>](quality-responsible-workers.md)
- [<span data-ttu-id="827d3-130">Strefy kwarantanny niezgodności</span><span class="sxs-lookup"><span data-stu-id="827d3-130">Quarantine zones for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="827d3-131">Typy diagnostyki niezgodności</span><span class="sxs-lookup"><span data-stu-id="827d3-131">Diagnostic types for nonconformances</span></span>](quality-diagnostic-types.md)
- [<span data-ttu-id="827d3-132">Opłaty związane z kontrolą jakości dla niezgodności</span><span class="sxs-lookup"><span data-stu-id="827d3-132">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="827d3-133">Operacje dotyczące niezgodności</span><span class="sxs-lookup"><span data-stu-id="827d3-133">Operations for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="827d3-134">Zarządzanie jakością dla procesów magazynowych</span><span class="sxs-lookup"><span data-stu-id="827d3-134">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
