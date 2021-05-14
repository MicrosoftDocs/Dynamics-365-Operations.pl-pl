---
title: Pracownicy odpowiedzialni za zatwierdzanie niezgodności
description: W tym temacie opisano sposób konfigurowania pracowników odpowiedzialnych za zatwierdzanie niezgodności.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5979cb33146a00c3ea49ada9577140b24c07928f
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956792"
---
# <a name="workers-responsible-for-approving-nonconformances"></a><span data-ttu-id="ecf0e-103">Pracownicy odpowiedzialni za zatwierdzanie niezgodności</span><span class="sxs-lookup"><span data-stu-id="ecf0e-103">Workers responsible for approving nonconformances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ecf0e-104">W tym temacie opisano sposób konfigurowania pracowników odpowiedzialnych za zatwierdzanie niezgodności.</span><span class="sxs-lookup"><span data-stu-id="ecf0e-104">This topic describes how to configure workers that are responsible for approving nonconformances.</span></span>

<span data-ttu-id="ecf0e-105">Niezgodności muszą zostać zatwierdzone, zanim użytkownicy będą zaczynali wprowadzać szczegóły, takie jak korekty lub operacje.</span><span class="sxs-lookup"><span data-stu-id="ecf0e-105">Nonconformances must be approved before users can start to enter details such as corrections or operations.</span></span> <span data-ttu-id="ecf0e-106">Zanim użytkownicy będą mieć możliwość zatwierdzania lub odrzucania niezgodności, ich identyfikator użytkownika (rekord użytkownika) musi być połączony z rekordem pracownika.</span><span class="sxs-lookup"><span data-stu-id="ecf0e-106">Before users can approve or reject nonconformances, their user ID (user record) must be linked to a worker record.</span></span> <span data-ttu-id="ecf0e-107">Opcjonalnie można skonfigurować pracowników odpowiedzialnych za jakość, a następnie zezwolić jednemu pracownikowi na zatwierdzanie pracy w imieniu innego pracownika.</span><span class="sxs-lookup"><span data-stu-id="ecf0e-107">You can optionally configure workers that are responsible for quality and then allow one worker to approve work on behalf of another worker.</span></span>

## <a name="enable-a-user-for-nonconformance-processing"></a><span data-ttu-id="ecf0e-108">Włączanie użytkownika dla przetwarzania niezgodności</span><span class="sxs-lookup"><span data-stu-id="ecf0e-108">Enable a user for nonconformance processing</span></span>

<span data-ttu-id="ecf0e-109">Zanim użytkownik będzie mieć możliwość zatwierdzania lub odrzucania niezgodności, musisz połączyć rekord użytkownika z rekordem pracownika.</span><span class="sxs-lookup"><span data-stu-id="ecf0e-109">Before a user can approve or reject nonconformances, you must link their user record to a worker record.</span></span> <span data-ttu-id="ecf0e-110">Pola zatwierdzania mogą być następnie ustawiane automatycznie, a bieżący użytkownik może zostać automatycznie wstawiony na potrzeby karty czasu pracy.</span><span class="sxs-lookup"><span data-stu-id="ecf0e-110">The approval fields can then be automatically set, and the current user can be automatically filled in for the timesheet.</span></span> <span data-ttu-id="ecf0e-111">Aby użytkownik mógł korzystać z notatek do dokumentu, musisz uaktywnić obsługę dokumentów w jego opcjach użytkownika.</span><span class="sxs-lookup"><span data-stu-id="ecf0e-111">Before the user can use the document notes, you must activate document handling in their user options.</span></span>

1. <span data-ttu-id="ecf0e-112">Wybierz kolejno opcje **Administrowanie systemem \> Użytkownicy \> Użytkownicy**.</span><span class="sxs-lookup"><span data-stu-id="ecf0e-112">Go to **System administration \> Users \> Users**.</span></span>
1. <span data-ttu-id="ecf0e-113">Znajdź i otwórz użytkownika, który powinien mieć możliwość zatwierdzania lub odrzucania niezgodności.</span><span class="sxs-lookup"><span data-stu-id="ecf0e-113">Find and open the user who should be able to approve or reject nonconformances.</span></span>
1. <span data-ttu-id="ecf0e-114">Ustaw w polu **Osoba** nazwisko pracownika, które jest powiązane z bieżącym rekordem użytkownika.</span><span class="sxs-lookup"><span data-stu-id="ecf0e-114">Set the **Person** field to the name of the worker that is related to the current user record.</span></span>
1. <span data-ttu-id="ecf0e-115">W Okienku akcji wybierz **Opcje użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="ecf0e-115">On the Action Pane, select **User options**.</span></span>
1. <span data-ttu-id="ecf0e-116">Na stronie **Opcje** dla bieżącego rekordu użytkownika na karcie **Preferencje** ustaw opcję **Włącz obsługę dokumentów** na wartość *Tak*.</span><span class="sxs-lookup"><span data-stu-id="ecf0e-116">On the **Options** page for the current user record, on the **Preferences** tab, set the **Enable document handling** option to *Yes*.</span></span>
1. <span data-ttu-id="ecf0e-117">Zamknij strony.</span><span class="sxs-lookup"><span data-stu-id="ecf0e-117">Close the pages.</span></span>

## <a name="define-workers-that-are-responsible-for-quality"></a><span data-ttu-id="ecf0e-118">Definiowanie pracowników odpowiedzialnych za jakość</span><span class="sxs-lookup"><span data-stu-id="ecf0e-118">Define workers that are responsible for quality</span></span>

1. <span data-ttu-id="ecf0e-119">Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Kontrola jakości \> Pracownicy odpowiedzialni za jakość**.</span><span class="sxs-lookup"><span data-stu-id="ecf0e-119">Go to **Inventory management \> Setup \> Quality control \> Workers responsible for quality**.</span></span>
2. <span data-ttu-id="ecf0e-120">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="ecf0e-120">On the Action Pane, select **New**.</span></span>
3. <span data-ttu-id="ecf0e-121">W polu **Pracownik** wybierz pracownika, który wprowadza dane jakości.</span><span class="sxs-lookup"><span data-stu-id="ecf0e-121">In the **Worker** field, select the worker that enters quality data.</span></span>
4. <span data-ttu-id="ecf0e-122">W polu **Pracownik odpowiedzialny** wybierz pracownika, w którego imieniu wybrany pracownik wprowadza pracę.</span><span class="sxs-lookup"><span data-stu-id="ecf0e-122">In the **Worker responsible** field, select the worker that the selected worker enters work on behalf of.</span></span> <span data-ttu-id="ecf0e-123">Po utworzeniu i zaktualizowaniu niezgodności ten pracownik będzie domyślnie wstawiany w polach **Pracownik**.</span><span class="sxs-lookup"><span data-stu-id="ecf0e-123">When nonconformances are created and updated, this worker will be entered by default in **Worker** fields.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ecf0e-124">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="ecf0e-124">Additional resources</span></span>

- [<span data-ttu-id="ecf0e-125">Omówienie zarządzanie jakością</span><span class="sxs-lookup"><span data-stu-id="ecf0e-125">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="ecf0e-126">Włączanie zarządzania kontrolą jakości i niezgodnością</span><span class="sxs-lookup"><span data-stu-id="ecf0e-126">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="ecf0e-127">Opłaty związane z kontrolą jakości</span><span class="sxs-lookup"><span data-stu-id="ecf0e-127">Quality charges</span></span>](quality-charges.md)
- [<span data-ttu-id="ecf0e-128">Strefy kwarantanny niezgodności</span><span class="sxs-lookup"><span data-stu-id="ecf0e-128">Quarantine zones for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="ecf0e-129">Typy diagnostyki niezgodności</span><span class="sxs-lookup"><span data-stu-id="ecf0e-129">Diagnostic types for nonconformances</span></span>](quality-diagnostic-types.md)
- [<span data-ttu-id="ecf0e-130">Opłaty związane z kontrolą jakości dla niezgodności</span><span class="sxs-lookup"><span data-stu-id="ecf0e-130">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="ecf0e-131">Operacje dotyczące niezgodności</span><span class="sxs-lookup"><span data-stu-id="ecf0e-131">Operations for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="ecf0e-132">Zarządzanie jakością dla procesów magazynowych</span><span class="sxs-lookup"><span data-stu-id="ecf0e-132">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
