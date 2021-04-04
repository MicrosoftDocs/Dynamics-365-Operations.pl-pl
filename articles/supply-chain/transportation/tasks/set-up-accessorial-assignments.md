---
title: Konfigurowanie przypisania usług dodatkowych
description: W tej procedurze pokazano sposób konfigurowania przypisania usług dodatkowych.
author: ShylaThompson
manager: tfehr
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSAccessorialAssignment
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: eed109551762ff2e120ab4362c6ca0f01f71d0c2
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5233758"
---
# <a name="set-up-accessorial-assignments"></a><span data-ttu-id="ababb-103">Konfigurowanie przypisania usług dodatkowych</span><span class="sxs-lookup"><span data-stu-id="ababb-103">Set up accessorial assignments</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ababb-104">W tej procedurze pokazano sposób konfigurowania przypisania usług dodatkowych.</span><span class="sxs-lookup"><span data-stu-id="ababb-104">This procedure shows how to set up an accessorial assignment.</span></span> <span data-ttu-id="ababb-105">Zazwyczaj jest to realizowane przez koordynatora transportu.</span><span class="sxs-lookup"><span data-stu-id="ababb-105">This is typically done by a transportation coordinator.</span></span> <span data-ttu-id="ababb-106">Zanim będzie można użyć tego przewodnika, należy wykonać zadania z przewodnika „Ustawianie opłat za usługi dodatkowe Centrum i głównych usług dodatkowych”.</span><span class="sxs-lookup"><span data-stu-id="ababb-106">Before you use this guide you need to run the "Set up hub accessorial charges and accessorial masters" guide.</span></span>


## <a name="set-up-accessorial-assignment"></a><span data-ttu-id="ababb-107">Konfigurowanie przypisania usług dodatkowych</span><span class="sxs-lookup"><span data-stu-id="ababb-107">Set up Accessorial assignment</span></span>
1. <span data-ttu-id="ababb-108">Wybierz kolejno opcje Zarządzanie transportem > Ustawienia > Ocena > Przypisania usług dodatkowych.</span><span class="sxs-lookup"><span data-stu-id="ababb-108">Go to Transportation management > Setup > Rating > Accessorial assignments.</span></span>
2. <span data-ttu-id="ababb-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ababb-109">Click New.</span></span>
3. <span data-ttu-id="ababb-110">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ababb-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="ababb-111">Przełącz rozwinięcie sekcji Szczegóły.</span><span class="sxs-lookup"><span data-stu-id="ababb-111">Toggle the expansion of the Details section.</span></span>
5. <span data-ttu-id="ababb-112">W polu Centrum kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="ababb-112">In the Hub field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="ababb-113">Z listy wybierz Centrum, dla których utworzono główne usługi dodatkowe podczas wykonywania zadań z przewodnika „Ustawianie opłat za usługi dodatkowe Centrum i głównych usług dodatkowych”.</span><span class="sxs-lookup"><span data-stu-id="ababb-113">In the list, select the Hub that you created an accessorial master for when you ran the "Set up hub accessorial charges and accessorial masters" guide.</span></span> 
7. <span data-ttu-id="ababb-114">W polu Identyfikator współpracownika centrum kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="ababb-114">In the Hub accessorial ID field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="ababb-115">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ababb-115">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="ababb-116">Przełącz rozwinięcie sekcji Kryteria.</span><span class="sxs-lookup"><span data-stu-id="ababb-116">Toggle the expansion of the Criteria section.</span></span>
    * <span data-ttu-id="ababb-117">W sekcji Kryteria można wybrać dokładne kryteria, kiedy ma być stosowana opłata, na podstawie różnych wartości oferowanych w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="ababb-117">In the Criteria section you can choose the exact criteria for when the charge should apply, based on the different values offered here.</span></span>  
10. <span data-ttu-id="ababb-118">W opcji Zawsze stosuj zaznacz wartość Tak.</span><span class="sxs-lookup"><span data-stu-id="ababb-118">Set the Always apply option to Yes.</span></span>
11. <span data-ttu-id="ababb-119">W polu Poziom przypisania usług dodatkowych wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="ababb-119">In the Accessorial assignment level field, select an option.</span></span>
12. <span data-ttu-id="ababb-120">Przełącz rozwinięcie sekcji Obliczanie.</span><span class="sxs-lookup"><span data-stu-id="ababb-120">Toggle the expansion of the Calculation section.</span></span>
13. <span data-ttu-id="ababb-121">W polu Typ opłaty za usługi dodatkowe wybierz opcję „Płaska”.</span><span class="sxs-lookup"><span data-stu-id="ababb-121">In the Accessorial fee type field, select 'Flat'.</span></span>
    * <span data-ttu-id="ababb-122">Typ opłaty za usługi dodatkowe określa sposób obliczania rzeczywistej opłaty.</span><span class="sxs-lookup"><span data-stu-id="ababb-122">The Accessorial fee type determines how to calculate the actual charge.</span></span> <span data-ttu-id="ababb-123">W tym przykładzie jest to opłata stała.</span><span class="sxs-lookup"><span data-stu-id="ababb-123">In this example it's a flat charge.</span></span>  
14. <span data-ttu-id="ababb-124">W polu Opłata za usługi dodatkowe wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="ababb-124">In the Accessorial fee field, enter a number.</span></span>
15. <span data-ttu-id="ababb-125">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="ababb-125">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]