---
title: Kody przyczyn zleceń serwisowych
description: Kody przyczyn ułatwiają wyjaśnienie stanu zlecenia serwisowego, gdy aktualizowany jest jego etap.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAStageTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9548d3a29c787b49713499519e1a02b5d218ac1c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836189"
---
# <a name="reason-codes-for-service-orders"></a><span data-ttu-id="a6e99-103">Kody przyczyn zleceń serwisowych</span><span class="sxs-lookup"><span data-stu-id="a6e99-103">Reason codes for service orders</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="a6e99-104">Można używać kodów przyczyn do wyjaśniania stanu zlecenia serwisowego, gdy aktualizowany jest jego etap.</span><span class="sxs-lookup"><span data-stu-id="a6e99-104">You can use reason codes to help explain the status of a service order when the stage of a service order is updated.</span></span> <span data-ttu-id="a6e99-105">Na przykład w przypadku anulowania zlecenia serwisowego, można wybrać kod przyczyny anulowania.</span><span class="sxs-lookup"><span data-stu-id="a6e99-105">For example, if you cancel a service order, you can select a reason code for the cancellation.</span></span>

<span data-ttu-id="a6e99-106">Aby przeglądać informacje o kodach przyczyn używanych do śledzenia postępu zleceń serwisowych, należy uruchomić raport postępu zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="a6e99-106">To view information about reason codes that are used to track the progress of service orders, run the Service order progress report.</span></span> <span data-ttu-id="a6e99-107">W raporcie tym są wyświetlane wszystkie zlecenia serwisowe, niezależnie od ich etapu, oraz kody przyczyn określone w momencie aktualizacji etapu zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="a6e99-107">This report lists all service orders, regardless of their stage, and the reason codes that are specified when a service order stage is updated.</span></span>

## <a name="turn-reason-codes-on-or-off"></a><span data-ttu-id="a6e99-108">Włączanie lub wyłączanie kodów przyczyn</span><span class="sxs-lookup"><span data-stu-id="a6e99-108">Turn reason codes on or off</span></span>

<span data-ttu-id="a6e99-109">Kody przyczyn są opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="a6e99-109">Reason codes are optional.</span></span> <span data-ttu-id="a6e99-110">Użytkownik może zdecydować, czy potrzebny jest kod przyczyny podczas aktualizowania zlecenia serwisowego w związku z rozpoczęciem określonego etapu.</span><span class="sxs-lookup"><span data-stu-id="a6e99-110">You can decide whether to require a reason code when you update a service order to a specific service stage.</span></span>

1.  <span data-ttu-id="a6e99-111">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Ustawienia** \> **Zlecenia serwisowe** \> **Etapy serwisu**.</span><span class="sxs-lookup"><span data-stu-id="a6e99-111">Click **Service management** \> **Setup** \> **Service orders** \> **Service stages**.</span></span>

2.  <span data-ttu-id="a6e99-112">W formularzu **Etapy serwisu** wybierz etap serwisu, a następnie zaznacz pole wyboru **Przyczyna** dla etapu serwisu.</span><span class="sxs-lookup"><span data-stu-id="a6e99-112">In the **Service stages** form, select a service stage, and then select the **Reason** check box for the service stage.</span></span>

3.  <span data-ttu-id="a6e99-113">Zamknij formularz, aby zapisać zmiany.</span><span class="sxs-lookup"><span data-stu-id="a6e99-113">Close the form to save your changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="a6e99-114">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="a6e99-114">See also</span></span>

[<span data-ttu-id="a6e99-115">Ustawianie etapów zlecenia serwisowego</span><span class="sxs-lookup"><span data-stu-id="a6e99-115">Set up service order stages</span></span>](set-up-service-order-stages.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]