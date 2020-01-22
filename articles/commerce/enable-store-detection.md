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
ms.openlocfilehash: c5fb59a9798e2cddfb75b71235ee7754e54b0e28
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/09/2020
ms.locfileid: "2945785"
---
# <a name="enable-location-based-store-detection"></a><span data-ttu-id="1f1b9-103">Włączanie wykrywania sklepu na podstawie lokalizacji</span><span class="sxs-lookup"><span data-stu-id="1f1b9-103">Enable location-based store detection</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="1f1b9-104">W tym temacie opisano sposób włączania wykrywania magazynu opartego na lokalizacji dla witryny Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1f1b9-104">This topic describes how to turn on location-based store detection for your Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="1f1b9-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="1f1b9-105">Overview</span></span>

<span data-ttu-id="1f1b9-106">Wykrywanie magazynu opartego na lokalizacji w module Commerce umożliwia dostarczanie klientom odpowiedniej zawartości oddziału na podstawie ich lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="1f1b9-106">Location-based store detection in Commerce lets you provide relevant site content to customers, based on their location.</span></span> <span data-ttu-id="1f1b9-107">Jeśli jest włączona funkcja wykrywania magazynu opartego na lokalizacji, usługa renderowanie Commerce będzie korzystać z informacji o kraju/regionie z adresu IP przeglądarki sieci Web klienta, aby skierować odbiorcę do najlepszej dostępnej konfiguracji geograficznej.</span><span class="sxs-lookup"><span data-stu-id="1f1b9-107">When location-based store detection is turned on, the Commerce rendering service uses the country/region information from the IP address of the customer's web browser to direct the customer to the best geographical site configuration that is available.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="1f1b9-108">Klauzula prywatności</span><span class="sxs-lookup"><span data-stu-id="1f1b9-108">Privacy notice</span></span>

<span data-ttu-id="1f1b9-109">Po włączeniu funkcji wykrywania magazynu opartego na lokalizacji informacje pochodzące z przeglądarki odbiorcy są wysyłane do usługi lokalizacyjnej firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1f1b9-109">If you turn on the location-based store detection feature, information from the customer's browser is sent to a Microsoft location service.</span></span> <span data-ttu-id="1f1b9-110">Te informacje są następnie używane w celu udostępnienia zawartości odbiorcy, która jest odpowiednia dla jego lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="1f1b9-110">This information is then used to provide the customer content that is relevant to his or her location.</span></span> <span data-ttu-id="1f1b9-111">Zarówno informacje wysyłane z przeglądarki klienta, jak i informacje na temat lokalizacji zwracane klientowi podlegają zasadom zachowania poufności i plików cookie.</span><span class="sxs-lookup"><span data-stu-id="1f1b9-111">Both the information that is sent from the customer's browser and the location-based information that is returned to the customer are subject to privacy and cookie compliance policies.</span></span>

## <a name="turn-on-location-based-store-detection"></a><span data-ttu-id="1f1b9-112">Włączanie wykrywania sklepu na podstawie lokalizacji</span><span class="sxs-lookup"><span data-stu-id="1f1b9-112">Turn on location-based store detection</span></span>

<span data-ttu-id="1f1b9-113">Aby włączyć wykrywanie sklepu opartego na lokalizacji w module Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="1f1b9-113">To turn on location-based store detection in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="1f1b9-114">W narzędziu autorskim przejdź do swojej witryny.</span><span class="sxs-lookup"><span data-stu-id="1f1b9-114">In the authoring tool, go to your site.</span></span>
1. <span data-ttu-id="1f1b9-115">W okienku nawigacji po lewej stronie zaznacz **Zarządzanie witryną**.</span><span class="sxs-lookup"><span data-stu-id="1f1b9-115">In the navigation pane on the left, select **Site Management**.</span></span>
1. <span data-ttu-id="1f1b9-116">Wubierz **Ustawienia witryny**.</span><span class="sxs-lookup"><span data-stu-id="1f1b9-116">Select **Site Settings**.</span></span>
1. <span data-ttu-id="1f1b9-117">Ustaw opcję **Włącz wykrywanie sklepu na podstawie lokalizacji** na **Włącz**.</span><span class="sxs-lookup"><span data-stu-id="1f1b9-117">Set the **Enable location based store detection** option to **On**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1f1b9-118">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="1f1b9-118">Additional resources</span></span>

[<span data-ttu-id="1f1b9-119">Konfigurowanie nazwy domeny</span><span class="sxs-lookup"><span data-stu-id="1f1b9-119">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="1f1b9-120">Wdrażanie nowej witryny handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="1f1b9-120">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="1f1b9-121">Tworzenie witryny handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="1f1b9-121">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="1f1b9-122">Kojarzenie witryny online z kanałem</span><span class="sxs-lookup"><span data-stu-id="1f1b9-122">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="1f1b9-123">Zarządzanie plikami robots.txt</span><span class="sxs-lookup"><span data-stu-id="1f1b9-123">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="1f1b9-124">Konfigurowanie stron niestandardowych do logowań użytkowników</span><span class="sxs-lookup"><span data-stu-id="1f1b9-124">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="1f1b9-125">Dodawanie obsługi dla sieci dostarczania zawartości (CDN)</span><span class="sxs-lookup"><span data-stu-id="1f1b9-125">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)
