---
title: Potwierdzenie produktu na potrzeby pobierania dla grupy
description: W tym temacie opisano, jak skonfigurować weryfikowanie towarów w połączeniu z pobieraniem dla grupy.
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFAutoConfirm
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 530129ba6877c68475217d3a035775e25930cd07
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808877"
---
# <a name="product-confirmation-for-cluster-picking"></a><span data-ttu-id="3f260-103">Potwierdzenie produktu na potrzeby pobierania dla grupy</span><span class="sxs-lookup"><span data-stu-id="3f260-103">Product confirmation for cluster picking</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3f260-104">Funkcjonalność pobierania dla grupy umożliwia pobieranie towarów równocześnie dla kilku zamówień.</span><span class="sxs-lookup"><span data-stu-id="3f260-104">Cluster picking allows you to pick items for several orders at the same time.</span></span> <span data-ttu-id="3f260-105">W przypadku stosowania pobierania dla grupy bardzo ważne jest potwierdzanie towarów dodawanych do grup.</span><span class="sxs-lookup"><span data-stu-id="3f260-105">When cluster picking is applied, item confirmation is crucial to verify the items that are added to clusters.</span></span> <span data-ttu-id="3f260-106">Weryfikowanie może się odbywać w trakcie procesu pobierania dla grup.</span><span class="sxs-lookup"><span data-stu-id="3f260-106">You can verify items in cluster picking during the cluster picking process.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="3f260-107">Zastosowanie</span><span class="sxs-lookup"><span data-stu-id="3f260-107">Where it applies</span></span>

<span data-ttu-id="3f260-108">Weryfikacja towarów w pobieraniu dla grupy działa tak samo, jak w zwykłych procesach pobierania.</span><span class="sxs-lookup"><span data-stu-id="3f260-108">Item verification for cluster picking works the same way as when you verify items in a non-cluster picking processes.</span></span> <span data-ttu-id="3f260-109">Konfiguracja zależy od ustawień kodów kreskowych produktów.</span><span class="sxs-lookup"><span data-stu-id="3f260-109">The setup is based on the product bar code setup.</span></span>

## <a name="set-up-item-verification-with-cluster-picking"></a><span data-ttu-id="3f260-110">Konfigurowanie weryfikowania towarów w trakcie pobierania dla grupy</span><span class="sxs-lookup"><span data-stu-id="3f260-110">Set up item verification with cluster picking</span></span>

1. <span data-ttu-id="3f260-111">Na urządzeniu przenośnym w menu otwórz formularz ustawień potwierdzenia pracy: **Zarządzanie magazynem** > **Zarządzanie magazynem** > **Ustawienia** > **Urządzenie przenośne** > **Elementy menu urządzenia przenośnego**.</span><span class="sxs-lookup"><span data-stu-id="3f260-111">On a mobile device menu item, open the setup form for work confirmation: **Warehouse management** > **Warehouse management** > **Setup** > **Mobile device** > **Mobile device menu items**.</span></span>
1. <span data-ttu-id="3f260-112">Na urządzeniu przenośnym w menu otwórz pozycję **Konfiguracja potwierdzenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="3f260-112">From the mobile device menu item, open **Work confirmation setup**.</span></span>

|        <span data-ttu-id="3f260-113">Opcja</span><span class="sxs-lookup"><span data-stu-id="3f260-113">Option</span></span>        |                                    <span data-ttu-id="3f260-114">opis</span><span class="sxs-lookup"><span data-stu-id="3f260-114">Description</span></span>                                    |
|----------------------|-----------------------------------------------------------------------------------|
| <span data-ttu-id="3f260-115">Potwierdzenie produktu</span><span class="sxs-lookup"><span data-stu-id="3f260-115">Product confirmation</span></span> | <span data-ttu-id="3f260-116">Umożliwia weryfikowanie każdego artykułu w zapasach z urządzenia przenośnego podczas skanowania.</span><span class="sxs-lookup"><span data-stu-id="3f260-116">Allows you to verify each piece of inventory from the mobile device when scanned.</span></span> |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]