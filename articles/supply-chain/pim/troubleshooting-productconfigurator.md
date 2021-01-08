---
title: Rozwiązywanie problemów z konfiguratorem produktów
description: W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z konfiguratorem produktów.
author: SmithaNataraj
manager: tfehr
ms.date: 11/04/2020
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
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: dacc7205eaf2084f6fbd3be9d8ac0572f9e1bcde
ms.sourcegitcommit: 8eefb4e14ae0ea27769ab2cecca747755560efa3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2020
ms.locfileid: "4516855"
---
# <a name="troubleshoot-the-product-configurator"></a><span data-ttu-id="5d5ad-103">Rozwiązywanie problemów z konfiguratorem produktów</span><span class="sxs-lookup"><span data-stu-id="5d5ad-103">Troubleshoot the product configurator</span></span>

<span data-ttu-id="5d5ad-104">W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z konfiguratorem produktów.</span><span class="sxs-lookup"><span data-stu-id="5d5ad-104">This topic describes how to fix issues that you might encounter while you work with the product configurator.</span></span>

## <a name="item-text-is-overwritten-when-i-configure-a-product-on-a-sales-order-line"></a><span data-ttu-id="5d5ad-105">Podczas konfigurowania produktu w wierszu zamówienia sprzedaży tekst towaru jest zastępowany.</span><span class="sxs-lookup"><span data-stu-id="5d5ad-105">Item text is overwritten when I configure a product on a sales order line.</span></span>

### <a name="issue-description"></a><span data-ttu-id="5d5ad-106">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="5d5ad-106">Issue description</span></span>

<span data-ttu-id="5d5ad-107">Ten problem występuje podczas tworzenia wiersza zamówienia sprzedaży dla towaru konfigurowalnego, a następnie modyfikowania tekstu towaru.</span><span class="sxs-lookup"><span data-stu-id="5d5ad-107">This issue occurs when you create a sales order line for a configurable item and then modify the item text.</span></span> <span data-ttu-id="5d5ad-108">Po skonfigurowaniu towaru i wybraniu opcji **OK** tekst jest zastępowany tekstem standardowym.</span><span class="sxs-lookup"><span data-stu-id="5d5ad-108">When you configure the item and then select **OK**, the text is overwritten with the standard text.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="5d5ad-109">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="5d5ad-109">Issue resolution</span></span>

<span data-ttu-id="5d5ad-110">To zachowanie jest oczekiwane.</span><span class="sxs-lookup"><span data-stu-id="5d5ad-110">This behavior is expected.</span></span> <span data-ttu-id="5d5ad-111">Pole tekstowe zawiera nazwę wariantu, która jest wypełniana tylko po skonfigurowaniu wiersza.</span><span class="sxs-lookup"><span data-stu-id="5d5ad-111">The text field includes the variant name, which is filled in only after you configure the line.</span></span> <span data-ttu-id="5d5ad-112">Dlatego należy zmienić tekst po skonfigurowaniu wiersza, a nie przed.</span><span class="sxs-lookup"><span data-stu-id="5d5ad-112">Therefore, you must change the text after you've configured the line, not before.</span></span>

## <a name="integer-attributes-are-incorrectly-rounded-when-product-configuration-models-are-calculated"></a><span data-ttu-id="5d5ad-113">Atrybuty liczb całkowitych są niepoprawnie zaokrąglane w przypadku obliczania modeli konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="5d5ad-113">Integer attributes are incorrectly rounded when product configuration models are calculated.</span></span>

### <a name="issue-description"></a><span data-ttu-id="5d5ad-114">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="5d5ad-114">Issue description</span></span>

<span data-ttu-id="5d5ad-115">Ten problem może wystąpić w przypadku wykonywania następującej serii akcji:</span><span class="sxs-lookup"><span data-stu-id="5d5ad-115">This issue can occur when you perform the following series of actions:</span></span>

1. <span data-ttu-id="5d5ad-116">Ustaw następujące atrybuty w modelu konfiguracji produkcji:</span><span class="sxs-lookup"><span data-stu-id="5d5ad-116">Set up the following attributes on a production configuration model:</span></span>

    - <span data-ttu-id="5d5ad-117">Dane wejściowe (liczba całkowita)</span><span class="sxs-lookup"><span data-stu-id="5d5ad-117">Input (integer)</span></span>
    - <span data-ttu-id="5d5ad-118">Procent (dziesiętny)</span><span class="sxs-lookup"><span data-stu-id="5d5ad-118">Percent (decimal)</span></span>
    - <span data-ttu-id="5d5ad-119">Wynik (liczba całkowita)</span><span class="sxs-lookup"><span data-stu-id="5d5ad-119">Result (integer)</span></span>

2. <span data-ttu-id="5d5ad-120">Utwórz obliczanie z następującymi wyrażeniami:</span><span class="sxs-lookup"><span data-stu-id="5d5ad-120">Create a calculation that has the following expression:</span></span>

    <span data-ttu-id="5d5ad-121">*Wynik* = *Dane wejściowe* × *Procent* ÷ 100</span><span class="sxs-lookup"><span data-stu-id="5d5ad-121">*Result* = *Input* × *Percent* ÷ 100</span></span>

<span data-ttu-id="5d5ad-122">W tym przypadku wynik liczby całkowitej nie zawsze jest poprawnie zaokrąglony.</span><span class="sxs-lookup"><span data-stu-id="5d5ad-122">In this case, the integer result isn't always correctly rounded.</span></span> <span data-ttu-id="5d5ad-123">Na przykład wartość wejściowa to 1000, a wartością procentową jest 2,40.</span><span class="sxs-lookup"><span data-stu-id="5d5ad-123">For example, the input is 1,000, and the percentage is 2.40.</span></span> <span data-ttu-id="5d5ad-124">Dlatego oczekiwana liczba całkowita to 24, ponieważ 2,40 procent z 1000 wynosi 24 (lub 24,00 w postaci dziesiętnej).</span><span class="sxs-lookup"><span data-stu-id="5d5ad-124">Therefore, you expect the integer result to be 24, because 2.40 percent of 1,000 is 24 (or 24.00 in decimal form).</span></span> <span data-ttu-id="5d5ad-125">Zamiast tego wynik jest pokazywany jako 23.</span><span class="sxs-lookup"><span data-stu-id="5d5ad-125">Instead, the result is shown as 23.</span></span> <span data-ttu-id="5d5ad-126">Jeśli jednak wartość procentowa wynosi 2,39, obliczenia są zaokrąglane do 24 zamiast 23.</span><span class="sxs-lookup"><span data-stu-id="5d5ad-126">However, when the percentage is 2.39, the calculation is rounded to 24 instead of 23.</span></span> <span data-ttu-id="5d5ad-127">Gdy wartość procentowa wynosi 2,50, obliczenia są zaokrąglane do 25, zgodnie z oczekiwaniami.</span><span class="sxs-lookup"><span data-stu-id="5d5ad-127">When the percentage is 2.50, the calculation is rounded to 25, as expected.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="5d5ad-128">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="5d5ad-128">Issue resolution</span></span>

<span data-ttu-id="5d5ad-129">Ten problem występuje ze względu na sposób, w jaki Microsoft Solver Foundation wewnętrznie reprezentuje liczby przy użyciu ułamków.</span><span class="sxs-lookup"><span data-stu-id="5d5ad-129">This issue occurs because of the way that Microsoft Solver Foundation internally represents numbers by using fractions.</span></span> <span data-ttu-id="5d5ad-130">W przypadku poprzedniego przykładu wynik obliczeń w przypadku, gdy procent wynosi 2,40, jest reprezentowany jako 27021597764222975 ÷ 1125899906842624 = 23,99999999999999911182158029987476766109466552734375.</span><span class="sxs-lookup"><span data-stu-id="5d5ad-130">For the preceding example, the result of the calculation where the percentage is 2.40 is represented as 27021597764222975 ÷ 1125899906842624 = 23.99999999999999911182158029987476766109466552734375.</span></span> <span data-ttu-id="5d5ad-131">Gdy platforma .NET rzutuje tę wartość na liczbę całkowitą, zwróci wartość 23.</span><span class="sxs-lookup"><span data-stu-id="5d5ad-131">When .NET casts this value as an integer, it will return 23.</span></span>

<span data-ttu-id="5d5ad-132">To zachowanie nie zostanie zmienione, ponieważ zależą od niego inne scenariusze.</span><span class="sxs-lookup"><span data-stu-id="5d5ad-132">This behavior won't be changed, because other scenarios depend on it.</span></span> <span data-ttu-id="5d5ad-133">W powyższym przykładzie można rozwiązać ten problem, wprowadzając dodatkowy atrybut dziesiętny i obliczenie.</span><span class="sxs-lookup"><span data-stu-id="5d5ad-133">For the preceding example, you can fix the issue by introducing an additional decimal attribute and a calculation.</span></span>

<span data-ttu-id="5d5ad-134">Na przykład można ustawić następujące atrybuty w modelu konfiguracji produkcji:</span><span class="sxs-lookup"><span data-stu-id="5d5ad-134">For example, you can set up the following attributes on a production configuration model:</span></span>

- <span data-ttu-id="5d5ad-135">Dane wejściowe (liczba całkowita)</span><span class="sxs-lookup"><span data-stu-id="5d5ad-135">Input (integer)</span></span>
- <span data-ttu-id="5d5ad-136">Procent (dziesiętny)</span><span class="sxs-lookup"><span data-stu-id="5d5ad-136">Percent (decimal)</span></span>
- <span data-ttu-id="5d5ad-137">ResultDecimal (liczba dziesiętna)</span><span class="sxs-lookup"><span data-stu-id="5d5ad-137">ResultDecimal (decimal)</span></span>
- <span data-ttu-id="5d5ad-138">ResultInteger (liczba całkowita)</span><span class="sxs-lookup"><span data-stu-id="5d5ad-138">ResultInteger (integer)</span></span>

<span data-ttu-id="5d5ad-139">Można dodać następujące obliczenia:</span><span class="sxs-lookup"><span data-stu-id="5d5ad-139">You can then add the following calculations:</span></span>

- <span data-ttu-id="5d5ad-140">*ResultDecimal* = *Dane wejściowe* × *Procent* ÷ 100</span><span class="sxs-lookup"><span data-stu-id="5d5ad-140">*ResultDecimal* = *Input* × *Percent* ÷ 100</span></span>
- <span data-ttu-id="5d5ad-141">*ResultInteger* = *ResultDecimal*</span><span class="sxs-lookup"><span data-stu-id="5d5ad-141">*ResultInteger* = *ResultDecimal*</span></span>
