---
title: Sklep detaliczny nie jest wyświetlany na liście sklepów, z których ma być odbiór
description: Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku, gdy sklep detaliczny nie jest wyświetlany na liście sklepów, w których można odbierać towary.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
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
ms.openlocfilehash: ad7ddf8a17640471a2344c45eef76f682d29ef2b
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020834"
---
# <a name="retail-store-doesnt-appear-in-the-list-of-stores-to-pick-up-from"></a><span data-ttu-id="7511c-103">Sklep detaliczny nie jest wyświetlany na liście sklepów, z których ma być odbiór</span><span class="sxs-lookup"><span data-stu-id="7511c-103">Retail store doesn't appear in the list of stores to pick up from</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7511c-104">Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku, gdy sklep detaliczny nie jest wyświetlany na liście sklepów, w których można odbierać towary.</span><span class="sxs-lookup"><span data-stu-id="7511c-104">This topic provides troubleshooting guidance that can help when a retail store doesn't appear in the list of stores where items can be picked up.</span></span>

## <a name="description"></a><span data-ttu-id="7511c-105">opis</span><span class="sxs-lookup"><span data-stu-id="7511c-105">Description</span></span>

<span data-ttu-id="7511c-106">Sklep detaliczny nie jest wyświetlany na liście sklepów, w których towary mogą zostać odebrane.</span><span class="sxs-lookup"><span data-stu-id="7511c-106">A retail store doesn't appear in the list of stores where items can be picked up.</span></span>

## <a name="resolution"></a><span data-ttu-id="7511c-107">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="7511c-107">Resolution</span></span>

### <a name="configure-the-longitude-and-latitude-for-the-store-address-in-commerce-headquarters"></a><span data-ttu-id="7511c-108">Konfigurowanie długości geograficznej i szerokości geograficznej dla adresu sklepu w programie Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="7511c-108">Configure the longitude and latitude for the store address in Commerce headquarters</span></span>

<span data-ttu-id="7511c-109">Aby skonfigurować długość i szerokość geograficzną adresu sklepu w siedzibie Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="7511c-109">To configure the longitude and latitude for the store address in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="7511c-110">Wybierz kolejno opcje **Handel detaliczny i inny \> Kanały \> Sklepy \> Wszystkie sklepy**.</span><span class="sxs-lookup"><span data-stu-id="7511c-110">Go to **Retail and Commerce \> Channels \> Stores \> All stores**.</span></span>
1. <span data-ttu-id="7511c-111">Znajdź sklep, który ma być wyświetlany wśród opcji pobrania w witrynie e-commerce.</span><span class="sxs-lookup"><span data-stu-id="7511c-111">Find the store that you want to appear among the pickup options on the e-commerce site.</span></span> <span data-ttu-id="7511c-112">Należy zwrócić uwagę na wartość **Numeru jednostki operacyjnej**.</span><span class="sxs-lookup"><span data-stu-id="7511c-112">Make a note of its **Operating unit number** value.</span></span>
1. <span data-ttu-id="7511c-113">Wybierz kolejno opcje **Administrowanie organizacją \> Organizacje \> Jednostki operacyjne**.</span><span class="sxs-lookup"><span data-stu-id="7511c-113">Go to **Organization administration \> Organizations \> Operating units**.</span></span>
1. <span data-ttu-id="7511c-114">Wyszukaj numer jednostki operacyjnej, opisano wcześniej, a następnie wybierz jednostkę operacyjną w wynikach wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="7511c-114">Search for the operating unit number that you noted earlier, and then select the operating unit in the search results.</span></span>
1. <span data-ttu-id="7511c-115">Na skróconej karcie **Adresy** wybierz opcję **Więcej opcji**, a następnie wybierz pozycję **Zaawansowane**.</span><span class="sxs-lookup"><span data-stu-id="7511c-115">On the **Addresses** FastTab, select **More options**, and then select **Advanced**.</span></span>
1. <span data-ttu-id="7511c-116">Na skróconej karcie **Ogólne** upewnij się, że pola **Długość** i **Szerokość** są poprawnie ustawione.</span><span class="sxs-lookup"><span data-stu-id="7511c-116">On the **General** FastTab, make sure that the **Longitude** and **Latitude** fields are correctly set.</span></span> <span data-ttu-id="7511c-117">W ramach tego kroku upewnij się, że wartości zostały poprawnie określone jako liczby dodatnie lub ujemne.</span><span class="sxs-lookup"><span data-stu-id="7511c-117">As part of this step, make sure that the values are correctly specified as positive or negative numbers.</span></span>

### <a name="configure-fulfillment-groups-in-commerce-headquarters"></a><span data-ttu-id="7511c-118">Konfigurowanie grup realizacji w programie Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="7511c-118">Configure fulfillment groups in Commerce headquarters</span></span>

<span data-ttu-id="7511c-119">Aby skonfigurować grupy realizacji w Commerce headquarters, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="7511c-119">To configure fulfillment groups in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="7511c-120">Wybierz kolejno opcje **Commerce \> Kanały \> Sklepy internetowe**.</span><span class="sxs-lookup"><span data-stu-id="7511c-120">Go to **Retail and Commerce \> Channels \> Online stores**.</span></span>
1. <span data-ttu-id="7511c-121">Wybierz sklep internetowy do skonfigurowania.</span><span class="sxs-lookup"><span data-stu-id="7511c-121">Select the online store to configure.</span></span>
1. <span data-ttu-id="7511c-122">W okienku akcji wybierz kartę **Konfiguracja** i wybierz opcję **Przypisanie grupy realizacji**.</span><span class="sxs-lookup"><span data-stu-id="7511c-122">On the Action Pane, select **Set up**, and then select **Fulfillment group assignment**.</span></span>
1. <span data-ttu-id="7511c-123">Na stronie **Przypisania grupy realizacji** wybierz grupę realizacji dla sklepu internetowego.</span><span class="sxs-lookup"><span data-stu-id="7511c-123">On the **Fulfillment group assignment** page, select the fulfillment group for the online store.</span></span>
1. <span data-ttu-id="7511c-124">W obszarze **Ustawienia** upewnij się, że sklep sieci sprzedaży jest poprawnie skonfigurowany dla grupy realizacji.</span><span class="sxs-lookup"><span data-stu-id="7511c-124">Under **Setup**, make sure that the retail store is correctly configured for the fulfillment group.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7511c-125">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="7511c-125">Additional resources</span></span> 

[<span data-ttu-id="7511c-126">Tworzenie jednostki operacyjnej</span><span class="sxs-lookup"><span data-stu-id="7511c-126">Create an operating unit</span></span>](../../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md)

[<span data-ttu-id="7511c-127">Konfigurowanie kanału online</span><span class="sxs-lookup"><span data-stu-id="7511c-127">Set up an online channel</span></span>](../channel-setup-online.md)