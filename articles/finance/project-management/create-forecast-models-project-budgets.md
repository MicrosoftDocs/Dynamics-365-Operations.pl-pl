---
title: Tworzenie modeli prognozy dla budżetów projektu
description: W tym temacie opisano sposób tworzenia modelu prognozy dla pozostałych budżetów.
author: RadhikaRS
manager: AnnBe
ms.date: 04/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 07e540f23a668b40a54906a67d87552fe991825a
ms.sourcegitcommit: 5de75c61c33e57c813944f1ab6100aceb020d432
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/29/2020
ms.locfileid: "3321786"
---
# <a name="create-forecast-models-for-project-budgets"></a><span data-ttu-id="99967-103">Tworzenie modeli prognozy dla budżetów projektu</span><span class="sxs-lookup"><span data-stu-id="99967-103">Create forecast models for project budgets</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="99967-104">W tym temacie opisano sposób tworzenia modelu prognozy dla pozostałych budżetów.</span><span class="sxs-lookup"><span data-stu-id="99967-104">This topic describes how to create a forecast model for remaining budgets.</span></span> <span data-ttu-id="99967-105">Projekt, dla którego obowiązuje kontrola budżetu używa dwóch typów budżetu: pierwotnego i pozostałego.</span><span class="sxs-lookup"><span data-stu-id="99967-105">A project that is subject to budget control uses two types of budgets: original and remaining.</span></span> <span data-ttu-id="99967-106">Podczas tworzenia budżetu projektu należy określić modele prognoz pozostałego i pierwotnego budżetu, które zostały utworzone na stronie **Modele prognoz**.</span><span class="sxs-lookup"><span data-stu-id="99967-106">When you create a project budget, you must specify the original and remaining budget forecast models that were created in the **Forecast models** page.</span></span> <span data-ttu-id="99967-107">Budżety projektów oparte na określonych modelach są tworzone podczas zatwierdzania budżetu projektu.</span><span class="sxs-lookup"><span data-stu-id="99967-107">Project budgets based on the specified models are created when you commit the project budget.</span></span>

> [!NOTE]
> <span data-ttu-id="99967-108">Model prognozy używany do kontroli budżetu nie może mieć podmodelu ani służyć jako podmodel.</span><span class="sxs-lookup"><span data-stu-id="99967-108">A forecast model that is used for budget control can’t have a submodel or be used as a submodel.</span></span>

1. <span data-ttu-id="99967-109">Wybierz pozycję **Zarządzanie projektami i ich księgowanie** > **Konfiguracja** > **Prognozy**  > **Modele prognoz**.</span><span class="sxs-lookup"><span data-stu-id="99967-109">Select **Project management and accounting** > **Setup** > **Forecasts**  > **Forecast models**.</span></span>
2. <span data-ttu-id="99967-110">Wybierz pozycję **Nowy**, aby utworzyć nowy model prognozy, a następnie wprowadź numer identyfikacyjny i nazwę nowego modelu.</span><span class="sxs-lookup"><span data-stu-id="99967-110">Select **New** to create a new forecast model, and then enter a model ID number and name for the new model.</span></span> 
3. <span data-ttu-id="99967-111">Ustaw opcję **Zatrzymano** na **Tak**, aby uniemożliwić wprowadzanie zmian w wierszach prognozy dla modelu prognozy.</span><span class="sxs-lookup"><span data-stu-id="99967-111">Set the **Stopped** option to **Yes** to prevent any changes to the forecast lines for the forecast model.</span></span> 
4. <span data-ttu-id="99967-112">Jeśli wiersze prognozy, z którymi model jest skojarzony, muszą generować prognozy przepływów pieniężnych w księdze głównej, ustaw opcję **Uwzględnianie budżetów w prognozach przepływów pieniężnych** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="99967-112">If the forecast lines that the model is associated with should generate cash flow forecasts in the general ledger, set **Include in Cash flow forecasts** to **Yes.**</span></span> 
5. <span data-ttu-id="99967-113">Aby użyć daty projektu jako daty faktury, ustaw **datę faktury prognozy** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="99967-113">To use the project date as the invoice date, set **Forecast Invoice date** to **Yes**.</span></span> 
6. <span data-ttu-id="99967-114">W polu **Typ budżetu** wybierz jeden z następujących typów modeli:</span><span class="sxs-lookup"><span data-stu-id="99967-114">In the **Budget type** field, select one of the following model types:</span></span>

   - <span data-ttu-id="99967-115">**Budżet pierwotny**: użyj kwot budżetu pierwotnego ustalonych podczas tworzenia i zatwierdzania początkowego budżetu.</span><span class="sxs-lookup"><span data-stu-id="99967-115">**Original budget**: Use the original budget amounts that are committed when the initial budget is created and approved.</span></span>
   - <span data-ttu-id="99967-116">**Pozostały budżet**: użyj kwot pozostałego budżetu w okresie użytkowania projektu.</span><span class="sxs-lookup"><span data-stu-id="99967-116">**Remaining budget**: Use the remaining budget amounts during the life of the project.</span></span> <span data-ttu-id="99967-117">Salda w tym modelu prognozy są pomniejszone o rzeczywiste transakcje i powiększone lub pomniejszone o korekty budżetu.</span><span class="sxs-lookup"><span data-stu-id="99967-117">The balances in this forecast model are reduced by actual transactions and increased or decreased by budget revisions.</span></span>
   - <span data-ttu-id="99967-118">**Przenieś na następny okres**: użyj kwot budżetu przeniesionego na późniejszy okres dla projektu.</span><span class="sxs-lookup"><span data-stu-id="99967-118">**Carry-forward**: Use the carry-forward budget amounts for the project.</span></span> <span data-ttu-id="99967-119">Przeniesienie na następny okres jest opcjonalnym procesem uruchamianym w celu przeniesienia niewykorzystanych kwot budżetu do innego roku obrachunkowego.</span><span class="sxs-lookup"><span data-stu-id="99967-119">Carry-forward is an optional process that can be run to transfer unused budget amounts from one fiscal year to another.</span></span>

7. <span data-ttu-id="99967-120">W razie potrzeby ustaw następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="99967-120">Set the following options as required:</span></span>

   - <span data-ttu-id="99967-121">Włącz **datę faktury projektu**, aby użyć daty projektu jako daty faktury.</span><span class="sxs-lookup"><span data-stu-id="99967-121">Enable **Forecast invoice date** to use the project date as the invoice date.</span></span>
   - <span data-ttu-id="99967-122">Włącz **prognozę przy użyciu PWT**, aby prognozować na podstawie pracy w toku (PWT), a następnie wybierz typ PWT.</span><span class="sxs-lookup"><span data-stu-id="99967-122">Enable **Forecast with WIP** to forecast based on work in progress (WIP), and then select the type of WIP.</span></span> 
   - <span data-ttu-id="99967-123">Możesz zachować domyślny **typ budżetu** jako **Brak** lub wprowadzić nowy typ.</span><span class="sxs-lookup"><span data-stu-id="99967-123">You can keep the default **Budget type** as **None** or enter a new type.</span></span> <span data-ttu-id="99967-124">Typu budżetu nie można zmienić po zmianie rekordu.</span><span class="sxs-lookup"><span data-stu-id="99967-124">The budget type can't be changed after you change a record.</span></span>     
    > [!NOTE]
    > <span data-ttu-id="99967-125">Zmiana domyślnego typu budżetu spowoduje, że wszystkie inne opcje staną się niedostępne dla aktualizacji i nie będzie można ponownie użyć tego modelu prognozy.</span><span class="sxs-lookup"><span data-stu-id="99967-125">If you change the default budget type, all other options will become unavailable for updates, and you can't reuse this forecast model.</span></span> 
   


 

