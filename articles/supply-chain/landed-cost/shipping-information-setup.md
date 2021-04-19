---
title: Konfiguracja informacji o wysyłce
description: W tym temacie opisano, jak skonfigurować informacje o wysyłce dla modułu Koszt z wyładunkiem.
author: sherry-zheng
ms.date: 12/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMGoodsDescriptionTable, ITMVesselTable, ITMExporterTable, ITMCommodityCodeTable, ITMCustomsDescription
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-04
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 74ac7e0eac545369eef1a48f0085c820a4728e75
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833696"
---
# <a name="shipping-information-setup"></a><span data-ttu-id="31291-103">Konfiguracja informacji o wysyłce</span><span class="sxs-lookup"><span data-stu-id="31291-103">Shipping information setup</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="31291-104">W tym temacie opisano, jak skonfigurować informacje o wysyłce dla modułu **Koszt z wyładunkiem**.</span><span class="sxs-lookup"><span data-stu-id="31291-104">This topic describes how to set up shipping information for the **Landed cost** module.</span></span>

## <a name="description-of-goods"></a><a name="description-of-goods"></a><span data-ttu-id="31291-105">Opis towarów</span><span class="sxs-lookup"><span data-stu-id="31291-105">Description of goods</span></span>

<span data-ttu-id="31291-106">Opisy towarów ułatwiają identyfikację podróży, kontenera wysyłkowego lub folio towarów i towarów w nich zawarte.</span><span class="sxs-lookup"><span data-stu-id="31291-106">Descriptions of goods help identify a voyage, shipping container, or folio of goods, and the goods in it.</span></span> <span data-ttu-id="31291-107">Możesz wybrać opis towarów w nagłówku kontenera wysyłkowego lub nagłówku folio.</span><span class="sxs-lookup"><span data-stu-id="31291-107">You can select a description of goods on the shipping container header or the folio header.</span></span>

<span data-ttu-id="31291-108">Aby pracować z opisami towarów, przejdź do **Koszt z wyładunkiem \> Konfiguracja informacji o wysyłce \> Opis towaru**.</span><span class="sxs-lookup"><span data-stu-id="31291-108">To work with descriptions of goods, go to **Landed cost \> Shipping information setup \> Description of goods**.</span></span> <span data-ttu-id="31291-109">Można tam wyświetlać, otwierać, tworzyć i usuwać rekordy opisów towarów.</span><span class="sxs-lookup"><span data-stu-id="31291-109">There, you can view, open, create, and delete records for descriptions of goods.</span></span> <span data-ttu-id="31291-110">W poniższej tabeli przedstawiono pola dostępne w nagłówku dla każdego zapisu.</span><span class="sxs-lookup"><span data-stu-id="31291-110">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="31291-111">Pole</span><span class="sxs-lookup"><span data-stu-id="31291-111">Field</span></span> | <span data-ttu-id="31291-112">opis</span><span class="sxs-lookup"><span data-stu-id="31291-112">Description</span></span> |
|---|---|
| <span data-ttu-id="31291-113">Opis towarów</span><span class="sxs-lookup"><span data-stu-id="31291-113">Description of goods</span></span> | <span data-ttu-id="31291-114">Wprowadź unikalną nazwę / numer identyfikacyjny dla rodzaju towarów, które będą używać tego opisu.</span><span class="sxs-lookup"><span data-stu-id="31291-114">Enter a unique identification name/number for the type of goods that will use this description.</span></span> |
| <span data-ttu-id="31291-115">opis</span><span class="sxs-lookup"><span data-stu-id="31291-115">Description</span></span> | <span data-ttu-id="31291-116">Umożliwia wprowadzenie opisu typu towarów w tej kategorii.</span><span class="sxs-lookup"><span data-stu-id="31291-116">Enter a description of the type of goods in this category.</span></span> |

## <a name="vessels"></a><a name="vessels"></a><span data-ttu-id="31291-117">Statki</span><span class="sxs-lookup"><span data-stu-id="31291-117">Vessels</span></span>

<span data-ttu-id="31291-118">Środek transportu to niepowtarzalna nazwa statku lub środka transportu, z którego korzysta przedsiębiorstwo żeglugowe lub agencja.</span><span class="sxs-lookup"><span data-stu-id="31291-118">A vessel is the unique name of a ship or vessel that a shipping company or agency uses.</span></span> <span data-ttu-id="31291-119">W przypadku tworzenia podróży należy zawsze wybrać lub wprowadzić środek transportu dla niego.</span><span class="sxs-lookup"><span data-stu-id="31291-119">When you create a voyage, you must always either select or enter a vessel for it.</span></span> <span data-ttu-id="31291-120">Jeśli często używasz tych samych statków, możesz przyspieszyć i ułatwić tworzenie nowej podróży, tworząc rekord statku dla każdego z nich, umożliwiając użytkownikom wybór statku z listy zamiast ręcznego wprowadzania nazwy lub numeru każdego z nich. czas.</span><span class="sxs-lookup"><span data-stu-id="31291-120">If you often use the same vessels, then you can make it faster and easier to create a new voyage by creating a vessel record for each of them, thereby allowing users to select the vessel from a list rather then enter the name or number manually each time.</span></span>

<span data-ttu-id="31291-121">Aby pracować ze statkami, przejdź do **Koszty dostawy \> Konfiguracja informacji o wysyłce \> Środki transportu**.</span><span class="sxs-lookup"><span data-stu-id="31291-121">To work with vessels, go to **Landed cost \> Shipping information setup \> Vessels**.</span></span> <span data-ttu-id="31291-122">Można tam wyświetlać, otwierać, tworzyć i usuwać środków transportu.</span><span class="sxs-lookup"><span data-stu-id="31291-122">There, you can view, open, create, and delete records for vessels.</span></span> <span data-ttu-id="31291-123">W poniższej tabeli przedstawiono pola dostępne w nagłówku dla każdego zapisu.</span><span class="sxs-lookup"><span data-stu-id="31291-123">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="31291-124">Pole</span><span class="sxs-lookup"><span data-stu-id="31291-124">Field</span></span> | <span data-ttu-id="31291-125">opis</span><span class="sxs-lookup"><span data-stu-id="31291-125">Description</span></span> |
|---|---|
| <span data-ttu-id="31291-126">Statek</span><span class="sxs-lookup"><span data-stu-id="31291-126">Vessel</span></span> | <span data-ttu-id="31291-127">Wprowadź unikatową nazwę/numer identyfikacyjny wysyłki, która będzie używana do transportu towarów w podróży.</span><span class="sxs-lookup"><span data-stu-id="31291-127">Enter a unique identification name/number for the ship that will be used to transport goods on a voyage.</span></span> |
| <span data-ttu-id="31291-128">opis</span><span class="sxs-lookup"><span data-stu-id="31291-128">Description</span></span> | <span data-ttu-id="31291-129">Wprowadź opis środka transportu.</span><span class="sxs-lookup"><span data-stu-id="31291-129">Enter a description of the vessel.</span></span> <span data-ttu-id="31291-130">Zwykle ten opis określa nazwę firmy przewozowej i firmy przewozowej/agenta.</span><span class="sxs-lookup"><span data-stu-id="31291-130">Typically, this description identifies the name of the ship and the shipping company/agent.</span></span> |
| <span data-ttu-id="31291-131">Metoda dostawy</span><span class="sxs-lookup"><span data-stu-id="31291-131">Mode of delivery</span></span> | <span data-ttu-id="31291-132">Umożliwia wybranie trybu dostawy używanego przez środek transportu (np. _Samolot_, _Ocean_ lub _Pociąg_).</span><span class="sxs-lookup"><span data-stu-id="31291-132">Select the mode of delivery that the vessel uses (such as _Air_, _Ocean_, or _Train_).</span></span> |

## <a name="exporters"></a><span data-ttu-id="31291-133">Eksporterzy</span><span class="sxs-lookup"><span data-stu-id="31291-133">Exporters</span></span>

<span data-ttu-id="31291-134">Każdy rekord eksportera identyfikuje dostawcę lub eksportera, który można zdefiniować jako dostawcę dla podróży.</span><span class="sxs-lookup"><span data-stu-id="31291-134">Each exporter record identifies a vendor or exporter that can be defined as the vendor for a voyage.</span></span> <span data-ttu-id="31291-135">Eksporter może być skojarzony z podróżą i używany do raportowania.</span><span class="sxs-lookup"><span data-stu-id="31291-135">The exporter can be associated with a voyage and used for reporting.</span></span>

<span data-ttu-id="31291-136">Aby pracować ze eksporterami, przejdź do **Koszty dostawy \> Konfiguracja informacji o wysyłce \> Eksporterzy**.</span><span class="sxs-lookup"><span data-stu-id="31291-136">To work with exporters, go to **Landed cost \> Shipping information setup \> Exporters**.</span></span> <span data-ttu-id="31291-137">Można tam wyświetlać, otwierać, tworzyć i usuwać eksporterów.</span><span class="sxs-lookup"><span data-stu-id="31291-137">There, you can view, open, create, and delete records for exporters.</span></span> <span data-ttu-id="31291-138">W poniższej tabeli przedstawiono pola dostępne w nagłówku dla każdego zapisu.</span><span class="sxs-lookup"><span data-stu-id="31291-138">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="31291-139">Pole</span><span class="sxs-lookup"><span data-stu-id="31291-139">Field</span></span> | <span data-ttu-id="31291-140">opis</span><span class="sxs-lookup"><span data-stu-id="31291-140">Description</span></span> |
|---|---|
| <span data-ttu-id="31291-141">Eksporter</span><span class="sxs-lookup"><span data-stu-id="31291-141">Exporter</span></span> | <span data-ttu-id="31291-142">Wprowadź niepowtarzalną nazwę / numer identyfikacyjny eksportera towarów przewożonych w podróży.</span><span class="sxs-lookup"><span data-stu-id="31291-142">Enter a unique identification name/number for the exporter of goods that are transported on a voyage.</span></span> |
| <span data-ttu-id="31291-143">opis</span><span class="sxs-lookup"><span data-stu-id="31291-143">Description</span></span> | <span data-ttu-id="31291-144">Wprowadź opis eksportera.</span><span class="sxs-lookup"><span data-stu-id="31291-144">Enter a description of the exporter.</span></span> <span data-ttu-id="31291-145">Zwykle ten opis określa pełną nazwę firmy przewozowej i firmy przewozowej/agenta.</span><span class="sxs-lookup"><span data-stu-id="31291-145">Typically, this description identifies the full name of the shipping company/agent.</span></span> |

## <a name="commodity-codes"></a><span data-ttu-id="31291-146">Kody asortymentu</span><span class="sxs-lookup"><span data-stu-id="31291-146">Commodity codes</span></span>

<span data-ttu-id="31291-147">Używasz kodów towarów, aby pomóc w identyfikacji celnej i obliczaniu stawek celnych dla towarów podczas podróży.</span><span class="sxs-lookup"><span data-stu-id="31291-147">You use commodity codes to help with customs identification and the calculation of duty rates for goods on a voyage.</span></span> <span data-ttu-id="31291-148">Kody asortymentu można wybierać na stronie **Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="31291-148">You can select commodity codes on the **Released products** page.</span></span>

<span data-ttu-id="31291-149">Aby pracować z kodami asortymentu, przejdź do **Koszty dostawy \> Konfiguracja informacji o wysyłce \> Kody asortymentu**.</span><span class="sxs-lookup"><span data-stu-id="31291-149">To work with commodity codes, go to **Landed cost \> Shipping information setup \> Commodity codes**.</span></span> <span data-ttu-id="31291-150">Można tam wyświetlać, otwierać, tworzyć i usuwać kody asortymentu.</span><span class="sxs-lookup"><span data-stu-id="31291-150">There, you can view, open, create, and delete records for commodity codes.</span></span> <span data-ttu-id="31291-151">W poniższej tabeli przedstawiono pola dostępne w nagłówku dla każdego zapisu.</span><span class="sxs-lookup"><span data-stu-id="31291-151">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="31291-152">Pole</span><span class="sxs-lookup"><span data-stu-id="31291-152">Field</span></span> | <span data-ttu-id="31291-153">opis</span><span class="sxs-lookup"><span data-stu-id="31291-153">Description</span></span> |
|---|---|
| <span data-ttu-id="31291-154">Kod asortymentu</span><span class="sxs-lookup"><span data-stu-id="31291-154">Commodity code</span></span> | <span data-ttu-id="31291-155">Umożliwia wprowadzenie unikatowego kodu asortymentu tego typu.</span><span class="sxs-lookup"><span data-stu-id="31291-155">Enter a unique code for this type of commodity.</span></span> |
| <span data-ttu-id="31291-156">opis</span><span class="sxs-lookup"><span data-stu-id="31291-156">Description</span></span> | <span data-ttu-id="31291-157">Umożliwia wprowadzenie opisu typu asortymentu.</span><span class="sxs-lookup"><span data-stu-id="31291-157">Enter a description of the commodity type.</span></span> |

## <a name="customs-description"></a><span data-ttu-id="31291-158">Opis płatności celnych</span><span class="sxs-lookup"><span data-stu-id="31291-158">Customs description</span></span>

<span data-ttu-id="31291-159">Opisy celne ułatwiają identyfikowanie towarów na potrzeby celne.</span><span class="sxs-lookup"><span data-stu-id="31291-159">Customs descriptions help identify goods for customs purposes.</span></span> <span data-ttu-id="31291-160">Możesz wybrać opis cła na stronie **Zwolnione produkty** lub w wierszach zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="31291-160">You can select a customs description on the **Released products** page or on purchase order lines.</span></span>

<span data-ttu-id="31291-161">Aby pracować z opisami cła, przejdź do **Koszt z wyładunkiem \> Konfiguracja informacji o wysyłce \> Opis cła**.</span><span class="sxs-lookup"><span data-stu-id="31291-161">To work with customs descriptions, go to **Landed cost \> Shipping information setup \> Customs description**.</span></span> <span data-ttu-id="31291-162">Można tam wyświetlać, otwierać, tworzyć i usuwać rekordy opisów cła.</span><span class="sxs-lookup"><span data-stu-id="31291-162">There, you can view, open, create, and delete records for custom descriptions.</span></span> <span data-ttu-id="31291-163">W poniższej tabeli przedstawiono pola dostępne w nagłówku dla każdego zapisu.</span><span class="sxs-lookup"><span data-stu-id="31291-163">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="31291-164">Pole</span><span class="sxs-lookup"><span data-stu-id="31291-164">Field</span></span> | <span data-ttu-id="31291-165">opis</span><span class="sxs-lookup"><span data-stu-id="31291-165">Description</span></span> |
|---|---|
| <span data-ttu-id="31291-166">Opis płatności celnych</span><span class="sxs-lookup"><span data-stu-id="31291-166">Customs description</span></span> | <span data-ttu-id="31291-167">Wprowadź unikalny kod dla tego typu klasyfikacji celnej.</span><span class="sxs-lookup"><span data-stu-id="31291-167">Enter a unique code for this type of customs classification.</span></span> <span data-ttu-id="31291-168">Często kod ten będzie oficjalnym opisem dostarczonym przez organ celny w celu opisu i jakościowej wartości towarów.</span><span class="sxs-lookup"><span data-stu-id="31291-168">Often, this code will be the official description that is provided by a customs authority for the description and qualitative value of the goods.</span></span> |
| <span data-ttu-id="31291-169">opis</span><span class="sxs-lookup"><span data-stu-id="31291-169">Description</span></span> | <span data-ttu-id="31291-170">Wprowadź opis klasyfikacji celnej.</span><span class="sxs-lookup"><span data-stu-id="31291-170">Enter a description of the customs classification.</span></span> |
