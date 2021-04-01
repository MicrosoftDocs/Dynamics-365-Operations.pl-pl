---
title: Materiały niebezpieczne
description: Ten temat zawiera informacje dotyczące dokumentów i informacje dotyczące materiałów niebezpiecznych przechowywanych w środowisku użytkownika.
author: lachlancashMS
manager: tfehr
ms.date: 01/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: kamaybac
ms.search.validFrom: 2019-10-14
ms.dyn365.ops.version: ''
ms.openlocfilehash: d27ec5b65cc607c22d97c1dc44bb573bc2772611
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5243184"
---
# <a name="hazardous-materials"></a><span data-ttu-id="bd926-103">Materiały niebezpieczne</span><span class="sxs-lookup"><span data-stu-id="bd926-103">Hazardous materials</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="bd926-104">Informacje dotyczące materiałów niebezpiecznych są konfigurowane w module Zarządzanie informacjami o produktach.</span><span class="sxs-lookup"><span data-stu-id="bd926-104">Information about hazardous materials is set up in Product information management.</span></span> <span data-ttu-id="bd926-105">Moduł ten zapewnia również dokumenty, które można wydrukować za pomocą modułu Zarządzanie magazynem.</span><span class="sxs-lookup"><span data-stu-id="bd926-105">This module also provides documents that can be printed through warehouse management.</span></span>

<span data-ttu-id="bd926-106">W przypadku wysyłki materiałów sklasyfikowanych jako towary niebezpieczne, do wysyłek należy dołączyć dodatkową dokumentację.</span><span class="sxs-lookup"><span data-stu-id="bd926-106">When you ship materials that are classified as dangerous goods, additional paperwork must be included with the shipments.</span></span> <span data-ttu-id="bd926-107">Funkcje materiałów niebezpiecznych umożliwiają klientom przechowywanie informacji dotyczących klasyfikacji i powiązanie ich ze zwalnianiem towarów.</span><span class="sxs-lookup"><span data-stu-id="bd926-107">The hazardous materials functionality lets customers store classification information and relate it to release items.</span></span> <span data-ttu-id="bd926-108">Te informacje mogą być następnie używane w celu przygotowania dokumentacji dotyczącej wysyłki.</span><span class="sxs-lookup"><span data-stu-id="bd926-108">This information can then be used to help prepare shipping documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd926-109">Funkcje dot. materiałów niebezpiecznych w Microsoft Dynamics 365 Supply Chain Management zawierają użyteczny zbiór pól informacji o produktach i związanych z nimi funkcji, które mogą pomóc w rejestrowaniu i odnajdywaniu informacji związanych z produktami niebezpiecznymi.</span><span class="sxs-lookup"><span data-stu-id="bd926-109">The hazardous materials features in Microsoft Dynamics 365 Supply Chain Management provide a collection of useful product information fields and related functionality that can help you record and reference information that is related to your hazardous products.</span></span> <span data-ttu-id="bd926-110">Te funkcje mogą również pomóc w projektowaniu i drukowaniu dokumentów dostawy, które zawierają niektóre z tych samych informacji o wszelkich transportowanych niebezpiecznych materiałach.</span><span class="sxs-lookup"><span data-stu-id="bd926-110">These features can also help you design and print shipment documents that include some of the same information about any hazardous materials that you're shipping.</span></span> <span data-ttu-id="bd926-111">Jednak system nie sprawi, że działania będą automatycznie zgodne ze wszystkimi przepisami danego kraju lub regionu.</span><span class="sxs-lookup"><span data-stu-id="bd926-111">However, the system won't automatically make you compliant with all applicable regulations in your country or region.</span></span> <span data-ttu-id="bd926-112">Chociaż narzędzia te mają na celu ułatwienie zgodności ze wspólnymi przepisami, same w sobie nie są wystarczające ani nie gwarantują poprawności.</span><span class="sxs-lookup"><span data-stu-id="bd926-112">Although these tools are intended to help you comply with common regulations, they are neither sufficient in themselves nor guaranteed to be so.</span></span> <span data-ttu-id="bd926-113">Twoja organizacja jest odpowiedzialna za zastosowanie wszystkich stosownych rozporządzeń i podjęcie wszelkich niezbędnych kroków w celu przestrzegania odpowiednich przepisów.</span><span class="sxs-lookup"><span data-stu-id="bd926-113">Your organization is responsible for being aware of all applicable regulations and for taking all necessary steps to comply with them.</span></span>

<span data-ttu-id="bd926-114">Aby można było skorzystać z tej funkcji, wymagane są następujące ustawienia:</span><span class="sxs-lookup"><span data-stu-id="bd926-114">Before you can use this functionality, the following setup is required:</span></span>

- <span data-ttu-id="bd926-115">**Zarządzanie informacjami o produktach:** umożliwia konfigurowanie kodów, które można stosować w odniesieniu do zwolnionych produktów.</span><span class="sxs-lookup"><span data-stu-id="bd926-115">**Product information management:** Set up codes that can be applied to released products.</span></span>
- <span data-ttu-id="bd926-116">**Zarządzanie magazynem** umożliwia drukowanie informacji o wysyłce przy użyciu dodatkowych dokumentów dotyczących wysyłki.</span><span class="sxs-lookup"><span data-stu-id="bd926-116">**Warehouse management:** Use additional shipping documents to print shipment information.</span></span>

## <a name="product-information-management"></a><span data-ttu-id="bd926-117">Zarządzanie informacjami o produktach</span><span class="sxs-lookup"><span data-stu-id="bd926-117">Product information management</span></span>

<span data-ttu-id="bd926-118">W module Zarządzanie informacjami o produktach istnieje zakres tabel ustawień, w którym można dodać informacje o odwołaniach, które znajdują się w wykazach towarów niebezpiecznych dla transportu drogowego, powietrznego i morskiego.</span><span class="sxs-lookup"><span data-stu-id="bd926-118">In Product information management, there is a range of setup tables where you can add the reference information that is provided in the dangerous goods lists for road, air, and sea freight.</span></span>

<span data-ttu-id="bd926-119">Oto kilka dostępnych regulacji, które często są używane:</span><span class="sxs-lookup"><span data-stu-id="bd926-119">Here are some of the regulations that are often referenced:</span></span>

- <span data-ttu-id="bd926-120">**ADR** — przepisy dotyczące międzynarodowego przewozu drogowego towarów niebezpiecznych</span><span class="sxs-lookup"><span data-stu-id="bd926-120">**ADR** – Regulations that are related to the international carriage of dangerous goods by road</span></span>
- <span data-ttu-id="bd926-121">**CFR 49** — przepisy w USA dot. przewozu towarów niebezpiecznych</span><span class="sxs-lookup"><span data-stu-id="bd926-121">**CFR 49** – Regulations in the United Sates for the carriage of dangerous goods</span></span>
- <span data-ttu-id="bd926-122">**IMDG** — Międzynarodowy kodeks ładunków niebezpiecznych (IMDG)</span><span class="sxs-lookup"><span data-stu-id="bd926-122">**IMDG** – The International Marine Dangerous Goods (IMDG) code</span></span>
- <span data-ttu-id="bd926-123">**IATA** — regulacje dotyczące towarów niebezpiecznych międzynarodowego zrzeszenia przewoźników powietrznych (IATA)</span><span class="sxs-lookup"><span data-stu-id="bd926-123">**IATA** – The International Air Transport Association (IATA) dangerous goods regulations</span></span>

<span data-ttu-id="bd926-124">Każde z tych rozporządzeń zawiera listę towarów niebezpiecznych, która zawiera kody referencyjne.</span><span class="sxs-lookup"><span data-stu-id="bd926-124">Each of these regulations has a dangerous goods list that includes reference codes.</span></span> <span data-ttu-id="bd926-125">Listy dla każdego typu transportu są łączone na wspólnych międzynarodowych klasyfikacjach.</span><span class="sxs-lookup"><span data-stu-id="bd926-125">The lists for each type of transport are combined on shared international classifications.</span></span> <span data-ttu-id="bd926-126">Program Supply Chain Management zawiera tabelę odwołań dla współdzielonych kodów z tych list.</span><span class="sxs-lookup"><span data-stu-id="bd926-126">Supply Chain Management provides a reference table for the shared codes in those lists.</span></span> <span data-ttu-id="bd926-127">Każda lista ma również kilka unikatowych kodów, które można zdefiniować.</span><span class="sxs-lookup"><span data-stu-id="bd926-127">Each list also has some unique codes that can be defined.</span></span>

<span data-ttu-id="bd926-128">Aby rozpocząć konfigurowanie tych informacji, należy utworzyć rozporządzenie, które będzie używane do konfigurowania początkowych parametrów.</span><span class="sxs-lookup"><span data-stu-id="bd926-128">To start to configure this information, create a regulation that you can use to configure the initial parameters.</span></span>

## <a name="warehouse-management"></a><span data-ttu-id="bd926-129">Zarządzanie magazynem</span><span class="sxs-lookup"><span data-stu-id="bd926-129">Warehouse management</span></span>

<span data-ttu-id="bd926-130">Po przygotowaniu wysyłki można wydrukować kilka nowych raportów.</span><span class="sxs-lookup"><span data-stu-id="bd926-130">When a shipment is prepared, several new reports can be printed.</span></span> <span data-ttu-id="bd926-131">W tych raportach są używane informacje skonfigurowane w module Zarządzanie informacjami o produktach.</span><span class="sxs-lookup"><span data-stu-id="bd926-131">These reports use the information that you set up in Product information management.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]