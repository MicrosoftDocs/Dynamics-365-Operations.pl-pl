--- 
title: Tworzenie metody punktowania dla ZO
description: "W tej procedurze pokazano sposób tworzenia metody punktowania."
author: mkirknel
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchRFQScoringMethod
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 0235723e0e5668c53ca6f6ac79732502aeae551a
ms.contentlocale: pl-pl
ms.lasthandoff: 09/11/2018

---
# <a name="create-a-scoring-method-for-rfqs"></a><span data-ttu-id="94ded-103">Tworzenie metody punktowania dla ZO</span><span class="sxs-lookup"><span data-stu-id="94ded-103">Create a scoring method for RFQs</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="94ded-104">W tej procedurze pokazano sposób tworzenia metody punktowania.</span><span class="sxs-lookup"><span data-stu-id="94ded-104">This procedure shows you how to create a scoring method.</span></span> <span data-ttu-id="94ded-105">Metoda punktowania to zbiór kryteriów, których można używać do porównywania ofert wysyłanych w odpowiedzi na zapytanie ofertowe (ZO).</span><span class="sxs-lookup"><span data-stu-id="94ded-105">A scoring method is a set of criteria that can be used to compare bids that are sent in reply to a request for quotation (RFQ).</span></span> <span data-ttu-id="94ded-106">Na przykład można ocenić dostawcę na podstawie przebiegu dotychczasowej współpracy lub tego, czy firma jest przyjazna środowisku albo komunikatywna, lub też porównać oferty na podstawie ceny.</span><span class="sxs-lookup"><span data-stu-id="94ded-106">For example, you might want to rate a vendor on past performance, or rate whether the company is environmentally friendly or a good collaborator, or you might want to compare bids based on price.</span></span> <span data-ttu-id="94ded-107">Metoda punktowania może być skojarzona z typem zdobywania zamówień jako domyślną metodą punktowania dla tego rodzaju ZO.</span><span class="sxs-lookup"><span data-stu-id="94ded-107">The scoring method can be associated with a solicitation type as the default scoring method for RFQs of that type.</span></span> <span data-ttu-id="94ded-108">Te zadania zazwyczaj wykonuje menedżer ds. zakupów.</span><span class="sxs-lookup"><span data-stu-id="94ded-108">These tasks would typically be carried out by a purchasing manager.</span></span> <span data-ttu-id="94ded-109">Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="94ded-109">You can use this procedure in demo data company USMF or on your own data.</span></span>

1. <span data-ttu-id="94ded-110">Wybierz kolejno opcje Zaopatrzenie i sourcing > Ustawienia > Zapytanie ofertowe > Metoda punktowa.</span><span class="sxs-lookup"><span data-stu-id="94ded-110">Go to Procurement and sourcing > Setup > Request for quotation > Scoring method.</span></span>
2. <span data-ttu-id="94ded-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="94ded-111">Click New.</span></span>
3. <span data-ttu-id="94ded-112">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="94ded-112">In the Name field, type a value.</span></span>
4. <span data-ttu-id="94ded-113">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="94ded-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="94ded-114">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="94ded-114">Click Save.</span></span>
6. <span data-ttu-id="94ded-115">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="94ded-115">Click New.</span></span>
7. <span data-ttu-id="94ded-116">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="94ded-116">In the Name field, type a value.</span></span>
8. <span data-ttu-id="94ded-117">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="94ded-117">In the Description field, type a value.</span></span>
    * <span data-ttu-id="94ded-118">Ten opis jest wyświetlany wraz z nazwą metody punktowania po wybraniu takiej metody dla ZO.</span><span class="sxs-lookup"><span data-stu-id="94ded-118">This description is shown along with the scoring method name when a scoring method is selected for an RFQ.</span></span>  
9. <span data-ttu-id="94ded-119">W polu Początek zakresu wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="94ded-119">In the Range from field, enter a number.</span></span>
    * <span data-ttu-id="94ded-120">Zakres ogranicza wartości, jakie pracownik działu zaopatrzenia może wprowadzić jako punktację.</span><span class="sxs-lookup"><span data-stu-id="94ded-120">The range limits what the procurement professional can enter as a score.</span></span> <span data-ttu-id="94ded-121">Jeśli istnieje wiele kryteriów punktowania dla ZO, wprowadzone wyniki punktowe są dodawane do siebie, po czym jest udostępniana suma umożliwiająca porównanie ofert.</span><span class="sxs-lookup"><span data-stu-id="94ded-121">When there are multiple scoring criteria on an RFQ, the scores that have been entered are added to each other and the sum is made available to allow the bids to be compared.</span></span>  
10. <span data-ttu-id="94ded-122">W polu Koniec zakresu wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="94ded-122">In the Range to field, enter a number.</span></span>
11. <span data-ttu-id="94ded-123">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="94ded-123">Click New.</span></span>
12. <span data-ttu-id="94ded-124">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="94ded-124">In the Name field, type a value.</span></span>
13. <span data-ttu-id="94ded-125">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="94ded-125">In the Description field, type a value.</span></span>
14. <span data-ttu-id="94ded-126">W polu Początek zakresu wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="94ded-126">In the Range from field, enter a number.</span></span>
15. <span data-ttu-id="94ded-127">W polu Koniec zakresu wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="94ded-127">In the Range to field, enter a number.</span></span>


