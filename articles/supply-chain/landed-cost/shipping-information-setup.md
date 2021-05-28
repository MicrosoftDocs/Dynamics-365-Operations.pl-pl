---
title: Konfiguracja informacji o wysyłce
description: W tym temacie opisano, jak skonfigurować informacje o wysyłce dla modułu Koszt z wyładunkiem.
author: sherry-zheng
ms.date: 12/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMGoodsDescriptionTable, ITMVesselTable, ITMExporterTable, ITMCommodityCodeTable, ITMCustomsDescription
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-04
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 5093e42b0b5247c24c271ad50c80889516586d58
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020894"
---
# <a name="shipping-information-setup"></a><span data-ttu-id="1b864-103">Konfiguracja informacji o wysyłce</span><span class="sxs-lookup"><span data-stu-id="1b864-103">Shipping information setup</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1b864-104">W tym temacie opisano, jak skonfigurować informacje o wysyłce dla modułu **Koszt z wyładunkiem**.</span><span class="sxs-lookup"><span data-stu-id="1b864-104">This topic describes how to set up shipping information for the **Landed cost** module.</span></span>

## <a name="description-of-goods"></a><a name="description-of-goods"></a><span data-ttu-id="1b864-105">Opis towarów</span><span class="sxs-lookup"><span data-stu-id="1b864-105">Description of goods</span></span>

<span data-ttu-id="1b864-106">Opisy towarów ułatwiają identyfikację podróży, kontenera wysyłkowego lub folio towarów i towarów w nich zawarte.</span><span class="sxs-lookup"><span data-stu-id="1b864-106">Descriptions of goods help identify a voyage, shipping container, or folio of goods, and the goods in it.</span></span> <span data-ttu-id="1b864-107">Możesz wybrać opis towarów w nagłówku kontenera wysyłkowego lub nagłówku folio.</span><span class="sxs-lookup"><span data-stu-id="1b864-107">You can select a description of goods on the shipping container header or the folio header.</span></span>

<span data-ttu-id="1b864-108">Aby pracować z opisami towarów, przejdź do **Koszt z wyładunkiem \> Konfiguracja informacji o wysyłce \> Opis towaru**.</span><span class="sxs-lookup"><span data-stu-id="1b864-108">To work with descriptions of goods, go to **Landed cost \> Shipping information setup \> Description of goods**.</span></span> <span data-ttu-id="1b864-109">Można tam wyświetlać, otwierać, tworzyć i usuwać rekordy opisów towarów.</span><span class="sxs-lookup"><span data-stu-id="1b864-109">There, you can view, open, create, and delete records for descriptions of goods.</span></span> <span data-ttu-id="1b864-110">W poniższej tabeli przedstawiono pola dostępne w nagłówku dla każdego zapisu.</span><span class="sxs-lookup"><span data-stu-id="1b864-110">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="1b864-111">Pole</span><span class="sxs-lookup"><span data-stu-id="1b864-111">Field</span></span> | <span data-ttu-id="1b864-112">opis</span><span class="sxs-lookup"><span data-stu-id="1b864-112">Description</span></span> |
|---|---|
| <span data-ttu-id="1b864-113">Opis towarów</span><span class="sxs-lookup"><span data-stu-id="1b864-113">Description of goods</span></span> | <span data-ttu-id="1b864-114">Wprowadź unikalną nazwę / numer identyfikacyjny dla rodzaju towarów, które będą używać tego opisu.</span><span class="sxs-lookup"><span data-stu-id="1b864-114">Enter a unique identification name/number for the type of goods that will use this description.</span></span> |
| <span data-ttu-id="1b864-115">opis</span><span class="sxs-lookup"><span data-stu-id="1b864-115">Description</span></span> | <span data-ttu-id="1b864-116">Umożliwia wprowadzenie opisu typu towarów w tej kategorii.</span><span class="sxs-lookup"><span data-stu-id="1b864-116">Enter a description of the type of goods in this category.</span></span> |

## <a name="vessels"></a><a name="vessels"></a><span data-ttu-id="1b864-117">Statki</span><span class="sxs-lookup"><span data-stu-id="1b864-117">Vessels</span></span>

<span data-ttu-id="1b864-118">Środek transportu to niepowtarzalna nazwa statku lub środka transportu, z którego korzysta przedsiębiorstwo żeglugowe lub agencja.</span><span class="sxs-lookup"><span data-stu-id="1b864-118">A vessel is the unique name of a ship or vessel that a shipping company or agency uses.</span></span> <span data-ttu-id="1b864-119">W przypadku tworzenia podróży należy zawsze wybrać lub wprowadzić środek transportu dla niego.</span><span class="sxs-lookup"><span data-stu-id="1b864-119">When you create a voyage, you must always either select or enter a vessel for it.</span></span> <span data-ttu-id="1b864-120">Jeśli często używasz tych samych statków, możesz przyspieszyć i ułatwić tworzenie nowej podróży, tworząc rekord statku dla każdego z nich, umożliwiając użytkownikom wybór statku z listy zamiast ręcznego wprowadzania nazwy lub numeru każdego z nich. czas.</span><span class="sxs-lookup"><span data-stu-id="1b864-120">If you often use the same vessels, then you can make it faster and easier to create a new voyage by creating a vessel record for each of them, thereby allowing users to select the vessel from a list rather then enter the name or number manually each time.</span></span>

<span data-ttu-id="1b864-121">Aby pracować ze statkami, przejdź do **Koszty dostawy \> Konfiguracja informacji o wysyłce \> Środki transportu**.</span><span class="sxs-lookup"><span data-stu-id="1b864-121">To work with vessels, go to **Landed cost \> Shipping information setup \> Vessels**.</span></span> <span data-ttu-id="1b864-122">Można tam wyświetlać, otwierać, tworzyć i usuwać środków transportu.</span><span class="sxs-lookup"><span data-stu-id="1b864-122">There, you can view, open, create, and delete records for vessels.</span></span> <span data-ttu-id="1b864-123">W poniższej tabeli przedstawiono pola dostępne w nagłówku dla każdego zapisu.</span><span class="sxs-lookup"><span data-stu-id="1b864-123">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="1b864-124">Pole</span><span class="sxs-lookup"><span data-stu-id="1b864-124">Field</span></span> | <span data-ttu-id="1b864-125">opis</span><span class="sxs-lookup"><span data-stu-id="1b864-125">Description</span></span> |
|---|---|
| <span data-ttu-id="1b864-126">Statek</span><span class="sxs-lookup"><span data-stu-id="1b864-126">Vessel</span></span> | <span data-ttu-id="1b864-127">Wprowadź unikatową nazwę/numer identyfikacyjny wysyłki, która będzie używana do transportu towarów w podróży.</span><span class="sxs-lookup"><span data-stu-id="1b864-127">Enter a unique identification name/number for the ship that will be used to transport goods on a voyage.</span></span> |
| <span data-ttu-id="1b864-128">opis</span><span class="sxs-lookup"><span data-stu-id="1b864-128">Description</span></span> | <span data-ttu-id="1b864-129">Wprowadź opis środka transportu.</span><span class="sxs-lookup"><span data-stu-id="1b864-129">Enter a description of the vessel.</span></span> <span data-ttu-id="1b864-130">Zwykle ten opis określa nazwę firmy przewozowej i firmy przewozowej/agenta.</span><span class="sxs-lookup"><span data-stu-id="1b864-130">Typically, this description identifies the name of the ship and the shipping company/agent.</span></span> |
| <span data-ttu-id="1b864-131">Metoda dostawy</span><span class="sxs-lookup"><span data-stu-id="1b864-131">Mode of delivery</span></span> | <span data-ttu-id="1b864-132">Umożliwia wybranie trybu dostawy używanego przez środek transportu (np. _Samolot_, _Ocean_ lub _Pociąg_).</span><span class="sxs-lookup"><span data-stu-id="1b864-132">Select the mode of delivery that the vessel uses (such as _Air_, _Ocean_, or _Train_).</span></span> |

## <a name="exporters"></a><span data-ttu-id="1b864-133">Eksporterzy</span><span class="sxs-lookup"><span data-stu-id="1b864-133">Exporters</span></span>

<span data-ttu-id="1b864-134">Każdy rekord eksportera identyfikuje dostawcę lub eksportera, który można zdefiniować jako dostawcę dla podróży.</span><span class="sxs-lookup"><span data-stu-id="1b864-134">Each exporter record identifies a vendor or exporter that can be defined as the vendor for a voyage.</span></span> <span data-ttu-id="1b864-135">Eksporter może być skojarzony z podróżą i używany do raportowania.</span><span class="sxs-lookup"><span data-stu-id="1b864-135">The exporter can be associated with a voyage and used for reporting.</span></span>

<span data-ttu-id="1b864-136">Aby pracować ze eksporterami, przejdź do **Koszty dostawy \> Konfiguracja informacji o wysyłce \> Eksporterzy**.</span><span class="sxs-lookup"><span data-stu-id="1b864-136">To work with exporters, go to **Landed cost \> Shipping information setup \> Exporters**.</span></span> <span data-ttu-id="1b864-137">Można tam wyświetlać, otwierać, tworzyć i usuwać eksporterów.</span><span class="sxs-lookup"><span data-stu-id="1b864-137">There, you can view, open, create, and delete records for exporters.</span></span> <span data-ttu-id="1b864-138">W poniższej tabeli przedstawiono pola dostępne w nagłówku dla każdego zapisu.</span><span class="sxs-lookup"><span data-stu-id="1b864-138">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="1b864-139">Pole</span><span class="sxs-lookup"><span data-stu-id="1b864-139">Field</span></span> | <span data-ttu-id="1b864-140">opis</span><span class="sxs-lookup"><span data-stu-id="1b864-140">Description</span></span> |
|---|---|
| <span data-ttu-id="1b864-141">Eksporter</span><span class="sxs-lookup"><span data-stu-id="1b864-141">Exporter</span></span> | <span data-ttu-id="1b864-142">Wprowadź niepowtarzalną nazwę / numer identyfikacyjny eksportera towarów przewożonych w podróży.</span><span class="sxs-lookup"><span data-stu-id="1b864-142">Enter a unique identification name/number for the exporter of goods that are transported on a voyage.</span></span> |
| <span data-ttu-id="1b864-143">opis</span><span class="sxs-lookup"><span data-stu-id="1b864-143">Description</span></span> | <span data-ttu-id="1b864-144">Wprowadź opis eksportera.</span><span class="sxs-lookup"><span data-stu-id="1b864-144">Enter a description of the exporter.</span></span> <span data-ttu-id="1b864-145">Zwykle ten opis określa pełną nazwę firmy przewozowej i firmy przewozowej/agenta.</span><span class="sxs-lookup"><span data-stu-id="1b864-145">Typically, this description identifies the full name of the shipping company/agent.</span></span> |

## <a name="commodity-codes"></a><span data-ttu-id="1b864-146">Kody asortymentu</span><span class="sxs-lookup"><span data-stu-id="1b864-146">Commodity codes</span></span>

<span data-ttu-id="1b864-147">Używasz kodów towarów, aby pomóc w identyfikacji celnej i obliczaniu stawek celnych dla towarów podczas podróży.</span><span class="sxs-lookup"><span data-stu-id="1b864-147">You use commodity codes to help with customs identification and the calculation of duty rates for goods on a voyage.</span></span> <span data-ttu-id="1b864-148">Kody asortymentu można wybierać na stronie **Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="1b864-148">You can select commodity codes on the **Released products** page.</span></span>

<span data-ttu-id="1b864-149">Aby pracować z kodami asortymentu, przejdź do **Koszty dostawy \> Konfiguracja informacji o wysyłce \> Kody asortymentu**.</span><span class="sxs-lookup"><span data-stu-id="1b864-149">To work with commodity codes, go to **Landed cost \> Shipping information setup \> Commodity codes**.</span></span> <span data-ttu-id="1b864-150">Można tam wyświetlać, otwierać, tworzyć i usuwać kody asortymentu.</span><span class="sxs-lookup"><span data-stu-id="1b864-150">There, you can view, open, create, and delete records for commodity codes.</span></span> <span data-ttu-id="1b864-151">W poniższej tabeli przedstawiono pola dostępne w nagłówku dla każdego zapisu.</span><span class="sxs-lookup"><span data-stu-id="1b864-151">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="1b864-152">Pole</span><span class="sxs-lookup"><span data-stu-id="1b864-152">Field</span></span> | <span data-ttu-id="1b864-153">opis</span><span class="sxs-lookup"><span data-stu-id="1b864-153">Description</span></span> |
|---|---|
| <span data-ttu-id="1b864-154">Kod asortymentu</span><span class="sxs-lookup"><span data-stu-id="1b864-154">Commodity code</span></span> | <span data-ttu-id="1b864-155">Umożliwia wprowadzenie unikatowego kodu asortymentu tego typu.</span><span class="sxs-lookup"><span data-stu-id="1b864-155">Enter a unique code for this type of commodity.</span></span> |
| <span data-ttu-id="1b864-156">opis</span><span class="sxs-lookup"><span data-stu-id="1b864-156">Description</span></span> | <span data-ttu-id="1b864-157">Umożliwia wprowadzenie opisu typu asortymentu.</span><span class="sxs-lookup"><span data-stu-id="1b864-157">Enter a description of the commodity type.</span></span> |

## <a name="customs-description"></a><span data-ttu-id="1b864-158">Opis płatności celnych</span><span class="sxs-lookup"><span data-stu-id="1b864-158">Customs description</span></span>

<span data-ttu-id="1b864-159">Opisy celne ułatwiają identyfikowanie towarów na potrzeby celne.</span><span class="sxs-lookup"><span data-stu-id="1b864-159">Customs descriptions help identify goods for customs purposes.</span></span> <span data-ttu-id="1b864-160">Możesz wybrać opis cła na stronie **Zwolnione produkty** lub w wierszach zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="1b864-160">You can select a customs description on the **Released products** page or on purchase order lines.</span></span>

<span data-ttu-id="1b864-161">Aby pracować z opisami cła, przejdź do **Koszt z wyładunkiem \> Konfiguracja informacji o wysyłce \> Opis cła**.</span><span class="sxs-lookup"><span data-stu-id="1b864-161">To work with customs descriptions, go to **Landed cost \> Shipping information setup \> Customs description**.</span></span> <span data-ttu-id="1b864-162">Można tam wyświetlać, otwierać, tworzyć i usuwać rekordy opisów cła.</span><span class="sxs-lookup"><span data-stu-id="1b864-162">There, you can view, open, create, and delete records for custom descriptions.</span></span> <span data-ttu-id="1b864-163">W poniższej tabeli przedstawiono pola dostępne w nagłówku dla każdego zapisu.</span><span class="sxs-lookup"><span data-stu-id="1b864-163">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="1b864-164">Pole</span><span class="sxs-lookup"><span data-stu-id="1b864-164">Field</span></span> | <span data-ttu-id="1b864-165">opis</span><span class="sxs-lookup"><span data-stu-id="1b864-165">Description</span></span> |
|---|---|
| <span data-ttu-id="1b864-166">Opis płatności celnych</span><span class="sxs-lookup"><span data-stu-id="1b864-166">Customs description</span></span> | <span data-ttu-id="1b864-167">Wprowadź unikalny kod dla tego typu klasyfikacji celnej.</span><span class="sxs-lookup"><span data-stu-id="1b864-167">Enter a unique code for this type of customs classification.</span></span> <span data-ttu-id="1b864-168">Często kod ten będzie oficjalnym opisem dostarczonym przez organ celny w celu opisu i jakościowej wartości towarów.</span><span class="sxs-lookup"><span data-stu-id="1b864-168">Often, this code will be the official description that is provided by a customs authority for the description and qualitative value of the goods.</span></span> |
| <span data-ttu-id="1b864-169">opis</span><span class="sxs-lookup"><span data-stu-id="1b864-169">Description</span></span> | <span data-ttu-id="1b864-170">Wprowadź opis klasyfikacji celnej.</span><span class="sxs-lookup"><span data-stu-id="1b864-170">Enter a description of the customs classification.</span></span> |
