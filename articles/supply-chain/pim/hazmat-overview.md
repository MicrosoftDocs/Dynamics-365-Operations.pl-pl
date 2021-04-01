---
title: Omówienie materiałów niebezpiecznych
description: Ten temat zawiera przegląd funkcji związanych z obsługą i dokumentami materiałów niebezpiecznych podczas zarządzania informacjami o produktach i zarządzania magazynem.
author: dasani-madipalli
manager: tfehr
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 4ff997214f80d97f6e558d32fbf66663cbc84143
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5231895"
---
# <a name="hazardous-materials-overview"></a><span data-ttu-id="ebf14-103">Omówienie materiałów niebezpiecznych</span><span class="sxs-lookup"><span data-stu-id="ebf14-103">Hazardous materials overview</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="ebf14-104">W celu zachowania zgodności z przepisami dotyczącymi wysyłki i transportu, organizacje, które dostarczają materiały, które są sklasyfikowane jako towary niebezpieczne, muszą zawierać dodatkowe dokumentacji wraz z ich wysyłką.</span><span class="sxs-lookup"><span data-stu-id="ebf14-104">To remain compliant with shipping and transport regulations, organizations that ship materials that are classified as dangerous goods must include additional paperwork with their shipments.</span></span> <span data-ttu-id="ebf14-105">Funkcja materiałów niebezpiecznych umożliwia klientom przechowywanie informacji związanych ze zwolnionymi pozycjami.</span><span class="sxs-lookup"><span data-stu-id="ebf14-105">The hazardous materials feature lets customers store information that is related to released items.</span></span> <span data-ttu-id="ebf14-106">Te informacje mogą być następnie używane w celu przygotowania dokumentacji dotyczącej wysyłki.</span><span class="sxs-lookup"><span data-stu-id="ebf14-106">This information can then be used to help prepare shipping documentation.</span></span> <span data-ttu-id="ebf14-107">Organizacja, która dostarcza towary niebezpieczne, musi dysponować własnymi procesami i procedurami służącymi do zarządzania procesem wysyłki.</span><span class="sxs-lookup"><span data-stu-id="ebf14-107">An organization that ships dangerous goods must have its own processes and procedures for managing the shipping process.</span></span> <span data-ttu-id="ebf14-108">Microsoft Dynamics 365 Supply Chain Management to tylko narzędzie, które może pomóc w wygenerowaniu wymaganych dokumentów.</span><span class="sxs-lookup"><span data-stu-id="ebf14-108">Microsoft Dynamics 365 Supply Chain Management is just a tool that can help generate the required documents.</span></span>

<span data-ttu-id="ebf14-109">Na poniższym diagramie przedstawiono kroki niezbędne do skonfigurowania i użycia funkcji materiałów niebezpiecznych.</span><span class="sxs-lookup"><span data-stu-id="ebf14-109">The following diagram illustrates the steps needed to set up and use the hazardous materials feature.</span></span>

<span data-ttu-id="ebf14-110">![Ustawienia i użycie funkcji materiałów niebezpiecznych](media/hazmat-overview.png "Ustawienia i użycie funkcji materiałów niebezpiecznych")</span><span class="sxs-lookup"><span data-stu-id="ebf14-110">![Setup and use of the hazardous materials feature](media/hazmat-overview.png "Setup and use of the hazardous materials feature")</span></span>

<span data-ttu-id="ebf14-111">Funkcja zarządzania materiałami niebezpiecznymi jest skonfigurowana w module Zarządzanie informacjami o produktach i zawiera dokumenty, które można wydrukować za pomocą modułu Zarządzanie magazynem.</span><span class="sxs-lookup"><span data-stu-id="ebf14-111">The hazardous materials feature is set up in Product information management and provides documents that can be printed through Warehouse management.</span></span> <span data-ttu-id="ebf14-112">Dzięki temu obszary te są tymi dwoma głównymi obszarami, które będą przeglądane, konfigurowane i zastosowane w następujących funkcjach:</span><span class="sxs-lookup"><span data-stu-id="ebf14-112">Therefore, broadly speaking, those areas are the two main areas where you will review, set up, and use this feature's functionality:</span></span>

- <span data-ttu-id="ebf14-113">**Zarządzanie informacjami o produktach:** — umożliwia konfigurowanie kodów, które będą stosowane w odniesieniu do zwolnionego produktu.</span><span class="sxs-lookup"><span data-stu-id="ebf14-113">**Product information management** – Set up the codes that will be applied to a released product.</span></span>
- <span data-ttu-id="ebf14-114">**Zarządzanie magazynem** — praca z dodatkowymi dokumentami wysyłki, które będą drukowane dla wysyłek.</span><span class="sxs-lookup"><span data-stu-id="ebf14-114">**Warehouse management** – Work with additional shipping documents that will be printed for shipments.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ebf14-115">Funkcje dot. materiałów niebezpiecznych w Supply Chain Management zawierają użyteczny zbiór pól informacji o produktach i związanych z nimi funkcji, które mogą pomóc w rejestrowaniu i odnajdywaniu informacji związanych z produktami niebezpiecznymi.</span><span class="sxs-lookup"><span data-stu-id="ebf14-115">The hazardous materials features in Supply Chain Management provide a collection of useful product information fields and related functionality that can help you record and reference information that is related to your hazardous products.</span></span> <span data-ttu-id="ebf14-116">Te funkcje mogą również pomóc w projektowaniu i drukowaniu dokumentów dostawy, które zawierają niektóre z tych samych informacji o wszelkich transportowanych niebezpiecznych materiałach.</span><span class="sxs-lookup"><span data-stu-id="ebf14-116">These features can also help you design and print shipment documents that include some of the same information about any hazardous materials that you're shipping.</span></span> <span data-ttu-id="ebf14-117">Jednak system nie sprawi, że działania będą automatycznie zgodne ze wszystkimi przepisami danego kraju lub regionu.</span><span class="sxs-lookup"><span data-stu-id="ebf14-117">However, the system won't automatically make you compliant with all applicable regulations in your country or region.</span></span> <span data-ttu-id="ebf14-118">Chociaż narzędzia te mają na celu ułatwienie zgodności ze wspólnymi przepisami, same w sobie nie są wystarczające ani nie gwarantują poprawności.</span><span class="sxs-lookup"><span data-stu-id="ebf14-118">Although these tools are intended to help you comply with common regulations, they are neither sufficient in themselves nor guaranteed to be so.</span></span> <span data-ttu-id="ebf14-119">Twoja organizacja jest odpowiedzialna za zastosowanie wszystkich stosownych rozporządzeń i podjęcie wszelkich niezbędnych kroków w celu przestrzegania odpowiednich przepisów.</span><span class="sxs-lookup"><span data-stu-id="ebf14-119">Your organization is responsible for being aware of all applicable regulations and for taking all necessary steps to comply with them.</span></span>

## <a name="product-information-management"></a><span data-ttu-id="ebf14-120">Zarządzanie informacjami o produktach</span><span class="sxs-lookup"><span data-stu-id="ebf14-120">Product information management</span></span>

<span data-ttu-id="ebf14-121">Zarządzanie informacjami o produktach zawiera zakres tabel ustawień, w którym można podać informacje o odwołaniach, które znajdują się w wykazach towarów niebezpiecznych dla transportu drogowego, powietrznego i morskiego.</span><span class="sxs-lookup"><span data-stu-id="ebf14-121">Product information management provides a range of setup tables where you can enter reference information for the various dangerous goods lists for road, air, and sea freight.</span></span>

<span data-ttu-id="ebf14-122">W przypadku opracowania tych funkcji nastąpiły odwołania do następujących wspólnych reguł:</span><span class="sxs-lookup"><span data-stu-id="ebf14-122">The following common regulations were referenced when this functionality was developed:</span></span>

- <span data-ttu-id="ebf14-123">**ADR** — przepisy dotyczące międzynarodowego przewozu drogowego towarów niebezpiecznych</span><span class="sxs-lookup"><span data-stu-id="ebf14-123">**ADR** – Regulations that are related to the international carriage of dangerous goods by road</span></span>
- <span data-ttu-id="ebf14-124">**CFR 49** — przepisy w USA dot. przewozu towarów niebezpiecznych</span><span class="sxs-lookup"><span data-stu-id="ebf14-124">**CFR 49** – Regulations in the United Sates for the carriage of dangerous goods</span></span>
- <span data-ttu-id="ebf14-125">**IMDG** — Międzynarodowy kodeks ładunków niebezpiecznych (IMDG)</span><span class="sxs-lookup"><span data-stu-id="ebf14-125">**IMDG** – The International Marine Dangerous Goods (IMDG) code</span></span>
- <span data-ttu-id="ebf14-126">**IATA** — regulacje dotyczące towarów niebezpiecznych międzynarodowego zrzeszenia przewoźników powietrznych (IATA)</span><span class="sxs-lookup"><span data-stu-id="ebf14-126">**IATA** – The International Air Transport Association (IATA) dangerous goods regulations</span></span>

<span data-ttu-id="ebf14-127">Każdy zbiór rozporządzeń zawiera standardowe wykazy towarów niebezpiecznych i kodów referencyjnych.</span><span class="sxs-lookup"><span data-stu-id="ebf14-127">Each set of regulations provides standardized lists of dangerous goods and reference codes.</span></span> <span data-ttu-id="ebf14-128">Z tego też powodu program Supply Chain Management zawiera tabelę odwołań dla wspólnych kodów z tych list.</span><span class="sxs-lookup"><span data-stu-id="ebf14-128">Therefore, Supply Chain Management provides a reference table for the common codes on those lists.</span></span> <span data-ttu-id="ebf14-129">Każda lista ma również kilka unikatowych kodów, które można zdefiniować.</span><span class="sxs-lookup"><span data-stu-id="ebf14-129">Each list also has some unique codes that you can define.</span></span>

<span data-ttu-id="ebf14-130">Aby uzyskać więcej informacji na temat konfigurowania przepisów i wartości materiałów niebezpiecznych oraz sposobu przypisywania wartości do odpowiednich produktów, należy zapoznać się z następującymi tematami:</span><span class="sxs-lookup"><span data-stu-id="ebf14-130">For more information about how to set up regulations and values for hazardous materials, and how to assign the values to relevant products, see the following topics:</span></span>

- [<span data-ttu-id="ebf14-131">Ustawianie materiałów niebezpiecznych</span><span class="sxs-lookup"><span data-stu-id="ebf14-131">Set up hazardous materials</span></span>](hazmat-setup.md)
- [<span data-ttu-id="ebf14-132">Materiały niebezpieczne w produktach, zamówieniach, wysyłkach i ładunkach</span><span class="sxs-lookup"><span data-stu-id="ebf14-132">Hazardous materials in products, orders, shipments, and loads</span></span>](hazmat-items.md)

## <a name="warehouse-management"></a><span data-ttu-id="ebf14-133">Zarządzanie magazynem</span><span class="sxs-lookup"><span data-stu-id="ebf14-133">Warehouse management</span></span>

<span data-ttu-id="ebf14-134">Podczas przygotowywania wysyłki w module Zarządzanie magazynem można wydrukować kilka nowych raportów korzystających z informacji skonfigurowanych w module Zarządzanie informacjami o produktach.</span><span class="sxs-lookup"><span data-stu-id="ebf14-134">When you prepare a shipment in Warehouse management, you will be able to print several new reports that use the information that you set up in Product information management.</span></span> <span data-ttu-id="ebf14-135">Aby uzyskać więcej informacji o dostępnych raportach i sposobach ich używania, zapoznaj się z [zapytaniami i raportami dotyczącymi materiałów niebezpiecznych](hazmat-reports.md).</span><span class="sxs-lookup"><span data-stu-id="ebf14-135">For more information about the available reports and how to use them, see [Hazardous materials inquiries and reports](hazmat-reports.md).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]