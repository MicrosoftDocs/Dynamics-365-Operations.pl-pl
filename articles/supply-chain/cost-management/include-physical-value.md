---
title: "Włącz wartość fizyczną"
description: "Pole wyboru Włącz wartość fizyczną na skróconej karcie Model magazynu na stronie Grupy modeli pozycji służy do określania, czy przy obliczaniu średniej kroczącej kosztu własnego towaru są uwzględniane fizycznie zaktualizowane transakcje."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 79033
ms.assetid: 1928c145-bf82-436d-87ca-e7a173e31923
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: e96d5e2a658a027d66663868329cf4eedcb1d46f
ms.contentlocale: pl-pl
ms.lasthandoff: 08/07/2018

---

# <a name="include-physical-value"></a><span data-ttu-id="11981-103">Włącz wartość fizyczną</span><span class="sxs-lookup"><span data-stu-id="11981-103">Include physical value</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="11981-104">Pole wyboru Włącz wartość fizyczną na skróconej karcie Model magazynu na stronie Grupy modeli pozycji służy do określania, czy przy obliczaniu średniej kroczącej kosztu własnego towaru są uwzględniane fizycznie zaktualizowane transakcje.</span><span class="sxs-lookup"><span data-stu-id="11981-104">You use the Include physical value check box on the Inventory model FastTab of the Item model groups page to specify whether physically updated transactions are considered when the running average cost price is calculated for an item.</span></span>

<span data-ttu-id="11981-105">Pole wyboru **Włącz wartość fizyczną** ma następujące wartości.</span><span class="sxs-lookup"><span data-stu-id="11981-105">The **Include physical value** check box has the following values.</span></span>

| <span data-ttu-id="11981-106">Wartość</span><span class="sxs-lookup"><span data-stu-id="11981-106">Value</span></span>    | <span data-ttu-id="11981-107">Wynik</span><span class="sxs-lookup"><span data-stu-id="11981-107">Result</span></span>                                                                                                                          |
|----------|---------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="11981-108">Wybrano</span><span class="sxs-lookup"><span data-stu-id="11981-108">Selected</span></span> | <span data-ttu-id="11981-109">Do obliczania średniej kroczącej kosztu własnego są używane transakcje zaktualizowane fizycznie i finansowo.</span><span class="sxs-lookup"><span data-stu-id="11981-109">Both physically updated transactions and financially updated transactions are used to calculate the running average cost price.</span></span> |
| <span data-ttu-id="11981-110">Zaakceptowane</span><span class="sxs-lookup"><span data-stu-id="11981-110">Cleared</span></span>  | <span data-ttu-id="11981-111">Do obliczania średniej kroczącej kosztu własnego są używane tylko transakcje zaktualizowane finansowo.</span><span class="sxs-lookup"><span data-stu-id="11981-111">Only financially updated transactions are used to calculate the running average cost price.</span></span>                                     |

<span data-ttu-id="11981-112">To pole wyboru działa nieco inaczej zależnie od wybranego modelu zapasów.</span><span class="sxs-lookup"><span data-stu-id="11981-112">The check box has slightly different effects, depending on the inventory model that you use.</span></span>

-   <span data-ttu-id="11981-113">Zaznaczenie pola wyboru **Włącz wartość fizyczną** w przypadku używania modelu zapasów FIFO (pierwszy na wejściu, pierwszy na wyjściu), LIFO (ostatni na wejściu, pierwszy na wyjściu) lub LIFO wg daty, zamknięcie zapasów powoduje korekty również transakcji zaktualizowanych fizycznie.</span><span class="sxs-lookup"><span data-stu-id="11981-113">If you select the **Include physical value** check box when you use the FIFO (First in, first out), LIFO (Last in, first out), or LIFO date inventory model, inventory close also makes adjustments to physically updated transactions.</span></span>
-   <span data-ttu-id="11981-114">Jeśli przy używaniu tych modeli zapasów nie zaznaczysz pola wyboru **Włącz wartość fizyczną**, zamknięcie zapasów spowoduje rozliczenie tylko z transakcjami zaktualizowanymi finansowo.</span><span class="sxs-lookup"><span data-stu-id="11981-114">If you don't select the **Include physical value** check box when you use these inventory models, inventory close makes settlements only to financially updated transactions.</span></span>
-   <span data-ttu-id="11981-115">W przypadku używania modelu zapasów Średnia ważona lub Średnia ważona z datą zamknięcie zapasów spowoduje rozliczenie tylko transakcji zaktualizowanych finansowo, niezależnie od tego, czy zaznaczono pole wyboru **Włącz wartość fizyczną**.</span><span class="sxs-lookup"><span data-stu-id="11981-115">When you use the weighted average or weighted average date inventory model, inventory close settles only financially updated transactions, regardless of whether you select the **Include physical value** check box.</span></span>

<span data-ttu-id="11981-116">**Przykład 1** Zaznaczono pole wyboru **Włącz wartość fizyczną** i przyjęto następujące zamówienia zakupu:</span><span class="sxs-lookup"><span data-stu-id="11981-116">**Example 1** You've selected the **Include physical value** check box and receive the following purchase orders:</span></span>

-   <span data-ttu-id="11981-117">Zamówienie zakupu na ilość 2 z kosztem własnym 10,00 zł, które zostało zaktualizowane przez dokument dostawy</span><span class="sxs-lookup"><span data-stu-id="11981-117">A purchase order for a quantity of 2 and a cost price of USD 10.00 that has been packing slip–updated</span></span>
-   <span data-ttu-id="11981-118">Zamówienie zakupu na ilość 3 z kosztem własnym 12,00 zł, które zostało zaktualizowane przez fakturę</span><span class="sxs-lookup"><span data-stu-id="11981-118">A purchase order for a quantity of 3 and a cost price of USD 12.00 that has been invoice-updated</span></span>

<span data-ttu-id="11981-119">W tym przypadku średnia krocząca kosztu własnego wyniesie 11,20 zł, ponieważ do jego obliczenia są używane transakcje zaktualizowane fizycznie i finansowo.</span><span class="sxs-lookup"><span data-stu-id="11981-119">In this case, the running average cost price will be USD 11.20, because both physically updated transactions and financially updated transactions are used to calculate the cost price.</span></span> <span data-ttu-id="11981-120">**Przykład 2** Nie zaznaczono pola wyboru **Włącz wartość fizyczną**, a koszt własny w konfiguracji towaru wynosi 10,00 zł.</span><span class="sxs-lookup"><span data-stu-id="11981-120">**Example 2** You haven't selected the **Include physical value** check box, and the cost price on the item setup is USD 10.00.</span></span> <span data-ttu-id="11981-121">Przyjęto zamówienie zakupu na ilość 20 z kosztem własnym 12,00 zł, które zostało zaktualizowane przez dokument dostawy.</span><span class="sxs-lookup"><span data-stu-id="11981-121">You receive a purchase order for a quantity of 20 and a cost price of USD 12.00 that has been packing slip–updated.</span></span> <span data-ttu-id="11981-122">Podczas księgowania zamówienia sprzedaży zaksięgowana kwota kosztu wyniesie 10,00 zł, ponieważ średnia krocząca kosztu własnego nie będzie uwzględniała transakcji zaktualizowanych fizycznie.</span><span class="sxs-lookup"><span data-stu-id="11981-122">When a sales order is posted, the posted cost amount is USD 10.00, because the running average cost price won't include physically posted transactions.</span></span> <span data-ttu-id="11981-123">**Uwaga:** Jeśli dla tego towaru zostałoby zaznaczone pole wyboru **Włącz wartość fizyczną**, podczas księgowania zamówienia sprzedaży zaksięgowana kwota kosztu wynosiłaby 12,00 zł.</span><span class="sxs-lookup"><span data-stu-id="11981-123">**Note:** For comparison, if you select the **Include physical value** check box for this item, when a sales order is posted, the posted cost amount will be USD 12.00.</span></span>




