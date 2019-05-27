---
title: Rozpoczynanie i zatrzymywanie rejestrowania czasu dla zlecenia serwisowego
description: Można rozpocząć i zatrzymać rejestrowania czasu dla zlecenia serwisowego.
author: ShylaThompson
manager: AnnBe
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 16d9f48ed38a5033fab94d45821f0ed6f7f1f011
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1558395"
---
# <a name="start-and-stop-time-recording-on-a-service-order"></a><span data-ttu-id="f06b4-103">Rozpoczynanie i zatrzymywanie rejestrowania czasu dla zlecenia serwisowego</span><span class="sxs-lookup"><span data-stu-id="f06b4-103">Start and stop time recording on a service order</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="f06b4-104">Niniejsza procedura umożliwia uruchamianie i zatrzymywanie rejestrowania czasu dla zlecenia serwisowego, dla którego jest zdefiniowana umowa dotycząca poziomu usług.</span><span class="sxs-lookup"><span data-stu-id="f06b4-104">Use this procedure to start and stop time recording for a service order for which a service level agreement is defined.</span></span>

## <a name="start-time-recording"></a><span data-ttu-id="f06b4-105">Rozpoczynanie rejestrowania czasu</span><span class="sxs-lookup"><span data-stu-id="f06b4-105">Start time recording</span></span>

1.  <span data-ttu-id="f06b4-106">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Zlecenia serwisowe** \> **Zlecenia serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="f06b4-106">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="f06b4-107">Kliknij kartę **Zlecenie serwisowe**. W **okienku akcji** w grupie **Umowa dotycząca poziomu usług** kliknij przycisk **Rozpocznij**.</span><span class="sxs-lookup"><span data-stu-id="f06b4-107">Click the **Service order** tab. On the **Action Pane**, in the **Service level agreement** group, click **Start**.</span></span>

3.  <span data-ttu-id="f06b4-108">Wprowadź datę i godzinę uruchomienia rejestrowania czasu.</span><span class="sxs-lookup"><span data-stu-id="f06b4-108">Enter the date and time that the time recording should be started.</span></span>

## <a name="stop-time-recording"></a><span data-ttu-id="f06b4-109">Zatrzymaj rejestrację czasu</span><span class="sxs-lookup"><span data-stu-id="f06b4-109">Stop time recording</span></span>

1.  <span data-ttu-id="f06b4-110">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Zlecenia serwisowe** \> **Zlecenia serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="f06b4-110">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="f06b4-111">Kliknij kartę **Zlecenie serwisowe**. W **okienku akcji** w grupie **Umowa dotycząca poziomu usług** kliknij przycisk **Zatrzymaj**.</span><span class="sxs-lookup"><span data-stu-id="f06b4-111">Click the **Service order** tab. On the **Action Pane**, in the **Service level agreement** group, click **Stop**.</span></span>

3.  <span data-ttu-id="f06b4-112">Wprowadź datę i godzinę zatrzymania rejestrowania czasu.</span><span class="sxs-lookup"><span data-stu-id="f06b4-112">Enter the date and time that the time recording should be stopped.</span></span>

4.  <span data-ttu-id="f06b4-113">Wybierz opcję **Dodaj do przyczyny unieważnienia** i wybierz kod przyczyny z listy **Kod przyczyny etapów**, aby podać przyczynę zatrzymania rejestrowania czasu.</span><span class="sxs-lookup"><span data-stu-id="f06b4-113">Select **Add a revocation reason**, and select a reason code in the **Stage reason code** list to provide a reason for stopping the time recording.</span></span>


> [!NOTE]
> <P><span data-ttu-id="f06b4-114">Jeśli w formularzu <STRONG>Parametry modułu Zarządzanie serwisem</STRONG> jest zaznaczona opcja <STRONG>Kod przyczyny dotyczący przekroczenia czasu</STRONG>, należy podać kod przyczyny, zanim będzie można zatrzymać rejestrowanie czasu.</span><span class="sxs-lookup"><span data-stu-id="f06b4-114">If <STRONG>Reason code on exceeding time</STRONG> is selected in the <STRONG>Service management parameters</STRONG> form, you must provide a reason code before you can stop the time recording.</span></span></P>



## <a name="see-also"></a><span data-ttu-id="f06b4-115">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="f06b4-115">See also</span></span>

<span data-ttu-id="f06b4-116">[Rozpocznij rejestrowanie czasu dla umowy SLA (formularz)](https://technet.microsoft.com/en-us/library/hh242297\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="f06b4-116">[Start SLA time recording (form)](https://technet.microsoft.com/en-us/library/hh242297\(v=ax.60\))</span></span>

<span data-ttu-id="f06b4-117">[Zatrzymaj rejestrowanie czasu dla umowy SLA (formularz)](https://technet.microsoft.com/en-us/library/hh242241\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="f06b4-117">[Stop SLA time recording (form)](https://technet.microsoft.com/en-us/library/hh242241\(v=ax.60\))</span></span>

  


