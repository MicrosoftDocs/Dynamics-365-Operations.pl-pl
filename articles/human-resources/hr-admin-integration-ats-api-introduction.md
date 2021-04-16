---
title: Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów
description: W tym temacie opisano interfejs API integracji systemu śledzenia kandydatów (ATS) Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 599f9728019cd6bc59c59a4f08df06c6c9c9ac31
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798426"
---
# <a name="applicant-tracking-system-integration-api-introduction"></a><span data-ttu-id="05da2-103">Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów</span><span class="sxs-lookup"><span data-stu-id="05da2-103">Applicant Tracking System integration API introduction</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="05da2-104">W tym temacie opisano interfejs API integracji systemu śledzenia kandydatów (ATS) Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="05da2-104">This topic describes the Dynamics 365 Human Resources Applicant Tracking System (ATS) integration API.</span></span> <span data-ttu-id="05da2-105">Celem API jest umożliwienie usprawnionej integracji między Dynamics 365 Human Resources i współpracującymi ATS.</span><span class="sxs-lookup"><span data-stu-id="05da2-105">The intent of the API is to enable streamlined integrations between Dynamics 365 Human Resources and partnering ATSs.</span></span>

![Przepływ integracji ATS](media/hr-admin-integration-ats-api-introduction-flow.png)

<span data-ttu-id="05da2-107">Zintegrowane doświadczenie zaczyna się w dziale zasobów ludzkich, gdy kierownik kadr tworzy wniosek rekrutacyjny.</span><span class="sxs-lookup"><span data-stu-id="05da2-107">The integrated experience begins in Human Resources when a hiring manager creates a recruiting request.</span></span> <span data-ttu-id="05da2-108">Gdy wniosek zostanie uaktywniony, ATS ściąga szczegóły wniosku o utworzenie projektu rekrutacji.</span><span class="sxs-lookup"><span data-stu-id="05da2-108">When the request is activated, the ATS pulls the detail for the request to create a recruiting project.</span></span> <span data-ttu-id="05da2-109">Następnie następuje rekrutacja, aby wybrać i zatrudnić kandydata na dane stanowisko.</span><span class="sxs-lookup"><span data-stu-id="05da2-109">Then it follows the recruiting pipeline to select and hire a candidate for the position(s).</span></span> <span data-ttu-id="05da2-110">Na koniec ATS kończy integrację w obie strony, przesyłając rekord wybranego kandydata do działu kadr.</span><span class="sxs-lookup"><span data-stu-id="05da2-110">Finally, the ATS completes the round-trip integration by sending the selected candidate’s record into Human Resources.</span></span> <span data-ttu-id="05da2-111">Rekord kandydata może następnie przejść przez kolejne walidacje wprowadzające i przepływy pracy, aby utworzyć rekord pracownika.</span><span class="sxs-lookup"><span data-stu-id="05da2-111">The candidate record can then go through more onboarding validations and workflows to create the employee record.</span></span>

<span data-ttu-id="05da2-112">Aby włączyć integrację, w składniku Human Resources zostały dodane następujące składniki:</span><span class="sxs-lookup"><span data-stu-id="05da2-112">To enable the integration, Human Resources has added the following components:</span></span>

1.  <span data-ttu-id="05da2-113">Funkcja do tworzenia wniosku o rekrutację.</span><span class="sxs-lookup"><span data-stu-id="05da2-113">Functionality to create a recruiting request.</span></span>
2.  <span data-ttu-id="05da2-114">Rozwinięty profil kandydata i powiązane przepływy pracy.</span><span class="sxs-lookup"><span data-stu-id="05da2-114">An expanded candidate profile and related workflows.</span></span>
3.  <span data-ttu-id="05da2-115">Integracyjny interfejs API, otwierający nową funkcjonalność do integracji aplikacji.</span><span class="sxs-lookup"><span data-stu-id="05da2-115">An integration API opening up the new functionality to integrating applications.</span></span>

<span data-ttu-id="05da2-116">Aby uzyskać więcej informacji na temat konfigurowania i korzystania z prośby o rekrutację i funkcji kandydata, zobacz [Rekrutowanie kandydatów do pracy](hr-personnel-recruit.md).</span><span class="sxs-lookup"><span data-stu-id="05da2-116">For more information about setting up and using the recruiting request and candidate functionality, see [Recruit job candidates](hr-personnel-recruit.md).</span></span>

## <a name="microsoft-dataverse"></a><span data-ttu-id="05da2-117">Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="05da2-117">Microsoft Dataverse</span></span>

<span data-ttu-id="05da2-118">Ten interfejs API jest wbudowany Microsoft Dataverse (poprzednio Common Data Service).</span><span class="sxs-lookup"><span data-stu-id="05da2-118">This API is built on Microsoft Dataverse (formerly Common Data Service).</span></span> <span data-ttu-id="05da2-119">Cała interakcja RESTful z tym interfejsem API odbywa się za pośrednictwem internetowego interfejsu API Microsoft Dataverse, który korzysta z protokołu OData.</span><span class="sxs-lookup"><span data-stu-id="05da2-119">All RESTful interaction with this API is done via the Microsoft Dataverse Web API, which uses OData.</span></span> <span data-ttu-id="05da2-120">Ten interfejs API jest podzestawem interfejsu API sieci Web Dataverse.</span><span class="sxs-lookup"><span data-stu-id="05da2-120">This API is a subset of the Dataverse Web API.</span></span> <span data-ttu-id="05da2-121">Interfejs API sieci Web Dataverse definiuje cechy, takie jak uwierzytelnianie, umowy SLA, partia, kontrola współbieżności i obsługa błędów.</span><span class="sxs-lookup"><span data-stu-id="05da2-121">The Dataverse Web API defines characteristics such as authentication, SLAs, batch, concurrency control, and error handling.</span></span>

<span data-ttu-id="05da2-122">Aby uzyskać więcej ogólnych informacji na temat interfejsu API sieci Web Microsoft Dataverse, zobacz:</span><span class="sxs-lookup"><span data-stu-id="05da2-122">For more general information about the Microsoft Dataverse Web API, see:</span></span>

- [<span data-ttu-id="05da2-123">Co to jest usługa Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="05da2-123">What is Microsoft Dataverse?</span></span>](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)
- [<span data-ttu-id="05da2-124">Użyj interfejsu API sieci Web Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="05da2-124">Use the Microsoft Dataverse Web API</span></span>](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/overview)
- [<span data-ttu-id="05da2-125">Podręcznik dewelopera Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="05da2-125">Microsoft Dataverse developer guide</span></span>](https://docs.microsoft.com/powerapps/developer/data-platform)

<span data-ttu-id="05da2-126">Powyższe dokumentacja zawiera szczegółowe wskazówki dla programistów dotyczące używania interfejsu API sieci Web Dataverse, takie jak [zarządzanie uwierzytelnianiem](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/authenticate-web-api), [wykonywanie operacji](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/perform-operations-web-api), [używanie Postmana z interfejsem API](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/use-postman-web-api) oraz [korzystanie z tokenów śledzenia zmian lub różnic](https://docs.microsoft.com/powerapps/developer/data-platform/use-change-tracking-synchronize-data-external-systems) z interfejsem API.</span><span class="sxs-lookup"><span data-stu-id="05da2-126">The above documentation includes detail and developer guidance on using the Dataverse Web API, such as [managing authentication](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/authenticate-web-api), [performing operations](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/perform-operations-web-api), [using Postman with the API](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/use-postman-web-api), and [using change tracking or delta tokens](https://docs.microsoft.com/powerapps/developer/data-platform/use-change-tracking-synchronize-data-external-systems) with the API.</span></span>

### <a name="option-sets"></a><span data-ttu-id="05da2-127">Zestawy opcji</span><span class="sxs-lookup"><span data-stu-id="05da2-127">Option sets</span></span>

<span data-ttu-id="05da2-128">Model danych dla interfejsu API integracji ATS opisany w tym dokumencie obejmuje zestawy opcji, które zapewniają wyliczone wartości powiązane z właściwościami jednostki.</span><span class="sxs-lookup"><span data-stu-id="05da2-128">The data model for the ATS integration API described in this document includes option sets that provide enumerated values associated with entity properties.</span></span> <span data-ttu-id="05da2-129">Aby uzyskać szczegółowe informacje dotyczące pracy z zestawami opcji w interfejsie API sieci Web Dataverse, zobacz temat [Tworzenie i aktualizowanie zestawów opcji przy użyciu interfejsu API sieci Web](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/create-update-optionsets).</span><span class="sxs-lookup"><span data-stu-id="05da2-129">For detail on working with option sets in the Dataverse Web API, see [Create and update option sets using the Web API](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/create-update-optionsets).</span></span> <span data-ttu-id="05da2-130">Zestawy opcji są definiowane dla każdego środowiska Dataverse.</span><span class="sxs-lookup"><span data-stu-id="05da2-130">Option sets are defined for each Dataverse environment.</span></span>

### <a name="virtual-tables-for-human-resources-in-dataverse"></a><span data-ttu-id="05da2-131">Wirtualne tabele dla Human Resources w Dataverse</span><span class="sxs-lookup"><span data-stu-id="05da2-131">Virtual tables for Human Resources in Dataverse</span></span>

<span data-ttu-id="05da2-132">Punkty końcowe dla interfejsu API integracji ATS korzystają z możliwości platformy tabel wirtualnych Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="05da2-132">The endpoints for the ATS integration API use the virtual table platform capabilities of Microsoft Dataverse.</span></span> <span data-ttu-id="05da2-133">Domyślnie tabele wirtualne i skojarzone z nimi punkty końcowe interfejsu API nie są wdrażane w środowiskach Human Resources, co umożliwia organizacjom określenie, które punkty końcowe OData będą widoczne dla środowiska.</span><span class="sxs-lookup"><span data-stu-id="05da2-133">By default, the virtual tables and their associated API endpoints are not deployed for Human Resources environments, enabling organizations to determine which OData endpoints will be exposed for the environment.</span></span> <span data-ttu-id="05da2-134">Aby można było korzystać z interfejsu API, należy wygenerować tabele wirtualne dla jednostek Human Resources dla środowiska.</span><span class="sxs-lookup"><span data-stu-id="05da2-134">To use the API, the virtual tables for the Human Resources entities must be generated for the environment.</span></span> 

<span data-ttu-id="05da2-135">Aby uzyskać informacje dotyczące generowania tabel wirtualnych dla interfejsu API, zobacz temat [Konfigurowanie tabel wirtualnych Dataverse](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service-virtual-entities).</span><span class="sxs-lookup"><span data-stu-id="05da2-135">For information on generating the virtual tables for the API, see [Configure Dataverse virtual tables](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service-virtual-entities).</span></span>

## <a name="data-model"></a><span data-ttu-id="05da2-136">Model danych</span><span class="sxs-lookup"><span data-stu-id="05da2-136">Data model</span></span>

<span data-ttu-id="05da2-137">Model danych jest na środku dwóch głównych jednostek:</span><span class="sxs-lookup"><span data-stu-id="05da2-137">The data model is centered around two main entities:</span></span>

- <span data-ttu-id="05da2-138">**RecruitingRequest** reprezentuje żądanie skierowane do ATS w celu rekrutacji na jedno lub więcej wolnych stanowisk. Aby zapoznać się z przykładowym zapytaniem, zobacz [Przykładowe zapytanie dotyczące wniosku rekrutacyjnego](hr-admin-integration-ats-api-recruiting-request-example-query.md).</span><span class="sxs-lookup"><span data-stu-id="05da2-138">**RecruitingRequest** represents a request to an ATS to recruit for one or more open positions.For an example query, see [Example query for Recruiting request](hr-admin-integration-ats-api-recruiting-request-example-query.md).</span></span>
- <span data-ttu-id="05da2-139">**CandidateToHire** przedstawia szczegóły kandydata, który zaakceptował ofertę na stanowisko.</span><span class="sxs-lookup"><span data-stu-id="05da2-139">**CandidateToHire** represents details of a candidate who has accepted an offer for a position.</span></span> <span data-ttu-id="05da2-140">**Osoba** reprezentuje osobę, która jest kandydatem.</span><span class="sxs-lookup"><span data-stu-id="05da2-140">**Person** represents the individual who is the candidate.</span></span> <span data-ttu-id="05da2-141">Osoba może pełnić w firmie wiele ról, takich jak kandydat, pracownik, pracownik pełnoetatowy czy zleceniobiorca.</span><span class="sxs-lookup"><span data-stu-id="05da2-141">A person can have multiple roles in the company, such as candidate, worker, employee, or contractor.</span></span> <span data-ttu-id="05da2-142">Aby uzyskać przykładowe zapytanie, zobacz [Przykład kwerendy dotyczącej kandydata do zatrudnienia](hr-admin-integration-ats-api-candidate-to-hire-example-query.md).</span><span class="sxs-lookup"><span data-stu-id="05da2-142">For an example query, see [Example query for Candidate to hire](hr-admin-integration-ats-api-candidate-to-hire-example-query.md).</span></span>

<span data-ttu-id="05da2-143">Poniższy diagram ilustruje relacje w ramach interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="05da2-143">The following diagram illustrates relationships within the API.</span></span> <span data-ttu-id="05da2-144">Kilka typów ma klucze obce do innych, wcześniej istniejących jednostek w dziale Human Resources, które nie zostały tutaj zilustrowane.</span><span class="sxs-lookup"><span data-stu-id="05da2-144">Several types have foreign keys to other, pre-existing entities in Human Resources that aren't illustrated here.</span></span> <span data-ttu-id="05da2-145">Ten dokument zawiera informacje o jednostkach, które są specyficzne dla scenariuszy integracji rekrutacji.</span><span class="sxs-lookup"><span data-stu-id="05da2-145">This document provides information on entities that are specific to recruiting integration scenarios.</span></span> <span data-ttu-id="05da2-146">W interfejsie API sieci Web Dataverse istnieje jednak wiele innych jednostek, które mogą być także istotne dla integracji Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="05da2-146">However, there are many other entities in the Dataverse Web API for Dynamics 365 Human Resources that may also be relevant to your integration.</span></span> <span data-ttu-id="05da2-147">Na przykład mogą być potrzebne szczegółowe informacje dotyczące pracowników, stanowisk, stanowisk lub innych jednostek, które nie zostały tutaj zdefiniowane.</span><span class="sxs-lookup"><span data-stu-id="05da2-147">For example, you may also need detail for workers, jobs, positions, or other entities not defined here.</span></span> <span data-ttu-id="05da2-148">Wiele z tych jednostek odwołuje się do relacji klucza obcego lub właściwości nawigacji.</span><span class="sxs-lookup"><span data-stu-id="05da2-148">Many of these entities are referenced in foreign key relationships or navigation properties.</span></span>

![Model danych ATS integracji API](media/hr-admin-integration-ats-api-data-model.png)

## <a name="recruiting-request-and-related-entities-and-option-sets"></a><span data-ttu-id="05da2-150">Żądania rekrutacji oraz powiązane jednostki i zestawy opcji</span><span class="sxs-lookup"><span data-stu-id="05da2-150">Recruiting request and related entities and option sets</span></span>

<span data-ttu-id="05da2-151">Przykład kwerendy:</span><span class="sxs-lookup"><span data-stu-id="05da2-151">Example query:</span></span> 

- [<span data-ttu-id="05da2-152">Przykładowa kwerenda dla wniosku o rekrutację</span><span class="sxs-lookup"><span data-stu-id="05da2-152">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)

<span data-ttu-id="05da2-153">Jednostki:</span><span class="sxs-lookup"><span data-stu-id="05da2-153">Entities:</span></span>

- [<span data-ttu-id="05da2-154">Wniosek o rekrutację</span><span class="sxs-lookup"><span data-stu-id="05da2-154">Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request.md)
- [<span data-ttu-id="05da2-155">Stanowisko wniosku o rekrutację</span><span class="sxs-lookup"><span data-stu-id="05da2-155">Recruiting request position</span></span>](hr-admin-integration-ats-api-recruiting-request-position.md)
- [<span data-ttu-id="05da2-156">Umiejętność we wniosku o rekrutację</span><span class="sxs-lookup"><span data-stu-id="05da2-156">Recruiting request skill</span></span>](hr-admin-integration-ats-api-recruiting-request-skill.md)
- [<span data-ttu-id="05da2-157">Rekrutacja wymaga edukacji</span><span class="sxs-lookup"><span data-stu-id="05da2-157">Recruiting request education</span></span>](hr-admin-integration-ats-api-recruiting-request-education.md)
- [<span data-ttu-id="05da2-158">Lokalizacja wniosku o rekrutację</span><span class="sxs-lookup"><span data-stu-id="05da2-158">Recruiting request location</span></span>](hr-admin-integration-ats-api-recruiting-request-location.md)

<span data-ttu-id="05da2-159">Zestawy opcji:</span><span class="sxs-lookup"><span data-stu-id="05da2-159">Option sets:</span></span>

- [<span data-ttu-id="05da2-160">Status zwolnienia z pracy</span><span class="sxs-lookup"><span data-stu-id="05da2-160">Job exempt status</span></span>](hr-admin-integration-ats-api-job-exempt-status.md)
- [<span data-ttu-id="05da2-161">Stan stanowiska dla wniosku o rekrutację</span><span class="sxs-lookup"><span data-stu-id="05da2-161">Recruiting request position status</span></span>](hr-admin-integration-ats-api-recruiting-request-position-status.md)
- [<span data-ttu-id="05da2-162">Stan wniosku o rekrutację</span><span class="sxs-lookup"><span data-stu-id="05da2-162">Recruiting request status</span></span>](hr-admin-integration-ats-api-recruiting-request-status.md)
- [<span data-ttu-id="05da2-163">Kategoria stanowisk prawnych</span><span class="sxs-lookup"><span data-stu-id="05da2-163">Regulatory job category</span></span>](hr-admin-integration-ats-api-regulatory-job-category.md)

## <a name="candidate-to-hire-and-related-entities-and-option-sets"></a><span data-ttu-id="05da2-164">Kandydat do pracy oraz powiązane jednostki i zestawy opcji</span><span class="sxs-lookup"><span data-stu-id="05da2-164">Candidate to hire and related entities and option sets</span></span>

<span data-ttu-id="05da2-165">Przykład kwerendy:</span><span class="sxs-lookup"><span data-stu-id="05da2-165">Example query:</span></span>

- [<span data-ttu-id="05da2-166">Przykład kwerendy dotyczącej kandydata do zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="05da2-166">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)

<span data-ttu-id="05da2-167">Jednostki:</span><span class="sxs-lookup"><span data-stu-id="05da2-167">Entities:</span></span>

- [<span data-ttu-id="05da2-168">Kandydat do zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="05da2-168">Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire.md)
- [<span data-ttu-id="05da2-169">Osoba</span><span class="sxs-lookup"><span data-stu-id="05da2-169">Person</span></span>](hr-admin-integration-ats-api-person.md)
- [<span data-ttu-id="05da2-170">Wykształcenie osoby</span><span class="sxs-lookup"><span data-stu-id="05da2-170">Person education</span></span>](hr-admin-integration-ats-api-person-education.md)
- [<span data-ttu-id="05da2-171">Doświadczenie zawodowe osoby</span><span class="sxs-lookup"><span data-stu-id="05da2-171">Person professional experience</span></span>](hr-admin-integration-ats-api-person-professional-experience.md)
- [<span data-ttu-id="05da2-172">Adres osoby</span><span class="sxs-lookup"><span data-stu-id="05da2-172">Person address</span></span>](hr-admin-integration-ats-api-person-address.md)
- [<span data-ttu-id="05da2-173">Osoba kontaktowa strony</span><span class="sxs-lookup"><span data-stu-id="05da2-173">Party contact</span></span>](hr-admin-integration-ats-api-party-contact.md)
- [<span data-ttu-id="05da2-174">Kwalifikacje osoby</span><span class="sxs-lookup"><span data-stu-id="05da2-174">Person skill</span></span>](hr-admin-integration-ats-api-person-skill.md)
- [<span data-ttu-id="05da2-175">Poziom oceniania</span><span class="sxs-lookup"><span data-stu-id="05da2-175">Rating level</span></span>](hr-admin-integration-ats-api-rating-level.md)
- [<span data-ttu-id="05da2-176">Certyfikat osoby</span><span class="sxs-lookup"><span data-stu-id="05da2-176">Person certificate</span></span>](hr-admin-integration-ats-api-person-certificate.md)
- [<span data-ttu-id="05da2-177">Typ certyfikatu</span><span class="sxs-lookup"><span data-stu-id="05da2-177">Certificate type</span></span>](hr-admin-integration-ats-api-certificate-type.md)
- [<span data-ttu-id="05da2-178">Kontrola osoby</span><span class="sxs-lookup"><span data-stu-id="05da2-178">Person screening</span></span>](hr-admin-integration-ats-api-person-screening.md)
- [<span data-ttu-id="05da2-179">Typy kontroli</span><span class="sxs-lookup"><span data-stu-id="05da2-179">Screening types</span></span>](hr-admin-integration-ats-api-screening-types.md)
- [<span data-ttu-id="05da2-180">Numer dokumentu identyfikacyjnego osoby</span><span class="sxs-lookup"><span data-stu-id="05da2-180">Person identification number</span></span>](hr-admin-integration-ats-api-person-identification-number.md)

<span data-ttu-id="05da2-181">Zestawy opcji:</span><span class="sxs-lookup"><span data-stu-id="05da2-181">Option sets:</span></span>

- [<span data-ttu-id="05da2-182">Wynik integracji kandydata</span><span class="sxs-lookup"><span data-stu-id="05da2-182">Applicant integration result</span></span>](hr-admin-integration-ats-api-applicant-integration-result.md)
- [<span data-ttu-id="05da2-183">Puste Tak Nie</span><span class="sxs-lookup"><span data-stu-id="05da2-183">Blank Yes No</span></span>](hr-admin-integration-ats-api-blank-yes-no.md)
- [<span data-ttu-id="05da2-184">Stan ukończenia</span><span class="sxs-lookup"><span data-stu-id="05da2-184">Completion status</span></span>](hr-admin-integration-ats-api-completion-status.md)
- [<span data-ttu-id="05da2-185">Typ kontaktu</span><span class="sxs-lookup"><span data-stu-id="05da2-185">Contact type</span></span>](hr-admin-integration-ats-api-contact-type.md)
- [<span data-ttu-id="05da2-186">Podstawa kredytu edukacyjnego</span><span class="sxs-lookup"><span data-stu-id="05da2-186">Education credit basis</span></span>](hr-admin-integration-ats-api-education-credit-basis.md)
- [<span data-ttu-id="05da2-187">Rodzaj</span><span class="sxs-lookup"><span data-stu-id="05da2-187">Gender</span></span>](hr-admin-integration-ats-api-gender.md)
- [<span data-ttu-id="05da2-188">Stan cywilny</span><span class="sxs-lookup"><span data-stu-id="05da2-188">Marital status</span></span>](hr-admin-integration-ats-api-marital-status.md)
- [<span data-ttu-id="05da2-189">Miesiące roku</span><span class="sxs-lookup"><span data-stu-id="05da2-189">Months of year</span></span>](hr-admin-integration-ats-api-months-of-year.md)
- [<span data-ttu-id="05da2-190">Nie, Tak</span><span class="sxs-lookup"><span data-stu-id="05da2-190">No Yes</span></span>](hr-admin-integration-ats-api-no-yes.md)
- [<span data-ttu-id="05da2-191">Jednostka okresu</span><span class="sxs-lookup"><span data-stu-id="05da2-191">Period unit</span></span>](hr-admin-integration-ats-api-period-unit.md)
- [<span data-ttu-id="05da2-192">Częstotliwość kontroli</span><span class="sxs-lookup"><span data-stu-id="05da2-192">Screening frequency</span></span>](hr-admin-integration-ats-api-screening-frequency.md)
- [<span data-ttu-id="05da2-193">Częstotliwość kontroli generowana na podstawie</span><span class="sxs-lookup"><span data-stu-id="05da2-193">Screening frequency generate from</span></span>](hr-admin-integration-ats-api-screening-frequency-generate-from.md)
- [<span data-ttu-id="05da2-194">Typ poziomu kwalifikacji</span><span class="sxs-lookup"><span data-stu-id="05da2-194">Skill level type</span></span>](hr-admin-integration-ats-api-skill-level-type.md)

## <a name="see-also"></a><span data-ttu-id="05da2-195">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="05da2-195">See also</span></span>

[<span data-ttu-id="05da2-196">Rekrutowanie kandydatów</span><span class="sxs-lookup"><span data-stu-id="05da2-196">Recruit job candidates</span></span>](hr-personnel-recruit.md)<br>
[<span data-ttu-id="05da2-197">Co to jest usługa Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="05da2-197">What is Microsoft Dataverse?</span></span>](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)<br>
[<span data-ttu-id="05da2-198">Użyj interfejsu API sieci Web Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="05da2-198">Use the Microsoft Dataverse Web API</span></span>](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/overview)<br>
[<span data-ttu-id="05da2-199">Tworzenie i aktualizowanie zestawów opcji przy użyciu interfejsu API sieci Web</span><span class="sxs-lookup"><span data-stu-id="05da2-199">Create and update option sets using the Web API</span></span>](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/create-update-optionsets)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]