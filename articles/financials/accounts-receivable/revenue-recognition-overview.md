---
title: Omówienie rozpoznawania przychodu
description: Ten temat zawiera informacje dotyczące funkcji Rozpoznawanie przychodu. Ta funkcja tworzy elastyczną strukturę, która umożliwia określanie reguł rozpoznawania zarówno ceny przychodu, jak i harmonogramu przychodu w przypadku zamówień wieloelementowych na poziomie danej firmy.
author: kweekley
manager: aolson
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: d52a9c7315cccf668a8b9bcf7ba5cad7039e186e
ms.sourcegitcommit: 299e20b59ebefa584ed46a13da3f1a7ff709e43c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2019
ms.locfileid: "1863570"
---
# <a name="revenue-recognition-overview"></a><span data-ttu-id="0ef6c-104">Omówienie rozpoznawania przychodu</span><span class="sxs-lookup"><span data-stu-id="0ef6c-104">Revenue recognition overview</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!NOTE]
> <span data-ttu-id="0ef6c-105">Funkcji Rozpoznawanie przychodu nie można jeszcze włączyć za pomocą modułu Zarządzanie funkcjami.</span><span class="sxs-lookup"><span data-stu-id="0ef6c-105">The Revenue recognition feature can't yet be turned on through Feature management.</span></span> <span data-ttu-id="0ef6c-106">Obecnie można ją włączyć tylko przy użyciu kluczy konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="0ef6c-106">Currently, you must use configuration keys to turn it on.</span></span>

<span data-ttu-id="0ef6c-107">Firmy w branży sprzedające wiele elementów, jak produkty, usługi, subskrypcje itd., muszą być w stanie rozdzielać zamówienia wieloelementowe, aby przychód mógł zostać rozpoznany na podstawie zbioru wytycznych właściwych dla danej firmy i branży.</span><span class="sxs-lookup"><span data-stu-id="0ef6c-107">Companies in industries that sell multiple elements, such as products, services, subscriptions, and so on, must be able to break out multi-element orders so that revenue can be recognized based on a set of company-specific and industry-specific guidelines.</span></span>

<span data-ttu-id="0ef6c-108">Proces rozpoznawania przychodu może generalnie służyć do wykonywania następujących zadań:</span><span class="sxs-lookup"><span data-stu-id="0ef6c-108">In general, the revenue recognition process can be used to perform these tasks:</span></span>

* <span data-ttu-id="0ef6c-109">Alokowanie przychodu, aby odpowiednia cena przychodu została uznana na podstawie wartości składników w zamówieniach wieloskładnikowych.</span><span class="sxs-lookup"><span data-stu-id="0ef6c-109">Allocate revenue, to help guarantee that the appropriate revenue price is recognized based on the value of the components on the multi-element orders.</span></span>
* <span data-ttu-id="0ef6c-110">Odraczanie przychodu, na podstawie harmonogramu przychodu, który reprezentuje uzgodniony w umowie przedział czasowy i udziały procentowe rozpoznawania przychodu z biegiem czasu.</span><span class="sxs-lookup"><span data-stu-id="0ef6c-110">Defer revenue, based on a revenue schedule that represents the contractual timeframe and percentages for recognizing revenue over time.</span></span>

<span data-ttu-id="0ef6c-111">Funkcja Rozpoznawanie przychodu tworzy elastyczną strukturę, która umożliwia określanie reguł rozpoznawania zarówno ceny przychodu, jak i harmonogramu przychodu na poziomie danej firmy.</span><span class="sxs-lookup"><span data-stu-id="0ef6c-111">The Revenue recognition feature provides a flexible framework that lets you define company-specific rules for recognizing both the revenue price and the revenue schedule.</span></span>

<span data-ttu-id="0ef6c-112">Zwolnione produkty służą do obsługi rozpoznawania przychodu w dokumentach zamówień sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="0ef6c-112">Released products are used to support revenue recognition on sales order documents.</span></span> <span data-ttu-id="0ef6c-113">Zwolnione produkty zawierają ustawienia wymagane do określenia ceny przychodu i harmonogramu przychodów.</span><span class="sxs-lookup"><span data-stu-id="0ef6c-113">The released products contain the setup that is required to determine the revenue price and the revenue schedule.</span></span> <span data-ttu-id="0ef6c-114">Zamówienie sprzedaży może pochodzić z projektu typu Czas i materiały.</span><span class="sxs-lookup"><span data-stu-id="0ef6c-114">The sales order can originate from a Time and material project.</span></span>

<span data-ttu-id="0ef6c-115">Firmy mogą używać funkcji harmonogramu przychodów bez korzystania z funkcji ceny przychodu.</span><span class="sxs-lookup"><span data-stu-id="0ef6c-115">Companies can use the revenue schedule functionality without using the revenue price functionality.</span></span> <span data-ttu-id="0ef6c-116">W związku z tym cena w wierszach zamówienia sprzedaży zawsze zostanie użyta jako przychód lub odroczony przychód.</span><span class="sxs-lookup"><span data-stu-id="0ef6c-116">Therefore, the price on the sales order lines will be used as either revenue or deferred revenue.</span></span> <span data-ttu-id="0ef6c-117">Jeśli w wierszu zamówienia sprzedaży istnieje harmonogram przychodów, cena w wierszu zamówienia sprzedaży zostanie odroczona.</span><span class="sxs-lookup"><span data-stu-id="0ef6c-117">If a revenue schedule exists on the sales order line, the price on the sales order line will be deferred.</span></span> <span data-ttu-id="0ef6c-118">Jeśli wiersz zamówienia sprzedaży nie zawiera harmonogramu przychodów, cena w wierszu zamówienia sprzedaży zostanie zaksięgowana na koncie przychodów po zafakturowaniu.</span><span class="sxs-lookup"><span data-stu-id="0ef6c-118">If a revenue schedule doesn't exist on the sales order line, the price on the sales order line will be posted to a revenue account when it's invoiced.</span></span>

<span data-ttu-id="0ef6c-119">Cena przychodu jest obliczana w momencie zatwierdzenia zamówienia sprzedaży albo zaksięgowania faktury.</span><span class="sxs-lookup"><span data-stu-id="0ef6c-119">The revenue price is calculated either when the sales order is confirmed or when the invoice is posted.</span></span> <span data-ttu-id="0ef6c-120">Aby wyświetlić podgląd ceny przychodu przed zaksięgowaniem faktury, należy potwierdzić zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="0ef6c-120">To preview the revenue price before the invoice is posted, you must confirm the sales order.</span></span>

<span data-ttu-id="0ef6c-121">Po potwierdzeniu zamówienia sprzedaży jest również tworzony oczekiwany harmonogram przychodów, jeśli dowolny wiersz zamówienia sprzedaży zawiera harmonogram przychodów.</span><span class="sxs-lookup"><span data-stu-id="0ef6c-121">When the sales order is confirmed, an expected revenue schedule is also created if any sales order line contains a revenue schedule.</span></span> <span data-ttu-id="0ef6c-122">Po zafakturowaniu zamówienia sprzedaży oczekiwany harmonogram przychodów zostanie usunięty i zastąpiony rzeczywistym harmonogramem rozpoznawania przychodu.</span><span class="sxs-lookup"><span data-stu-id="0ef6c-122">When the sales order is invoiced, the expected revenue schedule is deleted, and the expected revenue schedule is replaced with the actual revenue recognition schedule.</span></span>

<span data-ttu-id="0ef6c-123">Szczegóły harmonogramu rozpoznawania przychodu są obsługiwane dla każdego wiersza zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="0ef6c-123">The details of the revenue recognition schedule are maintained for each sales order line.</span></span> <span data-ttu-id="0ef6c-124">W związku z tym menedżer rozpoznawania przychodu może wyświetlać szczegóły i zwalniać wiersze do przychodu, gdy zobowiązanie umowne zostanie zrealizowane.</span><span class="sxs-lookup"><span data-stu-id="0ef6c-124">Therefore, the revenue recognition manager can view the details and can release lines to revenue when the contractual obligation has been completed.</span></span> <span data-ttu-id="0ef6c-125">Na koniec każdego okresu menedżer rozpoznawania przychodu może utworzyć arkusz przychodów w celu zwolnienia wierszy harmonogramu, które są należne w wyznaczonym przez niego dniu lub wcześniej.</span><span class="sxs-lookup"><span data-stu-id="0ef6c-125">At the end of each period, the revenue recognition manager can create a revenue journal to release any schedule lines that are due on or before a date that he or she defines.</span></span> <span data-ttu-id="0ef6c-126">Ten arkusz przychodów nie jest natychmiast księgowany.</span><span class="sxs-lookup"><span data-stu-id="0ef6c-126">This revenue journal isn't posted immediately.</span></span> <span data-ttu-id="0ef6c-127">W związku z tym menedżer rozpoznawania przychodu może sprawdzić, czy kwoty zwalniane z odroczonego do rzeczywistego przychodu są poprawne.</span><span class="sxs-lookup"><span data-stu-id="0ef6c-127">Therefore, the revenue recognition manager can verify that the correct amounts are being released from deferred revenue to actual revenue.</span></span>

<span data-ttu-id="0ef6c-128">Jeśli zmiana umowna spowoduje dodanie nowego wiersza zamówienia sprzedaży do istniejącego zamówienia sprzedaży lub nowego zamówienia sprzedaży, można uruchomić proces zmiany alokacji w celu skorygowania ceny przychodu we wszystkich wierszach zamówień sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="0ef6c-128">If a contractual change causes a new sales order line to be added either to the existing sales order or a new sales order, a reallocation process can be run to correct the revenue price across all lines the sales orders.</span></span>
