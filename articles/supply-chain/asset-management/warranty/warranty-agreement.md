---
title: Umowy gwarancyjne
description: W tym temacie opisano umowy gwarancyjne w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 08/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f049165fd12dfae672293e0c30ddb186ad3ed12c
ms.sourcegitcommit: 18c5ef10e311f3dd2dbf45c6439ae6beff921af8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/24/2020
ms.locfileid: "3719245"
---
# <a name="warranty-agreements"></a><span data-ttu-id="7653f-103">Umowy gwarancyjne</span><span class="sxs-lookup"><span data-stu-id="7653f-103">Warranty agreements</span></span>

[!include [banner](../../includes/banner.md)]

 


<span data-ttu-id="7653f-104">W module Zarządzanie składnikami majątku można skonfigurować warunki gwarancji, które mogą być połączone z składnikiem majątku lub typem składnika.</span><span class="sxs-lookup"><span data-stu-id="7653f-104">In Asset Management, you can set up warranty terms that can be connected to an asset or an asset type.</span></span> <span data-ttu-id="7653f-105">Warunki gwarancji są tworzone dla konkretnego okresu.</span><span class="sxs-lookup"><span data-stu-id="7653f-105">Warranty terms are created for a specific period.</span></span> <span data-ttu-id="7653f-106">Gwarancję można skonfigurować w taki sposób, aby zapewnić pełne pokrycie lub częściowe pokrycie, i można skonfigurować terminy związane z godzinami, wydatkami i towarami.</span><span class="sxs-lookup"><span data-stu-id="7653f-106">Warranty can be set up to provide full coverage or partial coverage, and you can set up terms that are related to hours, expenses, and items.</span></span>

<span data-ttu-id="7653f-107">Pierwszym krokiem jest utworzenie wszelkich umów gwarancyjnych od dostawców, które dysponujesz dla danego sprzętu.</span><span class="sxs-lookup"><span data-stu-id="7653f-107">The first step is to create any vendor warranty agreements that you have for your equipment.</span></span> <span data-ttu-id="7653f-108">Następnie można dołączać umowy gwarancyjne do składników majątku lub typów składników majątku.</span><span class="sxs-lookup"><span data-stu-id="7653f-108">You then attach warranty agreements to assets or asset types.</span></span> <span data-ttu-id="7653f-109">Umowy gwarancyjne dotyczące dostawców są używane tylko do celów informacyjnych.</span><span class="sxs-lookup"><span data-stu-id="7653f-109">Vendor warranty agreements are used only for informational purposes.</span></span> <span data-ttu-id="7653f-110">Jeśli dla składnika majątku jest ustawiona gwarancja dostawcy, w tym polu można wyświetlić okres pokrycia gwarancji.</span><span class="sxs-lookup"><span data-stu-id="7653f-110">If vendor warranty is set up on an asset, you can see the warranty coverage period on the asset.</span></span>

## <a name="create-a-warranty-agreement"></a><span data-ttu-id="7653f-111">Tworzenie umowy gwarancyjnej</span><span class="sxs-lookup"><span data-stu-id="7653f-111">Create a warranty agreement</span></span>

<span data-ttu-id="7653f-112">Umowa gwarancyjna może zawierać kilka wierszy umowy w celu pokrycia gwarancji na godziny pracy, wydatki i towary.</span><span class="sxs-lookup"><span data-stu-id="7653f-112">A warranty agreement can include several agreement lines to cover the warranty for work hours, expenses, and items.</span></span>

1. <span data-ttu-id="7653f-113">Wybierz kolejno **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Składniki majatku** \> **Gwarancje**.</span><span class="sxs-lookup"><span data-stu-id="7653f-113">Select **Asset management** \> **Setup** \> **Assets** \> **Warranty**.</span></span>
2. <span data-ttu-id="7653f-114">Wybierz **Nowa**, aby utworzyć produkt.</span><span class="sxs-lookup"><span data-stu-id="7653f-114">Select **New** to create a product.</span></span>
3. <span data-ttu-id="7653f-115">W polu **Gwarancja** wpisz identyfikator gwarancji.</span><span class="sxs-lookup"><span data-stu-id="7653f-115">In the **Warranty** field, enter a warranty ID.</span></span> 
4. <span data-ttu-id="7653f-116">W polu **Nazwa** wprowadź opis.</span><span class="sxs-lookup"><span data-stu-id="7653f-116">In the **Name** field, enter a description.</span></span>

    <span data-ttu-id="7653f-117">Na skróconej karcie **Szczegóły** pole **Składniki majątku** zawiera liczbę aktywnych składników, które korzystają z umowy gwarancyjnej.</span><span class="sxs-lookup"><span data-stu-id="7653f-117">On the **Details** FastTab, the **Assets** field shows the number of active assets that use the warranty agreement.</span></span>

5. <span data-ttu-id="7653f-118">Na skróconej karcie **Wiersze gwarancyjne** wykonaj następujące kroki, aby dodać wiersze, które powinny zostać uwzględnione w umowie gwarancyjnej:</span><span class="sxs-lookup"><span data-stu-id="7653f-118">On the **Warranty lines** FastTab, follow these steps to add lines that should be included in a warranty agreement:</span></span>

    1. <span data-ttu-id="7653f-119">Wybierz opcję **Dodaj wiersz**, aby dodać nowy warunek do gwarancji.</span><span class="sxs-lookup"><span data-stu-id="7653f-119">Select **Add line** to add a new condition to the warranty.</span></span> <span data-ttu-id="7653f-120">W polu **Wiersz** automatycznie jest wprowadzany następujący numer.</span><span class="sxs-lookup"><span data-stu-id="7653f-120">A sequential line number is automatically entered in the **Line** field.</span></span>
    2. <span data-ttu-id="7653f-121">W polu **Okres** wybierz częstotliwość typu gwarancji.</span><span class="sxs-lookup"><span data-stu-id="7653f-121">In the **Period** field, select the type of warranty period.</span></span>
    3. <span data-ttu-id="7653f-122">W polu **Interwał** wpisz numer.</span><span class="sxs-lookup"><span data-stu-id="7653f-122">In the **Interval** field, enter a number.</span></span> <span data-ttu-id="7653f-123">W tym polu jest określana liczba okresów obowiązywania gwarancji.</span><span class="sxs-lookup"><span data-stu-id="7653f-123">This field defines the number of periods that the warranty should be valid for.</span></span>
    4. <span data-ttu-id="7653f-124">W polu **procent** wprowadź wartość procentową pokrycia dla wiersza gwarancji.</span><span class="sxs-lookup"><span data-stu-id="7653f-124">In the **Percent** field, enter the coverage percentage for the warranty line.</span></span> <span data-ttu-id="7653f-125">Wartość procentowa wskazuje stopień pokryty przez firmę.</span><span class="sxs-lookup"><span data-stu-id="7653f-125">The percentage indicates how much is covered by your company.</span></span>

![Strona Gwarancja](media/01-warranty.png)
