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
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1e12de1d51658092fb19f652cef7c1cc78b255b5
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "322681"
---
# <a name="create-cost-objects"></a><span data-ttu-id="44a4e-103">Tworzenie obiektów kosztów</span><span class="sxs-lookup"><span data-stu-id="44a4e-103">Create cost objects</span></span> 

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="44a4e-104">W tej procedurze pokazano sposób tworzenia obiektów kosztów, importując wymiar finansowy centrum kosztu programu Dynamics 365 for Finance and Operations Enterprise Edition do modułu Rachunek kosztów za pośrednictwem łącznika danych.</span><span class="sxs-lookup"><span data-stu-id="44a4e-104">This procedure shows how to create cost objects by importing the Dynamics 365 for Finance and Operations, Enterprise edition cost center financial dimension into Cost accounting via a data connector.</span></span> <span data-ttu-id="44a4e-105">Dane wykorzystane do utworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="44a4e-105">The USMF demo company was used to create this procedure.</span></span> <span data-ttu-id="44a4e-106">Procedura dotyczy funkcji Rachunek kosztów dodanej w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="44a4e-106">This procedure is for a Cost accounting feature that was added in Dynamics 365 for Operations, version 1611.</span></span>


## <a name="create-new-cost-objects"></a><span data-ttu-id="44a4e-107">Tworzenie nowych obiektów kosztów</span><span class="sxs-lookup"><span data-stu-id="44a4e-107">Create new cost objects</span></span>
1. <span data-ttu-id="44a4e-108">Wybierz kolejno opcje Rachunek kosztów > Wymiary > Wymiary obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="44a4e-108">Go to Cost accounting > Dimensions > Cost object dimensions.</span></span>
2. <span data-ttu-id="44a4e-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="44a4e-109">Click New.</span></span>
3. <span data-ttu-id="44a4e-110">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="44a4e-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="44a4e-111">W polu Łącznik danych dla elementów członkowskich wymiarów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="44a4e-111">In the Data connector for dimension members field, enter or select a value.</span></span>
5. <span data-ttu-id="44a4e-112">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="44a4e-112">In the Description field, type a value.</span></span>
6. <span data-ttu-id="44a4e-113">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="44a4e-113">Click Save.</span></span>

## <a name="configure-the-data-connector"></a><span data-ttu-id="44a4e-114">Konfigurowanie łącznika danych</span><span class="sxs-lookup"><span data-stu-id="44a4e-114">Configure the data connector</span></span>
1. <span data-ttu-id="44a4e-115">Kliknij opcję Konfiguruj dostawcę elementów członkowskich wymiarów.</span><span class="sxs-lookup"><span data-stu-id="44a4e-115">Click Configure dimension member provider.</span></span>
    * <span data-ttu-id="44a4e-116">Wybierz centrum kosztu, aby zaimportować jego wymiar do modułu Rachunek kosztów.</span><span class="sxs-lookup"><span data-stu-id="44a4e-116">Select CostCenter to import the CostCenter dimension into Cost accounting.</span></span>  
2. <span data-ttu-id="44a4e-117">W polu Nazwa wymiaru wybierz wartość Centrum kosztu.</span><span class="sxs-lookup"><span data-stu-id="44a4e-117">In the Dimension name field, select Cost center.</span></span>
3. <span data-ttu-id="44a4e-118">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="44a4e-118">Click OK.</span></span>

## <a name="import-cost-centers"></a><span data-ttu-id="44a4e-119">Importowanie centrów kosztów</span><span class="sxs-lookup"><span data-stu-id="44a4e-119">Import cost centers</span></span>
1. <span data-ttu-id="44a4e-120">Kliknij opcję Importuj elementy członkowskie wymiaru.</span><span class="sxs-lookup"><span data-stu-id="44a4e-120">Click Import dimension members.</span></span>
2. <span data-ttu-id="44a4e-121">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="44a4e-121">Click OK.</span></span>

## <a name="view-the-imported-cost-centers"></a><span data-ttu-id="44a4e-122">Wyświetlanie zaimportowanych centrów kosztów</span><span class="sxs-lookup"><span data-stu-id="44a4e-122">View the imported cost centers</span></span>
1. <span data-ttu-id="44a4e-123">Kliknij opcję Wyświetl elementy członkowskie wymiaru.</span><span class="sxs-lookup"><span data-stu-id="44a4e-123">Click View dimension members.</span></span>

