---
title: Konfigurowanie stawek indeksowanych
description: W tym temacie opisano sposób konfigurowania stawek indeksowanych. Stawki indeksowane są wymagane, jeśli w organizacji kwoty opłat z tytułu wynajmu są łączone ze zbiorem stawek indeksowanych.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: b6d201329996f23d94c0fc76a9635d3bb99c931e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5249684"
---
# <a name="set-up-index-rates"></a><span data-ttu-id="01158-104">Konfigurowanie stawek indeksowanych</span><span class="sxs-lookup"><span data-stu-id="01158-104">Set up index rates</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="01158-105">Jeśli opłaty z tytułu wynajmu są uzależnione od indeksu, typy stawek indeksowanych można dodawać i obsługiwać w systemie.</span><span class="sxs-lookup"><span data-stu-id="01158-105">If lease payments depend on an index, the index rate types can be added and maintained in the system.</span></span> <span data-ttu-id="01158-106">Aby przeszacować opłaty z tytułu wynajmu na stronie **Typ stawki indeksowanej**, proces przeszacowania stawki indeksowanej używa najnowszej stawki indeksowanej z dnia przeszacowania.</span><span class="sxs-lookup"><span data-stu-id="01158-106">To revalue the lease payments from the **Index rate type** page, the index rate revaluation process uses the most recent index rate from the date of revaluation.</span></span>

<span data-ttu-id="01158-107">Aby dodać typy stawek indeksowanych i stawki indeksowane, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="01158-107">To add index rate types and index rates, follow these steps.</span></span>

1. <span data-ttu-id="01158-108">Przejdź do **Wynajem składnika majątku \> Ustawienia \> Typ stawki indeksowanej**.</span><span class="sxs-lookup"><span data-stu-id="01158-108">Go to **Asset leasing \> Setup \> Index rate type**.</span></span>
2. <span data-ttu-id="01158-109">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="01158-109">Select **New**.</span></span>
3. <span data-ttu-id="01158-110">W odpowiednich polach wprowadź typ stawki oraz nazwę stawki indeksowanej.</span><span class="sxs-lookup"><span data-stu-id="01158-110">In the appropriate fields, enter the rate type and the name of the index rate.</span></span>
4. <span data-ttu-id="01158-111">Aby dodać nową wartość stawki indeksowanej, wybierz typ stawki indeksowanej, a następnie wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="01158-111">To add a new index rate value, select the index rate type, and then select **Add**.</span></span>
5. <span data-ttu-id="01158-112">Zaznacz datę wejścia stawki w życie, a następnie wybierz wartość stawki.</span><span class="sxs-lookup"><span data-stu-id="01158-112">Select the effective start date of the rate, and select the rate value.</span></span>

<span data-ttu-id="01158-113">Jako metodę stawki indeksowanej należy wybrać opcję **Różnica wartości stawki indeksowanej** lub **Wartość stawki indeksowanej**.</span><span class="sxs-lookup"><span data-stu-id="01158-113">You must select either **Index rate value difference** or **Index rate value** as the index rate method.</span></span>

- <span data-ttu-id="01158-114">Wybierz metodę **Różnica wartości stawki indeksowanej**, aby obliczać nową opłatę z tytułu wynajmu na podstawie różnicy między stawką indeksowaną w dniu rozpoczęcia a najbardziej aktualną stawką indeksowaną.</span><span class="sxs-lookup"><span data-stu-id="01158-114">Select the **Index rate value difference** method to calculate a new lease payment, based on the difference between the index rate on the start date and the most recent index rate.</span></span> <span data-ttu-id="01158-115">Stawkę indeksowaną ustawia się w polu **Stawka indeksowana (%)**.</span><span class="sxs-lookup"><span data-stu-id="01158-115">The index rate is defined in the **Index rate (%)** field.</span></span>
- <span data-ttu-id="01158-116">Wybierz metodę **Wartość stawki indeksowanej**, aby obliczać opłatę z tytułu wynajmu przy użyciu wartości procentowej określonej w polu **Stawka indeksowana (%)**.</span><span class="sxs-lookup"><span data-stu-id="01158-116">Select the **Index rate value** method to calculate the lease payment by using the percentage that is specified in the **Index rate (%)** field.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]