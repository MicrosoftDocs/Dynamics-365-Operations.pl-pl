---
title: Potwierdzenie partii i numeru identyfikacyjnego
description: W tym temacie opisano sposób konfigurowania i stosowania funkcjonalności potwierdzania partii i numeru identyfikacyjnego z urządzenia przenośnego.
author: Mirzaab
manager: tfehr
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFAutoConfirm
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 97790b91d4de536b89b580c26ef1e37145f7d7c6
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977445"
---
# <a name="batch-and-license-plate-confirmation"></a><span data-ttu-id="2d6db-103">Potwierdzenie partii i numeru identyfikacyjnego</span><span class="sxs-lookup"><span data-stu-id="2d6db-103">Batch and license plate confirmation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2d6db-104">Funkcja potwierdzania partii umożliwia potwierdzenie, że na urządzeniu komórkowym jest wybierana poprawna partia.</span><span class="sxs-lookup"><span data-stu-id="2d6db-104">Batch confirmation allows you to confirm that the correct batch is being picked from the mobile device.</span></span> <span data-ttu-id="2d6db-105">W początkowym pobraniu pracy tylko dla towarów w partii powyżej, gdzie określenie partia powyżej wskazuje, że zakres partii sięga wyżej niż lokalizacja w hierarchii wyszukiwania, należy sprawdzić, czy pobierana partia jest taka sama, jak partia w wierszu pracy.</span><span class="sxs-lookup"><span data-stu-id="2d6db-105">On the initial pick of work for batch above-items only, where batch above indicates that batch ranges higher than location in the search hierarchy, you must verify that the batch that is picked matches the batch on the work line.</span></span>

<span data-ttu-id="2d6db-106">Funkcja potwierdzania numeru seryjnego umożliwia potwierdzenie, że na urządzeniu komórkowym jest wybierany poprawny numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="2d6db-106">License plate confirmation allows you to confirm that the correct license plate is being picked from the mobile device.</span></span> <span data-ttu-id="2d6db-107">Podczas pobierania pracy z lokalizacji pośredniej należy sprawdzić, czy pobierany numer identyfikacyjny jest taki sam, jak numer identyfikacyjny skojarzony z pracą.</span><span class="sxs-lookup"><span data-stu-id="2d6db-107">When picking work from a stage location, you must verify that the license plate that is picked matches the license plate that is associated with the work.</span></span> <span data-ttu-id="2d6db-108">Jeśli praca rozpoczyna się od zeskanowania numeru identyfikacyjnego, ten krok potwierdzania zostanie pominięty.</span><span class="sxs-lookup"><span data-stu-id="2d6db-108">If the work is started by scanning a license plate, this confirmation step will be skipped.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="2d6db-109">Zastosowanie</span><span class="sxs-lookup"><span data-stu-id="2d6db-109">Where it applies</span></span>

<span data-ttu-id="2d6db-110">Potwierdzanie stosuje się w następujących sytuacjach:</span><span class="sxs-lookup"><span data-stu-id="2d6db-110">Confirmation applies in the following scenarios:</span></span>

- <span data-ttu-id="2d6db-111">Potwierdzanie partii stosuje się do pierwotnych pobrań pracy dla towarów w partiach powyżej.</span><span class="sxs-lookup"><span data-stu-id="2d6db-111">Batch confirmation applies to the initial picks of work for batch above-items.</span></span>
- <span data-ttu-id="2d6db-112">Potwierdzanie numeru identyfikacyjnego stosuje się do pobrań z lokalizacji pośrednich.</span><span class="sxs-lookup"><span data-stu-id="2d6db-112">License plate confirmation applies to picks from stage locations.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2d6db-113">Uzupełnienie zapasów nie jest obsługiwane dla potwierdzenia numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="2d6db-113">Replenishment is not supported for license plate confirmation.</span></span> <span data-ttu-id="2d6db-114">W przypadku wykonywania pracy uzupełniania zapasów nie jest tworzony etap potwierdzenia numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="2d6db-114">When executing replenishment work, no license plate confirmation step is created.</span></span>

## <a name="set-up-batch-and-license-plate-confirmation"></a><span data-ttu-id="2d6db-115">Konfigurowanie potwierdzanie partii i numeru identyfikacyjnego</span><span class="sxs-lookup"><span data-stu-id="2d6db-115">Set up batch and license plate confirmation</span></span>

<span data-ttu-id="2d6db-116">Funkcjonalność potwierdzania partii i numeru identyfikacyjnego można skonfigurować z menu urządzenia komórkowego.</span><span class="sxs-lookup"><span data-stu-id="2d6db-116">You can configure batch and license plate confirmation from the mobile device menu items.</span></span>

1. <span data-ttu-id="2d6db-117">Na urządzeniu przenośnym w menu przejdź do pozycji Konfiguracja potwierdzenia pracy.</span><span class="sxs-lookup"><span data-stu-id="2d6db-117">From the mobile device menu items, enter the work confirmation setup.</span></span>  
1. <span data-ttu-id="2d6db-118">Wybierz opcję potwierdzania partii lub numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="2d6db-118">Select the option for either batch or license plate confirmation.</span></span> <span data-ttu-id="2d6db-119">Obie opcje są dostępne dla pobrań typów pracy, w których nie włączono opcji automatycznego potwierdzania.</span><span class="sxs-lookup"><span data-stu-id="2d6db-119">Both options are available for work type picks that do not have automatic confirmation enabled.</span></span>  
