---
title: Skanowanie kodów kreskowych za pomocą aparatu w rozwiązaniu – aplikacja magazynowa
description: W tym temacie opisano, jak w rozwiązaniu aplikacja magazynowa skonfigurować skanowanie kodów kreskowych przy użyciu aparatu w urządzeniu przenośnym.
author: MarkusFogelberg
manager: tfehr
ms.date: 01/03/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSMobileAppField
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2017-01-03
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 28a49736f43bd2d3bfd4c6856f2f87079a005ba2
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5239309"
---
# <a name="scan-bar-codes-using-a-camera-in-the-warehouse-app"></a><span data-ttu-id="90430-103">Skanowanie kodów kreskowych za pomocą aparatu w rozwiązaniu – aplikacja magazynowa</span><span class="sxs-lookup"><span data-stu-id="90430-103">Scan bar codes using a camera in the warehouse app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="90430-104">W tym temacie opisano, jak w rozwiązaniu aplikacja magazynowa skonfigurować skanowanie kodów kreskowych przy użyciu aparatu w urządzeniu przenośnym.</span><span class="sxs-lookup"><span data-stu-id="90430-104">This topic explains how to set up the warehouse app to scan bar codes using a camera on a mobile device.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="90430-105">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="90430-105">Prerequisites</span></span>
<span data-ttu-id="90430-106">Aby można było używać tej funkcji, trzeba mieć zainstalowaną wersję 1.2.0.0 aplikacji magazynowej, a urządzenie musi być wyposażone w aparat.</span><span class="sxs-lookup"><span data-stu-id="90430-106">To use this feature, you need to have version 1.2.0.0 of the warehouse app installed, and your device must have a camera.</span></span> <span data-ttu-id="90430-107">Gdy otworzysz aplikację po zaktualizowaniu, pojawi się monit o pozwolenie aplikacji na używanie aparatu.</span><span class="sxs-lookup"><span data-stu-id="90430-107">When you open the app after updating, you will be prompted to allow the app to use the camera.</span></span> <span data-ttu-id="90430-108">Jeśli urządzenie nie ma aparatu, monit nie będzie wyświetlany i nie będzie można używać aparatu jako skanera.</span><span class="sxs-lookup"><span data-stu-id="90430-108">If your device doesn’t have a camera, no prompt will be shown, and you will not be able to use a camera as a scanner.</span></span> 

## <a name="setup"></a><span data-ttu-id="90430-109">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="90430-109">Setup</span></span>
<span data-ttu-id="90430-110">W aplikacji magazynowej w ustawieniach wyświetlania można określić, czy aparat ma być używany do skanowania kodów kreskowych.</span><span class="sxs-lookup"><span data-stu-id="90430-110">In the Display settings of the warehouse application, you can select if the camera should be used for bar code scanning.</span></span> <span data-ttu-id="90430-111">Po włączeniu opcji **Używaj aparatu jako skanera** można używać aparatu do każdego pola wejściowego, które ma ustawiony preferowany tryb wprowadzania **Skanowanie**.</span><span class="sxs-lookup"><span data-stu-id="90430-111">If you enable **Use the camera as scanner**, you can use the camera on every input field that has the preferred input mode set to **Scanning**.</span></span> 

<span data-ttu-id="90430-112">Aby określić, czy pole wejściowe powinno obsługiwać skanowanie, na stronie **Nazwy pól w aplikacji Magazynowanie** w ustawieniu **Preferowany tryb wprowadzania** zaznacz wartość **Skanowanie**.</span><span class="sxs-lookup"><span data-stu-id="90430-112">To control whether an input field should be scannable, on the **Warehouse app field names** page, set **Preferred input mode** to **Scanning**.</span></span> <span data-ttu-id="90430-113">Gdy ta opcja jest zaznaczona, aparat może służyć do skanowania w aplikacji magazynowej.</span><span class="sxs-lookup"><span data-stu-id="90430-113">When this option is selected, a camera can be used for scanning in the warehouse app.</span></span> <span data-ttu-id="90430-114">Aby uzyskać informacje dotyczące sposobu konfigurowania nazw pól w aplikacji magazynowej, zobacz [Konfigurowanie nazw pól aplikacji w aplikacji magazynowej](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/warehousing/configure-app-field-names-priorities-warehouse).</span><span class="sxs-lookup"><span data-stu-id="90430-114">For information about how to configure app field names in Warehousing, see [Configure app field names in warehouse app](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/warehousing/configure-app-field-names-priorities-warehouse).</span></span>

## <a name="supported-bar-code-formats"></a><span data-ttu-id="90430-115">Obsługiwane formaty kodów kreskowych</span><span class="sxs-lookup"><span data-stu-id="90430-115">Supported bar code formats</span></span>
<span data-ttu-id="90430-116">Obsługiwane są najpopularniejsze formaty kodów kreskowych, w tym Kod 128, Kod 39, Kod 93, EAN-8, EAN-13, UPC-E, UPC-A i kody QR.</span><span class="sxs-lookup"><span data-stu-id="90430-116">The most common bar code formats are supported, including Code 128, Code 39, Code 93, EAN-8, EAN-13, UPC-E, UPC-A, and QR codes.</span></span> 

## <a name="navigation"></a><span data-ttu-id="90430-117">Nawigacja</span><span class="sxs-lookup"><span data-stu-id="90430-117">Navigation</span></span>
<span data-ttu-id="90430-118">Strona Aparat będzie inicjowana z każdej strony, w której pole wejściowe ma ustawiony preferowany tryb wprowadzania Skanowanie. Na stronie Aparat poniższe opcje służą do nawigowania:</span><span class="sxs-lookup"><span data-stu-id="90430-118">The camera page will be initiated on each page where the input field has the preferred input mode set to Scanning, when you are on the Camera page use the following options to navigate:</span></span>
- <span data-ttu-id="90430-119">Kliknij przycisk Wstecz, aby powrócić do strony Zadanie i szczegóły.</span><span class="sxs-lookup"><span data-stu-id="90430-119">Click the back button to go back to the Task and details page.</span></span> 
- <span data-ttu-id="90430-120">Kliknij ikonę ołówka na stronie Zadanie i szczegóły, aby przejść do strony, gdzie można wpisać dane wejściowe ręcznie.</span><span class="sxs-lookup"><span data-stu-id="90430-120">Click the pencil on the Task and details page to go to the page where you can type input manually.</span></span>
- <span data-ttu-id="90430-121">Kliknij ikonę aparatu na stronie Zadanie i szczegóły, aby wrócić do strony Aparat.</span><span class="sxs-lookup"><span data-stu-id="90430-121">Click the camera on the Task and details page to go back to the Camera page.</span></span> 

| <span data-ttu-id="90430-122">Strona Zadanie i szczegóły</span><span class="sxs-lookup"><span data-stu-id="90430-122">Task and details page</span></span> | <span data-ttu-id="90430-123">Strona Aparat</span><span class="sxs-lookup"><span data-stu-id="90430-123">Camera page</span></span> | 
| :---------------------: | :--------------------: |
| ![Strona Szczegóły przykładowego zadania skanowania kamery](./media/camera-scanning-example-task-detail-page50.png)          | ![Mniejsza strona przykładowej kamery skanowania kamery](./media/camera-scanning-example-camera-page50.png)          |

<span data-ttu-id="90430-126">Na stronie Aparat po kliknięciu przycisku Aparat będzie on wyszarzony podczas próby zidentyfikowania kodu kreskowego.</span><span class="sxs-lookup"><span data-stu-id="90430-126">On the camera page, when you click the Camera button, it will appear dimmed while trying to identify a bar code.</span></span> <span data-ttu-id="90430-127">Jeśli kod kreskowy nie zostanie zidentyfikowany w ciągu 5 sekund, upłynie limit czasu procesu, a przycisk aparatu znów stanie się dostępny.</span><span class="sxs-lookup"><span data-stu-id="90430-127">If a bar code is not identified within 5 seconds, the process will time out and the Camera button will become available again.</span></span> <span data-ttu-id="90430-128">Wtedy będzie można ponownie spróbować zeskanować kod kreskowy.</span><span class="sxs-lookup"><span data-stu-id="90430-128">You will then be able to try to scan a bar code again.</span></span>

<span data-ttu-id="90430-129">Kierując aparat na kod kreskowy, w celu uzyskania najlepszego wyniku utrzymuj kod kreskowy w granicach nawiasów kwadratowych.</span><span class="sxs-lookup"><span data-stu-id="90430-129">When you aim the camera at a bar code, keep the bar code aligned within the brackets for best result.</span></span> <span data-ttu-id="90430-130">Jeśli kod kreskowy zostanie zeskanowany pomyślnie, rezultat zostanie przetworzony, po czym nastąpi przejście do następnego kroku.</span><span class="sxs-lookup"><span data-stu-id="90430-130">When a bar code is scanned successfully, the result will be processed, and you will be taken to the next step.</span></span> <span data-ttu-id="90430-131">Jeśli następny krok zawiera kolejne pole wejściowe z ustawionym preferowanym trybem wprowadzania Skanowanie, strona Aparat zostanie ponownie uruchomiona.</span><span class="sxs-lookup"><span data-stu-id="90430-131">If the next step contains another input field with the preferred input mode set to Scanning, the camera page will start again.</span></span> <span data-ttu-id="90430-132">Jeśli w następnym kroku nie występuje pole obsługujące skanowanie, strona Aparat nie zostanie zainicjowana.</span><span class="sxs-lookup"><span data-stu-id="90430-132">If the next step is not a scanning field, then the camera page will not be initiated.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]