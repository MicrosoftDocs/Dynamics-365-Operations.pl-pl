---
title: Administrowanie organizacją — strona główna
description: W tym temacie wymieniono zasoby, które pomogą w organizacji.
author: sericks007
manager: AnnBe
ms.date: 08/18/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 20421
ms.assetid: 7aa24a03-d172-47e9-81f8-ebd39e80bc60
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1c5db94aad99a6ec17a52aee4876d40912a95ce9
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560758"
---
# <a name="organization-administration-home-page"></a><span data-ttu-id="4c2b6-103">Administrowanie organizacją — strona główna</span><span class="sxs-lookup"><span data-stu-id="4c2b6-103">Organization administration home page</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4c2b6-104">Ta zawartość ułatwi użytkownikom zaawansowanym i administratorom skonfigurowanie systemu w celu płynnej i efektywnej pracy w organizacji i biznesie.</span><span class="sxs-lookup"><span data-stu-id="4c2b6-104">This topic points to content that will help power users and administrators configure the system to work smoothly and effectively for your organization and business.</span></span>

<span data-ttu-id="4c2b6-105">Większość zawartości wymienionej tutaj dotyczy funkcji w module **Administracja organizacyjna**.</span><span class="sxs-lookup"><span data-stu-id="4c2b6-105">Much of the content listed here applies to features in the **Organizational administration** module.</span></span> <span data-ttu-id="4c2b6-106">Istnieje jednak kilka zadań, takich jak tworzenie i używanie szablonu rekordu, które mogą zostać wykonane w dowolnym module, aby ułatwić organizacji bardziej efektywne działanie.</span><span class="sxs-lookup"><span data-stu-id="4c2b6-106">However, there are a couple of tasks, such as creating and using a record template, that can be performed in any module to help your organization run more efficiently.</span></span>

## <a name="number-sequences"></a><span data-ttu-id="4c2b6-107">Sekwencje identyfikatorów</span><span class="sxs-lookup"><span data-stu-id="4c2b6-107">Number sequences</span></span>

<span data-ttu-id="4c2b6-108">Sekwencje numerów są używane do generowania czytelnych, unikatowych identyfikatorów dla rekordów danych głównych i rekordów transakcji, które muszą mieć identyfikatory.</span><span class="sxs-lookup"><span data-stu-id="4c2b6-108">Number sequences are used to generate readable, unique identifiers for master data records and transaction records that require identifiers.</span></span> <span data-ttu-id="4c2b6-109">Rekord transakcji lub danych głównych, który wymaga identyfikatora, odnosi się do *odwołania*.</span><span class="sxs-lookup"><span data-stu-id="4c2b6-109">A master data record or transaction record that requires an identifier is referred to as a *reference*.</span></span> <span data-ttu-id="4c2b6-110">Aby można było tworzyć nowe rekordy dla odwołania, należy ustawić sekwencję numerów i skojarzyć je z odwołaniem.</span><span class="sxs-lookup"><span data-stu-id="4c2b6-110">Before you can create new records for a reference, you must set up a number sequence and associate it with the reference.</span></span>

- [<span data-ttu-id="4c2b6-111">Omówienie sekwencji identyfikatorów</span><span class="sxs-lookup"><span data-stu-id="4c2b6-111">Number sequences overview</span></span>](number-sequence-overview.md)
- <span data-ttu-id="4c2b6-112">[Konfigurowanie sekwencji numeracji za pomocą kreatora](tasks/set-up-number-sequences-wizard.md) (Przewodnik po zadaniu)</span><span class="sxs-lookup"><span data-stu-id="4c2b6-112">[Set up number sequences using a wizard](tasks/set-up-number-sequences-wizard.md) (Task guide)</span></span>
- <span data-ttu-id="4c2b6-113">[Konfigurowanie indywidualnych sekwencji identyfikatorów](tasks/set-up-number-sequences-individual-basis.md) (przewodnik po zadaniu)</span><span class="sxs-lookup"><span data-stu-id="4c2b6-113">[Set up number sequences on an individual basis](tasks/set-up-number-sequences-individual-basis.md) (Task guide)</span></span>

## <a name="organizations"></a><span data-ttu-id="4c2b6-114">Organizacje</span><span class="sxs-lookup"><span data-stu-id="4c2b6-114">Organizations</span></span>

<span data-ttu-id="4c2b6-115">Organizacja to grupa osób, które pracują razem, aby przeprowadzić proces biznesowy lub osiągnąć cel.</span><span class="sxs-lookup"><span data-stu-id="4c2b6-115">An organization is a group of people who are working together to carry out a business process or achieve a goal.</span></span> <span data-ttu-id="4c2b6-116">Hierarchie organizacyjne reprezentują relacje między organizacjami, które tworzą firmę.</span><span class="sxs-lookup"><span data-stu-id="4c2b6-116">Organizational hierarchies represent the relationships between the organizations that make up your business.</span></span>

<span data-ttu-id="4c2b6-117">Przed skonfigurowaniem organizacji i hierarchii organizacyjnych upewnij się, że masz plan dotyczący modelowania firmy.</span><span class="sxs-lookup"><span data-stu-id="4c2b6-117">Before you set up organizations and organization hierarchies, make sure that you plan how your business will be modeled.</span></span> <span data-ttu-id="4c2b6-118">Model organizacyjny ma znaczny wpływ na implementację i na procesy biznesowe.</span><span class="sxs-lookup"><span data-stu-id="4c2b6-118">The organization model has a significant effect on implementation and business processes.</span></span>

- [<span data-ttu-id="4c2b6-119">Omówienie organizacji i hierarchii organizacyjnych</span><span class="sxs-lookup"><span data-stu-id="4c2b6-119">Organizations and organizational hierarchies overview</span></span>](organizations-organizational-hierarchies.md)
- [<span data-ttu-id="4c2b6-120">Planowanie hierarchii organizacyjnej</span><span class="sxs-lookup"><span data-stu-id="4c2b6-120">Plan your organizational hierarchy</span></span>](plan-organizational-hierarchy.md)
- <span data-ttu-id="4c2b6-121">[Tworzenie hierarchii organizacyjnej](tasks/create-organization-hierarchy.md) (przewodnik po zadaniu)</span><span class="sxs-lookup"><span data-stu-id="4c2b6-121">[Create an organization hierarchy](tasks/create-organization-hierarchy.md) (Task guide)</span></span>
- <span data-ttu-id="4c2b6-122">[Tworzenie firmy](tasks/create-legal-entity.md) (przewodnik po zadaniu)</span><span class="sxs-lookup"><span data-stu-id="4c2b6-122">[Create a legal entity](tasks/create-legal-entity.md) (Task guide)</span></span>
- <span data-ttu-id="4c2b6-123">[Tworzenie jednostki operacyjnej](tasks/create-operating-unit.md) (przewodnik po zadaniu)</span><span class="sxs-lookup"><span data-stu-id="4c2b6-123">[Create an operating unit](tasks/create-operating-unit.md) (Task guide)</span></span>

## <a name="address-books"></a><span data-ttu-id="4c2b6-124">Książki adresowe</span><span class="sxs-lookup"><span data-stu-id="4c2b6-124">Address books</span></span>

<span data-ttu-id="4c2b6-125">Globalna książka adresowa to scentralizowane repozytorium danych głównych, które musi być przechowywane dla wszystkich osób wewnętrznych i zewnętrznych, z którymi współpracuje firma.</span><span class="sxs-lookup"><span data-stu-id="4c2b6-125">The global address book is a centralized repository for master data that must be stored for all internal and external persons and organizations that the company interacts with.</span></span> <span data-ttu-id="4c2b6-126">Dane skojarzone z rekordami stron obejmują nazwę i adres oraz informacje kontaktowe.</span><span class="sxs-lookup"><span data-stu-id="4c2b6-126">The data that is associated with party records includes the party's name, address, and contact information.</span></span>

<span data-ttu-id="4c2b6-127">Po utworzeniu w globalnej książki adresowej można utworzyć dodatkowe książki adresowe, np. oddzielne książki adresowe dla każdej firmy w organizacji lub dla każdego wiersza biznesowego.</span><span class="sxs-lookup"><span data-stu-id="4c2b6-127">After you create the global address book, you can create additional address books as you require, such as a separate address book for each company in your organization or for each line of business.</span></span>

- [<span data-ttu-id="4c2b6-128">Omówienie globalnej książki adresowej</span><span class="sxs-lookup"><span data-stu-id="4c2b6-128">Global address book overview</span></span>](overview-global-address-book.md)
- [<span data-ttu-id="4c2b6-129">Planowanie globalnej książki adresowej i innych książek adresowych</span><span class="sxs-lookup"><span data-stu-id="4c2b6-129">Plan for the global address book and other address books</span></span>](plan-configuration-global-address-book-additional-address-books.md)
- [<span data-ttu-id="4c2b6-130">Konfigurowanie globalnej książki adresowej</span><span class="sxs-lookup"><span data-stu-id="4c2b6-130">Configure the global address book</span></span>](tasks/configure-global-address-book.md)
- [<span data-ttu-id="4c2b6-131">Książki adresowe — często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="4c2b6-131">Address books FAQ</span></span>](qa-address-books.md)

## <a name="workflow"></a><span data-ttu-id="4c2b6-132">Przepływ pracy</span><span class="sxs-lookup"><span data-stu-id="4c2b6-132">Workflow</span></span>

<span data-ttu-id="4c2b6-133">Przepływ pracy to system, którego można używać do tworzenia pojedynczych przepływów pracy, czyli procesów biznesowych.</span><span class="sxs-lookup"><span data-stu-id="4c2b6-133">Workflow is a system that you can use to create individual workflows, or business processes.</span></span> <span data-ttu-id="4c2b6-134">Utworzenie przepływu pracy definiuje sposób przepływu lub przenoszenia dokumentu przez system, pokazując, kto musi wykonać zadanie, podjąć decyzję lub zatwierdzić dokument.</span><span class="sxs-lookup"><span data-stu-id="4c2b6-134">When you create a workflow, you specify how a document flows, or moves, through the system by showing who must complete a task, make a decision, or approve a document.</span></span>

- [<span data-ttu-id="4c2b6-135">Omówienie systemu przepływów pracy</span><span class="sxs-lookup"><span data-stu-id="4c2b6-135">Workflow system overview</span></span>](overview-workflow-system.md)
- [<span data-ttu-id="4c2b6-136">Elementy przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="4c2b6-136">Workflow elements</span></span>](workflow-elements.md)
- [<span data-ttu-id="4c2b6-137">Akcje w procesach zatwierdzania w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="4c2b6-137">Actions in workflow approval processes</span></span>](workflow-actions.md)
- [<span data-ttu-id="4c2b6-138">Omówienie tworzenia przepływów pracy</span><span class="sxs-lookup"><span data-stu-id="4c2b6-138">Create workflows overview</span></span>](create-workflow.md)

## <a name="electronic-signatures"></a><span data-ttu-id="4c2b6-139">Podpisy elektroniczne</span><span class="sxs-lookup"><span data-stu-id="4c2b6-139">Electronic signatures</span></span>

<span data-ttu-id="4c2b6-140">Podpis elektroniczny potwierdza tożsamość osoby, która ma rozpocząć lub zatwierdzić jakiś proces obliczeniowy.</span><span class="sxs-lookup"><span data-stu-id="4c2b6-140">An electronic signature confirms the identity of a person who is about to start or approve a computing process.</span></span> <span data-ttu-id="4c2b6-141">W przypadku niektórych branż podpis elektroniczny jest tak samo prawnie wiążący jak podpis odręczny.</span><span class="sxs-lookup"><span data-stu-id="4c2b6-141">In some industries, an electronic signature is as legally binding as a handwritten signature.</span></span> <span data-ttu-id="4c2b6-142">Podpisy elektroniczne są wymagane przepisami w przypadku kilku branż regulowanych, takich jak przemysł farmaceutyczny, spożywczy oraz lotniczy i obronny.</span><span class="sxs-lookup"><span data-stu-id="4c2b6-142">Electronic signatures are a regulations compliance requirement for several regulated industries, such as pharmaceuticals, food and beverage, and aerospace and defense.</span></span>

<span data-ttu-id="4c2b6-143">Można używać podpisów elektronicznych w przypadku procesów biznesowych o podstawowym znaczeniu.</span><span class="sxs-lookup"><span data-stu-id="4c2b6-143">You can use electronic signatures for critical business processes.</span></span> <span data-ttu-id="4c2b6-144">Niektóre procesy mają wbudowane możliwości podpisu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="4c2b6-144">Some processes have built-in electronic signature capabilities.</span></span> <span data-ttu-id="4c2b6-145">Można również tworzyć niestandardowe wymagania dotyczące podpisu cyfrowego dla dowolnej tabeli lub pola bazy danych.</span><span class="sxs-lookup"><span data-stu-id="4c2b6-145">You can also create custom signature requirements for any database table and field.</span></span>

- [<span data-ttu-id="4c2b6-146">Omówienie podpisów elektronicznych</span><span class="sxs-lookup"><span data-stu-id="4c2b6-146">Electronic signatures overview</span></span>](electronic-signature-overview.md)
- <span data-ttu-id="4c2b6-147">[Konfigurowanie podpisów elektronicznych](tasks/set-up-electronic-signatures.md) (przewodnik po zadaniu)</span><span class="sxs-lookup"><span data-stu-id="4c2b6-147">[Set up electronic signatures](tasks/set-up-electronic-signatures.md) (Task guide)</span></span>

## <a name="case-management"></a><span data-ttu-id="4c2b6-148">Zarządzanie sprawami</span><span class="sxs-lookup"><span data-stu-id="4c2b6-148">Case management</span></span>

<span data-ttu-id="4c2b6-149">Planowanie, śledzenie i analizowanie spraw powoduje, że użytkownik może tworzyć wydajne rozwiązania, które mogą być używane dla podobnych spraw.</span><span class="sxs-lookup"><span data-stu-id="4c2b6-149">By planning, tracking, and analyzing cases, you can develop efficient resolutions that can be used for similar issues.</span></span> <span data-ttu-id="4c2b6-150">Na przykład, gdy przedstawiciele obsługi klienta lub specjaliści ds. personalnych tworzą sprawy, znajdują informacje w artykułach merytorycznych, ułatwiające pracę ze sprawami i ich efektywnego rozwiązywania.</span><span class="sxs-lookup"><span data-stu-id="4c2b6-150">For example, when customer service representatives or Human Resources generalists create cases, they can find information in knowledge articles to help them work with or resolve a case more efficiently.</span></span>

- [<span data-ttu-id="4c2b6-151">Omówienie zarządzania sprawami</span><span class="sxs-lookup"><span data-stu-id="4c2b6-151">Case management overview</span></span>](cases.md)
- [<span data-ttu-id="4c2b6-152">Planowanie kategorii zabezpieczeń, procesów zarządzania sprawami i kategorii spraw</span><span class="sxs-lookup"><span data-stu-id="4c2b6-152">Plan case category security, case processes, and case categories</span></span>](plan-case-management.md)

## <a name="record-templates"></a><span data-ttu-id="4c2b6-153">Szablony rekordów</span><span class="sxs-lookup"><span data-stu-id="4c2b6-153">Record templates</span></span>

<span data-ttu-id="4c2b6-154">Szablony rekordów pomagają w szybkim tworzeniu rekordów w systemie.</span><span class="sxs-lookup"><span data-stu-id="4c2b6-154">Record templates can help you to create records more quickly.</span></span> <span data-ttu-id="4c2b6-155">Można utworzyć szablon rekordu, tak aby wartości pól, które są często używane, nie musiały być jawnie wprowadzane dla każdego nowego rekordu.</span><span class="sxs-lookup"><span data-stu-id="4c2b6-155">You can create a record template so that field values that are used often do not have to be entered explicitly for each new record.</span></span>

- [<span data-ttu-id="4c2b6-156">Omówienie szablonów rekordów</span><span class="sxs-lookup"><span data-stu-id="4c2b6-156">Record templates overview</span></span>](record-templates.md)
- <span data-ttu-id="4c2b6-157">[Tworzenie szablonu rekordu w celu ułatwienia wprowadzania danych](../../dev-itpro/data-entities/tasks/create-record-template-facilitate-data-entry.md) (przewodnik zadania)</span><span class="sxs-lookup"><span data-stu-id="4c2b6-157">[Create a record template to facilitate data entry](../../dev-itpro/data-entities/tasks/create-record-template-facilitate-data-entry.md) (Task guide)</span></span>
- <span data-ttu-id="4c2b6-158">[Używanie szablonu rekordu do tworzenia nowego rekordu](../../dev-itpro/data-entities/tasks/use-record-template-new-record.md) (przewodnik zadania)</span><span class="sxs-lookup"><span data-stu-id="4c2b6-158">[Use record template to create a new record](../../dev-itpro/data-entities/tasks/use-record-template-new-record.md) (Task guide)</span></span>

## <a name="general-organization-administration"></a><span data-ttu-id="4c2b6-159">Ogólny administrator organizacji</span><span class="sxs-lookup"><span data-stu-id="4c2b6-159">General organization administration</span></span>

- <span data-ttu-id="4c2b6-160">[Zmienianie transparentu lub logo](../get-started/tasks/change-banner-or-logo.md) (przewodnik po zadaniu)</span><span class="sxs-lookup"><span data-stu-id="4c2b6-160">[Change the banner or logo](../get-started/tasks/change-banner-or-logo.md) (Task guide)</span></span>
- [<span data-ttu-id="4c2b6-161">Konfigurowanie zarządzania dokumentami</span><span class="sxs-lookup"><span data-stu-id="4c2b6-161">Configure document management</span></span>](configure-document-management.md)
- [<span data-ttu-id="4c2b6-162">Konfigurowanie i wysyłanie wiadomości e-mail</span><span class="sxs-lookup"><span data-stu-id="4c2b6-162">Configure and send email</span></span>](configure-email.md)
- [<span data-ttu-id="4c2b6-163">Dane dotyczące daty/godziny i strefy czasowe</span><span class="sxs-lookup"><span data-stu-id="4c2b6-163">Date/time data and time zones</span></span>](date-time-zones.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]