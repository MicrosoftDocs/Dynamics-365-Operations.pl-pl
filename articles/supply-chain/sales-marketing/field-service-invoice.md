---
title: Synchronizowanie faktur dotyczących umowy w rozwiązaniu Field Service z fakturami niezależnymi w rozwiązaniu Supply Chain Management
description: W tym temacie omówiono szablony i podstawowe zadania, które są używane do synchronizowania faktur umowy w Dynamics 365 Field Service z fakturami niezależnymi w Dynamics 365 Supply Chain Management.
author: ChristianRytt
manager: tfehr
ms.date: 04/10/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: f1790366cebf317472bc1ef9a5ecd2a19fe755d3
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980838"
---
# <a name="synchronize-agreement-invoices-in-field-service-to-free-text-invoices-in-supply-chain-management"></a><span data-ttu-id="15d15-103">Synchronizowanie faktur dotyczących umowy w rozwiązaniu Field Service z fakturami niezależnymi w rozwiązaniu Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="15d15-103">Synchronize agreement invoices in Field Service to free text invoices in Supply Chain Management</span></span>

[!include[banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="15d15-104">W tym temacie omówiono szablony i podstawowe zadania, które są używane do synchronizowania faktur umowy w Dynamics 365 Field Service z fakturami niezależnymi w Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="15d15-104">This topic discusses the templates and underlying tasks that are used to synchronize agreement invoices in Dynamics 365 Field Service to free text invoices in Dynamics 365 Supply Chain Management.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="15d15-105">Szablony i zadania</span><span class="sxs-lookup"><span data-stu-id="15d15-105">Templates and tasks</span></span>

<span data-ttu-id="15d15-106">Następujący szablon i podstawowe zadania są używane do wykonywania synchronizacji faktur za umowy w aplikacji Field Service z fakturami niezależnymi w aplikacji Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="15d15-106">The following template and underlying tasks are used to run synchronization of agreement invoices from Field Service to free text invoices in Supply Chain Management.</span></span>

<span data-ttu-id="15d15-107">**Nazwa szablonu w integracji danych**</span><span class="sxs-lookup"><span data-stu-id="15d15-107">**Name of the template in Data integration**</span></span>

- <span data-ttu-id="15d15-108">Faktury za umowy (rozwiązanie Field Service do Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="15d15-108">Agreement invoices (Field Service to Supply Chain Management)</span></span>

<span data-ttu-id="15d15-109">**Nazwy zadań w projekcie integracji danych**</span><span class="sxs-lookup"><span data-stu-id="15d15-109">**Names of the tasks in the Data integration project**</span></span>

- <span data-ttu-id="15d15-110">Nagłówki faktur</span><span class="sxs-lookup"><span data-stu-id="15d15-110">Invoice headers</span></span>
- <span data-ttu-id="15d15-111">Wiersze faktury</span><span class="sxs-lookup"><span data-stu-id="15d15-111">Invoice lines</span></span>

<span data-ttu-id="15d15-112">Następująca synchronizacja jest wymagana, zanim będzie można zsynchronizować faktury za umowy:</span><span class="sxs-lookup"><span data-stu-id="15d15-112">The following synchronization is required before synchronization of agreement invoices can occur:</span></span>

- <span data-ttu-id="15d15-113">Konta (Sales to Supply Chain Management) — bezpośrednie</span><span class="sxs-lookup"><span data-stu-id="15d15-113">Accounts (Sales to Supply Chain Management) – Direct</span></span>

## <a name="entity-set"></a><span data-ttu-id="15d15-114">Zestaw jednostek</span><span class="sxs-lookup"><span data-stu-id="15d15-114">Entity set</span></span>

| <span data-ttu-id="15d15-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="15d15-115">Field Service</span></span>  | <span data-ttu-id="15d15-116">Zarządzanie łańcuchem dostaw</span><span class="sxs-lookup"><span data-stu-id="15d15-116">Supply Chain Management</span></span>                 |
|----------------|----------------------------------------|
| <span data-ttu-id="15d15-117">faktury</span><span class="sxs-lookup"><span data-stu-id="15d15-117">invoices</span></span>       | <span data-ttu-id="15d15-118">Nagłówki faktur niezależnych dla odbiorców w usłudze Dataverse</span><span class="sxs-lookup"><span data-stu-id="15d15-118">Dataverse customer free text invoice headers</span></span> |
| <span data-ttu-id="15d15-119">invoicedetails</span><span class="sxs-lookup"><span data-stu-id="15d15-119">invoicedetails</span></span> | <span data-ttu-id="15d15-120">Wiersze faktur niezależnych dla odbiorców w usłudze Dataverse</span><span class="sxs-lookup"><span data-stu-id="15d15-120">Dataverse customer free text invoice lines</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="15d15-121">Przepływ jednostek</span><span class="sxs-lookup"><span data-stu-id="15d15-121">Entity flow</span></span>

<span data-ttu-id="15d15-122">Faktury tworzone na podstawie umowy w programie Field Service mogą być synchronizowane z programem Supply Chain Management za pomocą projektu integracji danych realizowanego w usłudze Microsoft Dataverse (CDS).</span><span class="sxs-lookup"><span data-stu-id="15d15-122">Invoices that are created from an agreement in Field Service can be synchronized to Supply Chain Management via a Microsoft Dataverse Data integration project.</span></span> <span data-ttu-id="15d15-123">Aktualizacje tych faktur będą synchronizowane z fakturami niezależnymi w programie Supply Chain Management, jeśli faktury niezależne mają stan księgowania **W trakcie przetwarzania**.</span><span class="sxs-lookup"><span data-stu-id="15d15-123">Updates to these invoices will be synchronized to the free text invoices in Supply Chain Management if the accounting status of the free text invoices is **In process**.</span></span> <span data-ttu-id="15d15-124">Po zaksięgowaniu faktur niezależnych w programie Supply Chain Management i zaktualizowaniu stanu księgowania na **Zakończone** nie będzie można synchronizować aktualizacji z programu Field Service.</span><span class="sxs-lookup"><span data-stu-id="15d15-124">After the free text invoices are posted in Supply Chain Management, and the accounting status is updated to **Completed**, you can no longer synchronize updates from Field Service.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="15d15-125">Rozwiązanie CRM Field Service</span><span class="sxs-lookup"><span data-stu-id="15d15-125">Field Service CRM solution</span></span>

<span data-ttu-id="15d15-126">Do tabeli **Faktury** dodano kolumnę **Zawiera wiersze ze źródłem umowy**.</span><span class="sxs-lookup"><span data-stu-id="15d15-126">The **Has Lines With Agreement Origin** column has been added to the **Invoice** table.</span></span> <span data-ttu-id="15d15-127">Ta kolumna pomaga zagwarantować, że są synchronizowane tylko faktury utworzone na podstawie umowy.</span><span class="sxs-lookup"><span data-stu-id="15d15-127">This column helps guarantee that only invoices that are created from an agreement are synchronized.</span></span> <span data-ttu-id="15d15-128">Wartością jest **prawda**, jeśli faktura zawiera co najmniej jeden wiersz faktury pochodzący z umowy.</span><span class="sxs-lookup"><span data-stu-id="15d15-128">The value is **true** if the invoice contains at least one invoice line that originates from an agreement.</span></span>

<span data-ttu-id="15d15-129">Do tabeli **Wiersz faktury** dodano kolumnę **Zawiera źródło umowy**.</span><span class="sxs-lookup"><span data-stu-id="15d15-129">The **Has Agreement Origin** column has been added to the **Invoice Line** table.</span></span> <span data-ttu-id="15d15-130">Ta kolumna pomaga zagwarantować, że są synchronizowane tylko wiersze faktury utworzone na podstawie umowy.</span><span class="sxs-lookup"><span data-stu-id="15d15-130">This column helps guarantee that only invoice lines that are created from an agreement are synchronized.</span></span> <span data-ttu-id="15d15-131">Wartością jest **prawda**, jeżeli wiersz faktury pochodzi z umowy.</span><span class="sxs-lookup"><span data-stu-id="15d15-131">The value is **true** if the invoice line originates from an agreement.</span></span>

<span data-ttu-id="15d15-132">Pole **Data faktury** jest wymagane w aplikacji Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="15d15-132">**Invoice date** is a mandatory field in Supply Chain Management.</span></span> <span data-ttu-id="15d15-133">W związku z tym kolumna musi mieć wartość w programie Field Service, zanim będzie mogła nastąpić synchronizacja.</span><span class="sxs-lookup"><span data-stu-id="15d15-133">Therefore, the column must have a value in Field Service before synchronization occurs.</span></span> <span data-ttu-id="15d15-134">Aby spełnić ten wymóg, dodano następującą logikę:</span><span class="sxs-lookup"><span data-stu-id="15d15-134">To meet this requirement, the following logic is added:</span></span>

- <span data-ttu-id="15d15-135">Jeśli kolumna **Data faktury** jest puste w tabeli **Faktura** (tzn. jeśli nie ma wartości), jest w nim ustawiana bieżąca data podczas dodawania wiersza faktury pochodzącego z umowy.</span><span class="sxs-lookup"><span data-stu-id="15d15-135">If the **Invoice Date** column is blank on the **Invoice** table (that is, if it has no value), it's set to the current date when an invoice line that originates from an agreement is added.</span></span>
- <span data-ttu-id="15d15-136">Użytkownik może zmienić wartość w kolumnie **Data faktury**.</span><span class="sxs-lookup"><span data-stu-id="15d15-136">The user can change the **Invoice Date** column.</span></span> <span data-ttu-id="15d15-137">Jednak gdy użytkownik próbuje zapisać fakturę pochodzącą z umowy, widzi błąd procesu biznesowego, jeśli kolumna **Data faktury** jest pusta na fakturze.</span><span class="sxs-lookup"><span data-stu-id="15d15-137">However, when the user tries to save an invoice that originates from an agreement, he or she receives a business process error if the **Invoice Date** column is blank on the invoice.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="15d15-138">Wymagania wstępne i ustawienia mapowania</span><span class="sxs-lookup"><span data-stu-id="15d15-138">Prerequisites and mapping setup</span></span>

### <a name="in-supply-chain-management"></a><span data-ttu-id="15d15-139">W Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="15d15-139">In Supply Chain Management</span></span>

<span data-ttu-id="15d15-140">Na potrzeby integracji należy skonfigurować pochodzenie faktury, tak aby w programie Supply Chain Management odróżniać faktury niezależne utworzone na podstawie faktur za umowy w programie Field Service.</span><span class="sxs-lookup"><span data-stu-id="15d15-140">An invoice origin must be set up for the integration, to distinguish the free text invoices in Supply Chain Management that are created from agreement invoices in Field Service.</span></span> <span data-ttu-id="15d15-141">Gdy faktura ma pochodzenie typu **Integracja faktury dotyczącej umowy**, pole **Zewnętrzny numer faktury** jest wyświetlane w nagłówku **Faktura sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="15d15-141">When an invoice has an invoice origin of the **Agreement invoice integration** type, the **External invoice number** field is shown on the **Sales invoice** header.</span></span>

<span data-ttu-id="15d15-142">Informacje z pola **Zewnętrzny numer faktury** nie tylko pojawiają się w nagłówku faktury, ale mogą również pomóc zagwarantować, że faktury tworzone na podstawie faktur za umowy w programie Field Service są odfiltrowywane podczas synchronizacji faktur między programami Supply Chain Management i Field Service.</span><span class="sxs-lookup"><span data-stu-id="15d15-142">Besides appearing on the invoice header, the **External invoice number** information can be used to help guarantee that invoices that are created from Field Service agreement invoices are filtered out during invoice synchronization from Supply Chain Management to Field Service.</span></span>

1. <span data-ttu-id="15d15-143">Wybierz kolejno opcje **Rozrachunki z odbiorcami** \> **Ustawienia** \> **Kody pochodzenia faktur**.</span><span class="sxs-lookup"><span data-stu-id="15d15-143">Go to **Accounts receivable** \> **Setup** \> **Invoice origin codes**.</span></span>
2. <span data-ttu-id="15d15-144">Wybierz opcję **Nowy**, aby utworzyć nowe pochodzenie faktury.</span><span class="sxs-lookup"><span data-stu-id="15d15-144">Select **New** to create a new invoice origin.</span></span>
3. <span data-ttu-id="15d15-145">W polu **Pochodzenie faktury** nadaj nazwę pochodzeniu faktury, taką jak **FS**.</span><span class="sxs-lookup"><span data-stu-id="15d15-145">In the **Invoice origin** field, enter a name for the invoice origin, such as **FS**.</span></span>
4. <span data-ttu-id="15d15-146">W polu **Opis** wprowadź opis, taki jak **Faktura za umowę w programie Field Service**.</span><span class="sxs-lookup"><span data-stu-id="15d15-146">In the **Description** field, enter a description, such as **Field Service Agreement Invoice**.</span></span>
5. <span data-ttu-id="15d15-147">Zaznacz pole wyboru **Przypisanie typu pochodzenia**.</span><span class="sxs-lookup"><span data-stu-id="15d15-147">Select the **Origin type assignment** check box.</span></span>
6. <span data-ttu-id="15d15-148">W polu **Typ pochodzenia faktury** ustaw wartość **Integracja faktury dotyczącej umowy**.</span><span class="sxs-lookup"><span data-stu-id="15d15-148">Set the **Invoice origin type** field to **Agreement invoice integration**.</span></span>
7. <span data-ttu-id="15d15-149">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="15d15-149">Select **Save**.</span></span>

### <a name="in-the-data-integration-project"></a><span data-ttu-id="15d15-150">W projekcie integracji danych</span><span class="sxs-lookup"><span data-stu-id="15d15-150">In the Data Integration project</span></span>

<span data-ttu-id="15d15-151">Zadanie: **Wiersze faktury**</span><span class="sxs-lookup"><span data-stu-id="15d15-151">Task: **Invoice lines**</span></span>  

<span data-ttu-id="15d15-152">Upewnij się, że wartość domyślna pola **Wartość wyświetlana konta głównego** w programie Supply Chain Management została zaktualizowana i jest zgodna z żądaną wartością.</span><span class="sxs-lookup"><span data-stu-id="15d15-152">Make sure that the default value for the Supply Chain Management field **Main Account Display Value** is updated to match the desired value.</span></span>

<span data-ttu-id="15d15-153">Wartość domyślna w szablonie to **401100**.</span><span class="sxs-lookup"><span data-stu-id="15d15-153">The default template value is **401100**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="15d15-154">Mapowanie szablonu w integracji danych</span><span class="sxs-lookup"><span data-stu-id="15d15-154">Template mapping in Data integration</span></span>

<span data-ttu-id="15d15-155">Na poniższych ilustracjach pokazano mapowanie szablonu w narzędziu Integracja danych.</span><span class="sxs-lookup"><span data-stu-id="15d15-155">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="agreement-invoices-field-service-to-supply-chain-management-invoice-headers"></a><span data-ttu-id="15d15-156">Faktury za umowy (rozwiązanie Field Service do Supply Chain Management): Nagłówki faktur</span><span class="sxs-lookup"><span data-stu-id="15d15-156">Agreement invoices (Field Service to Supply Chain Management): Invoice headers</span></span>

<span data-ttu-id="15d15-157">[![Mapowanie szablonu w integracji danych](./media/FSFreeTextInvoice1.png)](./media/FSFreeTextInvoice1.png)</span><span class="sxs-lookup"><span data-stu-id="15d15-157">[![Template mapping in Data integration](./media/FSFreeTextInvoice1.png)](./media/FSFreeTextInvoice1.png)</span></span>

### <a name="agreement-invoices-field-service-to-supply-chain-management-invoice-lines"></a><span data-ttu-id="15d15-158">Faktury za umowy (rozwiązanie Field Service do Supply Chain Management): Wiersze faktur</span><span class="sxs-lookup"><span data-stu-id="15d15-158">Agreement invoices (Field Service to Supply Chain Management): Invoice lines</span></span>

<span data-ttu-id="15d15-159">[![Mapowanie szablonu w integracji danych](./media/FSFreeTextInvoice2.png)](./media/FSFreeTextInvoice2.png)</span><span class="sxs-lookup"><span data-stu-id="15d15-159">[![Template mapping in Data integration](./media/FSFreeTextInvoice2.png)](./media/FSFreeTextInvoice2.png)</span></span>
