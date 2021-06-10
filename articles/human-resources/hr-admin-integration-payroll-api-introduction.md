---
title: Wprowadzenie do API integracji płac
description: W tym temacie opisano interfejs API integracji Listy płac Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e6d8a1cb9619a863184460a74e472af3f06934b6
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6058567"
---
# <a name="payroll-integration-api-introduction"></a><span data-ttu-id="a6e74-103">Wprowadzenie do API integracji płac</span><span class="sxs-lookup"><span data-stu-id="a6e74-103">Payroll integration API introduction</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="a6e74-104">W tym dokumencie opisano interfejs API integracji Listy płac Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a6e74-104">This document describes the Dynamics 365 Human Resources Payroll integration API.</span></span> <span data-ttu-id="a6e74-105">Interfejs API umożliwia uproszczone, końcowe integracje między Human Resources i partnerami systemów listy płac.</span><span class="sxs-lookup"><span data-stu-id="a6e74-105">The API enables streamlined end-to-end integrations between Human Resources and partnering payroll systems.</span></span> <span data-ttu-id="a6e74-106">Zintegrowane doświadczenie zaczyna się w dziale Human Resources od profilu pracownika, wynagrodzenia i odliczeń oraz informacji o składkach.</span><span class="sxs-lookup"><span data-stu-id="a6e74-106">The integrated experience begins in Human Resources with the employee profile, salary and deduction, and contribution information.</span></span> <span data-ttu-id="a6e74-107">Kiedy zatrudniasz pracownika i wprowadzasz wymagany profil i informacje o płacach do Human Resources, system płac pobiera te informacje do wykorzystania podczas przetwarzania listy płac.</span><span class="sxs-lookup"><span data-stu-id="a6e74-107">When you hire an employee and enter the required profile and pay information into Human Resources, the payroll system pulls this information to use when processing payroll.</span></span> <span data-ttu-id="a6e74-108">Wszelkie aktualizacje wprowadzone do pracownika lub informacje o wynagrodzeniach są również pobierane do wykorzystania w późniejszych okresach wypłaty.</span><span class="sxs-lookup"><span data-stu-id="a6e74-108">Any updates made to the employee or pay information are also pulled for use in later pay runs.</span></span>

![Przepływ integracji płac](media/hr-admin-integration-payroll-api-introduction-flow.png)

<span data-ttu-id="a6e74-110">Aby włączyć integrację, składnik Human Resources zawiera następujące składniki:</span><span class="sxs-lookup"><span data-stu-id="a6e74-110">To enable the integration, Human Resources includes the following components:</span></span>

- <span data-ttu-id="a6e74-111">Funkcja oznaczania pracownika jako gotowego do zapłaty</span><span class="sxs-lookup"><span data-stu-id="a6e74-111">Functionality to mark an employee as ready to pay</span></span>
- <span data-ttu-id="a6e74-112">Integracyjny interfejs API, otwierający nową funkcjonalność do integracji aplikacji</span><span class="sxs-lookup"><span data-stu-id="a6e74-112">An integration API opening up the new functionality to integrating applications</span></span>

## <a name="microsoft-dataverse"></a><span data-ttu-id="a6e74-113">Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="a6e74-113">Microsoft Dataverse</span></span>

<span data-ttu-id="a6e74-114">Ten interfejs API jest wbudowany Microsoft Dataverse (poprzednio Common Data Service).</span><span class="sxs-lookup"><span data-stu-id="a6e74-114">This API is built on Microsoft Dataverse (formerly Common Data Service).</span></span> <span data-ttu-id="a6e74-115">Cała interakcja RESTful z tym interfejsem API odbywa się za pośrednictwem internetowego interfejsu API Microsoft Dataverse, który korzysta z protokołu OData.</span><span class="sxs-lookup"><span data-stu-id="a6e74-115">All RESTful interaction with this API is done via the Microsoft Dataverse Web API, which uses OData.</span></span> <span data-ttu-id="a6e74-116">Ten interfejs API jest podzestawem interfejsu API sieci Web Dataverse.</span><span class="sxs-lookup"><span data-stu-id="a6e74-116">This API is a subset of the Dataverse Web API.</span></span> <span data-ttu-id="a6e74-117">Interfejs API sieci Web Dataverse definiuje cechy, takie jak uwierzytelnianie, umowy SLA, partia, kontrola współbieżności i obsługa błędów.</span><span class="sxs-lookup"><span data-stu-id="a6e74-117">The Dataverse Web API defines characteristics such as authentication, SLAs, batch, concurrency control, and error handling.</span></span>

<span data-ttu-id="a6e74-118">Aby uzyskać więcej ogólnych informacji na temat interfejsu API sieci Web Microsoft Dataverse, zobacz:</span><span class="sxs-lookup"><span data-stu-id="a6e74-118">For more general information about the Microsoft Dataverse Web API, see:</span></span>

- [<span data-ttu-id="a6e74-119">Co to jest usługa Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="a6e74-119">What is Microsoft Dataverse?</span></span>](/powerapps/maker/data-platform/data-platform-intro)
- [<span data-ttu-id="a6e74-120">Użyj interfejsu API sieci Web Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="a6e74-120">Use the Microsoft Dataverse Web API</span></span>](/powerapps/developer/data-platform/webapi/overview)
- [<span data-ttu-id="a6e74-121">Podręcznik dewelopera Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="a6e74-121">Microsoft Dataverse developer guide</span></span>](/powerapps/developer/data-platform)

<span data-ttu-id="a6e74-122">Ta dokumentacja zawiera szczegółowe informacje i wskazówki dla deweloperów dotyczące korzystania z internetowego interfejsu API Dataverse, w tym następujące tematy:</span><span class="sxs-lookup"><span data-stu-id="a6e74-122">This documentation includes details and developer guidance for using the Dataverse Web API, including the following topics:</span></span>

- [<span data-ttu-id="a6e74-123">Uwierzytelnianie z Microsoft Dataverse za pomocą interfejsu API sieci Web</span><span class="sxs-lookup"><span data-stu-id="a6e74-123">Authenticate to Microsoft Dataverse with the Web API</span></span>](/powerapps/developer/data-platform/webapi/authenticate-web-api)
- [<span data-ttu-id="a6e74-124">Wykonywanie operacji przy użyciu interfejsu API sieci Web</span><span class="sxs-lookup"><span data-stu-id="a6e74-124">Perform operations using the Web API</span></span>](/powerapps/developer/data-platform/webapi/perform-operations-web-api)
- [<span data-ttu-id="a6e74-125">Używanie Postman z interfejsem API sieci Web</span><span class="sxs-lookup"><span data-stu-id="a6e74-125">Use Postman with the Web API</span></span>](/powerapps/developer/data-platform/webapi/use-postman-web-api)
- [<span data-ttu-id="a6e74-126">Użyj śledzenia zmian, aby zsynchronizować dane z systemami zewnętrznymi</span><span class="sxs-lookup"><span data-stu-id="a6e74-126">Use change tracking to synchronize data with external systems</span></span>](/powerapps/developer/data-platform/use-change-tracking-synchronize-data-external-systems)

### <a name="virtual-tables-for-human-resources-in-dataverse"></a><span data-ttu-id="a6e74-127">Wirtualne tabele dla Human Resources w Dataverse</span><span class="sxs-lookup"><span data-stu-id="a6e74-127">Virtual tables for Human Resources in Dataverse</span></span>

<span data-ttu-id="a6e74-128">Punkty końcowe dla interfejsu API integracji listy płac korzystają z możliwości platformy tabel wirtualnych Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="a6e74-128">The endpoints for the Payroll integration API use the virtual table platform capabilities of Microsoft Dataverse.</span></span> <span data-ttu-id="a6e74-129">Domyślnie tabele wirtualne i skojarzone z nimi punkty końcowe interfejsu API nie są wdrażane w środowiskach Human Resources, co umożliwia organizacjom określenie, które punkty końcowe OData będą widoczne dla środowiska.</span><span class="sxs-lookup"><span data-stu-id="a6e74-129">By default, the virtual tables and their associated API endpoints aren't deployed for Human Resources environments, enabling organizations to determine which OData endpoints will be exposed for the environment.</span></span> <span data-ttu-id="a6e74-130">Aby można było korzystać z interfejsu API, należy wygenerować tabele wirtualne dla jednostek Human Resources dla środowiska.</span><span class="sxs-lookup"><span data-stu-id="a6e74-130">To use the API, the virtual tables for the Human Resources entities must be generated for the environment.</span></span>

<span data-ttu-id="a6e74-131">Aby uzyskać informacje dotyczące generowania tabel wirtualnych dla interfejsu API, zobacz temat [Konfigurowanie tabel wirtualnych Dataverse](./hr-admin-integration-common-data-service-virtual-entities.md).</span><span class="sxs-lookup"><span data-stu-id="a6e74-131">For information on generating the virtual tables for the API, see [Configure Dataverse virtual tables](./hr-admin-integration-common-data-service-virtual-entities.md).</span></span>

## <a name="data-model"></a><span data-ttu-id="a6e74-132">Model danych</span><span class="sxs-lookup"><span data-stu-id="a6e74-132">Data model</span></span>

<span data-ttu-id="a6e74-133">Poniższy diagram ilustruje relacje w ramach interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="a6e74-133">The following diagram illustrates relationships within the API.</span></span> <span data-ttu-id="a6e74-134">Kilka typów ma klucze obce do innych, wcześniej istniejących jednostek w dziale Human Resources, które nie zostały tutaj zilustrowane.</span><span class="sxs-lookup"><span data-stu-id="a6e74-134">Several types have foreign keys to other, pre-existing entities in Human Resources that aren't illustrated here.</span></span> <span data-ttu-id="a6e74-135">Ten dokument zawiera informacje o jednostkach, które są specyficzne dla scenariuszy integracji listy płac.</span><span class="sxs-lookup"><span data-stu-id="a6e74-135">This document provides information on entities that are specific to payroll integration scenarios.</span></span> <span data-ttu-id="a6e74-136">Jednak istnieje wiele innych podmiotów w Dataverse Web API for Human Resources, które mogą być również istotne dla Twojej integracji.</span><span class="sxs-lookup"><span data-stu-id="a6e74-136">However, there are many other entities in the Dataverse Web API for Human Resources that may also be relevant to your integration.</span></span> <span data-ttu-id="a6e74-137">Niektóre z tych jednostek odwołują się do relacji klucza obcego lub właściwości nawigacji.</span><span class="sxs-lookup"><span data-stu-id="a6e74-137">Some of these entities are referenced in foreign key relationships or navigation properties.</span></span>

![Model danych API integracji listy płac](media/hr-admin-payroll-api-data-model.png)

## <a name="payroll-employee-and-related-entities"></a><span data-ttu-id="a6e74-139">Pracownik etatowy na liście płac i jednostki powiązane</span><span class="sxs-lookup"><span data-stu-id="a6e74-139">Payroll employee and related entities</span></span>

<span data-ttu-id="a6e74-140">Jednostki:</span><span class="sxs-lookup"><span data-stu-id="a6e74-140">Entities:</span></span>

- [<span data-ttu-id="a6e74-141">Pracownik etatowy listy płac</span><span class="sxs-lookup"><span data-stu-id="a6e74-141">Payroll employee</span></span>](hr-admin-integration-payroll-api-payroll-employee.md)
- [<span data-ttu-id="a6e74-142">Adres pracownika listy płac</span><span class="sxs-lookup"><span data-stu-id="a6e74-142">Payroll worker address</span></span>](hr-admin-integration-payroll-api-payroll-worker-address.md)
- [<span data-ttu-id="a6e74-143">Plan stałych wynagrodzeń listy płac</span><span class="sxs-lookup"><span data-stu-id="a6e74-143">Payroll fixed compensation plan</span></span>](hr-admin-integration-ats-api-recruiting-request-education.md)
- [<span data-ttu-id="a6e74-144">Zadanie stanowiska listy płac</span><span class="sxs-lookup"><span data-stu-id="a6e74-144">Payroll position job</span></span>](hr-admin-integration-payroll-api-payroll-position-job.md)
- [<span data-ttu-id="a6e74-145">Stanowisko listy płac</span><span class="sxs-lookup"><span data-stu-id="a6e74-145">Payroll position</span></span>](hr-admin-integration-payroll-api-payroll-position.md)

## <a name="see-also"></a><span data-ttu-id="a6e74-146">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="a6e74-146">See also</span></span>

[<span data-ttu-id="a6e74-147">Generowanie i przeglądanie jednostek listy płac</span><span class="sxs-lookup"><span data-stu-id="a6e74-147">Generate and review payroll entities</span></span>](hr-admin-integration-payroll-api-generate-review-entities.md)<br>
[<span data-ttu-id="a6e74-148">Konfigurowanie parametrów rozwiązania Human Resources</span><span class="sxs-lookup"><span data-stu-id="a6e74-148">Configure Human Resources parameters</span></span>](hr-setup-parameters.md)<br>
[<span data-ttu-id="a6e74-149">Konfigurowanie udostępnionych parametrów rozwiązania Human Resources</span><span class="sxs-lookup"><span data-stu-id="a6e74-149">Configure Human Resources shared parameters</span></span>](hr-setup-shared-parameters.md)<br>
[<span data-ttu-id="a6e74-150">Co to jest usługa Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="a6e74-150">What is Microsoft Dataverse?</span></span>](/powerapps/maker/data-platform/data-platform-intro)<br>
[<span data-ttu-id="a6e74-151">Użyj interfejsu API sieci Web Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="a6e74-151">Use the Microsoft Dataverse Web API</span></span>](/powerapps/developer/data-platform/webapi/overview)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]