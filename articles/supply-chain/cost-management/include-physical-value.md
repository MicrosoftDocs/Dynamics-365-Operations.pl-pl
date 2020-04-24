---
title: Włącz wartość fizyczną
description: Pole wyboru Włącz wartość fizyczną na skróconej karcie Model magazynu na stronie Grupy modeli pozycji służy do określania, czy przy obliczaniu średniej kroczącej kosztu własnego towaru są uwzględniane fizycznie zaktualizowane transakcje.
author: AndersGirke
manager: tfehr
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 79033
ms.assetid: 1928c145-bf82-436d-87ca-e7a173e31923
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c6e70a40b15bf08d88958cbf3ee3e82ed63e7a48
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3201739"
---
# <a name="include-physical-value"></a><span data-ttu-id="0bcb3-103">Włącz wartość fizyczną</span><span class="sxs-lookup"><span data-stu-id="0bcb3-103">Include physical value</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0bcb3-104">Pole wyboru Włącz wartość fizyczną na skróconej karcie Model magazynu na stronie Grupy modeli pozycji służy do określania, czy przy obliczaniu średniej kroczącej kosztu własnego towaru są uwzględniane fizycznie zaktualizowane transakcje.</span><span class="sxs-lookup"><span data-stu-id="0bcb3-104">You use the Include physical value check box on the Inventory model FastTab of the Item model groups page to specify whether physically updated transactions are considered when the running average cost price is calculated for an item.</span></span>

<span data-ttu-id="0bcb3-105">Pole wyboru **Włącz wartość fizyczną** ma następujące wartości.</span><span class="sxs-lookup"><span data-stu-id="0bcb3-105">The **Include physical value** check box has the following values.</span></span>

| <span data-ttu-id="0bcb3-106">Wartość</span><span class="sxs-lookup"><span data-stu-id="0bcb3-106">Value</span></span>    | <span data-ttu-id="0bcb3-107">Wynik</span><span class="sxs-lookup"><span data-stu-id="0bcb3-107">Result</span></span>                                                                                                                          |
|----------|---------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="0bcb3-108">Wybrano</span><span class="sxs-lookup"><span data-stu-id="0bcb3-108">Selected</span></span> | <span data-ttu-id="0bcb3-109">Do obliczania średniej kroczącej kosztu własnego są używane transakcje zaktualizowane fizycznie i finansowo.</span><span class="sxs-lookup"><span data-stu-id="0bcb3-109">Both physically updated transactions and financially updated transactions are used to calculate the running average cost price.</span></span> |
| <span data-ttu-id="0bcb3-110">Zaakceptowane</span><span class="sxs-lookup"><span data-stu-id="0bcb3-110">Cleared</span></span>  | <span data-ttu-id="0bcb3-111">Do obliczania średniej kroczącej kosztu własnego są używane tylko transakcje zaktualizowane finansowo.</span><span class="sxs-lookup"><span data-stu-id="0bcb3-111">Only financially updated transactions are used to calculate the running average cost price.</span></span>                                     |

<span data-ttu-id="0bcb3-112">To pole wyboru działa nieco inaczej zależnie od wybranego modelu zapasów.</span><span class="sxs-lookup"><span data-stu-id="0bcb3-112">The check box has slightly different effects, depending on the inventory model that you use.</span></span>

-   <span data-ttu-id="0bcb3-113">Zaznaczenie pola wyboru **Włącz wartość fizyczną** w przypadku używania modelu zapasów FIFO (pierwszy na wejściu, pierwszy na wyjściu), LIFO (ostatni na wejściu, pierwszy na wyjściu) lub LIFO wg daty, zamknięcie zapasów powoduje korekty również transakcji zaktualizowanych fizycznie.</span><span class="sxs-lookup"><span data-stu-id="0bcb3-113">If you select the **Include physical value** check box when you use the FIFO (First in, first out), LIFO (Last in, first out), or LIFO date inventory model, inventory close also makes adjustments to physically updated transactions.</span></span>
-   <span data-ttu-id="0bcb3-114">Jeśli przy używaniu tych modeli zapasów nie zaznaczysz pola wyboru **Włącz wartość fizyczną**, zamknięcie zapasów spowoduje rozliczenie tylko z transakcjami zaktualizowanymi finansowo.</span><span class="sxs-lookup"><span data-stu-id="0bcb3-114">If you don't select the **Include physical value** check box when you use these inventory models, inventory close makes settlements only to financially updated transactions.</span></span>
-   <span data-ttu-id="0bcb3-115">W przypadku używania modelu zapasów Średnia ważona lub Średnia ważona z datą zamknięcie zapasów spowoduje rozliczenie tylko transakcji zaktualizowanych finansowo, niezależnie od tego, czy zaznaczono pole wyboru **Włącz wartość fizyczną**.</span><span class="sxs-lookup"><span data-stu-id="0bcb3-115">When you use the weighted average or weighted average date inventory model, inventory close settles only financially updated transactions, regardless of whether you select the **Include physical value** check box.</span></span>

<span data-ttu-id="0bcb3-116">**Przykład 1** Zaznaczono pole wyboru **Włącz wartość fizyczną** i przyjęto następujące zamówienia zakupu:</span><span class="sxs-lookup"><span data-stu-id="0bcb3-116">**Example 1** You've selected the **Include physical value** check box and receive the following purchase orders:</span></span>

-   <span data-ttu-id="0bcb3-117">Zamówienie zakupu na ilość 2 z kosztem własnym 10,00 zł, które zostało zaktualizowane przez dokument dostawy.</span><span class="sxs-lookup"><span data-stu-id="0bcb3-117">A purchase order for a quantity of 2 and a cost price of USD 10.00 that has been packing slip–updated.</span></span>
-   <span data-ttu-id="0bcb3-118">Zamówienie zakupu na ilość 3 z kosztem własnym 12,00 zł, które zostało zaktualizowane przez fakturę.</span><span class="sxs-lookup"><span data-stu-id="0bcb3-118">A purchase order for a quantity of 3 and a cost price of USD 12.00 that has been invoice-updated.</span></span>

<span data-ttu-id="0bcb3-119">W tym przypadku średnia krocząca kosztu własnego wyniesie 11,20 zł = (2x10+3x12)/(2+3), ponieważ do jego obliczenia są używane transakcje zaktualizowane fizycznie i finansowo.</span><span class="sxs-lookup"><span data-stu-id="0bcb3-119">In this case, the running average cost price will be USD 11.20 = (2x10+3x12)/(2+3), because both physically updated transactions and financially updated transactions are used to calculate the cost price.</span></span> 

<span data-ttu-id="0bcb3-120">**Przykład 2** Nie zaznaczono pola wyboru **Włącz wartość fizyczną**, a koszt własny w konfiguracji towaru wynosi 10,00 zł.</span><span class="sxs-lookup"><span data-stu-id="0bcb3-120">**Example 2** You haven't selected the **Include physical value** check box, and the cost price on the item setup is USD 10.00.</span></span> 

-   <span data-ttu-id="0bcb3-121">Przyjęto zamówienie zakupu na ilość 20 z kosztem własnym 12,00 zł, które zostało zaktualizowane przez dokument dostawy.</span><span class="sxs-lookup"><span data-stu-id="0bcb3-121">You receive a purchase order for a quantity of 20 and a cost price of USD 12.00 that has been packing slip–updated.</span></span>

<span data-ttu-id="0bcb3-122">Podczas księgowania zamówienia sprzedaży zaksięgowana kwota kosztu wyniesie 10,00 zł, ponieważ średnia krocząca kosztu własnego nie będzie uwzględniała transakcji zaktualizowanych fizycznie.</span><span class="sxs-lookup"><span data-stu-id="0bcb3-122">When a sales order is posted, the posted cost amount is USD 10.00, because the running average cost price won't include physically posted transactions.</span></span> 

> [!NOTE]
> <span data-ttu-id="0bcb3-123">Jeśli dla tego towaru zostałoby zaznaczone pole wyboru **Włącz wartość fizyczną**, podczas księgowania zamówienia sprzedaży zaksięgowana kwota kosztu wynosiłaby 12,00 zł.</span><span class="sxs-lookup"><span data-stu-id="0bcb3-123">For comparison, if you select the **Include physical value** check box for this item, when a sales order is posted, the posted cost amount will be USD 12.00.</span></span>
