---
title: "Pobieranie najstarszej partii na urządzeniu przenośnym"
description: "W tym temacie opisano sposób konfigurowania i stosowania opcji pobierania najstarszej partii z urządzenia przenośnego."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 25056886b1a18dbaef12c8732a1fd0bd92a6d04b
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="pick-oldest-batch-on-a-mobile-device"></a><span data-ttu-id="2ac5a-103">Pobieranie najstarszej partii na urządzeniu przenośnym</span><span class="sxs-lookup"><span data-stu-id="2ac5a-103">Pick oldest batch on a mobile device</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="2ac5a-104">Dostęp do konfiguracji **Pobierz z najstarszej partii** można uzyskać z menu urządzenia przenośnego, a następnie ustawić w niej wymuszanie lub ostrzeganie pracowników magazynu, aby pobierali najstarszą partia w swojej obecnej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="2ac5a-104">You can access the configuration **Pick oldest batch** via a mobile device menu and it allows you to force or warn warehouse workers to pick the oldest batch in their current location.</span></span>  

## <a name="where-it-applies"></a><span data-ttu-id="2ac5a-105">Zastosowanie</span><span class="sxs-lookup"><span data-stu-id="2ac5a-105">Where it applies</span></span>
<span data-ttu-id="2ac5a-106">Funkcjonalność pobierania najstarszej partii jest konfigurowana w menu urządzenia przenośnego i wpływa na pobieranie towarów w partiach poniżej.</span><span class="sxs-lookup"><span data-stu-id="2ac5a-106">Pick oldest batch is configured on mobile device menu items and effects the pick for batch below items.</span></span>

## <a name="how-to-set-up-the-configuration-for-pick-oldest-batch"></a><span data-ttu-id="2ac5a-107">Konfigurowanie pobierania najstarszej partii</span><span class="sxs-lookup"><span data-stu-id="2ac5a-107">How to set up the configuration for Pick oldest batch</span></span> 
<span data-ttu-id="2ac5a-108">Dla towarów skonfigurowanych do wykorzystywania istniejącej pracy w opcji **Pobierz z najstarszej partii** na urządzeniu komórkowym można ustawić wartość **Brak**, **Ostrzegaj** lub **Wymuszaj**.</span><span class="sxs-lookup"><span data-stu-id="2ac5a-108">For items that are set to use existing work, **Pick oldest batch** can be set to **None**, **Warn**, or **Force** from a mobile device menu.</span></span>

<span data-ttu-id="2ac5a-109">**Brak**: Pracownicy nie będą dostawać żadnych komunikatów i mogą pobierać dowolne partie w swoich lokalizacjach.</span><span class="sxs-lookup"><span data-stu-id="2ac5a-109">**None**: Workers will not receive any messages and they will be allowed to pick any batch in their location.</span></span>

<span data-ttu-id="2ac5a-110">**Ostrzegaj** i **Wymuszaj**: Gdy pracownik zaznaczy partię, nad formantem partii będzie wyświetlana lista partii z najstarszymi datami ważności.</span><span class="sxs-lookup"><span data-stu-id="2ac5a-110">**Warn** and **Force**:  A list of the batch(es) with the oldest expiration date will be displayed above the batch control when the worker selects a batch.</span></span> <span data-ttu-id="2ac5a-111">Jeśli lokalizacja jest kontrolowana przez numer identyfikacyjny, nad formantem numeru identyfikacyjnego zostanie wyświetlona lista numerów identyfikacyjnych z najstarszymi partiami.</span><span class="sxs-lookup"><span data-stu-id="2ac5a-111">If the location is license plate controlled, a list of license plates that have the oldest batch will be displayed above the license plate control.</span></span> 
-   <span data-ttu-id="2ac5a-112">**Ostrzeganie**: Jeśli pracownik wybierze numer identyfikacyjny lub partię, która nie znajduje się na wyświetlanej liście, formant będzie wygaszony i pojawi się ostrzeżenie, że istnieje starsza partia do wybrania.</span><span class="sxs-lookup"><span data-stu-id="2ac5a-112">**Warn**: If a worker chooses a license plate or batch that is not on the shown list, the control will be blanked and a warning will be shown that there is an older batch to select.</span></span> <span data-ttu-id="2ac5a-113">Aby móc kontynuować pracę, pracownik może ponownie wybrać ten sam numer identyfikacyjny lub partię.</span><span class="sxs-lookup"><span data-stu-id="2ac5a-113">To be allowed to continue the work, the worker can select the same license plate or batch again.</span></span>  
-   <span data-ttu-id="2ac5a-114">**Wymuszaj**: Pracownicy będą cały czas otrzymywać komunikat, że istnieje starsza partia do pobrania.</span><span class="sxs-lookup"><span data-stu-id="2ac5a-114">**Force**: Workers will continue to receive the message that there is an older batch to pick.</span></span>

