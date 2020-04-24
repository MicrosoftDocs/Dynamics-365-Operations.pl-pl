---
title: Dodawanie obliczenia do modelu konfiguracji produktu
description: W tej procedurze pokazano, jak dodać nowe obliczenie do modelu konfiguracji produktu.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 32bc2ac5815c2739147664f1e1df2528178db51e
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213407"
---
# <a name="add-a-calculation-to-a-product-configuration-model"></a><span data-ttu-id="d421d-103">Dodawanie obliczenia do modelu konfiguracji produktu</span><span class="sxs-lookup"><span data-stu-id="d421d-103">Add a calculation to a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d421d-104">W tej procedurze pokazano, jak dodać nowe obliczenie do modelu konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="d421d-104">This procedure shows how to add a new calculation to a product configuration model.</span></span> <span data-ttu-id="d421d-105">Pokazuje sposób tworzenia wyrażenia logicznego za pomocą operatora „If”, aby ustawić wysokość głośnika na 10 dla białych głośników i na 15 dla wszystkich pozostałych wykończeń obudowy.</span><span class="sxs-lookup"><span data-stu-id="d421d-105">It shows how you can create a logical expression using the "If" operator to set a speaker height to 10 for white speakers and 15 for all other cabinet finishes.</span></span> <span data-ttu-id="d421d-106">Procedura wykorzystuje składnik Głośnik o wysokiej jakości zawarty w firmie demonstracyjnych USMF.</span><span class="sxs-lookup"><span data-stu-id="d421d-106">The procedure uses the High end speaker component in the demo company USMF.</span></span>


## <a name="add-a-calculation"></a><span data-ttu-id="d421d-107">Dodawanie obliczenia</span><span class="sxs-lookup"><span data-stu-id="d421d-107">Add a calculation</span></span>

## <a name="create-calculation-expression"></a><span data-ttu-id="d421d-108">Tworzenie wyrażenia obliczenia</span><span class="sxs-lookup"><span data-stu-id="d421d-108">Create calculation expression</span></span>
1. <span data-ttu-id="d421d-109">Kliknij opcję Edytuj wyrażenie.</span><span class="sxs-lookup"><span data-stu-id="d421d-109">Click Edit expression.</span></span>
2. <span data-ttu-id="d421d-110">W polu ConstraintBody wpisz „If[CabinetFinish=="Biały", 10, 15]”.</span><span class="sxs-lookup"><span data-stu-id="d421d-110">In the ConstraintBody field, enter 'If[CabinetFinish=="White", 10, 15]'.</span></span>
3. <span data-ttu-id="d421d-111">Kliknij przycisk Sprawdź poprawność.</span><span class="sxs-lookup"><span data-stu-id="d421d-111">Click Validate.</span></span>
4. <span data-ttu-id="d421d-112">Kliknij przycisk Zamknij.</span><span class="sxs-lookup"><span data-stu-id="d421d-112">Click Close.</span></span>
5. <span data-ttu-id="d421d-113">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="d421d-113">Click OK.</span></span>

