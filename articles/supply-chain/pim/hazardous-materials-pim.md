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
ms.search.scope: Core, Operations, Retail
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: conradv
ms.search.validFrom: 2019-10-14
ms.dyn365.ops.version: ''
ms.openlocfilehash: 5006f06d90ddcc314a51878e9e21337de7d493e7
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3208475"
---
# <a name="hazardous-materials"></a><span data-ttu-id="e1f5c-103">Materiały niebezpieczne</span><span class="sxs-lookup"><span data-stu-id="e1f5c-103">Hazardous materials</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e1f5c-104">Informacje dotyczące materiałów niebezpiecznych są konfigurowane w module Zarządzanie informacjami o produktach.</span><span class="sxs-lookup"><span data-stu-id="e1f5c-104">Information about hazardous materials is set up in Product information management.</span></span> <span data-ttu-id="e1f5c-105">Moduł ten zapewnia również dokumenty, które można wydrukować za pomocą modułu Zarządzanie magazynem.</span><span class="sxs-lookup"><span data-stu-id="e1f5c-105">This module also provides documents that can be printed through warehouse management.</span></span>

<span data-ttu-id="e1f5c-106">W przypadku wysyłki materiałów sklasyfikowanych jako towary niebezpieczne, do wysyłek należy dołączyć dodatkową dokumentację.</span><span class="sxs-lookup"><span data-stu-id="e1f5c-106">When you ship materials that are classified as dangerous goods, additional paperwork must be included with the shipments.</span></span> <span data-ttu-id="e1f5c-107">Funkcje materiałów niebezpiecznych umożliwiają klientom przechowywanie informacji dotyczących klasyfikacji i powiązanie ich ze zwalnianiem towarów.</span><span class="sxs-lookup"><span data-stu-id="e1f5c-107">The hazardous materials functionality lets customers store classification information and relate it to release items.</span></span> <span data-ttu-id="e1f5c-108">Te informacje mogą być następnie używane w celu przygotowania dokumentacji dotyczącej wysyłki.</span><span class="sxs-lookup"><span data-stu-id="e1f5c-108">This information can then be used to help prepare shipping documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e1f5c-109">Aby ułatwić zarządzanie wysyłką towarów niebezpiecznych, program Microsoft Dynamics 365 Supply Chain Management umożliwia skonfigurowanie dodatkowych informacji dotyczących produktów, które są związane z produktami.</span><span class="sxs-lookup"><span data-stu-id="e1f5c-109">To help manage shipments of dangerous goods, Microsoft Dynamics 365 Supply Chain Management lets you set up additional reference information that is related to products.</span></span> <span data-ttu-id="e1f5c-110">Można również skonfigurować dodatkowe dokumenty wysyłki.</span><span class="sxs-lookup"><span data-stu-id="e1f5c-110">You can also set up additional shipment documents.</span></span> <span data-ttu-id="e1f5c-111">Jednak system nie jest automatycznie zgodny z przepisami dotyczącymi danego kraju lub regionu.</span><span class="sxs-lookup"><span data-stu-id="e1f5c-111">However, the system isn't automatically compliant with your country's or region's regulations.</span></span> <span data-ttu-id="e1f5c-112">Zamiast tego jest to narzędzie, które może pomóc w ogólnym programie.</span><span class="sxs-lookup"><span data-stu-id="e1f5c-112">Instead, it's a tool that can help your overall program.</span></span>

<span data-ttu-id="e1f5c-113">Aby można było skorzystać z tej funkcji, wymagane są następujące ustawienia:</span><span class="sxs-lookup"><span data-stu-id="e1f5c-113">Before you can use this functionality, the following setup is required:</span></span>

- <span data-ttu-id="e1f5c-114">**Zarządzanie informacjami o produktach:** umożliwia konfigurowanie kodów, które można stosować w odniesieniu do zwolnionych produktów.</span><span class="sxs-lookup"><span data-stu-id="e1f5c-114">**Product information management:** Set up codes that can be applied to released products.</span></span>
- <span data-ttu-id="e1f5c-115">**Zarządzanie magazynem** umożliwia drukowanie informacji o wysyłce przy użyciu dodatkowych dokumentów dotyczących wysyłki.</span><span class="sxs-lookup"><span data-stu-id="e1f5c-115">**Warehouse management:** Use additional shipping documents to print shipment information.</span></span>

## <a name="product-information-management"></a><span data-ttu-id="e1f5c-116">Zarządzanie informacjami o produktach</span><span class="sxs-lookup"><span data-stu-id="e1f5c-116">Product information management</span></span>

<span data-ttu-id="e1f5c-117">W module Zarządzanie informacjami o produktach istnieje zakres tabel ustawień, w którym można dodać informacje o odwołaniach, które znajdują się w wykazach towarów niebezpiecznych dla transportu drogowego, powietrznego i morskiego.</span><span class="sxs-lookup"><span data-stu-id="e1f5c-117">In Product information management, there is a range of setup tables where you can add the reference information that is provided in the dangerous goods lists for road, air, and sea freight.</span></span>

<span data-ttu-id="e1f5c-118">Oto kilka dostępnych regulacji, które często są używane:</span><span class="sxs-lookup"><span data-stu-id="e1f5c-118">Here are some of the regulations that are often referenced:</span></span>

- <span data-ttu-id="e1f5c-119">**ADR** — przepisy dotyczące międzynarodowego przewozu drogowego towarów niebezpiecznych</span><span class="sxs-lookup"><span data-stu-id="e1f5c-119">**ADR** – Regulations that are related to the international carriage of dangerous goods by road</span></span>
- <span data-ttu-id="e1f5c-120">**CFR 49** — przepisy w USA dot. przewozu towarów niebezpiecznych</span><span class="sxs-lookup"><span data-stu-id="e1f5c-120">**CFR 49** – Regulations in the United Sates for the carriage of dangerous goods</span></span>
- <span data-ttu-id="e1f5c-121">**IMDG** — Międzynarodowy kodeks ładunków niebezpiecznych (IMDG)</span><span class="sxs-lookup"><span data-stu-id="e1f5c-121">**IMDG** – The International Marine Dangerous Goods (IMDG) code</span></span>
- <span data-ttu-id="e1f5c-122">**IATA** — regulacje dotyczące towarów niebezpiecznych międzynarodowego zrzeszenia przewoźników powietrznych (IATA)</span><span class="sxs-lookup"><span data-stu-id="e1f5c-122">**IATA** – The International Air Transport Association (IATA) dangerous goods regulations</span></span>

<span data-ttu-id="e1f5c-123">Każde z tych rozporządzeń zawiera listę towarów niebezpiecznych, która zawiera kody referencyjne.</span><span class="sxs-lookup"><span data-stu-id="e1f5c-123">Each of these regulations has a dangerous goods list that includes reference codes.</span></span> <span data-ttu-id="e1f5c-124">Listy dla każdego typu transportu są łączone na wspólnych międzynarodowych klasyfikacjach.</span><span class="sxs-lookup"><span data-stu-id="e1f5c-124">The lists for each type of transport are combined on shared international classifications.</span></span> <span data-ttu-id="e1f5c-125">Program Supply Chain Management zawiera tabelę odwołań dla współdzielonych kodów z tych list.</span><span class="sxs-lookup"><span data-stu-id="e1f5c-125">Supply Chain Management provides a reference table for the shared codes in those lists.</span></span> <span data-ttu-id="e1f5c-126">Każda lista ma również kilka unikatowych kodów, które można zdefiniować.</span><span class="sxs-lookup"><span data-stu-id="e1f5c-126">Each list also has some unique codes that can be defined.</span></span>

<span data-ttu-id="e1f5c-127">Aby rozpocząć konfigurowanie tych informacji, należy utworzyć rozporządzenie, które będzie używane do konfigurowania początkowych parametrów.</span><span class="sxs-lookup"><span data-stu-id="e1f5c-127">To start to configure this information, create a regulation that you can use to configure the initial parameters.</span></span>

## <a name="warehouse-management"></a><span data-ttu-id="e1f5c-128">Zarządzanie magazynem</span><span class="sxs-lookup"><span data-stu-id="e1f5c-128">Warehouse management</span></span>

<span data-ttu-id="e1f5c-129">Po przygotowaniu wysyłki można wydrukować kilka nowych raportów.</span><span class="sxs-lookup"><span data-stu-id="e1f5c-129">When a shipment is prepared, several new reports can be printed.</span></span> <span data-ttu-id="e1f5c-130">W tych raportach są używane informacje skonfigurowane w module Zarządzanie informacjami o produktach.</span><span class="sxs-lookup"><span data-stu-id="e1f5c-130">These reports use the information that you set up in Product information management.</span></span>
