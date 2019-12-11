---
title: Włączanie wykrywania sklepu na podstawie lokalizacji
description: W tym temacie opisano sposób włączania wykrywania magazynu opartego na lokalizacji dla witryny Dynamics 365 Commerce.
author: brianshook
manager: annbe
ms.date: 10/01/2019
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
ms.openlocfilehash: a542d6987280451910b4ff3bcfb3a109a0e028c6
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697619"
---
# <a name="enable-location-based-store-detection"></a><span data-ttu-id="e8445-103">Włączanie wykrywania sklepu na podstawie lokalizacji</span><span class="sxs-lookup"><span data-stu-id="e8445-103">Enable location-based store detection</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="e8445-104">W tym temacie opisano sposób włączania wykrywania magazynu opartego na lokalizacji dla witryny Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e8445-104">This topic describes how to turn on location-based store detection for your Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="e8445-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="e8445-105">Overview</span></span>

<span data-ttu-id="e8445-106">Wykrywanie magazynu opartego na lokalizacji w module Commerce umożliwia dostarczanie klientom odpowiedniej zawartości oddziału na podstawie ich lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="e8445-106">Location-based store detection in Commerce lets you provide relevant site content to customers, based on their location.</span></span> <span data-ttu-id="e8445-107">Jeśli jest włączona funkcja wykrywania magazynu opartego na lokalizacji, usługa renderowanie Commerce będzie korzystać z informacji o kraju/regionie z adresu IP przeglądarki sieci Web klienta, aby skierować odbiorcę do najlepszej dostępnej konfiguracji geograficznej.</span><span class="sxs-lookup"><span data-stu-id="e8445-107">When location-based store detection is turned on, the Commerce rendering service uses the country/region information from the IP address of the customer's web browser to direct the customer to the best geographical site configuration that is available.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="e8445-108">Klauzula prywatności</span><span class="sxs-lookup"><span data-stu-id="e8445-108">Privacy notice</span></span>

<span data-ttu-id="e8445-109">Po włączeniu funkcji wykrywania magazynu opartego na lokalizacji informacje pochodzące z przeglądarki odbiorcy są wysyłane do usługi lokalizacyjnej firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e8445-109">If you turn on the location-based store detection feature, information from the customer's browser is sent to a Microsoft location service.</span></span> <span data-ttu-id="e8445-110">Te informacje są następnie używane w celu udostępnienia zawartości odbiorcy, która jest odpowiednia dla jego lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="e8445-110">This information is then used to provide the customer content that is relevant to his or her location.</span></span> <span data-ttu-id="e8445-111">Zarówno informacje wysyłane z przeglądarki klienta, jak i informacje na temat lokalizacji zwracane klientowi podlegają zasadom zachowania poufności i plików cookie.</span><span class="sxs-lookup"><span data-stu-id="e8445-111">Both the information that is sent from the customer's browser and the location-based information that is returned to the customer are subject to privacy and cookie compliance policies.</span></span>

## <a name="turn-on-location-based-store-detection"></a><span data-ttu-id="e8445-112">Włączanie wykrywania sklepu na podstawie lokalizacji</span><span class="sxs-lookup"><span data-stu-id="e8445-112">Turn on location-based store detection</span></span>

<span data-ttu-id="e8445-113">Aby włączyć wykrywanie sklepu opartego na lokalizacji w module Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="e8445-113">To turn on location-based store detection in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="e8445-114">W narzędziu autorskim przejdź do swojej witryny.</span><span class="sxs-lookup"><span data-stu-id="e8445-114">In the authoring tool, go to your site.</span></span>
1. <span data-ttu-id="e8445-115">W okienku nawigacji po lewej stronie zaznacz **Zarządzanie witryną**.</span><span class="sxs-lookup"><span data-stu-id="e8445-115">In the navigation pane on the left, select **Site Management**.</span></span>
1. <span data-ttu-id="e8445-116">Wubierz **Ustawienia witryny**.</span><span class="sxs-lookup"><span data-stu-id="e8445-116">Select **Site Settings**.</span></span>
1. <span data-ttu-id="e8445-117">Ustaw opcję **Włącz wykrywanie sklepu na podstawie lokalizacji** na **Włącz**.</span><span class="sxs-lookup"><span data-stu-id="e8445-117">Set the **Enable location based store detection** option to **On**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e8445-118">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="e8445-118">Additional resources</span></span>

[<span data-ttu-id="e8445-119">Omówienie sklepu internetowego</span><span class="sxs-lookup"><span data-stu-id="e8445-119">Online store overview</span></span>](online-store-overview.md)

[<span data-ttu-id="e8445-120">Tworzenie witryny handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="e8445-120">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="e8445-121">Wdrażanie nowej witryny handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="e8445-121">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="e8445-122">Kojarzenie witryny online z kanałem</span><span class="sxs-lookup"><span data-stu-id="e8445-122">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="e8445-123">Konfigurowanie nazwy domeny</span><span class="sxs-lookup"><span data-stu-id="e8445-123">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="e8445-124">Dodaj obsługę dla sieci dostarczania zawartości (CDN)</span><span class="sxs-lookup"><span data-stu-id="e8445-124">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="e8445-125">Konfigurowanie stron niestandardowych do logowań użytkowników</span><span class="sxs-lookup"><span data-stu-id="e8445-125">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)
