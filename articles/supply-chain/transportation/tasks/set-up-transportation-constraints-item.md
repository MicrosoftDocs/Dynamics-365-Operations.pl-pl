---
title: Konfigurowanie ograniczeń transportu towaru
description: Ta procedura skonfiguruje ograniczenie transportu uniemożliwiające przewożenie wybranego towaru za pośrednictwem wybranego centrum.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSConstraint, InventLocationIdLookup, InventItemIdLookupSimple
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4ccd7d79fbcdd600f78dbff98ce39c04865afe37
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3146153"
---
# <a name="set-up-transportation-constraints-for-an-item"></a><span data-ttu-id="6d9e1-103">Konfigurowanie ograniczeń transportu towaru</span><span class="sxs-lookup"><span data-stu-id="6d9e1-103">Set up transportation constraints for an item</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6d9e1-104">Ta procedura skonfiguruje ograniczenie transportu uniemożliwiające przewożenie wybranego towaru za pośrednictwem wybranego centrum.</span><span class="sxs-lookup"><span data-stu-id="6d9e1-104">This procedure will set up a transportation constraint to prevent a selected item from being transported through a selected hub.</span></span> <span data-ttu-id="6d9e1-105">To zadanie zazwyczaj wykonuje koordynator transportu.</span><span class="sxs-lookup"><span data-stu-id="6d9e1-105">This task would typically be carried out by a Transportation coordinator.</span></span> <span data-ttu-id="6d9e1-106">Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="6d9e1-106">You can use this procedure in the USMF demo data company or on your own data.</span></span>


## <a name="create-an-item-constaint"></a><span data-ttu-id="6d9e1-107">Tworzenie ograniczenia dla towaru</span><span class="sxs-lookup"><span data-stu-id="6d9e1-107">Create an item constaint</span></span>
1. <span data-ttu-id="6d9e1-108">Przejdź do okna Ograniczenia.</span><span class="sxs-lookup"><span data-stu-id="6d9e1-108">Go to Constraints.</span></span>
2. <span data-ttu-id="6d9e1-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="6d9e1-109">Click New.</span></span>
3. <span data-ttu-id="6d9e1-110">W polu Ograniczenie pozycji wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="6d9e1-110">In the Item constraint field, type a value.</span></span>
4. <span data-ttu-id="6d9e1-111">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="6d9e1-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="6d9e1-112">W polu Oddział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="6d9e1-112">In the Site field, enter or select a value.</span></span>
6. <span data-ttu-id="6d9e1-113">W polu Magazyn wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="6d9e1-113">In the Warehouse field, enter or select a value.</span></span>
7. <span data-ttu-id="6d9e1-114">W polu Numer towaru wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="6d9e1-114">In the Item number field, enter or select a value.</span></span>
8. <span data-ttu-id="6d9e1-115">W polu Centrum wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="6d9e1-115">In the Hub field, enter or select a value.</span></span>
9. <span data-ttu-id="6d9e1-116">W polu Akcja ograniczenia wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="6d9e1-116">In the Constraint action field, select an option.</span></span>
10. <span data-ttu-id="6d9e1-117">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="6d9e1-117">Click Save.</span></span>
11. <span data-ttu-id="6d9e1-118">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="6d9e1-118">Close the page.</span></span>

