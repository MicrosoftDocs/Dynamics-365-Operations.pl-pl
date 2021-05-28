---
title: Typy diagnostyki niezgodności
description: W tym temacie opisano sposób tworzenia i używania typów diagnostyki, które mogą być używane z niezgodnościami.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestDiagnosticType, InventTestCorrection
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b7a5c593f1d9e8f7a77f693f6e652e9355a985fb
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022283"
---
# <a name="diagnostic-types-for-nonconformances"></a><span data-ttu-id="f5262-103">Typy diagnostyki niezgodności</span><span class="sxs-lookup"><span data-stu-id="f5262-103">Diagnostic types for nonconformances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f5262-104">W tym temacie opisano sposób tworzenia i używania typów diagnostyki, które mogą być używane z niezgodnościami.</span><span class="sxs-lookup"><span data-stu-id="f5262-104">This topic describes how to use and create diagnostic types that can be used with nonconformances.</span></span>

<span data-ttu-id="f5262-105">Strona **Typy diagnostyki** służy do definiowania klasyfikacji akcji diagnostycznych.</span><span class="sxs-lookup"><span data-stu-id="f5262-105">You use the **Diagnostic types** page to define a classification of diagnostic actions.</span></span> <span data-ttu-id="f5262-106">Następnie podczas tworzenia korekty niezgodności należy wybrać diagnostykę.</span><span class="sxs-lookup"><span data-stu-id="f5262-106">Then, when you create a correction for a nonconformance, you select a diagnostic.</span></span> <span data-ttu-id="f5262-107">Korekta określa jakiego rodzaju działania diagnostyczne należy podjąć w przypadku zatwierdzonej niezgodności, a także osobę, która ma to działanie wykonać.</span><span class="sxs-lookup"><span data-stu-id="f5262-107">A correction specifies what type of diagnostic action should be taken for an approved nonconformance, and who should take that action.</span></span> <span data-ttu-id="f5262-108">Określa również żądaną datę ukończenia żądania planowaną datę ukończenia.</span><span class="sxs-lookup"><span data-stu-id="f5262-108">It also specifies the requested completion date and the planned completion date.</span></span>

## <a name="examples-of-diagnostic-types"></a><span data-ttu-id="f5262-109">Przykłady typów diagnostyki</span><span class="sxs-lookup"><span data-stu-id="f5262-109">Examples of diagnostic types</span></span>

<span data-ttu-id="f5262-110">Pracujesz w firmie produkcyjnej i masz towary, które nie przeszły testów kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="f5262-110">You work for a manufacturing company, and several items have failed quality tests.</span></span> <span data-ttu-id="f5262-111">Towary te są przenoszone do obszaru kwarantanny i oznaczane jako produkty niezgodności.</span><span class="sxs-lookup"><span data-stu-id="f5262-111">Those items are moved into a quarantine area and marked as nonconforming products.</span></span> <span data-ttu-id="f5262-112">Rekord niezgodności jest tworzony w systemie Microsoft Dynamics 365 Supply Chain Management w celu śledzenia szczegółów do rozwiązania problemu.</span><span class="sxs-lookup"><span data-stu-id="f5262-112">A nonconformance record is created in Microsoft Dynamics 365 Supply Chain Management to track the details through issue resolution.</span></span>

<span data-ttu-id="f5262-113">W tym przypadku problemy z jakością są spowodowane zatarciem i przegrzaniem łożysk w maszynie pakującej towary.</span><span class="sxs-lookup"><span data-stu-id="f5262-113">In this case, the quality issues are occurring because bearings in the machine that packages the items have gone bad and are overheating.</span></span> <span data-ttu-id="f5262-114">Korekta tego problemu polega na wymianie części w maszynie.</span><span class="sxs-lookup"><span data-stu-id="f5262-114">The correction for this problem is to replace the parts in the machine.</span></span>

<span data-ttu-id="f5262-115">Podczas konfigurowania typów diagnostyki można utworzyć wiele rekordów, z których każdy reprezentuje inny typ problemu, jaki może wystąpić w maszynie.</span><span class="sxs-lookup"><span data-stu-id="f5262-115">When you configure the diagnostic types, you can create multiple records, each of which represents a different type of problem that the machine might have.</span></span> <span data-ttu-id="f5262-116">Można również utworzyć jeden ogólny typ diagnostyki, który reprezentuje naprawę maszyny.</span><span class="sxs-lookup"><span data-stu-id="f5262-116">Alternatively, you can create one generic diagnostic type that represents machine repair.</span></span>

## <a name="create-a-diagnostic-type"></a><span data-ttu-id="f5262-117">Tworzenie typu diagnostyki</span><span class="sxs-lookup"><span data-stu-id="f5262-117">Create a diagnostic type</span></span>

1. <span data-ttu-id="f5262-118">Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Zarządzanie jakością \> Typy diagnostyki**.</span><span class="sxs-lookup"><span data-stu-id="f5262-118">Go to **Inventory management \> Setup \> Quality management \> Diagnostic types**.</span></span>
1. <span data-ttu-id="f5262-119">W okienku akcji wybierz opcję **Nowy**, aby dodać nowy wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="f5262-119">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="f5262-120">Następnie ustaw następujące pola dla nowego wiersza:</span><span class="sxs-lookup"><span data-stu-id="f5262-120">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="f5262-121">**Diagnostyka** — służy do wprowadzania unikatowego identyfikatora lub nazwy typu diagnostyki.</span><span class="sxs-lookup"><span data-stu-id="f5262-121">**Diagnostic** – Enter a unique ID or name for the diagnostic type.</span></span>
    - <span data-ttu-id="f5262-122">**Opis** – wprowadź szczegółowy opis typu diagnostyki.</span><span class="sxs-lookup"><span data-stu-id="f5262-122">**Description** – Enter a detailed description of the diagnostic type.</span></span>

1. <span data-ttu-id="f5262-123">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f5262-123">Close the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f5262-124">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="f5262-124">Additional resources</span></span>

- [<span data-ttu-id="f5262-125">Omówienie zarządzanie jakością</span><span class="sxs-lookup"><span data-stu-id="f5262-125">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="f5262-126">Włączanie zarządzania kontrolą jakości i niezgodnością</span><span class="sxs-lookup"><span data-stu-id="f5262-126">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="f5262-127">Pracownicy odpowiedzialni za zatwierdzanie niezgodności</span><span class="sxs-lookup"><span data-stu-id="f5262-127">Workers responsible for approving nonconformances</span></span>](quality-responsible-workers.md)
- [<span data-ttu-id="f5262-128">Strefy kwarantanny niezgodności</span><span class="sxs-lookup"><span data-stu-id="f5262-128">Quarantine zones for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="f5262-129">Typy problemów w niezgodnościach</span><span class="sxs-lookup"><span data-stu-id="f5262-129">Problem types for nonconformances</span></span>](quality-problem-types.md)
- [<span data-ttu-id="f5262-130">Opłaty związane z kontrolą jakości dla niezgodności</span><span class="sxs-lookup"><span data-stu-id="f5262-130">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="f5262-131">Operacje dotyczące niezgodności</span><span class="sxs-lookup"><span data-stu-id="f5262-131">Operations for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="f5262-132">Zarządzanie jakością dla procesów magazynowych</span><span class="sxs-lookup"><span data-stu-id="f5262-132">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
