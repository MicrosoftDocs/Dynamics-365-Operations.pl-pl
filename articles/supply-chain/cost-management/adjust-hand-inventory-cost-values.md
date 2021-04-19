---
title: Korygowanie wartości kosztowych dostępnych zapasów
description: Na stronie Korygowanie dostępnych zapasów można skorygować wartość kosztów ilości dostępnych zapasów po wykonaniu procesu zamknięcia zapasów.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventAdjInventOnHand
audience: Application User
ms.reviewer: kamaybac
ms.custom: 53231
ms.assetid: bc1fde9f-5ad9-4339-8ae8-e2839b792eb2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9ddb2962926e78fda80a9db7b9e5915550bc5965
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842208"
---
# <a name="adjust-on-hand-inventory-cost-values"></a><span data-ttu-id="ac931-103">Korygowanie wartości kosztowych dostępnych zapasów</span><span class="sxs-lookup"><span data-stu-id="ac931-103">Adjust on-hand inventory cost values</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ac931-104">Na stronie Korygowanie dostępnych zapasów można skorygować wartość kosztów ilości dostępnych zapasów po wykonaniu procesu zamknięcia zapasów.</span><span class="sxs-lookup"><span data-stu-id="ac931-104">Use the Adjustment of on-hand inventory page to adjust the cost value of the on-hand inventory quantities after an inventory close process is run.</span></span>

<span data-ttu-id="ac931-105">Można użyć strony **Korygowanie dostępnych zapasów** do korygowania wartości kosztu dostępnych zapasów po uruchomieniu procesu zamknięcia magazynu.</span><span class="sxs-lookup"><span data-stu-id="ac931-105">You can use the **Adjustment of on-hand inventory** page to adjust the cost value of on-hand inventory quantities after an inventory close process is run.</span></span> <span data-ttu-id="ac931-106">**Uwaga:** Aby otworzyć stronę **Korygowanie dostępnych zapasów**, na stronie **Zamknięcie i korekta** wybierz rekord zakończonego procesu zamknięcia zapasów, a następnie kliknij kolejno opcje **Korekta** &gt; **Dostępne**.</span><span class="sxs-lookup"><span data-stu-id="ac931-106">**Note:** To open the **Adjustment of on-hand inventory** page, on the **Closing and adjustment** page, select the record of a completed inventory close process, and then click **Adjustment** &gt; **On-hand**.</span></span> <span data-ttu-id="ac931-107">**Przykład:** W lutym są realizowane następujące transakcje:</span><span class="sxs-lookup"><span data-stu-id="ac931-107">**Example:** You have the following transactions in February:</span></span>

-   <span data-ttu-id="ac931-108">1 lutego: magazynowy przychód finansowy o ilości 2 i koszcie 10,00 USD;</span><span class="sxs-lookup"><span data-stu-id="ac931-108">February 1: An inventory financial receipt for a quantity of 2 at a cost of USD 10.00</span></span>
-   <span data-ttu-id="ac931-109">5 lutego: magazynowy przychód finansowy o ilości 1 i koszcie 13,00 USD;</span><span class="sxs-lookup"><span data-stu-id="ac931-109">February 5: An inventory financial receipt for a quantity of 1 at a cost of USD 13.00</span></span>
-   <span data-ttu-id="ac931-110">19 lutego: finansowy rozchód z magazynu o ilości 1 i bieżącym koszcie średnim 11,00 USD.</span><span class="sxs-lookup"><span data-stu-id="ac931-110">February 19: An inventory financial issue for a quantity of 1 at a running average cost of USD 11.00</span></span>

<span data-ttu-id="ac931-111">Ten towar został skonfigurowany przy użyciu modelu zapasów FIFO (pierwsze na wejściu, pierwsze na wyjściu), a zamknięcie zapasów zostało wykonane 28 lutego.</span><span class="sxs-lookup"><span data-stu-id="ac931-111">This item was set up with the first in, first out (FIFO) inventory model, and inventory close was performed as of February 28.</span></span> <span data-ttu-id="ac931-112">Transakcja wydania finansowego o wartości 11,00 USD zostanie rozliczona względem przyjęcia finansowego z 1 lutego oraz zostanie wykonana korekta o wysokości 1,00 USD.</span><span class="sxs-lookup"><span data-stu-id="ac931-112">The financial issue transaction of USD 11.00 will be settled against the financial receipt that is dated February 1, and an adjustment of USD 1.00 will be made.</span></span> <span data-ttu-id="ac931-113">Następujące przyjęcia na magazyn będą zawierać otwarte ilości magazynowe:</span><span class="sxs-lookup"><span data-stu-id="ac931-113">The following inventory receipts will then contain open inventory quantities:</span></span>

-   <span data-ttu-id="ac931-114">1 lutego: ilość 1, koszt 10,00 USD</span><span class="sxs-lookup"><span data-stu-id="ac931-114">February 1: A quantity of 1 at a cost of USD 10.00</span></span>
-   <span data-ttu-id="ac931-115">5 lutego: ilość 1, koszt 13,00 USD</span><span class="sxs-lookup"><span data-stu-id="ac931-115">February 5: A quantity of 1 at a cost of USD 13.00</span></span>

<span data-ttu-id="ac931-116">Aby ustawić koszt tych dwóch towarów na 15,00 USD, należy skorygować otwarte ilości dostępnych zapasów w ostatnim okresie zamknięcia magazynu za pomocą opcji korekty dostępnych zapasów.</span><span class="sxs-lookup"><span data-stu-id="ac931-116">To set the cost of these two items to USD 15.00, use the on-hand adjustment option to adjust the open on-hand quantities as of the last inventory close period.</span></span> <span data-ttu-id="ac931-117">**Uwaga:** Datą księgowania transakcji korekty dostępnych zapasów będzie dzień ostatniego zamknięcia magazynu.</span><span class="sxs-lookup"><span data-stu-id="ac931-117">**Note:** The posting date of the on-hand adjustment transaction will be the date of the last inventory close.</span></span> <span data-ttu-id="ac931-118">Tego ustawienia nie można zmodyfikować.</span><span class="sxs-lookup"><span data-stu-id="ac931-118">This date can't be modified.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]