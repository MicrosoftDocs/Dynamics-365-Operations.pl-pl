---
title: Dostosuj punkty ogniskowe obrazu
description: W tym temacie opisano, jak dostosować punktu ogniskowe obrazy w kreatorze witryn Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 03/03/2020
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
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 2c9bbd51f1fe9a19198a455eedd3ba744d54a165
ms.sourcegitcommit: 567132f4e4f7a1d76dccf762068209a42c788b52
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/03/2020
ms.locfileid: "3097065"
---
# <a name="customize-image-focal-points"></a><span data-ttu-id="400c5-103">Dostosuj punkty ogniskowe obrazu</span><span class="sxs-lookup"><span data-stu-id="400c5-103">Customize image focal points</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="400c5-104">W tym temacie opisano, jak dostosować punktu ogniskowe obrazy w kreatorze witryn Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="400c5-104">This topic describes how to customize image focal points in Microsoft Dynamics 365 Commerce site builder.</span></span>

## <a name="overview"></a><span data-ttu-id="400c5-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="400c5-105">Overview</span></span>

<span data-ttu-id="400c5-106">Po przekazaniu obrazu do biblioteki multimediów kreatora witryn modułu Commerce system próbuje określić punkt ogniskowy obrazu.</span><span class="sxs-lookup"><span data-stu-id="400c5-106">When an image is uploaded to the Commerce site builder Media Library, the system attempts to determine the focal point of the image.</span></span> <span data-ttu-id="400c5-107">Jeśli na przykład na obrazie znajduje się osoba, system ustawi domyślnie punkt ogniska na twarz osoby.</span><span class="sxs-lookup"><span data-stu-id="400c5-107">For example, if the image has a person on it, the system will set the focal point to the face of the person by default.</span></span> <span data-ttu-id="400c5-108">W większości przypadków automatyczne ustawianie punktu ogniskowego działa dobrze dla wszystkich wzierników, ale czasami może być konieczne dopasowanie punktu ogniskowego, aby zapewnić, że określona część obrazu jest zawsze widoczna.</span><span class="sxs-lookup"><span data-stu-id="400c5-108">In most cases the automatically set focal point works well for all viewports, but sometimes you may want to adjust the focal point to ensure that a specific part of the image is always visible.</span></span>

### <a name="define-a-custom-focal-point-for-an-image"></a><span data-ttu-id="400c5-109">Definiowanie niestandardowego punktu ogniskowego dla obrazu</span><span class="sxs-lookup"><span data-stu-id="400c5-109">Define a custom focal point for an image</span></span>

<span data-ttu-id="400c5-110">Aby zdefiniować niestandardowy punkt ogniska dla obrazu, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="400c5-110">To define a custom focal point for an image, follow these steps.</span></span>

1. <span data-ttu-id="400c5-111">W lewym okienku nawigacyjnym w module kreatora witryn Commerce wybierz **bibliotekę multimediów**.</span><span class="sxs-lookup"><span data-stu-id="400c5-111">In the left navigation pane of Commerce site builder, select **Media Library**.</span></span>
1. <span data-ttu-id="400c5-112">W oknie głównym wybierz obraz, który chcesz zmodyfikować.</span><span class="sxs-lookup"><span data-stu-id="400c5-112">In the main window, select the image you want to modify.</span></span>
1. <span data-ttu-id="400c5-113">Na pasku poleceń wybierz opcję **Edytuj**, aby wyewidencjonować plik.</span><span class="sxs-lookup"><span data-stu-id="400c5-113">On the command bar, select **Edit** to check out the file.</span></span>
1. <span data-ttu-id="400c5-114">Wybierz obraz, by wejść w **tryb edycji**.</span><span class="sxs-lookup"><span data-stu-id="400c5-114">Select the image to enter **Edit Mode**.</span></span>
1. <span data-ttu-id="400c5-115">W obszarze **Tryb edycji** wybierz opcję **Zmień punkt ogniska**.</span><span class="sxs-lookup"><span data-stu-id="400c5-115">Under **Edit Mode**, select **Change Focal Point**.</span></span> <span data-ttu-id="400c5-116">Nad obrazem pojawi się okrągły formant punktu ogniskowego.</span><span class="sxs-lookup"><span data-stu-id="400c5-116">A circular focal point control appears over the image.</span></span>
1. <span data-ttu-id="400c5-117">Umożliwia wybranie formantu punktu ogniskowego w celu przeniesienia go nad żądanym punktem ogniskowym.</span><span class="sxs-lookup"><span data-stu-id="400c5-117">Select the focal point control to move it over the desired focal point.</span></span>
1. <span data-ttu-id="400c5-118">Po zakończeniu pracy na pasku poleceń wybierz opcję **Zapisz**, a następnie wybierz opcję **Zakończ edycję**.</span><span class="sxs-lookup"><span data-stu-id="400c5-118">When you're done, on the command bar select **Save**, and then select **Finish editing**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="400c5-119">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="400c5-119">Additional resources</span></span>

[<span data-ttu-id="400c5-120">Omówienie zarządzania cyfrowymi składnikami majątku</span><span class="sxs-lookup"><span data-stu-id="400c5-120">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="400c5-121">Przekaż obrazy</span><span class="sxs-lookup"><span data-stu-id="400c5-121">Upload images</span></span>](dam-upload-images.md)

[<span data-ttu-id="400c5-122">Przekaż plik wideo</span><span class="sxs-lookup"><span data-stu-id="400c5-122">Upload video</span></span>](dam-upload-video.md)

[<span data-ttu-id="400c5-123">Przekaż pliki</span><span class="sxs-lookup"><span data-stu-id="400c5-123">Upload files</span></span>](dam-upload-files.md)

[<span data-ttu-id="400c5-124">Przytnij obrazy</span><span class="sxs-lookup"><span data-stu-id="400c5-124">Crop images</span></span>](dam-crop-images.md)
