---
title: Szukanie dostawców
description: Naucz się wyszukiwać dostawców na podstawie określonych kryteriów.
author: mkirknel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendSearchCriterion, VendSearchAddCategory
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dda8cfa55809ebeeda695d02ed5f99e493325c3b
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3207595"
---
# <a name="search-for-vendors"></a><span data-ttu-id="205ee-103">Szukanie dostawców</span><span class="sxs-lookup"><span data-stu-id="205ee-103">Search for vendors</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="205ee-104">Naucz się wyszukiwać dostawców na podstawie określonych kryteriów.</span><span class="sxs-lookup"><span data-stu-id="205ee-104">Learn how to search for vendors based on specific criteria.</span></span> <span data-ttu-id="205ee-105">W tym przykładzie przedstawiono sposób wyszukiwania dostawców, którzy są zatwierdzeni dla określonej kategorii zaopatrzenia i mają adres podstawowy w określonym kraju.</span><span class="sxs-lookup"><span data-stu-id="205ee-105">This example shows you how to search for vendors that are approved for a particular procurement category and have their primary address in a specific country.</span></span> <span data-ttu-id="205ee-106">Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="205ee-106">You can run this procedure in demo data company USMF, or on your own data.</span></span> <span data-ttu-id="205ee-107">To zadanie jest zazwyczaj wykonywane przez pracownika działu zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="205ee-107">This task would usually be carried out by a procurement professional.</span></span>

1. <span data-ttu-id="205ee-108">Wybierz kolejno opcje Zaopatrzenie i sourcing > Dostawcy > Wyszukiwanie dostawcy.</span><span class="sxs-lookup"><span data-stu-id="205ee-108">Go to Procurement and sourcing > Vendors > Vendor search.</span></span>
2. <span data-ttu-id="205ee-109">Kliknij ikonę plusa, aby otworzyć stronę Wybór kategorii zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="205ee-109">Click on the Plus icon to open the Procurement category selection page.</span></span>  
3. <span data-ttu-id="205ee-110">W drzewie zaznacz element „CORP PROCUREMENT CATEGORIES\OFFICE MACHINES”.</span><span class="sxs-lookup"><span data-stu-id="205ee-110">In the tree, select 'CORP PROCUREMENT CATEGORIES\OFFICE MACHINES'.</span></span>
    * <span data-ttu-id="205ee-111">Jeśli wykonujesz procedurę w przewodniku po zadaniach, przed wybraniem właściwego węzła może być konieczne kliknięcie ikony odblokowania.</span><span class="sxs-lookup"><span data-stu-id="205ee-111">If you're running this procedure as a task guide, you may have to click the Unlock button before you can select the correct node.</span></span> <span data-ttu-id="205ee-112">Jeśli nie używasz firmy USMF, wybierz jedną z posiadanych kategorii.</span><span class="sxs-lookup"><span data-stu-id="205ee-112">If you're not using USMF, select one of the categories that you have.</span></span>  
4. <span data-ttu-id="205ee-113">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="205ee-113">Click Add.</span></span>
    * <span data-ttu-id="205ee-114">W tym miejscu można wybrać więcej niż jedną kategorię.</span><span class="sxs-lookup"><span data-stu-id="205ee-114">It's possible to select more than one category here.</span></span> <span data-ttu-id="205ee-115">Jeśli tak zrobisz, wyszukiwanie znajdzie wszystkich dostawców, którzy zostali zatwierdzeni dla co najmniej jednej kategorii.</span><span class="sxs-lookup"><span data-stu-id="205ee-115">If you do so, the search will find all the vendors that are approved for at least one of the categories.</span></span>  
5. <span data-ttu-id="205ee-116">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="205ee-116">Click OK.</span></span>
6. <span data-ttu-id="205ee-117">W polu Kraj/region wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="205ee-117">In the Country/region field, type a value.</span></span>
7. <span data-ttu-id="205ee-118">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="205ee-118">Click OK.</span></span>

