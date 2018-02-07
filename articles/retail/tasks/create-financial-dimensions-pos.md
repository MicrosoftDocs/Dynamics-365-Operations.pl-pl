--- 
title: "Tworzenie wymiarów finansowych dla rejestrów punktu sprzedaży i konfigurowanie wartości wymiarów z rejestrów"
description: "Ta procedura prowadzi przez proces tworzenia wymiarów finansowych dla kas w punkcie sprzedaży (POS) i pokazuje, jak konfigurować wartości wymiarów finansowych w kasach."
author: jashanno
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: d2d34080409de25a3a1966d0898d0ecd98297891
ms.contentlocale: pl-pl
ms.lasthandoff: 02/07/2018

---
# <a name="create-financial-dimensions-for-pos-registers-and-configure-dimension-values-on-registers"></a><span data-ttu-id="e6dde-103">Tworzenie wymiarów finansowych dla rejestrów punktu sprzedaży i konfigurowanie wartości wymiarów z rejestrów</span><span class="sxs-lookup"><span data-stu-id="e6dde-103">Create financial dimensions for POS registers and configure dimension values on registers</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="e6dde-104">Ta procedura prowadzi przez proces tworzenia wymiarów finansowych dla kas w punkcie sprzedaży (POS) i pokazuje, jak konfigurować wartości wymiarów finansowych w kasach.</span><span class="sxs-lookup"><span data-stu-id="e6dde-104">This procedure walks through creating financial dimensions for point of sale (POS) registers, and demonstrates how to configure financial dimension values on registers.</span></span> <span data-ttu-id="e6dde-105">Procedura nie ma innych czynności pokrewnych, takich jak tworzenie zestawów wymiarów i struktur kont.</span><span class="sxs-lookup"><span data-stu-id="e6dde-105">This procedure doesn’t include other related steps, such as creating dimension sets and account structures.</span></span> <span data-ttu-id="e6dde-106">Te zadania znajdują się w innych artykułach.</span><span class="sxs-lookup"><span data-stu-id="e6dde-106">Those tasks can be found in other topics.</span></span> <span data-ttu-id="e6dde-107">To nagranie wykorzystuje firmę demonstracyjną USRT.</span><span class="sxs-lookup"><span data-stu-id="e6dde-107">This recording uses USRT demo company.</span></span>

1. <span data-ttu-id="e6dde-108">Wybierz kolejno opcje Księga główna > Plan kont > Wymiary > Wymiary finansowe.</span><span class="sxs-lookup"><span data-stu-id="e6dde-108">Go to General ledger > Chart of accounts > Dimensions > Financial dimensions.</span></span>
2. <span data-ttu-id="e6dde-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e6dde-109">Click New.</span></span>
3. <span data-ttu-id="e6dde-110">W polu Użyj wartości z wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="e6dde-110">In the Use values from field, select an option.</span></span>
4. <span data-ttu-id="e6dde-111">W polu Wymiar menu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e6dde-111">In the Dimension name field, type a value.</span></span>
5. <span data-ttu-id="e6dde-112">Kliknij Aktywacja.</span><span class="sxs-lookup"><span data-stu-id="e6dde-112">Click Activate.</span></span>
6. <span data-ttu-id="e6dde-113">Kliknij przycisk Zamknij.</span><span class="sxs-lookup"><span data-stu-id="e6dde-113">Click Close.</span></span>
7. <span data-ttu-id="e6dde-114">Kliknij Aktywacja.</span><span class="sxs-lookup"><span data-stu-id="e6dde-114">Click Activate.</span></span>
8. <span data-ttu-id="e6dde-115">Kliknij opcję Wartości wymiarów.</span><span class="sxs-lookup"><span data-stu-id="e6dde-115">Click Dimension values.</span></span>
9. <span data-ttu-id="e6dde-116">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e6dde-116">Close the page.</span></span>
10. <span data-ttu-id="e6dde-117">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="e6dde-117">Click Save.</span></span>
11. <span data-ttu-id="e6dde-118">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e6dde-118">Close the page.</span></span>
12. <span data-ttu-id="e6dde-119">Wybierz kolejno opcje Handel detaliczny i inny > Ustawienia kanału > Ustawienia punktu sprzedaży > Rejestry.</span><span class="sxs-lookup"><span data-stu-id="e6dde-119">Go to Retail and commerce > Channel setup > POS setup > Registers.</span></span>
13. <span data-ttu-id="e6dde-120">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="e6dde-120">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="e6dde-121">Przełącz rozwinięcie sekcji Wymiary finansowe.</span><span class="sxs-lookup"><span data-stu-id="e6dde-121">Toggle the expansion of the Financial dimensions section.</span></span>
15. <span data-ttu-id="e6dde-122">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="e6dde-122">Click Edit.</span></span>
16. <span data-ttu-id="e6dde-123">W polu Terminal kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="e6dde-123">In the Terminal field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="e6dde-124">Na liście znajdź i wybierz wartość wymiaru dla aktualizowanej kasy.</span><span class="sxs-lookup"><span data-stu-id="e6dde-124">In the list, find and select the dimension value for the register being updated.</span></span>
18. <span data-ttu-id="e6dde-125">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="e6dde-125">Click Save.</span></span>


