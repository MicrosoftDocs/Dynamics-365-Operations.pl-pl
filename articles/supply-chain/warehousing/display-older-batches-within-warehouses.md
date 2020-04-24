---
title: Konfigurowanie wyświetlania starszych partii w magazynie na urządzeniu przenośnym
description: W tym temacie opisano sposób konfigurowania urządzenia przenośnego do wyświetlania listy lokalizacji z partiami starszymi niż partie w bieżącej lokalizacji w wierszu pracy.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5b1c9452a811d662976a25993264be0617ac67fe
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3205651"
---
# <a name="configure-display-older-batches-within-warehouse-on-a-mobile-device"></a><span data-ttu-id="ee94d-103">Konfigurowanie wyświetlania starszych partii w magazynie na urządzeniu przenośnym</span><span class="sxs-lookup"><span data-stu-id="ee94d-103">Configure Display older batches within warehouse on a mobile device</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ee94d-104">Ustawienie **Wyświetl starsze partie w magazynie** pozwala wyświetlić listę lokalizacji zawierających partie starsze niż partie w bieżącej lokalizacji w wierszu pracy.</span><span class="sxs-lookup"><span data-stu-id="ee94d-104">The **Display older batches within warehouse** configuration lets you display a list of locations with batches older than the current location of the work line.</span></span> <span data-ttu-id="ee94d-105">Wyświetlona lista lokalizacji zawiera informacje o starszych partiach w lokalizacji z datami ważności oraz fizycznie zapasy każdej partii.</span><span class="sxs-lookup"><span data-stu-id="ee94d-105">The list of locations that are displayed includes information about the older batches in the location with the expiration date and the physical inventory of each batch.</span></span> <span data-ttu-id="ee94d-106">Można wybrać pobieranie z nowej lokalizacji albo kontynuować pobieranie z bieżącej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="ee94d-106">You can choose to pick from a new location or to continue picking from the current location.</span></span> 
- <span data-ttu-id="ee94d-107">Pobieranie z nowej lokalizacji — Po zaznaczeniu nowej lokalizacji, z której ma być wykonywane pobieranie, bieżący wiersz pracy zostanie zaktualizowany, tak aby używał nowej lokalizacji, a praca będzie kontynuowana w zwykły sposób, ale przy użyciu nowej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="ee94d-107">Pick from a new location - If you select a new location to pick from, the  current work line will be updated to use the new location and work will continue as usual with the new location.</span></span> <span data-ttu-id="ee94d-108">Aby nowa lokalizacja działała, musi mieć dostępną ilość wystarczającą dla całego wiersza pracy.</span><span class="sxs-lookup"><span data-stu-id="ee94d-108">For the new location to be valid, it must have enough available quantity for the whole work line.</span></span> <span data-ttu-id="ee94d-109">Jeśli wymagana ilość nie jest dostępna, wiersz pracy nie zostanie zaktualizowany i pojawi się lista.</span><span class="sxs-lookup"><span data-stu-id="ee94d-109">If the required quantity is not available, the work line will not be updated, and the list will display.</span></span> 
- <span data-ttu-id="ee94d-110">Kontynuowanie pobierania z bieżącej lokalizacji — W przypadku dalszego używania bieżącej lokalizacji wiersza pracy ilości dla wiersza pracy będą w dalszym ciągu pobierane z oryginalnej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="ee94d-110">Continue picking from the current location - If you continue with the current work line location, the quantities for the work line will continue to be picked from the original location.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="ee94d-111">Zastosowanie</span><span class="sxs-lookup"><span data-stu-id="ee94d-111">Where it applies</span></span>
<span data-ttu-id="ee94d-112">Funkcjonalność wyświetlania starszych partii w magazynie jest konfigurowana w menu urządzenia przenośnego i wpływa na pobieranie towarów w partiach poniżej.</span><span class="sxs-lookup"><span data-stu-id="ee94d-112">Display older batches within warehouse is configured on mobile device menu items and affects the pick for batch below items.</span></span>

## <a name="set-up-display-older-batches-within-warehouse"></a><span data-ttu-id="ee94d-113">Konfigurowanie wyświetlania starszych partii w magazynie</span><span class="sxs-lookup"><span data-stu-id="ee94d-113">Set up Display older batches within warehouse</span></span>
<span data-ttu-id="ee94d-114">Ustawienie **Wyświetl starsze partie w magazynie** jest dostępne w elementach menu urządzenia przenośnego, gdy w opcji **Pobierz z najstarszej partii** ustawiono wartość **Ostrzegaj**.</span><span class="sxs-lookup"><span data-stu-id="ee94d-114">The **Display older batches within warehouse** configuration is available on mobile device menu items when the **Pick oldest batch** option is set to **Warn**.</span></span>

- <span data-ttu-id="ee94d-115">W oknie **Zarządzanie magazynem** > **Ustawienia** > **Urządzenie przenośne** > **Elementy menu urządzenia przenośnego** w opcji **Użyj istniejącej pracy** ustaw wartość **Tak**, a następnie w polu **Pobierz z najstarszej partii** ustaw wartość **Ostrzegaj**.</span><span class="sxs-lookup"><span data-stu-id="ee94d-115">Under **Warehouse management** > **Setup** > **Mobile device** > **Mobile device menu items**, set **Use existing work** to **Yes** for the menu item, and select **Warn** in the **Pick oldest batch** field.</span></span> 

