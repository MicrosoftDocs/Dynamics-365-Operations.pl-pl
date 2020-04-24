---
title: Omówienie konserwacji zapobiegawczej
description: W tym temacie wyjaśniono konserwację zapobiegawczą w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8949f9b26917c4a93faa5aea74faa0b6735d770f
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3206019"
---
# <a name="preventive-maintenance-overview"></a><span data-ttu-id="12309-103">Omówienie konserwacji zapobiegawczej</span><span class="sxs-lookup"><span data-stu-id="12309-103">Preventive maintenance overview</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="12309-104">W tym temacie wyjaśniono konserwację zapobiegawczą w module Zarządzanie składnikami majątku.</span><span class="sxs-lookup"><span data-stu-id="12309-104">This topic explains preventive maintenance in Asset Management.</span></span> <span data-ttu-id="12309-105">Konserwacja zapobiegawcza to dyscyplina obejmująca planowane zadania konserwacyjne, na przykład regularne przeglądy, kalibrację i inspekcje.</span><span class="sxs-lookup"><span data-stu-id="12309-105">Preventive maintenance is a discipline involving planned maintenance jobs, for example, regular service, calibration, and inspections.</span></span> <span data-ttu-id="12309-106">W module **Zarządzanie składnikami majątku** można tworzyć plany konserwacji i konfigurować je w aktywach i lokalizacjach czynności konserwacji.</span><span class="sxs-lookup"><span data-stu-id="12309-106">In **Asset Management**, you can create maintenance plans and set them up on assets and functional locations.</span></span> <span data-ttu-id="12309-107">Można również ustawić serie czynności konserwacyjnych na czynnościach konserwacyjnych.</span><span class="sxs-lookup"><span data-stu-id="12309-107">You can also set up maintenance rounds on functional locations.</span></span> <span data-ttu-id="12309-108">Plany konserwacji dotyczące składników majątku są aktywne niezależnie od tego, gdzie jest zainstalowany składnik majątku.</span><span class="sxs-lookup"><span data-stu-id="12309-108">Maintenance plans on assets are active regardless of where the asset is installed.</span></span> <span data-ttu-id="12309-109">Plany konserwacji i serie czynności konserwacyjnych w lokalizacji czynności konserwacyjnych są aktywne dla składników majątku aktualnie zainstalowanych w danej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="12309-109">Maintenance plans and maintenance rounds on functional location are active for the assets currently installed at the location.</span></span> <span data-ttu-id="12309-110">Zamiast konfigurować plany konserwacji dla składników majatku lub konfigurować serie w lokalizacjach czynności konserwacyjnych, można utworzyć serie czynności konserwacyjnych obejmujące wiele składników majątku, dla których należy wykonać powiązane typy zadań konserwacyjnych w tej samej procedurze pracy.</span><span class="sxs-lookup"><span data-stu-id="12309-110">Instead of setting up maintenance plans on assets, or setting up maintenance rounds on functional locations, you can create maintenance rounds that include multiple assets on which you need to perform related types of maintenance jobs in the same work routine.</span></span> <span data-ttu-id="12309-111">Serie czynności konserwacyjnych stworzone ze składników majątki - zamiast stowrzone z lokalizacji czynności konserwacyjnych — oznacza, że można wybrać pewną liczbę składników majątku dla jednej serii czynności konserwacyjnych, które nie są zainstalowane w tej samej lokalizacji czynności konserwacyjnych.</span><span class="sxs-lookup"><span data-stu-id="12309-111">Maintenance rounds created from assets - instead of created on functional locations - means that you can select a number of assets for one maintenance round, which are not installed on the same functional location.</span></span>

<span data-ttu-id="12309-112">Plany konserwacji są używane do obsługi prewencyjnej i aktywnej konserwacji poszczególnych składników majątku.</span><span class="sxs-lookup"><span data-stu-id="12309-112">Maintenance plans are used for preventive and reactive maintenance on individual assets.</span></span> <span data-ttu-id="12309-113">Serie czynności konserwacyjnych są używane do obsługi profilaktycznej grupy lub zbioru składników majątku.</span><span class="sxs-lookup"><span data-stu-id="12309-113">Maintenance rounds are used for preventive maintenance on a group or a set of assets.</span></span> <span data-ttu-id="12309-114">Plany konserwacji i serie czynności konserwacyjnych służą do generowania propozycji zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="12309-114">Maintenance plans and maintenance rounds are used for generating work order proposals.</span></span> <span data-ttu-id="12309-115">Propozycje zleceń pracy są zapisywane jako wiersze harmonogramu konserwacji, które można powiązać i przekształcić w zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="12309-115">The work order proposals are saved as maintenance schedule lines, which can be bundled and converted into work orders.</span></span>

<span data-ttu-id="12309-116">Poniższa ilustracja przedstawia przepływ pracy, tworząc plany konserwacji i serie czynności konserwacyjnych w celu utworzenia zleceń pracy dla składników majątku na podstawie tych planów konserwacji i serii czynności konserwacyjnych.</span><span class="sxs-lookup"><span data-stu-id="12309-116">The following illustration provides an overview of the work flow from creating maintenance plans and maintenance rounds to creating work orders for assets, based on those maintenance plans and maintenance rounds.</span></span>

![Rysunek 1](media/01-preventive-maintenance.png)

