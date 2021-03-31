---
title: Tworzenie metody punktowania dla ZO
description: W tej procedurze pokazano sposób tworzenia metody punktowania.
author: RichardLuan
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchRFQScoringMethod
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ba3f0b2be16c02129616025c0ee6258996189c6a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211821"
---
# <a name="create-a-scoring-method-for-rfqs"></a><span data-ttu-id="926bc-103">Tworzenie metody punktowania dla ZO</span><span class="sxs-lookup"><span data-stu-id="926bc-103">Create a scoring method for RFQs</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="926bc-104">W tej procedurze pokazano sposób tworzenia metody punktowania.</span><span class="sxs-lookup"><span data-stu-id="926bc-104">This procedure shows you how to create a scoring method.</span></span> <span data-ttu-id="926bc-105">Metoda punktowania to zbiór kryteriów, których można używać do porównywania ofert wysyłanych w odpowiedzi na zapytanie ofertowe (ZO).</span><span class="sxs-lookup"><span data-stu-id="926bc-105">A scoring method is a set of criteria that can be used to compare bids that are sent in reply to a request for quotation (RFQ).</span></span> <span data-ttu-id="926bc-106">Na przykład można ocenić dostawcę na podstawie przebiegu dotychczasowej współpracy lub tego, czy firma jest przyjazna środowisku albo komunikatywna, lub też porównać oferty na podstawie ceny.</span><span class="sxs-lookup"><span data-stu-id="926bc-106">For example, you might want to rate a vendor on past performance, or rate whether the company is environmentally friendly or a good collaborator, or you might want to compare bids based on price.</span></span> <span data-ttu-id="926bc-107">Metoda punktowania może być skojarzona z typem zdobywania zamówień jako domyślną metodą punktowania dla tego rodzaju ZO.</span><span class="sxs-lookup"><span data-stu-id="926bc-107">The scoring method can be associated with a solicitation type as the default scoring method for RFQs of that type.</span></span> <span data-ttu-id="926bc-108">Te zadania zazwyczaj wykonuje menedżer ds. zakupów.</span><span class="sxs-lookup"><span data-stu-id="926bc-108">These tasks would typically be carried out by a purchasing manager.</span></span> <span data-ttu-id="926bc-109">Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="926bc-109">You can use this procedure in demo data company USMF or on your own data.</span></span>

1. <span data-ttu-id="926bc-110">Wybierz kolejno opcje Zaopatrzenie i sourcing > Ustawienia > Zapytanie ofertowe > Metoda punktowa.</span><span class="sxs-lookup"><span data-stu-id="926bc-110">Go to Procurement and sourcing > Setup > Request for quotation > Scoring method.</span></span>
2. <span data-ttu-id="926bc-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="926bc-111">Click New.</span></span>
3. <span data-ttu-id="926bc-112">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="926bc-112">In the Name field, type a value.</span></span>
4. <span data-ttu-id="926bc-113">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="926bc-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="926bc-114">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="926bc-114">Click Save.</span></span>
6. <span data-ttu-id="926bc-115">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="926bc-115">Click New.</span></span>
7. <span data-ttu-id="926bc-116">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="926bc-116">In the Name field, type a value.</span></span>
8. <span data-ttu-id="926bc-117">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="926bc-117">In the Description field, type a value.</span></span>
    * <span data-ttu-id="926bc-118">Ten opis jest wyświetlany wraz z nazwą metody punktowania po wybraniu takiej metody dla ZO.</span><span class="sxs-lookup"><span data-stu-id="926bc-118">This description is shown along with the scoring method name when a scoring method is selected for an RFQ.</span></span>  
9. <span data-ttu-id="926bc-119">W polu Początek zakresu wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="926bc-119">In the Range from field, enter a number.</span></span>
    * <span data-ttu-id="926bc-120">Zakres ogranicza wartości, jakie pracownik działu zaopatrzenia może wprowadzić jako punktację.</span><span class="sxs-lookup"><span data-stu-id="926bc-120">The range limits what the procurement professional can enter as a score.</span></span> <span data-ttu-id="926bc-121">Jeśli istnieje wiele kryteriów punktowania dla ZO, wprowadzone wyniki punktowe są dodawane do siebie, po czym jest udostępniana suma umożliwiająca porównanie ofert.</span><span class="sxs-lookup"><span data-stu-id="926bc-121">When there are multiple scoring criteria on an RFQ, the scores that have been entered are added to each other and the sum is made available to allow the bids to be compared.</span></span>  
10. <span data-ttu-id="926bc-122">W polu Koniec zakresu wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="926bc-122">In the Range to field, enter a number.</span></span>
11. <span data-ttu-id="926bc-123">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="926bc-123">Click New.</span></span>
12. <span data-ttu-id="926bc-124">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="926bc-124">In the Name field, type a value.</span></span>
13. <span data-ttu-id="926bc-125">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="926bc-125">In the Description field, type a value.</span></span>
14. <span data-ttu-id="926bc-126">W polu Początek zakresu wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="926bc-126">In the Range from field, enter a number.</span></span>
15. <span data-ttu-id="926bc-127">W polu Koniec zakresu wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="926bc-127">In the Range to field, enter a number.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]