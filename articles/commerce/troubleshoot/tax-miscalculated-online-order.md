---
title: Podatki w zamówieniach online są niepoprawnie obliczone
description: Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w nieprawidłowym obliczniu podatków od zamówień online lub gdy grupa podatków w wierszu sprzedaży nie jest poprawnie ustawiona.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 7f71add679e1d24f80db8ce3990058b591128ec1
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801418"
---
# <a name="taxes-on-online-orders-are-incorrectly-calculated"></a><span data-ttu-id="a2f31-103">Podatki w zamówieniach online są niepoprawnie obliczone</span><span class="sxs-lookup"><span data-stu-id="a2f31-103">Taxes on online orders are incorrectly calculated</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a2f31-104">Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w nieprawidłowym obliczniu podatków od zamówień online lub gdy grupa podatków w wierszu sprzedaży nie jest poprawnie ustawiona.</span><span class="sxs-lookup"><span data-stu-id="a2f31-104">This topic provides troubleshooting guidance that can help when taxes on online orders are incorrectly calculated, or when the tax group on the sales line isn't correctly set.</span></span>

## <a name="description"></a><span data-ttu-id="a2f31-105">opis</span><span class="sxs-lookup"><span data-stu-id="a2f31-105">Description</span></span>

<span data-ttu-id="a2f31-106">Po umieszczeniu zamówienia w sieci e-commerce podatki są niepoprawnie obliczone lub grupa podatków w wierszu sprzedaży jest niepoprawnie ustawiona.</span><span class="sxs-lookup"><span data-stu-id="a2f31-106">When an e-commerce order is placed, the taxes are incorrectly calculated, or the tax group on the sales line is incorrectly set.</span></span>

## <a name="resolution"></a><span data-ttu-id="a2f31-107">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="a2f31-107">Resolution</span></span>

### <a name="configure-the-sales-tax-for-a-retail-store-in-commerce-headquarters"></a><span data-ttu-id="a2f31-108">Konfigurowanie podatku dla sklepu detalicznego w programie Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="a2f31-108">Configure the sales tax for a retail store in Commerce headquarters</span></span>

<span data-ttu-id="a2f31-109">Aby skonfigurować podatek od sprzedaży dla sklepu detalicznego w siedzibie Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a2f31-109">To configure the sales tax for a retail store in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="a2f31-110">Wybierz kolejno opcje **Handel detaliczny i inny \> Kanały \> Wszystkie sklepy**.</span><span class="sxs-lookup"><span data-stu-id="a2f31-110">Go to **Retail and Commerce \> Channels \> All stores**.</span></span>
1. <span data-ttu-id="a2f31-111">Wybierz sklep, dla który ma zostać skonfigurowany podatek.</span><span class="sxs-lookup"><span data-stu-id="a2f31-111">Select the store to configure sales tax for.</span></span>
1. <span data-ttu-id="a2f31-112">Na skróconej karcie **Ogólne** w sekcji **Podatek** skonfiguruj informacje o podatku dla sklepu.</span><span class="sxs-lookup"><span data-stu-id="a2f31-112">On the **General** FastTab, in the **Sales tax** section, configure the sales tax information for the store.</span></span>

> [!NOTE]
> <span data-ttu-id="a2f31-113">W przypadku pobrania produktu ze sklepu grupa podatków pochodzi ze sklepu wybranego do pobrania.</span><span class="sxs-lookup"><span data-stu-id="a2f31-113">For product pickup from a store, the tax group comes from the store that is selected for pickup.</span></span> <span data-ttu-id="a2f31-114">Aby uzyskać więcej informacji, zobacz [Ustawianie innych opcji podatków dla sklepów](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).</span><span class="sxs-lookup"><span data-stu-id="a2f31-114">For more information, see [Set other tax options for stores](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).</span></span>

### <a name="configure-the-sales-tax-for-a-customers-address-in-commerce-headquarters"></a><span data-ttu-id="a2f31-115">Skonfiguruj podatek od sprzedaży dla adresu klienta w siedzibie Commerce</span><span class="sxs-lookup"><span data-stu-id="a2f31-115">Configure the sales tax for a customer's address in Commerce headquarters</span></span>

<span data-ttu-id="a2f31-116">Aby skonfigurować podatek od sprzedaży dla adresu klienta w siedzibie Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a2f31-116">To configure the sales tax for a customer's address in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="a2f31-117">Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Odbiorcy \> Wszyscy odbiorcy**.</span><span class="sxs-lookup"><span data-stu-id="a2f31-117">Go to **Accounts receivable \> Customers \> All customers**.</span></span>
1. <span data-ttu-id="a2f31-118">Wybierz klienta, dla którego chcesz skonfigurować podatki od sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="a2f31-118">Select the customer to configure sales taxes for.</span></span>
1. <span data-ttu-id="a2f31-119">Na skróconej karcie **Adresy** wybierz adres, dla których chcesz skonfigurować podatki, wybierz opcję **Więcej opcji**, a następnie wybierz opcję **Zaawansowane**.</span><span class="sxs-lookup"><span data-stu-id="a2f31-119">On the **Addresses** FastTab, select the address to configure sales taxes for, select **More options**, and then select **Advanced**.</span></span>
1. <span data-ttu-id="a2f31-120">Na karcie **Ogólne** wybierz **Grupa podatków**.</span><span class="sxs-lookup"><span data-stu-id="a2f31-120">On the **General** FastTab, select the **Tax group**.</span></span>
1. <span data-ttu-id="a2f31-121">W polu **Podatek** wybierz odpowiednią wartość.</span><span class="sxs-lookup"><span data-stu-id="a2f31-121">In the **Sales tax** field, select the appropriate value.</span></span>

> [!NOTE]
> <span data-ttu-id="a2f31-122">W przypadku wysyłki, która obejmuje podatek w adresie odbiorcy, adres dostawy wiersza określa grupę podatków dla wiersza.</span><span class="sxs-lookup"><span data-stu-id="a2f31-122">For shipping that involves sales tax on the customer's address, the delivery address of the line determines the tax group for the line.</span></span> <span data-ttu-id="a2f31-123">Jeśli odbiorca wysyła przesyłkę na istniejący adres, który ma już skonfigurowaną grupę podatków, używana będzie istniejąca grupa podatku.</span><span class="sxs-lookup"><span data-stu-id="a2f31-123">If the customer is shipping to an existing address that has a tax group that is already configured, the existing tax group will be used.</span></span> <span data-ttu-id="a2f31-124">Domyślnie podczas tworzenia adresów nie ma grupy podatków.</span><span class="sxs-lookup"><span data-stu-id="a2f31-124">By default, addresses don't have a tax group when they are created.</span></span>

### <a name="configure-general-sales-tax-groups-in-commerce-headquarters"></a><span data-ttu-id="a2f31-125">Konfigurowanie ogólnych grup podatków w programie Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="a2f31-125">Configure general sales tax groups in Commerce headquarters</span></span>

<span data-ttu-id="a2f31-126">Aby skonfigurować ogólne grupy podatków w Commerce headquarters, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a2f31-126">To configure general sales tax groups in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="a2f31-127">Wybierz kolejno opcje **Podatek \> Podatki pośrednie \> Podatek \> Grupy podatków**.</span><span class="sxs-lookup"><span data-stu-id="a2f31-127">Go to **Tax \> Indirect taxes \> Sales tax \> Sales tax group**.</span></span>
1. <span data-ttu-id="a2f31-128">W lewym okienku wybierz grupę podatków do skonfigurowania.</span><span class="sxs-lookup"><span data-stu-id="a2f31-128">In the left navigation, select the tax group to configure.</span></span>
1. <span data-ttu-id="a2f31-129">Na skróconej karcie **Podatek oparty na lokalizacji detalicznej** skonfiguruj podatki dla grupy podatków.</span><span class="sxs-lookup"><span data-stu-id="a2f31-129">On the **Retail destination based tax** FastTab, configure the taxes for the sales tax group.</span></span>

> [!NOTE]
> <span data-ttu-id="a2f31-130">W przypadku wysyłki, która nie obejmuje podatku w adresie odbiorcy, grupa podatków określa adres dostawy wiersza oraz podatki oparte na lokalizacji docelowej, które są skonfigurowane dla grupy podatków.</span><span class="sxs-lookup"><span data-stu-id="a2f31-130">For shipping that doesn't involve sales tax on the customer's address, the delivery address of the line and the destination-based taxes that are configured for the tax group determine the tax group.</span></span> <span data-ttu-id="a2f31-131">Aby uzyskać więcej informacji, zajrzyj do [Konfigurowanie podatków dla sklepów internetowych w oparciu o miejsce docelowe](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).</span><span class="sxs-lookup"><span data-stu-id="a2f31-131">For more information, see [Set up taxes for online stores based on destination](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a2f31-132">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="a2f31-132">Additional resources</span></span>

[<span data-ttu-id="a2f31-133">Konfigurowanie podatku dla zamówień online</span><span class="sxs-lookup"><span data-stu-id="a2f31-133">Configure sales tax for online orders</span></span>](../sales-tax-config.md)
