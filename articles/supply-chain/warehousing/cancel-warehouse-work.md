---
title: Anulowanie pracy magazynowej na potrzeby obsługi wyjątków
description: W tym temacie opisano funkcję anulowania pracy, która pozwala kierownikom magazynu na obsługę zablokowanej pracy.
author: omulvad
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSTroubIeshootingSeIfService, WHSTroubleshootingSelfService
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2019-10-1
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ae4062401cd5be2371c45642b78bf3708b04f664
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001205"
---
# <a name="cancel-warehouse-work-for-exception-handling"></a><span data-ttu-id="03731-103">Anulowanie pracy magazynowej na potrzeby obsługi wyjątków</span><span class="sxs-lookup"><span data-stu-id="03731-103">Cancel warehouse work for exception handling</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="03731-104">Funkcja anulowania pracy w rozwiązaniu Microsoft Dynamics 365 Supply Chain Management umożliwia administratorowi anulowanie konkretnej pracy magazynowej, która jest obecnie w toku, ale która została zablokowana przez system lub nie może zostać zakończona z powodu wyjątkowych okoliczności.</span><span class="sxs-lookup"><span data-stu-id="03731-104">The Cancel work functionality in Microsoft Dynamics 365 Supply Chain Management lets the admin user cancel specific warehouse work that is currently in progress, but that is blocked by the system or can't be completed because of exceptional circumstances.</span></span> <span data-ttu-id="03731-105">Ta funkcja to atrakcyjna i bezpieczna alternatywa dla skryptów korygujących SQL, które rozwiązują problemy z niespójnymi danymi.</span><span class="sxs-lookup"><span data-stu-id="03731-105">This functionality is an attractive and secure alternative to SQL corrective scripts that fix inconsistent data.</span></span> <span data-ttu-id="03731-106">Do obsługi tych skryptów są jednak zazwyczaj niezbędni informatycy, a funkcja anulowania pracy może być używana w firmie przez użytkowników z uprawnieniami administratora.</span><span class="sxs-lookup"><span data-stu-id="03731-106">However, whereas these scripts are typically requested from IT professionals, the Cancel work functionality can be used by users in the company who have admin rights.</span></span>

<span data-ttu-id="03731-107">Aby uzyskać dostęp do funkcji anulowania pracy, możesz przejść do obszaru **Zarządzanie magazynem** \> **Zadania okresowe** \> **Oczyszczanie \> Anuluj pracę**.</span><span class="sxs-lookup"><span data-stu-id="03731-107">You can access the Cancel work functionality at **Warehouse management** \> **Periodic tasks** \> **Clean up \> Cancel work**.</span></span> <span data-ttu-id="03731-108">W oknie dialogowym **Anulowanie pracy** określ identyfikator pracy do anulowania, a następnie wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="03731-108">In the **Cancel work** dialog box, specify the work ID of the work to cancel, and then select **OK**.</span></span>

## <a name="warehouse-work-that-can-be-canceled"></a><span data-ttu-id="03731-109">Praca magazynowa, którą można anulować</span><span class="sxs-lookup"><span data-stu-id="03731-109">Warehouse work that can be canceled</span></span>

<span data-ttu-id="03731-110">Podczas operacji pobrania z magazynu pracownik może napotkać sytuacje, w których ilości zostały zarejestrowane jako pobrane z lokalizacji magazynu do lokalizacji użytkownika, ale nie można zarejestrować operacji odłożenia.</span><span class="sxs-lookup"><span data-stu-id="03731-110">During warehouse picking operations, a worker might encounter situations where they have registered quantities as picked from a storage location to their user location, but then they can't register the put operation.</span></span> <span data-ttu-id="03731-111">Niespójne dane magazynu są często, ale nie zawsze, przyczyną zablokowania pracy.</span><span class="sxs-lookup"><span data-stu-id="03731-111">Inconsistent warehouse data is often, but not always, the reason why work is blocked.</span></span>

<span data-ttu-id="03731-112">W odróżnieniu od zwykłej funkcji anulowania, z której można skorzystać za pomocą przycisku **Anuluj** w nagłówku pracy, funkcja anulowania pracy nie wymaga, aby ostatni zakończony wiersz pracy miał typem pracy **Odłożenie**.</span><span class="sxs-lookup"><span data-stu-id="03731-112">Unlike the regular Cancel functionality that can be accessed by using the **Cancel** button on the work header, the Cancel work functionality doesn't require that the last completed work line be a work line of the **put** type.</span></span> <span data-ttu-id="03731-113">Mówiąc inaczej, w przypadku funkcji anulowania pracy można uruchomić logikę anulowania, nawet jeśli ilość pozycji w wierszu pracy znajduje się w lokalizacji użytkownika.</span><span class="sxs-lookup"><span data-stu-id="03731-113">In other words, for the Cancel work functionality, cancellation logic can be run even if the item quantity on a work line is in a user location.</span></span>

> [!NOTE]
> <span data-ttu-id="03731-114">W przypadku pracy, którą trzeba anulować z przyczyn operacyjnych, użytkownicy magazynu muszą nadal korzystać ze zwykłej funkcji anulowania na stronie pracy.</span><span class="sxs-lookup"><span data-stu-id="03731-114">For work that must be canceled for operational reasons, warehouse users must continue to use the regular Cancel functionality on the work page.</span></span>

<span data-ttu-id="03731-115">Za pomocą funkcji anulowania pracy można anulować tylko pracę następującego typu: **Sprzedaż**, **Wydanie przeniesienia**, **Pobranie zapasów** lub **Uzupełnianie zapasów**.</span><span class="sxs-lookup"><span data-stu-id="03731-115">Only work of the **Sales**, **Transfer issue**, **Raw material picking**, or **Replenishment** type can be canceled by using the Cancel work functionality.</span></span> <span data-ttu-id="03731-116">Logika anulowania nie zostanie uruchomiona dla zamrożonej pracy pobrania surowca lub pracy, którą można anulować za pomocą zwykłej funkcji anulowania (zobacz poprzednią notatkę).</span><span class="sxs-lookup"><span data-stu-id="03731-116">Cancellation logic won't be run for frozen raw material picking work or work that can be canceled by using the regular Cancel functionality (see the preceding note).</span></span>

<span data-ttu-id="03731-117">Aby odblokować pracę, system anuluje wszystkie pozostałe wiersze pracy i naprawia dane magazynu skojarzone z określonym przez użytkownika identyfikatorem pracy.</span><span class="sxs-lookup"><span data-stu-id="03731-117">To unblock the work, the system cancels any remaining work lines and fixes the warehouse data that is associated with the work ID that the user specified.</span></span> <span data-ttu-id="03731-118">Następnie można wznowić wszystkie zwykłe operacje obsługi magazynu, które obejmują uwzględnioną ilość pozycji.</span><span class="sxs-lookup"><span data-stu-id="03731-118">Any regular warehouse-handling operations that involve the affected item quantity can then resume.</span></span>

<span data-ttu-id="03731-119">Aby umieścić uwzględnioną pozycję w określonej lokalizacji po anulowaniu pracy, użytkownik musi skorzystać z operacji przeniesienia zapasów lub korekty ilości na urządzeniu przenośnym.</span><span class="sxs-lookup"><span data-stu-id="03731-119">To put the affected item in a specific location after the work is canceled, the user must use an inventory movement or quantity adjustment operation on a mobile device.</span></span>
