---
title: Włączanie wykrywania sklepu na podstawie lokalizacji
description: W tym temacie opisano sposób włączania wykrywania magazynu opartego na lokalizacji dla witryny Dynamics 365 Commerce.
author: brianshook
manager: annbe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 4d3a423bf64900e547a23f2e5eeb90aa679ec5d1
ms.sourcegitcommit: adf196c51e2b6f532d99c177b4c6778cea8a2efc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/02/2020
ms.locfileid: "3533397"
---
# <a name="enable-location-based-store-detection"></a><span data-ttu-id="593a4-103">Włączanie wykrywania sklepu na podstawie lokalizacji</span><span class="sxs-lookup"><span data-stu-id="593a4-103">Enable location-based store detection</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="593a4-104">W tym temacie opisano sposób włączania wykrywania magazynu opartego na lokalizacji dla witryny Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="593a4-104">This topic describes how to turn on location-based store detection for your Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="593a4-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="593a4-105">Overview</span></span>

<span data-ttu-id="593a4-106">Wykrywanie magazynu opartego na lokalizacji w module Commerce umożliwia dostarczanie klientom odpowiedniej zawartości oddziału na podstawie ich lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="593a4-106">Location-based store detection in Commerce lets you provide relevant site content to customers, based on their location.</span></span> <span data-ttu-id="593a4-107">Jeśli jest włączona funkcja wykrywania magazynu opartego na lokalizacji, usługa renderowanie Commerce będzie korzystać z informacji o kraju/regionie z adresu IP przeglądarki sieci Web klienta, aby skierować odbiorcę do najlepszej dostępnej konfiguracji geograficznej.</span><span class="sxs-lookup"><span data-stu-id="593a4-107">When location-based store detection is turned on, the Commerce rendering service uses the country/region information from the IP address of the customer's web browser to direct the customer to the best geographical site configuration that is available.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="593a4-108">Klauzula prywatności</span><span class="sxs-lookup"><span data-stu-id="593a4-108">Privacy notice</span></span>

<span data-ttu-id="593a4-109">Po włączeniu funkcji wykrywania magazynu opartego na lokalizacji informacje pochodzące z przeglądarki odbiorcy są wysyłane do usługi lokalizacyjnej firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="593a4-109">If you turn on the location-based store detection feature, information from the customer's browser is sent to a Microsoft location service.</span></span> <span data-ttu-id="593a4-110">Te informacje są następnie używane w celu udostępnienia zawartości odbiorcy, która jest odpowiednia dla jego lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="593a4-110">This information is then used to provide the customer content that is relevant to his or her location.</span></span> <span data-ttu-id="593a4-111">Zarówno informacje wysyłane z przeglądarki klienta, jak i informacje na temat lokalizacji zwracane klientowi podlegają zasadom zachowania poufności i plików cookie.</span><span class="sxs-lookup"><span data-stu-id="593a4-111">Both the information that is sent from the customer's browser and the location-based information that is returned to the customer are subject to privacy and cookie compliance policies.</span></span>

## <a name="turn-on-location-based-store-detection"></a><span data-ttu-id="593a4-112">Włączanie wykrywania sklepu na podstawie lokalizacji</span><span class="sxs-lookup"><span data-stu-id="593a4-112">Turn on location-based store detection</span></span>

<span data-ttu-id="593a4-113">Aby włączyć wykrywanie sklepu opartego na lokalizacji w module Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="593a4-113">To turn on location-based store detection in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="593a4-114">W narzędziu autorskim przejdź do swojej witryny.</span><span class="sxs-lookup"><span data-stu-id="593a4-114">In the authoring tool, go to your site.</span></span>
1. <span data-ttu-id="593a4-115">W okienku nawigacji po lewej stronie zaznacz **Zarządzanie witryną**.</span><span class="sxs-lookup"><span data-stu-id="593a4-115">In the navigation pane on the left, select **Site Management**.</span></span>
1. <span data-ttu-id="593a4-116">Wubierz **Ustawienia witryny**.</span><span class="sxs-lookup"><span data-stu-id="593a4-116">Select **Site Settings**.</span></span>
1. <span data-ttu-id="593a4-117">Ustaw opcję **Włącz wykrywanie sklepu na podstawie lokalizacji** na **Włącz**.</span><span class="sxs-lookup"><span data-stu-id="593a4-117">Set the **Enable location based store detection** option to **On**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="593a4-118">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="593a4-118">Additional resources</span></span>

[<span data-ttu-id="593a4-119">Konfigurowanie nazwy domeny</span><span class="sxs-lookup"><span data-stu-id="593a4-119">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="593a4-120">Wdrażanie nowej witryny handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="593a4-120">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="593a4-121">Tworzenie witryny handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="593a4-121">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="593a4-122">Kojarzenie witryny online z kanałem</span><span class="sxs-lookup"><span data-stu-id="593a4-122">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="593a4-123">Zarządzanie plikami robots.txt</span><span class="sxs-lookup"><span data-stu-id="593a4-123">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="593a4-124">Przekaż adresy URL przekierowań luzem</span><span class="sxs-lookup"><span data-stu-id="593a4-124">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="593a4-125">Konfigurowanie dzierżawy B2C w usłudze Commerce</span><span class="sxs-lookup"><span data-stu-id="593a4-125">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="593a4-126">Konfigurowanie stron niestandardowych do logowań użytkowników</span><span class="sxs-lookup"><span data-stu-id="593a4-126">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="593a4-127">Konfigurowanie wielu dzierżawców B2C w środowisku Commerce</span><span class="sxs-lookup"><span data-stu-id="593a4-127">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="593a4-128">Dodawanie obsługi dla sieci dostarczania zawartości (CDN)</span><span class="sxs-lookup"><span data-stu-id="593a4-128">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)
