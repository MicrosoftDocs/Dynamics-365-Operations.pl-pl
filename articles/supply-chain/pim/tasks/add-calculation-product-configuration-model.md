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
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 49d09a3544631960e3f6b292dbdd8927dd499f07
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4987061"
---
# <a name="add-a-calculation-to-a-product-configuration-model"></a><span data-ttu-id="29407-103">Dodawanie obliczenia do modelu konfiguracji produktu</span><span class="sxs-lookup"><span data-stu-id="29407-103">Add a calculation to a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="29407-104">W tej procedurze pokazano, jak dodać nowe obliczenie do modelu konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="29407-104">This procedure shows how to add a new calculation to a product configuration model.</span></span> <span data-ttu-id="29407-105">Pokazuje sposób tworzenia wyrażenia logicznego za pomocą operatora „If”, aby ustawić wysokość głośnika na 10 dla białych głośników i na 15 dla wszystkich pozostałych wykończeń obudowy.</span><span class="sxs-lookup"><span data-stu-id="29407-105">It shows how you can create a logical expression using the "If" operator to set a speaker height to 10 for white speakers and 15 for all other cabinet finishes.</span></span> <span data-ttu-id="29407-106">Procedura wykorzystuje składnik Głośnik o wysokiej jakości zawarty w firmie demonstracyjnych USMF.</span><span class="sxs-lookup"><span data-stu-id="29407-106">The procedure uses the High end speaker component in the demo company USMF.</span></span>


## <a name="add-a-calculation"></a><span data-ttu-id="29407-107">Dodawanie obliczenia</span><span class="sxs-lookup"><span data-stu-id="29407-107">Add a calculation</span></span>

## <a name="create-calculation-expression"></a><span data-ttu-id="29407-108">Tworzenie wyrażenia obliczenia</span><span class="sxs-lookup"><span data-stu-id="29407-108">Create calculation expression</span></span>
1. <span data-ttu-id="29407-109">Kliknij opcję Edytuj wyrażenie.</span><span class="sxs-lookup"><span data-stu-id="29407-109">Click Edit expression.</span></span>
2. <span data-ttu-id="29407-110">W polu ConstraintBody wpisz „If[CabinetFinish=="Biały", 10, 15]”.</span><span class="sxs-lookup"><span data-stu-id="29407-110">In the ConstraintBody field, enter 'If[CabinetFinish=="White", 10, 15]'.</span></span>
3. <span data-ttu-id="29407-111">Kliknij przycisk Sprawdź poprawność.</span><span class="sxs-lookup"><span data-stu-id="29407-111">Click Validate.</span></span>
4. <span data-ttu-id="29407-112">Kliknij przycisk Zamknij.</span><span class="sxs-lookup"><span data-stu-id="29407-112">Click Close.</span></span>
5. <span data-ttu-id="29407-113">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="29407-113">Click OK.</span></span>

