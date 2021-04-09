---
title: Konfigurowanie i przetwarzanie wymiany w przypadku zamówienia zwrotu
description: W tym temacie wyjaśniono sposób konfigurowania wymiany w przypadku zwrotu w rozwiązaniu Dynamics 365 Commerce.
author: josaw1
ms.date: 11/12/2018
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 46d6e912aca64951da2865f5609a9dc22fbbcbe3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5804608"
---
# <a name="configure-and-process-an-exchange-on-a-return-order"></a><span data-ttu-id="b5870-103">Konfigurowanie i przetwarzanie wymiany w przypadku zamówienia zwrotu</span><span class="sxs-lookup"><span data-stu-id="b5870-103">Configure and process an exchange on a return order</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b5870-104">W poprzednich wersjach rozwiązania Dynamics 365 Commerce zwroty dotyczące zamówień klientów były przetwarzane przy użyciu dokumentu zamówienia zwrotu w centrali.</span><span class="sxs-lookup"><span data-stu-id="b5870-104">In previous versions of Dynamics 365 Commerce, returns against customer orders were processed by using the return order document in Headquarters.</span></span> <span data-ttu-id="b5870-105">Jednak dokumenty zamówienia zwrotu mogą być używane tylko do przetwarzania produktów zwracanych.</span><span class="sxs-lookup"><span data-stu-id="b5870-105">However, the return order document can be used to process only products that are being returned.</span></span> <span data-ttu-id="b5870-106">Zwracane produkty są oznaczone ilością ujemną w wierszach zamówień zwrotu.</span><span class="sxs-lookup"><span data-stu-id="b5870-106">The returned products are indicated by a negative quantity on the return order lines.</span></span> <span data-ttu-id="b5870-107">Z drugiej strony sprzedaż jest wskazywana przez ilość dodatnią.</span><span class="sxs-lookup"><span data-stu-id="b5870-107">By contrast, sales are indicated by a positive quantity.</span></span> <span data-ttu-id="b5870-108">Dokument zamówienia zwrotu nie obsługuje jednak ilości dodatnich.</span><span class="sxs-lookup"><span data-stu-id="b5870-108">However, the return order document doesn't support positive quantities.</span></span> <span data-ttu-id="b5870-109">Ze względu na to ograniczenie w poprzednich wersjach aplikacji nie były obsługiwane sytuacje, w których wymiana produktu była dokonywana przy użyciu dokumentu zamówienia zwrotu.</span><span class="sxs-lookup"><span data-stu-id="b5870-109">Because of this limitation, previous versions of the app didn't support scenarios where product exchanges are done by using the return order document.</span></span>

<span data-ttu-id="b5870-110">Dodano jednak funkcję w celu obsługi sytuacji, w których wymiana odbywa się z wykorzystaniem zamówień zwrotu.</span><span class="sxs-lookup"><span data-stu-id="b5870-110">However, functionality has been added to support scenarios where exchanges are done on return orders.</span></span> <span data-ttu-id="b5870-111">Aby przetwarzać tego typu transakcje w aplikacji Commerce jest obecnie używany dokument zamówienia sprzedaży zamiast dokumentu zamówienia zwrotu.</span><span class="sxs-lookup"><span data-stu-id="b5870-111">Commerce now uses the sales order document instead of the return order document to process these types of transactions.</span></span>

## <a name="configure-commerce-to-support-exchanges-on-return-orders"></a><span data-ttu-id="b5870-112">Konfigurowanie aplikacji Commerce pod kątem obsługi wymiany w przypadku zamówień zwrotu</span><span class="sxs-lookup"><span data-stu-id="b5870-112">Configure Commerce to support exchanges on return orders</span></span>

<span data-ttu-id="b5870-113">Aby skonfigurować system do obsługi wymiany w przypadku zamówień zwrotu, należy wykonać poniższe czynności.</span><span class="sxs-lookup"><span data-stu-id="b5870-113">Follow these steps to configure the system to support exchanges on return orders.</span></span>

1. <span data-ttu-id="b5870-114">Kliknij kolejno opcje **Retail i Commerce \> Ustawienia centrali \> Parametry \> Parametry handlowe**.</span><span class="sxs-lookup"><span data-stu-id="b5870-114">Go to **Retail and Commerce \> Headquarters setup \> Parameters \> Commerce parameters**.</span></span> <span data-ttu-id="b5870-115">Na skróconej karcie **Zamówienia odbiorcy** ustaw wartość **Tak** opcji **Przetwarzanie zamówień zwrotu jako zamówień sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="b5870-115">On the **Customer orders** FastTab, set the **Process return orders as sales orders** option to **Yes**.</span></span>
2. <span data-ttu-id="b5870-116">Uruchom zadanie **Harmonogram dystrybucji konfiguracji globalnej** (**1110**).</span><span class="sxs-lookup"><span data-stu-id="b5870-116">Run the **Global configuration distribution schedule** job (**1110**).</span></span>

## <a name="make-an-exchange"></a><span data-ttu-id="b5870-117">Dokonywanie wymiany</span><span class="sxs-lookup"><span data-stu-id="b5870-117">Make an exchange</span></span>

<span data-ttu-id="b5870-118">Po skonfigurowaniu systemu w sposób opisany w poprzedniej sekcji użytkownik punktu sprzedaży (POS), aby przetworzyć zwrot, będzie w dalszym ciągu musiał wybrać zamówienie sprzedaży lub fakturę sprzedaży, podobnie jak w poprzednich wersjach aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b5870-118">After the system is configured as described in the previous section, the point of sale (POS) user will still select a sales order or sales invoice to process a return, as in previous versions of the app.</span></span> <span data-ttu-id="b5870-119">Jednak po dodaniu zwracanych pozycji do koszyka, użytkownik będzie mógł dodawać nowe wiersze sprzedaży do koszyka.</span><span class="sxs-lookup"><span data-stu-id="b5870-119">However, after the return items are added to the cart, the user will be able to add new sales lines to the cart.</span></span>

<span data-ttu-id="b5870-120">Dla tych nowych wierszy sprzedaży użytkownik musi zdefiniować wszystkie atrybuty, które są wymagane w celu przetworzenia wiersza zamówienia odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="b5870-120">For these new sales lines, the user must define all the attributes that are required in order to process a customer order line.</span></span> <span data-ttu-id="b5870-121">Do tych atrybutów należy metoda dostawy i lokalizacja realizacji.</span><span class="sxs-lookup"><span data-stu-id="b5870-121">These attributes include the delivery method and fulfillment location.</span></span> <span data-ttu-id="b5870-122">Płatność należna za transakcję będzie kwotą netto wierszy zamówienia zwrotu i wierszy zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="b5870-122">The payment that is due for the transaction will be a net of the return order lines and sales order lines.</span></span> <span data-ttu-id="b5870-123">Po przekazaniu płatności za transakcję zamówienie zwrotu zostanie zaksięgowane w centrali jako dokument zamówienia sprzedaży, a w systemie zostanie natychmiast wystawiona faktura dotycząca wierszy zwrotu.</span><span class="sxs-lookup"><span data-stu-id="b5870-123">When payment is tendered for the transaction, the return order will be posted as a sales order document in Headquarters, and the system will immediately invoice the return lines.</span></span>

<span data-ttu-id="b5870-124">Aby zapewnić lepszą widoczność różnych kwot w koszyku, zostały w nim dodane trzy nowe pola kwoty.</span><span class="sxs-lookup"><span data-stu-id="b5870-124">To provide better visibility into the various amounts for the cart, three new amount fields have been added to the cart.</span></span> <span data-ttu-id="b5870-125">W celu udostępnienia tych nowych pól w interfejsie użytkownika (UI) punktu sprzedaży można użyć projektanta układu ekranu.</span><span class="sxs-lookup"><span data-stu-id="b5870-125">You can use the screen designer to make these new fields available in the POS user interface (UI).</span></span>

- <span data-ttu-id="b5870-126">**Zastosowana kaucja** — kwota kaucji, która jest stosowana do transakcji, gdy użytkownik pobiera zamówienie odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="b5870-126">**Deposit applied** – The deposit amount that is applied on a transaction when the user does a customer order pickup.</span></span> <span data-ttu-id="b5870-127">Jeśli nie określono żadnych zastąpień kaucji oraz została skonfigurowana kaucja 10-procentowa, to kwota w tym polu stanowi 90 procent sumy zamówienia odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="b5870-127">If there is no deposit override, and a 10-percent deposit is configured, the amount in this field is 90 percent of the total amount of the customer order.</span></span>
- <span data-ttu-id="b5870-128">**Kwota zrealizowana** — łączna kwota dla wierszy, w których ustawiono metodę dostawy **Wyniesienie**, gdy zamówienie klienta zostało utworzone lub zmodyfikowane albo podczas wymiany zamówienia odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="b5870-128">**Carry out amount** – The total amount for lines where the delivery mode was set to **Carry out** when the customer order was created or edited, or during a customer order exchange.</span></span> <span data-ttu-id="b5870-129">Kwota w tym polu obejmuje podatki i opłaty.</span><span class="sxs-lookup"><span data-stu-id="b5870-129">The amount in this field includes taxes and charges.</span></span>
- <span data-ttu-id="b5870-130">**Kwota zwrotu** — suma dla wierszy, które zawierają ilości ujemne podczas wymiany zamówienia odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="b5870-130">**Return amount** – The total amount for lines that have negative quantities during the customer order exchange.</span></span> <span data-ttu-id="b5870-131">Kwota w tym polu obejmuje podatki i opłaty.</span><span class="sxs-lookup"><span data-stu-id="b5870-131">The amount in this field includes taxes and charges.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]