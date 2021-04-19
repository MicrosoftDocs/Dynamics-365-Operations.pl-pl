---
title: Włączanie wykrywania sklepu na podstawie lokalizacji
description: W tym temacie opisano sposób włączania wykrywania magazynu opartego na lokalizacji dla witryny Dynamics 365 Commerce.
author: brianshook
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 71e523cab20281d5db7efff40b5ef4f7293a4765
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799138"
---
# <a name="enable-location-based-store-detection"></a><span data-ttu-id="b1737-103">Włączanie wykrywania sklepu na podstawie lokalizacji</span><span class="sxs-lookup"><span data-stu-id="b1737-103">Enable location-based store detection</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b1737-104">W tym temacie opisano sposób włączania wykrywania magazynu opartego na lokalizacji dla witryny Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b1737-104">This topic describes how to turn on location-based store detection for your Dynamics 365 Commerce site.</span></span>

<span data-ttu-id="b1737-105">Wykrywanie magazynu opartego na lokalizacji w module Commerce umożliwia dostarczanie klientom odpowiedniej zawartości oddziału na podstawie ich lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="b1737-105">Location-based store detection in Commerce lets you provide relevant site content to customers, based on their location.</span></span> <span data-ttu-id="b1737-106">Jeśli jest włączona funkcja wykrywania magazynu opartego na lokalizacji, usługa renderowanie Commerce będzie korzystać z informacji o kraju/regionie z adresu IP przeglądarki sieci Web klienta, aby skierować odbiorcę do najlepszej dostępnej konfiguracji geograficznej.</span><span class="sxs-lookup"><span data-stu-id="b1737-106">When location-based store detection is turned on, the Commerce rendering service uses the country/region information from the IP address of the customer's web browser to direct the customer to the best geographical site configuration that is available.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="b1737-107">Klauzula prywatności</span><span class="sxs-lookup"><span data-stu-id="b1737-107">Privacy notice</span></span>

<span data-ttu-id="b1737-108">Po włączeniu funkcji wykrywania magazynu opartego na lokalizacji informacje pochodzące z przeglądarki odbiorcy są wysyłane do usługi lokalizacyjnej firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b1737-108">If you turn on the location-based store detection feature, information from the customer's browser is sent to a Microsoft location service.</span></span> <span data-ttu-id="b1737-109">Te informacje są następnie używane w celu udostępnienia zawartości odbiorcy, która jest odpowiednia dla jego lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="b1737-109">This information is then used to provide the customer content that is relevant to his or her location.</span></span> <span data-ttu-id="b1737-110">Zarówno informacje wysyłane z przeglądarki klienta, jak i informacje na temat lokalizacji zwracane klientowi podlegają zasadom zachowania poufności i plików cookie.</span><span class="sxs-lookup"><span data-stu-id="b1737-110">Both the information that is sent from the customer's browser and the location-based information that is returned to the customer are subject to privacy and cookie compliance policies.</span></span>

## <a name="turn-on-location-based-store-detection"></a><span data-ttu-id="b1737-111">Włączanie wykrywania sklepu na podstawie lokalizacji</span><span class="sxs-lookup"><span data-stu-id="b1737-111">Turn on location-based store detection</span></span>

<span data-ttu-id="b1737-112">Aby włączyć wykrywanie sklepu opartego na lokalizacji w module Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="b1737-112">To turn on location-based store detection in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="b1737-113">W narzędziu autorskim przejdź do swojej witryny.</span><span class="sxs-lookup"><span data-stu-id="b1737-113">In the authoring tool, go to your site.</span></span>
1. <span data-ttu-id="b1737-114">W okienku nawigacji po lewej stronie zaznacz **Zarządzanie witryną**.</span><span class="sxs-lookup"><span data-stu-id="b1737-114">In the navigation pane on the left, select **Site Management**.</span></span>
1. <span data-ttu-id="b1737-115">Wubierz **Ustawienia witryny**.</span><span class="sxs-lookup"><span data-stu-id="b1737-115">Select **Site Settings**.</span></span>
1. <span data-ttu-id="b1737-116">Ustaw opcję **Włącz wykrywanie sklepu na podstawie lokalizacji** na **Włącz**.</span><span class="sxs-lookup"><span data-stu-id="b1737-116">Set the **Enable location based store detection** option to **On**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b1737-117">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="b1737-117">Additional resources</span></span>

[<span data-ttu-id="b1737-118">Konfigurowanie nazwy domeny</span><span class="sxs-lookup"><span data-stu-id="b1737-118">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="b1737-119">Wdrażanie nowej dzierżawy handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="b1737-119">Deploy a new e-commerce tenant</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="b1737-120">Tworzenie witryny handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="b1737-120">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="b1737-121">Kojarzenie witryny Dynamics 365 Commerce z kanałem online</span><span class="sxs-lookup"><span data-stu-id="b1737-121">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="b1737-122">Zarządzanie plikami robots.txt</span><span class="sxs-lookup"><span data-stu-id="b1737-122">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="b1737-123">Zbiorowe przekazanie przekierowań adresów URL</span><span class="sxs-lookup"><span data-stu-id="b1737-123">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="b1737-124">Konfigurowanie dzierżawy B2C w usłudze Commerce</span><span class="sxs-lookup"><span data-stu-id="b1737-124">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="b1737-125">Konfigurowanie stron niestandardowych do logowań użytkowników</span><span class="sxs-lookup"><span data-stu-id="b1737-125">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="b1737-126">Konfigurowanie wielu dzierżawców B2C w środowisku Commerce</span><span class="sxs-lookup"><span data-stu-id="b1737-126">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="b1737-127">Dodawanie obsługi dla sieci dostarczania zawartości (CDN)</span><span class="sxs-lookup"><span data-stu-id="b1737-127">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
