---
title: Ustawianie grup środków trwałych
description: W tym temacie pokazano sposób tworzenia nowej grupy środków trwałych.
author: saraschi2
manager: AnnBe
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetGroup, AssetGroupBookSetup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4eead36e1274194b151b230767a4d6385173b12f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994847"
---
# <a name="set-up-fixed-asset-groups"></a><span data-ttu-id="20e8d-103">Ustawianie grup środków trwałych</span><span class="sxs-lookup"><span data-stu-id="20e8d-103">Set up fixed asset groups</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="20e8d-104">W tym temacie pokazano sposób tworzenia nowej grupy środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="20e8d-104">This topic explains how to create a new fixed asset group.</span></span> <span data-ttu-id="20e8d-105">Przewodnik korzysta z roli Księgowy i danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="20e8d-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="20e8d-106">W okienku nawigacji przejdź do **Moduły > Środki trwałe > Ustawienia > Grupy środków trwałych**.</span><span class="sxs-lookup"><span data-stu-id="20e8d-106">In the navigation pane, go to **Modules > Fixed assets > Setup > Fixed asset groups**.</span></span>
2. <span data-ttu-id="20e8d-107">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="20e8d-107">Select **New**.</span></span>
3. <span data-ttu-id="20e8d-108">W polu **Grupa środków trwałych** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="20e8d-108">In the **Fixed asset group** field, type a value.</span></span>
4. <span data-ttu-id="20e8d-109">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="20e8d-109">In the **Name** field, type a value.</span></span> <span data-ttu-id="20e8d-110">Ustawienia Automatyczna numeracja środków trwałych i Kod sekwencji numerów w oknie Grupa **środków trwałych** zastąpią ustawienia w oknie Parametry środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="20e8d-110">Autonumber fixed assets and Number sequence code on the **Fixed asset** group will override the settings on the Fixed assets parameters.</span></span> <span data-ttu-id="20e8d-111">Można zmienić to w tym oknie, jeśli składniki aktywów z tej grupy środków trwałych będą miały inną numerację niż pozostałe grupy.</span><span class="sxs-lookup"><span data-stu-id="20e8d-111">You can change it here if the assets in this fixed asset group will have different numbering from other groups.</span></span>  
5. <span data-ttu-id="20e8d-112">Wybierz **Księgi**.</span><span class="sxs-lookup"><span data-stu-id="20e8d-112">Select **Books**.</span></span>
6. <span data-ttu-id="20e8d-113">Wprowadź lub wybierz wartość w polu **Księga**.</span><span class="sxs-lookup"><span data-stu-id="20e8d-113">In the **Book** field, enter or select a value.</span></span> <span data-ttu-id="20e8d-114">Pole **Oblicz amortyzację** ma zaznaczoną opcję **Tak**, dlatego ewidencja składników majątku będzie uwzględniana w propozycjach amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="20e8d-114">The **Calculate depreciation** field is set to **Yes**, so the asset book will be included in depreciation proposals.</span></span> <span data-ttu-id="20e8d-115">Jeśli ustawienie **Oblicz amortyzację** ma wartość **Nie**, składnik majątku nie będzie automatycznie amortyzowany.</span><span class="sxs-lookup"><span data-stu-id="20e8d-115">If **Calculate depreciation** is set to **No**, the asset will not be automatically depreciated.</span></span>  
7. <span data-ttu-id="20e8d-116">Ustaw okres użytkowania składnika aktywów w latach.</span><span class="sxs-lookup"><span data-stu-id="20e8d-116">Set the Service life of the asset, in years.</span></span> <span data-ttu-id="20e8d-117">Należy zauważyć, że wartość pola **Okresy amortyzacji** jest obliczana po ustawieniu okresu użytkowania.</span><span class="sxs-lookup"><span data-stu-id="20e8d-117">Note that the **Depreciation periods** field value is calculated after setting the Service life.</span></span>  
8. <span data-ttu-id="20e8d-118">W polu **Konwencja amortyzacji** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="20e8d-118">In the **Depreciation convention** field, select an option.</span></span>
9. <span data-ttu-id="20e8d-119">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="20e8d-119">Close the page.</span></span>

