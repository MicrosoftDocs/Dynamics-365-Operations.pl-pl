---
title: Synchronizowanie faktur dotyczących umowy w rozwiązaniu Field Service z fakturami niezależnymi w rozwiązaniu Supply Chain Management
description: W tym temacie omówiono szablony i podstawowe zadania, które są używane do synchronizowania faktur umowy w Dynamics 365 Field Service z fakturami niezależnymi w Dynamics 365 Supply Chain Management.
author: ChristianRytt
ms.date: 04/10/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: f3066741781bd9058e09d7f577a35df4c9b453d4
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819215"
---
# <a name="synchronize-agreement-invoices-in-field-service-to-free-text-invoices-in-supply-chain-management"></a><span data-ttu-id="e8c69-103">Synchronizowanie faktur dotyczących umowy w rozwiązaniu Field Service z fakturami niezależnymi w rozwiązaniu Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="e8c69-103">Synchronize agreement invoices in Field Service to free text invoices in Supply Chain Management</span></span>

[!include[banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="e8c69-104">W tym temacie omówiono szablony i podstawowe zadania, które są używane do synchronizowania faktur umowy w Dynamics 365 Field Service z fakturami niezależnymi w Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e8c69-104">This topic discusses the templates and underlying tasks that are used to synchronize agreement invoices in Dynamics 365 Field Service to free text invoices in Dynamics 365 Supply Chain Management.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="e8c69-105">Szablony i zadania</span><span class="sxs-lookup"><span data-stu-id="e8c69-105">Templates and tasks</span></span>

<span data-ttu-id="e8c69-106">Następujący szablon i podstawowe zadania są używane do wykonywania synchronizacji faktur za umowy w aplikacji Field Service z fakturami niezależnymi w aplikacji Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e8c69-106">The following template and underlying tasks are used to run synchronization of agreement invoices from Field Service to free text invoices in Supply Chain Management.</span></span>

<span data-ttu-id="e8c69-107">**Nazwa szablonu w integracji danych**</span><span class="sxs-lookup"><span data-stu-id="e8c69-107">**Name of the template in Data integration**</span></span>

- <span data-ttu-id="e8c69-108">Faktury za umowy (rozwiązanie Field Service do Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="e8c69-108">Agreement invoices (Field Service to Supply Chain Management)</span></span>

<span data-ttu-id="e8c69-109">**Nazwy zadań w projekcie integracji danych**</span><span class="sxs-lookup"><span data-stu-id="e8c69-109">**Names of the tasks in the Data integration project**</span></span>

- <span data-ttu-id="e8c69-110">Nagłówki faktur</span><span class="sxs-lookup"><span data-stu-id="e8c69-110">Invoice headers</span></span>
- <span data-ttu-id="e8c69-111">Wiersze faktury</span><span class="sxs-lookup"><span data-stu-id="e8c69-111">Invoice lines</span></span>

<span data-ttu-id="e8c69-112">Następująca synchronizacja jest wymagana, zanim będzie można zsynchronizować faktury za umowy:</span><span class="sxs-lookup"><span data-stu-id="e8c69-112">The following synchronization is required before synchronization of agreement invoices can occur:</span></span>

- <span data-ttu-id="e8c69-113">Konta (Sales to Supply Chain Management) — bezpośrednie</span><span class="sxs-lookup"><span data-stu-id="e8c69-113">Accounts (Sales to Supply Chain Management) – Direct</span></span>

## <a name="entity-set"></a><span data-ttu-id="e8c69-114">Zestaw jednostek</span><span class="sxs-lookup"><span data-stu-id="e8c69-114">Entity set</span></span>

| <span data-ttu-id="e8c69-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="e8c69-115">Field Service</span></span>  | <span data-ttu-id="e8c69-116">Zarządzanie łańcuchem dostaw</span><span class="sxs-lookup"><span data-stu-id="e8c69-116">Supply Chain Management</span></span>                 |
|----------------|----------------------------------------|
| <span data-ttu-id="e8c69-117">faktury</span><span class="sxs-lookup"><span data-stu-id="e8c69-117">invoices</span></span>       | <span data-ttu-id="e8c69-118">Nagłówki faktur niezależnych dla odbiorców w usłudze Dataverse</span><span class="sxs-lookup"><span data-stu-id="e8c69-118">Dataverse customer free text invoice headers</span></span> |
| <span data-ttu-id="e8c69-119">invoicedetails</span><span class="sxs-lookup"><span data-stu-id="e8c69-119">invoicedetails</span></span> | <span data-ttu-id="e8c69-120">Wiersze faktur niezależnych dla odbiorców w usłudze Dataverse</span><span class="sxs-lookup"><span data-stu-id="e8c69-120">Dataverse customer free text invoice lines</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="e8c69-121">Przepływ jednostek</span><span class="sxs-lookup"><span data-stu-id="e8c69-121">Entity flow</span></span>

<span data-ttu-id="e8c69-122">Faktury tworzone na podstawie umowy w programie Field Service mogą być synchronizowane z programem Supply Chain Management za pomocą projektu integracji danych realizowanego w usłudze Microsoft Dataverse (CDS).</span><span class="sxs-lookup"><span data-stu-id="e8c69-122">Invoices that are created from an agreement in Field Service can be synchronized to Supply Chain Management via a Microsoft Dataverse Data integration project.</span></span> <span data-ttu-id="e8c69-123">Aktualizacje tych faktur będą synchronizowane z fakturami niezależnymi w programie Supply Chain Management, jeśli faktury niezależne mają stan księgowania **W trakcie przetwarzania**.</span><span class="sxs-lookup"><span data-stu-id="e8c69-123">Updates to these invoices will be synchronized to the free text invoices in Supply Chain Management if the accounting status of the free text invoices is **In process**.</span></span> <span data-ttu-id="e8c69-124">Po zaksięgowaniu faktur niezależnych w programie Supply Chain Management i zaktualizowaniu stanu księgowania na **Zakończone** nie będzie można synchronizować aktualizacji z programu Field Service.</span><span class="sxs-lookup"><span data-stu-id="e8c69-124">After the free text invoices are posted in Supply Chain Management, and the accounting status is updated to **Completed**, you can no longer synchronize updates from Field Service.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="e8c69-125">Rozwiązanie CRM Field Service</span><span class="sxs-lookup"><span data-stu-id="e8c69-125">Field Service CRM solution</span></span>

<span data-ttu-id="e8c69-126">Do tabeli **Faktury** dodano kolumnę **Zawiera wiersze ze źródłem umowy**.</span><span class="sxs-lookup"><span data-stu-id="e8c69-126">The **Has Lines With Agreement Origin** column has been added to the **Invoice** table.</span></span> <span data-ttu-id="e8c69-127">Ta kolumna pomaga zagwarantować, że są synchronizowane tylko faktury utworzone na podstawie umowy.</span><span class="sxs-lookup"><span data-stu-id="e8c69-127">This column helps guarantee that only invoices that are created from an agreement are synchronized.</span></span> <span data-ttu-id="e8c69-128">Wartością jest **prawda**, jeśli faktura zawiera co najmniej jeden wiersz faktury pochodzący z umowy.</span><span class="sxs-lookup"><span data-stu-id="e8c69-128">The value is **true** if the invoice contains at least one invoice line that originates from an agreement.</span></span>

<span data-ttu-id="e8c69-129">Do tabeli **Wiersz faktury** dodano kolumnę **Zawiera źródło umowy**.</span><span class="sxs-lookup"><span data-stu-id="e8c69-129">The **Has Agreement Origin** column has been added to the **Invoice Line** table.</span></span> <span data-ttu-id="e8c69-130">Ta kolumna pomaga zagwarantować, że są synchronizowane tylko wiersze faktury utworzone na podstawie umowy.</span><span class="sxs-lookup"><span data-stu-id="e8c69-130">This column helps guarantee that only invoice lines that are created from an agreement are synchronized.</span></span> <span data-ttu-id="e8c69-131">Wartością jest **prawda**, jeżeli wiersz faktury pochodzi z umowy.</span><span class="sxs-lookup"><span data-stu-id="e8c69-131">The value is **true** if the invoice line originates from an agreement.</span></span>

<span data-ttu-id="e8c69-132">Pole **Data faktury** jest wymagane w aplikacji Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e8c69-132">**Invoice date** is a mandatory field in Supply Chain Management.</span></span> <span data-ttu-id="e8c69-133">W związku z tym kolumna musi mieć wartość w programie Field Service, zanim będzie mogła nastąpić synchronizacja.</span><span class="sxs-lookup"><span data-stu-id="e8c69-133">Therefore, the column must have a value in Field Service before synchronization occurs.</span></span> <span data-ttu-id="e8c69-134">Aby spełnić ten wymóg, dodano następującą logikę:</span><span class="sxs-lookup"><span data-stu-id="e8c69-134">To meet this requirement, the following logic is added:</span></span>

- <span data-ttu-id="e8c69-135">Jeśli kolumna **Data faktury** jest puste w tabeli **Faktura** (tzn. jeśli nie ma wartości), jest w nim ustawiana bieżąca data podczas dodawania wiersza faktury pochodzącego z umowy.</span><span class="sxs-lookup"><span data-stu-id="e8c69-135">If the **Invoice Date** column is blank on the **Invoice** table (that is, if it has no value), it's set to the current date when an invoice line that originates from an agreement is added.</span></span>
- <span data-ttu-id="e8c69-136">Użytkownik może zmienić wartość w kolumnie **Data faktury**.</span><span class="sxs-lookup"><span data-stu-id="e8c69-136">The user can change the **Invoice Date** column.</span></span> <span data-ttu-id="e8c69-137">Jednak gdy użytkownik próbuje zapisać fakturę pochodzącą z umowy, widzi błąd procesu biznesowego, jeśli kolumna **Data faktury** jest pusta na fakturze.</span><span class="sxs-lookup"><span data-stu-id="e8c69-137">However, when the user tries to save an invoice that originates from an agreement, he or she receives a business process error if the **Invoice Date** column is blank on the invoice.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="e8c69-138">Wymagania wstępne i ustawienia mapowania</span><span class="sxs-lookup"><span data-stu-id="e8c69-138">Prerequisites and mapping setup</span></span>

### <a name="in-supply-chain-management"></a><span data-ttu-id="e8c69-139">W Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="e8c69-139">In Supply Chain Management</span></span>

<span data-ttu-id="e8c69-140">Na potrzeby integracji należy skonfigurować pochodzenie faktury, tak aby w programie Supply Chain Management odróżniać faktury niezależne utworzone na podstawie faktur za umowy w programie Field Service.</span><span class="sxs-lookup"><span data-stu-id="e8c69-140">An invoice origin must be set up for the integration, to distinguish the free text invoices in Supply Chain Management that are created from agreement invoices in Field Service.</span></span> <span data-ttu-id="e8c69-141">Gdy faktura ma pochodzenie typu **Integracja faktury dotyczącej umowy**, pole **Zewnętrzny numer faktury** jest wyświetlane w nagłówku **Faktura sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="e8c69-141">When an invoice has an invoice origin of the **Agreement invoice integration** type, the **External invoice number** field is shown on the **Sales invoice** header.</span></span>

<span data-ttu-id="e8c69-142">Informacje z pola **Zewnętrzny numer faktury** nie tylko pojawiają się w nagłówku faktury, ale mogą również pomóc zagwarantować, że faktury tworzone na podstawie faktur za umowy w programie Field Service są odfiltrowywane podczas synchronizacji faktur między programami Supply Chain Management i Field Service.</span><span class="sxs-lookup"><span data-stu-id="e8c69-142">Besides appearing on the invoice header, the **External invoice number** information can be used to help guarantee that invoices that are created from Field Service agreement invoices are filtered out during invoice synchronization from Supply Chain Management to Field Service.</span></span>

1. <span data-ttu-id="e8c69-143">Wybierz kolejno opcje **Rozrachunki z odbiorcami** \> **Ustawienia** \> **Kody pochodzenia faktur**.</span><span class="sxs-lookup"><span data-stu-id="e8c69-143">Go to **Accounts receivable** \> **Setup** \> **Invoice origin codes**.</span></span>
2. <span data-ttu-id="e8c69-144">Wybierz opcję **Nowy**, aby utworzyć nowe pochodzenie faktury.</span><span class="sxs-lookup"><span data-stu-id="e8c69-144">Select **New** to create a new invoice origin.</span></span>
3. <span data-ttu-id="e8c69-145">W polu **Pochodzenie faktury** nadaj nazwę pochodzeniu faktury, taką jak **FS**.</span><span class="sxs-lookup"><span data-stu-id="e8c69-145">In the **Invoice origin** field, enter a name for the invoice origin, such as **FS**.</span></span>
4. <span data-ttu-id="e8c69-146">W polu **Opis** wprowadź opis, taki jak **Faktura za umowę w programie Field Service**.</span><span class="sxs-lookup"><span data-stu-id="e8c69-146">In the **Description** field, enter a description, such as **Field Service Agreement Invoice**.</span></span>
5. <span data-ttu-id="e8c69-147">Zaznacz pole wyboru **Przypisanie typu pochodzenia**.</span><span class="sxs-lookup"><span data-stu-id="e8c69-147">Select the **Origin type assignment** check box.</span></span>
6. <span data-ttu-id="e8c69-148">W polu **Typ pochodzenia faktury** ustaw wartość **Integracja faktury dotyczącej umowy**.</span><span class="sxs-lookup"><span data-stu-id="e8c69-148">Set the **Invoice origin type** field to **Agreement invoice integration**.</span></span>
7. <span data-ttu-id="e8c69-149">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="e8c69-149">Select **Save**.</span></span>

### <a name="in-the-data-integration-project"></a><span data-ttu-id="e8c69-150">W projekcie integracji danych</span><span class="sxs-lookup"><span data-stu-id="e8c69-150">In the Data Integration project</span></span>

<span data-ttu-id="e8c69-151">Zadanie: **Wiersze faktury**</span><span class="sxs-lookup"><span data-stu-id="e8c69-151">Task: **Invoice lines**</span></span>  

<span data-ttu-id="e8c69-152">Upewnij się, że wartość domyślna pola **Wartość wyświetlana konta głównego** w programie Supply Chain Management została zaktualizowana i jest zgodna z żądaną wartością.</span><span class="sxs-lookup"><span data-stu-id="e8c69-152">Make sure that the default value for the Supply Chain Management field **Main Account Display Value** is updated to match the desired value.</span></span>

<span data-ttu-id="e8c69-153">Wartość domyślna w szablonie to **401100**.</span><span class="sxs-lookup"><span data-stu-id="e8c69-153">The default template value is **401100**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="e8c69-154">Mapowanie szablonu w integracji danych</span><span class="sxs-lookup"><span data-stu-id="e8c69-154">Template mapping in Data integration</span></span>

<span data-ttu-id="e8c69-155">Na poniższych ilustracjach pokazano mapowanie szablonu w narzędziu Integracja danych.</span><span class="sxs-lookup"><span data-stu-id="e8c69-155">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="agreement-invoices-field-service-to-supply-chain-management-invoice-headers"></a><span data-ttu-id="e8c69-156">Faktury za umowy (rozwiązanie Field Service do Supply Chain Management): Nagłówki faktur</span><span class="sxs-lookup"><span data-stu-id="e8c69-156">Agreement invoices (Field Service to Supply Chain Management): Invoice headers</span></span>

<span data-ttu-id="e8c69-157">[![Mapowanie szablonu w integracji danych](./media/FSFreeTextInvoice1.png)](./media/FSFreeTextInvoice1.png)</span><span class="sxs-lookup"><span data-stu-id="e8c69-157">[![Template mapping in Data integration](./media/FSFreeTextInvoice1.png)](./media/FSFreeTextInvoice1.png)</span></span>

### <a name="agreement-invoices-field-service-to-supply-chain-management-invoice-lines"></a><span data-ttu-id="e8c69-158">Faktury za umowy (rozwiązanie Field Service do Supply Chain Management): Wiersze faktur</span><span class="sxs-lookup"><span data-stu-id="e8c69-158">Agreement invoices (Field Service to Supply Chain Management): Invoice lines</span></span>

<span data-ttu-id="e8c69-159">[![Mapowanie szablonu w integracji danych](./media/FSFreeTextInvoice2.png)](./media/FSFreeTextInvoice2.png)</span><span class="sxs-lookup"><span data-stu-id="e8c69-159">[![Template mapping in Data integration](./media/FSFreeTextInvoice2.png)](./media/FSFreeTextInvoice2.png)</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]