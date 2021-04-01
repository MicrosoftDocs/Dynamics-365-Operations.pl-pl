---
title: Gwarancje na składniki majątku i typy składników majątku
description: W tym temacie wyjaśniono, jak konfigurować gwarancje składników majątku i typów składników majatku w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 08/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 78ac93b1e681fca7d7eefd921f282a8496aa9d0a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5245330"
---
# <a name="warranties-on-assets-and-asset-types"></a><span data-ttu-id="aeee1-103">Gwarancje na składniki majątku i typy składników majątku</span><span class="sxs-lookup"><span data-stu-id="aeee1-103">Warranties on assets and asset types</span></span>

[!include [banner](../../includes/banner.md)]

 


<span data-ttu-id="aeee1-104">W tym temacie wyjaśniono, jak konfigurować gwarancje składników majątku i typów składników majatku w module Zarządzanie składnikami majątku.</span><span class="sxs-lookup"><span data-stu-id="aeee1-104">This topic explains how to set up warranties on assets and asset types in Asset Management.</span></span>

## <a name="set-up-a-warranty-on-an-asset-type"></a><span data-ttu-id="aeee1-105">Konfiguruj gwarancję na typy składników majątku.</span><span class="sxs-lookup"><span data-stu-id="aeee1-105">Set up a warranty on an asset type</span></span>

1. <span data-ttu-id="aeee1-106">Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Typy składników majątku** \> **Typy składników majątku**.</span><span class="sxs-lookup"><span data-stu-id="aeee1-106">Select **Asset management** \> **Setup** \> **Asset types** \> **Asset types**.</span></span>
2. <span data-ttu-id="aeee1-107">W lewym okienku wybierz typ składnika majątku, do którego ma zostać dołączona umowa gwarancyjna dostawcy, a następnie wybierz opcję **Ustawienia domyślne typu składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="aeee1-107">In the left pane, select the asset type to attach a vendor warranty agreement to, and then select **Asset type defaults**.</span></span>
3. <span data-ttu-id="aeee1-108">Na skróconej karcie **Ogólne** w polu **Gwarancja dostawcy** wybierz umowę.</span><span class="sxs-lookup"><span data-stu-id="aeee1-108">On the **General** FastTab, in the **Vendor warranty** field, select the agreement.</span></span>

## <a name="set-up-a-warranty-on-an-asset"></a><span data-ttu-id="aeee1-109">Konfiguruj gwarancję na składnik majątku.</span><span class="sxs-lookup"><span data-stu-id="aeee1-109">Set up a warranty on an asset</span></span>

1. <span data-ttu-id="aeee1-110">Wybierz kolejno **Zarządzanie składnikami majątku** \> **Wspólne** \> **Składniki majątku** \> **Wszystkie składniki majątku**.</span><span class="sxs-lookup"><span data-stu-id="aeee1-110">Select **Asset management** \> **Common** \> **Assets** \> **All assets**.</span></span>
2. <span data-ttu-id="aeee1-111">Zaznacz składnik i kliknij przycisk **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="aeee1-111">Select the asset, and then select **Edit**.</span></span>
3. <span data-ttu-id="aeee1-112">Na skróconej karcie **Dostawcy** w sekcji **Gwarancja dostawcy** w polu **Gwarancja** wybierz umowę gwarancyjną.</span><span class="sxs-lookup"><span data-stu-id="aeee1-112">On the **Vendor** FastTab, in the **Vendor warranty** section, in the **Warranty** field, select the warranty agreement.</span></span>
4. <span data-ttu-id="aeee1-113">W polach **Rozpoczęcie gwarancji** i **Zakończenie gwarancji** wybierz datę początkową i końcową.</span><span class="sxs-lookup"><span data-stu-id="aeee1-113">In the **Warranty start** and **Warranty end** fields, select the start and end dates.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="aeee1-114">Jeśli w polu **Rozpoczęcie gwarancji** zlecenia pracy została wybrana data, gwarancja staje się ważna dla zlecenia dotyczącego tego dnia.</span><span class="sxs-lookup"><span data-stu-id="aeee1-114">If a date is selected in the **Warranty start** field on a work order, the warranty becomes valid for the work order on that date.</span></span> <span data-ttu-id="aeee1-115">Podczas tworzenia zlecenia pracy pole **Rozpoczęcie gwarancji** jest automatycznie ustawiane na datę utworzenia.</span><span class="sxs-lookup"><span data-stu-id="aeee1-115">When you create a work order, the **Warranty start** field is automatically set to the date of creation.</span></span> <span data-ttu-id="aeee1-116">Można jednak zmienić datę w taki sposób, aby odpowiadała, na przykład, dacie początkowej umowy gwarancyjnej.</span><span class="sxs-lookup"><span data-stu-id="aeee1-116">However, you can change the date so that it corresponds to, for example, the start date of a warranty agreement.</span></span>
    >
    > ![Strona Zlecenie pracy](media/02-warranty.png)

> [!NOTE]
> <span data-ttu-id="aeee1-118">W przypadku tworzenia zlecenia pracy dla składnika majątku objętego gwarancją dostawcy, jeśli zlecenie pracy ma oczekiwaną datę rozpoczęcia w okresie gwarancji, zostanie wyświetlone powiadomienie dotyczące umowy gwarancyjnej.</span><span class="sxs-lookup"><span data-stu-id="aeee1-118">When you create a work order for an asset that is covered by a vendor warranty, if the work order has an expected start date during the warranty period, you receive a notification about the warranty agreement.</span></span> <span data-ttu-id="aeee1-119">W razie konieczności można anulować zlecenie pracy.</span><span class="sxs-lookup"><span data-stu-id="aeee1-119">You can then cancel the work order, as you require.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]