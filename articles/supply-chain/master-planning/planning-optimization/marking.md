---
title: Oznaczanie zapasów przy użyciu modułu Optymalizacja planowania
description: Ten temat zawiera informacje o dostępnych opcjach oznaczania zapasów w zaakceptowanych zamówieniach podczas korzystania z optymalizacji planowania.
author: ChristianRytt
manager: tfehr
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 7813f570afb0260e6740507c9504320c3e87be93
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263357"
---
# <a name="inventory-marking-with-planning-optimization"></a><span data-ttu-id="7c3bd-103">Oznaczanie zapasów przy użyciu modułu Optymalizacja planowania</span><span class="sxs-lookup"><span data-stu-id="7c3bd-103">Inventory marking with Planning Optimization</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7c3bd-104">Ten temat zawiera informacje o dostępnych opcjach oznaczania zapasów w zaakceptowanych zamówieniach podczas korzystania z optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="7c3bd-104">This topic provides information about the options that are available for marking inventory in firmed orders when you use Planning Optimization.</span></span>

<span data-ttu-id="7c3bd-105">*Oznaczanie* służy do łączenia podaży i popytu.</span><span class="sxs-lookup"><span data-stu-id="7c3bd-105">*Marking* is used to link supply and demand.</span></span> <span data-ttu-id="7c3bd-106">Opcja ta jest podobna do *oznaczania transakcji*, które określa, jak popyt ma zostać pokryty według planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="7c3bd-106">It resembles *pegging*, which indicates how master planning expects to cover demand.</span></span> <span data-ttu-id="7c3bd-107">Z punktu widzenia planowania główna różnica polega na tym, że oznaczanie jest trwalsze od oznaczania transakcji.</span><span class="sxs-lookup"><span data-stu-id="7c3bd-107">From a planning point of view, the main difference is that marking is more permanent than pegging.</span></span>

<span data-ttu-id="7c3bd-108">Oznaczanie zostało wprowadzone, by umożliwić obsługę specjalnych scenariuszy wyceny dla metod FIFO (pierwsze na wejściu, pierwsze na wyjściu) i LIFO (ostatnie na wejściu, pierwsze na wyjściu).</span><span class="sxs-lookup"><span data-stu-id="7c3bd-108">Marking was introduced to support special costing scenarios for first in, first out (FIFO) and last in, first out (LIFO).</span></span> <span data-ttu-id="7c3bd-109">Obecnie jest także używane do niektórych scenariuszy niezwiązanych z wyceną.</span><span class="sxs-lookup"><span data-stu-id="7c3bd-109">However, it's now also used for some non-costing scenarios.</span></span> <span data-ttu-id="7c3bd-110">Oznaczanie połączeń między podażą a popytem jest opcjonalne i prawie trwałe.</span><span class="sxs-lookup"><span data-stu-id="7c3bd-110">Marking between supply and demand is optional and almost permanent.</span></span> <span data-ttu-id="7c3bd-111">Oznaczenie może zostać usunięte przez użytkownika ręcznie lub poprzez uruchomienie rozkładania wierszy zamówienia sprzedaży z zaznaczoną opcją **Usuń oznaczenie**.</span><span class="sxs-lookup"><span data-stu-id="7c3bd-111">Marking can be removed manually by a user, or it can be removed by running a sales order line explosion where the **Remove marking** option is selected.</span></span>

<span data-ttu-id="7c3bd-112">Oznaczanie transakcji jest kontrolowane przez planowanie główne na etapie określania zapotrzebowania i ma na celu połączenie popytu z wymaganą podażą.</span><span class="sxs-lookup"><span data-stu-id="7c3bd-112">Pegging is controlled by master planning during coverage to link demand with the required supply.</span></span> <span data-ttu-id="7c3bd-113">Oznaczanie transakcji można zaktualizować podczas każdego przebiegu planowania, by zoptymalizować podaż potrzebną do pokrycia popytu.</span><span class="sxs-lookup"><span data-stu-id="7c3bd-113">Pegging can be updated for each planning run to optimize the supply that is required to cover demand.</span></span> <span data-ttu-id="7c3bd-114">Gdy planowanie główne aktualizuje informacje związane z oznaczaniem transakcji, uwzględnia wszelkie istniejące oznaczenia.</span><span class="sxs-lookup"><span data-stu-id="7c3bd-114">When master planning updates pegging information, it respects any existing marking.</span></span>

<span data-ttu-id="7c3bd-115">Oznaczanie transakcji rozpoczyna się od uwzględnienia stosownych oznaczeń, rezerwacji dostępnych zapasów i rezerwacji zamówionych zapasów w następującej kolejności:</span><span class="sxs-lookup"><span data-stu-id="7c3bd-115">Pegging starts by including relevant marking, on-hand reservations, and on-order reservations, in the following sequence:</span></span>

1. <span data-ttu-id="7c3bd-116">Oznaczenia łączące popyt z podażą</span><span class="sxs-lookup"><span data-stu-id="7c3bd-116">Marking between demand and supply</span></span>
1. <span data-ttu-id="7c3bd-117">Rezerwacje dostępnych zapasów</span><span class="sxs-lookup"><span data-stu-id="7c3bd-117">On-hand reservations</span></span>
1. <span data-ttu-id="7c3bd-118">Rezerwacje zamówionych zapasów</span><span class="sxs-lookup"><span data-stu-id="7c3bd-118">On-order reservations</span></span>

<span data-ttu-id="7c3bd-119">Podczas akceptowania zamówienia planowanego w oknie dialogowym **Akceptacja** wyświetla się pole **Aktualizacja oznaczenia**, które służy do konfiguracji opcji oznaczania zamówień tworzonych w trakcie akceptowania.</span><span class="sxs-lookup"><span data-stu-id="7c3bd-119">When you firm a planned order, the **Firming** dialog box provides an **Update marking** field that you use to set marking options for the orders that are created during firming.</span></span> <span data-ttu-id="7c3bd-120">Należy wybrać jedną z następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="7c3bd-120">Select one of the following values:</span></span>

- <span data-ttu-id="7c3bd-121">**Nie** — zapasy nie są oznaczane.</span><span class="sxs-lookup"><span data-stu-id="7c3bd-121">**No** – No inventory marking is applied.</span></span>
- <span data-ttu-id="7c3bd-122">**Standardowa** — oznaczanie zapasów jest aktualizowane zgodnie z oznaczaniem transakcji.</span><span class="sxs-lookup"><span data-stu-id="7c3bd-122">**Standard** – Inventory marking is updated according to the pegging.</span></span> <span data-ttu-id="7c3bd-123">Zamówienie zapotrzebowania (popytu) jest oznaczane na podstawie zamówienia realizacji (podaży).</span><span class="sxs-lookup"><span data-stu-id="7c3bd-123">A requirement order (demand) is marked against a fulfillment order (supply).</span></span> <span data-ttu-id="7c3bd-124">Jeśli w zamówieniu realizacji pozostanie pewna ilość, zamówienie nie zostanie oznaczone, a dane referencyjne będą puste.</span><span class="sxs-lookup"><span data-stu-id="7c3bd-124">If some quantity remains on the fulfillment order, it isn't marked, and the reference information is left blank.</span></span> <span data-ttu-id="7c3bd-125">Na przykład jeśli zamówienie sprzedaży 100 ea otrzyma oznaczenie transakcji łączące je z zamówieniem zakupu 150 ea, informacje referencyjne zostaną przypisane wyłącznie do zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="7c3bd-125">For example, if a sales order for 100 ea is pegged against a purchase order for 150 ea, reference information will be assigned only to the sales order.</span></span>
- <span data-ttu-id="7c3bd-126">**Rozszerzona** — zarówno zamówienie zapotrzebowania (popyt), jak i zamówienie realizacji (podaż) są oznaczane niezależnie od tego, czy w zamówieniu realizacji pozostaje jakaś ilość.</span><span class="sxs-lookup"><span data-stu-id="7c3bd-126">**Extended** – Both the requirement order (demand) and the fulfillment order (supply) are marked, regardless of any quantity that remains on the fulfillment order.</span></span> <span data-ttu-id="7c3bd-127">Na przykład jeśli zamówienie sprzedaży 100 ea otrzyma oznaczenie transakcji łączące je z zamówieniem zakupu 150 ea, informacje referencyjne zostaną przypisane zarówno do zamówienia sprzedaży, jak i do zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="7c3bd-127">For example, if a sales order for 100 ea is pegged against a purchase order for 150 ea, reference information will be assigned to both the sales order and the purchase order.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]