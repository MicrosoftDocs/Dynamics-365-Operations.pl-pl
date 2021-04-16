---
title: Określ kurs krzyżowy
description: Ten temat zawiera informacje o kursach krzyżowych w Microsoft Dynamics 365 Finance.
author: abruer
ms.date: 05/16/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: eafaf660470cec5fd82454660f2f59b86d488d0c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5810301"
---
# <a name="specify-the-cross-rate"></a><span data-ttu-id="9d064-103">Określ kurs krzyżowy</span><span class="sxs-lookup"><span data-stu-id="9d064-103">Specify the cross rate</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9d064-104">W tym temacie wyjaśniono przeznaczenie kursu krzyżowego oraz sposobu określania kursu krzyżowego, gdy płatność jest rozliczana z fakturą.</span><span class="sxs-lookup"><span data-stu-id="9d064-104">This topic explains the purpose of a cross rate, and how to specify the cross rate when you settle a payment with an invoice.</span></span> <span data-ttu-id="9d064-105">Użyć kursu krzyżowego podczas stosowania wszystkich poniższych kryteriów:</span><span class="sxs-lookup"><span data-stu-id="9d064-105">Use a cross rate when all of the following criteria apply:</span></span> 
-   <span data-ttu-id="9d064-106">W przypadku rozliczania płatności z faktury.</span><span class="sxs-lookup"><span data-stu-id="9d064-106">You are settling a payment with an invoice.</span></span> 
-   <span data-ttu-id="9d064-107">Wiersz płatności i faktura używają różnych walut.</span><span class="sxs-lookup"><span data-stu-id="9d064-107">The payment line and the invoice line use different currencies.</span></span> 
-   <span data-ttu-id="9d064-108">Żadna waluta nie jest walutą rozliczeniową.</span><span class="sxs-lookup"><span data-stu-id="9d064-108">Neither currency is the accounting currency.</span></span> 

<span data-ttu-id="9d064-109">Kurs krzyżowy nie jest używany do obliczania przeliczenia waluty płatności transakcji na walutę rozliczeniową płatności.</span><span class="sxs-lookup"><span data-stu-id="9d064-109">The cross rate is not used to calculate the payment transaction currency translation to the payment accounting currency.</span></span> <span data-ttu-id="9d064-110">Zamiast tego w celu obliczenia kwoty w walucie transakcyjnej płatności i kwoty w walucie rozliczeniowej płatności są pobierane kursy wymiany z tabel kursów wymiany.</span><span class="sxs-lookup"><span data-stu-id="9d064-110">Instead, the exchange rates from the exchange rate tables are retrieved to calculate the value of the payment transaction currency amount and the payment accounting currency amount.</span></span> 

<span data-ttu-id="9d064-111">Na przykład gdy walutą rozliczeniową jest USD, a CAD jest waluta faktury, wtedy płatności waluty dokonywane są w EUR.</span><span class="sxs-lookup"><span data-stu-id="9d064-111">For example, the accounting currency is USD, the invoice currency is CAD, and the payment currency is EUR.</span></span> <span data-ttu-id="9d064-112">Kurs krzyżowy umożliwia wprowadzenie kursu wymiany do przetłumaczenia bezpośrednio między EUR a CAD, a nie jest konieczne tłumaczenie wersji USD.</span><span class="sxs-lookup"><span data-stu-id="9d064-112">The cross rate lets you enter an exchange rate to translate directly between CAD and EUR, and not have to translate through USD.</span></span> <span data-ttu-id="9d064-113">Po wybraniu faktury i płatności głównej dla wiersza faktury można wprowadzić kurs krzyżowy.</span><span class="sxs-lookup"><span data-stu-id="9d064-113">When you select an invoice and a primary payment, you can enter a cross rate for the invoice line.</span></span> <span data-ttu-id="9d064-114">Kurs ten określa przelicznik między walutami transakcji w dniu dokonania rozliczenia.</span><span class="sxs-lookup"><span data-stu-id="9d064-114">The cross rate is the exchange rate between the currencies for those transactions, as of the settlement date.</span></span>

1.  <span data-ttu-id="9d064-115">Przejdź do jednej z następujących stron:</span><span class="sxs-lookup"><span data-stu-id="9d064-115">Go to one of the following pages:</span></span>
- <span data-ttu-id="9d064-116">**Rozrachunki z odbiorcami > Wspólne > Odbiorcy > Wszyscy odbiorcy**</span><span class="sxs-lookup"><span data-stu-id="9d064-116">**Accounts receivable > Common > Customers > All customers**</span></span> 
- <span data-ttu-id="9d064-117">**Rozrachunki z dostawcami > Wspólne > Dostawcy > Wszyscy dostawcy**</span><span class="sxs-lookup"><span data-stu-id="9d064-117">**Accounts payable > Common > Vendors > All vendors**</span></span> 
- <span data-ttu-id="9d064-118">**Zaopatrzenie i sourcing > Wspólne > Dostawcy > Wszyscy dostawcy**</span><span class="sxs-lookup"><span data-stu-id="9d064-118">**Procurement and sourcing > Common > Vendors > All vendors**</span></span>
2.  <span data-ttu-id="9d064-119">Wybierz odbiorcę lub dostawcę, dla którego są rozliczane otwarte transakcje.</span><span class="sxs-lookup"><span data-stu-id="9d064-119">Select the customer or vendor whose open transactions you are settling.</span></span> 
3.  <span data-ttu-id="9d064-120">Dla odbiorcy na stronie listy **Wszyscy odbiorcy** wybierz kolejno opcje **Windykacja > Rozlicz otwarte transakcje**.</span><span class="sxs-lookup"><span data-stu-id="9d064-120">For a customer, on the **All customers** list page, go to **Collect > Settle open transactions**.</span></span> <span data-ttu-id="9d064-121">Dla dostawcy na stronie listy **Wszyscy dostawcy** wybierz kolejno opcje **Faktura > Rozlicz otwarte transakcje**.</span><span class="sxs-lookup"><span data-stu-id="9d064-121">For a vendor, on the **All vendors** list page, go to **Invoice > Settle open transactions**.</span></span> 
4.  <span data-ttu-id="9d064-122">Wybierz transakcję właściwą dla płatności głównej, a następnie kliknij przycisk **Oznacz płatność**.</span><span class="sxs-lookup"><span data-stu-id="9d064-122">Select the transaction that is the primary payment, and then click **Mark payment**.</span></span> <span data-ttu-id="9d064-123">Pole wyboru w kolumnie **Zaznacz** jest zaznaczone, a ikona informacji jest wyświetlana w kolumnie **Płatność główna**.</span><span class="sxs-lookup"><span data-stu-id="9d064-123">The check box in the **Mark** column is selected, and an information icon is shown in the **Primary payment** column.</span></span> 
5.  <span data-ttu-id="9d064-124">W polu **Kurs krzyżowy** wprowadź przelicznik między walutą faktury a walutą płatności na dzień dokonania rozliczenia.</span><span class="sxs-lookup"><span data-stu-id="9d064-124">In the **Cross rate** field, enter the exchange rate between the invoice currency and the payment currency, as of the settlement date.</span></span> 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]