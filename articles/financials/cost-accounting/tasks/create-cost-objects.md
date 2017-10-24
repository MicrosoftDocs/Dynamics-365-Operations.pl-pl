--- 
title: "Tworzenie obiektów kosztów"
description: "W tej procedurze pokazano sposób tworzenia obiektów kosztów, importując wymiar finansowy centrum kosztu programu Dynamics 365 for Finance and Operations Enterprise Edition do modułu Rachunek kosztów za pośrednictwem łącznika danych."
author: YuyuScheller
manager: AnnBe
ms.date: 10/25/2016
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
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5d43274aed2edbb91fd4e399cb8d45e91646b055
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="create-cost-objects"></a><span data-ttu-id="816bb-103">Tworzenie obiektów kosztów</span><span class="sxs-lookup"><span data-stu-id="816bb-103">Create cost objects</span></span> 

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="816bb-104">W tej procedurze pokazano sposób tworzenia obiektów kosztów, importując wymiar finansowy centrum kosztu programu Dynamics 365 for Finance and Operations Enterprise Edition do modułu Rachunek kosztów za pośrednictwem łącznika danych.</span><span class="sxs-lookup"><span data-stu-id="816bb-104">This procedure shows how to create cost objects by importing the Dynamics 365 for Finance and Operations, Enterprise edition cost center financial dimension into Cost accounting via a data connector.</span></span> <span data-ttu-id="816bb-105">Dane wykorzystane do utworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="816bb-105">The USMF demo company was used to create this procedure.</span></span> <span data-ttu-id="816bb-106">Procedura dotyczy funkcji Rachunek kosztów dodanej w programie Microsoft Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="816bb-106">This procedure is for a Cost accounting feature that was added in Dynamics 365 for Operations, version 1611.</span></span>


## <a name="create-new-cost-objects"></a><span data-ttu-id="816bb-107">Tworzenie nowych obiektów kosztów</span><span class="sxs-lookup"><span data-stu-id="816bb-107">Create new cost objects</span></span>
1. <span data-ttu-id="816bb-108">Wybierz kolejno opcje Rachunek kosztów > Wymiary > Wymiary obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="816bb-108">Go to Cost accounting > Dimensions > Cost object dimensions.</span></span>
2. <span data-ttu-id="816bb-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="816bb-109">Click New.</span></span>
3. <span data-ttu-id="816bb-110">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="816bb-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="816bb-111">W polu Łącznik danych dla elementów członkowskich wymiarów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="816bb-111">In the Data connector for dimension members field, enter or select a value.</span></span>
5. <span data-ttu-id="816bb-112">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="816bb-112">In the Description field, type a value.</span></span>
6. <span data-ttu-id="816bb-113">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="816bb-113">Click Save.</span></span>

## <a name="configure-the-data-connector"></a><span data-ttu-id="816bb-114">Konfigurowanie łącznika danych</span><span class="sxs-lookup"><span data-stu-id="816bb-114">Configure the data connector</span></span>
1. <span data-ttu-id="816bb-115">Kliknij opcję Konfiguruj dostawcę elementów członkowskich wymiarów.</span><span class="sxs-lookup"><span data-stu-id="816bb-115">Click Configure dimension member provider.</span></span>
    * <span data-ttu-id="816bb-116">Wybierz centrum kosztu, aby zaimportować jego wymiar do modułu Rachunek kosztów.</span><span class="sxs-lookup"><span data-stu-id="816bb-116">Select CostCenter to import the CostCenter dimension into Cost accounting.</span></span>  
2. <span data-ttu-id="816bb-117">W polu Nazwa wymiaru wybierz wartość Centrum kosztu.</span><span class="sxs-lookup"><span data-stu-id="816bb-117">In the Dimension name field, select Cost center.</span></span>
3. <span data-ttu-id="816bb-118">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="816bb-118">Click OK.</span></span>

## <a name="import-cost-centers"></a><span data-ttu-id="816bb-119">Importowanie centrów kosztów</span><span class="sxs-lookup"><span data-stu-id="816bb-119">Import cost centers</span></span>
1. <span data-ttu-id="816bb-120">Kliknij opcję Importuj elementy członkowskie wymiaru.</span><span class="sxs-lookup"><span data-stu-id="816bb-120">Click Import dimension members.</span></span>
2. <span data-ttu-id="816bb-121">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="816bb-121">Click OK.</span></span>

## <a name="view-the-imported-cost-centers"></a><span data-ttu-id="816bb-122">Wyświetlanie zaimportowanych centrów kosztów</span><span class="sxs-lookup"><span data-stu-id="816bb-122">View the imported cost centers</span></span>
1. <span data-ttu-id="816bb-123">Kliknij opcję Wyświetl elementy członkowskie wymiaru.</span><span class="sxs-lookup"><span data-stu-id="816bb-123">Click View dimension members.</span></span>


