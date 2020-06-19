---
title: Opcje raportowania
description: W tym artykule opisano, jak rozwiązać ten problem, w którym odbiorca chce dostosować raporty Microsoft Dynamics 365 Human Resources lub tworzyć nowe raporty.
author: andreabichsel
manager: AnnBe
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
ms.openlocfilehash: 5d47524033bf39a1db6b22b28ee3fcc65348829c
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2020
ms.locfileid: "3431022"
---
# <a name="reporting-options"></a><span data-ttu-id="7755d-103">Opcje raportowania</span><span class="sxs-lookup"><span data-stu-id="7755d-103">Reporting options</span></span>

<span data-ttu-id="7755d-104">**Szczegóły środowiska**</span><span class="sxs-lookup"><span data-stu-id="7755d-104">**Environment details**</span></span>

<span data-ttu-id="7755d-105">Ten problem dotyczy wszystkich środowisk.</span><span class="sxs-lookup"><span data-stu-id="7755d-105">This issue applies to all environments.</span></span>

<span data-ttu-id="7755d-106">**Objaw**</span><span class="sxs-lookup"><span data-stu-id="7755d-106">**Symptom**</span></span>

<span data-ttu-id="7755d-107">Odbiorca chce dostosować raporty Microsoft Dynamics 365 Human Resources lub tworzyć nowe raporty.</span><span class="sxs-lookup"><span data-stu-id="7755d-107">The customer wants to customize Microsoft Dynamics 365 Human Resources reports or create new reports.</span></span>

<span data-ttu-id="7755d-108">**Wystawienie**</span><span class="sxs-lookup"><span data-stu-id="7755d-108">**Issue**</span></span>

<span data-ttu-id="7755d-109">Użytkownik nie może dostosować osadzonych raportów programu Microsoft Power BI.</span><span class="sxs-lookup"><span data-stu-id="7755d-109">The user can't customize the embedded Microsoft Power BI reports.</span></span>

<span data-ttu-id="7755d-110">**Rozwiązanie**</span><span class="sxs-lookup"><span data-stu-id="7755d-110">**Solution**</span></span>

- <span data-ttu-id="7755d-111">Dane programu Human Resources wysyłane do Common Data Service mogą być zgłaszane w za pośrednictwem łącznika Power Apps Common Data Service do Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="7755d-111">The Human Resources data that flows to Common Data Service can be reported on via the Power Apps Common Data Service connector to Power BI Desktop.</span></span> <span data-ttu-id="7755d-112">Należy zauważyć, że usługa Common Data Service zawiera podzbiór danych programu Human Resources.</span><span class="sxs-lookup"><span data-stu-id="7755d-112">Note that Common Data Service contains a subset of Human Resources data.</span></span> <span data-ttu-id="7755d-113">Aby uzyskać więcej informacji dotyczących Power BI i pulpitów nawigacyjnych, zobacz [Tworzenie raportów Power BI i pulpitów nawigacyjnych za pomocą Power Apps Common Data Service](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).</span><span class="sxs-lookup"><span data-stu-id="7755d-113">For more information about Power BI and dashboards, see [Create Power BI reports and dashboards with Power Apps Common Data Service](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).</span></span>
- <span data-ttu-id="7755d-114">Raportowanie elektroniczne (RE) jest dostępne dla niektórych raportach w programie Human Resources.</span><span class="sxs-lookup"><span data-stu-id="7755d-114">Electronic reporting (ER) is available for some reports in Human Resources.</span></span> <span data-ttu-id="7755d-115">Dostosowania według odbiorcy można wykonać za pomocą opcji konfiguracji ER.</span><span class="sxs-lookup"><span data-stu-id="7755d-115">Customer-driven customizations can be done via the ER configuration options.</span></span>
- <span data-ttu-id="7755d-116">Dane można eksportować do Microsoft Excel lub Microsoft Word przy użyciu różnych elementów danych, które moduł Human Resources dostarcza dzięki integracji z Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="7755d-116">Data can be exported to Microsoft Excel or Microsoft Word by using the various data entities that Human Resources provides through the Microsoft Office integration.</span></span>

<span data-ttu-id="7755d-117">**Rozwiązanie długoterminowe**</span><span class="sxs-lookup"><span data-stu-id="7755d-117">**Long-term solution**</span></span>

<span data-ttu-id="7755d-118">Dodatkowe opcje Power BI będą dostępne i więcej danych i jednostek będzie wchodzić w skład Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="7755d-118">Additional Power BI options will be available, and more data and entities will be part of Common Data Service.</span></span>
