---
title: Niepoprawna wartość pola w rekordzie TaxTrans
description: Ten temat zawiera informacje dotyczące rozwiązywania problemów z niepoprawnymi wartościami pola w rekordzie TaxTrans.
author: bijian
ms.date: 04/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 488ff54f1dd99208db940024a2fe8b2d25861f44
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020170"
---
# <a name="incorrect-field-value-in-taxtrans"></a><span data-ttu-id="2c97a-103">Niepoprawna wartość pola w rekordzie TaxTrans</span><span class="sxs-lookup"><span data-stu-id="2c97a-103">Incorrect field value in TaxTrans</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2c97a-104">Jeśli wartość pola w rekordzie **TaxTrans** jest niepoprawna, użyj informacji z tego tematu, aby spróbować rozwiązać ten problem.</span><span class="sxs-lookup"><span data-stu-id="2c97a-104">If a field value in **TaxTrans** is incorrect, use the information in this topic to try to resolve the issue.</span></span>

## <a name="overview-of-values"></a><span data-ttu-id="2c97a-105">Przegląd wartości</span><span class="sxs-lookup"><span data-stu-id="2c97a-105">Overview of values</span></span>
<span data-ttu-id="2c97a-106">Na poniższej liście pokazano, że zestawy danych **TaxTrans**, **TaxUncommitted** i **TmpTaxWorkTrans** są do siebie podobne, ale różnią się sposobem działania.</span><span class="sxs-lookup"><span data-stu-id="2c97a-106">The following list shows how **TaxTrans**, **TaxUncommitted**, and **TmpTaxWorkTrans** are similar data sets, but in work differently.</span></span>

  - <span data-ttu-id="2c97a-107">**TaxTrans** jest wynikiem ostatniej zaksięgowanej transakcji podatkowej utrwalonym w bazie danych.</span><span class="sxs-lookup"><span data-stu-id="2c97a-107">**TaxTrans** is the final posted tax transaction result persisted in the database.</span></span>
  - <span data-ttu-id="2c97a-108">**TaxUncommitted** to pośredni obliczony wynik podatku utrwalony w bazie danych (jeśli ma zastosowanie), który będzie używany później podczas księgowania.</span><span class="sxs-lookup"><span data-stu-id="2c97a-108">**TaxUncommitted** is the intermediate calculated tax result persisted in the database (if applicable), which will be used later in posting.</span></span>
  - <span data-ttu-id="2c97a-109">**TmpTaxWorkTrans** to tymczasowy obliczony wynik podatku w tabeli w pamięci (typ tabeli = InMemory).</span><span class="sxs-lookup"><span data-stu-id="2c97a-109">**TmpTaxWorkTrans** is the temporary calculated tax result in the in-memory table (Table Type = InMemory).</span></span>

<span data-ttu-id="2c97a-110">Znalezienie przyczyny niepoprawnej kolumny **TaxTrans** oznacza także znalezienie głównej przyczyny niepoprawnej kolumny **TaxUncommitted** lub **TmpTaxWorkTrans**.</span><span class="sxs-lookup"><span data-stu-id="2c97a-110">If you find the root cause of an incorrect **TaxTrans** column, you've also found the root cause of an incorrect **TaxUncommitted** or **TmpTaxWorkTrans** column.</span></span> <span data-ttu-id="2c97a-111">Wynika to z tego, że te trzy kolumny są z siebie kopiowane.</span><span class="sxs-lookup"><span data-stu-id="2c97a-111">This is because the three columns are copied from each other.</span></span>

<span data-ttu-id="2c97a-112">Zwykle podczas obliczania podatku jest generowany rekord **TmpTaxWorkTrans**, a następnie ewentualnie rekord **TaxUncommitted**.</span><span class="sxs-lookup"><span data-stu-id="2c97a-112">Typically, during tax calculation, **TmpTaxWorkTrans** is generated, and then, if applicable, **TaxUncommitted** is generated.</span></span> <span data-ttu-id="2c97a-113">Podczas księgowania podatku jest generowany rekord **TaxTrans**.</span><span class="sxs-lookup"><span data-stu-id="2c97a-113">During tax posting, **TaxTrans** is generated.</span></span>


## <a name="add-breakpoints"></a><span data-ttu-id="2c97a-114">Dodawanie punktów przerwania</span><span class="sxs-lookup"><span data-stu-id="2c97a-114">Add breakpoints</span></span>
<span data-ttu-id="2c97a-115">Aby dodać punkty przerwania, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="2c97a-115">To add breakpoints, complete the following steps:</span></span> 

1. <span data-ttu-id="2c97a-116">Dodaj rozszerzenia i punkty przerwania w *insert()* and *update()* w rozszerzeniach w sposób pokazany poniżej.</span><span class="sxs-lookup"><span data-stu-id="2c97a-116">Add extensions and breakpoints in *insert()* and *update()* in the extensions as shown below.</span></span>

     - <span data-ttu-id="2c97a-117">**TaxTrans**</span><span class="sxs-lookup"><span data-stu-id="2c97a-117">**TaxTrans**</span></span>

        ```x++
        [ExtensionOf(tableStr(TaxTrans))]
        public final class TaxTrans_Extension
        {
            public void insert()
            {
                next insert();
            }
        
            public void update()
            {
                next update();
            }
        
        }
        ```

     - <span data-ttu-id="2c97a-118">**TaxUncommitted**</span><span class="sxs-lookup"><span data-stu-id="2c97a-118">**TaxUncommitted**</span></span>

        ```x++
        [ExtensionOf(tableStr(TaxUncommitted))]
        public final class TaxUncommitted_Extension
        {
            public void insert()
            {
                next insert();
            }
        
            public void update()
            {
                next update();
            }
        
        }
        ```

     - <span data-ttu-id="2c97a-119">**TmpTaxWorkTrans**</span><span class="sxs-lookup"><span data-stu-id="2c97a-119">**TmpTaxWorkTrans**</span></span>

        ```x++
        [ExtensionOf(tableStr(TmpTaxWorkTrans))]
        public final class TmpTaxWorkTrans_Extension
        {
            public void insert(boolean _ignoreCalculatedSalesTax)
            {
                next insert(_ignoreCalculatedSalesTax);
            }
        
            public void update(boolean _ignoreCalculatedSalesTax)
            {
                next update(_ignoreCalculatedSalesTax);
            }
        
        }
        
        ```

2. <span data-ttu-id="2c97a-120">Możesz również dodać punkty przerwania bezpośrednio w przypadku braku rekordu **TaxUncommitted**.</span><span class="sxs-lookup"><span data-stu-id="2c97a-120">Alternatively, you can add breakpoints directly when **TaxUncommitted** is not included.</span></span>

     - <span data-ttu-id="2c97a-121">*TaxTrans.insert()*, *TaxTrans.update()*</span><span class="sxs-lookup"><span data-stu-id="2c97a-121">*TaxTrans.insert()*, *TaxTrans.update()*</span></span>
     - <span data-ttu-id="2c97a-122">*TmpTaxWorkTrans.insert()*, *TmpTaxWorkTrans.update()*</span><span class="sxs-lookup"><span data-stu-id="2c97a-122">*TmpTaxWorkTrans.insert()*, *TmpTaxWorkTrans.update()*</span></span>

## <a name="reproduce-and-debug"></a><span data-ttu-id="2c97a-123">Odtwarzanie i debugowanie</span><span class="sxs-lookup"><span data-stu-id="2c97a-123">Reproduce and debug</span></span>

<span data-ttu-id="2c97a-124">Po skonfigurowaniu punktów przerwania każda zmiana utrwalania danych jest widoczna podczas debugowania.</span><span class="sxs-lookup"><span data-stu-id="2c97a-124">After the breakpoints are set, every data persistency change is visible during debugging.</span></span> <span data-ttu-id="2c97a-125">Aby znaleźć główną przyczynę niepoprawnej kolumny **TaxTrans**, **TaxUncommitted** lub **TmpTaxWorkTrans**, zbadaj następujące warunki:</span><span class="sxs-lookup"><span data-stu-id="2c97a-125">To find the root cause of an incorrect column of **TaxTrans**, **TaxUncommitted**, or **TmpTaxWorkTrans**, review and note the following items:</span></span>

- <span data-ttu-id="2c97a-126">Ostatni punkt przerwania, w którym kolumna jest poprawna.</span><span class="sxs-lookup"><span data-stu-id="2c97a-126">The last breakpoint where the column is correct.</span></span>
- <span data-ttu-id="2c97a-127">Pierwszy punkt przerwania, w którym kolumna jest niepoprawna.</span><span class="sxs-lookup"><span data-stu-id="2c97a-127">The first breakpoint where the column is incorrect.</span></span>
- <span data-ttu-id="2c97a-128">Co się dzieje między tymi dwoma punktami.</span><span class="sxs-lookup"><span data-stu-id="2c97a-128">What happens in between those two points.</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="2c97a-129">Określanie, czy dostosowanie istnieje</span><span class="sxs-lookup"><span data-stu-id="2c97a-129">Determine whether customization exists</span></span>
<span data-ttu-id="2c97a-130">Jeśli zostały wykonane kroki w poprzednich sekcjach, ale nie rozwiązano problemu, określ, czy istnieje dostosowanie.</span><span class="sxs-lookup"><span data-stu-id="2c97a-130">If you've completed the steps in the previous sections but have not been able to resolve the issue, determine whether customization exists.</span></span> <span data-ttu-id="2c97a-131">Jeśli nie istnieją żadne dostosowania, skontaktuj się z pomocą techniczną firmy Microsoft, aby uzyskać pomoc.</span><span class="sxs-lookup"><span data-stu-id="2c97a-131">If no customization exists, contact Microsoft Support for assistance.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

