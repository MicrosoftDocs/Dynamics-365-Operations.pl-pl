---
title: Tworzenie obiektów kosztów
description: W tej procedurze pokazano sposób tworzenia obiektów kosztów, importując wymiar finansowy centrum kosztu programu Dynamics 365 for Finance and Operations Enterprise Edition do modułu Rachunek kosztów za pośrednictwem łącznika danych.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension, CAMAXFinancialDimensionMemberProviderConfiguration, CAMDimensionMember
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8f63827977f080aa78fb385c60f757ad6b710005
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1841256"
---
# <a name="create-cost-objects"></a><span data-ttu-id="c3409-103">Tworzenie obiektów kosztów</span><span class="sxs-lookup"><span data-stu-id="c3409-103">Create cost objects</span></span> 

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c3409-104">W tej procedurze pokazano sposób tworzenia obiektów kosztów, importując wymiar finansowy centrum kosztu programu Dynamics 365 for Finance and Operations Enterprise Edition do modułu Rachunek kosztów za pośrednictwem łącznika danych.</span><span class="sxs-lookup"><span data-stu-id="c3409-104">This procedure shows how to create cost objects by importing the Dynamics 365 for Finance and Operations, Enterprise edition cost center financial dimension into Cost accounting via a data connector.</span></span> <span data-ttu-id="c3409-105">Dane wykorzystane do utworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="c3409-105">The USMF demo company was used to create this procedure.</span></span> <span data-ttu-id="c3409-106">Procedura dotyczy funkcji Rachunek kosztów dodanej w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="c3409-106">This procedure is for a Cost accounting feature that was added in Dynamics 365 for Operations, version 1611.</span></span>


## <a name="create-new-cost-objects"></a><span data-ttu-id="c3409-107">Tworzenie nowych obiektów kosztów</span><span class="sxs-lookup"><span data-stu-id="c3409-107">Create new cost objects</span></span>
1. <span data-ttu-id="c3409-108">Wybierz kolejno opcje Rachunek kosztów > Wymiary > Wymiary obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="c3409-108">Go to Cost accounting > Dimensions > Cost object dimensions.</span></span>
2. <span data-ttu-id="c3409-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="c3409-109">Click New.</span></span>
3. <span data-ttu-id="c3409-110">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c3409-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="c3409-111">W polu Łącznik danych dla elementów członkowskich wymiarów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c3409-111">In the Data connector for dimension members field, enter or select a value.</span></span>
5. <span data-ttu-id="c3409-112">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="c3409-112">In the Description field, type a value.</span></span>
6. <span data-ttu-id="c3409-113">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="c3409-113">Click Save.</span></span>

## <a name="configure-the-data-connector"></a><span data-ttu-id="c3409-114">Konfigurowanie łącznika danych</span><span class="sxs-lookup"><span data-stu-id="c3409-114">Configure the data connector</span></span>
1. <span data-ttu-id="c3409-115">Kliknij opcję Konfiguruj dostawcę elementów członkowskich wymiarów.</span><span class="sxs-lookup"><span data-stu-id="c3409-115">Click Configure dimension member provider.</span></span>
    * <span data-ttu-id="c3409-116">Wybierz centrum kosztu, aby zaimportować jego wymiar do modułu Rachunek kosztów.</span><span class="sxs-lookup"><span data-stu-id="c3409-116">Select CostCenter to import the CostCenter dimension into Cost accounting.</span></span>  
2. <span data-ttu-id="c3409-117">W polu Nazwa wymiaru wybierz wartość Centrum kosztu.</span><span class="sxs-lookup"><span data-stu-id="c3409-117">In the Dimension name field, select Cost center.</span></span>
3. <span data-ttu-id="c3409-118">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="c3409-118">Click OK.</span></span>

## <a name="import-cost-centers"></a><span data-ttu-id="c3409-119">Importowanie centrów kosztów</span><span class="sxs-lookup"><span data-stu-id="c3409-119">Import cost centers</span></span>
1. <span data-ttu-id="c3409-120">Kliknij opcję Importuj elementy członkowskie wymiaru.</span><span class="sxs-lookup"><span data-stu-id="c3409-120">Click Import dimension members.</span></span>
2. <span data-ttu-id="c3409-121">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="c3409-121">Click OK.</span></span>

## <a name="view-the-imported-cost-centers"></a><span data-ttu-id="c3409-122">Wyświetlanie zaimportowanych centrów kosztów</span><span class="sxs-lookup"><span data-stu-id="c3409-122">View the imported cost centers</span></span>
1. <span data-ttu-id="c3409-123">Kliknij opcję Wyświetl elementy członkowskie wymiaru.</span><span class="sxs-lookup"><span data-stu-id="c3409-123">Click View dimension members.</span></span>

