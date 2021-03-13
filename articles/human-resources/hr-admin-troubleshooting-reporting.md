---
title: Opcje raportowania
description: W tym artykule opisano, jak rozwiązać ten problem, w którym odbiorca chce dostosować raporty Microsoft Dynamics 365 Human Resources lub tworzyć nowe raporty.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 830c8c32128a8dfc1b009557afb272e48ae3a1ff
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2021
ms.locfileid: "5113824"
---
# <a name="reporting-options"></a><span data-ttu-id="2d466-103">Opcje raportowania</span><span class="sxs-lookup"><span data-stu-id="2d466-103">Reporting options</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="2d466-104">**Szczegóły środowiska**</span><span class="sxs-lookup"><span data-stu-id="2d466-104">**Environment details**</span></span>

<span data-ttu-id="2d466-105">Ten problem dotyczy wszystkich środowisk.</span><span class="sxs-lookup"><span data-stu-id="2d466-105">This issue applies to all environments.</span></span>

<span data-ttu-id="2d466-106">**Objaw**</span><span class="sxs-lookup"><span data-stu-id="2d466-106">**Symptom**</span></span>

<span data-ttu-id="2d466-107">Odbiorca chce dostosować raporty Microsoft Dynamics 365 Human Resources lub tworzyć nowe raporty.</span><span class="sxs-lookup"><span data-stu-id="2d466-107">The customer wants to customize Microsoft Dynamics 365 Human Resources reports or create new reports.</span></span>

<span data-ttu-id="2d466-108">**Wystawienie**</span><span class="sxs-lookup"><span data-stu-id="2d466-108">**Issue**</span></span>

<span data-ttu-id="2d466-109">Użytkownik nie może dostosować osadzonych raportów programu Microsoft Power BI.</span><span class="sxs-lookup"><span data-stu-id="2d466-109">The user can't customize the embedded Microsoft Power BI reports.</span></span>

<span data-ttu-id="2d466-110">**Rozwiązanie**</span><span class="sxs-lookup"><span data-stu-id="2d466-110">**Solution**</span></span>

- <span data-ttu-id="2d466-111">Dane programu Human Resources wysyłane do Dataverse mogą być zgłaszane w za pośrednictwem łącznika Power Apps Dataverse do Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="2d466-111">The Human Resources data that flows to Dataverse can be reported on via the Power Apps Dataverse connector to Power BI Desktop.</span></span> <span data-ttu-id="2d466-112">Należy zauważyć, że usługa Dataverse zawiera podzbiór danych programu Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2d466-112">Note that Dataverse contains a subset of Human Resources data.</span></span> <span data-ttu-id="2d466-113">Aby uzyskać więcej informacji dotyczących Power BI i pulpitów nawigacyjnych, zobacz [Tworzenie raportów Power BI i pulpitów nawigacyjnych za pomocą Power Apps Common Data Service](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).</span><span class="sxs-lookup"><span data-stu-id="2d466-113">For more information about Power BI and dashboards, see [Create Power BI reports and dashboards with Power Apps Common Data Service](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).</span></span>
- <span data-ttu-id="2d466-114">Raportowanie elektroniczne (RE) jest dostępne dla niektórych raportach w programie Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2d466-114">Electronic reporting (ER) is available for some reports in Human Resources.</span></span> <span data-ttu-id="2d466-115">Dostosowania według odbiorcy można wykonać za pomocą opcji konfiguracji ER.</span><span class="sxs-lookup"><span data-stu-id="2d466-115">Customer-driven customizations can be done via the ER configuration options.</span></span>
- <span data-ttu-id="2d466-116">Dane można eksportować do Microsoft Excel lub Microsoft Word przy użyciu różnych elementów danych, które moduł Human Resources dostarcza dzięki integracji z Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="2d466-116">Data can be exported to Microsoft Excel or Microsoft Word by using the various data entities that Human Resources provides through the Microsoft Office integration.</span></span>

<span data-ttu-id="2d466-117">**Rozwiązanie długoterminowe**</span><span class="sxs-lookup"><span data-stu-id="2d466-117">**Long-term solution**</span></span>

<span data-ttu-id="2d466-118">Dodatkowe opcje Power BI będą dostępne i więcej danych i jednostek będzie wchodzić w skład Dataverse.</span><span class="sxs-lookup"><span data-stu-id="2d466-118">Additional Power BI options will be available, and more data and entities will be part of Dataverse.</span></span>
