---
title: Opcje raportowania
description: W tym artykule opisano, jak rozwiązać ten problem, w którym odbiorca chce dostosować raporty Microsoft Dynamics 365 Human Resources lub tworzyć nowe raporty.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 64a03724d81745373d028d76a8cc64aab66efdbb
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053306"
---
# <a name="reporting-options"></a><span data-ttu-id="62cc9-103">Opcje raportowania</span><span class="sxs-lookup"><span data-stu-id="62cc9-103">Reporting options</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="62cc9-104">**Szczegóły środowiska**</span><span class="sxs-lookup"><span data-stu-id="62cc9-104">**Environment details**</span></span>

<span data-ttu-id="62cc9-105">Ten problem dotyczy wszystkich środowisk.</span><span class="sxs-lookup"><span data-stu-id="62cc9-105">This issue applies to all environments.</span></span>

<span data-ttu-id="62cc9-106">**Objaw**</span><span class="sxs-lookup"><span data-stu-id="62cc9-106">**Symptom**</span></span>

<span data-ttu-id="62cc9-107">Odbiorca chce dostosować raporty Microsoft Dynamics 365 Human Resources lub tworzyć nowe raporty.</span><span class="sxs-lookup"><span data-stu-id="62cc9-107">The customer wants to customize Microsoft Dynamics 365 Human Resources reports or create new reports.</span></span>

<span data-ttu-id="62cc9-108">**Wystawienie**</span><span class="sxs-lookup"><span data-stu-id="62cc9-108">**Issue**</span></span>

<span data-ttu-id="62cc9-109">Użytkownik nie może dostosować osadzonych raportów programu Microsoft Power BI.</span><span class="sxs-lookup"><span data-stu-id="62cc9-109">The user can't customize the embedded Microsoft Power BI reports.</span></span>

<span data-ttu-id="62cc9-110">**Rozwiązanie**</span><span class="sxs-lookup"><span data-stu-id="62cc9-110">**Solution**</span></span>

- <span data-ttu-id="62cc9-111">Dane programu Human Resources wysyłane do Dataverse mogą być zgłaszane w za pośrednictwem łącznika Power Apps Dataverse do Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="62cc9-111">The Human Resources data that flows to Dataverse can be reported on via the Power Apps Dataverse connector to Power BI Desktop.</span></span> <span data-ttu-id="62cc9-112">Należy zauważyć, że usługa Dataverse zawiera podzbiór danych programu Human Resources.</span><span class="sxs-lookup"><span data-stu-id="62cc9-112">Note that Dataverse contains a subset of Human Resources data.</span></span> <span data-ttu-id="62cc9-113">Aby uzyskać więcej informacji dotyczących Power BI i pulpitów nawigacyjnych, zobacz [Tworzenie raportów Power BI i pulpitów nawigacyjnych za pomocą Power Apps Common Data Service](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).</span><span class="sxs-lookup"><span data-stu-id="62cc9-113">For more information about Power BI and dashboards, see [Create Power BI reports and dashboards with Power Apps Common Data Service](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).</span></span>
- <span data-ttu-id="62cc9-114">Raportowanie elektroniczne (RE) jest dostępne dla niektórych raportach w programie Human Resources.</span><span class="sxs-lookup"><span data-stu-id="62cc9-114">Electronic reporting (ER) is available for some reports in Human Resources.</span></span> <span data-ttu-id="62cc9-115">Dostosowania według odbiorcy można wykonać za pomocą opcji konfiguracji ER.</span><span class="sxs-lookup"><span data-stu-id="62cc9-115">Customer-driven customizations can be done via the ER configuration options.</span></span>
- <span data-ttu-id="62cc9-116">Dane można eksportować do Microsoft Excel lub Microsoft Word przy użyciu różnych elementów danych, które moduł Human Resources dostarcza dzięki integracji z Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="62cc9-116">Data can be exported to Microsoft Excel or Microsoft Word by using the various data entities that Human Resources provides through the Microsoft Office integration.</span></span>

<span data-ttu-id="62cc9-117">**Rozwiązanie długoterminowe**</span><span class="sxs-lookup"><span data-stu-id="62cc9-117">**Long-term solution**</span></span>

<span data-ttu-id="62cc9-118">Dodatkowe opcje Power BI będą dostępne i więcej danych i jednostek będzie wchodzić w skład Dataverse.</span><span class="sxs-lookup"><span data-stu-id="62cc9-118">Additional Power BI options will be available, and more data and entities will be part of Dataverse.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]