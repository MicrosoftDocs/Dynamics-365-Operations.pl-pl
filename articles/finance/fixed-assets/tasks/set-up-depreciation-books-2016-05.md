---
title: Konfigurowanie ksiąg amortyzacji
description: Ta procedura prowadzi proces tworzenia nowej księgi amortyzacji i kojarzy ją z grupą środków trwałych.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepBookTable, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cd65cb77872b3e2f74402cf8c92c8b8989cea6ee
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5224700"
---
# <a name="set-up-depreciation-books"></a><span data-ttu-id="8588d-103">Konfigurowanie ksiąg amortyzacji</span><span class="sxs-lookup"><span data-stu-id="8588d-103">Set up depreciation books</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8588d-104">Ta procedura prowadzi proces tworzenia nowej księgi amortyzacji i kojarzy ją z grupą środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="8588d-104">This procedure walks through the process of creating a new depreciation book and associate it with a fixed asset group.</span></span> 

## <a name="create-a-depreciation-book"></a><span data-ttu-id="8588d-105">Tworzenie księgi amortyzacji</span><span class="sxs-lookup"><span data-stu-id="8588d-105">Create a depreciation book</span></span>
1. <span data-ttu-id="8588d-106">Wybierz kolejno opcje Środki trwałe > Ustawienia > Księgi amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="8588d-106">Go to Fixed assets > Setup > Depreciation books.</span></span>
2. <span data-ttu-id="8588d-107">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="8588d-107">Click New.</span></span>
3. <span data-ttu-id="8588d-108">W polu Księga amortyzacji wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="8588d-108">In the Depreciation book field, type a value.</span></span>
4. <span data-ttu-id="8588d-109">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="8588d-109">In the Description field, type a value.</span></span>
5. <span data-ttu-id="8588d-110">Zaznacz pole wyboru Oblicz amortyzację lub usuń jego zaznaczenie.</span><span class="sxs-lookup"><span data-stu-id="8588d-110">Check or uncheck the Calculate depreciation checkbox.</span></span>
6. <span data-ttu-id="8588d-111">W polu Profil amortyzacji kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="8588d-111">In the Depreciation profile field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="8588d-112">Na liście znajdź i zaznacz odpowiedni profil amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="8588d-112">In the list, find and select the desired depreciation profile.</span></span>
8. <span data-ttu-id="8588d-113">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="8588d-113">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="8588d-114">W polu Amortyzacja alternatywna kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="8588d-114">In the Alternative depreciation profile field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="8588d-115">Na liście zaznacz odpowiedni profil amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="8588d-115">In the list, select the desired depreciation profile.</span></span>
11. <span data-ttu-id="8588d-116">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="8588d-116">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="8588d-117">Profil Amortyzacja dodatkowa będzie używany na potrzeby dodatkowej amortyzacji składnika aktywów w nadzwyczajnych okolicznościach.</span><span class="sxs-lookup"><span data-stu-id="8588d-117">The Extraordinary depreciation profile is used for additional depreciation of an asset in unusual circumstances.</span></span> <span data-ttu-id="8588d-118">Na przykład może to służy do zarejestrowania amortyzacji powstałej w wyniku klęski żywiołowej.</span><span class="sxs-lookup"><span data-stu-id="8588d-118">For example, you might use this to record depreciation that results from a natural disaster.</span></span>  
12. <span data-ttu-id="8588d-119">Zaznacz lub wyczyść pole wyboru Tworzenie korekt amortyzacji przy korektach podstawy.</span><span class="sxs-lookup"><span data-stu-id="8588d-119">Check or uncheck the Create depreciation adjustments with basis adjustments checkbox.</span></span>
13. <span data-ttu-id="8588d-120">W polu Kalendarz kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="8588d-120">In the Calendar field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="8588d-121">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="8588d-121">In the list, click the link in the selected row.</span></span>

## <a name="associate-the-depreciation-book-with-a-fixed-asset-group"></a><span data-ttu-id="8588d-122">Kojarzenie księgi amortyzacji z grupą środków trwałych</span><span class="sxs-lookup"><span data-stu-id="8588d-122">Associate the depreciation book with a fixed asset group</span></span>
1. <span data-ttu-id="8588d-123">Kliknij opcję Grupy środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="8588d-123">Click Fixed asset groups.</span></span>
2. <span data-ttu-id="8588d-124">W polu Grupa środków trwałych kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="8588d-124">In the Fixed asset group field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="8588d-125">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="8588d-125">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="8588d-126">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="8588d-126">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="8588d-127">W polu Konwencja amortyzacji wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="8588d-127">In the Depreciation convention field, select an option.</span></span>
6. <span data-ttu-id="8588d-128">W polu Okres użytkowania wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="8588d-128">In the Service life field, enter a number.</span></span>
    * <span data-ttu-id="8588d-129">Należy zauważyć, że wartość pola Okresy amortyzacji jest obliczana po ustawieniu okresu użytkowania.</span><span class="sxs-lookup"><span data-stu-id="8588d-129">Notice the Depreciation periods field value is calculated after setting the Service life.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]