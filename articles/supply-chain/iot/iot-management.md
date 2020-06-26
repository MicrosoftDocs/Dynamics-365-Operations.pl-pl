---
title: Monitorowanie analizy Internetu rzeczy (IoT) i zarządzanie nią
description: W tym temacie wyjaśniono, jak monitorować analizę Internetu rzeczy (IoT) i zarządzać nią.
author: robinarh
manager: AnnBe
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: ''
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 97a87b78a0178424f00e464262bb7f69e8a5b4a0
ms.sourcegitcommit: 261b70ea358b2c231e20f320ed8bd6adc1e7d715
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/19/2020
ms.locfileid: "3386548"
---
# <a name="monitor-and-manage-iot-intelligence"></a><span data-ttu-id="64910-103">Monitorowanie analizy Internetu rzeczy (IoT) i zarządzanie nią</span><span class="sxs-lookup"><span data-stu-id="64910-103">Monitor and manage IoT Intelligence</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="64910-104">W tym temacie wyjaśniono, jak monitorować analizę Internetu rzeczy (IoT) i zarządzać nią.</span><span class="sxs-lookup"><span data-stu-id="64910-104">This topic explains how to monitor and manage IoT Intelligence.</span></span>

## <a name="monitor-scenarios-in-microsoft-dynamics-365-supply-chain-management"></a><a id="monitor-scenarios"></a><span data-ttu-id="64910-105">Monitorowanie scenariuszy w aplikacji Microsoft Dynamics 365 Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="64910-105">Monitor scenarios in Microsoft Dynamics 365 Supply Chain Management</span></span>

<span data-ttu-id="64910-106">Przetwarzanie analizy Internetu (IoT) można monitorować w kilku miejscach:</span><span class="sxs-lookup"><span data-stu-id="64910-106">You can monitor IoT Intelligence processing from several places:</span></span>

+ <span data-ttu-id="64910-107">**Moduły \> Kontrola produkcji \> Zapytania i raporty \> Analiza Internetu rzeczy (IoT) \> Powiadomienia** — wyświetla listę nierozwiązanych powiadomień.</span><span class="sxs-lookup"><span data-stu-id="64910-107">**Modules \> Production control \> Inquiries and reports \> IoT Intelligence \> Notifications** – View the list of unresolved notifications.</span></span>
+ <span data-ttu-id="64910-108">**Moduły \> Kontrola produkcji \> Zapytania i raporty \> Analiza Internetu rzeczy (IoT) \> Powiadomienia zamknięte** — wyświetla listę powiadomień rozwiązanych lub odrzuconych.</span><span class="sxs-lookup"><span data-stu-id="64910-108">**Modules \> Production control \> Inquiries and reports \> IoT Intelligence \> Closed notifications** – View the list of notifications that have been resolved or dismissed.</span></span>
+ <span data-ttu-id="64910-109">**Moduły \> Kontrola produkcji \> Zapytania i raporty \> Analiza Internetu rzeczy (IoT) \> Klucze metryk** — wyświetla klucze metryk dla wykresów szeregu czasowego **Stan zasobu**.</span><span class="sxs-lookup"><span data-stu-id="64910-109">**Modules \> Production control \> Inquiries and reports \> IoT Intelligence \> Metric keys** – View the metric keys for the **Resource Status** times series charts.</span></span>
+ <span data-ttu-id="64910-110">**Moduły \> Kontrola produkcji \> Wykonywanie produkcji \> Stan zasobu** — śledzi określone metryki przy użyciu okna dialogowego **Konfigurowanie**.</span><span class="sxs-lookup"><span data-stu-id="64910-110">**Modules \> Production control \> Manufacturing execution \> Resource status** – Track specific metrics by using the **Configure** dialog box.</span></span> <span data-ttu-id="64910-111">Jeśli scenariusz wykryje wyjątek, w powiadomieniu zostaną wyświetlone szczegóły wyjątku.</span><span class="sxs-lookup"><span data-stu-id="64910-111">If a scenario detects an exception, a notification shows the details of the exception.</span></span>
+ <span data-ttu-id="64910-112">**Obszary robocze \> Zarządzanie halą produkcyjną \> Powiadomienia** — wyświetla listę nierozwiązanych powiadomień.</span><span class="sxs-lookup"><span data-stu-id="64910-112">**Workspaces \> Production floor management \> Notifications** – View the list of unresolved notifications.</span></span>

## <a name="modify-a-running-iot-intelligence-scenario"></a><span data-ttu-id="64910-113">Modyfikowanie działającego scenariusza analizy Internetu rzeczy (IoT)</span><span class="sxs-lookup"><span data-stu-id="64910-113">Modify a running IoT Intelligence scenario</span></span>

<span data-ttu-id="64910-114">Po uruchomieniu scenariusza można wprowadzić następujące zmiany:</span><span class="sxs-lookup"><span data-stu-id="64910-114">When a scenario is running, you can make these changes:</span></span>

+ <span data-ttu-id="64910-115">Dodanie nowych definicji schematów czujników.</span><span class="sxs-lookup"><span data-stu-id="64910-115">Add new sensor schema definitions.</span></span>
+ <span data-ttu-id="64910-116">Wybranie nowych wartości danych sygnału.</span><span class="sxs-lookup"><span data-stu-id="64910-116">Select new signal data values.</span></span>
+ <span data-ttu-id="64910-117">Anulowanie wyboru istniejących wartości danych sygnału.</span><span class="sxs-lookup"><span data-stu-id="64910-117">Cancel the selection of existing signal data values.</span></span>
+ <span data-ttu-id="64910-118">Dodanie i zmapowanie nowych wartości danych sygnału.</span><span class="sxs-lookup"><span data-stu-id="64910-118">Add and map new signal data values.</span></span>
+ <span data-ttu-id="64910-119">Zaktualizowanie wartości progowych.</span><span class="sxs-lookup"><span data-stu-id="64910-119">Update threshold values.</span></span>

<span data-ttu-id="64910-120">Po uruchomieniu scenariusza nie można wprowadzać następujących zmian:</span><span class="sxs-lookup"><span data-stu-id="64910-120">When a scenario is running, these changes are prohibited:</span></span>

+ <span data-ttu-id="64910-121">Usunięcie lub zmodyfikowanie definicji schematu, które są obecnie używane przez włączony scenariusz.</span><span class="sxs-lookup"><span data-stu-id="64910-121">Delete or modify any schema definitions that are currently consumed by an enabled scenario.</span></span>
+ <span data-ttu-id="64910-122">Zmiana wybranych ścieżek schematu dla włączonego scenariusza.</span><span class="sxs-lookup"><span data-stu-id="64910-122">Change the enabled scenario's selected schema paths.</span></span>

## <a name="simulation-options"></a><span data-ttu-id="64910-123">Opcje symulacji</span><span class="sxs-lookup"><span data-stu-id="64910-123">Simulation options</span></span>

<span data-ttu-id="64910-124">Istnieje możliwość symulowania sygnałów urządzeń w fabryce.</span><span class="sxs-lookup"><span data-stu-id="64910-124">You can simulate factory machine signals.</span></span> <span data-ttu-id="64910-125">Aby uzyskać więcej informacji, zapoznaj się z tymi tematami.</span><span class="sxs-lookup"><span data-stu-id="64910-125">For more information, see these topics:</span></span>

+ [<span data-ttu-id="64910-126">Łączenie zestawu IoT DevKit AZ3166 z usługą Azure IoT Hub</span><span class="sxs-lookup"><span data-stu-id="64910-126">Connect IoT DevKit AZ3166 to Azure IoT Hub</span></span>](https://docs.microsoft.com/azure/iot-hub/iot-hub-arduino-iot-devkit-az3166-get-started)
+ [<span data-ttu-id="64910-127">Łączenie symulatora online Raspberry Pi z Azure IoT Hub (Node.js)</span><span class="sxs-lookup"><span data-stu-id="64910-127">Connect Raspberry Pi online simulator to Azure IoT Hub (Node.js)</span></span>](https://docs.microsoft.com/azure/iot-hub/iot-hub-raspberry-pi-web-simulator-get-started)
+ [<span data-ttu-id="64910-128">Omówienie akceleratora rozwiązania do symulacji urządzenia</span><span class="sxs-lookup"><span data-stu-id="64910-128">Device Simulation solution accelerator overview</span></span>](https://docs.microsoft.com/azure/iot-accelerators/iot-accelerators-device-simulation-overview)