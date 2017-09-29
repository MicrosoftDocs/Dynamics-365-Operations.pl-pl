--- 
title: "Dodawanie ograniczenia wyrażenia do modelu konfiguracji produktu"
description: "W tej procedurze pokazano, jak można dodać nowe wyrażenie ograniczenia do modelu konfiguracji produktu."
author: YuyuScheller
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 8db46c5b8361c96745b440c0d0684e18c06a6c6f
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="add-an-expression-constraint-to-a-product-configuration-model"></a><span data-ttu-id="75e80-103">Dodawanie ograniczenia wyrażenia do modelu konfiguracji produktu</span><span class="sxs-lookup"><span data-stu-id="75e80-103">Add an expression constraint to a product configuration model</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="75e80-104">W tej procedurze pokazano, jak można dodać nowe wyrażenie ograniczenia do modelu konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="75e80-104">This procedure shows how you can add a new constraint expression to a product configuration model.</span></span> <span data-ttu-id="75e80-105">Pokazuje sposób wprowadzenia wymogu zastosowania ochrony narożników do głośnika, jeśli użytkownik wybrał metalową maskownicę.</span><span class="sxs-lookup"><span data-stu-id="75e80-105">It shows how you can mandate that corner protection must be applied to a speaker if the user has selected a front grill in metal.</span></span> <span data-ttu-id="75e80-106">Procedura wykorzystuje składnik Głośnik o wysokiej jakości zawarty w firmie demonstracyjnych USMF.</span><span class="sxs-lookup"><span data-stu-id="75e80-106">The procedure uses the High end speaker component in the demo company USMF.</span></span>


## <a name="create-an-expression-constraint"></a><span data-ttu-id="75e80-107">Tworzenie ograniczenia wyrażenia</span><span class="sxs-lookup"><span data-stu-id="75e80-107">Create an expression constraint</span></span>
1. <span data-ttu-id="75e80-108">Kliknij opcję Definicja modelu wariantu produktu.</span><span class="sxs-lookup"><span data-stu-id="75e80-108">Click Product variant model definition.</span></span>
2. <span data-ttu-id="75e80-109">Kliknij opcję Modele konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="75e80-109">Click Product configuration models.</span></span>
3. <span data-ttu-id="75e80-110">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="75e80-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="75e80-111">W tym przykładzie jest używany model głośnika o wysokiej jakości.</span><span class="sxs-lookup"><span data-stu-id="75e80-111">This example uses the high end speaker model.</span></span>  
4. <span data-ttu-id="75e80-112">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="75e80-112">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="75e80-113">Rozwiń sekcję Ograniczenia.</span><span class="sxs-lookup"><span data-stu-id="75e80-113">Expand the Constraints section.</span></span>
6. <span data-ttu-id="75e80-114">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="75e80-114">Click Add.</span></span>
7. <span data-ttu-id="75e80-115">Kliknij przycisk Utwórz.</span><span class="sxs-lookup"><span data-stu-id="75e80-115">Click Create.</span></span>
8. <span data-ttu-id="75e80-116">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="75e80-116">In the Name field, type a value.</span></span>

## <a name="enter-expression"></a><span data-ttu-id="75e80-117">Wprowadź wyrażenie</span><span class="sxs-lookup"><span data-stu-id="75e80-117">Enter expression</span></span>
1. <span data-ttu-id="75e80-118">Kliknij opcję Edytuj wyrażenie.</span><span class="sxs-lookup"><span data-stu-id="75e80-118">Click Edit expression.</span></span>
    * <span data-ttu-id="75e80-119">Jeśli na tym etapie nagrania zadania odblokujesz interfejs użytkownika, możesz użyć funkcji IntelliSense i listy symboli, aby utworzyć wyrażenie ograniczenia.</span><span class="sxs-lookup"><span data-stu-id="75e80-119">If you unlock the user interface in the task recording at this stage, you can use IntelliSense and the list of symbols to build the constraint expression .</span></span>  
2. <span data-ttu-id="75e80-120">W polu ConstraintBody wpisz „Implies[FrontGrill=="Metal", CornerProtection]”.</span><span class="sxs-lookup"><span data-stu-id="75e80-120">In the ConstraintBody field, enter 'Implies[FrontGrill=="Metal", CornerProtection] '.</span></span>
    * <span data-ttu-id="75e80-121">Ta logika wyrażenia oznacza: Jeśli maskownica jest metalowa, to musi być zaznaczona opcja ochrony narożników.</span><span class="sxs-lookup"><span data-stu-id="75e80-121">This expression logic states: If the Front grill is  metal, then the corner protection option must be selected.</span></span>  
3. <span data-ttu-id="75e80-122">Kliknij przycisk Sprawdź poprawność.</span><span class="sxs-lookup"><span data-stu-id="75e80-122">Click Validate.</span></span>
    * <span data-ttu-id="75e80-123">Funkcja sprawdzania poprawności bada całe wyrażenie ograniczenia i wykrywa błędy składniowe.</span><span class="sxs-lookup"><span data-stu-id="75e80-123">The validate function runs through the constraint expression and checks for syntax errors.</span></span>  
4. <span data-ttu-id="75e80-124">Kliknij przycisk Zamknij.</span><span class="sxs-lookup"><span data-stu-id="75e80-124">Click Close.</span></span>
5. <span data-ttu-id="75e80-125">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="75e80-125">Click OK.</span></span>


