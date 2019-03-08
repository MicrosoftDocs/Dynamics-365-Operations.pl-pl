---
title: Dodawanie ograniczenia wyrażenia do modelu konfiguracji produktu
description: W tej procedurze pokazano, jak można dodać nowe wyrażenie ograniczenia do modelu konfiguracji produktu.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, SysClientPolymorphicCreateSelector, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 56f94b82f8b2642b12a993bde7d6bb323da79f98
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "360585"
---
# <a name="add-an-expression-constraint-to-a-product-configuration-model"></a><span data-ttu-id="8758b-103">Dodawanie ograniczenia wyrażenia do modelu konfiguracji produktu</span><span class="sxs-lookup"><span data-stu-id="8758b-103">Add an expression constraint to a product configuration model</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8758b-104">W tej procedurze pokazano, jak można dodać nowe wyrażenie ograniczenia do modelu konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="8758b-104">This procedure shows how you can add a new constraint expression to a product configuration model.</span></span> <span data-ttu-id="8758b-105">Pokazuje sposób wprowadzenia wymogu zastosowania ochrony narożników do głośnika, jeśli użytkownik wybrał metalową maskownicę.</span><span class="sxs-lookup"><span data-stu-id="8758b-105">It shows how you can mandate that corner protection must be applied to a speaker if the user has selected a front grill in metal.</span></span> <span data-ttu-id="8758b-106">Procedura wykorzystuje składnik Głośnik o wysokiej jakości zawarty w firmie demonstracyjnych USMF.</span><span class="sxs-lookup"><span data-stu-id="8758b-106">The procedure uses the High end speaker component in the demo company USMF.</span></span>


## <a name="create-an-expression-constraint"></a><span data-ttu-id="8758b-107">Tworzenie ograniczenia wyrażenia</span><span class="sxs-lookup"><span data-stu-id="8758b-107">Create an expression constraint</span></span>
1. <span data-ttu-id="8758b-108">Kliknij opcję Definicja modelu wariantu produktu.</span><span class="sxs-lookup"><span data-stu-id="8758b-108">Click Product variant model definition.</span></span>
2. <span data-ttu-id="8758b-109">Kliknij opcję Modele konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="8758b-109">Click Product configuration models.</span></span>
3. <span data-ttu-id="8758b-110">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="8758b-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="8758b-111">W tym przykładzie jest używany model głośnika o wysokiej jakości.</span><span class="sxs-lookup"><span data-stu-id="8758b-111">This example uses the high end speaker model.</span></span>  
4. <span data-ttu-id="8758b-112">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="8758b-112">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="8758b-113">Rozwiń sekcję Ograniczenia.</span><span class="sxs-lookup"><span data-stu-id="8758b-113">Expand the Constraints section.</span></span>
6. <span data-ttu-id="8758b-114">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="8758b-114">Click Add.</span></span>
7. <span data-ttu-id="8758b-115">Kliknij przycisk Utwórz.</span><span class="sxs-lookup"><span data-stu-id="8758b-115">Click Create.</span></span>
8. <span data-ttu-id="8758b-116">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="8758b-116">In the Name field, type a value.</span></span>

## <a name="enter-expression"></a><span data-ttu-id="8758b-117">Wprowadź wyrażenie</span><span class="sxs-lookup"><span data-stu-id="8758b-117">Enter expression</span></span>
1. <span data-ttu-id="8758b-118">Kliknij opcję Edytuj wyrażenie.</span><span class="sxs-lookup"><span data-stu-id="8758b-118">Click Edit expression.</span></span>
    * <span data-ttu-id="8758b-119">Jeśli na tym etapie nagrania zadania odblokujesz interfejs użytkownika, możesz użyć funkcji IntelliSense i listy symboli, aby utworzyć wyrażenie ograniczenia.</span><span class="sxs-lookup"><span data-stu-id="8758b-119">If you unlock the user interface in the task recording at this stage, you can use IntelliSense and the list of symbols to build the constraint expression .</span></span>  
2. <span data-ttu-id="8758b-120">W polu ConstraintBody wpisz „Implies[FrontGrill=="Metal", CornerProtection]”.</span><span class="sxs-lookup"><span data-stu-id="8758b-120">In the ConstraintBody field, enter 'Implies[FrontGrill=="Metal", CornerProtection] '.</span></span>
    * <span data-ttu-id="8758b-121">Ta logika wyrażenia oznacza: Jeśli maskownica jest metalowa, to musi być zaznaczona opcja ochrony narożników.</span><span class="sxs-lookup"><span data-stu-id="8758b-121">This expression logic states: If the Front grill is  metal, then the corner protection option must be selected.</span></span>  
3. <span data-ttu-id="8758b-122">Kliknij przycisk Sprawdź poprawność.</span><span class="sxs-lookup"><span data-stu-id="8758b-122">Click Validate.</span></span>
    * <span data-ttu-id="8758b-123">Funkcja sprawdzania poprawności bada całe wyrażenie ograniczenia i wykrywa błędy składniowe.</span><span class="sxs-lookup"><span data-stu-id="8758b-123">The validate function runs through the constraint expression and checks for syntax errors.</span></span>  
4. <span data-ttu-id="8758b-124">Kliknij przycisk Zamknij.</span><span class="sxs-lookup"><span data-stu-id="8758b-124">Click Close.</span></span>
5. <span data-ttu-id="8758b-125">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="8758b-125">Click OK.</span></span>

