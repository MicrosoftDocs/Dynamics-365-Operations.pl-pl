---
title: Opcje raportowania w aplikacji Talent
description: W tym temacie opisano, jak rozwiązać ten problem, w którym odbiorca chce dostosować raporty Microsoft Dynamics 365 for Talent lub tworzyć nowe raporty.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 7e00a6e4fc01f72e1ef2347e08754997135215ed
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518856"
---
# <a name="reporting-options-in-talent"></a><span data-ttu-id="b243b-103">Opcje raportowania w aplikacji Talent</span><span class="sxs-lookup"><span data-stu-id="b243b-103">Reporting options in Talent</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b243b-104">**Szczegóły środowiska**</span><span class="sxs-lookup"><span data-stu-id="b243b-104">**Environment details**</span></span>

<span data-ttu-id="b243b-105">Ten problem dotyczy wszystkich środowisk.</span><span class="sxs-lookup"><span data-stu-id="b243b-105">This issue applies to all environments.</span></span>

<span data-ttu-id="b243b-106">**Objaw**</span><span class="sxs-lookup"><span data-stu-id="b243b-106">**Symptom**</span></span>

<span data-ttu-id="b243b-107">Odbiorca chce dostosować raporty Microsoft Dynamics 365 for Talent lub tworzyć nowe raporty.</span><span class="sxs-lookup"><span data-stu-id="b243b-107">The customer wants to customize Microsoft Dynamics 365 for Talent reports or create new reports.</span></span>

<span data-ttu-id="b243b-108">**Wystawienie**</span><span class="sxs-lookup"><span data-stu-id="b243b-108">**Issue**</span></span>

<span data-ttu-id="b243b-109">Użytkownik nie może dostosować osadzonych raportów programu Microsoft Power BI.</span><span class="sxs-lookup"><span data-stu-id="b243b-109">The user can't customize the embedded Microsoft Power BI reports.</span></span>

<span data-ttu-id="b243b-110">**Rozwiązanie**</span><span class="sxs-lookup"><span data-stu-id="b243b-110">**Solution**</span></span>

- <span data-ttu-id="b243b-111">Dane Core HR wysyłane do Common Data Service mogą być zgłaszane w za pośrednictwem łącznika usługi PowerApps Common Data Service do Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="b243b-111">The Core HR data that flows to Common Data Service can be reported on via the PowerApps Common Data Service connector to Power BI Desktop.</span></span> <span data-ttu-id="b243b-112">Należy zauważyć, że usługa Common Data Service zawiera podzbiór danych Core HR.</span><span class="sxs-lookup"><span data-stu-id="b243b-112">Note that Common Data Service contains a subset of Core HR data.</span></span> <span data-ttu-id="b243b-113">Aby uzyskać więcej informacji dotyczących Power BI i pulpitów nawigacyjnych, zobacz [tworzenie raportów Power BI i pulpitów nawigacyjnych za pomocą PowerApps Common Data Service](https://powerapps.microsoft.com/en-us/blog/cdsconnectortopowerbi).</span><span class="sxs-lookup"><span data-stu-id="b243b-113">For more information about Power BI and dashboards, see [Create Power BI reports and dashboards with PowerApps Common Data Service](https://powerapps.microsoft.com/en-us/blog/cdsconnectortopowerbi).</span></span>
- <span data-ttu-id="b243b-114">Raportowanie elektroniczne (RE) jest dostępne dla niektórych raportach w Talent.</span><span class="sxs-lookup"><span data-stu-id="b243b-114">Electronic reporting (ER) is available for some reports in Talent.</span></span> <span data-ttu-id="b243b-115">Dostosowania według odbiorcy można wykonać za pomocą opcji konfiguracji ER.</span><span class="sxs-lookup"><span data-stu-id="b243b-115">Customer-driven customizations can be done via the ER configuration options.</span></span>
- <span data-ttu-id="b243b-116">Dane można eksportować do Microsoft Excel lub Microsoft Word przy użyciu różnych elementów danych, które Talent dostarcza dzięki integracji z Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="b243b-116">Data can be exported to Microsoft Excel or Microsoft Word by using the various data entities that Talent provides through the Microsoft Office integration.</span></span>

<span data-ttu-id="b243b-117">**Rozwiązanie długoterminowe**</span><span class="sxs-lookup"><span data-stu-id="b243b-117">**Long-term solution**</span></span>

<span data-ttu-id="b243b-118">Dodatkowe opcje Power BI będą dostępne i więcej danych i jednostek będzie wchodzić w skład Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="b243b-118">Additional Power BI options will be available, and more data and entities will be part of Common Data Service.</span></span>
