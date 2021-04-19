---
title: Skanowanie kodów kreskowych za pomocą aparatu w aplikacji mobilnej Warehouse Management
description: W tym temacie opisano, jak w rozwiązaniu aplikacja Warehouse Management skonfigurować skanowanie kodów kreskowych przy użyciu aparatu w urządzeniu przenośnym.
author: MarkusFogelberg
ms.date: 01/03/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileAppField
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2017-01-03
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 2f61f9c45b95b730a7f1743963658ec00abfbb56
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831225"
---
# <a name="scan-bar-codes-using-a-camera-in-the-warehouse-management-mobile-app"></a><span data-ttu-id="427e5-103">Skanowanie kodów kreskowych za pomocą aparatu w aplikacji mobilnej Warehouse Management</span><span class="sxs-lookup"><span data-stu-id="427e5-103">Scan bar codes using a camera in the Warehouse Management mobile app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="427e5-104">W tym temacie opisano, jak w rozwiązaniu aplikacja Warehouse Management skonfigurować skanowanie kodów kreskowych przy użyciu aparatu w urządzeniu przenośnym.</span><span class="sxs-lookup"><span data-stu-id="427e5-104">This topic explains how to set up the Warehouse Management mobile app to scan bar codes using a camera on a mobile device.</span></span>

## <a name="setup"></a><span data-ttu-id="427e5-105">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="427e5-105">Setup</span></span>

<span data-ttu-id="427e5-106">W aplikacji Warehouse Management w ustawieniach wyświetlania można określić, czy aparat ma być używany do skanowania kodów kreskowych.</span><span class="sxs-lookup"><span data-stu-id="427e5-106">In the display settings of the Warehouse Management mobile app, you can select if the camera should be used for bar code scanning.</span></span> <span data-ttu-id="427e5-107">Po włączeniu opcji **Używaj aparatu jako skanera** można używać aparatu do każdego pola wejściowego, które ma ustawiony preferowany tryb wprowadzania **Skanowanie**.</span><span class="sxs-lookup"><span data-stu-id="427e5-107">If you enable **Use the camera as scanner**, you can use the camera on every input field that has the preferred input mode set to **Scanning**.</span></span>

<span data-ttu-id="427e5-108">Aby określić, czy pole wejściowe powinno obsługiwać skanowanie, na stronie **Nazwy pól w aplikacji Magazynowanie** w ustawieniu **Preferowany tryb wprowadzania** zaznacz wartość **Skanowanie**.</span><span class="sxs-lookup"><span data-stu-id="427e5-108">To control whether an input field should be scannable, on the **Warehouse app field names** page, set **Preferred input mode** to **Scanning**.</span></span> <span data-ttu-id="427e5-109">Gdy ta opcja jest zaznaczona, aparat może służyć do skanowania w aplikacji Warehouse Management.</span><span class="sxs-lookup"><span data-stu-id="427e5-109">When this option is selected, a camera can be used for scanning in the Warehouse Management mobile app.</span></span> <span data-ttu-id="427e5-110">Aby uzyskać więcej informacji, zobacz temat [Konfigurowanie pól aplikacji mobilnej Warehouse Management](configure-app-field-names-priorities-warehouse.md).</span><span class="sxs-lookup"><span data-stu-id="427e5-110">For more information, see [Configure fields for the Warehouse Management mobile app](configure-app-field-names-priorities-warehouse.md).</span></span>

## <a name="supported-bar-code-formats"></a><span data-ttu-id="427e5-111">Obsługiwane formaty kodów kreskowych</span><span class="sxs-lookup"><span data-stu-id="427e5-111">Supported bar code formats</span></span>

<span data-ttu-id="427e5-112">Obsługiwane są najpopularniejsze formaty kodów kreskowych, w tym Kod 128, Kod 39, Kod 93, EAN-8, EAN-13, UPC-E, UPC-A i kody QR.</span><span class="sxs-lookup"><span data-stu-id="427e5-112">The most common bar code formats are supported, including Code 128, Code 39, Code 93, EAN-8, EAN-13, UPC-E, UPC-A, and QR codes.</span></span>

## <a name="navigation"></a><span data-ttu-id="427e5-113">Nawigacja</span><span class="sxs-lookup"><span data-stu-id="427e5-113">Navigation</span></span>

<span data-ttu-id="427e5-114">Strona Aparat będzie inicjowana z każdej strony, w której pole wejściowe ma ustawiony **Preferowany tryb wprowadzania** *Skanowanie*. Na stronie aparatu poniższe opcje służą do nawigowania:</span><span class="sxs-lookup"><span data-stu-id="427e5-114">The camera page will be initiated on each page where the input field has its **Preferred input mode** set to *Scanning*, when you are on the camera page use the following options to navigate:</span></span>

- <span data-ttu-id="427e5-115">Wybierz przycisk Wstecz, aby powrócić do strony **Zadanie i szczegóły**.</span><span class="sxs-lookup"><span data-stu-id="427e5-115">Select the back button to go back to the **Task and details** page.</span></span>
- <span data-ttu-id="427e5-116">Wybierz ikonę ołówka na stronie **Zadanie i szczegóły**, aby przejść do strony, gdzie można wpisać dane wejściowe ręcznie.</span><span class="sxs-lookup"><span data-stu-id="427e5-116">Select the pencil on the **Task and details** page to go to the page where you can type input manually.</span></span>
- <span data-ttu-id="427e5-117">Wybierz ikonę aparatu na stronie **Zadanie i szczegóły**, aby wrócić do strony Aparat.</span><span class="sxs-lookup"><span data-stu-id="427e5-117">Select the camera on the **Task and details** page to go back to the camera page.</span></span>

<span data-ttu-id="427e5-118">Na stronie Aparat po kliknięciu przycisku aparatu będzie on wyszarzony podczas próby zidentyfikowania kodu kreskowego.</span><span class="sxs-lookup"><span data-stu-id="427e5-118">On the camera page, when you select the camera button, it will appear dimmed while trying to identify a bar code.</span></span> <span data-ttu-id="427e5-119">Jeśli kod kreskowy nie zostanie zidentyfikowany w ciągu 5 sekund, upłynie limit czasu procesu, a przycisk aparatu znów stanie się dostępny.</span><span class="sxs-lookup"><span data-stu-id="427e5-119">If a bar code is not identified within 5 seconds, the process will time out and the camera button will become available again.</span></span> <span data-ttu-id="427e5-120">Wtedy będzie można ponownie spróbować zeskanować kod kreskowy.</span><span class="sxs-lookup"><span data-stu-id="427e5-120">You will then be able to try to scan a bar code again.</span></span>

<span data-ttu-id="427e5-121">Kierując aparat na kod kreskowy, w celu uzyskania najlepszego wyniku utrzymuj kod kreskowy w granicach nawiasów kwadratowych.</span><span class="sxs-lookup"><span data-stu-id="427e5-121">When you aim the camera at a bar code, keep the bar code aligned within the brackets for best result.</span></span> <span data-ttu-id="427e5-122">Jeśli kod kreskowy zostanie zeskanowany pomyślnie, rezultat zostanie przetworzony, po czym nastąpi przejście do następnego kroku.</span><span class="sxs-lookup"><span data-stu-id="427e5-122">When a bar code is scanned successfully, the result will be processed, and you will be taken to the next step.</span></span> <span data-ttu-id="427e5-123">Jeśli następny krok zawiera kolejne pole wejściowe z ustawionym preferowanym trybem wprowadzania Skanowanie, strona Aparat zostanie ponownie uruchomiona.</span><span class="sxs-lookup"><span data-stu-id="427e5-123">If the next step contains another input field with the preferred input mode set to Scanning, the camera page will start again.</span></span> <span data-ttu-id="427e5-124">Jeśli w następnym kroku nie występuje pole obsługujące skanowanie, strona Aparat nie zostanie zainicjowana.</span><span class="sxs-lookup"><span data-stu-id="427e5-124">If the next step is not a scanning field, then the camera page will not be initiated.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]