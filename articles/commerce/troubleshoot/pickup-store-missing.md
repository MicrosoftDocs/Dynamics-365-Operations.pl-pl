---
title: Sklep detaliczny nie jest wyświetlany na liście sklepów, z których ma być odbiór
description: Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku, gdy sklep detaliczny nie jest wyświetlany na liście sklepów, w których można odbierać towary.
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
ms.openlocfilehash: 9974b3e10bbdcd2e8a8723a3be4b70401bb9e546
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801610"
---
# <a name="retail-store-doesnt-appear-in-the-list-of-stores-to-pick-up-from"></a><span data-ttu-id="a62da-103">Sklep detaliczny nie jest wyświetlany na liście sklepów, z których ma być odbiór</span><span class="sxs-lookup"><span data-stu-id="a62da-103">Retail store doesn't appear in the list of stores to pick up from</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a62da-104">Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku, gdy sklep detaliczny nie jest wyświetlany na liście sklepów, w których można odbierać towary.</span><span class="sxs-lookup"><span data-stu-id="a62da-104">This topic provides troubleshooting guidance that can help when a retail store doesn't appear in the list of stores where items can be picked up.</span></span>

## <a name="description"></a><span data-ttu-id="a62da-105">opis</span><span class="sxs-lookup"><span data-stu-id="a62da-105">Description</span></span>

<span data-ttu-id="a62da-106">Sklep detaliczny nie jest wyświetlany na liście sklepów, w których towary mogą zostać odebrane.</span><span class="sxs-lookup"><span data-stu-id="a62da-106">A retail store doesn't appear in the list of stores where items can be picked up.</span></span>

## <a name="resolution"></a><span data-ttu-id="a62da-107">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="a62da-107">Resolution</span></span>

### <a name="configure-the-longitude-and-latitude-for-the-store-address-in-commerce-headquarters"></a><span data-ttu-id="a62da-108">Konfigurowanie długości geograficznej i szerokości geograficznej dla adresu sklepu w programie Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="a62da-108">Configure the longitude and latitude for the store address in Commerce headquarters</span></span>

<span data-ttu-id="a62da-109">Aby skonfigurować długość i szerokość geograficzną adresu sklepu w siedzibie Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a62da-109">To configure the longitude and latitude for the store address in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="a62da-110">Wybierz kolejno opcje **Handel detaliczny i inny \> Kanały \> Sklepy \> Wszystkie sklepy**.</span><span class="sxs-lookup"><span data-stu-id="a62da-110">Go to **Retail and Commerce \> Channels \> Stores \> All stores**.</span></span>
1. <span data-ttu-id="a62da-111">Znajdź sklep, który ma być wyświetlany wśród opcji pobrania w witrynie e-commerce.</span><span class="sxs-lookup"><span data-stu-id="a62da-111">Find the store that you want to appear among the pickup options on the e-commerce site.</span></span> <span data-ttu-id="a62da-112">Należy zwrócić uwagę na wartość **Numeru jednostki operacyjnej**.</span><span class="sxs-lookup"><span data-stu-id="a62da-112">Make a note of its **Operating unit number** value.</span></span>
1. <span data-ttu-id="a62da-113">Wybierz kolejno opcje **Administrowanie organizacją \> Organizacje \> Jednostki operacyjne**.</span><span class="sxs-lookup"><span data-stu-id="a62da-113">Go to **Organization administration \> Organizations \> Operating units**.</span></span>
1. <span data-ttu-id="a62da-114">Wyszukaj numer jednostki operacyjnej, opisano wcześniej, a następnie wybierz jednostkę operacyjną w wynikach wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="a62da-114">Search for the operating unit number that you noted earlier, and then select the operating unit in the search results.</span></span>
1. <span data-ttu-id="a62da-115">Na skróconej karcie **Adresy** wybierz opcję **Więcej opcji**, a następnie wybierz pozycję **Zaawansowane**.</span><span class="sxs-lookup"><span data-stu-id="a62da-115">On the **Addresses** FastTab, select **More options**, and then select **Advanced**.</span></span>
1. <span data-ttu-id="a62da-116">Na skróconej karcie **Ogólne** upewnij się, że pola **Długość** i **Szerokość** są poprawnie ustawione.</span><span class="sxs-lookup"><span data-stu-id="a62da-116">On the **General** FastTab, make sure that the **Longitude** and **Latitude** fields are correctly set.</span></span> <span data-ttu-id="a62da-117">W ramach tego kroku upewnij się, że wartości zostały poprawnie określone jako liczby dodatnie lub ujemne.</span><span class="sxs-lookup"><span data-stu-id="a62da-117">As part of this step, make sure that the values are correctly specified as positive or negative numbers.</span></span>

### <a name="configure-fulfillment-groups-in-commerce-headquarters"></a><span data-ttu-id="a62da-118">Konfigurowanie grup realizacji w programie Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="a62da-118">Configure fulfillment groups in Commerce headquarters</span></span>

<span data-ttu-id="a62da-119">Aby skonfigurować grupy realizacji w Commerce headquarters, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a62da-119">To configure fulfillment groups in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="a62da-120">Wybierz kolejno opcje **Commerce \> Kanały \> Sklepy internetowe**.</span><span class="sxs-lookup"><span data-stu-id="a62da-120">Go to **Retail and Commerce \> Channels \> Online stores**.</span></span>
1. <span data-ttu-id="a62da-121">Wybierz sklep internetowy do skonfigurowania.</span><span class="sxs-lookup"><span data-stu-id="a62da-121">Select the online store to configure.</span></span>
1. <span data-ttu-id="a62da-122">W okienku akcji wybierz kartę **Konfiguracja** i wybierz opcję **Przypisanie grupy realizacji**.</span><span class="sxs-lookup"><span data-stu-id="a62da-122">On the Action Pane, select **Set up**, and then select **Fulfillment group assignment**.</span></span>
1. <span data-ttu-id="a62da-123">Na stronie **Przypisania grupy realizacji** wybierz grupę realizacji dla sklepu internetowego.</span><span class="sxs-lookup"><span data-stu-id="a62da-123">On the **Fulfillment group assignment** page, select the fulfillment group for the online store.</span></span>
1. <span data-ttu-id="a62da-124">W obszarze **Ustawienia** upewnij się, że sklep sieci sprzedaży jest poprawnie skonfigurowany dla grupy realizacji.</span><span class="sxs-lookup"><span data-stu-id="a62da-124">Under **Setup**, make sure that the retail store is correctly configured for the fulfillment group.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a62da-125">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="a62da-125">Additional resources</span></span> 

[<span data-ttu-id="a62da-126">Tworzenie jednostki operacyjnej</span><span class="sxs-lookup"><span data-stu-id="a62da-126">Create an operating unit</span></span>](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit)

[<span data-ttu-id="a62da-127">Konfigurowanie kanału online</span><span class="sxs-lookup"><span data-stu-id="a62da-127">Set up an online channel</span></span>](../channel-setup-online.md)
