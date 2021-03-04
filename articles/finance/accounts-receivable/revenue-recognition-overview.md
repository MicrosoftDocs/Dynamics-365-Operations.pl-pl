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
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: a7e37a0800ec7909f79e5a2354f59c7450995641
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4995621"
---
# <a name="revenue-recognition-overview"></a><span data-ttu-id="a1a56-104">Omówienie rozpoznawania przychodu</span><span class="sxs-lookup"><span data-stu-id="a1a56-104">Revenue recognition overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a1a56-105">Firmy w branży sprzedające wiele elementów, jak produkty, usługi, subskrypcje itd., muszą być w stanie rozdzielać zamówienia wieloelementowe, aby przychód mógł zostać rozpoznany na podstawie zbioru wytycznych właściwych dla danej firmy i branży.</span><span class="sxs-lookup"><span data-stu-id="a1a56-105">Companies in industries that sell multiple elements, such as products, services, subscriptions, and so on, must be able to break out multi-element orders so that revenue can be recognized based on a set of company-specific and industry-specific guidelines.</span></span>

> [!NOTE]
> <span data-ttu-id="a1a56-106">Funkcji Rozpoznawanie przychodów nie można włączyć za pomocą modułu Zarządzanie funkcjami.</span><span class="sxs-lookup"><span data-stu-id="a1a56-106">The Revenue recognition feature can't be turned on through Feature management.</span></span> <span data-ttu-id="a1a56-107">Obecnie można ją włączyć tylko przy użyciu kluczy konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="a1a56-107">Currently, you must use configuration keys to turn it on.</span></span>

> <span data-ttu-id="a1a56-108">Funkcje rozpoznawania przychodów, w tym funkcja pakietu, nie są obsługiwane w kanałach Commerce (handel elektroniczny, punkt sprzedaży, biuro obsługi).</span><span class="sxs-lookup"><span data-stu-id="a1a56-108">Revenue recognition, including bundle functionality, isn't supported for use in Commerce channels (e-commerce, POS, call center).</span></span> <span data-ttu-id="a1a56-109">Towary skonfigurowane pod kątem rozpoznawania przychodu nie powinny być dodawane do zamówień ani transakcji tworzonych w kanałach Commerce.</span><span class="sxs-lookup"><span data-stu-id="a1a56-109">Items configured with revenue recognition should not be added to orders or transactions created in Commerce channels.</span></span>

<span data-ttu-id="a1a56-110">Proces rozpoznawania przychodu może generalnie służyć do wykonywania następujących zadań:</span><span class="sxs-lookup"><span data-stu-id="a1a56-110">In general, the revenue recognition process can be used to perform these tasks:</span></span>

* <span data-ttu-id="a1a56-111">Alokowanie przychodu, aby odpowiednia cena przychodu została rozpoznana na podstawie wartości składników w zamówieniach wieloskładnikowych.</span><span class="sxs-lookup"><span data-stu-id="a1a56-111">Allocate revenue, to help ensure that the appropriate revenue price is recognized, based on the value of the components on multi-element orders.</span></span>
* <span data-ttu-id="a1a56-112">Odraczanie przychodu na podstawie harmonogramu przychodu, który reprezentuje uzgodniony w umowie przedział czasowy, i udziały procentowe rozpoznawania przychodu z biegiem czasu.</span><span class="sxs-lookup"><span data-stu-id="a1a56-112">Defer revenue, based on a revenue schedule that represents the contractual time frame and percentages for recognizing revenue over time.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44iER]

<span data-ttu-id="a1a56-113">Film [Sposób korzystania z rozpoznawania przychodów w aplikacji Dynamics 365 Finance](https://youtu.be/v3amIsiqvoo) (widoczny powyżej) znajduje się na [liście odtwarzania aplikacji Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) dostępnej w witrynie YouTube.</span><span class="sxs-lookup"><span data-stu-id="a1a56-113">The [How to use revenue recognition in Dynamics 365 Finance](https://youtu.be/v3amIsiqvoo) video (shown above) is included in the [Finance and Operations playlist](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) available on YouTube.</span></span>

<span data-ttu-id="a1a56-114">Funkcja Rozpoznawanie przychodu tworzy elastyczną strukturę, która umożliwia określanie reguł rozpoznawania zarówno ceny przychodu, jak i harmonogramu przychodu na poziomie danej firmy.</span><span class="sxs-lookup"><span data-stu-id="a1a56-114">The Revenue recognition feature provides a flexible framework that lets you define company-specific rules for recognizing both the revenue price and the revenue schedule.</span></span>

<span data-ttu-id="a1a56-115">Zwolnione produkty służą do obsługi rozpoznawania przychodu w dokumentach zamówień sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="a1a56-115">Released products are used to support revenue recognition on sales order documents.</span></span> <span data-ttu-id="a1a56-116">Zwolnione produkty zawierają ustawienia wymagane do określenia ceny przychodu i harmonogramu przychodów.</span><span class="sxs-lookup"><span data-stu-id="a1a56-116">The released products contain the setup that is required to determine the revenue price and the revenue schedule.</span></span> <span data-ttu-id="a1a56-117">Zamówienie sprzedaży może pochodzić z projektu typu czas i materiały.</span><span class="sxs-lookup"><span data-stu-id="a1a56-117">The sales order can originate from a Time and materials project.</span></span>

<span data-ttu-id="a1a56-118">Firmy mogą używać funkcji harmonogramu przychodów bez korzystania z funkcji ceny przychodu.</span><span class="sxs-lookup"><span data-stu-id="a1a56-118">Companies can use the revenue schedule functionality without using the revenue price functionality.</span></span> <span data-ttu-id="a1a56-119">W związku z tym cena w wierszach zamówienia sprzedaży zawsze zostanie użyta jako przychód lub odroczony przychód.</span><span class="sxs-lookup"><span data-stu-id="a1a56-119">Therefore, the price on the sales order lines will be used as either revenue or deferred revenue.</span></span> <span data-ttu-id="a1a56-120">Jeśli w wierszu zamówienia sprzedaży istnieje harmonogram przychodów, cena w wierszu zamówienia sprzedaży zostanie odroczona.</span><span class="sxs-lookup"><span data-stu-id="a1a56-120">If a revenue schedule exists on the sales order line, the price on the sales order line will be deferred.</span></span> <span data-ttu-id="a1a56-121">Jeśli wiersz zamówienia sprzedaży nie zawiera harmonogramu przychodów, cena w wierszu zamówienia sprzedaży zostanie zaksięgowana na koncie przychodów po zafakturowaniu.</span><span class="sxs-lookup"><span data-stu-id="a1a56-121">If a revenue schedule doesn't exist on the sales order line, the price on the sales order line will be posted to a revenue account when it's invoiced.</span></span>

<span data-ttu-id="a1a56-122">Cena przychodu jest obliczana w momencie zatwierdzenia zamówienia sprzedaży albo zaksięgowania faktury.</span><span class="sxs-lookup"><span data-stu-id="a1a56-122">The revenue price is calculated either when the sales order is confirmed or when the invoice is posted.</span></span> <span data-ttu-id="a1a56-123">Aby wyświetlić podgląd ceny przychodu przed zaksięgowaniem faktury, należy potwierdzić zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="a1a56-123">To preview the revenue price before the invoice is posted, you must confirm the sales order.</span></span>

<span data-ttu-id="a1a56-124">Po potwierdzeniu zamówienia sprzedaży jest również tworzony oczekiwany harmonogram przychodów, jeśli dowolny wiersz zamówienia sprzedaży zawiera harmonogram przychodów.</span><span class="sxs-lookup"><span data-stu-id="a1a56-124">When the sales order is confirmed, an expected revenue schedule is also created if any sales order line has a revenue schedule.</span></span> <span data-ttu-id="a1a56-125">Po zafakturowaniu zamówienia sprzedaży oczekiwany harmonogram przychodów zostanie usunięty i zastąpiony rzeczywistym harmonogramem rozpoznawania przychodów.</span><span class="sxs-lookup"><span data-stu-id="a1a56-125">When the sales order is invoiced, the expected revenue schedule is deleted, and the expected revenue schedule is replaced with the actual revenue recognition schedule.</span></span>

<span data-ttu-id="a1a56-126">Szczegóły harmonogramu rozpoznawania przychodu są obsługiwane dla każdego wiersza zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="a1a56-126">The details of the revenue recognition schedule are maintained for each sales order line.</span></span> <span data-ttu-id="a1a56-127">W związku z tym menedżer rozpoznawania przychodu może wyświetlać szczegóły i zwalniać wiersze do przychodu, gdy zobowiązanie umowne zostanie zrealizowane.</span><span class="sxs-lookup"><span data-stu-id="a1a56-127">Therefore, the revenue recognition manager can view the details and can release lines to revenue when the contractual obligation has been completed.</span></span> <span data-ttu-id="a1a56-128">Na koniec każdego okresu menedżer rozpoznawania przychodu może utworzyć arkusz przychodów w celu zwolnienia wierszy harmonogramu, które są należne w wyznaczonym przez niego dniu lub wcześniej.</span><span class="sxs-lookup"><span data-stu-id="a1a56-128">At the end of each period, the revenue recognition manager can create a revenue journal to release any schedule lines that are due on or before a date they define.</span></span> <span data-ttu-id="a1a56-129">Ten arkusz przychodów nie jest natychmiast księgowany.</span><span class="sxs-lookup"><span data-stu-id="a1a56-129">This revenue journal isn't posted immediately.</span></span> <span data-ttu-id="a1a56-130">W związku z tym menedżer rozpoznawania przychodu może sprawdzić, czy kwoty zwalniane z odroczonego do rzeczywistego przychodu są poprawne.</span><span class="sxs-lookup"><span data-stu-id="a1a56-130">Therefore, the revenue recognition manager can verify that the correct amounts are being released from deferred revenue to actual revenue.</span></span>

<span data-ttu-id="a1a56-131">Jeśli zmiana umowna spowoduje dodanie nowego wiersza zamówienia sprzedaży do istniejącego zamówienia sprzedaży lub nowego zamówienia sprzedaży, można uruchomić proces zmiany alokacji w celu skorygowania ceny przychodu we wszystkich wierszach zamówień sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="a1a56-131">If a contractual change causes a new sales order line to be added either to the existing sales order or a new sales order, a reallocation process can be run to correct the revenue price across all lines on the sales orders.</span></span>
