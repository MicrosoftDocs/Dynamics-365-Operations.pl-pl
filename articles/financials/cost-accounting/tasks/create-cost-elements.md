---
title: Tworzenie składników kosztu
description: Istnieje kilka sposobów tworzenia składników kosztów w module Rachunek kosztów.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension, CAMAXMainAccountDimensionMemberProviderConfiguration, CAMDimensionMember
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bbaf4f7533d51d554d838e8e9e2aa05ca451298a
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1543802"
---
# <a name="create-cost-elements"></a><span data-ttu-id="c8a16-103">Tworzenie składników kosztu</span><span class="sxs-lookup"><span data-stu-id="c8a16-103">Create cost elements</span></span> 

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c8a16-104">Istnieje kilka sposobów tworzenia składników kosztów w module Rachunek kosztów.</span><span class="sxs-lookup"><span data-stu-id="c8a16-104">There are several ways to create cost elements in Cost accounting.</span></span> <span data-ttu-id="c8a16-105">W tej procedurze pokazano, jak utworzyć składniki kosztów, importując konta główne za pośrednictwem łącznika danych.</span><span class="sxs-lookup"><span data-stu-id="c8a16-105">This procedure shows how to create cost elements by importing main accounts via a data connector.</span></span> <span data-ttu-id="c8a16-106">Dane wykorzystane do utworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="c8a16-106">The USMF demo company was used to create this procedure.</span></span> <span data-ttu-id="c8a16-107">Procedura dotyczy funkcji Rachunek kosztów dodanej w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="c8a16-107">This procedure is for a Cost accounting feature that was added in Dynamics 365 for Operations, version 1611.</span></span>


## <a name="create-new-cost-elements"></a><span data-ttu-id="c8a16-108">Tworzenie nowych składników kosztów</span><span class="sxs-lookup"><span data-stu-id="c8a16-108">Create new cost elements</span></span>
1. <span data-ttu-id="c8a16-109">Wybierz kolejno opcje Rachunek kosztów > Wymiary > Wymiary składników kosztów.</span><span class="sxs-lookup"><span data-stu-id="c8a16-109">Go to Cost accounting > Dimensions > Cost element dimensions.</span></span>
2. <span data-ttu-id="c8a16-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="c8a16-110">Click New.</span></span>
3. <span data-ttu-id="c8a16-111">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c8a16-111">In the Name field, type a value.</span></span>
4. <span data-ttu-id="c8a16-112">W polu Łącznik danych dla elementów członkowskich wymiarów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c8a16-112">In the Data connector for dimension members field, enter or select a value.</span></span>
5. <span data-ttu-id="c8a16-113">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="c8a16-113">In the Description field, type a value.</span></span>
6. <span data-ttu-id="c8a16-114">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="c8a16-114">Click Save.</span></span>

## <a name="configure-the-data-connector"></a><span data-ttu-id="c8a16-115">Konfigurowanie łącznika danych</span><span class="sxs-lookup"><span data-stu-id="c8a16-115">Configure the data connector</span></span>
1. <span data-ttu-id="c8a16-116">Kliknij opcję Konfiguruj dostawcę elementów członkowskich wymiarów.</span><span class="sxs-lookup"><span data-stu-id="c8a16-116">Click Configure dimension member provider.</span></span>
2. <span data-ttu-id="c8a16-117">W polu Plan kont wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c8a16-117">In the Chart of accounts field, enter or select a value.</span></span>
    * <span data-ttu-id="c8a16-118">Wybierz opcję Współdzielony, aby używać wspólnego planu kont.</span><span class="sxs-lookup"><span data-stu-id="c8a16-118">Select Shared to use the shared chart of accounts.</span></span>  
3. <span data-ttu-id="c8a16-119">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="c8a16-119">Click New.</span></span>
4. <span data-ttu-id="c8a16-120">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="c8a16-120">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="c8a16-121">Do kont można zastosować filtry, aby zostały spełnione żądane kryteria.</span><span class="sxs-lookup"><span data-stu-id="c8a16-121">You can apply filters to accounts to meet your criteria.</span></span>  
5. <span data-ttu-id="c8a16-122">W polu Z konta głównego wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c8a16-122">In the From main account field, enter or select a value.</span></span>
6. <span data-ttu-id="c8a16-123">W polu Do konta głównego wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c8a16-123">In the To main account field, enter or select a value.</span></span>
7. <span data-ttu-id="c8a16-124">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="c8a16-124">Click OK.</span></span>

## <a name="import-main-accounts"></a><span data-ttu-id="c8a16-125">Importuj konta główne</span><span class="sxs-lookup"><span data-stu-id="c8a16-125">Import main accounts</span></span>
1. <span data-ttu-id="c8a16-126">Kliknij opcję Importuj elementy członkowskie wymiaru.</span><span class="sxs-lookup"><span data-stu-id="c8a16-126">Click Import dimension members.</span></span>
    * <span data-ttu-id="c8a16-127">Konta główne zostaną zaimportowane do modułu Rachunek kosztów i będą używane jako składniki kosztu.</span><span class="sxs-lookup"><span data-stu-id="c8a16-127">Main accounts will be imported into Cost accounting and used as cost elements.</span></span>  
2. <span data-ttu-id="c8a16-128">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="c8a16-128">Click OK.</span></span>

## <a name="view-the-imported-accounts-as-cost-elements"></a><span data-ttu-id="c8a16-129">Wyświetlanie zaimportowanych kont jako składników kosztów</span><span class="sxs-lookup"><span data-stu-id="c8a16-129">View the imported accounts as cost elements</span></span>
1. <span data-ttu-id="c8a16-130">Kliknij opcję Wyświetl elementy członkowskie wymiaru.</span><span class="sxs-lookup"><span data-stu-id="c8a16-130">Click View dimension members.</span></span>
    * <span data-ttu-id="c8a16-131">Umożliwia wyświetlanie zaimportowanych kont księgowych jako składników kosztów w firmie, do których mogą spływać koszty.</span><span class="sxs-lookup"><span data-stu-id="c8a16-131">View the imported ledger accounts as cost elements in your business that costs can flow to.</span></span>  

