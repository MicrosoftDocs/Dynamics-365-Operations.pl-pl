---
title: Skanowanie kodów kreskowych za pomocą aparatu w rozwiązaniu Dynamics 365 for Finance and Operations – aplikacja Magazynowanie
description: W tym temacie opisano, jak w rozwiązaniu Dynamics 365 for Finance and Operations – aplikacja Magazynowanie skonfigurować skanowanie kodów kreskowych przy użyciu aparatu w urządzeniu przenośnym.
author: MarkusFogelberg
manager: AnnBe
ms.date: 01/03/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSMobileAppField
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2017-01-03
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 58cf27a250778d68bdffa1eefa5e939276e467fc
ms.sourcegitcommit: dd960cf07d8be791fd27c7bb72e6baa2d63ccd51
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/14/2019
ms.locfileid: "2578156"
---
# <a name="scan-bar-codes-using-a-camera-in-dynamics-365-supply-chain-management---warehousing-app"></a><span data-ttu-id="47caf-103">Skanowanie kodów kreskowych za pomocą aparatu w rozwiązaniu Dynamics 365 Supply Chain Management — aplikacja Magazynowanie</span><span class="sxs-lookup"><span data-stu-id="47caf-103">Scan bar codes using a camera in Dynamics 365 Supply Chain Management - Warehousing app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="47caf-104">W tym temacie opisano, jak w rozwiązaniu Dynamics 365 for Finance and Operations – aplikacja Magazynowanie skonfigurować skanowanie kodów kreskowych przy użyciu aparatu w urządzeniu przenośnym.</span><span class="sxs-lookup"><span data-stu-id="47caf-104">This topic explains how to set up Dynamics 365 for Finance and Operations – Warehousing app to scan bar codes using a camera on a mobile device.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="47caf-105">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="47caf-105">Prerequisites</span></span>
<span data-ttu-id="47caf-106">Aby można było używać tej funkcji, trzeba mieć zainstalowaną wersję 1.2.0.0 aplikacji Magazynowanie, a urządzenie musi być wyposażone w aparat.</span><span class="sxs-lookup"><span data-stu-id="47caf-106">To use this feature, you need to have version 1.2.0.0 of the Warehousing app installed, and your device must have a camera.</span></span> <span data-ttu-id="47caf-107">Gdy otworzysz aplikację po zaktualizowaniu, pojawi się monit o pozwolenie aplikacji na używanie aparatu.</span><span class="sxs-lookup"><span data-stu-id="47caf-107">When you open the app after updating, you will be prompted to allow the app to use the camera.</span></span> <span data-ttu-id="47caf-108">Jeśli urządzenie nie ma aparatu, monit nie będzie wyświetlany i nie będzie można używać aparatu jako skanera.</span><span class="sxs-lookup"><span data-stu-id="47caf-108">If your device doesn’t have a camera, no prompt will be shown, and you will not be able to use a camera as a scanner.</span></span> 

## <a name="setup"></a><span data-ttu-id="47caf-109">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="47caf-109">Setup</span></span>
<span data-ttu-id="47caf-110">W aplikacji Magazynowanie w ustawieniach wyświetlania można określić, czy aparat ma być używany do skanowania kodów kreskowych.</span><span class="sxs-lookup"><span data-stu-id="47caf-110">In the Display settings of the Warehousing application, you can select if the camera should be used for bar code scanning.</span></span> <span data-ttu-id="47caf-111">Po włączeniu opcji **Używaj aparatu jako skanera** można używać aparatu do każdego pola wejściowego, które ma ustawiony preferowany tryb wprowadzania **Skanowanie**.</span><span class="sxs-lookup"><span data-stu-id="47caf-111">If you enable **Use the camera as scanner**, you can use the camera on every input field that has the preferred input mode set to **Scanning**.</span></span> 

<span data-ttu-id="47caf-112">Aby określić, czy pole wejściowe powinno obsługiwać skanowanie, na stronie **Nazwy pól w aplikacji Magazynowanie** w ustawieniu **Preferowany tryb wprowadzania** zaznacz wartość **Skanowanie**.</span><span class="sxs-lookup"><span data-stu-id="47caf-112">To control whether an input field should be scannable, on the **Warehouse app field names** page, set **Preferred input mode** to **Scanning**.</span></span> <span data-ttu-id="47caf-113">Gdy ta opcja jest zaznaczona, aparat może służyć do skanowania w aplikacji Magazynowanie.</span><span class="sxs-lookup"><span data-stu-id="47caf-113">When this option is selected, a camera can be used for scanning in the Warehousing app.</span></span> <span data-ttu-id="47caf-114">Aby uzyskać informacje dotyczące sposobu konfigurowania nazw pól w aplikacji Magazynowanie, zobacz [Konfigurowanie nazw pól aplikacji w aplikacji Magazynowanie](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/warehousing/configure-app-field-names-priorities-warehouse).</span><span class="sxs-lookup"><span data-stu-id="47caf-114">For information about how to configure app field names in Warehousing, see [Configure app field names in Warehousing app](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/warehousing/configure-app-field-names-priorities-warehouse).</span></span>

## <a name="supported-bar-code-formats"></a><span data-ttu-id="47caf-115">Obsługiwane formaty kodów kreskowych</span><span class="sxs-lookup"><span data-stu-id="47caf-115">Supported bar code formats</span></span>
<span data-ttu-id="47caf-116">Obsługiwane są najpopularniejsze formaty kodów kreskowych, w tym Kod 128, Kod 39, Kod 93, EAN-8, EAN-13, UPC-E, UPC-A i kody QR.</span><span class="sxs-lookup"><span data-stu-id="47caf-116">The most common bar code formats are supported, including Code 128, Code 39, Code 93, EAN-8, EAN-13, UPC-E, UPC-A, and QR codes.</span></span> 

## <a name="navigation"></a><span data-ttu-id="47caf-117">Nawigacja</span><span class="sxs-lookup"><span data-stu-id="47caf-117">Navigation</span></span>
<span data-ttu-id="47caf-118">Strona Aparat będzie inicjowana z każdej strony, w której pole wejściowe ma ustawiony preferowany tryb wprowadzania Skanowanie. Na stronie Aparat poniższe opcje służą do nawigowania:</span><span class="sxs-lookup"><span data-stu-id="47caf-118">The camera page will be initiated on each page where the input field has the preferred input mode set to Scanning, when you are on the Camera page use the following options to navigate:</span></span>
- <span data-ttu-id="47caf-119">Kliknij przycisk Wstecz, aby powrócić do strony Zadanie i szczegóły.</span><span class="sxs-lookup"><span data-stu-id="47caf-119">Click the back button to go back to the Task and details page.</span></span> 
- <span data-ttu-id="47caf-120">Kliknij ikonę ołówka na stronie Zadanie i szczegóły, aby przejść do strony, gdzie można wpisać dane wejściowe ręcznie.</span><span class="sxs-lookup"><span data-stu-id="47caf-120">Click the pencil on the Task and details page to go to the page where you can type input manually.</span></span>
- <span data-ttu-id="47caf-121">Kliknij ikonę aparatu na stronie Zadanie i szczegóły, aby wrócić do strony Aparat.</span><span class="sxs-lookup"><span data-stu-id="47caf-121">Click the camera on the Task and details page to go back to the Camera page.</span></span> 

| <span data-ttu-id="47caf-122">Strona Zadanie i szczegóły</span><span class="sxs-lookup"><span data-stu-id="47caf-122">Task and details page</span></span> | <span data-ttu-id="47caf-123">Strona Aparat</span><span class="sxs-lookup"><span data-stu-id="47caf-123">Camera page</span></span> | 
| :---------------------: | :--------------------: |
| ![Strona Szczegóły przykładowego zadania skanowania kamery](./media/camera-scanning-example-task-detail-page50.png)          | ![Mniejsza strona przykładowej kamery skanowania kamery](./media/camera-scanning-example-camera-page50.png)          |

<span data-ttu-id="47caf-126">Na stronie Aparat po kliknięciu przycisku Aparat będzie on wyszarzony podczas próby zidentyfikowania kodu kreskowego.</span><span class="sxs-lookup"><span data-stu-id="47caf-126">On the camera page, when you click the Camera button, it will appear dimmed while trying to identify a bar code.</span></span> <span data-ttu-id="47caf-127">Jeśli kod kreskowy nie zostanie zidentyfikowany w ciągu 5 sekund, upłynie limit czasu procesu, a przycisk aparatu znów stanie się dostępny.</span><span class="sxs-lookup"><span data-stu-id="47caf-127">If a bar code is not identified within 5 seconds, the process will time out and the Camera button will become available again.</span></span> <span data-ttu-id="47caf-128">Wtedy będzie można ponownie spróbować zeskanować kod kreskowy.</span><span class="sxs-lookup"><span data-stu-id="47caf-128">You will then be able to try to scan a bar code again.</span></span>

<span data-ttu-id="47caf-129">Kierując aparat na kod kreskowy, w celu uzyskania najlepszego wyniku utrzymuj kod kreskowy w granicach nawiasów kwadratowych.</span><span class="sxs-lookup"><span data-stu-id="47caf-129">When you aim the camera at a bar code, keep the bar code aligned within the brackets for best result.</span></span> <span data-ttu-id="47caf-130">Jeśli kod kreskowy zostanie zeskanowany pomyślnie, rezultat zostanie przetworzony, po czym nastąpi przejście do następnego kroku.</span><span class="sxs-lookup"><span data-stu-id="47caf-130">When a bar code is scanned successfully, the result will be processed, and you will be taken to the next step.</span></span> <span data-ttu-id="47caf-131">Jeśli następny krok zawiera kolejne pole wejściowe z ustawionym preferowanym trybem wprowadzania Skanowanie, strona Aparat zostanie ponownie uruchomiona.</span><span class="sxs-lookup"><span data-stu-id="47caf-131">If the next step contains another input field with the preferred input mode set to Scanning, the camera page will start again.</span></span> <span data-ttu-id="47caf-132">Jeśli w następnym kroku nie występuje pole obsługujące skanowanie, strona Aparat nie zostanie zainicjowana.</span><span class="sxs-lookup"><span data-stu-id="47caf-132">If the next step is not a scanning field, then the camera page will not be initiated.</span></span>

