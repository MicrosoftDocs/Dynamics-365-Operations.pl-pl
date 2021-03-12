---
title: Tworzenie obiektów kosztów
description: W tej procedurze pokazano sposób tworzenia obiektów kosztów, importując wymiar finansowy centrum kosztu do modułu Rachunek kosztów za pośrednictwem łącznika danych.
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
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f3d2ef7d6549bdeb3ba2afd2a594f36b47c912db
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990774"
---
# <a name="create-cost-objects"></a><span data-ttu-id="88c39-103">Tworzenie obiektów kosztów</span><span class="sxs-lookup"><span data-stu-id="88c39-103">Create cost objects</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="88c39-104">W tej procedurze pokazano sposób tworzenia obiektów kosztów, importując wymiar finansowy centrum kosztu do modułu Rachunek kosztów za pośrednictwem łącznika danych.</span><span class="sxs-lookup"><span data-stu-id="88c39-104">This procedure shows how to create cost objects by importing the cost center financial dimension into Cost accounting via a data connector.</span></span> <span data-ttu-id="88c39-105">Dane wykorzystane do utworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="88c39-105">The USMF demo company was used to create this procedure.</span></span> 


## <a name="create-new-cost-objects"></a><span data-ttu-id="88c39-106">Tworzenie nowych obiektów kosztów</span><span class="sxs-lookup"><span data-stu-id="88c39-106">Create new cost objects</span></span>
1. <span data-ttu-id="88c39-107">Wybierz kolejno opcje Rachunek kosztów > Wymiary > Wymiary obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="88c39-107">Go to Cost accounting > Dimensions > Cost object dimensions.</span></span>
2. <span data-ttu-id="88c39-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="88c39-108">Click New.</span></span>
3. <span data-ttu-id="88c39-109">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="88c39-109">In the Name field, type a value.</span></span>
4. <span data-ttu-id="88c39-110">W polu Łącznik danych dla elementów członkowskich wymiarów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="88c39-110">In the Data connector for dimension members field, enter or select a value.</span></span>
5. <span data-ttu-id="88c39-111">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="88c39-111">In the Description field, type a value.</span></span>
6. <span data-ttu-id="88c39-112">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="88c39-112">Click Save.</span></span>

## <a name="configure-the-data-connector"></a><span data-ttu-id="88c39-113">Konfigurowanie łącznika danych</span><span class="sxs-lookup"><span data-stu-id="88c39-113">Configure the data connector</span></span>
1. <span data-ttu-id="88c39-114">Kliknij opcję Konfiguruj dostawcę elementów członkowskich wymiarów.</span><span class="sxs-lookup"><span data-stu-id="88c39-114">Click Configure dimension member provider.</span></span>
    * <span data-ttu-id="88c39-115">Wybierz centrum kosztu, aby zaimportować jego wymiar do modułu Rachunek kosztów.</span><span class="sxs-lookup"><span data-stu-id="88c39-115">Select CostCenter to import the CostCenter dimension into Cost accounting.</span></span>  
2. <span data-ttu-id="88c39-116">W polu Nazwa wymiaru wybierz wartość Centrum kosztu.</span><span class="sxs-lookup"><span data-stu-id="88c39-116">In the Dimension name field, select Cost center.</span></span>
3. <span data-ttu-id="88c39-117">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="88c39-117">Click OK.</span></span>

## <a name="import-cost-centers"></a><span data-ttu-id="88c39-118">Importowanie centrów kosztów</span><span class="sxs-lookup"><span data-stu-id="88c39-118">Import cost centers</span></span>
1. <span data-ttu-id="88c39-119">Kliknij opcję Importuj elementy członkowskie wymiaru.</span><span class="sxs-lookup"><span data-stu-id="88c39-119">Click Import dimension members.</span></span>
2. <span data-ttu-id="88c39-120">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="88c39-120">Click OK.</span></span>

## <a name="view-the-imported-cost-centers"></a><span data-ttu-id="88c39-121">Wyświetlanie zaimportowanych centrów kosztów</span><span class="sxs-lookup"><span data-stu-id="88c39-121">View the imported cost centers</span></span>
1. <span data-ttu-id="88c39-122">Kliknij opcję Wyświetl elementy członkowskie wymiaru.</span><span class="sxs-lookup"><span data-stu-id="88c39-122">Click View dimension members.</span></span>

