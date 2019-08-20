---
title: Przychodzące i wychodzące składniki majątku
description: W tym temacie opisano sposób rejestrowania przychodzących i wychodzących składników majątku w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 62998da7f541379296d5ac325ae29f24a42f9b7c
ms.sourcegitcommit: 871b76f8808a48d282f151144829323258ffc912
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/02/2019
ms.locfileid: "1847558"
---
# <a name="inbound-and-outbound-assets"></a><span data-ttu-id="e1b94-103">Przychodzące i wychodzące składniki majątku</span><span class="sxs-lookup"><span data-stu-id="e1b94-103">Inbound and outbound assets</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="e1b94-104">Jeśli firma wykonuje zadania naprawy lub konserwacji na składnikach majątku, które są odbierane z innych lokalizacji lub od innych klientów, zarządzanie składnikami majątku można śledzić zarówno w odniesieniu do przychodzących składników majątku w drodze do firmy, jak i składników wychodzących, które są zwracane.</span><span class="sxs-lookup"><span data-stu-id="e1b94-104">If your company does repair jobs or maintenance jobs on assets that are received from other locations or customers, Asset Management can track both inbound assets that are on their way to your company and outbound assets that are being returned.</span></span>

> [!NOTE]
> <span data-ttu-id="e1b94-105">Jeśli chcesz używać stanów cyklu życia przychodzącego i wychodzącego do zarządzania składnikami majątku, które przychodzą i są zwracane, musisz skonfigurować stany cyklu życia żądania konserwacji oraz modele cyklu życia do obsługi tych czynności.</span><span class="sxs-lookup"><span data-stu-id="e1b94-105">If you want to use inbound and outbound lifecycle states to manage assets that are coming in and being returned, you must set up maintenance request lifecycle states and lifecycle models to support these actions.</span></span> <span data-ttu-id="e1b94-106">Aby uzyskać więcej informacji, zobacz temat [Ustawienia żądań konserwacji](../setup-for-maintenance-requests/requests.md).</span><span class="sxs-lookup"><span data-stu-id="e1b94-106">For more information, see [Setup for maintenance requests](../setup-for-maintenance-requests/requests.md).</span></span>

<span data-ttu-id="e1b94-107">Konfiguracja modułu Zarządzanie składnikami majątku określa, czy można pracować z przychodzącymi i wychodzącymi składnikami majątku.</span><span class="sxs-lookup"><span data-stu-id="e1b94-107">The setup of Asset Management determines whether you can work with inbound and outbound assets.</span></span>

## <a name="register-assets-as-inbound"></a><span data-ttu-id="e1b94-108">Rejestrowanie składników majątku jako przychodzących</span><span class="sxs-lookup"><span data-stu-id="e1b94-108">Register assets as inbound</span></span>

1. <span data-ttu-id="e1b94-109">Wybierz **Zarządzanie składnikami majątku** \> **Wspólne** \> **Żądania konserwacji** \> **Aktywne żądania konserwacji**.</span><span class="sxs-lookup"><span data-stu-id="e1b94-109">Select **Asset management** \> **Common** \> **Maintenance requests** \> **Active maintenance requests**.</span></span>
2. <span data-ttu-id="e1b94-110">Wybierz żądanie konserwacji.</span><span class="sxs-lookup"><span data-stu-id="e1b94-110">Select the maintenance request.</span></span>
3. <span data-ttu-id="e1b94-111">Wybierz **Aktualizuj stan żądania konserwacji**.</span><span class="sxs-lookup"><span data-stu-id="e1b94-111">Select **Update maintenance request state**.</span></span>
4. <span data-ttu-id="e1b94-112">Wybierz **Przychodzące** (lub inny stan cyklu życia utworzony dla przychodzących składników majątku), a następnie wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1b94-112">Select **Inbound** (or another lifecycle state that you've created for inbound assets), and then select **OK**.</span></span>

![Rysunek 1](media/07-manage-maintenance-requests.png)

## <a name="register-inbound-assets-as-received"></a><span data-ttu-id="e1b94-114">Rejestrowanie przychodzących składników majątku jako odebranych</span><span class="sxs-lookup"><span data-stu-id="e1b94-114">Register inbound assets as received</span></span>

1. <span data-ttu-id="e1b94-115">Wybierz **Zarządzanie składnikami majątku** \> **Wspólne** \> **Przychodzące/wychodzące** \> **Zasoby przychodzące**.</span><span class="sxs-lookup"><span data-stu-id="e1b94-115">Select **Asset management** \> **Common** \> **Inbound/outbound** \> **Inbound assets**.</span></span>
2. <span data-ttu-id="e1b94-116">Wybierz składnik majątku lub żądanie konserwacji.</span><span class="sxs-lookup"><span data-stu-id="e1b94-116">Select the asset or maintenance request.</span></span>
3. <span data-ttu-id="e1b94-117">Wybierz opcję **Odbierz składniki majątku**.</span><span class="sxs-lookup"><span data-stu-id="e1b94-117">Select **Receive assets**.</span></span>
4. <span data-ttu-id="e1b94-118">W polu **Odebrane** wpisz datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="e1b94-118">In the **Received** field, enter the date and time.</span></span> <span data-ttu-id="e1b94-119">Następnie wybierz opcję **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1b94-119">Then select **OK**.</span></span> <span data-ttu-id="e1b94-120">Rekord zostanie usunięty ze strony listy **Przychodzące składniki majątku**.</span><span class="sxs-lookup"><span data-stu-id="e1b94-120">The record is removed from the **Inbound assets** list page.</span></span>

![Rysunek 2](media/08-manage-maintenance-requests.png)

## <a name="register-assets-as-outbound"></a><span data-ttu-id="e1b94-122">Rejestrowanie zasobów jako wychodzących</span><span class="sxs-lookup"><span data-stu-id="e1b94-122">Register assets as outbound</span></span>

<span data-ttu-id="e1b94-123">Po ukończeniu zadania konserwacji lub naprawy można zarejestrować zasób jako zwrócony.</span><span class="sxs-lookup"><span data-stu-id="e1b94-123">When you've completed the maintenance or repair job, you can register the asset as returned.</span></span>

1. <span data-ttu-id="e1b94-124">Wybierz **Zarządzanie składnikami majątku** \> **Wspólne** \> **Żądania konserwacji** \> **Aktywne żądania konserwacji**.</span><span class="sxs-lookup"><span data-stu-id="e1b94-124">Select **Asset management** \> **Common** \> **Maintenance requests** \> **Active maintenance requests**.</span></span>
2. <span data-ttu-id="e1b94-125">Wybierz żądanie konserwacji.</span><span class="sxs-lookup"><span data-stu-id="e1b94-125">Select the maintenance request.</span></span>
3. <span data-ttu-id="e1b94-126">Wybierz **Aktualizuj stan żądania konserwacji**.</span><span class="sxs-lookup"><span data-stu-id="e1b94-126">Select **Update maintenance request state**.</span></span>
4. <span data-ttu-id="e1b94-127">Wybierz **Wychodzące** (lub inny stan cyklu życia utworzony dla zasobów wychodzących), a następnie wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1b94-127">Select **Outbound** (or another lifecycle state that you've created for outbound assets), and then select **OK**.</span></span>

## <a name="register-outbound-assets-as-delivered"></a><span data-ttu-id="e1b94-128">Rejestrowanie zasobów wychodzących jako dostarczonych</span><span class="sxs-lookup"><span data-stu-id="e1b94-128">Register outbound assets as delivered</span></span>

1. <span data-ttu-id="e1b94-129">Wybierz **Zarządzanie składnikami majątku** \> **Wspólne** \> **Przychodzące/wychodzące** \> **Zasoby wychodzące**.</span><span class="sxs-lookup"><span data-stu-id="e1b94-129">Select **Asset management** \> **Common** \> **Inbound/outbound** \> **Outbound assets**.</span></span>
2. <span data-ttu-id="e1b94-130">Wybierz składnik majątku lub żądanie konserwacji.</span><span class="sxs-lookup"><span data-stu-id="e1b94-130">Select the asset or maintenance request.</span></span>
3. <span data-ttu-id="e1b94-131">Wybierz opcję **Dostarcz zasoby**.</span><span class="sxs-lookup"><span data-stu-id="e1b94-131">Select **Deliver assets**.</span></span>
4. <span data-ttu-id="e1b94-132">W polu **Dostarczone** wpisz datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="e1b94-132">In the **Delivered** field, enter the date and time.</span></span> <span data-ttu-id="e1b94-133">Następnie wybierz opcję **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1b94-133">Then select **OK**.</span></span> <span data-ttu-id="e1b94-134">Rekord zostanie usunięty ze strony listy **Zasoby wychodzące**.</span><span class="sxs-lookup"><span data-stu-id="e1b94-134">The record is removed from the **Outbound assets** list page.</span></span>
