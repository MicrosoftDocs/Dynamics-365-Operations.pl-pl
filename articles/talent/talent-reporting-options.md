---
title: Opcje raportowania w aplikacji Talent
description: W tym temacie opisano, jak rozwiązać ten problem, w którym odbiorca chce dostosować raporty Microsoft Dynamics 365 for Talent lub tworzyć nowe raporty.
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 2007e6adec7255b0b3abda7490c2103a8583393f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "305846"
---
# <a name="reporting-options-in-talent"></a><span data-ttu-id="65ab0-103">Opcje raportowania w aplikacji Talent</span><span class="sxs-lookup"><span data-stu-id="65ab0-103">Reporting options in Talent</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="65ab0-104">**Szczegóły środowiska**</span><span class="sxs-lookup"><span data-stu-id="65ab0-104">**Environment details**</span></span>

<span data-ttu-id="65ab0-105">Ten problem dotyczy wszystkich środowisk.</span><span class="sxs-lookup"><span data-stu-id="65ab0-105">This issue applies to all environments.</span></span>

<span data-ttu-id="65ab0-106">**Objaw**</span><span class="sxs-lookup"><span data-stu-id="65ab0-106">**Symptom**</span></span>

<span data-ttu-id="65ab0-107">Odbiorca chce dostosować raporty Microsoft Dynamics 365 for Talent lub tworzyć nowe raporty.</span><span class="sxs-lookup"><span data-stu-id="65ab0-107">The customer wants to customize Microsoft Dynamics 365 for Talent reports or create new reports.</span></span>

<span data-ttu-id="65ab0-108">**Wystawienie**</span><span class="sxs-lookup"><span data-stu-id="65ab0-108">**Issue**</span></span>

<span data-ttu-id="65ab0-109">Użytkownik nie może dostosować osadzonych raportów programu Microsoft Power BI.</span><span class="sxs-lookup"><span data-stu-id="65ab0-109">The user can't customize the embedded Microsoft Power BI reports.</span></span>

<span data-ttu-id="65ab0-110">**Rozwiązanie**</span><span class="sxs-lookup"><span data-stu-id="65ab0-110">**Solution**</span></span>

- <span data-ttu-id="65ab0-111">Dane Core HR wysyłane do Common Data Service for Apps mogą być zgłaszane w za pośrednictwem łącznika usługi PowerApps CDS do Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="65ab0-111">The Core HR data that flows to Common Data Service for Apps can be reported on via the PowerApps CDS connector to Power BI Desktop.</span></span> <span data-ttu-id="65ab0-112">Należy zauważyć, że usługa Common Data Service for Apps zawiera podzbiór danych Core HR.</span><span class="sxs-lookup"><span data-stu-id="65ab0-112">Note that Common Data Service for Apps contains a subset of Core HR data.</span></span> <span data-ttu-id="65ab0-113">Aby uzyskać więcej informacji dotyczących Power BI i pulpitów nawigacyjnych, zobacz [tworzenie raportów Power BI i pulpitów nawigacyjnych za pomocą PowerApps Common Data Service](https://powerapps.microsoft.com/en-us/blog/cdsconnectortopowerbi).</span><span class="sxs-lookup"><span data-stu-id="65ab0-113">For more information about Power BI and dashboards, see [Create Power BI reports and dashboards with PowerApps Common Data Service](https://powerapps.microsoft.com/en-us/blog/cdsconnectortopowerbi).</span></span>
- <span data-ttu-id="65ab0-114">Raportowanie elektroniczne (RE) jest dostępne dla niektórych raportach w Talent.</span><span class="sxs-lookup"><span data-stu-id="65ab0-114">Electronic reporting (ER) is available for some reports in Talent.</span></span> <span data-ttu-id="65ab0-115">Dostosowania według odbiorcy można wykonać za pomocą opcji konfiguracji ER.</span><span class="sxs-lookup"><span data-stu-id="65ab0-115">Customer-driven customizations can be done via the ER configuration options.</span></span>
- <span data-ttu-id="65ab0-116">Dane można eksportować do Microsoft Excel lub Microsoft Word przy użyciu różnych elementów danych, które Talent dostarcza dzięki integracji z Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="65ab0-116">Data can be exported to Microsoft Excel or Microsoft Word by using the various data entities that Talent provides through the Microsoft Office integration.</span></span>

<span data-ttu-id="65ab0-117">**Rozwiązanie długoterminowe**</span><span class="sxs-lookup"><span data-stu-id="65ab0-117">**Long-term solution**</span></span>

<span data-ttu-id="65ab0-118">Dodatkowe opcje Power BI będą dostępne i więcej danych i jednostek będzie wchodzić w skład Common Data Service for Apps.</span><span class="sxs-lookup"><span data-stu-id="65ab0-118">Additional Power BI options will be available, and more data and entities will be part of Common Data Service for Apps.</span></span>
