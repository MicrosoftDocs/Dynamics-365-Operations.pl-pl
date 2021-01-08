---
title: Moduł zgody na pliki cookie
description: W tym temacie opisano moduły zgody na pliki cookie i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 60ce530575841c22355e4a14e8b0bbec6c0e35ab
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4414840"
---
# <a name="cookie-consent-module"></a><span data-ttu-id="2e0dd-103">Moduł zgody na pliki cookie</span><span class="sxs-lookup"><span data-stu-id="2e0dd-103">Cookie consent module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2e0dd-104">W tym temacie opisano moduły zgody na pliki cookie i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-104">This topic covers cookie consent modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="2e0dd-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="2e0dd-105">Overview</span></span>

<span data-ttu-id="2e0dd-106">Moduł zgody na pliki cookie wysyła użytkownikom zapytanie o udzielenie zgody na używanie plików cookie na potrzeby funkcji lub modułu śledzącego pliki cookie przeglądarki.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-106">The cookie consent module prompts site users to explicitly provide consent to allow cookies for any feature or module that tracks browser cookies.</span></span> <span data-ttu-id="2e0dd-107">Zgoda jest wymagana w momencie, gdy użytkownik odwiedzający witrynę po raz pierwszy przegląda witrynę w nowej sesji przeglądarki.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-107">The consent is required the first time a site user browses a site in a new browser session.</span></span> <span data-ttu-id="2e0dd-108">Po otrzymaniu zgody pliki będą śledzone, a użytkownik witryny nie będzie ponownie pytany o zgodę.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-108">When consent is received, it is tracked and the site user will not be prompted for consent again.</span></span> <span data-ttu-id="2e0dd-109">Aby uzyskać więcej informacji, zajrzyj do [Zgodność z plikami cookie](cookie-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="2e0dd-109">For more information, see [Cookie compliance](cookie-compliance.md).</span></span>

<span data-ttu-id="2e0dd-110">Jeśli nie otrzymano zgody na wykorzystanie pliku cookie, wszelkie funkcje lub moduły wymagające zgody na plik cookie nie będą wykorzystywane na stronie.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-110">If site user cookie consent is not received, any features or modules that require cookie consent will not be rendered on the page.</span></span> <span data-ttu-id="2e0dd-111">Na przykład, moduł realizacji transakcji, moduł udostępniania w mediach społecznościowych i moduł preferowanego sklepu wymagają wyrażenia zgody na wykorzystanie pliku cookie i nie będą wykorzystywane, jeśli nie otrzymano zgody użytkownika.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-111">For example, the checkout module, social share module, and preferred store feature all require cookie consent and will not be rendered if site user consent is not received.</span></span> 

<span data-ttu-id="2e0dd-112">Moduł zgody na wykorzystanie plików cookie można skonfigurować na fragmencie nagłówka strony, dzięki czemu można wymusić jego załadowanie podczas.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-112">A cookie consent module can be configured on a page's header fragment so that it can be enforced when the page loads.</span></span> <span data-ttu-id="2e0dd-113">Moduł zgody na wykorzystanie plików cookie powinien zawierać jasny komunikat informujący użytkownika witryny o sposobie użycia plików cookie w witrynie i powinien zawierać łącze do strony prywatności witryny.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-113">The cookie consent module should have a clear message informing the site user about cookie usage on the site and should provide a link to the site's privacy page.</span></span>

<span data-ttu-id="2e0dd-114">Na poniższej ilustracji przedstawiono przykład prośby o udzielenie zgody na wykorzystanie pliku cookie z łączem do strony zasady prywatności witryny, który wyświetlany jest w nagłówku strony witryny.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-114">The following illustration highlights an example of a cookie consent message with a link to the site's privacy policy page displayed on the header of a site page.</span></span>
<span data-ttu-id="2e0dd-115">![Przykład modułu zgody na wykorzystanie plików cookie](./media/ecommerce-cookieconsent.png)</span><span class="sxs-lookup"><span data-stu-id="2e0dd-115">![Example of a cookie consent module](./media/ecommerce-cookieconsent.png)</span></span>

## <a name="cookie-consent-module-properties"></a><span data-ttu-id="2e0dd-116">Moduł zgody na wykorzystanie plików cookie — właściwości</span><span class="sxs-lookup"><span data-stu-id="2e0dd-116">Cookie consent module properties</span></span>

| <span data-ttu-id="2e0dd-117">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="2e0dd-117">Property name</span></span>             | <span data-ttu-id="2e0dd-118">Wartość</span><span class="sxs-lookup"><span data-stu-id="2e0dd-118">Value</span></span>                 | <span data-ttu-id="2e0dd-119">opis</span><span class="sxs-lookup"><span data-stu-id="2e0dd-119">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="2e0dd-120">Tekst sformatowany</span><span class="sxs-lookup"><span data-stu-id="2e0dd-120">Rich Text</span></span>                  | <span data-ttu-id="2e0dd-121">Tekst sformatowany</span><span class="sxs-lookup"><span data-stu-id="2e0dd-121">Rich Text</span></span> | <span data-ttu-id="2e0dd-122">Określa powiadomienie w postaci tekstu sformatowanego dla użytkowników witryny mówiące o tym, że witryna korzysta z plików cookie, a użytkownicy powinni zaakceptować użycie plików cookie w celu zapewnienia pełni funkcjonalności witryny.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-122">Specifies a Rich Text notification to site users that the site uses browser cookies and that users should accept the use of cookies for the site to be fully functional.</span></span> |
| <span data-ttu-id="2e0dd-123">Linki</span><span class="sxs-lookup"><span data-stu-id="2e0dd-123">Links</span></span> | <span data-ttu-id="2e0dd-124">Adres URL</span><span class="sxs-lookup"><span data-stu-id="2e0dd-124">URL</span></span> | <span data-ttu-id="2e0dd-125">Co najmniej jedno łącze można dodać do strony dotyczącej prywatności witryny, która opisuje typy plików cookie śledzonych w witrynie.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-125">One or more links can be added to a site's privacy page that describes the types of cookies that are tracked on the site.</span></span> |

## <a name="add-a-cookie-consent-module-to-site-pages"></a><span data-ttu-id="2e0dd-126">Dodaj moduł zgody na pliki cookie do stron witryny</span><span class="sxs-lookup"><span data-stu-id="2e0dd-126">Add a cookie consent module to site pages</span></span>

<span data-ttu-id="2e0dd-127">Aby efektywnie dodać moduł zgody na pliki cookie do wielu stron w witrynie, można go dodać do fragmentu współużytkowanego nagłówka strony.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-127">To efficiently add a cookie consent module to multiple site pages, it can be added to a shared page header fragment.</span></span> <span data-ttu-id="2e0dd-128">Po dodaniu fragmentu nagłówka do wszystkich stron w witrynie powiadomienie o zgodzie na wykorzystanie pliku cookie będzie automatycznie renderowane przy pierwszym przejściu użytkownika do dowolnej strony witryny.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-128">After the header fragment is added to all site pages, a cookie consent notification will automatically be rendered the first time a site user navigates to any site page.</span></span>

<span data-ttu-id="2e0dd-129">Aby uzyskać więcej informacji o fragmentach i modułach nagłówka, skorzystaj z tematu [nagłówek modułu](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="2e0dd-129">For more information about header fragments and modules, see [Header module](author-header-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2e0dd-130">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="2e0dd-130">Additional resources</span></span>

[<span data-ttu-id="2e0dd-131">Omówienie biblioteki modułów</span><span class="sxs-lookup"><span data-stu-id="2e0dd-131">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="2e0dd-132">Moduł nagłówka</span><span class="sxs-lookup"><span data-stu-id="2e0dd-132">Header module</span></span>](author-header-module.md) 

[<span data-ttu-id="2e0dd-133">Zgodność z plikami cookie</span><span class="sxs-lookup"><span data-stu-id="2e0dd-133">Cookie compliance</span></span>](cookie-compliance.md)
