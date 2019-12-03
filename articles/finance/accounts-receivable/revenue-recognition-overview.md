---
title: Omówienie rozpoznawania przychodu
description: Ten temat zawiera informacje dotyczące funkcji Rozpoznawanie przychodu. Ta funkcja tworzy elastyczną strukturę, która umożliwia określanie reguł rozpoznawania zarówno ceny przychodu, jak i harmonogramu przychodu w przypadku zamówień wieloelementowych na poziomie danej firmy.
author: kweekley
manager: aolson
ms.date: 11/11/2019
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
ms.openlocfilehash: 8743183c46463395cad3138261860442701e0178
ms.sourcegitcommit: 0138b6c108a10f2bcb90c91205da8092917160d8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2019
ms.locfileid: "2781903"
---
# <a name="revenue-recognition-overview"></a><span data-ttu-id="4fb66-104">Omówienie rozpoznawania przychodu</span><span class="sxs-lookup"><span data-stu-id="4fb66-104">Revenue recognition overview</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="4fb66-105">Funkcji Rozpoznawanie przychodów nie można włączyć za pomocą modułu Zarządzanie funkcjami.</span><span class="sxs-lookup"><span data-stu-id="4fb66-105">The Revenue recognition feature can't be turned on through Feature management.</span></span> <span data-ttu-id="4fb66-106">Obecnie można ją włączyć tylko przy użyciu kluczy konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="4fb66-106">Currently, you must use configuration keys to turn it on.</span></span>

<span data-ttu-id="4fb66-107">Firmy w branży sprzedające wiele elementów, jak produkty, usługi, subskrypcje itd., muszą być w stanie rozdzielać zamówienia wieloelementowe, aby przychód mógł zostać rozpoznany na podstawie zbioru wytycznych właściwych dla danej firmy i branży.</span><span class="sxs-lookup"><span data-stu-id="4fb66-107">Companies in industries that sell multiple elements, such as products, services, subscriptions, and so on, must be able to break out multi-element orders so that revenue can be recognized based on a set of company-specific and industry-specific guidelines.</span></span>

<span data-ttu-id="4fb66-108">Proces rozpoznawania przychodu może generalnie służyć do wykonywania następujących zadań:</span><span class="sxs-lookup"><span data-stu-id="4fb66-108">In general, the revenue recognition process can be used to perform these tasks:</span></span>

* <span data-ttu-id="4fb66-109">Alokowanie przychodu, aby odpowiednia cena przychodu została rozpoznana na podstawie wartości składników w zamówieniach wieloskładnikowych.</span><span class="sxs-lookup"><span data-stu-id="4fb66-109">Allocate revenue, to help guarantee that the appropriate revenue price is recognized, based on the value of the components on multi-element orders.</span></span>
* <span data-ttu-id="4fb66-110">Odraczanie przychodu na podstawie harmonogramu przychodu, który reprezentuje uzgodniony w umowie przedział czasowy, i udziały procentowe rozpoznawania przychodu z biegiem czasu.</span><span class="sxs-lookup"><span data-stu-id="4fb66-110">Defer revenue, based on a revenue schedule that represents the contractual time frame and percentages for recognizing revenue over time.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE44iER]

<span data-ttu-id="4fb66-111">Film [Sposób korzystania z rozpoznawania przychodów w Dynamics 365 Finance](https://youtu.be/v3amIsiqvoo) (widoczny powyżej) znajduje się na [liście odtwarzania Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) dostępnej w witrynie YouTube.</span><span class="sxs-lookup"><span data-stu-id="4fb66-111">The [How to use revenue recognition in Dynamics 365 Finance](https://youtu.be/v3amIsiqvoo) video (shown above) is included in the [Finance and Operations playlist](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) available on YouTube.</span></span>

<span data-ttu-id="4fb66-112">Funkcja Rozpoznawanie przychodu tworzy elastyczną strukturę, która umożliwia określanie reguł rozpoznawania zarówno ceny przychodu, jak i harmonogramu przychodu na poziomie danej firmy.</span><span class="sxs-lookup"><span data-stu-id="4fb66-112">The Revenue recognition feature provides a flexible framework that lets you define company-specific rules for recognizing both the revenue price and the revenue schedule.</span></span>

<span data-ttu-id="4fb66-113">Zwolnione produkty służą do obsługi rozpoznawania przychodu w dokumentach zamówień sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="4fb66-113">Released products are used to support revenue recognition on sales order documents.</span></span> <span data-ttu-id="4fb66-114">Zwolnione produkty zawierają ustawienia wymagane do określenia ceny przychodu i harmonogramu przychodów.</span><span class="sxs-lookup"><span data-stu-id="4fb66-114">The released products contain the setup that is required to determine the revenue price and the revenue schedule.</span></span> <span data-ttu-id="4fb66-115">Zamówienie sprzedaży może pochodzić z projektu typu czas i materiały.</span><span class="sxs-lookup"><span data-stu-id="4fb66-115">The sales order can originate from a Time and materials project.</span></span>

<span data-ttu-id="4fb66-116">Firmy mogą używać funkcji harmonogramu przychodów bez korzystania z funkcji ceny przychodu.</span><span class="sxs-lookup"><span data-stu-id="4fb66-116">Companies can use the revenue schedule functionality without using the revenue price functionality.</span></span> <span data-ttu-id="4fb66-117">W związku z tym cena w wierszach zamówienia sprzedaży zawsze zostanie użyta jako przychód lub odroczony przychód.</span><span class="sxs-lookup"><span data-stu-id="4fb66-117">Therefore, the price on the sales order lines will be used as either revenue or deferred revenue.</span></span> <span data-ttu-id="4fb66-118">Jeśli w wierszu zamówienia sprzedaży istnieje harmonogram przychodów, cena w wierszu zamówienia sprzedaży zostanie odroczona.</span><span class="sxs-lookup"><span data-stu-id="4fb66-118">If a revenue schedule exists on the sales order line, the price on the sales order line will be deferred.</span></span> <span data-ttu-id="4fb66-119">Jeśli wiersz zamówienia sprzedaży nie zawiera harmonogramu przychodów, cena w wierszu zamówienia sprzedaży zostanie zaksięgowana na koncie przychodów po zafakturowaniu.</span><span class="sxs-lookup"><span data-stu-id="4fb66-119">If a revenue schedule doesn't exist on the sales order line, the price on the sales order line will be posted to a revenue account when it's invoiced.</span></span>

<span data-ttu-id="4fb66-120">Cena przychodu jest obliczana w momencie zatwierdzenia zamówienia sprzedaży albo zaksięgowania faktury.</span><span class="sxs-lookup"><span data-stu-id="4fb66-120">The revenue price is calculated either when the sales order is confirmed or when the invoice is posted.</span></span> <span data-ttu-id="4fb66-121">Aby wyświetlić podgląd ceny przychodu przed zaksięgowaniem faktury, należy potwierdzić zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="4fb66-121">To preview the revenue price before the invoice is posted, you must confirm the sales order.</span></span>

<span data-ttu-id="4fb66-122">Po potwierdzeniu zamówienia sprzedaży jest również tworzony oczekiwany harmonogram przychodów, jeśli dowolny wiersz zamówienia sprzedaży zawiera harmonogram przychodów.</span><span class="sxs-lookup"><span data-stu-id="4fb66-122">When the sales order is confirmed, an expected revenue schedule is also created if any sales order line has a revenue schedule.</span></span> <span data-ttu-id="4fb66-123">Po zafakturowaniu zamówienia sprzedaży oczekiwany harmonogram przychodów zostanie usunięty i zastąpiony rzeczywistym harmonogramem rozpoznawania przychodów.</span><span class="sxs-lookup"><span data-stu-id="4fb66-123">When the sales order is invoiced, the expected revenue schedule is deleted, and the expected revenue schedule is replaced with the actual revenue recognition schedule.</span></span>

<span data-ttu-id="4fb66-124">Szczegóły harmonogramu rozpoznawania przychodu są obsługiwane dla każdego wiersza zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="4fb66-124">The details of the revenue recognition schedule are maintained for each sales order line.</span></span> <span data-ttu-id="4fb66-125">W związku z tym menedżer rozpoznawania przychodu może wyświetlać szczegóły i zwalniać wiersze do przychodu, gdy zobowiązanie umowne zostanie zrealizowane.</span><span class="sxs-lookup"><span data-stu-id="4fb66-125">Therefore, the revenue recognition manager can view the details and can release lines to revenue when the contractual obligation has been completed.</span></span> <span data-ttu-id="4fb66-126">Na koniec każdego okresu menedżer rozpoznawania przychodu może utworzyć arkusz przychodów w celu zwolnienia wierszy harmonogramu, które są należne w wyznaczonym przez niego dniu lub wcześniej.</span><span class="sxs-lookup"><span data-stu-id="4fb66-126">At the end of each period, the revenue recognition manager can create a revenue journal to release any schedule lines that are due on or before a date that he or she defines.</span></span> <span data-ttu-id="4fb66-127">Ten arkusz przychodów nie jest natychmiast księgowany.</span><span class="sxs-lookup"><span data-stu-id="4fb66-127">This revenue journal isn't posted immediately.</span></span> <span data-ttu-id="4fb66-128">W związku z tym menedżer rozpoznawania przychodu może sprawdzić, czy kwoty zwalniane z odroczonego do rzeczywistego przychodu są poprawne.</span><span class="sxs-lookup"><span data-stu-id="4fb66-128">Therefore, the revenue recognition manager can verify that the correct amounts are being released from deferred revenue to actual revenue.</span></span>

<span data-ttu-id="4fb66-129">Jeśli zmiana umowna spowoduje dodanie nowego wiersza zamówienia sprzedaży do istniejącego zamówienia sprzedaży lub nowego zamówienia sprzedaży, można uruchomić proces zmiany alokacji w celu skorygowania ceny przychodu we wszystkich wierszach zamówień sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="4fb66-129">If a contractual change causes a new sales order line to be added either to the existing sales order or a new sales order, a reallocation process can be run to correct the revenue price across all lines on the sales orders.</span></span>
