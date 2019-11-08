---
title: Zgłaszanie wyrobów gotowych do lokalizacji niekontrolowanej przez Urządzenie karty zadań
description: Ten temat decribes proces kończenia wyrobów gotowych w zleceniu produkcyjnym do zapasów, gdy określa lokalizację.
author: johanhoffmann
manager: AnnBe
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistration, ProdJournalTransJob, ProdJournalTransRoute, ProdParmReportFinished
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19351
ms.assetid: bcc9e242-b4b8-4144-b14d-c3c106fb40ec
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2019-09-06
ms.dyn365.ops.version: AX 10.0.6
ms.openlocfilehash: cb809e596fd6bf3030bcee460838798435512b95
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2019
ms.locfileid: "2572136"
---
[!include [banner](../includes/banner.md)]

# <a name="report-as-finished-to-a-license-plate-controlled-location-from-the-job-card-device"></a><span data-ttu-id="7ac64-103">Zgłaszanie wyrobów gotowych do lokalizacji niekontrolowanej przez Urządzenie karty zadań</span><span class="sxs-lookup"><span data-stu-id="7ac64-103">Report as finished to a license plate controlled location from the Job card device</span></span> 

<span data-ttu-id="7ac64-104">Proces zwany Gotowym zgłoszeniem wyrobów gotowych w zleceniu produkcyjnym do magazynu.</span><span class="sxs-lookup"><span data-stu-id="7ac64-104">The process called Reporting as finished completes finished products on a production order to the inventory.</span></span> <span data-ttu-id="7ac64-105">Jeśli produkt gotowy jest włączony dla zaawansowanych procesów magazynowych, produkt jest zgłaszany jako gotowy do lokalizacji zwanej lokalizacją wyjściową produkcji.</span><span class="sxs-lookup"><span data-stu-id="7ac64-105">If the finished product is enabled for the advanced warehouse processes, the product is reported as finished to a location called the production output location.</span></span> <span data-ttu-id="7ac64-106">Aby uzyskać informacje dotyczące konfigurowania lokalizacji produkcji, przejrzyj [Lokalizację wyjściową produkcji](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location).</span><span class="sxs-lookup"><span data-stu-id="7ac64-106">For information about setting up the production output location, see [Production output location](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location).</span></span>

<span data-ttu-id="7ac64-107">Musisz wybrać istniejący numer identyfikacyjny do wykonania tego zadania.</span><span class="sxs-lookup"><span data-stu-id="7ac64-107">You must select an existing license plate number to complete this task.</span></span> <span data-ttu-id="7ac64-108">Jeśli lokalizacja wyjściowa produkcji jest skonfigurowana do śledzenia według numeru identyfikacyjnego, podczas zgłaszania lokalizacji produkcji jako zakończonej należy uwzględnić numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="7ac64-108">If the production output location is set up to be tracked by license plate, then a license plate number must be included when reporting the production output location as finished.</span></span> <span data-ttu-id="7ac64-109">Pole **numeru identyfikacyjnego** jest widoczne w monicie **raportu o postępie** na stronie **Urządzenie karty zadań**.</span><span class="sxs-lookup"><span data-stu-id="7ac64-109">The **License plate** field is visible on the **Report progress** prompt on the **Job card device** page.</span></span> <span data-ttu-id="7ac64-110">Pole jest widoczne tylko po wyświetleniu monitu **raportu o postępie** podczas tworzenia raportów dotyczących ostatniej operacji zlecenia produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="7ac64-110">The field is only visible on the **Report progress** prompt when reporting on the last operation of the production order.</span></span> <span data-ttu-id="7ac64-111">To pole jest wyświetlane tylko wtedy, gdy towar dla zlecenia produkcyjnego jest włączony dla procesów zarządzania magazynem.</span><span class="sxs-lookup"><span data-stu-id="7ac64-111">The field is only shown if the item for the production order is enabled for the warehouse management processes.</span></span> 
