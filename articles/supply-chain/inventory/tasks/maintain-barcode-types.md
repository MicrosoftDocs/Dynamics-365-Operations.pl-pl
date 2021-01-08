---
title: Obsługa typów kodów kreskowych
description: W tej procedurze pokazano sposób konfigurowania nowej definicji kodu kreskowego, która następnie może służyć jako część raportu listy pobrania.
author: perlynne
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BarcodeSetup, InventParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 979726a1d094146b546bbc6d31963367de2c59f5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435482"
---
# <a name="maintain-barcode-types"></a><span data-ttu-id="09386-103">Obsługa typów kodów kreskowych</span><span class="sxs-lookup"><span data-stu-id="09386-103">Maintain barcode types</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="09386-104">W tej procedurze pokazano sposób konfigurowania nowej definicji kodu kreskowego, która następnie może służyć jako część raportu listy pobrania.</span><span class="sxs-lookup"><span data-stu-id="09386-104">This procedure shows you how to set up a new barcode definition which can then be used as part of the picking list report.</span></span> <span data-ttu-id="09386-105">Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="09386-105">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="09386-106">Jeśli używasz firmy USMF, można wybrać wyświetlone przykładowe wartości.</span><span class="sxs-lookup"><span data-stu-id="09386-106">If you are using USMF you can use the example values that are shown.</span></span> <span data-ttu-id="09386-107">Te zadania zazwyczaj wykonuje kierownik magazynu.</span><span class="sxs-lookup"><span data-stu-id="09386-107">These tasks would typically be carried out by a warehouse manager.</span></span>

1. <span data-ttu-id="09386-108">Przejdź do okna Kody kreskowe.</span><span class="sxs-lookup"><span data-stu-id="09386-108">Go to Bar codes.</span></span>
2. <span data-ttu-id="09386-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="09386-109">Click New.</span></span>
3. <span data-ttu-id="09386-110">W polu Konfiguracja kodów kreskowych wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="09386-110">In the Barcode setup field, type a value.</span></span>
4. <span data-ttu-id="09386-111">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="09386-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="09386-112">W polu Typ kodu kreskowego wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="09386-112">In the Bar code type field, select an option.</span></span>
    * <span data-ttu-id="09386-113">Jeśli używasz firmy demonstracyjnej USMF, można wybrać opcję „Kod 39”.</span><span class="sxs-lookup"><span data-stu-id="09386-113">If you're using USMF, you can select 'Code 39'.</span></span>  
6. <span data-ttu-id="09386-114">W polu Rozmiar wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="09386-114">In the Size field, enter a number.</span></span>
7. <span data-ttu-id="09386-115">W polu Długość maksymalna wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="09386-115">In the Maximum length field, enter a number.</span></span>
8. <span data-ttu-id="09386-116">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="09386-116">Click Save.</span></span>
9. <span data-ttu-id="09386-117">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="09386-117">Close the page.</span></span>
10. <span data-ttu-id="09386-118">Przejdź do okna Parametry modułu Zarządzanie zapasami i magazynem.</span><span class="sxs-lookup"><span data-stu-id="09386-118">Go to Inventory and warehouse management parameters.</span></span>
11. <span data-ttu-id="09386-119">W polu Konfiguracja kodów kreskowych wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="09386-119">In the Barcode setup field, enter or select a value.</span></span>
    * <span data-ttu-id="09386-120">Wybierz utworzoną wcześniej konfigurację kodu kreskowego, ale pamiętaj, że format kodu kreskowego musi być zgodny z formatem unikatowego identyfikatora typu rekordu używanego w procesie.</span><span class="sxs-lookup"><span data-stu-id="09386-120">Select the barcode setup that you created before, but be aware that the bar code format must match the format of the unique identifier for the record type used in the process.</span></span> <span data-ttu-id="09386-121">Na przykład dla marszrut pobrania format kodu kreskowego musi być zgodny z formatem odwołania do marszruty pobrania, który jest zazwyczaj sekwencją numeracji.</span><span class="sxs-lookup"><span data-stu-id="09386-121">For example, for picking routes, the bar code format should match the format of the picking route reference, which is typically a number sequence.</span></span>  
12. <span data-ttu-id="09386-122">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="09386-122">Click Save.</span></span>
13. <span data-ttu-id="09386-123">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="09386-123">Close the page.</span></span>

