---
title: Zgłaszanie wyrobów gotowych do lokalizacji niekontrolowanej przez Urządzenie karty zadań
description: Ten temat opisuje proces kończenia wyrobów gotowych w zleceniu produkcyjnym do zapasów, gdy określa lokalizację.
author: johanhoffmann
manager: tfehr
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistration, ProdJournalTransJob, ProdJournalTransRoute, ProdParmReportFinished
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19351
ms.assetid: bcc9e242-b4b8-4144-b14d-c3c106fb40ec
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2019-09-06
ms.dyn365.ops.version: AX 10.0.6
ms.openlocfilehash: f5863202facc83afb91b380ba5666334783ccbcf
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3211176"
---
[!include [banner](../includes/banner.md)]

# <a name="report-as-finished-to-a-license-plate-controlled-location-from-the-job-card-device"></a><span data-ttu-id="c09b7-103">Zgłaszanie wyrobów gotowych do lokalizacji niekontrolowanej przez Urządzenie karty zadań</span><span class="sxs-lookup"><span data-stu-id="c09b7-103">Report as finished to a license plate controlled location from the Job card device</span></span> 

<span data-ttu-id="c09b7-104">Proces zwany Gotowym zgłoszeniem wyrobów gotowych w zleceniu produkcyjnym do magazynu.</span><span class="sxs-lookup"><span data-stu-id="c09b7-104">The process called Reporting as finished completes finished products on a production order to the inventory.</span></span> <span data-ttu-id="c09b7-105">Jeśli produkt gotowy jest włączony dla zaawansowanych procesów magazynowych, produkt jest zgłaszany jako gotowy do lokalizacji zwanej lokalizacją wyjściową produkcji.</span><span class="sxs-lookup"><span data-stu-id="c09b7-105">If the finished product is enabled for the advanced warehouse processes, the product is reported as finished to a location called the production output location.</span></span> <span data-ttu-id="c09b7-106">Aby uzyskać informacje dotyczące konfigurowania lokalizacji produkcji, przejrzyj [Lokalizację wyjściową produkcji](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location).</span><span class="sxs-lookup"><span data-stu-id="c09b7-106">For information about setting up the production output location, see [Production output location](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location).</span></span>

<span data-ttu-id="c09b7-107">Jeśli lokalizacja wyjściowa produkcji jest kontrolowana przez numer rejestracyjny, należy podać numer identyfikacyjny w przypadku zgłaszania produktu jako gotowego.</span><span class="sxs-lookup"><span data-stu-id="c09b7-107">If the production output location is license plate controlled, then a license plate must be provided when reporting as finished.</span></span> <span data-ttu-id="c09b7-108">Pole **numeru identyfikacyjnego** jest widoczne w monicie **raportu o postępie** na stronie **Urządzenie karty zadań**.</span><span class="sxs-lookup"><span data-stu-id="c09b7-108">The **License plate** field is visible on the **Report progress** prompt on the **Job card device** page.</span></span> <span data-ttu-id="c09b7-109">To pole jest widoczne tylko w monicie **zgłaszania postępu** podczas zgłaszania ostatniej operacji zlecenia produkcyjnego, a towar dla zlecenia produkcyjnego jest włączony do procesów zarządzania magazynem.</span><span class="sxs-lookup"><span data-stu-id="c09b7-109">The field is only visible on the **Report progress** prompt when reporting on the last operation of the production order and the item for the production order is enabled for the warehouse management processes.</span></span> 

<span data-ttu-id="c09b7-110">Istnieją dwie opcje podawania numeru rejestracyjnego</span><span class="sxs-lookup"><span data-stu-id="c09b7-110">There are two options for providing the license plate</span></span>
- <span data-ttu-id="c09b7-111">Użytkownik wybiera istniejący numer identyfikacyjny w polu Numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="c09b7-111">The user is selecting an existing license plate in the license plate field.</span></span>
- <span data-ttu-id="c09b7-112">Numer identyfikacyjny jest generowany automatycznie na podstawie sekwencji numerów i ustawiany domyślnie w polu numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="c09b7-112">The license plate is automatically generated from a number sequence and defaulted to the license plate field.</span></span>

<span data-ttu-id="c09b7-113">Opcja automatycznego generowania numeru rejestracyjnego jest konfigurowana przez wybranie opcji **Generuj numer identyfikacyjny** na stronie **Konfigurowanie karty zadań dla urządzeń**.</span><span class="sxs-lookup"><span data-stu-id="c09b7-113">The option to have the license plate generated automatically is configured by selecting the option **Generate license plate** on the **Configure job card for devices** page.</span></span>
