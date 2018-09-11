--- 
title: Dodawanie obliczenia do modelu konfiguracji produktu
description: "W tej procedurze pokazano, jak dodać nowe obliczenie do modelu konfiguracji produktu."
author: ShylaThompson
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: bdd596e93301bceb9261d531264dc42299ca36c6
ms.contentlocale: pl-pl
ms.lasthandoff: 09/11/2018

---
# <a name="add-a-calculation-to-a-product-configuration-model"></a><span data-ttu-id="12705-103">Dodawanie obliczenia do modelu konfiguracji produktu</span><span class="sxs-lookup"><span data-stu-id="12705-103">Add a calculation to a product configuration model</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="12705-104">W tej procedurze pokazano, jak dodać nowe obliczenie do modelu konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="12705-104">This procedure shows how to add a new calculation to a product configuration model.</span></span> <span data-ttu-id="12705-105">Pokazuje sposób tworzenia wyrażenia logicznego za pomocą operatora „If”, aby ustawić wysokość głośnika na 10 dla białych głośników i na 15 dla wszystkich pozostałych wykończeń obudowy.</span><span class="sxs-lookup"><span data-stu-id="12705-105">It shows how you can create a logical expression using the "If" operator to set a speaker height to 10 for white speakers and 15 for all other cabinet finishes.</span></span> <span data-ttu-id="12705-106">Procedura wykorzystuje składnik Głośnik o wysokiej jakości zawarty w firmie demonstracyjnych USMF.</span><span class="sxs-lookup"><span data-stu-id="12705-106">The procedure uses the High end speaker component in the demo company USMF.</span></span>


## <a name="add-a-calculation"></a><span data-ttu-id="12705-107">Dodawanie obliczenia</span><span class="sxs-lookup"><span data-stu-id="12705-107">Add a calculation</span></span>

## <a name="create-calculation-expression"></a><span data-ttu-id="12705-108">Tworzenie wyrażenia obliczenia</span><span class="sxs-lookup"><span data-stu-id="12705-108">Create calculation expression</span></span>
1. <span data-ttu-id="12705-109">Kliknij opcję Edytuj wyrażenie.</span><span class="sxs-lookup"><span data-stu-id="12705-109">Click Edit expression.</span></span>
2. <span data-ttu-id="12705-110">W polu ConstraintBody wpisz „If[CabinetFinish=="Biały", 10, 15]”.</span><span class="sxs-lookup"><span data-stu-id="12705-110">In the ConstraintBody field, enter 'If[CabinetFinish=="White", 10, 15]'.</span></span>
3. <span data-ttu-id="12705-111">Kliknij przycisk Sprawdź poprawność.</span><span class="sxs-lookup"><span data-stu-id="12705-111">Click Validate.</span></span>
4. <span data-ttu-id="12705-112">Kliknij przycisk Zamknij.</span><span class="sxs-lookup"><span data-stu-id="12705-112">Click Close.</span></span>
5. <span data-ttu-id="12705-113">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="12705-113">Click OK.</span></span>


