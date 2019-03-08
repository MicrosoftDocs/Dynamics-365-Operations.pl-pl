---
title: Ustawianie grup środków trwałych
description: W tej procedurze pokazano sposób tworzenia nowej grupy środków trwałych.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetGroup, AssetGroupBookSetup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 48784ef4eb12a4a1cae3387e3a45afdf34f2a0fd
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "321807"
---
# <a name="set-up-fixed-asset-groups"></a><span data-ttu-id="0e402-103">Ustawianie grup środków trwałych</span><span class="sxs-lookup"><span data-stu-id="0e402-103">Set up fixed asset groups</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0e402-104">W tej procedurze pokazano sposób tworzenia nowej grupy środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="0e402-104">This procedure shows how to create a new fixed asset group.</span></span> <span data-ttu-id="0e402-105">Przewodnik korzysta z roli Księgowy i danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="0e402-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="0e402-106">Wybierz kolejno opcje Środki trwałe > Ustawienia > Grupy środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="0e402-106">Go to Fixed assets > Setup > Fixed asset groups.</span></span>
2. <span data-ttu-id="0e402-107">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="0e402-107">Click New.</span></span>
3. <span data-ttu-id="0e402-108">W polu Grupa środków trwałych wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0e402-108">In the Fixed asset group field, type a value.</span></span>
4. <span data-ttu-id="0e402-109">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0e402-109">In the Name field, type a value.</span></span>
    * <span data-ttu-id="0e402-110">Ustawienia Automatyczna numeracja środków trwałych i Kod sekwencji numerów w oknie Grupa środków trwałych zastąpią ustawienia w oknie Parametry środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="0e402-110">Autonumber fixed assets and Number sequence code on the Fixed asset group will override the settings on the Fixed assets parameters.</span></span> <span data-ttu-id="0e402-111">Można zmienić to w tym oknie, jeśli składniki aktywów z tej grupy środków trwałych będą miały inną numerację niż pozostałe grupy.</span><span class="sxs-lookup"><span data-stu-id="0e402-111">You can change it here if the assets in this fixed asset group will have different numbering from other groups.</span></span>  
5. <span data-ttu-id="0e402-112">Kliknij opcję Księgi.</span><span class="sxs-lookup"><span data-stu-id="0e402-112">Click Books.</span></span>
6. <span data-ttu-id="0e402-113">Wprowadź lub wybierz wartość w polu Księga.</span><span class="sxs-lookup"><span data-stu-id="0e402-113">In the Book field, enter or select a value.</span></span>
    * <span data-ttu-id="0e402-114">Pole Oblicz amortyzację ma zaznaczoną opcję Tak, dlatego ewidencja środków trwałych będzie uwzględniana w propozycjach amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="0e402-114">The Calculate depreciation field is set to Yes, so the asset book will be included in depreciation proposals.</span></span> <span data-ttu-id="0e402-115">Jeśli ustawienie Oblicz amortyzację ma wartość Nie, środek trwały nie będzie automatycznie amortyzowany.</span><span class="sxs-lookup"><span data-stu-id="0e402-115">If Calculate depreciation is set to No, the asset will not be automatically depreciated.</span></span>  
7. <span data-ttu-id="0e402-116">Ustaw okres użytkowania składnika aktywów w latach.</span><span class="sxs-lookup"><span data-stu-id="0e402-116">Set the Service life of the asset, in years.</span></span>
    * <span data-ttu-id="0e402-117">Należy zauważyć, że wartość pola Okresy amortyzacji jest obliczana po ustawieniu okresu użytkowania.</span><span class="sxs-lookup"><span data-stu-id="0e402-117">Note that the Depreciation periods field value is calculated after setting the Service life.</span></span>  
8. <span data-ttu-id="0e402-118">W polu Konwencja amortyzacji wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="0e402-118">In the Depreciation convention field, select an option.</span></span>
9. <span data-ttu-id="0e402-119">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="0e402-119">Close the page.</span></span>

